# P151：L69.2- GAN的渐进学习 - ShowMeAI - BV1Dg411F71G

Okay in that case let's move on and let's go back to some applications so far I'm sure you have noticed that most of the images that we were working with where low resolution when it came to GNs and there is a reason for that because it wasn't converging so we saw 64 by 64 we saw 256 by 256 but these are low resolution can we increase the resolution to something that is 1024 like this and generate high quality images that's the objective you want to generate high quality images one might say that okay just write down your framework create your neural network one is a generator it's going to take a latent variable it's going to take a vector it's going to first create  four by four features and then you're going keep using transpo convolutions until you get to the order of 1000。



![](img/16e8c43192da54bc373ca28918b993ae_1.png)

![](img/16e8c43192da54bc373ca28918b993ae_2.png)

![](img/16e8c43192da54bc373ca28918b993ae_3.png)

![](img/16e8c43192da54bc373ca28918b993ae_4.png)

![](img/16e8c43192da54bc373ca28918b993ae_5.png)

![](img/16e8c43192da54bc373ca28918b993ae_6.png)

24 by 1024 That's your generator Give the generated image and the real image to a discriminator and then this discriminator is gonna give you a single number and do your optimization on that theoretically beautiful once you sit behind the computer youre write down this model and it's not going to converge it's not going to give you images or it's not going give you high quality images So this is one of those papers that it's not about the last function it's not about your neural network structure it's about how you train it so you have to gradually train this neural network step by step whatever you gonna do first you generate four by four images So very low resolution images they're going to look like this This is four by four you're going to generate four by four images。

 your real images you're gonna downsample them。 you're going to make them look four by four and then you give that to a discriminator and then you。



![](img/16e8c43192da54bc373ca28918b993ae_8.png)

![](img/16e8c43192da54bc373ca28918b993ae_9.png)

![](img/16e8c43192da54bc373ca28918b993ae_10.png)

![](img/16e8c43192da54bc373ca28918b993ae_11.png)

![](img/16e8c43192da54bc373ca28918b993ae_12.png)

![](img/16e8c43192da54bc373ca28918b993ae_13.png)

![](img/16e8c43192da54bc373ca28918b993ae_14.png)

![](img/16e8c43192da54bc373ca28918b993ae_15.png)

![](img/16e8c43192da54bc373ca28918b993ae_16.png)

![](img/16e8c43192da54bc373ca28918b993ae_17.png)

![](img/16e8c43192da54bc373ca28918b993ae_18.png)

ra that then you need to somehow move to the next step and gradually add convolution deconvolutions and convolutions and then look at8 by8 versions of your images train that train those parameters and then these parameters are the same parameters as before you're adding new parameters here you're adding new convolutions and youcap you keep adding it one after another and that's why you have the progressive growing so you're growing your generative neural network this is beautiful but things are this discontinuous when you go from one step to the next one you cannot just plug in。



![](img/16e8c43192da54bc373ca28918b993ae_20.png)

![](img/16e8c43192da54bc373ca28918b993ae_21.png)

![](img/16e8c43192da54bc373ca28918b993ae_22.png)

![](img/16e8c43192da54bc373ca28918b993ae_23.png)

![](img/16e8c43192da54bc373ca28918b993ae_24.png)

![](img/16e8c43192da54bc373ca28918b993ae_25.png)

![](img/16e8c43192da54bc373ca28918b993ae_26.png)

A new convolution because it's gonna to confuse the training process you want things to happen gradually you want to go from this step to the next step somehow gradually and the way that you're going to do it is let's say you are now at pixel level16 by 16 so now that's your resolution and you want to go to 32 by 32 Sam thing is happening here from4 by4 you are going to 8 by8 so you're doubling the resolution This is this a step the first step that you have here you have a 16 by 16 and by the way this is going to be 16 by 16 by for instance 512 theyre not going be three channels here it's going to be 512 you're going to use one by one convolutions which are just pixel by pixel matrix multiplications to turn the 512 channels to three channels red green and blue so wherever you see two RGB is just the one。



![](img/16e8c43192da54bc373ca28918b993ae_28.png)

![](img/16e8c43192da54bc373ca28918b993ae_29.png)

![](img/16e8c43192da54bc373ca28918b993ae_30.png)

![](img/16e8c43192da54bc373ca28918b993ae_31.png)

![](img/16e8c43192da54bc373ca28918b993ae_32.png)

![](img/16e8c43192da54bc373ca28918b993ae_33.png)

![](img/16e8c43192da54bc373ca28918b993ae_34.png)

![](img/16e8c43192da54bc373ca28918b993ae_35.png)

![](img/16e8c43192da54bc373ca28918b993ae_36.png)

![](img/16e8c43192da54bc373ca28918b993ae_37.png)

![](img/16e8c43192da54bc373ca28918b993ae_38.png)

![](img/16e8c43192da54bc373ca28918b993ae_39.png)

by one convolution changing the dimension from 512 to3 and it pixel Y each pixel is going to use the same weights Each pixel here is 512 dimensional you're gonna multiply it by matrix that is 512 by3 and that's going to give you a 16 by 16 image in red green and blue you do the same thing here that is also a one by one convolution so that's your generator that's your discriminator now you want to increase the resolution to go to 32 by 32 The first step you're going to do a nearest neighbor filtering so you're just copying and pasting the same pixel value in four locations because each pixel in this image is going to turn into four pixels in the next image in the up sample one so you're just going to copy and paste and that's nearest neighbor filtering you're going do a convolution and that's going to give you a 32 by 32 with some number of channels but let's forget about this route for。



![](img/16e8c43192da54bc373ca28918b993ae_41.png)

![](img/16e8c43192da54bc373ca28918b993ae_42.png)

![](img/16e8c43192da54bc373ca28918b993ae_43.png)

![](img/16e8c43192da54bc373ca28918b993ae_44.png)

![](img/16e8c43192da54bc373ca28918b993ae_45.png)

![](img/16e8c43192da54bc373ca28918b993ae_46.png)

![](img/16e8c43192da54bc373ca28918b993ae_47.png)

![](img/16e8c43192da54bc373ca28918b993ae_48.png)

![](img/16e8c43192da54bc373ca28918b993ae_49.png)

![](img/16e8c43192da54bc373ca28918b993ae_50.png)

![](img/16e8c43192da54bc373ca28918b993ae_51.png)

Second let's set alpha to be zero what's going to happen you take a 16 by 16 image。

 you do nearest neighbor filtering and then you turn it into red green blue so this is basically the same operation here so it's the same network and you' are not adding any new parameters so the only thing that you're adding is nearest neighbor filtering so you're just copying and pasting so nothing happens there。



![](img/16e8c43192da54bc373ca28918b993ae_53.png)

![](img/16e8c43192da54bc373ca28918b993ae_54.png)

![](img/16e8c43192da54bc373ca28918b993ae_55.png)

![](img/16e8c43192da54bc373ca28918b993ae_56.png)

So this route is exactly this route here same thing down there you start with a 32 by 32 image。

 you downsample it， then you turn it into red green blue and if alpha is zero this is exactly this framework here it's exactly the same neural network you're just adding downs which is average pulling so you take four pixels and then you average them into one pixel and the other one is just nearest neighbor filtering so it's exactly this route if alpha is zero but then during training the same way that you can have a learning rate schedule you can have a schedule for alpha you continuously change it from alpha being zero to alpha being one if alpha is one then you're forgetting that route gradually and then you're gonna be in the route that is giving you the next resolution so now this is the way that you're going to progressively grow yourgans so once alpha。



![](img/16e8c43192da54bc373ca28918b993ae_58.png)

![](img/16e8c43192da54bc373ca28918b993ae_59.png)

![](img/16e8c43192da54bc373ca28918b993ae_60.png)

![](img/16e8c43192da54bc373ca28918b993ae_61.png)

![](img/16e8c43192da54bc373ca28918b993ae_62.png)

![](img/16e8c43192da54bc373ca28918b993ae_63.png)

![](img/16e8c43192da54bc373ca28918b993ae_64.png)

![](img/16e8c43192da54bc373ca28918b993ae_65.png)

![](img/16e8c43192da54bc373ca28918b993ae_66.png)

![](img/16e8c43192da54bc373ca28918b993ae_67.png)

![](img/16e8c43192da54bc373ca28918b993ae_68.png)

![](img/16e8c43192da54bc373ca28918b993ae_69.png)

pha is one you forget the previous route and you are now in the route ready for the next step and that's going to give you this framework but these are engineering papers see a lot of experimentation is going to go on on how to use alpha so there is no mathematical theory for how to change alpha perfect so not only you need to do that the way that you train your neural network we saw this observations so for this I'm going to go back to this is slide here。

 this one we cover just as a reminder do you remember mini batch discrimination and we had to do that to deal with modco and we wanted our observations to look at the other observations in a mini batch so not only look at yourself but look at the look at your neighbors and maybe that's going to help you pull out of more collapse the question is is there a simpler way of achieving the same objective or at least similar results。



![](img/16e8c43192da54bc373ca28918b993ae_71.png)

![](img/16e8c43192da54bc373ca28918b993ae_72.png)

![](img/16e8c43192da54bc373ca28918b993ae_73.png)

![](img/16e8c43192da54bc373ca28918b993ae_74.png)

![](img/16e8c43192da54bc373ca28918b993ae_75.png)

![](img/16e8c43192da54bc373ca28918b993ae_76.png)

Let's say you are sitting at this location。 This is going to be 4 by4 by 512。

 So each pixel is going to be。

![](img/16e8c43192da54bc373ca28918b993ae_78.png)

![](img/16e8c43192da54bc373ca28918b993ae_79.png)

512 dimensional and that's your batch This is where the batch is going to come in So n is your mini batch the size of your mini batch and that's your feature map。

 what we are going to do is going to take an average over the data so I is the index for the data F is the index for the channels x and y are the indexdices for the pixels you compute the mean and standard deviation of your mini batch up until this point it is similar to batch normalization but now we are going to use these staistic in a different way。

 we are going take that and average it over all of your channels over all of your pixels so you are doing an averaging on that and then youre just going to this formula here is just telling you that the first 512 feature maps you are going to keep them the same so it's an identity but then you are concatenating this z value basically are broadcasting it。



![](img/16e8c43192da54bc373ca28918b993ae_81.png)

![](img/16e8c43192da54bc373ca28918b993ae_82.png)

![](img/16e8c43192da54bc373ca28918b993ae_83.png)

![](img/16e8c43192da54bc373ca28918b993ae_84.png)

![](img/16e8c43192da54bc373ca28918b993ae_85.png)

![](img/16e8c43192da54bc373ca28918b993ae_86.png)

![](img/16e8c43192da54bc373ca28918b993ae_87.png)

![](img/16e8c43192da54bc373ca28918b993ae_88.png)

![](img/16e8c43192da54bc373ca28918b993ae_89.png)

![](img/16e8c43192da54bc373ca28918b993ae_90.png)

![](img/16e8c43192da54bc373ca28918b993ae_91.png)

And then're concatenating it channel wise Now y if x was n by 512 by 4 by4 y is going be n by 513 by4 by four so this is a way for you to look at your neighbors to look at the statistics of your neighbors and it turns out that this is going to help you deal with modcos slightly another feature is how you initialize your neural network so in part one of the course we go through a paper。

 it's a theoretical paper and it tells us how to properly initialize convolutional neuro network when you have as your activation and the initialization scheme is the paper is by climbing he it's called delving deep into rectifiers it's by climbing he and the scheme the initialization scheme is called climbing initialization。



![](img/16e8c43192da54bc373ca28918b993ae_93.png)

![](img/16e8c43192da54bc373ca28918b993ae_94.png)

![](img/16e8c43192da54bc373ca28918b993ae_95.png)

![](img/16e8c43192da54bc373ca28918b993ae_96.png)

![](img/16e8c43192da54bc373ca28918b993ae_97.png)

![](img/16e8c43192da54bc373ca28918b993ae_98.png)

![](img/16e8c43192da54bc373ca28918b993ae_99.png)

![](img/16e8c43192da54bc373ca28918b993ae_100.png)

![](img/16e8c43192da54bc373ca28918b993ae_101.png)

![](img/16e8c43192da54bc373ca28918b993ae_102.png)

![](img/16e8c43192da54bc373ca28918b993ae_103.png)

Because the first author is timing but how we're going to initialize it。

 it turns out that the number of channels that you have for your convolutions and your filter size matters where each layer you're going to have a different filter size。

 you're going to have different channel dimension， you're going to create an n which is k is squared by D and then you' are going to create C sees the inverse of your standard deviation that you're going to use to initialize your weights and then this is how you' are going to initialize your weights you're going to sample from normal distribution and then you' are going to divide those values by C。



![](img/16e8c43192da54bc373ca28918b993ae_105.png)

![](img/16e8c43192da54bc373ca28918b993ae_106.png)

![](img/16e8c43192da54bc373ca28918b993ae_107.png)

![](img/16e8c43192da54bc373ca28918b993ae_108.png)

![](img/16e8c43192da54bc373ca28918b993ae_109.png)

![](img/16e8c43192da54bc373ca28918b993ae_110.png)

![](img/16e8c43192da54bc373ca28918b993ae_111.png)

And if your variables， if what you are optimizing over is W hat I and if you are using a stochastic gradient decentcent or Aldam optimization。

 it could happen that for some layers and some weights your learning rate is too big and for some layers and some weights your learning rate is too small so you're going to have a learning rate that is at the same time big and small and that could be the reason that your neural network is not converging properly so they say that in this paper rather than your parameters being W hats let your parameters be w and then these are just some other layers in your your neural network so you' are just dividing by C Now if all of your variables are coming from a normal that is0 and1 they're going to have the same scale therefore their learning rate is going to be equalized so it's not the case that for some of the variables。



![](img/16e8c43192da54bc373ca28918b993ae_113.png)

![](img/16e8c43192da54bc373ca28918b993ae_114.png)

![](img/16e8c43192da54bc373ca28918b993ae_115.png)

![](img/16e8c43192da54bc373ca28918b993ae_116.png)

![](img/16e8c43192da54bc373ca28918b993ae_117.png)

![](img/16e8c43192da54bc373ca28918b993ae_118.png)

![](img/16e8c43192da54bc373ca28918b993ae_119.png)

![](img/16e8c43192da54bc373ca28918b993ae_120.png)

![](img/16e8c43192da54bc373ca28918b993ae_121.png)

![](img/16e8c43192da54bc373ca28918b993ae_122.png)

![](img/16e8c43192da54bc373ca28918b993ae_123.png)

![](img/16e8c43192da54bc373ca28918b993ae_124.png)

Your learning rate is too big and for some of them is too small so that's another trick for how you train your neural network another trick is pixel wise feature vector normalization so the first paper that generated deep learning as we know it today was the paper by Jeffrey Hinton in 2012 and they were using local response normalization in that paper we know that normalization is important and they were using a typical version of normalization called local response but then batch normalization came and then people stopped using local response normalization because batch normalization was enough for classification but it turns out that for Gs and for generation actually local response normalization helps and it's better than batch normalization so what is the idea of local response normalization this is a simplified version of that but。



![](img/16e8c43192da54bc373ca28918b993ae_126.png)

![](img/16e8c43192da54bc373ca28918b993ae_127.png)

![](img/16e8c43192da54bc373ca28918b993ae_128.png)

![](img/16e8c43192da54bc373ca28918b993ae_129.png)

![](img/16e8c43192da54bc373ca28918b993ae_130.png)

![](img/16e8c43192da54bc373ca28918b993ae_131.png)

![](img/16e8c43192da54bc373ca28918b993ae_132.png)

![](img/16e8c43192da54bc373ca28918b993ae_133.png)

![](img/16e8c43192da54bc373ca28918b993ae_134.png)

![](img/16e8c43192da54bc373ca28918b993ae_135.png)

![](img/16e8c43192da54bc373ca28918b993ae_136.png)

![](img/16e8c43192da54bc373ca28918b993ae_137.png)

The idea if the activity of one of these features or one of these channels。

 J is counting the channel， if the activity of one of your channels increases the activity of this channel here should increase as well if this is channel I if the activity of one of the channel Js increases to compensate for that and to have the same level of activity。

 the activity of channel I should increase as well so this is a way of creating competition between activities of your neural network。



![](img/16e8c43192da54bc373ca28918b993ae_139.png)

![](img/16e8c43192da54bc373ca28918b993ae_140.png)

![](img/16e8c43192da54bc373ca28918b993ae_141.png)

![](img/16e8c43192da54bc373ca28918b993ae_142.png)

![](img/16e8c43192da54bc373ca28918b993ae_143.png)

![](img/16e8c43192da54bc373ca28918b993ae_144.png)

![](img/16e8c43192da54bc373ca28918b993ae_145.png)

We know that convolutions are going to look at your pixels X and y in a local manner so the near the neighboring pixels are going to have impact on each other。

 but then the channels are independent This is one way of creating competition across channels so that your channels are talking to each other as well and at the same time it is normalizing so these values are not going to get too big or too small so these trick is coming back for gamess So what are what loss function are you're going to use in the end you have multiple options you can use the loss function from。



![](img/16e8c43192da54bc373ca28918b993ae_147.png)

![](img/16e8c43192da54bc373ca28918b993ae_148.png)

![](img/16e8c43192da54bc373ca28918b993ae_149.png)

![](img/16e8c43192da54bc373ca28918b993ae_150.png)

![](img/16e8c43192da54bc373ca28918b993ae_151.png)

![](img/16e8c43192da54bc373ca28918b993ae_152.png)

![](img/16e8c43192da54bc373ca28918b993ae_153.png)

The vast stream cans type of loss functions， or you can do the least square cans type of loss function。

 So these two papers we cover they are low resolution。

 either of them are going to do fine and you can increase that to high resolution So these are now higher resolution images and you can see that they look much better and these are generated images and these are also generated images here and they are 1024 by 1024 Okay any questions。

Is everything clear， okay？