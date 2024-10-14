# 【双语字幕+资料下载】PyTorch 极简实战教程！全程代码讲解，在实践中掌握深度学习&搭建全pipeline！＜实战教程系列＞ - P10：L10- 数据集转换 - ShowMeAI - BV12m4y1S7ix

Hi everybody， welcomele back to your new Pytorarch tutorial。 This time we want to talk about transforms for our data In the last tutorial。 we use the built in data and data loader classes and if we use a built in data like we see here then we see that we can pass the transform argument to this data set and then apply some transforms。So in this example， we used to build an Ms data set， and then we apply the2tenzo transform。

 which will convert images or Nmpy arrays to Tzos， and Pytorch already has a lot of transforms implemented for us。 so please have a look at the official documentation which you can find at this link。![](img/57a6f303b8d13bb7d856025a14ce5b5e_1.png)

And there you can see all the available transforms。And for example。 there are transforms that can be applied to images。 For example。 centre crop or grayscale or petting。 And then there are transforms that can be applied to Tenzos like the linear transformation or normalize。

![](img/57a6f303b8d13bb7d856025a14ce5b5e_3.png)

Then there are conversion transforms， for example， the Tu pillow image and the Tutenzoa transform。![](img/57a6f303b8d13bb7d856025a14ce5b5e_5.png)

Then there are also generic transforms where we can use Lambdas。 or we can write our very own custom class。![](img/57a6f303b8d13bb7d856025a14ce5b5e_7.png)

And then we can also compose multiple transforms so we can use transform dot compose and then pass in a list which will apply multiple transforms after each other。And。Yeah， so in the last tutorial， we implemented a custom wine data set。 Now。 let's extend this class to support our transforms and write our own transform classes。 So let's start。

![](img/57a6f303b8d13bb7d856025a14ce5b5e_9.png)

And here， I。Copiied the code from the last tutorial where we have our own custom wine data set。 which will load the data。 and then we implemented the get item and the length method。 which will allow indexing and the length function。So let's extend this data set。 So now this should also support the transform argument。 So we put this in our in it and say。

 transform， oh， sorry。Transform equals。 So this is optional。 So by default， this is none。 And then in the in it， we store this。 So we say self dot transform equals transform。![](img/57a6f303b8d13bb7d856025a14ce5b5e_11.png)

And now we also have to make some changes to our get item function。 So here we want to apply a transform。 if it's available。 So let's say here， sample equals this。 and then we say if self dot transform。 So if this is not none。 Then we apply this。 So we say sample equal self dot transform our sample。 and then we simply return our sample。

 So let's return。![](img/57a6f303b8d13bb7d856025a14ce5b5e_13.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_14.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_15.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_16.png)

Sample。And this is all the change that we need for our data set。 and now let's continue and let's create some custom transform classes， for example。 we can write our own to Tenor class。 So in the last tutorial we already converted it to a Tensor right here in this step but we don't need to do this so we can leave this as a nuy array and then let's implement a to Tenor class。 which will then be passed to our data set and which will then later。



![](img/57a6f303b8d13bb7d856025a14ce5b5e_18.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_19.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_20.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_21.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_22.png)

Convert this to a tenzo。![](img/57a6f303b8d13bb7d856025a14ce5b5e_24.png)

So the class twotenzor。 And the only thing that we need is that we need to implement is the double underscore call method。 which will get self and a sample。![](img/57a6f303b8d13bb7d856025a14ce5b5e_26.png)

So now this is a callable object。And what we do here is first， we unpack our samples。 So we say inputs。And labels or targets。![](img/57a6f303b8d13bb7d856025a14ce5b5e_28.png)

Equal sample。 And then we say， return。Torch dot from Numpai， and here inputs。And then also torch dot from nuy targets。![](img/57a6f303b8d13bb7d856025a14ce5b5e_30.png)

So here also， we return。 We still want to return a tuple， like we did here。![](img/57a6f303b8d13bb7d856025a14ce5b5e_32.png)

And this is all that we need for our2tenar transform。 And now we can pass this in here。 So now we can say our wine data set gets the transform。Transform。Equals。To Tenz are。![](img/57a6f303b8d13bb7d856025a14ce5b5e_34.png)

Which is a function。And。Now， let's have a look at this。 So let's get the first item。 So let's say first data equals data set of index 0。 and then let's unpick our data， so。First data。 So let's say features and labels equals first data。 And now let's print the type。Of the features and also the type of the labels。 So now if we run this。

 then we should see this is now of class torch Tenor。 And if we don't pass this in here。 So if you say this is none。 No transform， then we see that it's still a nuy and D array。 So this is how we write our own Tenor， our own transform and then apply it for our own data set。

![](img/57a6f303b8d13bb7d856025a14ce5b5e_36.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_37.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_38.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_39.png)

And now let's write， for example， another custom transform。 So let's call this mule transform。 So a multiplication。 And here we implement the init method。 So this has self。 and this has a factor argument。 So here we store this self dot factor equals factor。 And then again。 we must implement the double underscore call function or call method。

 which gets self and this sample。![](img/57a6f303b8d13bb7d856025a14ce5b5e_41.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_42.png)

And here again， let's unpack our samples。 So let's say inputs and。Inputs and target equal sample。 And then let's only apply the factor to our features。 So let's say， inputs。Time is multiplied by our self dot factor。And now let's return our inputs。 our modified inputs and our target still as a tuple。



![](img/57a6f303b8d13bb7d856025a14ce5b5e_44.png)

And so this is the multiplication transform。 And now。Let's apply this。 So let's apply a。![](img/57a6f303b8d13bb7d856025a14ce5b5e_46.png)

And let's say a comp transform in this case， to see how we can use this。![](img/57a6f303b8d13bb7d856025a14ce5b5e_48.png)

So。Let's say composed equals。 And here we need torch vision dot transforms， dot compose。 And here we put in a list of our transforms。 So here first， we want to have totenor。 And then we want to have mal transform。![](img/57a6f303b8d13bb7d856025a14ce5b5e_50.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_51.png)

And。Let's say， so this needs a factor。 So let's say multiplied by 2。 And now let's create a new data set equals wine data set。 which gets the transform equals our comp transform。![](img/57a6f303b8d13bb7d856025a14ce5b5e_53.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_54.png)

Composed， and now again， let's get this。 So get or let's just copy this from here。![](img/57a6f303b8d13bb7d856025a14ce5b5e_56.png)

And run this to see if this is working。![](img/57a6f303b8d13bb7d856025a14ce5b5e_58.png)

So now here we have a Tenzoa。 and let's also have a look at the。 So let's print。![](img/57a6f303b8d13bb7d856025a14ce5b5e_60.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_61.png)

The features。And here， also， print the features。![](img/57a6f303b8d13bb7d856025a14ce5b5e_63.png)

To see if the multiplication got applied。 So here now we should see that each value got doubled。![](img/57a6f303b8d13bb7d856025a14ce5b5e_65.png)

And now let's use another factor。 So let's multiply it by4 and run this。 And now we should see that each of the value should now be multiplied by 4。![](img/57a6f303b8d13bb7d856025a14ce5b5e_67.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_68.png)

And yeah， so this is how we can use the transform for our data sets。 and it's very useful。![](img/57a6f303b8d13bb7d856025a14ce5b5e_70.png)

Yeah， most of the time you see the conversion transform to Tensor。 but also a lot of times when we work with images， you might see some of them。![](img/57a6f303b8d13bb7d856025a14ce5b5e_72.png)

![](img/57a6f303b8d13bb7d856025a14ce5b5e_73.png)

So， yeah， please check that out on the documentation website。 and I hope you like this tutorial。 Please subscribe to the channel and see you next time， bye。![](img/57a6f303b8d13bb7d856025a14ce5b5e_75.png)