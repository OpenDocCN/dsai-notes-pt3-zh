# 【双语字幕+资料下载】PySpark 大数据处理入门，带你玩转Python+Spark大数据操作与分析！＜实战教程系列＞ - P5：L5- Pyspark DataFrames 分组和聚合函数 - ShowMeAI - BV1sL4y147dP

。

![](img/1babe07f0737b77a8ca240e4a3c70599_1.png)

Hello all， my name is Krisnaak and welcome to my YouTube channel。

 So guys we will be continuing the Pipar series and in this particular video we are going to see group by an aggregate function。

😊，Already I have actually created somewhere around four tutorials on Pipar。

 this is basically the fit tutorial。 And again， this is a part of a data frame。

 why we should actually use group by aggregate functions again for doing some kind of data preprosing。

 So let's begin for this particular data for this particular problem I created a data which has three features like name departments and salary and you have some of the data like Kris data science salary。

 right， something like this。 So over here in short。

 if I want to basically understand about this particular data they are some departments probably where Krisish and other people teach and based on different different departments。

 they get a different different salary， So let's see how we can perform different different group by an aggregate functions and see how we can preproces or how we can get some or retrieve some kind of results from this particular data。

 So to begin with what we are going to do we are a first of all going to import Pipar。



![](img/1babe07f0737b77a8ca240e4a3c70599_3.png)

![](img/1babe07f0737b77a8ca240e4a3c70599_4.png)

SQL import。Spark session， as usual， we have to create a spark session。 So after this。

 what we have to do， I'll create a spark variable。 So I'll use spark session， dot builder dot。

Ap name， I think everybody must be familiar with this。 but again， I'm trying to show you this one。

 So let me write it as aggregate。Dot。Get or create。 So now I've actually created a spark session。

Okay， probably this will take some time now if I go and check out my spark variable。

 so here is your entire information okay。With respect to this particular spark very well。 Now。

 let's go ahead and try to read the data set。 Now， I will just write D F underscore pi spark。

And then here I'll write Sp dot read。Dot CSv， the CV file name is basically test。3 dot Csv。

 And remember， I'll be giving this particular CV file in the Github also。

 and then I'll be using header is equal to true。Coma infer schema is equal to2。Now。

 this is my dear underscoreosscope by spark。Now， what I'll do in the next statement。

 I will write Df underscorecope pipar dot show。Right now here you'll be able to see that I am actually being able to see all the data sets here I have name。

 departments and salary on all this particular information。

If I really want to see the schema or the columns like which all columns where it belongs to。

 just like a data types， I can definitely use DF underscorecope Ipar。

Dot print schema right and now here you can see name is a string department is string and salary is basically an in teacher okay。

Now， let's perform some group by operation。 First， we'll start by group by operation。

Probably I want to group by name and probably try to see what will be the mean average salary。

You know what suppose let's let's take a specific example over here。

 So I'll write Pf dot underscorecope bypar dot group by。

 supposeupp I want to go and check who is having the maximum salary out of all these people that are present in this particular data set。

 So I'll first of all group by name if I execute this you can see that we will be getting a return type of group data at some specific memory location。

And you should always know that guys group by aggregate functions works together。

 That basically limits is first of all， we we need to apply a group by functionality。

 and then we need to apply an aggregate function。 So aggregate function here really want to check just press dot and press tab So here you'll be able to see a lot of different different function examples like aggregate average count max mean pi and many mode right now what I'm going to do I'm just going to use this dot sum because I really need to find which is the maximum salary。

😊，HoweverFrom out of all these particular employees， who is having the maximum salary。

 So here I'll say dot sum。 And if I execute it， you'll be able to see that we are getting a sQL dot data frame。

 which has name and sum of salary。 This is very much important as sum of salary because I really want to have the sum of the salary。

 remember， we cannot apply sum on the string。 So that is the reason it has not done over here。

 it is just giving you the name because we have group by name。

 And this dot sum will just get applied on this particular salary。 Now。

 if I go and write dot show here you will be able to see。😊。

Sudanhu over here is having the highest salary of 35000。 Sunny has 12000。 Krissh has 19000。

 Mahesh has 7000。 So if you go and see over here， Sudanhu is basically present here。

 here and in big data。 So overall， his salary should be 35000 if you compute it Similarlyly。

 you can go and compute my salary over here。🤧Over here by just calculating this。

 and then you can also compute sunny salary。 and you can also see my H。

 So this is one just an example。 So here I'll just write。 we have grouped。Do fine。The maximum salary。

AndDefinite over here from this entire observation。

 we can retrieve that Sudanhi is having the highest salary。 Okay， now let's go to one step ahead。

 one more step ahead。 now we will try to group by departments to find out which department gives maximum salary Okay。

 we are going to do a group by。Departments。Which gives maximum salary。 Suppose this is my。

This is my requirement。 Okay， and different different types of requirement makeup up。

 I'm just trying to show you some examples。 So I'm just going to copy this。南 going do。

Use this department。Okay， and then I'm basically going to say dot sum dot show。

 If I execute it let me see department is a wrong column name so I'll write department it is department So let me write S now if I go and see Iot over here gives some salary around115000 to this employees to all the employees right combined because we are doing the sum big data gives somewhere around 15000 data science gifts Im around 4300 Now suppose if I go and see big data over here 404080008000 and 13000。

130015000 so I hope I'm getting yes， big data is actually giving us 15000 so you can go and calculate it suppose if you want to find out the mean you can also find out the mean okay。

 so let me just write it over here， just copy this entire thing paste it over here and write me write instead of instead of sum I'll write to write mean so by default the mean salary。

Here you can see that for a particular employee somewhere for I O T to 7500。

 because this mean will be based on how many number of people are working in the department， right。

 So like this， you can actually find out Now， I can also check one more thing。 guys， I can copy this。

 I can try to find out how many number of。Employees are actually working based on the department。

 so I can use dot count。 And then if I go and execute this， probably this is a method。Okay。

Now here you will be seeing that in Io there are two people in big data there are four people in data science they are four people。

 so4 plus 4 plus8 total employees that are present over here is basically 10。Now。

 one more way that I can basically apply a directly aggregate function also to see。

 these are all some of the examples and again， you can do different different group by let me use Df Ppar。

 suppose I say dot aggregate okay， and inside this I will just give my key value pairs like this。

 suppose I say let me say that salary， I want to find out the sum of the salaries。

The overall salary that is basically given to the entire total expenditure insert。

 So the total expenditure that you will be able to see somewhere around 73000 alright。

 so we can also apply direct aggregate function， otherwise this all are also aggregate function which we basically apply after after you know applying a group by function now suppose this are probably the salary I want to find out suppose I'll take this example I want to find out the maximum salary that the person is basically getting who is getting the maximum salary sorry。

So here instead of writing dot sum now I'll write max dot show now here you can see Sudansha is basically getting 20000 over here10000 Krisish is getting 10000 my is getting for 4000 right so all this particular data is theyy Kris is basically getting with respect to data science over here 10000 so it has basically picked up it is not picking up both the records but at least when it is grouping by name and then it is showing this particular data that time you will be able to see it let's see whether Ill be also able to see this or not。

So group by， if I score and write min。So here you will be able to see minimum value with respect to different different records when Im grouping by here you will be able to see that Suanhu sorry。

 Sudanhu is getting a minimum salary of 50002000 Kris is getting a minimum salary of 4000 right。

 we can also get that particular information。 Now let's see what all different different types of operation are there。

Average is also there。 So if I write A V G， it's just like mean only guys。

 So this is basically the mean salary that probably again。Again。

 you can check out different different functionalities why these all things are basically required。

 Under one thing is that you really need to do a lot of data preprosing a lot of retrieving skills that you basically do。

 You can check it out this one and you can do different different functionalities as you like。

 So I hope you like this particular video Probably in the next video I'm going to start with spark Mlib libraries where we'll be solving some machine learning algorithm problems。



![](img/1babe07f0737b77a8ca240e4a3c70599_6.png)

So I hope you like this particular video I'll see you all in the next week。

 Have a great day thank you baba。