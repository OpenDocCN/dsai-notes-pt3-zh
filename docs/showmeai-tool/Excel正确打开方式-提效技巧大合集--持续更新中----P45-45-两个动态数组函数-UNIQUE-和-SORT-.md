# Excel正确打开方式！提效技巧大合集！(持续更新中) - P45：45）两个动态数组函数：UNIQUE 和 SORT 

![](img/d297961bf4ff678426926aaad9188dbb_0.png)

在这个视频中，我们将看一下Excel的两个新的动态数组函数：unique函数和sort函数。我们还将看看如何将这两个函数结合起来做一些相当令人兴奋的事情。所以这里我有一个电子表格，上面有乐队专辑及其更多信息。但正如你所看到的，乐队是重复的，专辑也是重复的，为什么呢？因为它是按季度列出的，每个季度都有。

不同的销售结果，诸如此类。那么，如果我想生成一个所有乐队的列表呢？就这样，我不需要重复项，我只需要每个乐队的列表。好吧。我现在可以通过在Microsoft Excel中使用相对较新的unique函数来做到这一点。如果你有Microsoft 365版本的Excel，你应该能够使用这个函数。

所以我将在J2单元格上单击，然后输入等于unique，你会注意到当我开始输入unique时，Excel会建议我可能想要使用的一些函数，但unique就是我想要的。我输入左括号。那么，接下来是什么呢？Excel在询问一个数组。

那么我想让Excel查找独特项的数组是什么呢？好吧，就是这个。是B列。现在我可以通过左键单击B来选择整个列。你可以看到Excel的表现。它输入了B:B。换句话说，整个B列。我应该输入我的右括号。其实我并不真的需要。我会按下回车键，你会注意到它做了什么。

它找到了该列中每个独特的单词或短语，并在J2中重现了它。现在，它无法将所有数据放入J2，因此结果溢出。希望你看过我之前关于Excel中溢出结果的视频。现在，这些结果是动态的。我们已经溢出一个动态数组或范围。所以现在看看会发生什么。

如果我更改其基础数据。例如，假设我删除了jelly rocks。他们是一支非常有趣的乐队。如果我将他们从乐队列表中删除所有引用，你会注意到我的溢出结果会反映出这一点。我将撤销这一操作。好吧，我们再试一次，但这次我不仅想要获取乐队。

但我也想获取专辑。我们来试试。我将在J2单元格上单击，也可以单击J1，这其实没什么关系。实际上，我想这次选择J1。等于unique左括号。我会从B拖动到C，右括号，按下回车，看看溢出结果。它溢出了专辑和乐队。

而且只想要独特的乐队。看看会发生什么。如果我插入另一条记录。比如说the killers，太棒了，我按下回车。看看我的动态范围或动态数组发生了什么。溢出结果会反映我添加的内容。现在，你可能会说，等等，乐队。

"杀手乐队"并不是乐队的独特之处。的确如此。但在我的公式中，我说我想要的是B和C列中的独特内容。所以它考虑了B列和C列中的数据，以决定什么是独特的，什么不是。所以因为乐队和专辑的组合是独特的，所以它在我的结果中列出。接下来我想尝试的不仅是过滤掉那些不独特的内容。

但我也想根据乐队名称对结果进行排序。让我们看看能否做到这一点。所以我会点击J1，删除该单元格的内容。正如你所知道的，所有这些溢出数据都是基于J1中的公式生成的。所以当我删除它时，它会去掉所有的溢出数据。

所以这次在J1，我会输入=unique左括号，然后输入sort。这是另一个动态数组函数。左括号。然后我会选择B和C，让我们看看我目前的公式。通常查看公式栏是最好的选择。

看那里，现在我会放一个右括号，然后再一个右括号，按下键盘上的回车键，看看右侧的结果。不仅生成了与乐队一起的独特专辑，而且它们还按乐队名称的字母顺序排列。现在也可以通过输入=sort左括号，选择一个范围来进行排序，在这种情况下是整列，按下回车，所以你可以使用排序函数对任何范围进行排序，并将结果溢出到下面，有时是右侧，所以你可以这样做。

但我认为以我展示的方式结合排序和独特功能特别令人兴奋，但你也可以将其与其他动态数组函数结合，做到同时生成唯一数据和排序。感谢观看这个教程。

我希望你觉得这个视频有帮助，如果是的话，请查看我的其他动态数组函数视频，以及我关于溢出结果的视频，但如果你觉得有帮助，请。![](img/d297961bf4ff678426926aaad9188dbb_2.png)

关注并订阅，当你这样做时点击铃铛，这样你就会在我发布另一个视频时收到通知。如果你想支持我的频道，可以通过我的Patreon账户和购买频道商品来做到这一点，你会在视频下方的描述中看到这些机会的链接。

![](img/d297961bf4ff678426926aaad9188dbb_4.png)

![](img/d297961bf4ff678426926aaad9188dbb_5.png)
