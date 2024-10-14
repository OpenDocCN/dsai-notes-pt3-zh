# 【双语字幕+资料下载】数据可视化神器 Tebleau！无需编程，使用拖拽和点击就做出超精美的图表。1小时新手教程，从安装到做图一气呵成~＜快速入门系列＞ - P9：9）在 Tableau 中创建新视图 - ShowMeAI - BV1T341117q7

In creating a view， you should always start with a question that will be answered by your visualization。 Do you want to know how much sales growth you had this year。What category can you group your customers into。Once you have a question in mind。 you can start developing how your view will look。

![](img/c3650f5386fb2ff3f4543fd84c2180d4_1.png)

There are four ways to create a view in Tableau desktoptop。First is to drag fields from the data pane and dropping them onto the cards and shelves。 Here。 we will drag the sales measure into both the color and the marks card。Then we will add the product category into the label。Upon doing so。

 we now have a tree map in our view that has a rectangle。 which shows how much sails each category brings and is also color coded based on the sails from the least。 which has a light blue color up to the greatest sails， which has a darker blue shade。😊。This method is great to use if you are already familiar with how fields and the placement of cards affect a visualization。

The second way of creating a view is by double clicking one or more fields in the data pane。In this second worksheet， double click the dimension field zip code。 This will execute a query to process the zip code and order generate its latitude and longitude。Once done， double click on the measure field shipping cost。

The shipping cost has dictated the size of each point or circle in the symbol map that was created。 This second method is useful If you are not particular with the type of chart or graph to use。As Tableau automatically generates the view based on the type of fields you have selected。Third。 you can create a view by selecting one or more fields in the data pane。

 Then using Show me to set a chart。In this view， select the dimension customer segment。 Then hold the control key in your keyboard and select the measure order quantity。Once the fields you need are already selected， navigate to the show me button in the upper right and select the horizontal bars chart。Once the chart is selected， Tableau generates the horizontal bars grouped by a customer segment with the length of each bar based on the total order。

 quantity。Using the Show me method is great for beginners so they can familiarize themselves with the types of charts available based on the fields selected。The fourth method is by dropping the fields into the drop field here grid of the canvas。Drag the order date into the column header grid。Once done。 drag the product name into the row grid by dropping it into the leftmost side。

 which shows a broken line indicator。Finally， add the field profit as the values。As a result。 a text table has been created。Do take note that this fourth method is only limited to tabular views。![](img/c3650f5386fb2ff3f4543fd84c2180d4_3.png)

It is also essential to understand how the placement and type of fields affects the output visualization。![](img/c3650f5386fb2ff3f4543fd84c2180d4_5.png)

As we have discussed from the data concepts。We categorize data as either dimensions or measures。 then classify them as either discrete or continuous。 Let's look at how each type creates a different chart。A discrete dimension creates categories or groups of the values。 For example。

 we have a single bar on this sheet， which marks the total sum of sales。Obserbve what happens when we add a discrete dimension to it。 Dr the product category into the columns shelf。As you can see。 it has separated the bar into three using the product category， which is a discrete dimension field。

Most of the time， dimensions are categorized as discrete because they contain separate。 unique values。But an exception to this is the date data type fields。 A date can be converted into either discrete or continuous。 Let's look at how it is visualized in this sheet。We are still using sales as the measure value。

 Tra the order date into the columns shelf， then click on the fields。 drop down and convert it to continuous。 This makes a line chart that is automatically sorted according to the data of sales shown by year。 A continuous dimension creates a numeric axis in the visualization。Now。 let's see how a continuous measure looks。At the same line graph that we have created。

 the sail sp placed on the row shelf is set as a continuous measure。 as you can observe on the vertical axis of the graph。 it has created a range of values。 starting from 0， up to 4 million。Measures are mostly categorized as continuous。Due to their range of values。 But that does not mean that you cannot use a discrete measure。

Let's clear the items on this sheet and create a new chart。 Dr a discrete dimension field of product subcatego into the row shelf。 Then let's include the measure。 drag the sales and place it on the rows after the product sub category。 Notice that since this is still a continuous measure， It created a bar graph。

 which has its individual axis per row。 Look at what happens when we convert it to a discrete measure。In the dropdown of the sales field， set it as discre。Because of the conversion。 the bars were replaced with plain text。 A discrete measure is visualized as labels or plain text in the visualization。Another essential part to learn when were creating a view is the Mars card。

 The Marx card provides you with control of how the points or marks will look in a view。It can apply different properties to the marks of the graph。 which adds additional meaning and detail。 The first part of the marks card is a drop down list where you can control the type of mark displayed in the view。 The default mark is set as automatic， wherein Tableau will generate the best mark type for the data。

In this sheet， we have some of sales on the column and some of profit in the rose shelf。 Since both fields in the shelves are continuous measures。Tableau automatically generates a shape marked type to plot the total value between both measures。The automatically selected mark type symbol is visible in the drop down。

 Observe the changes when we change the sum of sales into a discrete dimension。Let's remove the sum of sales pill and drag in the customer segment field。 The mark of each value is now set as a bar。 The symbol of the mark's card was also changed to a bar Setting the mark type to automatic will let tableau choose a mark based on the type of fields that we drag into the row and column shelf。 This does not mean that you cannot change the mark according to your preferences。

You can always choose a different mark type on the list if you need a different view， for example。 we can easily change this bar graph into an area chart if we set the mark type to area。Below the mark type is the color using different colors。 lets users easily distinguish the different marks on the view。 The default color is set to blue。

 but you can customize this based on a static color by choosing a new color from the palette。 or by dragging a field into the colors card。 for example。 Let's change the mark type back into a bar， Then drag the customer segment field from the data pane into the colors card。 This applies individual colors to each bar of customer segment。To change the colors used。

 you can click on the colors card and select the editit Col button in the new window。 you can assign a different palette from the drop down or choose a new color for each segment using the current palette。Next， we have the size card in the current bar graph。 This adjust the bar's width。You can use the slider to increase and decrease the size of the marks。 Same as the color。

 You can also set a dynamic size based on a field by dragging it to the size card。 The shape card is only visible when the card is set as a scatter plot， symbol map or circle views。In this sheet， we have a scatter plot， which currently has one single point。 showing the intersection of the total sales and profit。

Let's add a field to the shape card and see what happens。Add the product category field into the Shapes card。Before we indicated a discrete dimension as the indicator for shape。 the single point was now divided into three different shape of marks based on the members of the dimension。

Clicking on the shape card will open a new window where you can choose the shapes to use or change to a different shapes palette。 In addition， Tableau also provides a legend to the right of the canvas to serve as reference。Another way of adding separate marks to the view is by using the detail card。 droppingping another dimension into the detail card adds another level of granularity to the view。

 For example， let's add the product subcatego to the details card of the scatter plot。 This adds additional points of products in the grid， but it does not change the structure。 and the points are still divided by shape using the shape card。Above the shape card is the label。 simply put， it dictates the labels or text values that will be shown in the view。For example。

 let's continue working with this scatter plot and indicate a label for each point。Drag another product category field from the data pane into the label card。 This adds the product category name for each point。Additional options for changing the font color and label alignment are available when clicking the label card。

When working with a tabular data such as this fourth sheet， the label is replaced by text。It allows you to insert plain text values into the table。 You can add additional fields or text into the table by clicking on the text card and clicking the three dots to open the text editor window。From this window， you can also set the font， size， style， color。

An alignment of the text in the table。Finally， we have the tool tip。Tool tip is the information that appears when you hover over one or more marks in the view By default。 the tool tip will contain information about the fields that we have added to the view。 such as the fields on the columns and rows。 and the field used for the marks。

 The tool tip can contain both dynamic and static text to add a field information on the tool tip。 drag the field into the tool tip card。 For example。 Let's set the measure order quantity into the tool tip。Dragging it to the tool tip cards as the aggregated value of the measure or dimension into it。

 you can edit the text formatting and arrangement by clicking the tool tip card。There are four ways to create a view in Tableau desktop。First is to drag fields from the data pane and dropping them onto the cards and shelves。 Here。 we will drag the sales measure into both the color and the marks card。

Then we will add the product category into the label。Upon doing so。 we now have a tree map in our view that has a rectangle。 which shows how much sail each category brings and is also color coded based on the sails from the least。 which has a light blue color up to the greatest sails， which has a darker blue shade。

 The second way of creating a view is by double clicking one or more fields in the data pane。😊。In this second worksheet， double click the dimension field zip code。 This will execute a query to process the zip code and order generate its latitude and longitude。 Once done， double click on the measure field Shi cost The shipping cost is dictated the size of each point or circle in the symbol map that was created。

Third， you can create a view by selecting one or more fields in the data pane。 Then using show me to set a chart。In this view， select the dimension customer segment。 Then hold the control key in your keyboard and select the measure order quantity。Once the fields you need are already selected， navigate to the Show me button in the upper right and select the horizontal bars chart。

Once the chart is selected， Tableau generates the horizontal bars grouped by a customer segment with the length of each bar based on the total order。 quantity。The fourth method is by dropping the fields into the drop field here grid of the canvas。 Drg the order date into the column header grid。Once done。 drag the product name into the row grid by dropping it into the leftmost side。

 which shows a broken line indicator。Finally， add the field profit as the values。As a result。 a text table has been created。Do take note that this fourth method is only limited to tabular views。 Another essential part to learn when we're creating a view is the marks card。 The Mars card provides you with control of how the points or marks will look in a view。

It can apply different properties to the marks of the graph。 which adds additional meaning and detail。 The first part of the marks card is a drop down list where you can control the type of mark displayed in the view。 The default mark is set as automatic。 wherein Tableau will generate the best mark type for the data。In this sheet， we have some of sales on the column and some of profit in the rose shelf。

 Since both fields in the shelves are continuous measures。Tableau automatically generates a shape marked type to plot the total value between both measures。The automatically selected mark type symbol is visible in the drop down。 Observe the changes when we change the sum of sales into a discrete dimension。

Let's remove the sum of sales pill and drag in the customer segment field。 The mark of each value is now set as a bar。 The symbol of the marks card was also changed to a bar。 Se the mark type to automatic， will'll let tableau choose a mark based on the type of fields that we drag into the row and column shelf。 You can always choose a different mark type on the list if you need a different view。 For example。

 we can easily change this bar graph into an area chart。 If we set the mark type 2 area。Below the mark type is the color using different colors。 lets users easily distinguish the different marks on the view。 The default color is set to blue。 but you can customize this based on a static color。 by choosing a new color from the palette。

 or by dragging a field into the colorss card。 For example。 let's change the mark type back into a bar， Then drag the customer segment field from the data pane into the color card。 This applies individual colors to each bar of customer segment。 Next。 we have the size card In the current bar graph。 This adjust the bar's width。

You can use the slider to increase and decrease the size of the marks。 The shape card is only visible when the card is set as a scatter plot， symbol map or circle views。In this sheet， we have a scatter plot， which currently has one single point。 showing the intersection of the total sales and profit。

Dropping another dimension into the detail card adds another level of granularity to the view。 For example， let's add the product subcatego to the details card of the scatter plot。 This adds additional points of products in the grid， but it does not change the structure。 and the points are still divided by shape using the shape card。

Above the shape card is the label simply put it dictates the labels or text values that will be shown in the view。Drag another product category field from the data pane into the label card。 This adds the product category name for each point。 Finally， we have the tool tip。 To tip is the information that appears when you hover over one or more marks in the view。

 by default， the tool tip will contain information about the fields that we have added to the view。 such as the fields on the columns and rows。![](img/c3650f5386fb2ff3f4543fd84c2180d4_7.png)