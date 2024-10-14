# 【双语字幕+资料下载】PyTorch 极简实战教程！全程代码讲解，在实践中掌握深度学习&搭建全pipeline！＜实战教程系列＞ - P13：L13- 前馈神经网络 - ShowMeAI - BV12m4y1S7ix

Hi， everybody。 Welcome to a new Pytorch tutorial。 Today。 we will implement our first multilayer neural network that can do diit classification based on the famous endlessnes data set。 In this tutorial， we put all the things from the last tutorials together。 So we use the data loader to load our data。 We apply a transform to the data。

 Then we will implement our neural net with input layer， hidden layer and output layer。 and we will also apply activation functions。 Then we set up the loss and the optimizer and implement the training loop that can use batch training。 and finally， we evaluate our model and calculate the accuracy。 And additionally。 we will make sure that our whole code can also run on the GPu if we have GPU support。

 So let's start。 and first of all， we import the things we need。 So we import torch。 Then we import torch dot and N as an N。 Then we import torch。😊，Vision for the data sets。 and we import torch vision dot transforms as transforms。And we also import Matpllip dot pipl S P L T to show you some data later。 And then first of all。

 we do the device configuration， So device config。 And for this。 we create a device by saying device equals torch dot device， and this has the name Kuda。 if we have GP support。 So if。Torch dot kuda dot is available。 And if it is not available。 So else。 we call our device simply CPU。 And then later， we have to push our tenzos to the device。

 And this will guarantee that it will run on the GP if this is supported。So， yeah。 so let's define some hyper parameters。And here let's define the input size。 And this is 784。 And this is because later we see that our images have the size 28 by 28。 And then we will flatten this array to be a 1 d Tenzoa and 28 times 28 is 784。

 So that's why our input size has to be 784。 Then let's define a hidden size。 And here I will say this is 100。 You can also try our different sizes here。And the number of classes。 And this has to be 10 because we have 10 different classes。 We have the digtits from 0 to 9。Then let's define the number of epochs。

 And here I will simply say two so that a training doesn't take too long。 but you can set this to a higher value。Then we define the batch size here， and this is， let's say。 100。 And let's also define the learning rate here by saying learning rate equals 0。001。And now let's import the famous Amnes data。 So you can have that from the Pytorrch library by saying training data set equals。

 And here we use torchvision dot data sets dot Amist。![](img/ee06be2433f88c7e880533bc41c954a0_1.png)

And this will have to have the root where it has to be stored， So root。![](img/ee06be2433f88c7e880533bc41c954a0_3.png)

Equals， and here， this should be in the same folder。 So dot。 And then it should create a folder called data。![](img/ee06be2433f88c7e880533bc41c954a0_5.png)

And then we say train equals true。 So this is our training data set。![](img/ee06be2433f88c7e880533bc41c954a0_7.png)

And then we say we apply a transform right away。 So we say transform equals transforms dot to tenzo。 So we convert this to a tenzzo here。![](img/ee06be2433f88c7e880533bc41c954a0_9.png)

And then we also say download equals true。 So it should be downloaded if it is not available already。![](img/ee06be2433f88c7e880533bc41c954a0_11.png)

Then let's copy this and do the same thing with our test data set。 And here we have to say train equals false。 And we also don't have to download this any more。So now let's continue and create the data loaders by saying train loader equals。 And here we get this from torch dot u dot data dot data loader。

 and then it will have to have the data set by saying data set equals。 And here it gets the training。![](img/ee06be2433f88c7e880533bc41c954a0_13.png)

![](img/ee06be2433f88c7e880533bc41c954a0_14.png)

![](img/ee06be2433f88c7e880533bc41c954a0_15.png)

Data set， a train data set。 Then we have to specify the batch size。 So this is equal to the batch size。![](img/ee06be2433f88c7e880533bc41c954a0_17.png)

And then we also have to say， or we can say shuffle equals true。 So this is pretty good for training。And then we copy this again and do the same thing for our test loader。 So test loader equals gets the test data set。 And we can say shuffle equals false because it doesn't matter for the evaluation。And now let's have a look at one batch of this data by saying examples equals。

 And then we convert it to a inner object， Iter of the train loader。 And then we can call the next method and unpack this into samples and into labels by saying this equals examples dot next。 And now let's print the size of these。 So let's print samples dot shape。

![](img/ee06be2433f88c7e880533bc41c954a0_19.png)

And also， print， print the label dot shape。![](img/ee06be2433f88c7e880533bc41c954a0_21.png)

And now let's save this and run this。 So let's call Python feet forward dot p to see if this is working so far。 And yes， here we have the size of the samples。 So this is 100 by 1 by 28 by 28。 And this is because our batch size is 100。 So we have 100 samples in our batch。 Then the one is because we only have one channel。 So we don't have any colored channels here。

 So only one channel。 And this is our actual image array。 So 28 by 28， as I said in the beginning。And our labels is only a tenor of size 100。 So for each class label， we have one value here。So yeah。 this is our some example data。 And now let's also plot this here to see how this is looking。 So for I in range 6 and here we use matplotlip， So I call PLT dot subplot of the with two rows and three columns and the index I plus1 and then I can say PLt do I show。

 and here I want to show the actual data， So samples of I and then of0 because we want to access the first channel and then I will also give this a column map So C map equals gray。![](img/ee06be2433f88c7e880533bc41c954a0_23.png)

![](img/ee06be2433f88c7e880533bc41c954a0_24.png)

![](img/ee06be2433f88c7e880533bc41c954a0_25.png)

![](img/ee06be2433f88c7e880533bc41c954a0_26.png)

And then I say P， LT dot show。And let's save this， and run this again。![](img/ee06be2433f88c7e880533bc41c954a0_28.png)

And here we have a look at the data。 So these are some example handwritten digtits。 and now we want to classify these digtits。 So for this。 we want to set up a fully connected neural network with one hidden layer。 So let's do this。![](img/ee06be2433f88c7e880533bc41c954a0_30.png)

![](img/ee06be2433f88c7e880533bc41c954a0_31.png)

So let's comment this out again。And now let's create a class neural net。 And this has to be derived from an and dot module。 And now we have to define the in it and the forward method。 So the in it method。 So this will self。 And then it will has to have the input size， then the hidden size， and then the output size。

 So the output size is the number of classes。 And here first， we want to call the super in it。 So super of neural net and self and dot in it。Self。Dot。In it。And then we create our layers。 So first， we want to have a linear layer by saying self dot L 1 equals Nn dot linear。 And this will have has the input size as input and the output size is the hidden size。

 Then after the first layer， we want to apply a activation function。 And here I simply use the famous relu activation。 So self dot relu equals N N dot reallu。![](img/ee06be2433f88c7e880533bc41c954a0_33.png)

And then at the end， we have another linear layer。 So self dot L 2 equals。![](img/ee06be2433f88c7e880533bc41c954a0_35.png)

N， N dot linear。 Now we have to be careful。 So the input size here is the hidden size。 and the output size is the number of classes。![](img/ee06be2433f88c7e880533bc41c954a0_37.png)

And now let's define the forward method。 So this will have self and one sample X。 and now we apply all these layers。 So we say out equals。 and now we use the first layer L1。 which gets the sample X and then the next out is self dot relu now use the activationation function。 which will get the previous output here， and the last out equals self dot L2 out。

 So this will apply the second linear function and now we have to be careful again because here at the end。 we don't want an activation function。 So we don't apply the softm here as usual in multiclass classification problems because in a second。 we will see that we will use the cross entropy loss， and this will apply。

![](img/ee06be2433f88c7e880533bc41c954a0_39.png)

![](img/ee06be2433f88c7e880533bc41c954a0_40.png)

Ply the soft max for us。 So no soft max here。 So we simply say return out。 So this is our whole model。 And then we can create it here by saying model equals neural net。And this will get the input size， then the hidden size and the number of classes。So， yeah。 now we have the models。 So now let's come create the loss and the optr。

 So here we say criterion equals N N dot cross entropy loss。 And this will apply the soft marks for us。 So that's why we don't want this here。 So be very careful about this。And now let's create our optimizer as well by saying tor optimizer equals torch dot optim dot。嗯。Now， let's use the atom optimizer here。 And this has to get the parameters。

 And here we can use model dot parameters。 And it also has to get the learning rate。 L R equals learning rate。![](img/ee06be2433f88c7e880533bc41c954a0_42.png)

![](img/ee06be2433f88c7e880533bc41c954a0_43.png)

Now we have the loss and the optimizer。 and now we can do our training loop。 So training loop now。And for this， let's first define the number of total steps。 So n total steps equals。 And this is the length of the training loader。So now we can do the typical loop。 So we say four epoch in range。

![](img/ee06be2433f88c7e880533bc41c954a0_45.png)

Noum epochs。![](img/ee06be2433f88c7e880533bc41c954a0_47.png)

And so this will loop over the epochs。 And now we loop over all the batches。 So here we say for I。 And then again， we unpack this。 So we say images， images and labels。And then we iterate over。 enumerate over our train loader。 So the enumerate function will give us the actual index and then the data and the data here is the tuple of the images and the labels and now we have to reshape our images first。 because if we have a look at the shape， then we see that this is 100 by1 by 28 by 28。

 as I showed you in the beginning。 And now we set our input size is 784。 So our image tensor needs the size100 by and 784 is second dimension。![](img/ee06be2433f88c7e880533bc41c954a0_49.png)

So the number of batches first。So， let's reshape our。Our tenor first。 So we can do this by saying images equals images dot reshape。 And here we put in -1 as the first dimension。 So then Tsor can find out this automatically for us。And here as second dimension， we want to have 28 by 28。 And then we also call2 device。

 We will push this to the GP U， if it is available。And we have also have to push it to the。 push the labels to the device。 So labels equals labels to。Deevvice。And now let's do the forward pass。 So first， we do the forward pass。 and afterwards。 the backward pass。So the forward pass， we simply say outputs equals model。

 And this will get the images。 and then we calculate the loss by saying loss。Equals。 and then here we call our criterion。 And this will get the predicted outputs and the actual labels。 So this is the forward pass。 And then in the backward pass。 the first thing we want to do is call optr dot0 gra to empty the values in the gradient attribute。



![](img/ee06be2433f88c7e880533bc41c954a0_51.png)

![](img/ee06be2433f88c7e880533bc41c954a0_52.png)

And then we can do the next step by saying lost dot backward。 So this will do the back propagation。 And now we can call optr dot step。 So this will do an update step and update the parameters for us。And now， let's also print some。Print the loss。 So let's say， if I plus1。Moulular 100 equals equals 0。 So every 100th step， we want to print some information。 So let's print the current epoch。

 So by saying this is epoch epoch plus  one。 And then we want to print all the。Epoch。 So number of epochs。 Then let's also print the current step by saying step。 And this is I plus1。 And then the total number of steps by saying n total steps。And we also want to print the loss by saying loss equals loss dot item。

 And let's also say we only want to print four decimal values。So， yeah。 now we are done with the training。 So this is the whole training loop。 And now let's do the testing and the evaluation。And for this。 we don't want to compute the gradients for all the steps we do。

 So we want to wrap this in a with torch dot no gra statement。And then first。 we say the number of correct predictions equals 0 and the number of samples equals 0 in the beginning。 And then we loop over all the batches in the test samples。 So we say four images and labels in。And here we can simply say in test loader。 and then again， we have to reshape this。

 So like we did here。 So images and labels， we want to reshape this and put it and push it to the device。And。Then let's call。 let's calculate the predictions by saying outputs equals models。 So this is our trained model now， and this will get the test images here。And then let's get the actual predictions by saying underscore and then predictions equals torch dot max。

Of the outputs and along the dimension， along the number one。So the torch up max function will return the value and the index。 So we are interested in the actual index。 So this is the class label。 So that's why we don't need the first actual value。So these are our predictions。 And now。

 let's say the number of samples plus equals。 And here we say labels dot shape 0。 So this will give us the number of samples and the current。Batch。So should be 100。 And then we say the number of correct。 So the correct predictions equals。 And here we can say predictions equals equals the actual labels and then dot sum and then dot item。

 So for each correct prediction， we will add plus one。And then， of course。 we have to say plus equals the number of correct。Values。 And then when we are done with the loop。 we calculate the total accuracy by saying a equals 100 times the number of correct。And predictions divided by the number of samples。 So this is the accuracy in percent。

 And now let's print this。 So print。嗯。And we want to print accuracy equals。 And here we simply say a。 And then we are done。 So now let's save this and clear this and let's run this and hope that everything is working。So now our training starts， and we should see that the loss should be increased with every step。 Sometimes it will also increase again。 But finally， it should get lower and lower。And。Now。

 it should be done and testing is very fast。 So now we see that the accuracy is 94。9。 So it worked。 Our first feet forward model is done。 And yeah， I hope you understood everything。 And you enjoyed this。 If you like it， please subscribe to the channel and see you next time， bye。

![](img/ee06be2433f88c7e880533bc41c954a0_54.png)