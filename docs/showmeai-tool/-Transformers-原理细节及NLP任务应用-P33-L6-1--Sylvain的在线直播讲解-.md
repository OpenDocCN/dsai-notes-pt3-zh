#  Transformers 原理细节及NLP任务应用！P33：L6.1- Sylvain的在线直播讲解 

不过我觉得是时候开始了，欢迎来到这个课程，我们将一起学习第一章，这里是提问的最佳场所，请在聊天中提问，我会每五到十分钟查看一次聊天，阅读问题并尽量回答。

这个课程的目的如我所说，这一节将涵盖第一章，这一章旨在非常一般性地介绍变换模型的功能，所以你不需要担心目前的设置，几个好的样本将展示如何在coab中直接运行它们。

另一个是Greenface网站。我不会再看介绍视频，因为你可以在自己的时间里观看，视频内容没有什么信息。第一部分的目标，可能就是现在这个粉色部分，是为了向你介绍变换模型，今天的网络结构，并教你如何从Eb下载预训练模型，找出自己的数据以进行文本分类任务。

然后将结果传回模型。在第二部分，我们将更深入探讨所有NLP任务如何调整文本分类，而课程的最后一部分将进一步深入。因此第二部分将在秋季发布，第三部分将在明年初发布。

一旦你完成了这部分课程，你应该能够下载该模型，并在自己的问题上进行使用。然后，创建一个较小的上传，结果将传回中心。因此你应该查看论坛，我将展示如何讨论这个阶段。

接下来，你将在这个直播结束后，可以在课程类别中提出任何问题，每章都有一个讨论区供你提问，并且我会密切关注另一个讨论区，所以请分享你的项目主题，确保分享在学习课程第一部分后所做的任何构建。

嗯，好的。那么让我们深入探讨吧。如果现在没有任何一般性问题，我们就开始第一章。变换模型主要用于处理NLP任务，而NLP代表自然语言处理，这是一个与语言相关的领域。因此，NLP任务的目标是对一些文本进行分类。

例如，获取评论的情感，检测邮件是否为垃圾邮件，判断某个在线评论是友好还是不友好，判断句子是否语法正确，等等。我们的任务可以是对文本中的词汇进行分类，例如，能够解析语法成分，以判断这个词是人名、地点还是组织。

另一种NLP任务是生成文本内容。因此，完成一个提示是Jo smartF在你尝试撰写消息时所做的。通常它会建议使用X，甚至Gmail现在在邮件中也这样做。嗯。填充B syn文本，这是另一种文本生成。另一种任务是从文本中提取答案。

因此，给定一个非常长的文本，然后一个问题，模型能够提取该问题的答案。答案是从上下文中提取，或根据输入文本生成这些新句子。例如，生成文本的翻译，总结我最近看到的一个新文本的内容。

例如，一种随意风格或更正式的风格。所以这些都是课程中，特别是第2部分将要处理的各种enLP任务。而且这相当具有挑战性，因为计算机处理信息的方式与我们不同。因此，一个新的变换模型让你可以深入学习。

能够从你有标签的几个样本中恰当地进行概括，而不需要你去创建。例如，在深度学习盛行之前，一件事情是解析文本并有一些特殊规则，如果我看到这个词，也许意味着这是积极的；如果我看到这个词，也许意味着这是消极的，等等。对吧。所以这不是现在所做的，主要是使用可变换模型和再次使用face库。

这些模型，如果你还没有，你应该跟随一个深度学习课程的介绍。这些模型通常是经过训练的，并不遵循人类编写的一组特定规则。它们有权重，遵循一种称为梯度下降的算法，并根据输入的训练数据，它们在每一步使损失函数或指标变得更好，因此我们最终得到的模型有点像一个黑匣子。但我们可以使用并在数据上进行良好的概括，但看起来与训练集的数据相似。

所以让我们看看这个模型在实践中能做什么。因此，我们有两种方式可以做到这一点，第一种方式是点击这个“在颜色中打开”按钮。所以Collab是由谷歌维护的平台，提供免费的资源访问，例如在Jupyter Notebook环境中的GPU或TPU。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_1.png)

所以，你可以直接执行。好。![](img/1b5e5fce582c60e42117fe3a72e59e6a_3.png)

在其中。因此，第一个单元需要执行以安装我将要使用的所有库。我会让它运行，我们会稍微了解一下课程，然后我们就能运行其他好的样本，我稍后会回到那个窗口。所以变换模型无处不在，现在许多公司都在使用它们，这些是使用Gface模型的公司的示例，我们有预训练的模型，并可能在内部使用它们。

Transformers 库是提供访问这些模型的主要接口库。我们将快速浏览一下。稍后模型应用是所有后训练模型的所在，它是整个生态系统的一部分，我们将能够在稍后的模型应用中运行与在 Coab 笔记本上尝试的相同代码。您需要做的事情是访问论坛并能够玩弄所有模型，点击章节 1 中的链接。

所以我们首先来看更高层次的 API 对象，称为管道计划函数。![](img/1b5e5fce582c60e42117fe3a72e59e6a_5.png)

我会给大家几分钟时间。只是想给视频一些加载时间，并且回答你们在聊天中提出的任何问题。所以，我看到的第一个问题是，LSTM 模型（如 OMF）是否仍然有用？如果有，它们在哪些方面优于变压器模型，或者至少应该被考虑？这是一个非常好的问题。

非常好的问题，确实仍然有 LSTM 模型的应用。当前变压器模型被广泛使用的主要原因是计算效率更高，尤其是在硬件 TPU 和 GPU 上，因为 LSTM 依赖于递归机制，而这种机制的优化相对较难。不过，例如，LSTM 在 EMDB 数据集上取得了非常好的先进结果，该数据集用于电影评论分类。最近才发现变压器模型在该任务上的表现，我认为这与 EMDB 评论非常长有关，而变压器模型在处理较长序列时表现良好。

通常来说，它是 512，但对于 12 来说，如果有超过这个长度的内容，似乎 LSTM 模型可以看到。这将是一个非常好的选择。另一个问题，我会在这个视频之后回答，因为它是关于管道的。所以，嗯，让我们先看视频，我会从屏幕上消失，这样你们可以不受干扰地观看，视频结束后我会回来。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_7.png)

这是管道结束函数。管道函数是 Transformers 库中最高层次的 API。它将所有步骤组合在一起，从文本到可用的预测。使用的模型本质上是一个管道，但管道还包含所有必要的预处理，因为模型并不期望文本，而是数字。同时还包括一些后处理，使模型的输出易于人类理解。

让我们看一下保罗与情感分析管道的第一阶段。该管道对给定输入执行文本分类，并确定它是正面还是负面。这里它将正面标签归因于给定文本，置信度为 95%。你可以将多个文本传递给同一管道，这些文本将作为批处理一起处理并传递给模型。

输出是与输入文本顺序相同的个别结果列表。这里我们发现第一个文本的分数标签相同。第二个文本的标签是 church negative，置信度为 99.9%。零-shot 分类管道是一种更通用的文本分类管道。

它允许你提供想要的标签。这里我们想沿着教育、政治和商业的标签对输入文本进行分类。管道成功识别出它与教育标签的关系比与瑜伽标签更密切，置信度为 84%。接下来，我们的任务是文本生成管道，它将完成给定提示。输出是带有一点随机性的生成，因此每次在给定提示上调用生成器对象时都会有所不同。

直到现在，我们一直使用与每个任务相关的默认模型的 Biman APIpi。但你可以使用任何已经经过自由训练或微调的模型。哦。继续使用模型 H，再次是 F dogo slash models。你可以按任务过滤可用模型。我们之前示例中使用的默认成人模型是 GPT2。

但还有许多其他可用模型，而不仅仅是英文。让我们回到下一个生成管道，并用另一个模型 distill JPT2 加载它。这是由 Eingface 团队创建的 GT2 的轻量版本。将管道应用于给定提示时，我们可以指定多个参数。

例如生成文本的最大长度，以及我们想返回的句子数，因为生成中存在一些随机性。通过猜测 X12 生成文本是强度很大的，这也是 GPT2 的预训练目标。领域质量管道是 Bro 的一个预训练目标，目的是猜测质量的值。在这种情况下，我们根据模型询问两个最可能缺失单词的值。

并尽可能获得数学或计算方面的答案。任务转换模型的形式是对句子中的每个单词进行分类，而不是将整个句子作为一个整体。例如，这就是命名实体识别，它的任务是在句子中识别如人、组织或地点等实体。这里，模型正确识别了人，sva。

组织 Gface 以及输入文本中的布鲁克林位置。该组实体 equal2 参数的使用是将与同一实体相关的不同墙壁聚集在一起，例如这里的 eggging 和 face。通过 byg API 提供的新任务是提取式问题和对不起。提供一个上下文和一个问题，模型将识别上下文中包含答案的文本范围。

获取非常长文本的简短摘要也是Transformers库可以帮助的，特别是在摘要方面。最后，B API支持的最后一个任务是翻译。在这里，我们使用一个法英模型，从Mo Hub找到，用于获取我们快速文本的英文版本。这里是我们在这个视频中研究的所有任务的简要总结，可以通过现代Hub中的影响切换进行尝试。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_9.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_10.png)

是的。抱歉一开始的歌曲，我试着让自己更好，我不能在播放视频的同时专心，所以那部分似乎已经处理过了，对于延迟的问题，我尝试找到解决方案，但我不知道可能是什么，所以下一个视频可能会更好，我试着最小化操作系统，画面可能会更好。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_12.png)

所以我在视频前跳过的问题是，当你进行管道情感分析时，如何确定使用的是哪个模型，狗字符串并没有太大帮助。确实，它没有在文档中，我们可能应该努力使其更好地记录，最好的方法是检查源代码，现在我将给你展示这一点。所以，你需要继续。

进入管道，这是个很好的问题，实际上我们使其更易于访问和查看，但你需要进入管道模块的源代码，在文件中，你会看到每个管道所使用的默认模型，所以在这里我们使用文本分类和情感分析的默认模型是基于SS2英语的。

不知道为什么那个人没有选择一个短名字，但这就是它的名字。让我看看还有没有其他问题。是的，我会在聊天中发送下一个视频的链接，或者你可以同时在课程章节中跟随并直接查看它们，好的，看起来有很多其他问题，所以让我们继续。那么这一章。

所以本节的其余部分只是视频中展示的良好示例。所以我不打算详细介绍，而是要看看我的调用，希望。应该是。![](img/1b5e5fce582c60e42117fe3a72e59e6a_14.png)

我需要重启自己的时间，所有都是美好的。![](img/1b5e5fce582c60e42117fe3a72e59e6a_16.png)

希望重新安装所有内容不会花太长时间。好好好。你为什么要和我在一起？好的。这样对你会更顺畅一点。一旦我们安装了Transformers库，我们可以运行第一个单元，例如。与视频中的内容相同，没错。V是刚发布的最新版本的书。

所以我们无法在Collab上运行任何东西。这也很棒。不确定我们能否以某种方式获取你的版本。あ。好的，所以希望Pytoch的工作人员能尽快修复这个bug，你们都能在此期间轻松运行所有的collapse。

我将尝试在tripyter笔记本中向你展示同样的事情，我不打算做可以运行的事情。Ge。所以让我去。我不会在这里。所以如果你更喜欢在本地赢得笔记本。所有内容都在名为Notes的报告中，里面有一个Eing F Or，使用这个笔记本你有一个课程子文件夹，当你按章节或直接用于视频时。所以让我们看看。我们尝试在Collab中运行的同一个笔记本。放大一点。

让我们减少一点，好吗。所以在运行安装后。我不需要这样做，因为我已经安装好一切。你可以运行我们在视频中看到的代码，可以随意更改，试试其他句子，同时尝试多个句子。两次那里写的分类管道，和我们在视频中看到的所有管道。

😊，接下来。你可以尝试所有这些的另一种方式是模型。嗯。规范教育。不得有你怎么样。诶。你可以去的地方，所以模型会出现，你可以点击任何模型。例如，如果我们去，并将蒸馏基于案例好的转成英语。这是我们看到的情感分析管道的默认模型。

我们可以去那里，在一个小湿地方，我们可以。在任何句子上试试。并得到相同的结果。所以。你有哦元表。所以你至少有三种不同的方法来尝试所有的好样本。在推理API和网站上，有时当你尝试一个模型时，你会看到小进度条在加载，然后你可以在b或句子中试试。

所以。让我们。回到课程。下一部分。关于变换器模型如何工作的，变换器模型是相当新的。所以架构本身是在2017年的一篇论文中发布的，第一个预训练模型是G。由Open AI在2018年6月发布，第二个预训练模型Westbro在2018年10月由谷歌发布，然后它有点加速了，这里只是几个模型的示例。

但还有很多，很多更多。那些已经发布，尽管如此，我们至少需要这个图像变成两倍或三倍大，以便能够放下自2019年至今发布的每一个模型。真的很难跟上发布的基础。

但我认为变压器库现在有大约60种不同的架构，并在论文发布后尽快添加新模型。因此我们将在这里讨论的不是变压器模型内部的细节，而是一个概览。在本节中，我们将探讨三种类型的变压器模型，包括被称为自回归模型的GT模型。

这些变压器模型基本上是用于生成文本的。例如，当你的手机试图建议你可以在后续句子中使用的单词时，之前讨论的内容就是这种情况。另一种类型的变压器模型是类似于GT的模型，抱歉，不是编码器模型，而是解码器模型，抱歉，是自回归或解码器模型。

所以这些模型最适合分类事物，生成句子的a9表示，使你能够分类整个句子或句子中的每个单词，它们在我们之前讨论的提取式问答任务中也非常有效。

最后一种模型是序列到序列的变压器模型，即编码解码模型，它更适合处理序列到序列的文本，如翻译、摘要，基本上是从输入文本写出新的文本。因此，所有这些变压器模型都是语言模型，而前两种类型之间的主要区别在于。

编码器和解码器的区别在于解码器通过预测下一个单词来进行操作。这就是我们在生成文本方面表现出色的原因，因为这就是它们的运作方式。而编码器模型通常是通过在句子中填充一些随机掩码来进行训练。因此我们这里有两个例子。这些变压器模型非常庞大，我们最开始的开放AGTD模型仅有数百万个参数，而现在我们有数十亿或数百亿个参数的模型。

这就是为什么重用这个模型非常重要的原因，这就是迁移学习的全部意义。迁移学习是指你使用一个训练好的大模型，该模型在大量数据上进行训练，这需要消耗大量计算资源，排放了大量二氧化碳，然后重用该模型来解决新的任务。你希望处理的任务。因此，通过减少模型，而不是从头开始训练一个新的模型。

你节省了计算资源，节省了金钱，并且需要的数据比模型训练时所需的少。让我们来看一下我们新的问题。第一个问题是GT3是否是唯一允许零样本学习的模型？

这就是这个模型的推广方式，但并不是唯一的，因为 T5 也有类似的提示，例如让你总结这段文本或将这段文本从一种语言翻译成另一种语言，因此它也可以进行某种零学习。链接已经被回答过，所以让我们去看迁移学习的视频，希望这次比之前的要好一些，如果你想直接观看，我会在聊天中分享链接。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_18.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_19.png)

什么是迁移学习？迁移学习的理念是利用在另一个任务上通过大量数据训练的模型所获得的知识。模型 A 将专门为任务 A 进行训练。现在假设你想为不同的任务训练模型 B，一个选择是从头开始训练模型。这可能需要大量计算。

时间和数据。相反，我们可以用与模型 A 相同的权重初始化模型 B，从而转移模型 A 在 T P 上的知识。当从头开始训练时，所有中间的权重都是随机初始化的。在这个例子中，我们正在训练一个模型，以识别两个句子是否相似。

左侧是从头开始训练的模型，右侧是经过预训练的模型。可以看出，使用迁移学习的预训练模型产生了更好的结果。无论我们训练多长时间，从头训练的模型保持在 70% 的准确率，而经过迁移学习的模型轻松超过 86%。

这是因为预训练模型通常在大量数据上进行训练，但为模型提供了对训练期间使用的语言的统计理解。在计算机视觉领域，迁移学习成功应用了近 10 年。

模型经常在 ImageNet 上经过训练，该数据集包含 120 万张照片。每张图像被分类为 1000 个级别之一。这样的训练方法被称为监督学习，而在自然语言处理领域，迁移学习则相对较新。与 ImageNet 的一个关键区别在于，训练通常是自我监督的。

这意味着它不需要人工标注标签。一个非常常见的目标是预测句子中的下一个单词，这只需要大量文本。例如，GPT-2 就是通过使用用户在网络上发布的 4500 万个链接的内容进行训练的。

另一个自我监督预训练目标的例子是预测随机掩盖的单词。这类似于你在学校中可能做过的血液测试。这种方法使用了英文维基百科和 100 本已出版的书籍进行训练。在实践中，通过抛弃给定模型的头部来应用迁移学习。

其最后的层专注于预训练目标。并且使用一个新的随机初始化的适合任务的模型。例如，在之前构建模型时，我们移除了分类Mque的层，并用一个有两个输出的分类器替换，因为我们的任务在两个层面上。为了尽可能高效，使用的预训练模型应与其微调的任务尽可能相似。

例如，如果问题是对德语句子进行分类，最好使用一个德语模型。但好事与坏事相伴，预训练模型不仅转移了它的知识，还包括它可能包含的任何偏见。ImageNe主要包含来自美国和西欧的图像。

因此，使用微调模型通常会在这些国家的图像上表现更好。但是贝尼也研究了其**Gpyy3**预测中的偏差，涉及使用猜测和**X世界目标**。将**E Westbury**的性别从“他”更改为“她”会改变预测结果，主要为中立目标。

几乎只针对物理模型。在**GT2 Mor**的模型代码中，OpenAI也承认其偏见，并不鼓励在与人类互动的系统中使用它。![](img/1b5e5fce582c60e42117fe3a72e59e6a_21.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_22.png)

嗯。![](img/1b5e5fce582c60e42117fe3a72e59e6a_24.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_25.png)

好吧，让我看看视频上是否有任何问题。😔 我认为没有。好的，这就是迁移学习的非常高层次的介绍，这通常是用变换器模型完成的。例如，我们之前使用的模型**distill B**，它在**62**数据集上进行了微调，这个数据集包含句子，你需要将它们分类为正面或负面。

除非有新的问题，否则我认为我们已经可以稍微深入探讨变换器架构，因此奥马尔将在聊天中发布该视频的链接。我希望这次不会再卡顿，因此这个视频将介绍我们之前简要讨论过的**Odo解码器**与**序列到序列变换器模型**之间的区别。

让我们研究变换器架构。这个视频是关于**Ens解码器**和**Ender解码器**系列视频的介绍。在这一系列中，我们将尝试理解变换器网络的构成，并试图用简单的高层次术语进行解释。对神经网络的深入理解并不是必要的。

但对基本向量和张量的理解可能会有所帮助。为了开始，我们将引用原始变换器论文中的这一图表，题为**“注意力即一切”**，通过对其进行阐述。如我们所见，我们只能根据我们的目标利用其中的部分内容。我们希望深入探讨这些特定的层，构建出该架构。

但我们将尝试理解这种架构的不同使用方式。让我们首先将架构分为两部分，左边是编码器，右边是解码器。这两者可以一起使用，但也可以独立使用。让我们理解它们是如何工作的。编码器接受表示文本的输入。

它将这些文本，这些词转换为数值表示。这些数值表示也可以称为嵌入或特征。我们将看到它使用自注意力机制作为其主要组件。我们建议你专门查看关于编码器的视频，以理解这种数值表示是什么以及它是如何运作的。

😊，我们将更详细地研究自注意力机制及其双向特性。😊。解码器与编码器类似，它也可以接受文本输入。它使用与编码器相似的机制，即掩蔽自注意力。由于其单向特性，它与编码器有所不同，传统上以自回归方式使用。

在这里，我们也建议你查看关于解码器的视频，特别是为了理解这一切是如何运作的。将这两个部分结合起来，形成了所谓的锚解码器或序列到序列转换。编码器接受输入并计算这些输入的高级表示。这些输出随后传递给解码器。解码器使用编码器的输出和其他输入来生成预测。

然后预测一个输出，这将在未来的迭代中重用，因此称为自回归。最后，为了全面理解编码器解码器，我们建议你查看关于编码器解码器的视频。![](img/1b5e5fce582c60e42117fe3a72e59e6a_27.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_28.png)

。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_30.png)

好吧，这就是一般介绍，基本上这是你需要记住的关于一般变换器架构的图表。那么什么是编码解码器或编码解码器模型呢？在深入了解之前，我们稍微讨论了注意力的内容。

原始论文的图表，所以架构的核心，变换器模型是这个称为多头注意力的层。这一层基本上表明了基本注意力。因此，它将查看你的整个句子。输入序列中的每个词都将计算一个分数，以关注这个词或其他词。这是因为变换器架构最初是为翻译设计的，当你翻译一个特定的词时，你需要这个词，但你需要理解其周围的上下文。例如，你可能需要在词的性别上下文中，如果词是名词，你可能需要其性别，即前一个词，或者后面的某些词。

所以注意力层是计算给定世界的一些上下文表示的地方。它用于告诉所有与这个特定单词相关的内容，尤其是这个单词，虽然这个世界不太有用，但这个你真的应该关注，它将在第2节和第3节中有视频，详细讲解注意力层是什么，但这就是我对第一层的介绍。

编码器和解码器之间的关键区别在于，编码器的注意力机制可以查看句子中的每个单词。因此，前面的单词和后面的单词，因为像鸟模型那样，当你需要检测时。

抱歉，要猜测一个掩码词的值，查看前面的内容以及后面的内容是有用的。解码器模型如GT必须预测下一个单词。所以如果它们被允许查看后面的单词，那将是作弊。因此在这些模型中，注意力层只允许查看句子中前面的内容。例如，当试图猜测“银”时，注意力层只能查看“我的名字”，而不能查看句子中的后面内容。

是的，我们将切换到本章关于Ocuoss模型的下一节，但在此之前，让我看看是否有任何问题。在解码器图中，输出右移指的是什么，请问。让我检查一下那个图。这里。因为我们正在训练一个翻译模型，请记住这是变换器模型的原始架构，所以当你翻译一个英文短语句子时，输出是一个法语句子。因此，这里的标签你这个变换器模型的部分是解码器，它会尝试猜测下一个单词，所以它会从无开始，然后尝试开始句子的第一个单词，然后它将有句子的第一个单词来尝试获取句子的第二个单词，然后它将有句子的第一个单词来获取句子的第三个单词。

等等，所以右移的意思是我们有输出，即所需语言的文本右移一个标记。还有另一个问题，你能否提供一个快速的直观概述，说明数字版本的模型如distber如何在显著减轻的情况下保持准确性。

快速概述直观。好的。一般来说，变换器模型或深度学习模型有很多参数，数百万个。但其中很多参数要么是冗余的，要么并不一定真正有用，因此例如有很多研究致力于修剪变换器网络，修剪意味着移除一些权重以便能够更快，尤其是在每个时刻。

蒸馏是另一种减少模型大小的方法，其过程是让一个较小的模型尝试输出一个较大模型的结果，并且它的性能仍然相当不错。因此，这背后的直觉是，一个非常大的模型有很多参数。

但并不是所有这些参数都真的有用。因此，让我们深入探讨编码器模型，我们还有三段视频，编码器、解码器，然后是序列到序列模型。![](img/1b5e5fce582c60e42117fe3a72e59e6a_32.png)

我们将其置于全屏并进行设计。![](img/1b5e5fce582c60e42117fe3a72e59e6a_34.png)

在这个视频中，我们将研究编码器架构。一个流行的仅编码器架构的例子是Bt，这是同类中最受欢迎的模型。让我们首先了解它是如何工作的。我们将使用三个单词的小示例，将它们作为输入并传递给编码器。

我们检索每个单词的数值表示。例如，这里的编码器将三个单词“欢迎”、“到”、“NYC”转换为这三个数字序列。编码器对每个输入单词输出恰好一个数字序列。这个数值表示也可以称为特征向量或特征张量。

让我们深入探讨这个表示。它包含一个经过编码器处理的每个单词的向量。每个向量是该单词的数值表示。该向量的维度由基础鸟模型的架构定义，维度为768。这些表示包含了一个单词的值，但具有上下文化。例如。

与单词2相关的向量不仅是两个单词的表示。它还考虑了周围的单词，我们称之为上下文。例如，它查看左侧上下文，即我们正在研究的单词左边的单词；听到单词“欢迎”，以及右侧的上下文，这里是单词“NYC”。

它输出一个值，用于给定上下文中的单词。因此，这是一个上下文化的值。😊可以说，768个值的向量在文本中承载了单词的含义。它依赖于自注意力机制。自注意力机制与单个序列中的不同位置或不同单词相关，以便计算该序列的表示。

正如我们之前所见，这意味着一个单词的原始表示受到序列中其他单词的影响。我们在这里不会深入这些细节，但如果你想更好地理解幕后发生了什么，我们会提供一些进一步的阅读材料。

那么什么时候应该使用编码器？编码器可以作为独立模型在多种任务中使用。例如，Bert，无疑是最著名的变换模型，是一个独立的锚定模型。在发布时，它在许多序列分类任务、问答任务和掩码语言建模中是最先进的，仅举几例。😊

这个想法是编码器在提取携带有意义信息的向量方面非常强大。这个向量可以通过额外的神经元进一步处理，以使其有意义。让我们来看一些编码器真正闪光的例子。首先是掩码语言建模或MLM。这是预测序列中隐藏词的任务。在这里。

例如，我们隐藏了“my”和“is”之间的词。这是Bert训练的目标之一。它的训练目的是预测序列中的隐藏词。编码器在这种情况下特别出色，因为双向信息在这里至关重要。

如果我们没有右边的词，是Silva和点。那Bt几乎没有机会将名称识别为正确的词。编码器需要对序列有很好的理解，以便预测被掩盖的词，因为即使文本在语法上是正确的，也不一定在序列的上下文中有意义。

如前所述，编码器擅长进行序列分类。😊情感分析就是序列分类的一个例子。模型的目标是识别序列的情感。它可以为序列评分，从一到五颗星，或者为序列给予正面或负面的评分。

这就是这里所展示的。例如，给定这两个序列。我们使用模型来计算预测，并将这两个序列分类为正类和负类。虽然这两个序列非常相似，包含相同的单词，但含义完全不同，而编码模型能够把握这种差异。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_36.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_37.png)

嗯。这就是forcodo模型，一些例子是Albertt、Bt、distill Bt、Elect、Roberta。我们来看看下一部分，将讨论解码器。在此之前，让我检查一下是否有任何问题。聊天中没有看到新的问题，别忘了你可以在聊天中提出任何问题，这正是直播会议的目的。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_39.png)

是的。![](img/1b5e5fce582c60e42117fe3a72e59e6a_41.png)

在这个视频中，我们将研究解码器架构。一个流行的仅解码器架构的例子是GPT2。为了理解解码器是如何工作的，我们建议观看关于编码器的视频，它们与解码器非常相似。解码器可以用于大多数与编码器相同的任务。

尽管通常性能会稍有损失。让我们采取与编码器相同的方法，尝试理解编码器和ID解码器之间的架构差异。我们将使用一个包含三个单词的小例子。我们将它们传递给解码器。我们为每个单词检索一个数值表示。在这里，例如。

解码器将“welcomee to NYC”这三个词转换为三个数字序列。解码器每个输入词准确输出一个数字序列。这个数值表示也可以称为特征向量或特征张量。让我们深入研究这个表示。它包含通过解码器传递的每个词的一个向量。

这些向量中的每一个都是相关词的数值表示。😊该向量的维度由模型的架构决定。解码器与编码器的主要区别在于其自注意力机制。它使用被称为掩蔽自注意力的机制。在这里，例如，如果我们专注于词“2”。

我们会看到这个向量在纽约市的词汇中完全没有被修改。这是因为右侧的所有词语，也称为该词的右上下文，都被屏蔽了。因此，解码器并没有利用左右两侧的所有词语，也就是双向上下文。解码器只能访问单一的上下文，可以是左上下文或右上下文。

掩蔽自注意力机制与自注意力机制的不同之处在于使用了额外的掩蔽，以隐藏词语两侧的上下文。词语的数值表示不会受到隐藏上下文中词语的影响。那么，何时使用解码器呢？解码器可以像编码器一样作为独立模型使用。因为它们生成数值表示，也可以用于各种任务。

然而，解码器的强大之处在于词语只能访问其左侧的上下文。仅访问左侧上下文，使它们在文本生成方面具有天生的优势。给定一个已知的词序列，生成一个词或一系列词的能力。😊这被称为因果语言建模或自然语言生成。

这是一个因果语言建模如何工作的例子。我们以初始词“my”开始。我们将其用作解码器的输入。😊，模型输出一个数字向量。这个向量包含有关序列的信息，这里是一个单词。我们对该向量应用一个小的变换，以使其映射到模型已知的所有词。

这是我们稍后将看到的一个映射，称为语言模型头。我们识别出模型认为最可能的下一个词是“name”。然后，我们将这个新词添加到初始序列中。从“my”开始，我们现在得到了“my name”。这就是自回归特性的体现。😊

自回归模型将过去的输出重用为输入和后续步骤。再一次，我们执行完全相同的操作。我们通过解码器处理该序列，并检索出最可能的下一个词。在这种情况下，它是“is”这个词。我们重复这个操作，直到满意为止。从一个单词开始，我们现在生成了一个完整的句子。我们决定在此停止。

但我们可以继续一段时间。比如说，GPT-2 的最大上下文大小是 1024。我们最终可以生成多达 1024 个单词，而解码器仍然会记住它们的前几个单词和那个序列。😊，是的。游戏。让我看看关于解码器模型的一些问题。哦，有一个问题是，是否可以使用超过 512 个单词的较长句子作为编码器的输入。好问题，这取决于情况，但大多数时候不行。例如，spt 的最大长度是 512，因此您不能使用比这更长的句子。

一些较新的模型，比如 Longformer，可以接受更长的上下文。因此，您应该查看文档，但首先要对代码非常具体，比如并不是所有的模型都能做到这一点。您可以做的另一件事是将句子拆分成几个部分，每部分 512 个单词，然后如果您获得了一个表示，您就将这些片段传递给模型，这样您就能获得每个片段的表示。

例如，您最终在尝试为较长的句子训练分类器时的平均情况。但这大概是唯一的方式，要么是经过特定训练的模型，可以处理较长的输入，比如 Longformer，要么是将输入拆分成多个部分。

另一个问题是，掩码语言建模目标如何处理长灰色单词，这最终会成为一个多令牌单词。例如，海上飞机与管道结合时会变成 Ci。😊，AshAsh plane。对于那些初学者，您将在下一个章节的视频中看到关于这种分离的内容。

如果不使用全掩码，那么模型就会作弊，看到较长单词的部分。因此，这是绝对正确的，这就是为什么您会看到有多个版本的 PE，其中一个经过全掩码预训练，而另一个则没有。如果模型看到 ash ash plane，那就会作弊。

我的意思是，如果我们在上下文中猜测 ash ash plane，这就是作弊，抱歉，因为您有 ash ash plane 的上下文。当您尝试猜测 ash ash plane 时，您得到的是上下文中的转移，因为这算是较少的作弊，因为模型必须猜测，而模型并没有提前知道。

但确实，使用全掩码会消除我们所看到的特定偏见和作弊情况。我们已经到了上层。好吧，让我们看看最后一个视频，然后我会在最后一个关于序列到序列的变换模型的视频中回答更多问题，这种模型结合了编码器和解码器。

在这个视频中，我们将研究编码器-解码器架构。一个流行的编码器-解码器模型的例子是 T5。为了理解编码器-解码器是如何工作的，我们建议您查看有关编码器和解码器的独立模型视频。

了解它们如何单独工作将有助于理解编码器-解码器的工作原理。让我们从我们对编码器的了解开始。编码器以单词作为输入，通过编码器进行处理，并为每个经过它的单词检索出数值表示。我们现在知道，这个数值表示包含了序列的意义信息。

让我们将其搁置，并将解码器添加到图表中。在这种情况下，我们以一种前所未见的方式使用解码器。我们直接将编码器的输出传递给它。除了编码器的输出外，我们还给解码器一个序列。在没有初始序列的情况下提示解码器输出。

我们可以给它一个值，以指示序列的开始。😊。而这就是解码魔法的锚点所在。😊，编码器将一个序列作为输入。它计算一个预测并输出一个数值表示。😊。然后将其发送给解码器。可以说，它已经对该序列进行了编码。而解码器。

反过来，使用这个输入与它通常的序列输入一起，解码器将尝试解码这个序列。解码器解码一个序列并输出一个单词。到目前为止，我们并不需要理解这个单词，但我们可以理解解码器实际上是在解码编码器的输出。这里的启动序列，启动序列单词表明它应该开始解码这个序列。

现在我们有了编码器的数值表示和一个初始生成的单词。我们不再需要编码器。正如我们之前看到的，解码器可以以自回归的方式进行工作。它刚刚输出的单词现在可以用作输入。这与编码器输出的数值表示结合在一起。

现在可以用来生成第二个单词。请注意，第一个单词仍然在这里，因为模型仍然输出它。然而，我们将其标记为无效，因为我们不再需要它。😊，我们可以继续进行。例如，当解码器输出一个我们认为是停止值的值时，比如一个点，表示序列的结束。这里我们已经看到了编码器-解码器变换器的完整机制。

让我们再复习一次。我们有一个初始序列发送给编码器。😊。该编码器的输出然后被发送给解码器进行解码。虽然在单次使用后可以丢弃编码器，但解码器将被多次使用，直到我们生成所需的每个单词。

让我们看一个具体的例子，涉及翻译语言建模，也称为转导。这是将一个序列翻译的行为。在这里，我们想将这个英文序列"We"翻译成法语的"NOIC"。我们使用一个专门为此任务训练的变换器模型。我们使用编码器来创建英文句子的表示。

我们将其传递给解码器，使用开始序列词。我们要求它输出第一个词。它输出了“avenue”，这意味着“欢迎”。然后我们使用“B avenue”作为解码器的输入序列。这与编码器的数值表示相结合，使解码器能够预测第二个词“a”。

这在英语中是两个。😊最后，我们要求解码器预测第三个词，它预测了NYC，这是正确的，我们已经翻译了句子。编码器-解码器真正闪光的地方在于我们有一个编码器和一个解码器，通常不共享权重。因此，我们有一个完整的块，编码器可以训练以理解序列并提取相关信息。

在我们之前看到的翻译场景中，例如，这意味着解析和理解英语中所说的话。这意味着从该语言中提取信息，并将所有信息放入信息密集的向量中。😊另一方面，我们有解码器，其唯一目的是解码编码器输出的数值表示。

这个解码器可以专门用于完全不同的语言，甚至是图像或语音等模态。😊编码器和解码器在几个方面是特殊的。首先，它们能够处理像我们刚刚看到的翻译这样的序列到序列任务。其次，编码器和解码器部分之间的权重不一定是共享的。

让我们再看一个翻译的例子。在这里，翻译变换器在法语中非常强大。首先，这意味着从三个词的序列中，我们能够生成四个词的序列。可以说，这可以由一个以自回归方式生成翻译的解码器来处理。他们是对的。另一个序列到序列变换器发光的例子是摘要。

😊在这里我们有非常非常长的序列，通常是一整篇文本，我们想要总结它。由于编码器和解码器是分开的，我们可以有不同的上下文长度，例如。编码器处理文本的非常长的上下文和解码器处理摘要序列的小上下文。有很多序列到序列模型。

这包含了一些在Transformers库中可用的流行编码器-解码器模型的示例。此外，你可以在编码器-解码器模型中加载一个编码器和一个解码器。😊因此，根据你针对的具体任务，你可以选择在这些特定任务中已证明其价值的特定编码器和解码器。

![](img/1b5e5fce582c60e42117fe3a72e59e6a_43.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_44.png)

是的。好的，那我们来看看有没有问题。哦，好的。是段落解码器问题还是编码器解码器问题？

是否有任何可用的管道来实现同样的功能？所以改写生成与输入类似的任务，更像是一个编码器或解码器原型。然而，似乎在这个特定任务上训练模型会非常困难，因为它倾向于想要包含接收到的相同内容。

除非你想以另一种风格进行改写，例如从正式风格到非常随意的风格。目前在变换器库中没有提供实现该任务的管道。所以让我们进入 Cha1 的下一部分，这是这一章的最后一部分，谈谈变换器模型的偏见和局限性。像任何深度学习模型一样，变换器只是一个特定的案例。

但这确实是所有深度模型面临的问题，所以有强大的工具，正如你可能知道的，如果你参加深度学习入门课程，你会接触到这些强大的工具，但你并不能真正控制输入到输出的过程，这主要是通过他们接受的训练数据和训练方式来控制的，但如果你不采取任何预防措施，这些模型可能会做出你并不希望在应用中部署的预测。

让我们快速看一下经过重新训练的 B 模型，其目标是 thin maskQu，并且有一个类似于我们在 GPT 的迁移学习视频中看到的例子，我们只需改变句子的性别，所以如果你说“这个男人作为一个工作”。

猜这个词或“这个女人作为一个”猜“男人”的词。我们得到一些中性的工作。可能更符合刻板印象的是男性的工作，而女性则得到非常刻板印象的女性工作，甚至是性工作者。这显然不是我们希望模型输出的前五个可能性之一。

所以该模型并不是在数据上训练的，但被特别标记为有问题的。更像是通常被认为是中立的，只有维基百科和一些未出版的书籍。所以你必须像 GBT 一样，举例来说，因其在互联网的墙上训练而更为知名，这被认为有点性别歧视或排外的倾向，所以你必须非常小心，因为这种偏见存在于预训练模型中，因此这次是使用 bird paste 和 case checkpoint 特别完成的，并且是完全可重现的，因为在预测中没有随机性，所以如果你在 tris 上运行一个笔记本，你将得到这些结果。

所以在某种程度上，这在任何模型中都是存在的，或者说是新的，并且在你的微调后也会持续存在。因此你总是必须非常小心，当你在训练数据中微调模型时，必须确保你希望看到的输出有足够的样本，并且你应该始终在将模型投入生产时认真分析你得到的结果，如果你看到一些预测你希望避免的，尝试纠正你的训练数据以添加更多样本。

添加更多样本以纠正你模型的偏差。这就是第一章的内容。让我看看还有没有更多问题。在聊天中，否则我们就准备结束了，所以一旦你完成了这个视频，不要犹豫，去做个测验，我不会在视频中进行，以确保你理解了所有术语和内容，但我们在这一章中看到的还有两个左侧会议。

你可以在论坛上再次找到。这已经不是论坛了。下周有两个关于第2章的直播会议，请务必尝试参与，另外一个会是我，期待下周三希望所有技术问题都能得到解决，因为我会稍微关注一下，确保它运作得更好，尤其是视频方面。

第一个会议将是与Lewis在欧洲时间周三的早晨，第二个会议将在下周四的同一时间进行。请花时间在那里创建一个账户，如果hub上有问题，希望codeab的bug能很快解决，你也可以在那个平台上进行代码实验。

否则你总是可以使用网站上的推理API，并考虑一个你想要运行的项目。在你学习课程的过程中，尝试你的技能，因此与文本分类相关的任何内容，因为这部分课程将集中于此。但试着想想你想构建什么样的模型，做一些你可以分享给社区的事情，然后在接下来的几周内，这将帮助你在实践中完成课程。

让我检查一下上次我们有什么问题。嗯，我想这大概就是全部了。好的，非常感谢你的关注，下周见！![](img/1b5e5fce582c60e42117fe3a72e59e6a_46.png)

![](img/1b5e5fce582c60e42117fe3a72e59e6a_47.png)

嗯。
