# P184：L81.2- 自动驾驶汽车的端到端学习 - ShowMeAI - BV1Dg411F71G

So far whatever that we have been doing was either an Atari game or a game of chess go or we were training simple robots in simulated environments like Mojuku like open AI gym can we get a little bit more serious and more ambitious and actually were work in the physical world so the next two papers are about that but they are going be very quick the methodology is not too complicated but the fact that whatever that we learned before about reinforcement learning is actually useful and we are going to use it in practice so these actually real stuff you put some camera in front of your car a left camera a center camera and a right camera。



![](img/33757f97d185b28c5313eed5159afb38_1.png)

And somebody is gonna sit in a car in a car that has these three cameras and starts driving so they're going to keep steering the wheel and they're going to change the angle and keep driving so somebody is driving you're monitoring your road collecting data both from the driver and from these cameras and you're storing them in your SSD hard drive so you keep driving you hire a couple of drivers and you let them drive that's going to give you a lot of data to work with but if you have a good driver。

 they're not gonna to make much mistakes so they're not they're gonna to drive a straight line if they have to so they are going keep their lane and if you don't make any many mistakes in your life you're not going to learn it's the same thing for a neural network if you don't show it some mistakes it's not going to learn but you don't want to collect mistakes because you're in the real world。

 you don't want to cross the line because it's gonna。



![](img/33757f97d185b28c5313eed5159afb38_3.png)

![](img/33757f97d185b28c5313eed5159afb38_4.png)

Leading to accidents but what can you do you can take a look at your cameras and then do random shifts and rotations and you know what shift and rotation you did to those images so the same way you can correct the behavior of your steering to bring you back to the same location so this shift and rotation is simulating the behavior that you just you're just crossing a line you' are not keeping your lane but then we know how to cancel that out because this is a shift and rotation that we introduced to the data so we can cancel that out we know that what type of steering is going to cancel that out if the car is going to the left we are going to cancel it out by turning the wheel to the right so your CNN is going to take these cameras those images and it's going to give you the steering command you know the ground truth you know what the CNN is outputing。



![](img/33757f97d185b28c5313eed5159afb38_6.png)

's gonna to give you some errors that you can back propagate and update your CNN so that's how you're supervising your CNN so it is imitation learning and you keep doing that。

 you have a lot of data you keep doing that and let's see what happens that's training for testing you look at your center camera you push it your CNN and that's gonna give you your steering command now your car is driving on its own and then physically you're gonna drive by by some wiring interface So these are engineering problems we don't want to go into that So you are turning your wheel based on the output of your CNN What is your CNN that's your CNN so very basic a bunch of convolutions and a bunch of fully connected that's gonna give you your steering command so nothing complicated How do you evaluate the performance because you don't want to take this CNN put it in your car sit in it and let it drive What is one step before that How can you make sure that everything is。



![](img/33757f97d185b28c5313eed5159afb38_8.png)

![](img/33757f97d185b28c5313eed5159afb38_9.png)

![](img/33757f97d185b28c5313eed5159afb38_10.png)

Correct before actually sitting in a car risking your life what can you do you can take your data and these are some test data。

 these are the data that your car hasn't seen during training you collect some test data the same way so somebody is driving your car the same way that we did shift and rotation you're going to do shift and rotation to these test data and that's going to give you some synthesized images of the road you show them to your CNN your network is going to make some predictions it's going to keep trying to drive that car based on those simulations and then you can see are you making mistakes are you keeping your lane or you're not keeping your lane what is happening but can you actually give me a number if you have a manager in your industry they want you to report your key performance indicator how do you evaluate this give me a number so you can define a metric and your metric is。



![](img/33757f97d185b28c5313eed5159afb38_12.png)

![](img/33757f97d185b28c5313eed5159afb38_13.png)

![](img/33757f97d185b28c5313eed5159afb38_14.png)

![](img/33757f97d185b28c5313eed5159afb38_15.png)

![](img/33757f97d185b28c5313eed5159afb38_16.png)

![](img/33757f97d185b28c5313eed5159afb38_17.png)

![](img/33757f97d185b28c5313eed5159afb38_18.png)

![](img/33757f97d185b28c5313eed5159afb38_19.png)

![](img/33757f97d185b28c5313eed5159afb38_20.png)

While your network is making predictions， it might decide to go left and then if you decide to correct it so somebody is correcting it is intervening。



![](img/33757f97d185b28c5313eed5159afb38_22.png)

![](img/33757f97d185b28c5313eed5159afb38_23.png)

doing some interventions you count the number of interventions that a human had to do so a human is sitting behind his desk in his office or her office and then driving that car in the simulated environment and you count the number of interventions and then you keep driving for a while and that's going to give you a metric that you can report of how good your CNN is doing and once everything is done you're happy you can take that car put it in the car in the road and see in reality is it actually driving correctly or no so this is a framework of imitation learning that you're using in practice so your car wants to imitate how an expert human driver would drive and you can collect as much data as you have space for so these data you're gonna store in a cloud okay but did actually did you actually learn anything so classically if you want to do reinforce if you want to do self-driving cars there are a lot。



![](img/33757f97d185b28c5313eed5159afb38_25.png)

![](img/33757f97d185b28c5313eed5159afb38_26.png)

![](img/33757f97d185b28c5313eed5159afb38_27.png)

![](img/33757f97d185b28c5313eed5159afb38_28.png)

![](img/33757f97d185b28c5313eed5159afb38_29.png)

![](img/33757f97d185b28c5313eed5159afb38_30.png)

Algorithms that are going to try to detect the lane， so they are going to be lane detections。

You can see that without any lane detections without any supervision by just looking at raw data and looking at a human and trying to mimic the behavior of a human your network in its weights or in its activations so these are the actual activations these are the first and second layer so this is the first layer and the second layer of the activations you're taking a look at them and you can see that a network is focusing on the lanes so it's doing lane detection on its own so there is no need for somebody to be labeling that this is a lane and this is actually what companies are doing and usually when you want to do something。

Put a neural network in production or put a software in production you don't do it you don't use only one framework so you don't only use this framework you use multiple different types of frameworks。

 different types of neural networks so is the same idea on some link so some neural networks are trained based on doing the lane detection some of them are trained this way you put all of them on your car and then you take the consensus and if there is no consensus these are safety concerns maybe you stop maybe you warn the driver something okay so it's not the only method but it's one of the methods that are going to be mounted on your car any questions Yeah I was curious in this case the output layer is it a single scaling and that's like a positive if it turns right and negative if it turns left or is it like a softmax multinoal kind of thing no it's a continuous action space。

And it's the angle of this wheel。So this it's a scalar continuous scaling okay， continuous scalar。

 yes， so this output here is a continuous scalar。Any other questions， so in terms of methodology。

 there is nothing complicated here， but you can imagine that this is a hard engineering problem okay。

