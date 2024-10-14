# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P27：L5.1- 正则化简介：Ridge 和 Lasso - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton， welcome to App of Deep neural Networks with Washington University。

In this module we're going to start looking at regularization。

 which is another tool to combat overfitting in neural networks and other model types as well。

In fact， many of the regularization techniques， particularly L1 and L2。

 came from much older models than neural networks， specifically linear regression we're going to start here and we're going to see the origins of L1 and L2 which will help us to understand it for neural networks for the latest on my AI course and projects。

 click subscribe and the bell next to it to be notified of every new video so let's look at how L1 and L2 regularization were actually introduced。



![](img/66334a38d34a532260ca2145f0ccb84a_1.png)

They come from Rige and Lasso regression， which are just forms a linear regression。

 We're going to use the auto miles per gallon data set to demonstrate these with just straight up linear regression then we'll see how in a later video how we can introduce L1 and L2 into Kara's neural networks so I've loaded the data and I'm also creating a function here that reports the coefficients。

Coefics in linear regression those tell you the relative importance of each of the various inputs and then the intercept which shows sort of what happens at zero so let's look at just straight up linear regression before we do that we're going to use a psyic learn linear regression model and we're going to fit the auto miles per gallon to this。

So you can see certain things like the cylinders is very negatively correlated to the efficiency of the car for miles per gallon。

The origin is very positively。This is 1970s data， so basically the origin there is meaning that the was the card not made in the United States。

 if it was made in the United States， it was pretty inefficient。

Year also is important because as the year increases the car got more efficient and you can actually see the values so you could truly calculate a cars miles per gallon。

 you just take all of these values multiply each by the coefficients and then you add in the intercept and it'll give you a rough estimate of what the miles per gallon is by the way。

 I will point out to that origin， I probably should have been turning that into dummy variables。

 but here we're just treating it as a basic numeric。I've never found that to to give me much。

 much lift on this particular one。 Let's look at L1 Lasso。 L1 Lasso makes use of。

We're basically adding the weights together， so we're summing the weights。

And we are using the weights as a penalty， so if the weights get too high。

 the absolute value of the weights gets too high that counts along with the error。

 so the difference between the expected outputs and the real outputs and those two together。

 you're giving the neural network multiple objectives。As it's trained， you're saying， okay。

 on one hand， be as accurate as possible， but on the other hand， don't let those weights get too big。

 And this deals somewhat with Oham's razor in that the more simple solution is usually the better one。

Now， the absolute value is a fairly sharp cut off。 so that will tend to completely eliminate some inputs。

 This is good for feature selection。 L1， if you have a lot of input features and you are thinking that some of those are not necessary。

 L1 can be a good regularization technique business simply cutle out。 And let's the neural network。

Later， neural network for now， linear regression focus on the more important ones。

 We'll go ahead and run this one。 You can see that it cut off a lot of these down here。

 It pushed them to near 0， and we're focusing just on year。And origin。

 you can also see the final score is is not that bad， considering that we are not using the full。

The full data set， the full columns of the data set， these are getting pretty much eliminated。

 by the way， you'll also notice that we specified a alpha that is the degree to which the weights。

Are counted as， as a bad indicator for。For the multi objective。 So you're giving it two objectives。

 whenever my boss comes to me and says， okay， this is a high priority and this is a high priority。

 Okay， you've got a weighted which， which of those two high priorities is the highest high priority。

 And this is what's going on there。 the this is very much telling the neural network that okay。Yes。

 the regression， the regularization is important， but it's only1/10th as important as getting an accurate result。

But nonetheless， this gets it to chopping off some of those， so it's pretty effective。

 it is doing what alassso you're expecting it to do， it is removing unneeded columns。

Now what's the effect of changing that？That alpha。You can see as you make alpha bigger and bigger。

 the error gets considerably， considerably worse。 So that's basically what that is， is demonstrated。

 So you don't want to make the alpha usually too big。

 but it is it's yet another hyperparameter to tune。 So later。

 when we get to the kle competition module， we're going to see how several ways that we can optimize all these hyperparameters。

 because this is getting to be a lot of things to manage on a neural network。

 you have regularization， How do you pick how many neurons， how many layers。

 all that kind of L2 Rige regression。 instead of taking an absolute value， you're squaring it。

 And that makes it more， more round it。 So that causes。

It to be less harsh on trying to eliminate individual columns altogether and rather just seeks to keep the weights down or the coefficients down。

 This is L2 regression。 We'll go ahead and run it。 We're using ridge from second learn here I'm setting the alpha fairly aggressively。

 and you can see the results here。 It is definitely pushing some of the middle ones。

 but not as intensely as the as the other ones。 And by the way， choosing the alpha of one。 largely。

 I just play around with these to see which。Which results gave me the better one？In module。

 in a later module， we're going to see how we can use Bayesian optimization to help help pick some of these。

 There's also elastic net。 El net combines both of them。 So now you have an alpha。And the L1 ratio。

 So this is allowing you to。You， you specify the。Alpha are the L2 and then the L1 ratio。

Balances that together， so you have two hyperparameters now to deal with for this one。If I run this。

 you'd see it's it's somewhat similar to the to the L2。

 and that has to do with some of how I set the。The two ratios。

 but this is yet another way that you can do this we'll talk more about when you'd use L1 and L2 together later in this module once we get them up to neural networks。

For now we've just seen how to do these on linear regression just to show you some of the fundamentals because we won't be able to look at the weights of the neural networks。

 there's too many of them and watch these same sort of things happen and the next video we're going to look at kfold cross validation which we will use to better understand if our regular is neural a sample predictions content changes often up to date and intelligence。



![](img/66334a38d34a532260ca2145f0ccb84a_3.png)