# 【双语字幕+资料下载】Tebleau操作详解，照着实例学做图！数据科学家的必备可视化工具，简单快速做出精美图表！＜实战教程系列＞ - P21：21）关系、联接和合并 - ShowMeAI - BV1iq4y1P77U

Hi folks， welcomelcom to another episode of Tableau in two minutes。 I know it's been a long time since we last posted one， but I've found a better time。 and hopefully we can do a few videos over the next over the next few weeks and few months。 The first thing that I want to cover， though is something that is a new feature introduced in tableableau 2020 do2。

 And that is changes to the data model where you can now create relationships instead of just having to join and union your data like you were writing a SQL script。 The relationships make things super flexible。 So sort of sort of excited to。😊，To get into them。

 So why don't we talk from about why you might want to use them and why they are a little bit easier than the old way。So these joins are don't require any knowledge of SQL to work well。 you know。 you can set up a relationship without having to know whether it's a left join or a right join or whatever。 So instead of spending all the time preparing your data， you're going to spend more time exploring。

 visualizing， sharing and all that sort of thing。OurRe are also going to help sidestep some of the issues with granularity where Tableau is going to be less sensitive to where you put which table and the order in which the relationship is defined right so if you didn't have your most granular table as the one that everything else was being joined to sometimes you ended up duplicating rows or making other mistakes or if you had two tables that had different levels of aggregation when you joined them together sometimes you could end up creating sort of weird dupplications of data and you had to be very careful and spend a lot of time cleaning up the data before you ever brought it into tableableau in order to try and avoid those sort of issues。

 I don't know about you but I have spent a lot of time cleaning up my data and aligning it so that the aggregations are all correct when it gets pulled into tableableau。Tableaus also introduced this concept called smart aggregation that means you have less risk of accidentally duplicating the data or accidentally getting the answers wrong or something like that if you're using data from multiple sources。

 So what tableau is going to do in the background is instead of having everything like prepackaged into tables。 it's going to aggregate the data at a different level for each visualization depending on what pieces you bring into the view。 So we're going to take a look at that in a second。But first of all。 we're going to take a look at relationships right。

 So because you don't have to make such a strict choice early about how you're going join your data that allows。 that's what allows this level of flexibility。 So we're going to see what that looks like as you're building the data。 So the first thing that I'm going to do is I'm going to join to this bookshop data set。 that tableableau's example of how and why you might want to use the relationships instead of traditional joins and things like that。

 And this is a great data set to try with because there's a whole bunch of stuff that we can pull together。 So the first thing we're going to pull in is this book table。😊。This is like the base table of the data。And with this base table。 we're going to sort of build the relationships from this table right so the concept is that we have some data about books。

 books can have a book is obviously a book， but a book can have multiple editions so it might have a hardcover version。 a softcover version， in addition to that we have information about the author who the publisher is。 whether there's any ratings or awards， and we have some sales data about these these books as well。So we've added our first table， we've added the book table here and the first。

 the other table I'm going to just add is the awards table。😡，Right， so when we add the award table。 you see we get this edit relationship dialo box。 We can choose the field from the book table and the field from the award table that should match in order to。

Define the relationship between these two。 we can also， if we want to。 we can add more fields so we could， if we needed to join on more than one criteria。 we could add that as well。And we also have these performance options。 Now。 performance options are similar。To what you might find or what you might think about when you do a join。

 But they are a little different。So first， we can adjust this cardinality of the join。 I think the thing to remember about both of these options is if you're not sure whether you should change it。 you should probably leave it with a default。 The default's going to do a good job in most situations。 you might get some small performance benefit。 if you change some of these options with the right data set。

 But the risk is that if you do it with the wrong data set。 It's going to。Going to give you the wrong， the wrong information， so。The default is many to many。 but if one of your data sources had one line for every value， right， you could set this as one。And when you do that， tableau pre aggregategregates the data rate。

 so it pulls the data together before it pulls it into the visualization。 and that has some performance enhancements， right， It makes things perform a little bit better。 particularly if you have a big data set。 But if you have if you think you have one row。 but you actually have more than one row that will duplicate items in this data set and that will cause you issues。

 right， you'll get the wrong answers to some of your calculations and things like that。 So bottom line is if you're not absolutely certain that you only have a unique row for for each value in this key。 you should leave this as many to many。Now， for referential integrity， again。 default values are probably the best， but you have two options。

 you can select either some records match or all records match。😊，If you select some records match。 then Tableau is going to look to see which ones it does， right， and's as it builds its query。 it's going to look to see which relation which records match and which records don't match。If by selecting all records match， you can tell Tableau that we know already that all records match and that helps behind the scenes right that's going to help make the join a bit simpler and it's going to potentially speed up or make your visualization more responsive。

😡，For a small data set， it's going to make not that much difference， but for a big data set。 it can be quite helpful， but again， if you're not sure it's best to leave it as a default because if you don't leave it as the default or you put it as all records match。

But all records don't match。 You're gonna end up missing， missing data。So here's what we're going to do。 We're going add we've sort of walked through this dialog box。 Let's go ahead and add the author's table as well。 You'll see that the award that was joined on the title。

 Now we have something that's joining on the author I and we have all the same options right So we're going leave it as default many to many summer records match and summer records match。😊，Now， why don't we go for one that's a little bit more challenging For this one。

 I'm gonna to add the info table。 Now， up until now， when we added the author in the award table。 the fields that we were joining on had the same name in both tables。 But when we add the author table， there aren't fields with the same name in both tables in both both tables。 So it's not sure what to join on。 So we get this red exclamation point in the triangle and it says we have to select the matching fields in order to create this relationship。

 Now， one of the great things about this new version of tableau is that we can create what's called a relationship calculation。 Now that means that we can sort of combine these two fields like in the edit relationship dial box instead of having to do it either in the data source or to come up with some other way of doing it Tableau wasn't super flexible if you didn't have two matching fields。

 even though you may have the same information in both of them。 Now。 I know from looking at the data and I'll post a link to the data in。😊，The video description。But I know that this book I field is the combination of book I 1 and book I 2。 So we're going to concatenate book I 1 and book I 2。 And to do that。

 we're going to create our relationship calculation。 There's just a regular calculation dialog box。 See we can pop out all of our functions on the side here， and we're going to say book I 1 plus。Book ID 2。Apply that。And we've created our join。 and you can see when you look at it right。 if we look at the data here， the book I 1 is two letters and then book I2 is three numbers。

 and if we click on book，And we look at the book table。 You can see that that's， again。 it's those two letters plus the three numbers。So that is now。Successfully joined now。Much more flexible。T SQL， a lot easier to use than SQel 2， to be honest。 Alright。 So we're gonna add a couple more tables here， And I'm gonna show you something else。

 First thing we're gonna do is just add the edition table。 note that where you drag it， right。 different， It's trying to join to different tables。 We want to join to the book table。 So we want to make sure this little orange squiggly line when we drop it。😊。With the orange squiggly line points to the book table， not one of the other tables。 Again。

 we want that to join on book I D。 So that is fine。 Now， we have our addition table。 We're join the sales table to it。 We're gonna take the sales table。😊，Out over here。 the sales table joins to the addition table。Oh， hang on a second。 I've joined it to the wrong table。 It's not gone well。 There we go。There we go。 Allright。

 So now we're connected to the edition table on the ISBN number。 know anything about books。 the IBN number is what identifies a particular， a particular edition。So now that we've dragged the Q1 table out we have some sales information and this is all nicely going to aggregate together。 but we have different sales tables for each quarter， so we have one for Q1， one for Q2， one for Q3。

 and one for Q4。😊，So what I'm going do is I'm going to we have to union these together， right。 So a union is a sQL concept。 and it's still present in tableableau。 We didn't get completely away from it。 And what a union does is it takes two tables with identical structures。 and it basically stacks them on top of one another so that instead of one table， we get。Sorry。

 instead of two tables， you have one table with all the information of both tables in it。 Now。 all the columns need to be the same。 and they all need to be the same data type。 And sos there's some restrictions to it。 But fundamentally， that's what we're going to do。 And that's what we want to do with these tables， right， because we have sales data for Q1。

 We have sales data for Q2， Q3 and Q4， And we want to put them all together so that we have a full year。 So what we're going to do is we'll take this Q2 data。 And to create a union between two tables。 So that is to stack one on top of the other。 We're going to drag it until it sits just under the Q1 data。 And we get this little orange union dial box pop up。We're going to drop it there。

And then you'll see that our sales Q1 data now has changed a bit。The Excel Q2 data has disappeared。 but we've got this icon。On the left hand side。 And if we hover over it。 it tells us what's going on inside that data。 So sales Q1 is made up of two tables。 And we can see that from this little piece in here。 Now， if we wanted to dig further into that。

 as it says， we can double click on the sales data。 And this digs in right deeper and then shows us what's happening behind the scenes。 So in order to edit the union， we have to go back in here and click， edit union。And you can see these are our two tables。 And if we wanted to add more tables to this， right。

 we can add the Q3。And the Q4 sales data。Click， O。So we can do it that way。 Let's remove them from this。Okay， so we're going to jump out of there。 I'm gonna x out of that。 But if we could also add them out here， right， so we can drag them and I can drop it right here。And then， I'm going to go。Back in here， right。 So now I've added Q1， Q2， Q 3 and Q4。

 And when I doubled click。I go inside， and I go in here to edit the union。You can see that I have all my four tables stacked on top of one another。 Now I'm going to temporarily remove these tables because one of them。Is doing something funky somewhere else down the line。 I was just testing that earlier on。

 So we'll get back to that。 But that is how you could uni in the four tables together。 That dial box is also how you could join two fields together。 Now。 we defined the the author relationship。And by。Using this line right here， right。 at by just dragging it out and dropping it in。 But let's say that we wanted to。

Join it directly to the book table。 So what I did is I double clicked on the book table just the same way we did with the sales table。 And this is where your traditional sQel joins are hidden。 So if I drag out my author table now。 you can see that I get this little symbol and this little symbol is telling me that instead of it being a relationship now we're defining a join。 And if you've used tableableau before in all the previous versions， right。

 you'll be pretty familiar with this interface。😊，We click on the little Venn diagram and that allows us to define the type of join that we want to do。It allows us to define what the fields are， if there's more than one field。 we can add that down here， and so on and so on and so on。If you're not familiar with SQL。 you might not be familiar with exactly what some of these words mean。

 but it's pretty simple and the Venn diagram really helps you figure it out。The four join types that we have here， you have an inner join in an inner join。 we're going to take all of the records from the book table。And all of the records from the author table that match。

 So a record from the book table must have a match in the author table in order to be included in the what what's output from the joint。 right， in order to join together and vice versa。 So a record from the author table must have a match in the book table。

In order to， to be included in this join。If we were to use a left join。😡。That's going to include anything from the left table， in this case。 the left table is quite literally the table on the left。And it's going to include all the records from this table and any records from the author table that match。

 So anything from the author table that has a match in the book table is going to be included。 anything from the author table that has no match is going to be excluded。If we were to go with the right join， it's the same thing， but we're heading in the other direction。 So anything from the right， we're going to get everything。 Sorry， from the right table。

 from this author table， but only those books that match。They have a match in the author table。And then our final option。The full outer join， sometimes called a full join。 sometimes called outer join， they're basically all the same thing， not basically all the same thing。 they are all the same thing。 that's going to include all of the records from both tables and where possible it's going to match them up and where there's no match。

 it's just going to fill in nulls So you're going to get every record from the book table and every record from the author table regardless of whether they match or not。So， so let's think about that， right， Let's， let's think about doing an inner join between these two tables。

So we have one book， one author。 Those joined great。 We're only including books with authors。Because it has to have a record in both tables， right for our inner join， but。If we have a book with two authors。What happens is both those authors will get joined to the book。 right， so we'll have one book。And then。We'll have another record for that book with the second author。

 So I have one record for that book for the first order。 one record for that book for the second order author。So that's going to potentially duplicate rows in the book data set。If we did this join and anywhere that we use this join table。 we're going to have to deal with that duplication issue。 Now sometimes it's a deal breaker。 sometimes it's not a deal breaker， depends on exactly what you're trying to do。But the bottom line is that duplication is something we don't really want。 And we can avoid that instead by removing this table from the join inside the book data source and leaving it as defined by this relationship up here。

So since relationships are so flexible right， well why might we want to go back to joins why might we want to have something that we do inside one of these like data blocks inside one of these tables instead of just defining the relationship well。Relationships are great， but。There might be certain things where there's something in the data or there's some particularly unique aspect to this relationship that requires us to have that very specific level of control and level of granularity that we get through the joints。

We might have something where。If those two tables are not joined together in a specific way。 one of them does not aggregate correctly， or one of them doesn't count correctly。 So。 so we want to be aware of that as we walk through it with our data， these are typically。 I think if you're working with a lot of data， you'd probably be aware of these types of issues before。

 right， because this is not the only place where you would have to deal with them。So。 so it's worth bearing in mind。 It's worth knowing how to do it。 but relationships super flexible and very much a a big step forward in terms of the data model。Now。 for those of you coming from the old Tableau。😡，say the old tableau right it's only been not around for a few months。

 but from the old data model， I guess a few things have changed in 2020 dot2 that we want to take a look at。 So the first thing is you'll see over here on the left hand side instead of being organized by dimensions and measures and having dimensions pan up top and a measures pane down the bottom now we have individual tables and the fields that come from each individual tables。

 so we have all of the fields from our author table here。 we have the dimensions and we have a line and then we have the measures from each table。😊，So。That changes a little bit the way calculations behave。So if we were to create a calculation that just used this author table， right。

 so let's go ahead and create a calculation that is the percentage of time each day an author spends writing。Okay， so we're going to take the hours writing per day。 We're not going aggregate it。 We're just going divide it by 24。Now you see that when you do that， that's a row level calculation。 there's no aggregation within the calculation itself， right， so it's a row level calculation。

And because it's a row level calculation and it is only using fields from the author data source。It sits right here in the author data source。 It doesn't go anywhere。But。If we were to create a calculation that combined two different fields。 So say we wanted to get the sales price for a book， right， now。

 the sales price consists of two things。 It consists of the price。 which comes from the addition table， and then it。We subtract the discount。 and the discount comes from the sales table。So if we were going to do that。Let's go ahead and create that calculation。Fky capitalization in there wops。 There we go。 Alright。

 so it's price minus discount。So when we create that calculation and apply it。 you'll see that it doesn't pop up in either of the two data sources。 It goes all the way down here to the bottom。 and down at the bottom is where we're going to have all of our calculations that。Cover multiple。Tables or multiple things， right， They're using those relationships in order to create the calculation。

 And one of the things we want to remember is that when those calculations are being calculated。 when they're being run， when tableau is figuring out what the answer is。 it's using an inner join between these two tables in order to make it work。Now， if。The reason that's worth remembering right is because if we're doing things that aggregate in certain ways。

 we're not going to get any records that don't match between those two tables。 any records that don't have a key between those two tables。Right。 so if we wanted to figure out what the sales price was for every single book。In。That had an addition， right？ And we summed this， this sales price。U。

We would only get because it's doing it in a joint， right， Remember。 So we need a record in both sales。 We would only get additions for which at least one item has been sold。 If no items have been sold， it still has a sales price because it was still on a shelf somewhere for sale。 hasnn't been sold， but it was for sale。But because we don't have a record in the sales table。

 it doesn't pull in the price for that record in the addition table， which means potentially。We don't get the total sales prices， right， for everything。so。Definitely worth thinking about。 particularly if you get unexpected results or anything looks odd in the data。 something to watch out for。 Now， nine times out of ten0 rate。

 these things are not going to come back and bite you， but if you do see something odd。 it's definitely worth looking at。So a couple of other things that。We want to look at。 sorry。 one other thing that we want to look at。In the old world， when you created a constant。So when I just typed in one， right up here。It would put that one。

 that one by itself as a row level calculation， so it puts it on every single row in the data source。Which used to mean that if you summed it up just like this。 you would get a sum of the number of records in the data source because， you know。 a row level calculation， as we know， is calculated once for every single row。

This one is calculated is still being calculated for every single row。 But when we use the relationship based data model instead of the join based data model。 we're only pulling in to the visualization the data that is relevant for that visualization rate。 So when I created this one up here， there's only one row in our data source。

 So the sum of all of the rows in our data source is one because the only data point that we've brought in is this constant。😊，So。So what happens then， right， if we bring in， let's say we bring in author。I will bring in the last name of the author。 There we go。Now you see that。I've still got one for each。Each row in my data source， right。

 each one of these authors is now a single row in my data source。That's the data source that's being used to generate this visualization。 So。 so each author has a value of one or or this constant is showing for each author。 And if we summed it up， we'd get however many authors there are in this data set。 Now。

 remember that， right， Every author has a value of one。With this constant， until。We bring out the title。Yeah， the title to it。 well now。Dantic cat。I'm。Because they've published a number of titles or because this person's published a number of titles。 right， you've got 1，2，3，4，5，6，7，8 titles that they've published。

 There's eight values for this constant。In the data set。 So instead of having one。 So we've gone。 we started off with just a single row in our data source。And it was the total was just one。 there was only one。Whereas then we added in the authors and we had a one for each author。 And now we've added in the title。 and now we're getting a one for each title and each author。 right。

 So we've got two。For this author， we've got8， as I said， for this author and so on and so forth。 So the bottom line is。Constants don't necessarily behave the way that you might expect them to behave if you use them in the old world。Again， why might you care。 The real reason is that as you look at workarounds and as you look at tricks and things like that。 a lot of them use these constants in order to represent certain things。 So we want to。

Just be careful when we do use those workarounds that what we're actually getting is the result that we expect from you know。 from using that that constant。I so。😊，Will be helpful if we knew how to troubleshoot these sort of data sources and we'll dig into these calculations in a little bit more detail in a future video so expect to see a little bit of information about how we can troubleshoot some of our data sources both from a relationships perspective and from a join perspective and some videos around calculation coming up at some point in the not too distant future but for now I really appreciate you watching if you like the content please go ahead and hit that subscribe button and you'll get more tableau and data analytics content as we go forward there's a link as I said to this data set in the video description so if you want to download Tableau public and follow along that's great that's exactly what I use totally free very cool and I look forward to seeing what you have to say in the comments and speaking to you next time。

😊。![](img/771599ba487d4847a03dea1e21567f41_1.png)

![](img/771599ba487d4847a03dea1e21567f41_2.png)