# P183：L81.1- 双Q学习 - ShowMeAI - BV1Dg411F71G

Let's get us started actually let's continue with deep reinforcement learning with double Q learning and I'm going to tell you why you need to do double Q learning and why it helps and what it is actually but let's start with a little background we know about Bman equation。

 Bman optimality equation and we have been using it you can write it either for the value function or the optimal value function or you can write it for state value function。

 your Q function， what do we have here you have an expectation with respect to the future as prime and then you have a transition probability that is taking you from one state and action a pair of state and action to the next state so this is your environment and then you get a return for taking that pair of state and action and going to the next state and then the future。



![](img/3004ee33629c253d4a5a4af78be2950e_1.png)

![](img/3004ee33629c253d4a5a4af78be2950e_2.png)

![](img/3004ee33629c253d4a5a4af78be2950e_3.png)

![](img/3004ee33629c253d4a5a4af78be2950e_4.png)

![](img/3004ee33629c253d4a5a4af78be2950e_5.png)

![](img/3004ee33629c253d4a5a4af78be2950e_6.png)

![](img/3004ee33629c253d4a5a4af78be2950e_7.png)

![](img/3004ee33629c253d4a5a4af78be2950e_8.png)

![](img/3004ee33629c253d4a5a4af78be2950e_9.png)

![](img/3004ee33629c253d4a5a4af78be2950e_10.png)

![](img/3004ee33629c253d4a5a4af78be2950e_11.png)

![](img/3004ee33629c253d4a5a4af78be2950e_12.png)

You're summarizing it by via star and then you choose your maximum action to give you the optimal value and then you can use this to do value iteration algorithm and these are for this is a historic algorithm you use it in economics macroecons microeconomics you use it for control you used it for the classical type of reinforcement learning and this is for tabular data so these are the type of data where you can put your value in a matrix or in a vector so finite state and finite action then there is Q value iteration algorithm you have a similar equation beman optimality equation for your Q and then you can do Q value iteration this is also classical you have your transition probability reward and then you are choosing the maximum action based on your Q and this is actuallyre going to give you a greedy policy but then also classically you could use。



![](img/3004ee33629c253d4a5a4af78be2950e_14.png)

![](img/3004ee33629c253d4a5a4af78be2950e_15.png)

![](img/3004ee33629c253d4a5a4af78be2950e_16.png)

![](img/3004ee33629c253d4a5a4af78be2950e_17.png)

![](img/3004ee33629c253d4a5a4af78be2950e_18.png)

![](img/3004ee33629c253d4a5a4af78be2950e_19.png)

![](img/3004ee33629c253d4a5a4af78be2950e_20.png)

![](img/3004ee33629c253d4a5a4af78be2950e_21.png)

![](img/3004ee33629c253d4a5a4af78be2950e_22.png)

![](img/3004ee33629c253d4a5a4af78be2950e_23.png)

![](img/3004ee33629c253d4a5a4af78be2950e_24.png)

![](img/3004ee33629c253d4a5a4af78be2950e_25.png)

orral difference learning so what are you're doing you are creating a moving average between the history of type of values that you saw plus some update so here what I'm doing is trying to simplify that equation up here so it's a sloppy notation so don't read too much into it and I'm removing this maximum and I'm removing this expectation just for the sake of the notation to be simpler but to be precise you need to include that maximum that expectation in the next term in the second term but I'm just removing them for simplicity it's gonna be a weighted average between the history of your values and this update there is the return plus gamma and VkS prime if youre rearrange your terms and factor out alpha you're going get VkS plus alpha of a delta which is a function of your。



![](img/3004ee33629c253d4a5a4af78be2950e_27.png)

![](img/3004ee33629c253d4a5a4af78be2950e_28.png)

![](img/3004ee33629c253d4a5a4af78be2950e_29.png)

![](img/3004ee33629c253d4a5a4af78be2950e_30.png)

![](img/3004ee33629c253d4a5a4af78be2950e_31.png)

![](img/3004ee33629c253d4a5a4af78be2950e_32.png)

![](img/3004ee33629c253d4a5a4af78be2950e_33.png)

![](img/3004ee33629c253d4a5a4af78be2950e_34.png)

![](img/3004ee33629c253d4a5a4af78be2950e_35.png)

![](img/3004ee33629c253d4a5a4af78be2950e_36.png)

![](img/3004ee33629c253d4a5a4af78be2950e_37.png)

![](img/3004ee33629c253d4a5a4af78be2950e_38.png)

If you reward， the next stage。And this algorithm is called temporal difference learning so it's an extension to value iteration and the idea is that you don't want to forget whatever that you learned previously and you want to change your value in a smooth fashion you can do the same thing for Q you can do temporal difference on your Q function and again it's going to be one minus alpha of the previous Q plus whatever that your whatever information that you just saw for updating your Q which is R plus gamma maximum of a prime over cus then you can rearrange your terms and this is going to give you a delta the change a difference and that's why it's called temporal difference Why did I give you that background because it turns out that Q learning is a form of temporal difference learning so I'm going to show you that I'm going to go through a little bit of a math to show you that yes actually this is true Q learning is a form of temporal difference learning there is also another。



![](img/3004ee33629c253d4a5a4af78be2950e_40.png)

![](img/3004ee33629c253d4a5a4af78be2950e_41.png)

![](img/3004ee33629c253d4a5a4af78be2950e_42.png)

![](img/3004ee33629c253d4a5a4af78be2950e_43.png)

![](img/3004ee33629c253d4a5a4af78be2950e_44.png)

![](img/3004ee33629c253d4a5a4af78be2950e_45.png)

![](img/3004ee33629c253d4a5a4af78be2950e_46.png)

![](img/3004ee33629c253d4a5a4af78be2950e_47.png)

![](img/3004ee33629c253d4a5a4af78be2950e_48.png)

![](img/3004ee33629c253d4a5a4af78be2950e_49.png)

![](img/3004ee33629c253d4a5a4af78be2950e_50.png)

![](img/3004ee33629c253d4a5a4af78be2950e_51.png)

That we are going make so for now I want you to believe me that Q learning。

 the algorithm that we started reinforcement learning a couple of sessions back actually overestimates the action values so it overestimates Q so for now believe me but then I'm going to show you why I'm going show you an example let's start with this fact so what is Q if if you' are sitting in state S and you just took action A and for the future you're going to follow a policy pi and basically your conditioning on S A and pi this is going be your expected reward expected expected return and it's expected discounted future return and you're discounting it pi gamma and Q star is when you get rid of pi actually you optimize over pi you find your best pi best policy so when we did Q learning or actually deep Q learning。



![](img/3004ee33629c253d4a5a4af78be2950e_53.png)

![](img/3004ee33629c253d4a5a4af78be2950e_54.png)

![](img/3004ee33629c253d4a5a4af78be2950e_55.png)

![](img/3004ee33629c253d4a5a4af78be2950e_56.png)

![](img/3004ee33629c253d4a5a4af78be2950e_57.png)

![](img/3004ee33629c253d4a5a4af78be2950e_58.png)

![](img/3004ee33629c253d4a5a4af78be2950e_59.png)

![](img/3004ee33629c253d4a5a4af78be2950e_60.png)

![](img/3004ee33629c253d4a5a4af78be2950e_61.png)

![](img/3004ee33629c253d4a5a4af78be2950e_62.png)

![](img/3004ee33629c253d4a5a4af78be2950e_63.png)

![](img/3004ee33629c253d4a5a4af78be2950e_64.png)

What we did was we approximate Q by neuron network and this enabled us to go beyond tabular type of data and this enabled us to go into the continuous state and continuous action so that's where you're going go put your neuron network and then we said we are going to use the beman optimalality equation to write down a loss function which was in terms of mean squared error so it was a target minus your Q squared now we are taking the derivative of that square term this term is going to remain and here you're going to get your gradient so this is nothing but taking the derivative of your square function and then you are doing gradient essence minimizing your minus square error but whatever that you're doing you're doing gradient you are taking steps in the direction of your gradients Okay so far so good but whatever are we doing the next step is doing a Tayloror series expansion we are going to write down Q of Sa and theta。



![](img/3004ee33629c253d4a5a4af78be2950e_66.png)

![](img/3004ee33629c253d4a5a4af78be2950e_67.png)

![](img/3004ee33629c253d4a5a4af78be2950e_68.png)

![](img/3004ee33629c253d4a5a4af78be2950e_69.png)

![](img/3004ee33629c253d4a5a4af78be2950e_70.png)

![](img/3004ee33629c253d4a5a4af78be2950e_71.png)

![](img/3004ee33629c253d4a5a4af78be2950e_72.png)

![](img/3004ee33629c253d4a5a4af78be2950e_73.png)

![](img/3004ee33629c253d4a5a4af78be2950e_74.png)

![](img/3004ee33629c253d4a5a4af78be2950e_75.png)

![](img/3004ee33629c253d4a5a4af78be2950e_76.png)

![](img/3004ee33629c253d4a5a4af78be2950e_77.png)

T plus1 and then write down a Taylor series expansion and this target is nothing but your reward plus gamma maximum of your Q。

 let's do our Tayloror series expansion and you are going to do your Taylor series expansion around theta T So theta T plus1 you know it formula it's up there now you're doing a Taylor series expansion。

 It's as if you're evaluating your function at theta and then this term is going to remain。

 this is going to come out all of this。 This is basically your delta theta that's going to remain。

 and then you're going have the first gradient of your Q function evaluated that theta T So this term this gradient and the new gradient that you just compute it because of the Taylor series expansion that's going to give you a norm So anyways in the end what did we get let's take a look at our temporal difference you had Q from the previous state you have it here。



![](img/3004ee33629c253d4a5a4af78be2950e_79.png)

![](img/3004ee33629c253d4a5a4af78be2950e_80.png)

![](img/3004ee33629c253d4a5a4af78be2950e_81.png)

![](img/3004ee33629c253d4a5a4af78be2950e_82.png)

![](img/3004ee33629c253d4a5a4af78be2950e_83.png)

![](img/3004ee33629c253d4a5a4af78be2950e_84.png)

![](img/3004ee33629c253d4a5a4af78be2950e_85.png)

![](img/3004ee33629c253d4a5a4af78be2950e_86.png)

![](img/3004ee33629c253d4a5a4af78be2950e_87.png)

![](img/3004ee33629c253d4a5a4af78be2950e_88.png)

![](img/3004ee33629c253d4a5a4af78be2950e_89.png)

![](img/3004ee33629c253d4a5a4af78be2950e_90.png)

you have a step our step is now going to be alpha times this gradient gradient squared so it's an adaptive step and then the rest of it the term in the parenthes is exactly a term that you have down here because of the form of your yq it's R plus gamma that maximum term it's R plus gamma this maximum term minus the previous state so Q learning is a form of temporal difference learning so far so good for deep Q network algorithm we had two tricks one of them was that you're going to set aside a target network and then you're going to have an experience replay for the target network every couple of iterations you would store a bunch of parameters and then that's going to give you a target this is a way of you separating your target from the actual Q function because whenever you want to do supervised learning you need to have a target。



![](img/3004ee33629c253d4a5a4af78be2950e_92.png)

![](img/3004ee33629c253d4a5a4af78be2950e_93.png)

![](img/3004ee33629c253d4a5a4af78be2950e_94.png)

![](img/3004ee33629c253d4a5a4af78be2950e_95.png)

![](img/3004ee33629c253d4a5a4af78be2950e_96.png)

![](img/3004ee33629c253d4a5a4af78be2950e_97.png)

![](img/3004ee33629c253d4a5a4af78be2950e_98.png)

![](img/3004ee33629c253d4a5a4af78be2950e_99.png)

![](img/3004ee33629c253d4a5a4af78be2950e_100.png)

![](img/3004ee33629c253d4a5a4af78be2950e_101.png)

![](img/3004ee33629c253d4a5a4af78be2950e_102.png)

![](img/3004ee33629c253d4a5a4af78be2950e_103.png)

That is independent of the parameters that you're updating so you're going to fix that every couple of state you're going to update it So this we saw before for double Q learning there is this observation that you can decouple this selection from actually evaluating what do I mean it can actually decouple this term this maximization term here how so far everything is the same as above or T plus gamma now that maximum term you can do an arc max first find a maximum a the maximum argument and you're maximizing with respect to a and then evaluate your function Q at that maximum so this is an equivalent way of writing the formula up there So it's exactly is's going to give you the same thing assuming that your theta t is theta T theta t minus is theta T So it's exactly the same thing Why is it helpful there is this classical algorithm。



![](img/3004ee33629c253d4a5a4af78be2950e_105.png)

![](img/3004ee33629c253d4a5a4af78be2950e_106.png)

![](img/3004ee33629c253d4a5a4af78be2950e_107.png)

![](img/3004ee33629c253d4a5a4af78be2950e_108.png)

![](img/3004ee33629c253d4a5a4af78be2950e_109.png)

![](img/3004ee33629c253d4a5a4af78be2950e_110.png)

![](img/3004ee33629c253d4a5a4af78be2950e_111.png)

![](img/3004ee33629c253d4a5a4af78be2950e_112.png)

![](img/3004ee33629c253d4a5a4af78be2950e_113.png)

![](img/3004ee33629c253d4a5a4af78be2950e_114.png)

![](img/3004ee33629c253d4a5a4af78be2950e_115.png)

![](img/3004ee33629c253d4a5a4af78be2950e_116.png)

the double Q learning which observed the same thing that Q learning overestimates action values and one solution for that was separating the evaluation from selection so Q is now evaluating and this is the selection step your first select and then you evaluate and then you would use two value functions so let's build on that idea and introduce double Dq and double deep Q network and the idea is very similar to it's a combination of deep Q learning what we saw before and double Q learning where your evaluation network so this is the one that is estimating the action values you are using a target network for it like what you are doing up there so you have a target network for theta T minus that you update every couple of states every couple of steps and then your。



![](img/3004ee33629c253d4a5a4af78be2950e_118.png)

![](img/3004ee33629c253d4a5a4af78be2950e_119.png)

![](img/3004ee33629c253d4a5a4af78be2950e_120.png)

![](img/3004ee33629c253d4a5a4af78be2950e_121.png)

![](img/3004ee33629c253d4a5a4af78be2950e_122.png)

![](img/3004ee33629c253d4a5a4af78be2950e_123.png)

![](img/3004ee33629c253d4a5a4af78be2950e_124.png)

![](img/3004ee33629c253d4a5a4af78be2950e_125.png)

![](img/3004ee33629c253d4a5a4af78be2950e_126.png)

![](img/3004ee33629c253d4a5a4af78be2950e_127.png)

![](img/3004ee33629c253d4a5a4af78be2950e_128.png)

![](img/3004ee33629c253d4a5a4af78be2950e_129.png)

Policy is actually going to be your most recent policy be based on your most recent cu so you select your actions based on the most updated queue but then you evaluate your those actions based on an old policy based on the target network and I promise that I'm going to tell you why actually show you empirically that yes actually Q learning overestimates action values。

 so this is Q learning for different Atari gains alien space invader etc。

 and for all of them you're seeing that overestimation the actual or the true value is this red line down here and that's the overestimation double queue learning still overestimates slightly but it's not as exaggerated as the other guy and it turns out that this overestimation interferes with convergence。



![](img/3004ee33629c253d4a5a4af78be2950e_131.png)

![](img/3004ee33629c253d4a5a4af78be2950e_132.png)

![](img/3004ee33629c253d4a5a4af78be2950e_133.png)

![](img/3004ee33629c253d4a5a4af78be2950e_134.png)

And being able to get good policies and good Q networks and you can see that across a lot of games the same behavior but you might say how are you getting this ground truth how do you get your true value you actually play your game and you do your reinforcement learning the usual way for instance you do your Q learning here you find a cu based on which you can select your actions you're going know your policy or greedy policy but then to get the ground truth you are not going use the estimated queue you're going to use this formula because once you play the game you're going to know your reward you're going know your reward at time one you're gonna to know your reward at time two until the end of the game and that's going give you the underlying true value and this is how you observe that you're overestd any questions so this what is this x axis here for these pots the x axis is the iterations it's time okay。

So does it so like as you're learning your Q value is changing when you're using a deep Q network Yes so you're gonna have at this point in time while you're playing your game you have a different estimate and then this constant value is achieve using the final Q value and then playing the game with that policy yes okay so you let your game you play your game based on the optimal cu that you found and then once you're at the end of the game you know what are you collect it and then you use that to obtain an estimate okay thanks yeah yeah so you first learn your cu and then you play your game based on Q to give you the actual the underlying ground truth the true value Okay any other questions。

What was the only contribution， what was the only smart observation is that you can actually decouple selection from evaluation you select your actions based on a different Q than the one that you use to evaluate your actions and that's why it's called double Q learning so it's a simple extension to what we covered previously as as training progresses those two networks track together right like the evaluation network gets updated by copying the value network and then it's held static for some amount of iterations but then it continues to keep up with the value network or yes that's correct so this theta T minus is going to get it's lagged it's lagging behind theta T so every couple of steps you update and you updated just by copying theta T and theta T。

E gets gradient descent orius gradient ascent updates exactly okay。

 so you don't do gradient ascent or descent on this guy， you do it onta0。

So this is just a copy so you have two options either copy every couple of steps or theta t bar is a moving average of the theta Ts that you saw yeah we saw this version also that this could be a moving average but anyways it's going to lag behind theta T it's interesting that battleman changes this overestimate so much Yes so what these algorithm double Q learning there is actually proof so it's a theoretical algorithm in the case of finite state and finite actions so there is actually theoretical motivation for doing this okay it's not but it's not by lock that this is working any other questions okay perfect。

