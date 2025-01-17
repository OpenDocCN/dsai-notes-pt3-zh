# Excel高级教程（持续更新中） - P6：6）宏初学者指南 - 创建快捷方式 

![](img/7ba82c55ded348860e2d89a225c4d048_0.png)

这是关于 Excel 宏的初学者指南。如何使用宏为你在 Excel 中需要执行的任务创建快捷方式。我将用来举例的电子表格是一个员工列表。你可以看到这里有几个员工的列表，适用于一个假设的小型企业。

它包含一些关于他们的信息，比如他们被雇佣的日期、员工 ID 和他们所在的团队。在这个项目标签上，我有一些项目的列表，我希望将这些员工分配给这些项目，以便他们可以参与工作。所以我会在第一个标签和第二个标签之间来回切换。当然，我可以通过点击标签轻松做到这一点。

但是让我们创建一个宏，让这个过程变得稍微简单一点，更方便一点。我希望最后得到一个按钮，可能就在这里，当我点击那个按钮时，它会带我到第二个标签。在这个工作簿中的第二个表。所以我该怎么做呢？我只需去开发者标签。如果你看不到开发者标签。

你可能需要在功能区上右键单击并选择自定义功能区，确保开发者选项在这里被包含。但无论如何，我只是去开发者标签并点击它。功能区会更改以匹配这一点。在左侧，有一些与宏相关的选项。在这个初学者指南中。

我们基本上将坚持使用记录宏以及这个宏按钮。所以在这个情况下。我将点击记录宏。它会打开一个小向导，我可以用来创建这个宏。默认情况下，它将这个宏命名为宏 5。因为在过去，我在这个电子表格中创建了一些其他宏。所以我将对它进行重命名。

然后我会调用这个按钮到项目标签。接下来，我需要为这个宏建立一个快捷键，一个键盘快捷键。现在，如果你想一想，你知道，这里需要小心。因为它们已经是 R。键盘快捷键。我们有控制 X，控制 Z，控制 C。这些都是已经存在的键盘快捷键。所以我不想在这里放控制 C。

那就会是一个错误，因为控制 C 已经执行复制。所以实际上在这个框中放两个键是个好主意。所以我会按住 Shift 并按 A。所以控制 Shift A 现在是我为这个即将创建的宏保留的键盘快捷键。它会把这个宏存储在这个工作簿中。

这意味着我这里的电子表格集合。现在，只有两个电子表格，但我可以添加另一个表，另一个，再一个。它们都是同一个工作簿的一部分。我想将这个宏存储在这个工作簿中。还有其他选项，但我们就只讨论这个。接下来。

如果我想，我可以描述这个宏。我想我会这么做。所以给我一分钟来输入描述，然后我会继续视频。这里是我非常详细的描述，我点击确认。然后我收到了一个错误信息。我想让你看到这一点，以便你知道宏标题中不能包含空格。

所以现在当我点击O时，它应该接受了。确实如此。现在，注意左上角。现在它显示停止录制。它不再显示录制宏。所以它目前正在记录我在Excel中的操作，但重要的是要意识到它并不记录时间的流逝。所以我可以坐在这里思考我将如何处理这个宏。我正在录制。

我可以思考这个问题，可能是10分钟，也可能是1小时，甚至10天，随我喜欢。没关系，因为这并不记录时间。它也不记录我的鼠标指针的位置。我可以把鼠标移到我想要的任何地方。那些都不会被记录。被记录的是我点击的位置以及我在Excel中更改的选项和设置。

好的，我想记录什么。我希望它记录我从员工电子表格到项目电子表格的过程。所以我会点击项目。这就是我希望它记录的全部内容。所以我点击停止录制。这个宏已经成功录制。现在，我要跳回员工电子表格，让我们看看我创建的宏。

如果我在宏选项上点击，它应该列出此工作簿中所有存在的宏。在这里，按钮到项目选项卡。现在我在这里，我想让你注意我刚刚选择的宏选项。它确实允许你删除不想使用的宏。还有其他一些选项。好的，我就取消这个。现在是我创建一个按钮并将其链接到那个宏的时候了。

在开发者选项卡上，我将下拉到插入，然后点击。这会弹出一些表单控件。在之前的教程中，我向你展示了如何创建一个滚动条并在Excel中使用它。如果你还没看过那个视频，希望你能回去看看。在这个教程中。

我们要使用另一种表单控件，那就是按钮。所以我会点击按钮选项。注意我的鼠标指针发生了什么。😊它变成了十字线，基本上变成了一个加号。这是我可以在屏幕上绘制某物的标志。所以我将点击并拖动以绘制一个按钮，我可以根据需要将其做得很大或很小，尺寸和所有这些都由我决定。

我想我会选择这个大小。当我松开鼠标按钮时，它会弹出一个窗口，让我选择要链接到我创建的这个按钮的宏。目前，实际上只有一个选项。所以我点击按钮到项目选项卡，然后点击O。我的按钮就创建好了。如果我双击按钮的文本。

有时只需单击一下。我可以更改按钮上的文本。所以我输入“项目”。好吧，现在我将点击按钮外部来测试一下。我右键点击按钮，看看它做了什么。它立即执行了我使用录制宏创建的宏。

它存储在宏列表中。😊当我点击按钮时，它把我带到了这里。所以现在我可以向一个项目添加某个人。我的好朋友**Marcellina Resrepo**怎么样？我会把她放在项目A上。现在我强烈推荐，如果你要创建这样的按钮，从一个电子表格跳转到另一个，最好在第二个电子表格上创建一个按钮，带你回到第一个。

所以很快，我会点击开发者录制宏。我会把它命名为“返回员工表”。我会给它一个快捷键，这次我将跳过描述。我点击O，宏现在已经命名，并准备录制。所以这次我会点击员工。我录制完毕，点击停止。

然后我回到项目表创建我的表单控件按钮。😊在这个弹出窗口中，我需要确保选择正确的，返回员工表，点击O，也许点击并拖动以突出显示按钮1。我就叫这个“返回”。现在，当你使用按钮时，如果你点击按钮外部，下次再点击它。

这会有效。它会按预期工作。那么我该如何编辑这个按钮呢？如果我后悔它的形状或位置，我无法点击和拖动。所以诀窍是右键点击按钮。如果你右键点击它，它会被选中。然后你可以点击别处，再次点击按钮来移动或调整其大小，如果你想的话。

你可以剪切或执行其他操作。所以此时，我有两个按钮，一个将我带到我的项目列表，另一个让我回到员工列表。现在，这只是其中一种宏。如果你仔细想想，我可以记录几个其他步骤。

你可以创建多个操作的宏，当你执行宏时会发生这些操作。但我选择从这些简单的按钮开始，它们只是从一个工作表切换到下一个。让我们再看一个例子。在这个开始的视频中，假设我是这家公司的所有者，现在是时候与所有员工进行绩效评估了。

也许我想追踪已经评估过的人和下一个需要评估的人。展示这一点的一种方法是使用颜色。所以假设我和**M Rerepo**进行了评估。我可以点击并拖动以突出整个行，或者如果我更喜欢，只突出她的名字。然后在“主页”选项卡中，我可以更改文本的颜色，或者也许填充背景色。

也许我会说蓝色代表我们已经进行了审核。这是一种方法。但现在，让我给你展示如何作为宏来做。这样我就可以点击一个人的名字，点击一个按钮，自动将正确的颜色应用于该人的名字。为此，我会创建一个宏。首先我想做的是点击一下电子表格的空白部分。

然后我会去开发者选项卡，点击录制宏。我将为其命名为“标记为已审核”。快捷键我会设置为控制+Shift+C，然后我点击O。现在开始录制。你可能会想要点击这里选择Gina Pullulin或Regia Loftus，或者其他这些优秀的人。但相反，我故意保持这个单元格被选中。

我将简单地去“首页”选项卡，首页功能区，选择这个蓝色背景色。它只改变了那个单元格的颜色。现在我回到开发者选项卡，点击停止录制。为什么我保持这个单元格被选中呢？原因是如果我点击选择Gina Pullulin或Regia Loftus，或者任何其他人。那么每次我执行宏时，该特定单元格，比如在这种情况下的单元格A6。

本来应该变成蓝色，但只有这个单元格。原因是我在开始录制宏后点击了它。但我实际做的方式是，我先点击这里，然后录制宏，并且没有点击其他任何东西。因此，Excel的解释是，它说O。

他没有点击任何东西。因此，选中的内容将变为蓝色，而不是任何特定的单元格。现在，有时你会希望它是一个特定的单元格。在这种情况下，录制宏后，点击你想要变成蓝色的内容，或者宏所执行的任何操作。让我们创建一个按钮，看看它是否有效。所以我会去开发者选项卡插入一个表单控件按钮。

我将点击并拖动在屏幕上绘制。然后我只需点击“标记为已审核”，点击O，这就是我的按钮。在我忘记它的意思之前，我最好在按钮本身更改名称。我将点击按钮之外。所以假设Jimmy Kinslow和我进行了很好的审核，我可以点击名字，点击已审核。

然后它立刻将他的名字高亮显示为我想要的确切蓝色。所以我不必猜测或试图记住其中哪个。我可以简单地点击选择，然后点击已审核，它就会改变颜色。现在，如果我想让整行变成蓝色，比如说对于Salw Cordew。

我可以点击并拖动以高亮整行，然后点击“已审核”。现在，整个内容变成了蓝色。当然，这时我可以创建另一个宏，如果这些名字或任何选中的内容下次需要审核，就将其变成黄色。所以我希望这些例子能给你一些关于如何使用宏的想法。

你可以为许多不同的事情制作宏。然后创建一个链接到宏的表单控制按钮。这真的可以为你节省大量时间和精力。它将帮助你轻松快速地在工作表之间跳转。现在，当然，在这个特定的工作簿中，只有两个工作表，想象一下如果我这里有10或20个工作表，那确实很难准确点击我需要的标签。因此，拥有一个按钮可以带你到一个特别重要的标签或工作表，确实可以为你节省时间。所以我们假设在这一点上。

我已经完成在这个Excel电子表格中创建宏。每当你在电子表格中构建宏时，还有一步重要的步骤需要进行。那就是你要去左上角的文件，然后点击另存为，因为这个电子表格中有宏。

我很重要的是要去这里，点击这个下拉箭头，并将其从普通的Excel工作簿更改为启用宏的Excel工作簿。如果你不这样做，它在未来将无法工作。因此我会点击保存。那么现在让我们试试，看它是否有效。假设明天。

我需要再次处理那个电子表格，我可以直接打开。![](img/7ba82c55ded348860e2d89a225c4d048_2.png)

![](img/7ba82c55ded348860e2d89a225c4d048_3.png)

在我最近使用的电子表格列表中，找到了它。注意后缀末尾有一个M。通常在Microsoft Excel中，后缀以S或X结尾。但在这种情况下，它是X，L，S，M表示启用宏的。现在，看看当我双击打开它时会发生什么，因为这个电子表格中有宏。

至少在你第一次打开它时，你可能会收到安全警告。宏已被禁用。因此，为了使用它们，我必须点击启用内容。现在，我的宏应该可以工作了，确实可以。![](img/7ba82c55ded348860e2d89a225c4d048_5.png)
