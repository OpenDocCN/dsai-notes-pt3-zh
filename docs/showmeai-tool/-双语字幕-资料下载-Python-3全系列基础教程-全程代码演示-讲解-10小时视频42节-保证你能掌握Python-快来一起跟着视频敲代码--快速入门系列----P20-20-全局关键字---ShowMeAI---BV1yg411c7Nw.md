# 【双语字幕+资料下载】Python 3全系列基础教程，全程代码演示&讲解！10小时视频42节，保证你能掌握Python！快来一起跟着视频敲代码~＜快速入门系列＞ - P20：20）全局关键字 - ShowMeAI - BV1yg411c7Nw

![](img/d5b9b4b1de0f36c8a154c3be6260d944_0.png)

Welcome back everyone， my name is Brian， we're going to continue our journey to Python 3 with the global keyword。 This is extremely cool， it's extremely easy and it solves a complex problem。😊，For example。 we've seen this code before。 X is1。 We have a function x is 6。 If we run this。 what's going to happen。Let's find out。 So we have6 and one。 Basically， X is two different variables。

 and they're being treated different because it's two different scopes。 Remember。 whenever you're defining a function， you're actually defining a scope。 So what the global keyword allows us to do is actually modify variables at。 Well， you guessed it。 the global scope。 Let's dive in and take a look。

![](img/d5b9b4b1de0f36c8a154c3be6260d944_2.png)

![](img/d5b9b4b1de0f36c8a154c3be6260d944_3.png)

Okay， in case you skipped that video on scope， what we're really diving into here is。Well。 blocks of code。 we're defining a function， which has its own scope。 The problem is Python is lexically or statically scoped， which means if we run this。 we have two different variables。 However， this is frustrating。 If you comment at this out。

 It's going to access the global scope。 So what we want to do is to be able to access and modify。 and that's what the global keyword does。 So first things first。 now that we understand that basic premise， let's go ahead and test this code。 Sure enough，1，1。 we can access at a higher scope。 Let's figure out how to modify。

 let's go ahead and make a global variable。Good that's it。 It's really that easy Just because we put it on this very first line。 There's no padding。 This is just right at the edge of the file here。 That is now considered in the global scope。Let's take a look at the scope issues in depth here，Let's say scope issues。

And let's make a function called count。Which is going to have some type of maximum number that we're going to count to。Now， without the global keyword， Python is going to get very， very confused very， very fast。let's go and demonstrate that。 So I'm going to say。Counter。Equals， actually。 little'll do plus equals。 We're just going to increment this right off the bat here。

And sometimes Python will' let you do it。 Sometimes it's not。 Other times it's going to just completely freak out and not have a clue what you're doing。 But before we even run this， you can see right now， it's saying。Undefined variable counter。 And this is perplexing because it's literally right here。So remember our conversation。

 we're accessing it。 But now it's suddenly saying， well， who， it's not defined。That is frustrating。 Let's go ahead and try and run that， let'd say。Out。And let's just try to count one just to see what happens here。O oh， unbound local variable。 local error。 sorry， Local variable counter reference before assignment。

Referenced before assignment really is our clue as to what's going on here。What it's saying is。It is now making a new variable。And then trying to increment it before we've actually assigned it。 So remember， Python types are a little bit。 Well， a mystery。 We don't know if that's a string。 a bull actually as soon as it's created， it's an undefined。 So if you take undefined。

 and you try to add one to it， what is the expected behavior。Remember， undefined is not0。 It's just simply there's nothing， literally nothing。 It has no idea what type it is。So Python' is going to get super confused， super， super fast。And let's just continue on with typing away here just to see how bad this can get we're going to say。

Counter。Is greater than or equal to the max， Then let's just go ahead and return false。Otherwise。 we're just going to return true。See， same problem。 So right here， it thinks it's just fine。 it actually knows it's an integer， but right here， it's saying it's undefined。 This is what I mean by Python gets very confused very， very quickly。Oh， that is frustrating。

 So we're going to fix this problem by saying。Logo。Mouner。And notice it's got the exact same name。So really what we're doing is we're saying use the global variable called counter and give it this same name here。Save that。 And as soon as you save it， you notice in telecentense is smart enough to know that， hey。 this is actually defined now and we can start working with it， and it knows it's an integer。

Let's go ahead and just see the global keyword in action here。 I'm going to make a variable called limit。 It's going to be 5。And I want to increment our counter using that。 So Im say 4 x in range。And we're going to use our limit。Go ahead and get a variable from that function。Using that limit。

Let's go ahead and print it out。Or print out our counter。And just for giggles。 let's go ahead and print out。Just done。 So we can see it actually worked。Go ahead run， Sure enough。 Oh，'m done。 So it's working as expected now， and it's all because of this simple little keyword right here。Now， standard practice， I tend to avoid modifying global variables inside of a function for this very reason。

 for example， let's just say。I want to grab this。And make an entire new function out of it。 And I go。 home， I don't need that global。 I just want a variable called counter。 And I don't need that。 Now。 suddenly， you guessed it， we are right back to the exact same issue。 So now it gets very confusing about which counter we're talking about and in which function。

You can very easily fix it by just doing this， but then of course。 now you're going back to modifying a global variable。 which is not really a good programming practice。When in doubt。 we're going to have a conversation about encapsulation later。 but you want to encapsulate or use pretty much everything internal to your scope without going up modifying other scopes。![](img/d5b9b4b1de0f36c8a154c3be6260d944_5.png)