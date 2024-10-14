# 【双语字幕+资料下载】SQL常用知识点合辑——高效优雅的学习教程，复杂SQL剖析与最佳实践！＜快速入门系列＞ - P35：L35- 创建表的副本 - ShowMeAI - BV1Pu41117ku

![](img/635946abf0739e20a34437b943210825_0.png)

哦。In this tutorial， I'm going to show you how to copy data from one table to another。 For example。 in our orders table currently we have about a dozen records。 Now let's say we want to create a copy of this table called orders archived and we want to insert every row that we have in this table into that new table if we have 10 orders we don't want to code an insert statement with 10 set of values that is very time consuming so I'm going to show you a powerful technique to quickly copy data from one table to another。

😊，First， we need to create this new table orders archive for that。 we're going to use the create table as statement， so create table。Orders archived as。Now。 right after that， we write a select statement to get everything from。😊，The orders table。Now let's see what happens when we execute this query。There you go， so back in the navigator panel。

We have to refresh this view by clicking on this icon over here。Now we have a new table orders archived， let's look at the data。So you can see all the orders are here and we have the exact same columns as the orders table。 however， if you open this table in the design mode。😊。

You can see that in this table we don't have a primary key。 so the order ID column is not marked as a primary key。 and also it's not marked as an auto increment column。 so when we create a table using this technique， myQ will ignore these attributes and that means if you want to explicitly insert a record into this new table。

 we have to supply a value for order ID because this column is no longer an auto increment column okay。So。Using Cre Table as statement， you can quickly create a copy of a table。Now we refer to this select statement as a sub query。 so a sub queryry is a select statement that is part of another SQL statement。Now。

 we can also use a sub query in an insert statement， and that's a very powerful technique。 It allows us to do really cool things。 Let me show you。 So first。 let's right click the orders archive table。😊，And click on Truncet table because we want to delete all the data in this table。All right， it's asking for confirmation， let's trunk at the table。So now back to this table。😊。

Let's refresh the table， we don't have any records here， okay。Now back to our query editor。 let's say we want to copy only a subset of records from the orders table into this table。 like all the orders placed before 2019。 So first let's select everything from the orders table where。😊，Order date is less than 2019 January 1t。So。😊，These are all the orders， orders number 2 to 10。

 beautiful。 Now we want to copy these orders into the orders archive table so。😊。We can use the select statement as a sub queryry in an insert statement。Werite insert。Into orders archive Now we don't need to supply the column names because we're going to supply values for every column that we have in this query。😊，So。We did it that and。This is an example of using a select statement as a sub query in an insert statement。

Let's execute this All right， now back to the table。😊，Let's refresh the records。We only have the orders placed before 2019。Al right， here's a really， really。 really cool exercise for you Back to our SQL invoicing database。 Look at the invoices table。😊。So in this table we have these columns invoice ID number client ID。

 which is associated or related to the client ID column in the client's table followed by a few other columns Now let's say we want to create a copy of the records in this table and put them in a new table called Invoices archive however。 in that table instead of the client ID column we want to have the client name column So you need to join this table with the client' table and then use that query as a sub queryry in a create table statement Also to make the exercise more interesting I want you to copy only the invoices that do have a payment So if you look over here。

This payment date column determines if a payment has been made towards this invoice or not。 so select only the invoices that do have a payment date。 It's a really， really good exercise。 Spend2 to three minutes on this and then come by， continue watching。

![](img/635946abf0739e20a34437b943210825_2.png)

嗯。![](img/635946abf0739e20a34437b943210825_4.png)

All right， first I'm going to use the SQL invoicing database。Now let's select everything。😊。From the Invoices table。And join it with the client's table。Here I'm going to use the using statement to simplify my join what column are we going to use for joining the client ID column。😊，Let's execute this query up to this point。Alright。

 so first we see the client ID column that is used for joining these tables。😊，After that。 we have the columns from the invoices table like invoice ID number and so on followed by。The columns from the client table like name， address and so on。 Obviously we don't want all of these columns。 We only need the columns from the invoices table。

 but we should replace the client Id column with the client name column。 So let's have a quick look at the design of the invoices table。Here we have invoices ID， number。 client ID， we want to replace this column with the client name。😊，So back to our queryium。I'm gonna to pick you。Avoice ID。Number。And then client do name， let's rename it to client。

What other columns do we have here？We have invoice total and payment total。 so let's add those as well。Invoice， total， as well as payment total。We also have three columns。For dates， invoice date， due date and payment date， so。Let me close the Navigator panel。Invoice。 date， payment， date and due date。 Now， technically。

 because these columns only exist in the invoices table。 we don't have to prefix them with a table alias。So we could simplify the code like this。 However。 I personally prefer to prefix them because that gives me a more clear picture of how I'm joining these tables。 It's just a personal preference。 Another developer might disagree。 And that's perfectly fine。

 So whatever you prefer， That's perfectly fine。 Let's execute the query and make sure we get the right result。😊，So we have the invoice ID， number， client， beautiful， followed by these other columns。😊。Now we want to filter the result and return only the invoices that do have a payment。😊。So we can either return records that have a payment date or the records that have a payment total of greater than 0。

 Those are perfectly fine。 So back to our query。Down the bottom， let's add a word clause。Where payment date is not known， that's better， let's execute the query one more time。Now we get only this handful of invoices beautiful。 finally。 let's use our query as a sub query in a create table as statement。😊。

So right before select we type create table invoices archived as there you go。Let's execute the queryium。Beautiful now back to the navigator panel， let's refresh the view。😊。So here's our new table invoice as archive。 Let's look at the data。There you go。We only have the invoices paid， and heres the name of the client for each invoice beautiful。Now。

 just note that if you execute this query one more time。 you're going to get an error because we already have a table called Invoices archive Later in the course。 I will show you how to drop tables。 That's pretty easy。 But for now you can just right click and go to drop table。😊，And then confirm。



![](img/635946abf0739e20a34437b943210825_6.png)

Allright， and then you can run the query one more time。😊，Yeah。![](img/635946abf0739e20a34437b943210825_8.png)