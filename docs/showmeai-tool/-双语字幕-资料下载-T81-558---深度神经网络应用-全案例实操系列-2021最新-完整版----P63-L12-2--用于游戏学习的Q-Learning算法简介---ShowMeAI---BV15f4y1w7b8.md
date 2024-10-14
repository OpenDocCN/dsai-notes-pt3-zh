# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P63：L12.2- 用于游戏学习的Q-Learning算法简介 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Hayton。 welcome to applications of deep neural networks with Washington University。 In this video， we're going to build on using G。 We saw open AI gym in the previous video。 Now we're going to apply Q learning to that。 And we're going to see how we can build up using machine learning a basic lookup table that shows us what action to take for any state that the environment might work on。 Then we're going to continue this and show how deep neural network can become a very complex representation of a table so that we don't have to store literally every combination in there。

 And that begins the deep Q neural network to see all my videos about Cale neural networks and other AI topics。 Click the subscribe button and the bell next to it and select all to be notified of every new video。 So let's have a look at Q learning。 I'm going to run this in Google coabab。 This really does not require GPU。 The code here actually is not even designed to take advantage of a GP。

😊。![](img/30d4f6c3c88418548a35fcff3628ad27_1.png)

I'm going to give you just a Python implementation of doing a tablebased Q learning lookup。 which is really kind of how Q learning works In the next part。 we will extend this and we'll actually use Kra's TF agents to actually implement this in deep learning and then go of completely beyond this and use something that has a much more complex environment like an Atari game So here I have the setup for Google Coab we definitely want to use Tensorflow 2。

0 and I have some additional code here that if you're running coabab will execute because coab at least as it was as of the recording of this video does not include TF agents and some other things that I want so that I'm able to display videos literally write in the browser here TF agents provides a very good way to take a snapshot of just a single image from an environment running as it's rendering and show it to you there's other ways。

Get around it， but TF agents makes that real easy other than that we're not using TF agents for this video。 We'll use TF agents in the next one。 I will go ahead and run this part。 it will say note using Google coab once this actually runs that I run this part to install all of the libraries that I would like to have this can take a bit so we'll fast forward through it Now Q learning there's a couple of terms that I'll refer to as we're going through this So it's good to go ahead and go through those now agent think of this in terms of a video game although in the very last part of this chapter we will do something that's not a video game but the agent that's your player that your computer player that is going through the environment playing the video game now the environment is the universe that the agent exists in the environment has state and the state of the environment changes as the agent interacts with it and the agent interacts with the environment by。



![](img/30d4f6c3c88418548a35fcff3628ad27_3.png)

![](img/30d4f6c3c88418548a35fcff3628ad27_4.png)

First of all， just seeing the state of the environment in this part this video。 the environment state is just going to be a vector of some numbers that tell us the position of a cart or how fast it's going things like that but when we get to Atari the environment is actually a grid that's the video screen as the game is being played a step is one cycle through the environment so you take an action that's like move up。

 move down， move left， move right and then see what that does to the environment and one complete cycle of performing some action and seeing the results that's a step all of the steps until you accomplish your goal or get killed or the simulation ends that's called an episode so that's like one play of the video game an Epoch is a training construct it can be some number of episodes depending on how you configure figure things and then the terminal state is the step that you get to that causes the game to end。

you win， you run out of lives， something like that。 So Q learning basically builds up table so that every state in this environment。 it gives us a indication of which action is going to be the most rewarding because as you're going through this you get a reward at the end of each step and that tells you how how effective that step was some gains are mean they don't give you any reward until the very。

 very end and only if you want it。 those can be a little harder to optimize for。 but Q learning still does that。 that would be almost like going through your foury degree and at the very end。 either you get a diploma or you don't And if you don't who knows why you did something wrong。 But that's the torture that we put computers through。

 So we're going to work with something called the mountain car。 This is a classic reinforcement learning hello world kind of thing it is essentially a mountain car Now if you run this code here。 I'm not going to。On it because it's already rendered。 But this will show you one frame of whatever environment you're specifying。

 I'm specifying the mountain car。 If I put in space invaders， it would draw the space invaders。 all the little aliens coming down to be blasted。 So this is how mountain car works。 The idea of this game is your mountain car essentially， you can provide forward thrust。 So you really only have three actions you can take One action is no action。

 And then the other two actions are either thrust this way up the hill or thrust this way up this side of the hill。 The trick is your little car is just not strong enough to make it up the hill。 try to just blast up the hill。 I'll show you that in a moment。 You're not that successful。 So what you've got to do is blast up the hill。 get as far as you can go and then you'll roll back but you'll roll back and build up some potential energy up the hill on this side。

 and then you charge， charge straight through and go。😊，Up again。 maybe usually you'll make it in two shots。 but the idea is to get all the way up here using potential energy from that other hill and conserving your momentum there。 so you can apply a left force， you can apply no force or you can apply a right force So those are the numbers that specify those discrete actions the way the Q table works you can only apply a discrete action So these are the three things there's no like apply maximum force left apply half force like your car like your accelerator when you press that down flooring the car gives you a completely different result than tapping it this is possible with Q learning but you need to use some special tricks and other things。

 we'll get into that when we get into deep Q learning using the deep neural network but typically it's assumed that these are discrete actions but continuous actions are fine you just have to use different algorithms for those and in our very last part of this module will。

Look at an application of deep neural networks， deep queue networks that is not a game。 and it does take continuous actions。 Now， the mountain car environment。 essentially all you have is the position of this car。 I believe zero is right here and then negative and positive and then the velocity。

 How fast is it going and that's positive or negative too and those are continuous values。 So the velocity that you're going this way or the velocity that you're going that way。 negative versus positive。 Now this is using some code that allows you to actually visualize it and see it go up I don't have the code the video from last time。 So let me go ahead and run this。 So I'm going to run this and what this does is it gives you a couple of functions to show the video and actually see the video in a web browser which is handy because a lot of these you'll require a GPU and you may want to actually run those in Google coab to get advantage of the free GPU but you can also display it in a browser if you're running it locally or a little screen。

😊，'ll typically pop up and show it to you。 So now let me go ahead and run it。 So what this does。 This is a mountain car that very stubbornly just tries to apply maximum acceleration to the right。 So it just it just floors it well there is no maximum it just pushes with full power to the right。 tries to scale the mountain and ultimately is not strong enough。 Now this output you see here。

 you can see the state。 So the state is showing essentially where the car so it's velocity how fast it's going。 it kind of reaches full velocity and varies a little bit。 this is a little bit random。 And then this is the position。 you can see it's basically going further and further and further up the hill and at some point yeah right around there。 it starts to slide back down。 pictureture is worth a thousand words。 So if you look at this。

 this is what it does it tries it tries who's the Greek guy that pushes the boulder up the hill sisyphus if I remember my history classes is right。That's basically an impossible task。 Now， what I do is I use old school programming。 I program a car to solve this。 And for a simple case like this。 yeah。 I can I can write a completely deterministic program， just give it some rules。

 and the rule essentially that I'm going to look at。 I'm going to look at the state。 and I'm going to only pay attention to the state。 I am not going to pay attention to the velocity。 I don't care。 I want to know just the position of the state。 and this position if the position is greater than0 zero。 So this way。

 then I'm going to push this way。 if the car is going this way。 I am going to push this way and try to get， try to get it as far up this side as possible to build up as much potential energy as it possibly can。 and the program to do this is really pretty simple。 If the position So the first element of the state is greater than zero， I apply to。

 which is push it to the right。 Otherwise， I apply zero， which is push it to the left。 One is no power at all。 I don't believe any bra is apply but。We really don't need to break in order to achieve our goal or ever let up on the engine。 So here we run it。 We see the same steps。 Notice there is no reward。

 This is like trying to get through your four years of college and the only feedback you get as you graduate or you don't。 but we get all the away to the end。 eventually， oh， and I don't display the last steps。 So you don't even see your reward that you that you ultimately get when this thing wins。 But let's take a look at how my programmed car works。

 You can see it's a bit more successful and it wins。 All right， that is a hardcod rule。 Imagine if the Tesla engineer is set there and try to think of every possible case that would ever come up when you're driving an actual car。 it would be quite miserable。 and it just wouldn't work。 You would never think of everything。 I mean。 this is almost a1 B world like flatwor because I can't go really up or down。

 I'm only going left and right。 So reinforcement learning。 how this works。 is we have our agent and we have the environment。Agent takes some action on the environment。 And there's two outputs from that。 There is the state for the next frame。 and then there's the reward that you receive from that action for the mountain car。

 you only receive a reward when you actually succeed and make it all the way up the hill。 Now。 I'll mention this briefly because this is sometimes done in reinforcement learning is if the environment doesn't necessarily give you a reward。 you can sometimes get greater effects by engineering your own reward。 And that might be doing something like saying， okay。

 I'm going to give it a reward for maybe getting up the hill further than it's ever gotten before or something。 So use your your mind， your heuristics as a human to actually come up with some intermediate reward just maybe to give it better。 better results。 Now this line here means that training occurs and it adjusts it。 And then the next state goes into the agent。 and it continues。

 It continues and continues and continues。Now， this equation is how Q learning is typically represented。 It looks kind of big and crazy if you've not seen a lot of these kind of equations before。 but it's not that bad。 And I want to take you through the parts of it because this is actually quite important。 So the way Q learning works is it's keeping that table。

 So a table for every possible state that the environment can be in。 Now in this case。 this is a grid of all the possible positions and all the possible velocities because those are your two states that you have and state T。 that just means all of those states。 So S is essentially a array holding those two values in the case of this problem。 and for each action that you might take。 So each of those different states in that grid。

 there's three actions you can take。 So this is really a cube every value on the grid is essentially the three actions and anticipated reward that you would get for for being there。 So what this is doing what this is saying is the。Value is going to be changed。

 It is essentially going to be added to。 So this this old value， this is almost like in programming。 a equals a plus plus something else plus sub delta a equals a plus1。 if this whole thing was one。 So this whole part over here is the delta We're calculating how much we want to change that Q value of I。 This is very typical of machine learning。 This is how I don't even know how many algorithms I studied have exactly this format。

Like the weight in a neural network， the weight equals the weight plus essentially the gradient times a learning rate。 The learning rate is there to scale it back。 Learn to walk before you learn to run。 If you didn't have this learning rate here， then this whole big value would just be flipping those Q values all over the place。 It would be too aggressive of a change。 And it would be like the learning algorithm got super excited about every little new thing that it learned that it completely overrode most of what it had learned previously。

 So your alpha is your learning rate。 I use a learning rate in this example of01。 So one10th of whatever we're going to calculate for this delta is what we're going to apply。 And they call it a temporal difference。 I took this right from Wikipedia。 The equation。 Now you get back a reward。 So let's look at how that reward is everything hinges on the reward actually happens。

 I like to look at these equations。😊，in blocks and then rip the block apart。 So inside of this delta that is being multiplied by the learning rate， there's really two parts。 Notice this old value。 That's the same old value that you add here。 You could do some algebraic simplification and do some canceling and not have that。

 but that's just the way this is written。 basically we want this whole thing to be a delta to be added to this。 so we have to subtract off the old value so that basically this is our new value。 This is the old value so the difference between these two。 We desire to get to hear this new value。 So we have to subtract the old value from it so that we need to see the magnitude change。

 and then we scale it by the learning rate and at it。 So let's look at the new value because that's the interesting part。 that is just setting up the delta。 We need to know how much we want to change it by。 So this is the theoretical new value that we would like to eventually take it to。 So the reward。

 Re is important。The reward is what we were given for applying this state and action that we currently did。 So we're updating the Q value for whatever action we took on the current state。 So the reward is I mean fundamentally the reward would be the estimate of the future value that we're going to get So those values in the table。 they tell you the reward for each of those actions at a particular state。

 usually you just take the highest of those actions。 but we want to evaluate the other two actions that we're not taking now we want to get to the eventual reward that we're going to get So what we do is after we've applied so we've done our action we've gotten a reward or not then we take this discount factor this is set to 0。

95 so we're taking 95% of whatever the maximum Q value was for this next state that we're moving into based on that action So whatever that action。ultted in this new state。 We look at the Q values for this new state and we take the maximum of those action Q values。

 So that is the maximum that is an estimate， as it says of the optimal future reward for the next the next step in all of this。 You don't want to necessarily apply this directly to it because then its mind is too much to the future。 and is the here and now is quite important The reward that we just got it's a balance between these two。 but a very common setting for this one。 and the one I'm using is 95%。

 So we're taking both of these into consideration considerably。 So that's it。 That is how this equation works。 and I wanted to take you through each step of it because this is a very common format equation for machine learning and I give you a description of what these values are。

 we just went through all of those。 So let's look at the Q learning car。 the Q learning car is going to basically learn to perform similar to the preprogrammed car that。I gaveve you。 the trick is it's learned by a machine that has no concept of gravity or hills or anything like that。 It just plays with the car until it finally gets its reward and distributes that across the actions and eventually gets a pretty good program。

 So this is the Q learning car。 This is calculating to the discrete state。 this is just putting the position into one of those 10 buckets。 This is running the game。 So while we're not done， we are going to basically this is a very important part to understand here。 This is how epsilon is used。 Epsilon is a value。 One means make the car move completely erratically random0 means make the car move completely according to the Q table。

5 means do it kind of half in half。 This epsilon value starts out very random at first。 and then we decay it as we go so that it goes closer and closer to zero。 and then eventually for the last part， it is performing completely from the Q table。And learning completely on the Q table。 The randomness forces it to explore and try out radical new ideas。

 And then once you've locked in on a pretty good overall technique。 then the machine learning can take over and refine that simulated andneing is a very similar process to this and other Monte Carlo techniques as well。 We get our reward by calling the environment。 Con the state into a discrete value。 We check to see if we've reached the goal position if we have we're done。

 and then we update the Q value。 This is that big hair equation from before written in Python。 and then we switch the state to to the new state that we have moved to。 So this is basically running the game。 This runs one step of the game。 and these are all these hyperparameters。 Learn rate is the learning rate for the algorithm。

 how quickly we update those Q values Disc I told you before that's the 95% How many episodes we want to run how often do we want an update I set that to every thousand discrete grid size。Using just 10 so that whole left or right between the two mountains is effectively broken into into 10 values just to keep it a discrete input into Q learning。

 which is how key learning typically works We can get Q learning to work on continuous values but that that gets into other algorithms that we'll see later in this chapter This is the decay for the epsilon like I told you about。So we load up the mountain car environment。 We set up the epsilon change so that it can decay eventually to0 over the episodes that we wanted to。

 We're gonna loop until we're done with the episodes。 When we hit the show every so show every 1000 in the case that I gave you。 it will show you what's going on and run a game。 you'll only see the game if you're running this locally。 we count the successes and we run it。 So you can see from the first thousand episodes。

 there were no successes at all。 We don't get any successes until 4000。 And through a lot of this since there's no feedback。 The only really capability it has here is trying random approaches。 And finally。 it gets some success。 And that is why the epsilon is decaying because we want that randomness to start to go away。

 And once it starts to get some learning to refine what it's learned。 You can see here of the thousand episodes， it finally is completely successful。 However。 there's a lot of random。to the environment。 So it's， it's not learned completely yet。 I like to let it go until it gets to fairly consistent success like here。

 you could modify this so that the code actually looks at this and stops based on the the thousands getting consistent。 However， the problem you have then is。You increase the total number of episodes and then your decay of the epsilon doesn't work as well。

 because you don't know how deep you're going at the very beginning。 Now to run it。 we can see it run here。 and it rocks， and it's not quite as good as the preprogram card。 but it does it。 Now let's look inside a deep let's look inside a Q learning's brain and see what's going on here I can dump the table。 So the velocity is discreetized as is the position。 We have to discreteet these two。 Otherwise。

 how would we have a table， we would have infinite values here。 Now。 when we get into deep Q learning， we can deal quite easily out of the box with continuous values for both of these two。 However， deep Q learning does require some further algorithms added to it if we want to continuous actions so that basically we can apply the accelerator maybe halfway or three quarterss away or something like that。 Now just looking at the grid， this doesn't tell me a lot。 first of all。

I don't feel that velocity is even all that useful of an input for this problem When I did my preprogrammed car I used only position。 So what I did was I took the mean of these so that I can see kind of row and column at a time because like I said for this problem I'm not seeing really the value of the velocity and you can see when I take the means look these line up you can see that it's learned almost a gradient and it learns particular this is the one that I'm more interested in。

 it's learning to apply more of it and less well one direction versus the other direction up here versus down here。 Now up here these last two those are a bit anomalies but that could also because it's already hit the goal stated it's already crashing to the top of the mountain it may not really matter what it's doing at that point and that's Q learning Q learning is tablebased will'll look more at this with deep learning where we can get deal better with continuous values first in。



![](img/30d4f6c3c88418548a35fcff3628ad27_6.png)

St and then also in the actions。 Thank you for watching this video。 In the next video。 we're going to look at how to extend this table into deep Q learning that way we don't have to represent literally every combination we can let the neural network learn to generalize。

