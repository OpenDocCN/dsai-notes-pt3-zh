# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P25：L4.4- 反向传播、Nesterov动量和ADAM训练 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton。 Welcom to applications of deep neural networks with Washington University。

 In this video， I am going to show you how。😊，The back propagation algorithm works internally。

 We'll look at back propagation， classic， also atom。

 Netroov momentum and other techniques that are commonly used to train deep neural networks for the latest on among AI course and projects。

 Click subscribe in the bell next to it to be notified of every new video。

 So classic back propagation。 Back propagation has been around for a while。

 It is Jeffrey Henton contributed quite a bit to it。 and werebo as well。

 So a variety of people introduced aspects of back propagation。

 and has been continued to be built upon over many years。

 This equation that you see here is sort of your very general training equation。

 This just says that T。 Now T is the current epoch or time。 This is saying that the weights。

 which are the weights of theta。 The weights for the current time are equal to the weights from the previous time minus V the current time。

 V。😊。

![](img/6491afaa3cf5a798f8c7f93f7b8bf376_1.png)

From the current time is just a vector。 All of these are vectors that holds the amounts that we're going to change each of the weights by。

 So this doesn't tell us a whole lot by itself。 It just says that we are going to change the weights。

 And each time by this vector of change amounts。 Now， the vector of change amounts。

 V sub T will see a variety of functions that show us how to calculate v sub T。

 The first is classic back propagation。 So if we look at this， this is gradient descent。

 So you have Eta multiplied by now， Eta is multiplied by the rest of this。

 This is essentially one unit。 This is not。This thing multiplied by the J function。

This is the Nabla or the upside down Delta or the harp shaped operator。

 This says take the gradients of the loss function with respect to the weights from the previous time step or the previous epoch。

 So this is essentially giving you all of the gradients。

Multiplied by the learning rate at a common values for the learning rate are these 0。10。01。

 rarely Would you ever want to make that one so that you're fully adding the gradients to the weights that would that would simply be too chaotic。

 Now， let's see really what the gradient is and how it's actually used。 This is a derivative。

 It's a partial derivative， So you always take the partial derivative of one multivariate calculus。

 you take the derivative of one single variable and a multivariable expression。

 So one single weight with all other weights held constant。

 So this shows you essentially the error function for a particular weight。

 So the error for this weight as you adjust the weight。 So if you make the weight0。

 the error is going to be here， then it goes up and then it swings way down。

 This is potentially true as you vary just one weight in the neural network。

 the error function will go up down and change its value。 Typically， we're doing gradient。

So we want to get the weight all the way to the lowest point here。 Now， we don't want to graph。

 generate this entire graph and and sample the neural network at each of these points。

 that would be computationally expensive because there is a different chart of this for every single weight in the entire neural network。

And as you change one weight， all all the others potentially change2。

 This is where you have to do the partial derivative。

 We're doing the partial derivative for just one weight。 sayy the weight was currently at 1。5。

 So all we would know is that the error was here。 we don't have the rest of the lead up or continuation of the chart。

 we just have this one point， that point doesn't tell us too much until we take the derivative of the loss function。

 then that tells us the instantaneous rate of change。 So youve got the slope。

 this point right here on the error function curve。 Notice this line has a negative slope。

 But if we if we just added that gradient to it， the negative value， whatever that negative slope is。

 that would decrease the weight。 It would go in the wrong direction。

 So if if you truly want to go this direction， because were past just a little bit of the crest of that hill。

 if you want to go in this direction， you need to take the opposite of the slope。

 That is why up here we're。Ting the sub T because if this， I mean， say we're right here。

 then the line would be very much this this direction。

 and that would be a very negatively sloped line。 you would want a positive number。

 So you continued on your way down。 If we were right here， then the slope would be positive。

 but we would want to subtract one from the weight to continue along this direction。

 So that is classic。Back propagation。 It's governed by the learning rate。

 If you made your learning rate too big instead set a gradient dissenting down here。

 you'd probably jump completely to the other side of it。

 and you would never find your way down to this lower value。

 So learning rate just describes how quickly we're going to attempt to push the weights to optimal values。

 And this link is pretty handy。 It shows a javascript application that I wrote that takes you through all the steps of a classic back propagation。

 So you can see literally how an entire neural network is calculated for X O R。

 Next is momentum propagation。 back propagation。 So momentum is something that was added to back propagation to prevent from being from settling into a local minima。

 So local minima could be right here。 It might be that further over here。

 there would be an even more optimal value。 But once the weight gets settled into here。

 It's really hard for it to push its way completely out of that valley and continue on。いに？

We have the case here。 The weight， which is where that ball currently is at。

 is essentially stuck in a local minimum。 There might be a global minimum here。

 It's really hard to know where the global minimum is。 It's usually almost impossible。

 So this weight would have been continuing down， down down， but it would potentially get stuck here。

 If not for the momentum that pushes it over the hump and allows it to continue。

 Moment just as its name implies。 You can think of these weights as moving through high dimension space。

 Moment just gives the gives the weight push and continues that push as it maintains its momentum。

 This is the formula for momentum。 Now we have two hyperparameters。 We have Eta。

 which is the learning rate。 but we also have lambda， which is the momentum rate。

 The first part of this is completely the same as classic back propagation。

 You are simply taking the gradient。Multiply by the learning rate。

 But you have this additional term here。 And this is the momentum term。 This is lambda times V t -1。

 So whatever our previous delta our previous update was， we're scaling it by lambda and adding it。

 You're just adding the last update scaled right onto the equation with everything else。

 That's really all that momentum is。 So as you were moving down this。

 you would have built up a lot of momentum because you would potentially be moving down fairly fast。

 Then that change is very much a positive weight that would keep getting added on the weight and hopefully push it over the hump and on to possibly out of the local minima and onto a better situation。

 hopefully， by the way， very common value for momentum is 0。9。

 They usually favor a fair amount of momentum。 learning rate is often much smaller。 It's usually 0。

10。01 or some other negative power of 10。 Next， we're going to look at。

And online batch propagation so this is an important concept for propagation training。

 We'll see later that we can configure these values in TensorF and determine what the batch sizes will be batchch is simply how many training set elements do you need to go through so each of these each of these gradients that we're calculating is for a single train set element。

So you might have1 thousand elements in your training set。

 How many of those you don't have to literally update the weights every single time you calculate a training row and get the deltas to the weight。

 you can batch those up and you batch them up simply by summing up the gradients So you process the first row of training training data and you get a vector gradients equal to or changes the V equal to the size of the weights and you just you can calculate the next training row and you add those gradients onto whatever read had before。

 you keep vector adding the gradients until you've made it to the batch size。 So a batch size。

 if you had a batch size of 10， that means as it's going through the training set。

 itll make it through 10 elements， and then at the end of the 10 elements。

 it has the gradients that are basically the sum of that whole run。

 and then it will apply the changes to the weights。

 Online training simply applies the change to the weight as soon。

You calculate the gradient just one at a time， calculate a gradient for one training row。

 apply it to the weights， move on to the next training row， calculate its gradients。

 add it to the weights and continue Having the batch sizes this can provide considerable efficiency to the training of the neural network this is also very big data compliant because if you've got a very。

 very large data set you just need to randomly sample many batches from it so many batch training that's another very common technique for training neural networks many batches are typically between 32 and 64 in size so they're relatively small step and iteration that is just how many training cycles has has the neural network gone through step iteration or even and then all right now we'll look at stochastic gradient descent which is often used in conjunction with many batch training stochastic gradient descent is used to it provides a very stochastic or。

scentWhat's happening is rather than calculating the gradients with the current with the entire data set。

 you just pick small groups and you keep going through these random samples with replacement。

 of the neural network training data and as you go through each of these one by one by one the error will decrease it'll go up sometimes sometimes you'll pick particularly bad sets of training data sometimes you'll pick particularly good sets。

 It just all pretty much depends。 So stochastic gradient descent is often used alone or as part of another training。

 It's computationally efficient and it decreases overfitting by focusing only on a small number of relatively good weights and also there's a variety of other techniques like I said。

 back propagation and gradient descent。 that's just the main backbone some of these other techniques。

 what they attempt to solve is the learning rate and momentum。 These are both hyperparameter。

 These are numbers that you need to tune along with everything else。

 you thought it was bad enough that you had to pick how many hidden letters and how。

neurons you want on each head layer Now you've got a learning rate of momentum。

 and you need to figure out what the best learning rate is。

 what the best momentum is so that you will be able to effectively train this neural network。

 The problem is the learning rate， if you adjust it too small。

 it's never going to accurately train your neural network it's just not taking enough risk if you make it too large your neural network will be very。

 very erratic and momentum， same thing if you make it too large， things become erratic。

 if you make it too small， it's not really having effect。 Also if you think about it。

 this learning rate is being applied to every every weight in the entire neural network。

 maybe a single learning rate is not enough， maybe some neurons are learning faster than others。

 So they like a concept of putting on multiple learning rates or you can also sometimes you will see that they will just automatically decrease the learning rate as training progresses So we're trying to move away from having every weight having a global learning rate and momentum and then also。

Move to making those those values very sensitive， very nonsensitive are very accommodating to values that weren't chosen so well。

 These are some other training techniques that we that I've worked with in the past。

 There's resilient propagation。 It works pretty well。

 It basically recognizes that the sign of the gradient is probably the most important thing。

 It tells you which direction the weight should move to better optimize。

 It also does not need a learning rate and momentum。 So it was popular back in the day。

 It's not seen as much use with a deep learning N of accelerated a gradient。

 What that does is with stochastic gradient descent。

 It helps to mitigate the risk of just picking a really bad mini batch that then damages the rest of the training that you' that you've done There's addedgrad and Ana delta。

 These are both。At a grad， basically it keeps a per weight decaying learning rate。

But it's monoomically decreasing， it never increases again。

 so that's why added Delta was created to address atgrads issues where that that learning rate could just go in a direction and decrease to pretty much zero。

There's also nongraient methods。 If you can't take a derivative of your last function。

 these might be useful。 This includes simulated anneling， genetic algorithms， particle swarm。

 Nedermeed and many more。 So the atom update rule talked about before classic back propagation。

 It's just another way of calculating V to put into this weight update algorithm that we have before。

 Now the atom update rule。 what is very nice about it is it doesn't have you don't really have to focus too much on a learning rate。

 there is a learning rate present but of the values that you that you have。

 the authors of the original paper King Muba， they give some good recommendations for the hyperparameters。

 and I rarely， even that learning rate at the end tend to the negative8。

 they don't you often do not have to have to change those。

 This is a relatively new training algorithm。 It was introduced in 2014。 It's a popular one。

 It deals with training for a sparse for sparse data。

We lots of missing values and then also stochastic error function the error function is stochastic because we're doing stochastic gradient descent so we're constantly randomly subsampling a batch size of many batch and updating the neural network based on that So your the changes that you make from one iteration to the other might not help because you're grabbing a different set of set of training data on each one the paper for this for this is given here at Cornell University the archive if you haven't dealt with archive before that's the Greek letter chi so a archive archive and moment moment momentest method of moments that you see here it's a way of estimating each of the moments of of a distribution of values so that's the mean the variance and reliance and so on so let's look at。

The actual paper for this， this is very similar to the code that we've seen for the other ones。

 so this is just t equals t plus one that's indicating that we're moving through the time we're initializing the first and second moment the first moment is the mean。

 so the mean of the gradients that you're trying to estimate。And V is the variance。

 so the second moment there is a third and additional moments。

 but all we're dealing with are these two the first two moments。

 by the way that's where the name add comes from adaptive moment estimation and then we initialize the time set to zero。

 so these two initial estimates are zero。We are going to calculate the G， the gradient。

 so this is the gradient， just like we're doing before， very similar to classic back propagation。

 a little bit different terminology instead of the J that I use they use F so this is this is the loss function with the weights that's exactly the notation from the module for the previous one。

And we are going to。Get that gradient。 These two values deal with a bias on the。

That occurs early on since these are initialized to 0， that creates a tremendous bias towards  zero。

 So these are just two。嗯。I'm sorry the hats down here are actually that that's where they're calculating the they're dealing with the the initial。

Fact that these are starting out at zero。 So M hat and V hat M and VT themselves。

 this is essentially updating each of these。 so you'll notice that it's M based on the previous T。

They're updating as they go through it， they are essentially creating more and more of a estimate of the first and second moments。

 and these are vectors。Obviously they're across the weights。

 so that's essentially creating almost a learning rate for each。

The first one is on the first power and then second power， so this is squared。

We calculate these adjustment values just to deal with the fact that these started at a 0。

 and then we're going to update the weights。 So weight t， this is very simple。

 So this part is exactly like what we had from trying to highlight the bottom row。

 But up to here is exactly what we had for the for classic。We're subtracting the gradient。

 but instead of subtracting the gradient， we're using this formula to update the parameters or weights。

Alpha is the learning rate， so usually learning rates or step size， as they call it。

 you're multiplying by the rest of this to scale this。And you're putting in the two hat values。

 which were based on these just to adjust them so that they're not so biased initially towards zero。

That is essentially Adam， it's a little bit more complicated than your classic back propagation。

 but not a whole lot not I mean this is not terrible to implement and。

In Java or another programming language， they discuss the algorithm。

And they talk about that initial bias correction where why that is needed and how you are calculating the two hat values that are very necessary for that。

I will admit I have not read through this part and find it somewhat very complex。

 they're doing some analysis of the convergence， this is essentially proof for why it works。

And then they quote related work and then experiments where they sort of empirically prove through experiment why it works and with E theorems they attempt to talk about why it sort of proofwise why it works。

 related work， R Pro and Agrad， those are two other training very similar training techniques that existed prior to Adam and this is just straight sort of from the paper。

 but I like looking the pseudocode a little bit better。

 but I reproduced it there if you're interested in it。This is a really good diagram。

 I did not create it， I have links to where this is where I found it。Yeah。So anyway。

 and then he cites it to the original author can。Definitely want to give credit where credit is due。

 This is a very， very good diagram of this。 It's an animated g。 So these are。

 this is essentially a search space。 So you can think of this as a rugged sort of two dimensional plane。

 Star is the lowest point。 That's where you want to get to。 And it's like。😊。

It's sort of like marbles rolling down a ridge。This is stochastic gradient descent。

 which is the slowest one。 So that's your classic back propagation。 It's eventually getting there。

 The one that gets there really first is add Delta and。It seems like green。Momentum starts out slow。

 but then really， as you can see， builds up the momentum and then blasts right past it。

 So just your different different training methods。

 Adam is out on here because when this was created。

 Adam did not exist or at least was not all that common yet。 But you can。

 you can definitely see some of them like momentum。 It's very obvious that it's。

It starts to really build that momentum， the little green ball and shoots right past it。

 SGD is just slowly methodically working there and it doesn't even make it。

 they give up and reset it because everybody else has made it。

Kras and Tensorflowlow has a variety of these these techniques available for you。

 Can you the ones that are highlighted they have， so they have stochastic gradient descent in Adam。

 I believe there's other ways you can get to some of these。 I'm sorry。

 these are all of the ones that Tensorflowlow has。 I honestly have no idea what FTRL is or I'm familiar with the other ones。

 the ones that I have highlighted are probably the ones you're the most interested in。

 I would be tempted to highlight RMSs Pro as well。 you can you can definitely experiment with these and get potentially better results where you specify it is down here with the optimizer。

If you specify one of these that means a learning rate you'll pass in a class here and actually pass in the parameters as well you can go to the Tensorflow documentation and they show you ourki is anyway and they they give you the actual class names for this。

 but you can just use any of them just by putting its name in here you'll need to put an object in there if you want to specify even additional parameters these are some of the results that I got trying these out so you can see that on the miles per gallon data set we got basically different results and some like unit's momentum needed a lot more training than say at。

Showing the last successful or the last number of iterations。 So Adam converges pretty quick。

 I I'm pretty fond of that training technique， and I use it often At agrad is also pretty good as well。

 So at agrad， I like RMS Pro definitely， definitely I have seen it T's uses。 I will。😊。

I will try between these and look at them when I am training neural networks and I often start with the atom。

 but then we'll try at agrad or our MSP。There are probably better。

 more scientific ways to pick those， but that tends to work pretty well for me。 All right。

 That is the end of this module。

![](img/6491afaa3cf5a798f8c7f93f7b8bf376_3.png)

Thank you for watching this video on how to train a neural network。 In the next video。

 we're going to literally calculate a neural network from scratch。

 We're going to see how to export the weights from Kes and use those to actually calculate what the output of the neural network would have been。

 This removes all magic from the process。 This content changes often。

 So subscribe to the channel to stay up to date on this course and other topics and artificial intelligence。

😊。