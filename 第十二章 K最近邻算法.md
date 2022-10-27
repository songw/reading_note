#data-science/tutorial/chapter12
# 第十二章 $k$近邻算法
$k$ 近邻法（k-nearest neighbor，k-NN）是一种基本分类与回归方法，是由  Cover 和 Hart 在1968 年提出的。本节课只讨论分类问题中的 $k$ 近邻法，它简单直观，假设给定一个训练数据集，对新的输入实例，在训练数据集中找到与该实例最近邻的 $k$ 个实例，这 $k$ 个实例的多数属于某个类，就把该输入实例分为这个类。

我们通过下面这幅图来更加直观地了解下$k$ 近邻算法。

![[knn.jpeg]]

在图中，红色的正方形为待分类的物体。首先计算待分类物体和训练集中各个物体的距离，当 $k=3$ 时，距离正方形物体最近的三个点中有一个五角星和两个三角形，按照多数表决的决策规则，待分类的物体应该属于三角形的类别；当 $k=9$ 时，距离正方形物体最近的九个点中有五个五角星和四个三角形，按照多数表决的决策规则，待分类的物体应该属于五角星的类别。

下面看下具体的算法描述：
输入：训练数据集
$$T = {(x_1,y_1),(x_2,y_2),...,(x_N,y_N)}$$
其中，$x_i \in \mathcal{X} \subseteq R^n$ 为实例的特征向量，$y_i \in \mathcal{Y} = \{c_1,c_2,...,c_K\}$ 为实例的类别，$i = 1,2,...,N$；

输出：实例 $x$ 所属的类 $y$。
算法的流程如下：
1. 根据给定的距离度量，在训练集 $\boldsymbol {T}$ 中找出与 $x$ 最邻近的 $k$ 个点，涵盖这 $k$ 个点的 $x$ 的邻域记作 $N_k(x)$。
2. 在 $N_k(x)$ 中根据分类决策规则（如多数表决）决定 $x$ 的类别 $y$。

从算法流程中可以看出，算法有三个基本要素，分别是距离度量、$k$ 值的选择和分类决策规则决定。当训练集、距离度量（如欧氏距离）、$k$ 值及分类决策规则（如多数表决）确定后，对于任何一个新的输入实例，它所属的类唯一地确定。


### 距离计算
特征空间中两个实例点之间的距离反映了两个实例点的相似程度。距离越大，相似度越小；距离越小，相似度越大。$k$ 近邻模型的特征空间一般是 $n$ 维实数向量空间 $R^n$。使用的距离是欧式距离，但也可以是其他距离，如更一般的 $L_p$（$L_p$ distance） 距离或闵可夫斯基距离（Minkowski distance）。
设特征空间 $\mathcal{X}$ 是 $n$ 维实数向量空间 $R^n$，$x_i$，$x_j$ $\in$ $\mathcal{X}$，$x_i$ = ($x_i^{(1)}$, $x_i^{(2)}$ ,..., $x_i^{(n)}$)$^T$，$x_j$ = ($x_j^{(1)}$, $x_j^{(2)}$ ,..., $x_j^{(n)}$)$^T$，$x_i$，$x_j$ 的 $L_p$ 距离定义为<br> <center>$L_p(x_i, y_i)$ = $\Bigg(\displaystyle \sum^n_{l=1}|x_i^{(l)}-x_j^{(l)}|^p\Bigg)^\frac{1}{p}$， $p \geq 1$，</center><br>当 $p = 2$时，称为欧式距离，即 <br><center>$L_2(x_i, y_i)$ = $\Bigg(\displaystyle \sum^n_{l=1}|x_i^{(l)}-x_j^{(l)}|^2\Bigg)^\frac{1}{2}$，<br></center>当 $p = 1$ 时，称为曼哈顿距离，即 <br><center>$L_1(x_i, y_i)$ = $\displaystyle \sum^n_{l=1}|x_i^{(l)}-x_j^{(l)}|$，<br></center>当 $p = \infty$ 时，它是各个坐标距离的最大值，即 <br><center>$L_\infty(x_i, y_j) = \mathop{max}\limits_{l}|x_i^{(l)}-x_j^{(l)}|$，<br></center>称为切比雪夫距离。

**举个例子：**
已知二维空间的 3 个点 $x_1 = (2,2)^T, x_2=(10,2)^T, x_3=(8,8)^T$，试求在不同的距离公式下，$x_1$ 的最近邻点。

当使用欧氏距离时：
$x_1$ 到 $x_2$ 的距离为：8
$x_1$ 到 $x_3$ 的距离为：8.48

当使用曼哈顿距离时：
$x_1$ 到 $x_2$ 的距离为：8
$x_1$ 到 $x_3$ 的距离为：12

### $k$ 值的选择
$k$ 值的选择会对 $k$ 近邻法的结果产生重大影响。如果选择较小的 $k$ 值，就相当于用较小的邻域中的训练实例进行预测，”学习“的近似误差（可以理解为对现有训练集的训练误差）会减小，只有与输入实例较近的训练实例才会对预测结果起作用。但缺点是”学习“的估计误差（可以理解为对测试集的测试误差）会增大，预测结果会对临近的实例点非常敏感。如果邻近的实例点恰巧是噪声，预测就会出错。换句话说，$k$ 值的减小就意味着整体模型变得复杂，容易发生过拟合。

如果选择较大的 $k$ 值，就相当于用较大邻域中的训练实例进行预测。其优点是可以减少学习的估计误差，但缺点是学习的近似误差会增大。这时与输入实例较远的训练实例也会对预测起作用，使预测发生错误。$k$ 值的增大就意味着整体的模型变得简单。

如果 $k = N$，那么无论输入实例是什么，都将简单地预测它属于在训练实例中最多的类。这时，模型过于简单，完全忽略训练实例中的大量有用信息，是不可取的。

在应用中，$k$ 值一般取一个比较小的数值。通常采用交叉验证法来选取最优的 $k$ 值。

### 分类决策规则
$k$ 近邻法中的分类决策规则往往是多数表决，即由输入实例的 $k$ 个邻近的训练实例中的多数类决定输入实例的类。

## 两个例子
### 鸢尾花的分类
![[Pasted image 20220722105617.png]]
鸢尾花的分类问题属于监督学习中比较经典的问题。鸢尾花有三个类别，分别为山鸢尾（Iris Setosa）、杂色鸢尾（Iris Versicolour）和维吉尼亚鸢尾（Iris Virginica）。每个类别的鸢尾花都有四个属性，分别是花萼长度（SepalLength）、花萼宽度（SepalWidth）、花瓣长度（PetalLength）以及花瓣宽度（PetalWidth）。鸢尾花的分类问题就是通过花萼长度、花萼宽度、花瓣长度以及花瓣宽度的值来对鸢尾花进行分类。下面我们通过 Scikit-learn 中的 $k$-NN 算法对鸢尾花进行分类。
1. 导入库
```python
import pandas as pd
from sklearn import metrics
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.preprocessing import StandardScaler
```
2. 读取数据
```python
iris_data = pd.read_csv('Iris.csv')
```
3. 将数据集分成训练数据集和测试数据集
```python
y = iris_data['Species']
x = iris_data[['SepalLengthCm', 'SepalWidthCm', 'PetalLengthCm', 'PetalWidthCm']]
train_x, test_x, train_y, test_y = train_test_split(x, y, test_size=0.3, random_state=33)
```
4. 使用训练数据对模型进行训练，并使用得到的模型对测试数据进行测试。
```python
knn = KNeighborsClassifier()
knn.fit(train_x, train_y)
predict_y = knn.predict(test_x)
```
5. 输出测试结果
```python
print("KNN准确率: %.4lf" % accuracy_score(test_y, predict_y))
```
6. output
```pyhton
KNN准确率: 0.9556
```

### 糖尿病的预测
糖尿病的预测是根据患者的一些信息来预测患者是否有糖尿病。下面我们通过 Scikit-learn 中的 $k$-NN 算法对患者是否患有糖尿病进行预测。
1. 导入库
```python
import pandas as pd
from sklearn import metrics
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.preprocessing import StandardScaler
```
2. 读取数据
```python
diabetes_data = pd.read_csv('diabetes.csv')
```
3. 对数据进行清洗，对于某列数据中的0值，使用这一列值的平均值进行填充。
```python
diabetes_data.replace({
    'Glucose': 0,
    'BloodPressure': 0,
    'SkinThickness': 0,
    'BMI': 0,
    'Insulin': 0
}, np.NaN, inplace=True)

glucose_mean = diabetes_data['Glucose'].mean()
blood_pressure_mean = diabetes_data['BloodPressure'].mean()
skin_thickness_mean = diabetes_data['SkinThickness'].mean()
bmi_mean = diabetes_data['BMI'].mean()
insulin_mean = diabetes_data['Insulin'].mean()

diabetes_data['Glucose'].replace(np.NaN, glucose_mean, inplace=True)
diabetes_data['BloodPressure'].replace(np.NaN, blood_pressure_mean, inplace=True)
diabetes_data['SkinThickness'].replace(np.NaN, skin_thickness_mean, inplace=True)
diabetes_data['BMI'].replace(np.NaN, bmi_mean, inplace=True)
diabetes_data['Insulin'].replace(np.NaN, insulin_mean, inplace=True)
```
4. 将数据集分成训练数据集和测试数据集。
```python
y = diabetes_data['Outcome']
x = diabetes_data[['Pregnancies', 'Glucose', 'BloodPressure', 'SkinThickness', 'Insulin', 'BMI', 'DiabetesPedigreeFunction', 'Age']]
train_x, test_x, train_y, test_y = train_test_split(x, y, test_size=0.2, random_state=0)
```
5. 对数据进行规范化。
```python
sc_x = StandardScaler()
train_x = sc_x.fit_transform(train_x)
test_x = sc_x.fit_transform(test_x)
```
6. 使用训练数据对模型进行训练，并使用得到的模型对测试数据进行测试。
```python
knn = KNeighborsClassifier(n_neighbors=11, metric='euclidean', p=2, weights='uniform', algorithm='auto', leaf_size=30)
knn.fit(train_x, train_y)
predict_y = knn.predict(test_x)
```
7. 输出测试结果
```python
print("KNN准确率: %.4lf" % accuracy_score(test_y, predict_y))
```
8. output
```python
KNN准确率: 0.8052
```
