# SQL常用知识点合辑——P32：L32- 插入单行 

![](img/89d6aadd09799eb0a2adeb5a6b77e305_0.png)

哦。在本教程中，你将学习如何向表中插入一行。为此，我们将使用插入语句。😊 我们要将这一行插入到 customers 表中，所以我们在这里输入表的名称，后面跟上值子句。在这里的括号中，我们为这个表的每一列提供值。

所以回到我们的表定义，这些是所有的列。首先，我们需要为客户 ID 列提供一个值。然而，在这一列中，启用了自增属性，正如我之前告诉你的。如果我们不提供一个值，MySQL 会为我们生成一个唯一的值。😊 所以我们可以回到我们的语句，显式赋值或者使用默认值，让 MySQL 来生成这个值。

这是首选的方法，因为如果你使用像 200 这样的显式值，可能会有另一个客户拥有相同的 ID。所以当你执行这个语句时，你会得到一个错误，因为这一列中不能有重复值，每个值都应该是唯一的。因此，我们将使用默认关键字，让 MySQL 为客户 ID 生成一个唯一的值。

现在，在此之后，我们需要为名和姓列提供一个值。假设是约翰·史密斯。请注意，我用引号括住这些值，因为正如我之前告诉你的，在 SQL 中，我们应该始终用引号括住字符串和日期值，可以使用单引号或双引号。😊 现在，还有什么？回到我们的 customers 表。姓之后是出生日期，不过。

正如我们所看到的，这一列是可选的，因为这个复选框没有被选中。所以在这里我们可以使用 null 或显式值，null 表示没有值。😊 所以回到我们的语句。我们可以输入一个出生日期，比如 1990 年 1 月 1 日，或者我们可以使用 null 关键字在这个演示中，我将使用一个有效的日期。现在。

为了让这段代码更简洁易读，我将把它分成多行。😊 这样更好。现在回到我们的表。接下来，我们有电话，而电话也是可选的，因为这个复选框没有被选中，而 null 是这一列的默认值。

所以在这里，我们可以显式传递 null 或使用默认关键字，让 MySQL 将 null 放入这一列。这是完全相同的。所以回到我们的语句，我们可以传递 null 或默认。这两种方法都会有相同的结果。在这个例子中，我将使用 null 关键字。😊 好的，我们再看一下我们的表。😊 接下来，我们还有更多的必需列。

所以地址，城市，州和积分，并注意积分的默认值是0。因此，我们可以使用一个显式值，比如200，或者使用默认关键字，让MySQL生成0。回到我们的语句，输入一个地址。实际上无所谓，接着是一个城市。😊。还有一个州，我们说，加州。最后是积分。再次。

我们可以使用显式值或默认值。😊，所以这就是我们如何向表中插入一行。然而，在这个例子中，我们只为名字，姓氏，出生日期，以及这个地址字段提供了值。所以我们忽略了电话号码，客户ID和积分。还有另一种写语句的方法，我来给你演示一下。😊，所以在表名后。

在这种情况下，我们可以选择性地提供我们想要插入值的列列表。名字。😊，姓氏。生日。现在，我将再次把这个语句拆分成多行。😊，所以还有三列，地址，城市，和州。这六列是我们将要提供值的列。通过这个改变，我们不必使用这些默认或空值。

我们只为这些列提供值，所以我将从这里删除默认值，然后是空值，最后是这个最后的默认关键字。因此，我们在这里提供的这六个值用于这六列。现在通过这个改变，我们也可以重新排列列的顺序。我们不必按客户表中定义的顺序列出它们。😊

例如，我们可以先放姓氏。😊，然后显然，我们也应该交换这些值的顺序，因此我们可以以任何顺序列出它们。现在，让我们执行这个语句。😊，现在如果你看底部的输出窗口，你应该会看到语句后面跟着一行受影响。不幸的是。

我无法调整这个窗口的大小来给你显示这个消息，但如果你看下面，你可以看到一条记录受到了影响，这基本上意味着一条记录被插入到这个表中。现在让我们看一下客户表中的数据。😊，好的。所以最后一行是我们插入的那一行。

你可以看到我的技能自动生成了值11。这是自增属性的效果。因此，它取最后一行的值并将其加一。😊，所以这里我们有名字，姓氏，生日。我们没有为电话属性提供值，这就是为什么我们没有值。

我们还有地址，城市，州，以及积分的默认值0。![](img/89d6aadd09799eb0a2adeb5a6b77e305_2.png)

哦。![](img/89d6aadd09799eb0a2adeb5a6b77e305_4.png)
