A foundation model is any model that is trained on broad data at scale and can be adapted (e.g., fine-tuned) to a wide range of downstream tasks; current examples include BERT [Devlin et al. 2019], GPT-3 [Brown et al. 2020], and CLIP [Radford et al. 2021].

 ![[Pasted image 20220608104028.png]]

From a technological point of view, foundation models are not new — they are based on deep neural networks and self-supervised learning, both of which have existed for decades.

**what’s really innovative is the scale** at which these models are created

![[Pasted image 20220608104325.png]]

The foundation model can also be multi-modal, meaning it can work with several modalities (content-types) at once, e.g. CLIP and DALL·E models from OpenAI work with both image and texts.

The significance of foundation models can be summarized with two words: emergence and homogenization. Emergence means that the behavior of a system is implicitly induced rather than explicitly constructed; it is both the source of scientific excitement and anxiety about unanticipated consequences. Homogenization indicates the consolidation of methodologies for building machine learning systems across a wide range of applications; it provides strong leverage towards many tasks but also creates single points of failure.

基础模型是任意的在大规模数据上训练并且可以适配(例如，微调)广泛下游任务的模型;当前的例子包括BERT[Devlin et al. 2019]、GPT-3 [Brown et al. 2020]和CLIP[Radford et al. 2021]。从技术角度来看，基础模型并不新鲜—它们基于深度神经网络和自监督学习，两者都已经存在了几十年。然而，过去几年基础模型的庞大规模和应用范围已经超出了我们对其可能性的想象。例如，GPT-3有1750亿个参数，尽管没有在特定任务上进行明确的训练，仍可以通过自然语言提示(prompts)适配到特定任务上，在大多数任务上取得了不错的效果 [Brown et al. 2020]。

在无数科幻片中，机器人拥有了人一样的智能，甚至最终统治人类。这类机器人远远超越了普通AI层面，实现了AGI（通用人工智能），即拥有人一样的智能，可以像人一样学习、思考、解决问题。

斯坦福大学学者谈到的基础模型，国际上也称预训练模型，也被国内研究者称为大模型。

大模型成了最近AI产学界刷屏率颇高的词汇。需要更大算力、更大数据集的大模型，为何可能是未来AI最好的伙伴？这要从AI开发者们的一次次挫败与碰壁说起。

深度学习技术兴起的近10年间，AI模型基本上是针对特定应用场景需求进行训练的小模型。小模型用特定领域有标注的数据训练，通用性差，换到另外一个应用场景中往往不适用，需要重新训练。另外，小模型的训练方式基本是“手工作坊式”，调参、调优的手动工作太多，需要大量的AI工程专业人员来完成。同时，传统模型训练需要大规模的标注数据，如果某些应用场景的数据量少，训练出的模型精度就会不理想。

小模型的这些问题，导致当前AI研发整体成本较高，效率偏低。由于AI人才短缺以及成本昂贵，对于中小行业用户来说，小模型的这些问题阻碍了行业用户采用人工智能技术的脚步，成为AI普惠的障碍。

虽然，之前全球呈现“千村万户大炼模型”的热闹场面，但这种“自家炼钢自己用”的作坊方式显然不符合现代产业发展规律。
 
 大模型可以解决这些问题，其泛化能力强，可以做到‘举一反三’，同一模型利用少量数据进行微调或不进行微调就能完成多个场景的任务，中小企业可以直接调用，不需要招聘很多AI算法专业人员就能进行应用开发，显著降低中小企业的研发门槛，促进AI技术落地。
 
 得益于这些优势，人工智能的发展已经从“大炼模型”逐步迈向“炼大模型”的阶段。以美国OpenAI、谷歌、微软、脸书等机构为代表，布局大规模智能模型已成为全球引领性趋势，并形成了GPT—3、Switch Transformer等千亿或万亿参数量的大模型。可以说，人工智能大模型时代正在到来！
 
 人工智能大模型是‘大数据+大算力+强算法’结合的产物，是集成大数据内在精华的‘隐式知识库’，也是实现人工智能应用的载体。大模型是连接人工智能技术生态和产业生态的桥梁，向下带动基础软硬件发展，向上支撑了智能应用百花齐放，是整个人工智能生态的核心。
 
 未来，大模型会形成类似电网的智能基础平台，像发电厂一样为全社会源源不断地供应‘智力源’。
 
 类比人的教育培养，大模型所完成的培训就如同基础性、通识性的大学本科培养，“学成”后的大模型具备处理一般事物的能力。如果要完成更专业、更高级的任务，大模型还需要“研究生”阶段的专业培养。
 
 AI大模型通常是在大规模无标注数据上进行训练，学习数据中蕴含的特征、结构和知识。
 
 超大规模预训练模型的出现，很可能改变信息产业格局，即基于数据的互联网时代、基于算力的云计算时代之后，接下来可能将进入基于大模型的AI时代。
 
 认为大模型的特点之一是“同质化”，好处在于大模型的任何一点改进就可以迅速覆盖整个AI社区。但同时，它也带来一些隐患，大模型的缺陷会被所有下游模型所继承。特点之二是海量数据训练出的基础模型具有“涌现”特性，也就是产生未曾预先设想的新能力，这种特性有望让AI具备处理语言、视觉、机器人、推理、人际互动等各类相关任务的能力。因此这类模型将赋能各行各业，加快行业的智能化转型，在法律、医疗、教育等领域都会带来具有社会价值的影响。
 

前段时间的微软开发者大会上，微软 CEO 萨提亚·纳德拉公布了辅助开发者进行编程的GitHub Copilot 工具，GitHub Copilot 工具由 OpenAI 开发的全新 AI 系统 OpenAI Codex 提供支持。Codex 基于 GPT-3 自然语言处理模型演化而来，基于开源代码和自然语言进行了训练，可以理解编程语言和人类语言，并独立生成各种形式的文本。上面提到的GPT-3便属于近来年在人工智能领域颇受追捧的大模型，之所以称为大模型，是因为训练这样一个模型需要更大算力、更大数据集并且模型包含的参数也更多。像GPT-3模型，训练一次需要耗费1200万美元，训练数据集达到570G，包含1750亿个参数。大模型之所以受追捧，是因为只需要对大模型进行微调，便可以适用于各个特定的领域。这和之前的模型形成了鲜明的对比，之前的AI模型基本上是针对特定应用场景需求进行训练的小模型。小模型用特定领域有标注的数据训练，通用性差，换到另外一个应用场景中往往不适用，需要重新训练，这极大阻碍了AI模型的大规模应用。但是，大模型是机遇也是挑战，大模型的特点之一是“同质化”，好处在于大模型的任何一点改进就可以迅速覆盖整个AI社区。但同时，它也带来一些隐患，大模型的缺陷会被所有下游模型所继承。特点之二是海量数据训练出的基础模型具有“涌现”特性，也就是产生未曾预先设想的新能力，这种特性有望让AI具备处理语言、视觉、机器人、推理、人际互动等各类相关任务的能力。尽管大模型已经展示了初步潜力，但仍处于早期阶段，我们对其知之甚少，围绕着大模型的规范也不够完善。在通过强人工智能的道路，我们只是迈出了万里长征的第一步，以后还有很长的路要走。