# P70：L9.5.2- PyTorch 中的自定义数据加载器(代码示例) - ShowMeAI - BV1ub4y127jj

Yeah， let's not talk about Pytor custom data loader。

 So the data loader is a class and Pythtorch that lets us， yeah。

 a lot of data more conveniently compared to doing it manually。 I will show you two notebooks。

 One is yeah just the data loader itself with a simple example。

 and then I will show you how we can use it in a yeah model training context。

So yeah what I should say is I'm actually using MNIS here and you may wonder why MN because there is already MNT data set and data lot are implemented in Torch Viion which we could technically import which is what we have done in the yeah last couple of videos so the reason is MNIS is relatively small and yeah in this way I can upload it to GitHub so I can upload this without let's say taking too much space in that repository and it's also for you faster to download and just convenient。

Because you are already familiar with it， but of course here Mnes this represents a more general data。

 so think of it as an arbitrary data consisting of P andG files。

So what I've done is I yeah divided Mnest。And do three parts， a training set。

 a validation set and a test set。So I put them here into yeah PN G files， just in each folder。

 there's a set of PN G files， as you can see here。And。I have also corresponding on CV file。

 So here in the CV file， I have the class tables。

![](img/363ca9888bed55788c258cb6b3103f4e_1.png)

And the file name。Of course， you can also， if you like， you can have only one。

Folder with P And G files and then have a column with validation train and test index so you can also specify it like this。

 I mean， how you set it up is up to you。 I sometimes find it convenient to do it like this。

 Sometimes I only have one gigantic P And G file folder and keep track of what is training what is validation with this test。

 I keep track of it with columns in the C file。 But this is really optional。 I mean。

 how you want to set up is up to you。 You can set it up， however you like。

 and I will show you how we can then handle that with Pyhar data class。



![](img/363ca9888bed55788c258cb6b3103f4e_3.png)

So back to this notebook I showed you now， I have these files so focus now only on these three folders and these these V files。

 the help a function， I will use them later in this train model notebook。



![](img/363ca9888bed55788c258cb6b3103f4e_5.png)

So yeah， let's get started。 So usually when I have a new dataset what I do first is I inspect this dataset。

 So I sometimes use I use image IO。 Sometimes I just use the Python image library I'm not very consistent。

 It doesn't really matter the are multiple libraries and Python that lets you open a P and G file or JpeEC file in Python itself。

 and then you can take a look at it。 So here I'm using P it's the Python imaging library。

 If you have to install it。 I think you have to do install。



![](img/363ca9888bed55788c258cb6b3103f4e_7.png)

Hello。Why pillow and not wipe。Pill or PL。 That is because the Python imaging library。

 I think it got abandoned at some point。 And then some people forked it on Gitthub to further maintain it。

 And this fork is called pillow。 But even if you install it as pillow the import is identical。

 you use this one to import it。 or here in particular。

 we are only implementing the importing this image class。



![](img/363ca9888bed55788c258cb6b3103f4e_9.png)

So here I'm just looking at the image。 So here。

![](img/363ca9888bed55788c258cb6b3103f4e_11.png)

I'm loading one data point or one image from this Mest train folder。 why C map binary。 Yeah。

 because colour maps by default is this verus colour map， which is kind of useful for heat maps。

 But yeah here maybe it looks a bit goofy if we have these colors for Ms。

 So here we use just this version。

![](img/363ca9888bed55788c258cb6b3103f4e_13.png)

![](img/363ca9888bed55788c258cb6b3103f4e_14.png)

Alright， yeah， also， I find it helpful to just take a look at the image dimension。

 So here it's 28 by 28。 There is no colour channel。 And you can see the values。

 the pixel values are between 0 and。

![](img/363ca9888bed55788c258cb6b3103f4e_16.png)

![](img/363ca9888bed55788c258cb6b3103f4e_17.png)

![](img/363ca9888bed55788c258cb6b3103f4e_18.png)

255。

![](img/363ca9888bed55788c258cb6b3103f4e_20.png)

ItCould be 254。 I'm not actually not quite sure here actually I see the the highest one is 253。



![](img/363ca9888bed55788c258cb6b3103f4e_22.png)

Alright， so then looks， okay。 So we now， know what we are working with。



![](img/363ca9888bed55788c258cb6b3103f4e_24.png)

![](img/363ca9888bed55788c258cb6b3103f4e_25.png)

Let's know。lot the CV files。

![](img/363ca9888bed55788c258cb6b3103f4e_27.png)

padas， and then I'm loading my CV files。 So these are only the first five rows with this head command。



![](img/363ca9888bed55788c258cb6b3103f4e_29.png)

![](img/363ca9888bed55788c258cb6b3103f4e_30.png)

Yeah， and I can also show you， oh， you can see it right here。The dataset is。

 yeah only made it artificially small。 There are only 256 images in each dataset set。 Mnes is。

 of course， much bigger。 It's usually I think 50000 in the training set and 10000 a test set here。

 I just made it smaller because I'm going to upload this to Github so you can download it。

 And in this way it's not like too much taking up too much space there。



![](img/363ca9888bed55788c258cb6b3103f4e_32.png)

![](img/363ca9888bed55788c258cb6b3103f4e_33.png)

Otherwise， I don't want to upload 50000 small filess and stuff， you know， Alright， so here。



![](img/363ca9888bed55788c258cb6b3103f4e_35.png)

Here's our interesting part now。 that's the data set class and Pythtorch。

 and so in order to do to use the data la we need a data set so there are two parts。

 one is the data and one is the data la， So let's talk about the data first because that's what we need for making the data la。

 So here the data is really how we read the data。

![](img/363ca9888bed55788c258cb6b3103f4e_37.png)

![](img/363ca9888bed55788c258cb6b3103f4e_38.png)

So this is something you yeah have to set up yourself or a new dataset。

 So here this is from Pytorch Torch U data。 This is yeah something a class from Pytorch。

 and here this is called class inheritance in Python。

 So we are inheriting certain features from dataset so that they are available in all our dataset。

 So it's called class inheritance。 It's like a not a Pytorch， but a Python concept。So。

 and then we are defining our own dataset set， I'm just calling it my dataset set。

 but you can call it whatever you like。

![](img/363ca9888bed55788c258cb6b3103f4e_40.png)

And then like in every class， we have an init method。 And again。

 in this constructor and this init method， I'm specifying certain things。It's basically by the way。

 arbitrary what I put here， it's not required to put anything here。

 but on what we need here because we have CV files and we have folders， I put both the CV path。

 the path to the CV file， let's say the training CV and the image directory， for example， here。

 this directory。And there's also a transform for doing a custom image transformation。

 I will show you just a very basic transformation。 Actually， we' are not doing any transformation。

 I will talk about this in the next lecture。

![](img/363ca9888bed55788c258cb6b3103f4e_42.png)

Yeah， so what's going on here is in the in。 in the unit。

 we are loading the CCV file and keep it attached to the data loaddown。Not， no。

 we don't need it attached We one second， so。We lot the CV file。

 We save the image directory to the self dot image dear attribute so we can use it later。

 and then we save the image names as self do image names。

 And this comes from the CV file from the file name column。 So if I scroll up again。

 this is this column we just save this column here。



![](img/363ca9888bed55788c258cb6b3103f4e_44.png)

![](img/363ca9888bed55788c258cb6b3103f4e_45.png)

And then we also save the class label column itself dot y。



![](img/363ca9888bed55788c258cb6b3103f4e_47.png)

These sell class labels。 And then we just store whatever we provide a transform here。

 So this is a setup for the data set when it's created。



![](img/363ca9888bed55788c258cb6b3103f4e_49.png)

And here， this is how a data point gets loaded。 a single data point。

 Remember that this one was in short you the animation loading a pair of。

Or a data point with its training label， basically， So one image and one label。

 So that's what we are what's loaded with us get item here。

Here you have to have this index here I in there other ways， but I find it convenient with the index。

And then we have to specify。 So what we do is here we specify how we obtain one image and one corresponding label。



![](img/363ca9888bed55788c258cb6b3103f4e_51.png)

So how do we open the image， So image that open So this is similar to what I used。



![](img/363ca9888bed55788c258cb6b3103f4e_53.png)

Up here。The mentioned stood open。

![](img/363ca9888bed55788c258cb6b3103f4e_55.png)

And then I'm giving it the path。 So the path is。Based on the image directory that I provide here。

 and then。The image name。

![](img/363ca9888bed55788c258cb6b3103f4e_57.png)

So the image name is in this column， right， so。Here what I M G is。 It will be， for example。

 something like Emest。

![](img/363ca9888bed55788c258cb6b3103f4e_59.png)

Train。Let's say， one dot P And G。

![](img/363ca9888bed55788c258cb6b3103f4e_61.png)

So here， index will select a random once it could be either 1 or3 or 5，1，2。123， whatever， so。

This is chosen randomly。 so this is how this data set is basically shuffled by always picking the ind season in random order。



![](img/363ca9888bed55788c258cb6b3103f4e_63.png)

And then there is an optional transformation that we can apply to the images， for example。

 normalization， rotation and things like that。 and I will show you how that works in the next lecture。



![](img/363ca9888bed55788c258cb6b3103f4e_65.png)

And then we also obtain the corresponding class label。



![](img/363ca9888bed55788c258cb6b3103f4e_67.png)

So if index is， let's say one。Then we will， or let's say indexes yeah here 1。

 then we would obtain image 513 to PN G and the corresponding label 0。



![](img/363ca9888bed55788c258cb6b3103f4e_69.png)

And then it returns both the image and the label。And that's essentially it。

 There's one more method here。 That's the length。 And this one is the length of the data set。

 So that is how this data set knows when one epoch is finished。

 So here we can simply compute the length by。Getting the shape of this y。

 which is the class label column， so。

![](img/363ca9888bed55788c258cb6b3103f4e_71.png)

Essentially。

![](img/363ca9888bed55788c258cb6b3103f4e_73.png)

Oh， I have not imported anything here。😔。

![](img/363ca9888bed55788c258cb6b3103f4e_75.png)

I actually should have。

![](img/363ca9888bed55788c258cb6b3103f4e_77.png)

D it's not different，hu。Oh， I， sorry。 I call a dift train。



![](img/363ca9888bed55788c258cb6b3103f4e_79.png)

![](img/363ca9888bed55788c258cb6b3103f4e_80.png)

Okay。

![](img/363ca9888bed55788c258cb6b3103f4e_82.png)

So this is our data set。 So this is really specifying how we lot a data set or images from the data。



![](img/363ca9888bed55788c258cb6b3103f4e_84.png)

And now this is the data laer that is also loading data points。

 but this is really for making our mini batches。

![](img/363ca9888bed55788c258cb6b3103f4e_86.png)

![](img/363ca9888bed55788c258cb6b3103f4e_87.png)

So。For doing that， we need。

![](img/363ca9888bed55788c258cb6b3103f4e_89.png)

The data set。So。Here what I'm doing is I'm setting up the training dataset set。

 So the training dataset set has the CB file Min MnesT underscore train dot CB and the folder Mnes train。



![](img/363ca9888bed55788c258cb6b3103f4e_91.png)

![](img/363ca9888bed55788c258cb6b3103f4e_92.png)

This is this folder here and this C file。

![](img/363ca9888bed55788c258cb6b3103f4e_94.png)

Let me before I explain this in more detail， also show you the validation data set。

 so here's the same thing for the validation set， but notice that the folder names are different and the C file names are different and here is the same for the test set。



![](img/363ca9888bed55788c258cb6b3103f4e_96.png)

![](img/363ca9888bed55788c258cb6b3103f4e_97.png)

![](img/363ca9888bed55788c258cb6b3103f4e_98.png)

Now。See， there is another thing going on Trans。 and this is our custom transformation。

 We don't do anything here except converting the image to a Pytorch tensor。

 So there is the Torch vision library， which has this transforms package or sub library。

 and there are different。

![](img/363ca9888bed55788c258cb6b3103f4e_100.png)

Methods for augmenting and transforming images here。 I'm using something called2 tensor。

 and this one will convert an image to a Pyth tensor。

 but it will also normalize the images by dividing them by 255 automatically。I actually find this。

 I don't know。 I would like if it wouldn't do this automatically because it's maybe something we don't want to do。

 but in any case， yeah it does that so what I mean is it would be cool to have the choice whether we do it or not。

 Maybe there's a new function that has or give you gives you the choice。

 but it's actually not a bad idea to normalize images。 So in that way。

 it's maybe good so people avoid making mistakes because yeah。

 training a network on unnmalized images is usually a bad idea。



![](img/363ca9888bed55788c258cb6b3103f4e_102.png)

Okay。Yes， so this is how we then set up along。Training data。 Now we have created a dataset。

 a training dataset using our my dataset class that we defined here。

 So here this is just defining the class and here we are actually using it。

 And now we are setting up the data la。 So that's the main part。



![](img/363ca9888bed55788c258cb6b3103f4e_104.png)

![](img/363ca9888bed55788c258cb6b3103f4e_105.png)

![](img/363ca9888bed55788c258cb6b3103f4e_106.png)

Which。Takes in this training dataset。 And here we also specify the batch size。

We specify whether we shuffle or not after each epoch。

 this is shuffling or essentially before each epoch。 and there is also a parameter nu workers。So。

It would be great to have a whiteboard here or something。 I don't have one。But think about it。

As this。 So if we Python is single threaded， usually。 So there's one mainy Python process。

 one process running。 So there's usually， let's say data processing。And then there's our model。

 And this， let's say。We give our data to the GPU。 and then on the GPU。

 there happens the model training， and then。嗯。It then it goes back to。Data processing again。And then。

It's basically a repeating loop。 So we are going from data processing to the GPU where we do the model training and then data processing。

 GPU model training。 And this would also be true for CPU。

 The main point is that this is sequential because Python is usually one single process。

 one main process， however。Data processing。Can be slow。 I mean， it can take， let's say。

10 seconds or 5 seconds to load the images。So。It would be more efficient if we have the data processing decoupled。

From giving the data to the GPU and the model training， if those happen like in parallel， right。

 So we could have actually multiple。CPUus， via multiple CPUUus。 We can do the data processing。

 and then the data is already ready in the memory。 and the GPU just has to read it and do the model training。

 It has never， never has to wait until the next batch is processed。So in that sense。

 we can use multi processing of our CPU to prepare the next batch of images for the GPU。

 so the GPU doesn't have to wait。For that， we can use the number of workers greater than0 if we have0 then only one main python process is used for both for everything for the whole pipeline。

 if we set it to one， then it will create one sub process to load the data which makes it more efficient and two is even better。

I noticed when I run it here， actually， I get problems recently with recent versions。

 I think this is because Mnes is so fast to load that it will just load too many things at once。

 And then it has too many open files waiting for the GPU to be processed。

 So I get nowadays an error when I run it on Mnes。 But if I have any other data set other than Mnes that is usually not the problem。

 because Mnes is really just too simple。 I think that's the problem。 So I set it to0。

 But in your projects， you may want to set it to a higher number。 And for example。

 in my research projects， I usually use two3 without problems。



![](img/363ca9888bed55788c258cb6b3103f4e_108.png)

嗯Yeah。Or I should also explain what drop last means。

So if you have a number that is let's say not divisible by 32。

 then there will be a last batch that is smaller than 32 right And if drop last is true。

 it will be dropped you don't have to do this I mean you don't have to drop this。

 but I noticed sometimes in my research code that if I have， let's say batch sizes of 512。

 and then the last batch is only 11 examples。 this last batch can be extremely noisy and sometimes harm the model performance as a bad update at the end of the epoch。

 So personally in my projects I found usually dropping the last mini batch。If it's smaller。

 then the batch size is sometimes good。Alright， let's take a look now。

 So here we are initializing all the data load for the training set， for the br set and the test set。



![](img/363ca9888bed55788c258cb6b3103f4e_110.png)

![](img/363ca9888bed55788c258cb6b3103f4e_111.png)

![](img/363ca9888bed55788c258cb6b3103f4e_112.png)

And here I'm just， yeah， I'm iterating through it to just make sure that it works。

 So here I'm simulating how we would train a model。 So we have， let's say。

 just two epochs and then we iterate through the batches here。For our training order。

 this is actually what you have seen before。 We have used the built in endless data set。



![](img/363ca9888bed55788c258cb6b3103f4e_114.png)

I am transferring it to the device。 So the device， if you have a GPU， it will be the first GPU。

 Otherwise， it will be the CPU。

![](img/363ca9888bed55788c258cb6b3103f4e_116.png)

So yeah， it will just iterate sea。

![](img/363ca9888bed55788c258cb6b3103f4e_118.png)

So just give the batch size。 so it will create。

![](img/363ca9888bed55788c258cb6b3103f4e_120.png)

1，2，3，4，5，6，7，8 mini batches。

![](img/363ca9888bed55788c258cb6b3103f4e_122.png)

And that is it let me change this to one and see what happens I。



![](img/363ca9888bed55788c258cb6b3103f4e_124.png)

Don't always get this error， but with amness。

![](img/363ca9888bed55788c258cb6b3103f4e_126.png)

Yeahep， see， I get something。Called。

![](img/363ca9888bed55788c258cb6b3103f4e_128.png)

Like this。

![](img/363ca9888bed55788c258cb6b3103f4e_130.png)

I think this is because there are too many open files。



![](img/363ca9888bed55788c258cb6b3103f4e_132.png)

Doesn't say so explicitly。Because the weird thing is。

 I don't get this error when I run this on data sets that are not Mnes。 There's something about Mnes。

 I think it's。

![](img/363ca9888bed55788c258cb6b3103f4e_134.png)

![](img/363ca9888bed55788c258cb6b3103f4e_135.png)

And this is just as simple。

![](img/363ca9888bed55788c258cb6b3103f4e_137.png)

It's a little bit weird， to be honest。Also， I can't remember in the past getting this error about you anyways。



![](img/363ca9888bed55788c258cb6b3103f4e_139.png)

Could also be my computer because I compiled Pythr from scratch。

 but I also get this error on my other machine， so。



![](img/363ca9888bed55788c258cb6b3103f4e_141.png)

![](img/363ca9888bed55788c258cb6b3103f4e_142.png)

Anyways。So。

![](img/363ca9888bed55788c258cb6b3103f4e_144.png)

Let's go back to this one Yeah。 and here we can also just print the shape of one of the batches here。



![](img/363ca9888bed55788c258cb6b3103f4e_146.png)

So the shape is 32。 Then the color channel is only one color channel。

 So because it's black and white and then 28 pixels high，28 pixels white。

 here's just printing it as a vector if we reshape it。



![](img/363ca9888bed55788c258cb6b3103f4e_148.png)

32 times 784。 So this is what our multilayer perceptron needs as an input。

 so convolal networks can work with this input directly。 multilayer perceptrons cannot。

 They can only work with this。

![](img/363ca9888bed55788c258cb6b3103f4e_150.png)

Just just for reference how it looks like the torch tensor。 can see it's normalized。

 We should be able。 maybe we can't。

![](img/363ca9888bed55788c258cb6b3103f4e_152.png)

It's just see if it's。Cause it's abbreviating it。

![](img/363ca9888bed55788c258cb6b3103f4e_154.png)

If we get printed it。Here you can see the highest value 。999 because it's 253 divided by 255。Alright。

 so this is how the data load works。 Let me now show you the model training code here。



![](img/363ca9888bed55788c258cb6b3103f4e_156.png)

Using the custom data model。

![](img/363ca9888bed55788c258cb6b3103f4e_158.png)

So here I'm now using a hybrid of what I showed you two videos ago when I use helper functions。

 helper scripts and a Jupyter notebook。So here I have set up several helper files that I may reuse in different projects。

 and this helps me keeping the notebook kind of small。 So if I make a new notebook。

 let's say I call it notebook。2， I can make some changes to this notebook， for example。

 some settings， but I don't have to copy and paste all the code。 It's in that way， easier to read。

 especially if you want to， let's say modify some function as a bug in the accuracy function。

 Then you don't have to go back to every file here and change the code。

 You only have to change it in one of the files and the P files。 So I can just maybe open them。



![](img/363ca9888bed55788c258cb6b3103f4e_160.png)

Show you what I mean。So。😔。

![](img/363ca9888bed55788c258cb6b3103f4e_162.png)

Examp， help I evaluate。 I have this set all seats Demin compute accuracy。 So if there's a bug。

 for example， I only have to change it here once I don't have to go back to all my notebooks。

 I find this very helpful if I have a project with multiple model training and model notebook scripts or notebooks and scripts。

 alright。

![](img/363ca9888bed55788c258cb6b3103f4e_164.png)

![](img/363ca9888bed55788c258cb6b3103f4e_165.png)

Me closes again。 We can take a look at individual ones。



![](img/363ca9888bed55788c258cb6b3103f4e_167.png)

So。

![](img/363ca9888bed55788c258cb6b3103f4e_169.png)

Yeah yeah importing certain functions from this。All from these helpalpa files。



![](img/363ca9888bed55788c258cb6b3103f4e_171.png)

Then here are my settings。 You can also， like I explained before have a separate settings file here。

 I have the notebook itself， random seat， batch size and number of epochs。



![](img/363ca9888bed55788c258cb6b3103f4e_173.png)

And then， I'm using these。To make that deterministic。 And he has just。



![](img/363ca9888bed55788c258cb6b3103f4e_175.png)

So yeah， I have a get data load function that actually uses the data load from the previous notebook that I showed you。

 I just put it into。

![](img/363ca9888bed55788c258cb6b3103f4e_177.png)

![](img/363ca9888bed55788c258cb6b3103f4e_178.png)

This script here。 Now I have my data set here， and I have written a get data order， which will。



![](img/363ca9888bed55788c258cb6b3103f4e_180.png)

Set it up for me automatically。

![](img/363ca9888bed55788c258cb6b3103f4e_182.png)

So that it's basically just a slightly modified version of what I've showed you in the previous notebook where I just have arbitrary paths and stuff。

 and it will return the training order， validation order and test order。



![](img/363ca9888bed55788c258cb6b3103f4e_184.png)

![](img/363ca9888bed55788c258cb6b3103f4e_185.png)

And here I'm just testing that they actually work。 So just getting some statistics。 and you can see。

 So if I run this again， you can see that the shuffling works because you can see that these numbers change。

 So these are the first 10 labels。So you can see this。 So every time it will start from scratch。

 because I break here。So you can see these numbers change。However， if I set my random seat。

I always get the same order， see。Can run this again。



![](img/363ca9888bed55788c258cb6b3103f4e_187.png)

Always get the same order because of the random seed， the the random seed。Yeah， makes the。嗯。

Makes it consistent。 Its so， for example， if you run this code。

 you will get the same model and same accuracy I got because you use the same random seat。

 This is useful， for example， if you do research and you develop some code and want to share it with someone else and the other person wants to reproduce your code。



![](img/363ca9888bed55788c258cb6b3103f4e_189.png)

嗯。

![](img/363ca9888bed55788c258cb6b3103f4e_191.png)

So yeah， here is the multi perceptionceptron。 I yeah simplified this a little bit。

 So I'm using sequential。 Now。 I mean， simplified compared to two videos ago here I'm actually using flattened。

 This is actually new。 I like this a lot。 So this way we don't have to reshape。



![](img/363ca9888bed55788c258cb6b3103f4e_193.png)

Our feature vector。 So it will essentially reshape the 28 by 28 to 784 for us。



![](img/363ca9888bed55788c258cb6b3103f4e_195.png)

So we don't have to do it manually somewhere down here。Yeah， and this is it。

 So here I'm using sequential。 so I don't have to do anything in the forward。

 It will automatically return the logicits。 So here this is a multilay perception with only one hidden layer。

 So this is the first hidden layer。 Then we have a sigmoid activation。

 and then we have the output layer。And then we would technically have a softm。

 but we don't need to have the soft max because the functional cross entropy loss in Pythtch computes the softm for us。



![](img/363ca9888bed55788c258cb6b3103f4e_197.png)

![](img/363ca9888bed55788c258cb6b3103f4e_198.png)

Alright， so this is how it works。 So don't need to set another seat herecause I've done it above。



![](img/363ca9888bed55788c258cb6b3103f4e_200.png)

So here the seat would be for。

![](img/363ca9888bed55788c258cb6b3103f4e_202.png)

For the initial random weights， we'll also talk about this in a in。2 lectures。

 So not the next lecture， but the lecture。 after that。

 we will talk about these different ways we can initialize weights。



![](img/363ca9888bed55788c258cb6b3103f4e_204.png)

Mse stochastic， great incent。

![](img/363ca9888bed55788c258cb6b3103f4e_206.png)

And here， I also， yeah just brought a function for training The model is essentially what you have seen before。

 I just put it into a separate file here。 So if I go to help train Pi。

 I have all the code I have had previously in here。



![](img/363ca9888bed55788c258cb6b3103f4e_208.png)

![](img/363ca9888bed55788c258cb6b3103f4e_209.png)

![](img/363ca9888bed55788c258cb6b3103f4e_210.png)

Because it's essentially always the same code， so you can use that in other projects as well。



![](img/363ca9888bed55788c258cb6b3103f4e_212.png)

You can just， yeah， copy and paste that。 It just keeps the notebook more readable in that way。

 It's not such a long notebook anymore。

![](img/363ca9888bed55788c258cb6b3103f4e_214.png)

Oops， what do we got here， Yep， that's what I always forget， defining things。



![](img/363ca9888bed55788c258cb6b3103f4e_216.png)

![](img/363ca9888bed55788c258cb6b3103f4e_217.png)

Alright， so trains。 It will train very fast， actually。

 because we only have 256 data points in each data set。



![](img/363ca9888bed55788c258cb6b3103f4e_219.png)

Yep， it is training fast。

![](img/363ca9888bed55788c258cb6b3103f4e_221.png)

Yeah， we get actually pretty high accuracy。 I mean， given that we only have 256 images。

 it's also Ba overfitting。 It's actually not yeah， you can see it's 91% and 73。 It's actually。

 it is overfitting。But yeah， the validation， accuracy and test accuracy are almost identical。

 The difference here， Why is the difference is's usually just a small random effect， right。

 because it's a small data set 156。

![](img/363ca9888bed55788c258cb6b3103f4e_223.png)

嗯。Yeah， and then I also have functions for plotting the training loss and the accuracys also helpful。



![](img/363ca9888bed55788c258cb6b3103f4e_225.png)

So yeah， I have the version with a running average。



![](img/363ca9888bed55788c258cb6b3103f4e_227.png)

And。😔，Can see the loss goes down。

![](img/363ca9888bed55788c258cb6b3103f4e_229.png)

We get train for one our epochs。 And here the accuracy goes up。 But then at some point。

 there's more and more overfitting。So I put these plotting functions in help plotting if you ever need them。

 I think I will also personally reuse them in future lectures because then I don't have to make these long notebooks because this code is really always the same。



![](img/363ca9888bed55788c258cb6b3103f4e_231.png)

![](img/363ca9888bed55788c258cb6b3103f4e_232.png)

![](img/363ca9888bed55788c258cb6b3103f4e_233.png)

So I have it some time defined find here and then I can reuse that。



![](img/363ca9888bed55788c258cb6b3103f4e_235.png)

You don't have to honestly memorize any of that or。

It's good maybe to understand it if you want to change it。

 but you don't even technically have to understand any of these details。



![](img/363ca9888bed55788c258cb6b3103f4e_237.png)

![](img/363ca9888bed55788c258cb6b3103f4e_238.png)

So it's also something I wrote one time。 and if I ever need it again， I'll just copy and paste it。



![](img/363ca9888bed55788c258cb6b3103f4e_240.png)

Because there are too many other things to worry about。 It's rewriting this is it took me some time。

 I had to there were some bugs and things didn't work and。



![](img/363ca9888bed55788c258cb6b3103f4e_242.png)

In that way， you write it once so that it works and then you can just reuse it。



![](img/363ca9888bed55788c258cb6b3103f4e_244.png)

Alright， so last as a show examples function I wrote。 So it shows some of the images so you can see。



![](img/363ca9888bed55788c258cb6b3103f4e_246.png)

P means predicted and T means true label or target label。



![](img/363ca9888bed55788c258cb6b3103f4e_248.png)

So these are all correct。Yeah， so here this is a。Predicted as2， but the target is 6。 I see。

 I think I made an arrow here that can't be right。Maybe it is right， but let me double check。

I haven't plant this。 It's very spontaneous。 so good that we look at it。 I think is yeah， I sorry。

 it's my mistake。

![](img/363ca9888bed55788c258cb6b3103f4e_250.png)

Now， I just wrote this code， actually， for this lecture。So。Made a mistake。



![](img/363ca9888bed55788c258cb6b3103f4e_252.png)

AndLet's。Do this again。

![](img/363ca9888bed55788c258cb6b3103f4e_254.png)

![](img/363ca9888bed55788c258cb6b3103f4e_255.png)

![](img/363ca9888bed55788c258cb6b3103f4e_256.png)

Hoops should have been targets。Yeah， one it disadvantage is because I have the import at the top of this notebook。



![](img/363ca9888bed55788c258cb6b3103f4e_258.png)

I have to run the whole notebook。😔。

![](img/363ca9888bed55788c258cb6b3103f4e_260.png)

![](img/363ca9888bed55788c258cb6b3103f4e_261.png)

But it's faster run。

![](img/363ca9888bed55788c258cb6b3103f4e_263.png)

Alright， so that looks better Now。 predicted 6， target 2 predicted 5 well。Target 0。

Some other mistake here you can see the model makes some mistakes。

 but I think these are just mistakes because the model hasnt haven't hasn't seen enough numbers because these should be easy to distinguish。

 I think they are clearly number twos。Okay， so yeah， this is the custom nilota。

 So that's it then for this lecture。 next week， we will talk about。



![](img/363ca9888bed55788c258cb6b3103f4e_265.png)

Regularization， like preventing。Overfitting。 All right。 Have a good weekend。



![](img/363ca9888bed55788c258cb6b3103f4e_267.png)