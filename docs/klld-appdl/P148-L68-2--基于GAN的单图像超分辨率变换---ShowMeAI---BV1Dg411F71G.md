# P148：L68.2- 基于GAN的单图像超分辨率变换 - ShowMeAI - BV1Dg411F71G

Let's move on now let's go back to applications i'm going to go back to what there is trying GN and try to improve it。

 but for now let's see an application another application of GNs let's say you have an image this is low resolution and then you want to make it high resolution again what is the problem set up this is going to be a one to many example you have one example but then there could be many good high resolution versions of this this is an illpost problem there is not a unique answer to this problem okay once an image is downs sampleampled it is downsampled forever the information is gone but you want to make it you might you want to have a mapping from a low dimensional image to a high dimensional image and then you wanted to make to look realistic for instance if you use by cubic interpolation that's going to give you an image it is going to be very。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_1.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_2.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_3.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_4.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_5.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_6.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_7.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_8.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_9.png)

Larry， if you use neural networks without any GNs it's going to give you some better performance。

 but it still it's not perfect， but then you have this neural network here super resolution G and you can see that it is actually imagining some parts it is for instance here it's imagining some details it's not the exact details in your original image but it doesn't look bad okay it's going to give you those fine details so what is the math behind this you're gonna have a high resolution superre image this is coming out of your neural network so ISR is the output of your neural network is the output of your generator ILr is the low resolution input image and IHR is the ground truth So you have a high resolution counterpart of ILR so these are your data This is the output of your network the cool thing about super resolution is。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_11.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_12.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_13.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_14.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_15.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_16.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_17.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_18.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_19.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_20.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_21.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_22.png)

You can generate as many data as you want how you take a high resolution image。

 this is your original image， you put a Gaussian， you push it through a Gaussian filter。

 it's going to make things blurry and then you down samplele rather than saving all of the pixels you're going to subsample your pixels and you're going to downs sampleample by a factor of R by a factor of two。

 three， four etc and that's going to give you a lot of data as soon as you know your higher resolution image you can generate the low resolution image on the fly so it can have a lot of data。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_24.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_25.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_26.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_27.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_28.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_29.png)

Let's say sees the number of color channels let's say three channels red green blue for your images then the low resolution image is going to have doubleu times H pixelels and each one is going to have three channels red green blue so that's your low resolution what's going happen to the high resolution and the superre images theyre going to have a higher resolution it's going to be two times bigger or three times bigger or four times bigger you're gonna have more pixels you're going put a generator this is going to be conditional yourre conditioning on the low result image and then you are outputting a higher resolution image that's your generator how do you train it the neural network structure is going be a bunch of residual connections Okay that one we cover in part one of the course and that's where we saw this result but we don't worry about the neural network structure here so you just have a neural network a bunch of convolution。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_31.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_32.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_33.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_34.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_35.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_36.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_37.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_38.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_39.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_40.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_41.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_42.png)

run networks with some shortcuts that's going to give you a high resolution。

 That's the underlying ground truth。 This is the output of your generator now you want to learn these parameters the question is what is your last function What last function are you going to use and this is where we are going get creative Our loss function could come out of a discriminator if you're using the original again if you're using bus is trying again this could be a cr So whatever that you do you're going to end up with a loss function as soon as you learn your discriminator you're gonna to know your loss function because then you're going to use that discriminator and try to fool it okay and it is discriminating between highre images the original images and the generated images coming out of this generator So for this objective theta G is known and you're maximizing with respect theta D and that's going to give you your last function Okay perfect。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_44.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_45.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_46.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_47.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_48.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_49.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_50.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_51.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_52.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_53.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_54.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_55.png)

Now we are going to play around with this loss loss of super resolution and you're going to have a lot of flexibility here X is an unknown and i'm going to tell you what that is these part is they generated adversarial loss coming out of your discriminator and then you can add the two with some hyperparameter okay so what is this what is this content loss and don't worry about this perceptual loss i'm going to tell you what that is。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_57.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_58.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_59.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_60.png)

For this guy you can use a minus squared error loss What's going to happen is that youre going to look at the peak cells of the highred image and the peak cells of the generated image you are going to subtract them from each other square them do a summation all of those peak cells and then find the average divide by the total number of pixel cellss that's a minus squared error loss and MSE is an example of these x here equivalently rather than looking at the peak cells of the original image you can look at the peak cells of some hidden layer or some hidden unit inside your neuraln network so let's say you' are gonna pick some pre-trained neuraln network and that's going to be VGG it's a pre-trained neural network you can just load it fix the parameters and that VGG network is really good at classifying and it is trained on image net now you can go ahead push your。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_62.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_63.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_64.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_65.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_66.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_67.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_68.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_69.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_70.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_71.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_72.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_73.png)

age through this neuraln network and a stop at some layer and at that layer you're going to look at the pixels and you're gonna to have a minus squared error on that layer Why are we doing this because we want our images to look perceptly similar you don't want it to be similar at the pixel level you want your images to have similar meanings and this is a way of incorporating those meanings now I'm sure you're asking what is I and J phi I and J is actually your network and you're cutting your network at the J is convolution this is after the activation so this is after value and before doing any max pooling so you're going this is the output of your network after the Jsconvolution this is going give you J and before the I max pullinging so you're going to stop there and then you're going to compare the features and this is supposedly going to give you the meaning of an image。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_75.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_76.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_77.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_78.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_79.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_80.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_81.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_82.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_83.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_84.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_85.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_86.png)

You don't care about single every single pixel in your image。

 you care about that this image corresponds to a person， for instance， it has a meaning。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_88.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_89.png)

So that's another realization of x X could be MSE X could be VGG and for the super resolution the generator we are going to use this objective here your d is fixed and you're learning your generator and this is the original Gs objective Okay perfect in terms of your neural network structure I don't want to go into details of the neural network structure here but you are going to take a lower resolution image and then you are going to do a bunch of convolutions this is a convolution with a kernel size of9 and then you are going to have 64 filters these are the output filters and then you are going have a straight of one this is the first convolution Pre is parametric value it's very similar to leak key value where the leak parameter is free you can learn it from one iteration to the next iteration it's going to get optimized then you're going have a bunch of residual。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_91.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_92.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_93.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_94.png)

Connections and residual blocks convolution batch norm T value convolution batch norm and then here is where your residual connection is going to come in this is the kernel size this is the number of output channels straight of one and then you keep repeating the same pattern one times two times three times and four times you put a bunch of other convolutions and batch norm you're going to put a residual connection because it is easier to learn the difference between a low result image and a high result image rather than learning the entire function because the low result image is very similar to the original image and you are just learning the modifications and that's the intuition behind these shortcuts you do a bunch of other convolutions and then in the end you get your superre image your discriminator is going to take as input images they are either fake or real and it's going to output the probability of it being fake or real okay we。

Deffined our data set。 so that's our data set。 how that's how you're going to get your data。

 We defined our set of priors or prior assumptions。 These are our neural networks。 This is our model。

 This is our last function。Wwhich is going to help you optimize these two neural networks。

 the discriminator and the generator and now how you're going to evaluate them you are going to evaluate them there are no good metrics for higher resolution images or this problem super resolution these are some metrics that you can learn about them are you can just Google them and take a look at the Wikipedia page their definitions are very simple for instance the signal to noise ratio is very correlated to the MSE loss that you have out there it's basically the same formula you're changing the furniture rearranging the furniture a little bit mean opinion score is coming out of showing these generated images to human evaluators maybe you're going to use Amazon torque and then they are going to say okay this image looks more realistic it looks better and then you count the number of people who gave you a better score and that's how you're going to compare two methods。

Maybe SRRSNe versus SRgan and there is another metric as I am that you can learn about on your own okay any questions about this this is really smart using we learned that you can use a pre-trained neural network to come up with a metric for measuring the quality of generated images and that was giving you the inception score now you're using a pre-trained network in this case VGG to give you a loss function this are a smart observations okay now that you did a lot of work and you pretrained a neural network can you use it somehow and this is one of the ways that you can use that going give you a new loss function so it's very similar to the loss function that is coming here out of your discriminator this is again another neural network it is not pretrained but then you' are training it on the fly to give you your loss function。

