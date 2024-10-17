# P66：L32.1- 扩张卷积 [续] - ShowMeAI - BV1Dg411F71G

So last session， we covered the lab， and we started covering。

Context aggregation because context matters when you want to do semantic segmentation。



![](img/16a526f250132a598f8fe3512f20b048_1.png)

And this paper is nice because it's going to give us a new perspective on convolutions as well and it should be able to help us put the pieces of the puzzle together because we know about convolutions and convolutions have been around I don't know things forever so there are not something new but how are they related to the convolutions that we see in computer vision these paper is going to give us the mathematical formula so you can think of your images as functions you can think of your kernels as functions and you can convolve them and you can introduce dilated convolutions and for this paper it's very important for them to make a distinction between mind terminology some people use as convolutions some people use dilated convolutions。



![](img/16a526f250132a598f8fe3512f20b048_3.png)

![](img/16a526f250132a598f8fe3512f20b048_4.png)

![](img/16a526f250132a598f8fe3512f20b048_5.png)

![](img/16a526f250132a598f8fe3512f20b048_6.png)

![](img/16a526f250132a598f8fe3512f20b048_7.png)

![](img/16a526f250132a598f8fe3512f20b048_8.png)

![](img/16a526f250132a598f8fe3512f20b048_9.png)

![](img/16a526f250132a598f8fe3512f20b048_10.png)

![](img/16a526f250132a598f8fe3512f20b048_11.png)

Some people use convolutions with holes， et cea。That's okay you're going to see that in different papers but if you want to be precise dilated convolutions is the correct name because originally it was Ats it was an algorithm it's the name of an algorithm and it was for vlet decomposition but and they were using dilated convolutions so probably a better terminology is dilated convolutions rather than at convolutions but it's not a big deal it's just terminology potato potatota it doesn't matter that much but the cool thing is that you can use dilated convolutions to support exponentially expanding receptive fields which is nice and the way you do it you're gonna start working with powers of two as your dilation factor or dilation rate。



![](img/16a526f250132a598f8fe3512f20b048_13.png)

![](img/16a526f250132a598f8fe3512f20b048_14.png)

![](img/16a526f250132a598f8fe3512f20b048_15.png)

![](img/16a526f250132a598f8fe3512f20b048_16.png)

![](img/16a526f250132a598f8fe3512f20b048_17.png)

![](img/16a526f250132a598f8fe3512f20b048_18.png)

![](img/16a526f250132a598f8fe3512f20b048_19.png)

![](img/16a526f250132a598f8fe3512f20b048_20.png)

![](img/16a526f250132a598f8fe3512f20b048_21.png)

![](img/16a526f250132a598f8fe3512f20b048_22.png)

![](img/16a526f250132a598f8fe3512f20b048_23.png)

And you're going to keep convolving with three by three filters。

 and this is going to enable you to have a very large receptive field。

 And this is a precise definition of what a receptive field is any pixel in your original image that's affecting。



![](img/16a526f250132a598f8fe3512f20b048_25.png)

![](img/16a526f250132a598f8fe3512f20b048_26.png)

The current pixel in your current layer through do some computations。

 that's going to be part of your receptive field and when you do powers of two。



![](img/16a526f250132a598f8fe3512f20b048_28.png)

![](img/16a526f250132a598f8fe3512f20b048_29.png)

You're going to end up with the size of your receptive field exponentially growing the deeper you go。

 the size of the receptive field is gonna grow exponentially and last session we started discussing this and we have some discussions over what this figure means I think it's better to think about it this way。

 These red points are the points that are directly affecting the current pixel in your current layer and these nine points are the ones that are affecting the center point in your next layer and the dilation factor originally is zero is two to the power zero that's going be a one So that's just a three by three convolution and that's going to be your receptive field Now you have a convolution with a dilation factor of two for the next layer and this is a di So these nine points the red ones are going to affect a single points in the next layer and each one of these points have a receptive field。



![](img/16a526f250132a598f8fe3512f20b048_31.png)

![](img/16a526f250132a598f8fe3512f20b048_32.png)

![](img/16a526f250132a598f8fe3512f20b048_33.png)

![](img/16a526f250132a598f8fe3512f20b048_34.png)

![](img/16a526f250132a598f8fe3512f20b048_35.png)

![](img/16a526f250132a598f8fe3512f20b048_36.png)

![](img/16a526f250132a598f8fe3512f20b048_37.png)

![](img/16a526f250132a598f8fe3512f20b048_38.png)

![](img/16a526f250132a598f8fe3512f20b048_39.png)

![](img/16a526f250132a598f8fe3512f20b048_40.png)

![](img/16a526f250132a598f8fe3512f20b048_41.png)

![](img/16a526f250132a598f8fe3512f20b048_42.png)

of three by three because of what we just discovered from the previous layer So these ones are gonna to have receptive fields of three by three and the original the final receptive field is going be this in the original image Now let's go to dilation factor of four two to the power2 So these points are going be four pixels apart and these nine red pixels in this layer are going to affect one pixel in the next layer and each one of them have a receptive field of this speak and that's coming from panel B of this figure So each one have a receptive field of that size and if you put everything together the original receptive the final receptive field of these operations is going be bigger and it's growing exponentially and then we move on to context network architecture So what network architecture are they using the first two。



![](img/16a526f250132a598f8fe3512f20b048_44.png)

![](img/16a526f250132a598f8fe3512f20b048_45.png)

![](img/16a526f250132a598f8fe3512f20b048_46.png)

![](img/16a526f250132a598f8fe3512f20b048_47.png)

![](img/16a526f250132a598f8fe3512f20b048_48.png)

![](img/16a526f250132a598f8fe3512f20b048_49.png)

![](img/16a526f250132a598f8fe3512f20b048_50.png)

![](img/16a526f250132a598f8fe3512f20b048_51.png)

![](img/16a526f250132a598f8fe3512f20b048_52.png)

![](img/16a526f250132a598f8fe3512f20b048_53.png)

![](img/16a526f250132a598f8fe3512f20b048_54.png)

Layers are going to have a dilation factor of one and then the dilation is gonna be powers of two and you're gonna have two architectures in terms of your channel size。

 One is the basic where the channel sizes are the same and the other one has channel size is being different but then it's a matter of training this network and when they trained it when they set behind the computer and they trained it the network didn't converge and it had to do with the way that you have to initialize your network so initialization matters you can use identity initializations for your filters and apparently that solved the problem because now you're taking your image and initially during the initial phase of your training。

 you are just pushing your image to the end it's just the identity map and we know that identity helps we saw that in residual network paper resnets so it's trying to be at least initially similar to a residual network and then later on depart from it。



![](img/16a526f250132a598f8fe3512f20b048_56.png)

![](img/16a526f250132a598f8fe3512f20b048_57.png)

![](img/16a526f250132a598f8fe3512f20b048_58.png)

![](img/16a526f250132a598f8fe3512f20b048_59.png)

![](img/16a526f250132a598f8fe3512f20b048_60.png)

![](img/16a526f250132a598f8fe3512f20b048_61.png)

![](img/16a526f250132a598f8fe3512f20b048_62.png)

![](img/16a526f250132a598f8fe3512f20b048_63.png)

![](img/16a526f250132a598f8fe3512f20b048_64.png)

![](img/16a526f250132a598f8fe3512f20b048_65.png)

![](img/16a526f250132a598f8fe3512f20b048_66.png)

![](img/16a526f250132a598f8fe3512f20b048_67.png)

Based on the training， how the training goes， This is where the basic architecture。

 if your architecture is having different channels from one layer to the next one like from here to here and from here to the next one then you cannot use this identity mapping anymore。

 it's gonna be a little bit more complex to initialize and to come up with identity initializations or as close as possible to identity and this is just the generalization of the formula as you see up there and to see that C and C plus one are the number of channels number of filter maps in two consecutive layers。

 So for instance， it's gonna to be 8c and 16 C。 and let's assume they are the same。

 let's say we are with the basic network for now and C is a number that's dividing both of them。

 So that's gonna be the common divisor and let's say C and C plus one are the same。

 So when you do the division you're gonna to get the one here C divided by that is going。



![](img/16a526f250132a598f8fe3512f20b048_69.png)

![](img/16a526f250132a598f8fe3512f20b048_70.png)

![](img/16a526f250132a598f8fe3512f20b048_71.png)

![](img/16a526f250132a598f8fe3512f20b048_72.png)

![](img/16a526f250132a598f8fe3512f20b048_73.png)

![](img/16a526f250132a598f8fe3512f20b048_74.png)

![](img/16a526f250132a598f8fe3512f20b048_75.png)

![](img/16a526f250132a598f8fe3512f20b048_76.png)

![](img/16a526f250132a598f8fe3512f20b048_77.png)

![](img/16a526f250132a598f8fe3512f20b048_78.png)

![](img/16a526f250132a598f8fe3512f20b048_79.png)

![](img/16a526f250132a598f8fe3512f20b048_80.png)

Give you A because these are the same and that's gonna to give you B。

 So that's gonna to give you the identity initialization。 So yes。

 it's a general formula compared to that one。 And there is a question for those A and B indices。

 we are assuming a flattened feature map， not really So you have two components to your kernel one is taking care of your pixels T。

 and if you remember T is a number is a pair of numbers from negative r to our it's a pair of integers So that's gonna to be your index and what we are saying is that on the diagonal of our image of our kernel we are setting up one then we are setting a bunch of zeros of diagonal and channel wise。

 these are gonna be matrices your kernels that are taking you from one dimension to the next one from dimension C to the next one and the diagonal of that matrix you have also the identity one Otherwise it's0 Yes。

 so。

![](img/16a526f250132a598f8fe3512f20b048_82.png)

![](img/16a526f250132a598f8fe3512f20b048_83.png)

![](img/16a526f250132a598f8fe3512f20b048_84.png)

![](img/16a526f250132a598f8fe3512f20b048_85.png)

![](img/16a526f250132a598f8fe3512f20b048_86.png)

![](img/16a526f250132a598f8fe3512f20b048_87.png)

![](img/16a526f250132a598f8fe3512f20b048_88.png)

![](img/16a526f250132a598f8fe3512f20b048_89.png)

![](img/16a526f250132a598f8fe3512f20b048_90.png)

![](img/16a526f250132a598f8fe3512f20b048_91.png)

![](img/16a526f250132a598f8fe3512f20b048_92.png)

![](img/16a526f250132a598f8fe3512f20b048_93.png)

Question is A B T or each dules T is a pair of numbers。

 pair of integers from negative R to R A is a scalar， B is a scalar these are。



![](img/16a526f250132a598f8fe3512f20b048_95.png)

![](img/16a526f250132a598f8fe3512f20b048_96.png)

Your matrix entries。

![](img/16a526f250132a598f8fe3512f20b048_98.png)

T is a tool ball A and BR scalrs or integers Does that answer your question It says here that that a is the index of the input feature map say it again right right here in the where your cursor is below it says a is the index of the input feature map and D is the index exactly so these are a scalrs and T is a pixel T is two dimensional a is one dimension because we have like multiple input feature maps in multiple output feature maps I think is exactly yes in a feature map is like an array basically your a matrix exactly so each feature map is a tensor it has a bunch of pixels and it has a number of channel but in the end you're going to get an identity out of this out of this can initially that's your initialization and you let it train what is the backbone or what is the front end of your network that's going be vG16 and your input or added images and。



![](img/16a526f250132a598f8fe3512f20b048_100.png)

![](img/16a526f250132a598f8fe3512f20b048_101.png)

![](img/16a526f250132a598f8fe3512f20b048_102.png)

![](img/16a526f250132a598f8fe3512f20b048_103.png)

![](img/16a526f250132a598f8fe3512f20b048_104.png)

![](img/16a526f250132a598f8fe3512f20b048_105.png)

![](img/16a526f250132a598f8fe3512f20b048_106.png)

![](img/16a526f250132a598f8fe3512f20b048_107.png)

![](img/16a526f250132a598f8fe3512f20b048_108.png)

![](img/16a526f250132a598f8fe3512f20b048_109.png)

![](img/16a526f250132a598f8fe3512f20b048_110.png)

![](img/16a526f250132a598f8fe3512f20b048_111.png)

're usings reflection padding like unit using and in the end you're going to get a lower resolution tensor with 21 channels because you have 21 classes in Askcal VC and then you have to increase the resolution go back to the original resolution and then you you do your prediction so there is an sampling going on after this layer and let's compare this to fully convolutional networks and with deep lab the previous late paper that we covered and deep lab multical multi scale images and with this front end and dilated convolutions constructed this way you are getting more context and because you have more context of the entire image you have a bigger field of view you can increase the intersection over unit that your metrics and qualitatively these are the type of。



![](img/16a526f250132a598f8fe3512f20b048_113.png)

![](img/16a526f250132a598f8fe3512f20b048_114.png)

![](img/16a526f250132a598f8fe3512f20b048_115.png)

![](img/16a526f250132a598f8fe3512f20b048_116.png)

![](img/16a526f250132a598f8fe3512f20b048_117.png)

Predictions that you're gonna get This is your front end if you add the context using dilated convolutions。

 you are able to get rid of some of these confusions that your network is making and when you add CRf。

 you're going to get better results and we know what CRf is we covered it last session is just a post processing step and you can compare it with the ground truth So these are really good predictions does that CRf was the CRf we talked about did that also include some RN or is this different the CRf no that one didn't include any R but you can include but whatever you do that's a post processing step and in terms of numbers front end your basic network。

 the large one is doing the best in terms of mean intersection or union if you add CRf you're going to add a little bit of improvement CRf we can apply to any。

The predictions of any network， so it's going to improve the prediction and any other questions before I move on to the nexty perfect。

