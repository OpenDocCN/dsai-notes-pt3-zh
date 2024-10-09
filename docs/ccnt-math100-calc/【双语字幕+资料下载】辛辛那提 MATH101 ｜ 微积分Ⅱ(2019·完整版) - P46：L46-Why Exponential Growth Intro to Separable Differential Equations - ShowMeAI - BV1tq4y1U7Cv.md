# 【双语字幕+资料下载】辛辛那提 MATH101 ｜ 微积分Ⅱ(2019·完整版) - P46：L46-Why Exponential Growth Intro to Separable Differential Equations - ShowMeAI - BV1tq4y1U7Cv

What is a differential equation， Where do they come from。

 How do you solve them In this introduction to differential equations。

 I'm going to focus on one of the simpler classes of these so called differential equations called separable equations。

 I actually want to begin with the solution to one of them first， namely exponential growth。

Exponential growth is something that we see all around us in nature。 One example of this is well。

 a pandemic。 This is the graph of coronavirus cases outside of China leading up to March 10。

 and this is a period before countries were trying different social distancing techniques And as you can see。

 the number of cases is well modeled by an exponential curve。

 But why exactly is it exponential growth and not just some other type of growth that gets larger as time goes on。

 like for example， quadratic growth or cubic growth。😊。

And why would the spread of coronavirus be similar， for example。

 to the growth of money in your bank account Here， I imagine I have 100 bucks to invest 5% impressed for 20 years。

 Well， the growth of the amount of money in your bank account if it's compounding continuously is also given by an exponential curve。

 So what I want to do in this video is try to describe the socalled differential equations that are going to govern this kind of exponential growth。

 This， by the way， is the first video in a whole playlist on differential equations。

 I'll encourage you to check out the link in the description。

 Give the video a like for that YouTube algorithm。 We're all mathematicians here。 We like algorithms。

 YouTube like algorithms， it helps the video a lot。 and let's get into the video。

 So what is a differential equation。 Well， it's an equation。

 But what you're allowed to have in the equation is rates of change of the variable or derivatives of the variable。

 the derivative of why is equal to in this case， three times y。

eququation might relate an independent variable and a dependent variable。

 but it wouldn't have derivatives in them。 A more complicated example could look something like this。

 It might have second derivatives， first derivatives。

 the dependent variable Y and the independent variable T all mixed together。

 So I'm going to specifically focus on the top one。

 The derivative of y is some multiple K previously written 3。

 but could be any number multiplied by y。Now， why would this differential equation be useful？

What's happening on the left side is that I have a rate of change of why that's what a derivative represents。

😡，Whereas on the right hand side， I'm claiming that this is proportional。

 some proportionality constant K just to the variable y itself。😡。

Imagine the case of my 00 dollars being invested。 The amount of money that I make per unit of time。

 the rate of change at which I make money， the growth rate。 Well。

 it depends on how much money I have。 If I had  a million dollars。

 I'd make more money per year at the same interest rate than I would。 if I had $100 dollars。

 So the idea is that the rate of change is therefore proportional to the amount that you actually have。

 If you start with more， you get a higher rate of change or consider the case of the growth rate of a virus。

If one person is infected， they may go and infect， for example。

 three other people in some unit of time， so the growth rate of the infection。

 the number of new cases you're going to get per unit of time is just a multiple of the number of infected cases you have already。

So the point of this differential equation is that it captures the idea of growth rates being proportional to the amount you have。

 And that relationship is something that we see very often。

 So now I want to manipulate this equation。 The first thing I'm going to do I'm gonna divide out by this value of Y I'm doing this so that on the left hand side。

 I have the derivative of y and something that depends on y And on the right hand side。

 there is nothing that depends on y Then I'm going to go along。

 and I'm going to take the integral with respect to T of both sides。

 So the integral of one over y y prime Dt is equal to the integral of Kdt。

 I'm always allowed to do the same thing to both sides of an equation， and therefore。

 I'm going to integrate both sides of this equation。 Now for the left term。

 let me make a substitution I'm going to define the differential Dy to simply be the derivative d Y Dt multiplied by the differential Dt that is I will write this is one over y d。

 This differential dy is just defined to be。you would get from chain rule， the Y prime Dt。

The reason I've done this is that the left integral can now just be thought of some function of y。

 integrated with respect to Y， whereas on the right， I have some function。

 just the function K integrated with respect to T。If I then evaluate those two integrals。

 one over y integrates to the logarithm of y， and the value of K integrates to K T。

 because these are indefinite intervals。 I'm going to add a plus C on the right hand side。

 I could have had two different plus C's， perhaps a C1 and a C2 for each of the intervals。

 but I'll just combine them into this single plus C on the right hand side。

My goal now is to solve for y。 and I can do this by taking the exponential of both sides。 Again。

 I can do the same thing to both sides of an equation。

 So let me raise both sides of the equation E to the power。

 So E to the logarithm of y and E to the Kt plus E。😡，On the left。

 this is just going to cancel out and be the absolute value of y。 And on the right， Well。

 E to the K T plus C。 And then finally， I'm going to do a little bit of trickery here with that plus C。

 The first thing I note is that E to the K T plus E。

 I could separate it and write as an E to the C out the front and then multiply by the E to the K T。

😊，But E to the C is just well some other constant and so I'm going to replace E to the C with the constant A and if I allow a to be negative or positive。

 that reflects the fact that I had an absolute value， which could be plus or minus as well。😡。

And we even allow the constant a to be equal to 0 because if you went to the original differential equation and took the derivative of 0 as equal to k times 0。

 that would have satisfied it as well。 So in the end。

 I have this Y is a constant A times the E to the Kt。

 So I call this a solution to the differential equation。

 Y equal to A E to the Kt is a solution to it。 Indeed， if you just take this y and plug it in。

 It works。 When you take the derivative， you would get K A E to the Kt is equal to K times A E to the K T。

 It's the same thing on both sides。 So it works out。This is called， by the way。

 an ordinary differential equation or an ODE in multivariable calculus。

 you could have functions that have multiple independent variables and you could take partial derivatives of those and therefore you would get a partial differential equation。

 so there's another category that you can investigate in your future。

The next thing I want to do is imagine that I impose some condition。

 Imagine I impose that at time t equal to 0， the value of y is 100。

 This is called an initial condition。 It says I'm going to specify one point。 that at t equal to 0。

 This is equal to 100。 Then what I get out of this。 If I just plug it in is that， well。

100 is what happens when you plug in t equal to 0， A E to the K times 0。 and E to the0 was just 1。

 So this is just give me the value of a。In other words。

 my initial condition that y of 0 is 100 tells me what the a is。

 so now I have a more specific solution Y is 100 E to the Kt putting these two different things together gives something called an IVP or an initial value problem and initial value problem is when I have a differential equation together with an initial condition that y of 0 is some specified value why not and what we've managed to drive is that the solution to that differential equation is that y is this constant y not E to the Kt。

😡，So solving this equation is where the exponential growth formulas come from。

 you begin with a very reasonable relationship that the rate of change is proportional to the quantity。

 which seems reasonable whether it's the growth of a virus or the growth in your bank account。😡。

And then solving that differential equation led to this particular solution， the exponential growth。

 We can do the same basic idea for more general separable equations。 Consider， for example。

 the following。I want to have a rate of change DYDT。Is equal to a specific form。

 This is a class of ordinary differential equations。

 It's the specific form where it can be written as a function of T on the top and a function of Y on the bottom。

 exactly like that。😊，Well， if it is of this specialized form。

 then I can just basically do what we did before， so the first thing I can do is I can move the G of Y over。

That means that on the left， I only have Y and Y prime appearing and on the right I only have T appearing。

😡，Then I could integrate both sides of this with respect to T。

 and this is going to be the integral of G of Y， Dy d T dt is equal to the integral of F of TDt。

Making the same definition that DY is going to be the DY DTE。

 I get now an integral in terms of y on the left an integral in terms of T on the right。

If I then define that capital G of y is an antider to lowercase G of y。

 I define that capital F of T is an anti derivative to lowercase F of T。

 then I get the equation capital G of y is capital F of T plus that arbitrary constant C。

This equation that I have down here is my solution to the original differential equation。

 the original separable differential equation， Sometimes the G of y is relatively nice as it was in our first example。

 and I can solve it explicitly to say that y is this specific function of T and sometimes the G of y is quite messy and I'm not able to do that。

😡，Nevertheless， we have a nice procedure to be able to solve these separable differential equations。

I hope you enjoyed this introduction to differential equations。

 if you want more differential equations， check out the rest of the playlist and Li as in the description。

 give this video a like if you haven't already and we'll do some more math in the next video。

