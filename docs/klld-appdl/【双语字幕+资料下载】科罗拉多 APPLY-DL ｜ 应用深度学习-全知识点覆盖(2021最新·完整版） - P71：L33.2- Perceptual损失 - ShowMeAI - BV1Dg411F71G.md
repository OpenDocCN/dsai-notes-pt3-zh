# P71：L33.2- Perceptual损失 - ShowMeAI - BV1Dg411F71G

okay let's move on to the next one now，the question is。



![](img/d3fb2049701e86ce38d2c5b59f58b928_1.png)

uh is l2 distance，or is mean squared error the correct，loss function。

what could be a better loss function so，in，uh for machine learning in general。

including deep learning。

![](img/d3fb2049701e86ce38d2c5b59f58b928_3.png)

you have four components data your model，your loss function and then your。

evaluation so we need to focus on the，loss function，because we know that convolutions are。



![](img/d3fb2049701e86ce38d2c5b59f58b928_5.png)

going to do a good job but maybe there，are some，improvements that you can make on the，loss function。



![](img/d3fb2049701e86ce38d2c5b59f58b928_7.png)

so let's see how we can do that so there，were some comments on the chat。

so i was reading that which is okay，sounds good so what is this perceptual，loss why is it。



![](img/d3fb2049701e86ce38d2c5b59f58b928_9.png)

performing so good if you look at it，this is the previous paper。



![](img/d3fb2049701e86ce38d2c5b59f58b928_11.png)

this is this paper and you're seeing，more of the details，of the shared of this tennis player。



![](img/d3fb2049701e86ce38d2c5b59f58b928_13.png)

that's one application，the other one is you can also use the，same framework。



![](img/d3fb2049701e86ce38d2c5b59f58b928_15.png)

type，you have an input image and then you。

![](img/d3fb2049701e86ce38d2c5b59f58b928_17.png)

want to translate this。

![](img/d3fb2049701e86ce38d2c5b59f58b928_19.png)

image to the style of uh the style image，that you started with so why is。



![](img/d3fb2049701e86ce38d2c5b59f58b928_21.png)

uh why are we looking for a different，loss function，for the mean squared error if you take。

your image。

![](img/d3fb2049701e86ce38d2c5b59f58b928_23.png)

you shift it one pixel to the right or，one pixel。

![](img/d3fb2049701e86ce38d2c5b59f58b928_25.png)

up one pixel down or one pixel to the，left you're gonna have a huge loss。

but we know that these two images are。

![](img/d3fb2049701e86ce38d2c5b59f58b928_27.png)

the same we just took it and push it one，pixel to the right。



![](img/d3fb2049701e86ce38d2c5b59f58b928_29.png)

so we need to look for a different way，of，enforcing the similarity between two。



![](img/d3fb2049701e86ce38d2c5b59f58b928_31.png)

images and the idea of this paper is，neat，is very neat you can actually。



![](img/d3fb2049701e86ce38d2c5b59f58b928_33.png)

use a pre-trained neural network like，vdg-16。

![](img/d3fb2049701e86ce38d2c5b59f58b928_35.png)

to give you the last function that you，want and actually we can。

use a neural network to give you a loss。

![](img/d3fb2049701e86ce38d2c5b59f58b928_37.png)

function and here，we are going to use vgd16 to give us the，loss function。



![](img/d3fb2049701e86ce38d2c5b59f58b928_39.png)

so we don't care about the neural，network structure，there is an input image you push it。



![](img/d3fb2049701e86ce38d2c5b59f58b928_41.png)

through a bunch of convolutions，and then you're going to output an，output image y hat。



![](img/d3fb2049701e86ce38d2c5b59f58b928_43.png)

and let's say you want to do style，transfer，you start with a style and then here if。



![](img/d3fb2049701e86ce38d2c5b59f58b928_45.png)

you're doing style transfer，yc is going to be x what you want to，have is。



![](img/d3fb2049701e86ce38d2c5b59f58b928_47.png)

x to be as close as possible to y hat，and then you push it through your vgg，network。

at some point you're gonna compare the。

![](img/d3fb2049701e86ce38d2c5b59f58b928_49.png)

outputs of those feature maps，and try to see how similar they are to。

each other similarly for this style you。

![](img/d3fb2049701e86ce38d2c5b59f58b928_51.png)

can stop at some layer，pick up the feature maps compare the，feature maps and that's going to give。

you a loss function，relu。

![](img/d3fb2049701e86ce38d2c5b59f58b928_53.png)

one the first value uh the second value，the third layer value etc。



![](img/d3fb2049701e86ce38d2c5b59f58b928_55.png)

and then you're gonna have a combination，of these loss function。



![](img/d3fb2049701e86ce38d2c5b59f58b928_57.png)

with some parameters some hyper，parameters that you're gonna choose。

and then you're gonna combine your loss，function according to that。



![](img/d3fb2049701e86ce38d2c5b59f58b928_59.png)

so this is no more the mean squared，error anymore。

![](img/d3fb2049701e86ce38d2c5b59f58b928_61.png)

this is a loss function coming out of，your network。



![](img/d3fb2049701e86ce38d2c5b59f58b928_63.png)

this is the li the loss function coming，out of a vgg16 and this is pre-trained。



![](img/d3fb2049701e86ce38d2c5b59f58b928_65.png)

and why are we using that because we，know that the vgg16 is。



![](img/d3fb2049701e86ce38d2c5b59f58b928_67.png)

encoding some information about the，content，of our image so it has some perceptive。



![](img/d3fb2049701e86ce38d2c5b59f58b928_69.png)

capabilities，because we trained it on that on that，task we wanted to be able to。



![](img/d3fb2049701e86ce38d2c5b59f58b928_71.png)

distinguish one image from another so。

![](img/d3fb2049701e86ce38d2c5b59f58b928_73.png)

the same structure is going to help you，solve both of the problems。

for the style transfer your yc is going。

![](img/d3fb2049701e86ce38d2c5b59f58b928_75.png)

to be x，so this is your input image and your，style。



![](img/d3fb2049701e86ce38d2c5b59f58b928_77.png)

we are going to pick a style and then，train one network。



![](img/d3fb2049701e86ce38d2c5b59f58b928_79.png)

peristyle so you're gonna keep that，aside，but then if you change your style you're。

gonna have to retrain a network。

![](img/d3fb2049701e86ce38d2c5b59f58b928_81.png)

and uh for the super resolution pass，you're not gonna use the style。



![](img/d3fb2049701e86ce38d2c5b59f58b928_83.png)

part of your loss so we are not going to，use that but yc is going to be the，higher resolution image。



![](img/d3fb2049701e86ce38d2c5b59f58b928_85.png)

x is the low resolution one the output，is going to be y hat，and you want y hat to be as close as。



![](img/d3fb2049701e86ce38d2c5b59f58b928_87.png)

possible to the high resolution image，rather than finding the mean squared。



![](img/d3fb2049701e86ce38d2c5b59f58b928_89.png)

error between these two，we push them through a vgg g16 and then，you compare。



![](img/d3fb2049701e86ce38d2c5b59f58b928_91.png)

the features at that layer so you're，loss，and we know that our features are。



![](img/d3fb2049701e86ce38d2c5b59f58b928_93.png)

tensors there's a bunch of channels it，has a height。



![](img/d3fb2049701e86ce38d2c5b59f58b928_95.png)

and it has a width and let's say this is，the activations，after the j layer of rvg。



![](img/d3fb2049701e86ce38d2c5b59f58b928_97.png)

this is after the j layer that is what j。

![](img/d3fb2049701e86ce38d2c5b59f58b928_99.png)

denotes and how do you come up with your，feature loss feature reconstruction loss。



![](img/d3fb2049701e86ce38d2c5b59f58b928_101.png)

you take the features，you compute the l2 norm and then you，average them you find the mean。



![](img/d3fb2049701e86ce38d2c5b59f58b928_103.png)

so basically you're averaging over your，channel，height and weight and that's going to。



![](img/d3fb2049701e86ce38d2c5b59f58b928_105.png)

give you your loss so basically you're，doing a mean squared，error loss but you're doing it on the。



![](img/d3fb2049701e86ce38d2c5b59f58b928_107.png)

features，of a pre-trained network this is smart，you can have a style。



![](img/d3fb2049701e86ce38d2c5b59f58b928_109.png)

reconstruction loss that one is like，slightly different，for that we are going to take a look at。



![](img/d3fb2049701e86ce38d2c5b59f58b928_111.png)

the gram matrix，and what is the gram metrics it's going，to tell you。



![](img/d3fb2049701e86ce38d2c5b59f58b928_113.png)

it's going to give you information about，which features。



![](img/d3fb2049701e86ce38d2c5b59f58b928_115.png)

are going to tend to activate together，so it's sort of a correlation。

between features and how do you compute。

![](img/d3fb2049701e86ce38d2c5b59f58b928_117.png)

it you take，feature c and c prime。

![](img/d3fb2049701e86ce38d2c5b59f58b928_119.png)

and then you're gonna do a，multiplication，this is a point-wise multiplication of。



![](img/d3fb2049701e86ce38d2c5b59f58b928_121.png)

uh，this vector j because we know that each。

![](img/d3fb2049701e86ce38d2c5b59f58b928_123.png)

pixel is going to be a，vector so now you're picking two，channels。



![](img/d3fb2049701e86ce38d2c5b59f58b928_125.png)

c and c prime and then you are doing the，inner product of those two。

uh images and then that's going to give。

![](img/d3fb2049701e86ce38d2c5b59f58b928_127.png)

you the correlation，between one pixel one channel and the，other one。



![](img/d3fb2049701e86ce38d2c5b59f58b928_129.png)

and then you're going to use that to，construct your loss that's just going to，be the frobenius norm。



![](img/d3fb2049701e86ce38d2c5b59f58b928_131.png)

of the gram matrix coming out of y hat，and the gram matrix coming out of range。



![](img/d3fb2049701e86ce38d2c5b59f58b928_133.png)

that's ys，your style okay now let's see how this，method compares qualitatively。

when it comes to style transfer to the，previous state of the art。

that's your content that's your style，that's the previous，state of the art that's what you get out。

of this method，your style could be the simpsons your，content could be a cat or this person。

and then that's going to be the output，and for each of these，slides styles you'll train the network。

so if you change your style，you trained another network so far so，good but what is this 11，do。

an optimization per each content image，so you pick a content image you pick a，style。

the loss functions are the same as the，loss functions in this paper。

and then this tv stands for total，variation，so it's acting as a regularizer these。

are hyper parameters to balance the，trade-off between different components，of your loss。

but the difference is that in this paper，you are taking，x and pushing it through a neural。

network to give you y hat，but 11 had to optimize，over the image because there was no，neural network。

key for it so per each content and style，problem，and that's expensive if you use 100。

optimization steps or 300 optimizations，there's or 500，and different resolutions the method in。

this paper，is gonna have that much speed up，so 11 is this much slower compared to。

what we covered here，because of this neural network and then，you can also。

see the difference when you do，super resolution this is by cubic this，is srcnn。

the previous paper and this is from loss，of the，features from these slots and you can。

see more pattern，compared to the blurry ones that you're，getting from the previous one。

so any questions so far in this case um，are we training both the parameters of，the。

image transform net as well as the lost，network or is the lost network。

just giving us a penalty that then，applies to，what our image transfer net spits out。

the last network is fixed there is no，training on that，there's no training ever okay so that's。

that's just giving us，basically a um confirmation of how good，or how bad our y hat is。

to then change the parameters of fw，exactly so that only speaks what。

fw got it um okay that makes total sense，thank you so this is clever to use a。

neural network as your loss function，of，these neural networks so you take a，pre-trained。

vg and you use that in your last，function any other questions，are there any other uses or like cases。

where you could use a，another network for a loss function i，know that。

there is another a bunch of other papers，that use it for evaluation metric。

you can use it for instance to judge the，quality of，images generated by your generator so。

you can also use it for as a metric，some big，discussions in the chat about peak。

signal optimize ratio，that's not the best metric you can，actually use and run network there。

to give you a better metric that，understands some of the concepts。

for us it's for us as humans it's very，easy we're gonna look at this uh。

these two images and we're gonna say yes，of course this is better。

but sometimes uh the signal to noise，ratio is not the correct metric for that。

it's going to give you a high signal to，noise ratio but then the image is。

crappy yes it seems like it can replace，uh，like when we usually do a qualitative。

judgment on something，yes so that's a good way to put it any，other questions。

this this speed up table on the bottom，right is really just talking about like，right。

yes okay because you'd have to train the，image transform net on like a bunch of。

images and a bunch of ways of generating，with like a certain style。

and then once it's trained it's fast for，stylizing a picture。

exactly and the thing is if you remember，the objective of deep learning。

is to give you an algorithm that you can，use in production，so you don't care how much it took yeah。

to come up with that algorithm，but once you have it you can use it in。

production and this is exactly what，you're going to put，as a post-processing step after your，image。

you're gonna put a neural network it's，gonna be very cheap，and then it's gonna give you high。

quality images yeah，and that's actually a way to boost the，performance of your。

gaming engine or gaming environments，it's cool it's gonna take a lot of，effort to actually make that。

production ready because these gamers，are，not usually that happy customers this。

the slightest of glitches is gonna end，up with bad reviews about your product。

so it's a different thing it's a，research paper but then making it。

