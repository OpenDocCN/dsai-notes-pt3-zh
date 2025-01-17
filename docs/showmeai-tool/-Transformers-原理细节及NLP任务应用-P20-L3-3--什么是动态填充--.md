#  Transformers 原理细节及NLP任务应用！P20：L3.3- 什么是动态填充？ 

什么是动态填充？在将输入批量组合的视频中，我们看到能够将不同长度的输入分组到同一批次中。我们需要为所有较短的输入添加填充标记，直到它们都相同。例如，这里最长的句子是第三个，我们需要添加五个填充标记。

两个或七个填充标记到其他句子中，以使四个句子具有相同的长度。在处理单词数据集时，我们可以应用一些有价值的策略。因此，我们大多数情况下使用的一个策略是将数据集的所有元素填充到相同的长度，即最长样本的长度。这将使我们得到的补丁都具有由最大序列长度决定的相同形状。

所以缺点是补丁由短句组成，我们有很多填充标记。这会引入模型中我们最终不需要的更多计算。为避免这种情况，另一种策略是将元素拼接到批次中最长的句子上。这样，批次就由短输入电压组成，且小于包含数据集中最长句子的批次。

这将在CPU和GPU上带来不错的速度。因此缺点是所有批次将具有不同的形状，这会在像TPU这样的加速器上减慢速度。让我们在实践中应用这两种策略。我们实际上已经看到在我们提出的Ar PCC数据集中应用了固定填充，在对数据集进行分词后，我们对整个数据集应用了带填充的分词，使所有样本的长度为128。

因此，如果我们将此数据集传递给一个批次数据，我们得到的补丁形状为补丁大小，这里是16和528。要应用动态填充，我们必须推迟填充到批次准备中。所以我们从分词函数中移除那部分。我们仍然保留合并部分，以便处理大于模型通常接受的最大长度（通常为512）的输入，这些输入会被截断到该长度。然后我们通过使用数据策展人动态填充一些填充标记。

转换库中的这些类负责在形成批次之前应用所有最终的预处理。在这里，带填充的解码器将所有样本填充到补丁中的最大长度。我们将其传递给Pyth的拼接函数，并观察到批次生成的长度各不相同，远低于之前的128。动态填充在CPU和GPU上几乎总是更快，因此如果可以的话，您应该应用它。

但是，请记住，如果您在TU上运行训练脚本或需要固定批次，请切换回固定填充！[](img/36eaaa3469c7215a06d948547906cbae_1.png)

。

![](img/36eaaa3469c7215a06d948547906cbae_3.png)
