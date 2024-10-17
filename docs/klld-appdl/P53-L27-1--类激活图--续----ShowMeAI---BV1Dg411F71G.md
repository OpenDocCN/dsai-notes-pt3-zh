# P53：L27.1- 类激活图 [续] - ShowMeAI - BV1Dg411F71G

so we have started uh taking a look at，what happens inside the network and the，aim is to debug。

networks by looking at your data and try，to see what the network is learning。

we covered two methods of doing it so，far，one was using the convolutions we。

covered also another paper，that was more generic for，trying to understand the predictions of，any。

classifier so that one was more generic，and the idea there was that if you have。

a very complicated nonlinear model，locally a linear model might be able to，approximate。

its predictions and a linear model，is going to be interpretable and you can，interpret that。

and equivalently you're interpreting the，predictions of your，black box neural network this is also。

the one that we are covering today，and we started covering uh in the，previous session。

is specific to convolution on our own，networks and we want to find the class，activation map。

given a class what part of the image。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_1.png)

is activating most and that's going to，tell us，understand what the network is thinking。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_3.png)

about for instance brushing teeth，cutting trees and you can see where the，networks are。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_5.png)

focusing but how do we get these class，activation maps we know that if you have。

a high resolution image，and you push it through a bunch of，convolutions you're。

reducing the resolution each time you do。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_7.png)

it now you're gonna end up with a，low resolution feature map or a bunch of，feature maps。

and depending on the network the last，convolution，is probably going through。

some fully connected neural networks the，idea is，if of this paper is that just remove。

those fully connected neural networks，replace that with a global average，pooling。

once you do that you take a feature map，and then you collapse it into a single。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_9.png)

scalar by taking the average now the，last layer is just a linear combination。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_11.png)

of these features to predict your，prediction your label，now the idea is you take these weights。

that you learned。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_13.png)

you multiply them by the corresponding，feature map and then you basically turn。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_15.png)

create a linear combination of these，feature maps using these weights。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_17.png)

and in the end it's going to tell you，what part of the，image is activating the most or where。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_19.png)

the network is looking，to make the prediction for that，particular prediction but there is also。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_21.png)

another catch，this is of a lower resolution this class。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_23.png)

activation map has a lower resolution，compared to the input image so you just。

do a you just increase the resolution by，doing bi-linear interpolation and that's，going to help you。

put the class activation map on top of，your original image and see which parts。

are getting activated the most，but the question is why do you want to。

replace the fully connected part，with a global average pulling and the。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_25.png)

answer is in the math，so let's take a look at these，activations these are functions each one。

of these is a function，the inputs are the pixel locations x and。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_27.png)

y and the kth one is one of these it's，either blue red or green。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_29.png)

these are slices of your feature maps，what global average pooling does。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_31.png)

is you take an average over the pixels，and probably you are dividing by the，number of pixels。

that's going to give you fk these are，these blue dots，that we see here now the prediction for。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_33.png)

a particular class，is going to be a linear combination of。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_35.png)

these baits these features，with some weights that depend on the。

class so each class has its own weights，and this c is a pretty soft max so you，take a c。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_37.png)

you push it through your soft max，function it's going to give you the，probabilities。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_39.png)

but then let's take a look at this c s c，is a linear combination i'm using this，formula here。

of a bunch of weights multiplied by your。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_41.png)

fk and fk is just the global average，pooling operation，and why did we use global average。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_43.png)

pooling because now everything is linear，we can switch and bring this summation。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_45.png)

in the beginning and now though your，weights are getting multiplied by the。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_47.png)

feature maps，you are summing over all of your。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_49.png)

features over all of your feature maps，and that's com that's what is going to，give you your。

class activation map so the outcome of，this summation is what you see here。

the summation of your weight the blue。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_51.png)

feature map the red weight，the red feature map etc and that's going，to give your。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_53.png)

class activation map and here we are，just calling it m of c。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_55.png)

x i'm y can i ask a quick question yes，so this，uh this class activation map here is。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_57.png)

just a function，of the learned weights and。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_59.png)

oh never mind okay i see i see and it's，and it's also a function of like so it。

depends on the input image。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_61.png)

sorry that was my conclusion thanks yes，it depends on the input image。

and it's a linear combination of these。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_63.png)

features but now，the cool thing is that you could do this。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_65.png)

and call this your feature activation，class activation map and visualize mc。

and it is going to tell you how，important a particular pixel is。



![](img/81ca03f87dc4edcc54d14e998d65ec4b_67.png)

it's a。

![](img/81ca03f87dc4edcc54d14e998d65ec4b_69.png)

function of the pixels and the pixel，the the pixels and the label that you're，predicting。

um where does the upscaling the，resolution，come from in these formula oh where does，it come from。

this this has a lower resolution this，m c of x and y x and y here are。

the pixels in these feature maps and we，know that you have，less pixels here compared to the。

original image，and then you were saying you just，interpolate to visualize it together。

yes okay thanks you can actually，do the interpolation here as well but。

whatever you do you're gonna have an，up sampling going on and that's why。

in these peaks in these pictures you see，these lines，these discontinuities because of that up。

sampling，that you have to do but one application，of class activation maps is that you can，visualize。

what the network is thinking the other，application is when it comes to。

weekly supervised object localization，we are going to do object detection。

later on but for those applications，we are giving it the bounding box the。

ground truth bounding boxes，here your data set is just uh，an image and the corresponding label for。

instance that image，is a cat that image is a dock you are，not saying that that's an image。

and this is a box around the cat，this is not your data here your data are，just input outputs。

input design image output is the label，no bounding boxes，and that's why it's weakly supervised。

but what you can do，is take a look at this prediction of，your network。

it's activating some parts of your image，and you can put a，box that is surrounding this。

prediction basically what you can do is，uh have a threshold，below that threshold you're not putting。

your box and above that you're just，putting a box，and that's going to give you a bounding。

box around the prediction，so it's actually helping you localize。

your object and the bounding boxes are，not that accurate，but it is still impressive that it's。

finding the，american alligator without any labels，without any bounding boxes in the data。

so does this make sense any questions，okay perfect，you can do weekly supervised text，detector。

so in this image it's going to take the，text for us，there's a text here there's a text here。

and there one here，one here and another one here and these，are all weakly supervised we are not。

telling it where the text is，another application is this is，multimodal learning we are gonna go into。

more details，i think in the next semester and with，multi-modal learning。

you have two modes or three modes for，instance you are combining an image。

and text together and so one application，is visual question answering。

so an input is gonna be an image，and a question for instance you fit in，this image。

and you say what is this port and the，network has to predict that it's a。

skateboarding you give it this image and，you're gonna tell it，or ask from it where are the cows and。

it's gonna say，here on the grass so this is a different，application that we have seen so far and。

if you want to move towards general，a。i these are the sort of things that we，need to be able to do。

multi-modal learning it's not only one，mode but，not only an artificial intelligence，system。

should be able to process images it，should be able to process，text speech audio etc。

