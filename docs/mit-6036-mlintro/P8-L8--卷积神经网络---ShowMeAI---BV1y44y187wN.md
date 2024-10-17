# P8：L8- 卷积神经网络 - ShowMeAI - BV1y44y187wN

okay，it's that time so let's go ahead and get，started on，um what we will be calling lecture eight。

so you'll have noticed that there was，no uh lecture seven this year we had the，holiday。

um so our last lecture was lecture six，but the naming convention that we were，using is by week。

rather than by how many lectures we've，had before so this is lecture eight。

um so we hope as usual that you will um，you know participate in things like the。

discourse um and so just look for that，lecture eight，category for this one okay so。

last time that we were together for a，lecture we talked about neural networks。

we define neural networks um。

![](img/395e120dde62bd3055c1917104f18f93_1.png)

you know we we talked about all kinds of，different things like，how to represent them um both from a。



![](img/395e120dde62bd3055c1917104f18f93_3.png)

sort of mathematical，standpoint like notation but also，in this function graph that we had。

talked about，and in particular we really focused on。



![](img/395e120dde62bd3055c1917104f18f93_5.png)

two layer neural networks so in，particular one layer was，creating a sort of new set of features。



![](img/395e120dde62bd3055c1917104f18f93_7.png)

um and that was a new idea for us last，lecture this idea of，learning a set of features as part of。

the learning that we were doing，rather than just having them be。



![](img/395e120dde62bd3055c1917104f18f93_9.png)

something that we we，specify in advance that we come up with，in advance。



![](img/395e120dde62bd3055c1917104f18f93_11.png)

so that was a new idea um and when we，were doing that we were having。

um our layer that was learning those，features be fully connected，um so every output was connected to。

every input by a set of weights，um and then finally we had a fully。

connected layer that sort of did the，classification or did the regression and。

sometimes that wasn't new，that layer like you could think of the。

neural networks that we talked about，last time with two layers if you got rid。

of that hidden layer you're back to。

![](img/395e120dde62bd3055c1917104f18f93_13.png)

logistic regression or linear regression，or one of the things we've seen before。

so in some sense at this point we've。

![](img/395e120dde62bd3055c1917104f18f93_15.png)

talked about，one layer neural networks we've talked，about two-layer neural networks and，today。



![](img/395e120dde62bd3055c1917104f18f93_17.png)

we're going to talk about deep neural，networks which basically means more than，two。

more than two layers um and in，particular more than one hidden layer。

so last time we had this output layer，that you know did the classification put。

the for sort of features we've learned，together，into either a classification or a。

regression and then we had the hidden，layer that was constructing the features。

and so that's what we're going to be。

![](img/395e120dde62bd3055c1917104f18f93_19.png)

growing，we're going to be growing the number of，hidden layers。



![](img/395e120dde62bd3055c1917104f18f93_21.png)

so we'll talk about that today um in，particular，you know there are lots of ways that you。



![](img/395e120dde62bd3055c1917104f18f93_23.png)

could do that but we're going to talk，about one particular way um。

and hopefully in a moment you'll see why。

![](img/395e120dde62bd3055c1917104f18f93_25.png)

it's been a very popular way to have a，deep neural network，um this is uh convolutional neural。

networks um it might be called cnns，might be called convnets there are lots，of different。

um words but we're going to talk about，that as another hypothesis class for，things like。



![](img/395e120dde62bd3055c1917104f18f93_27.png)

classification things like regression，along the way。



![](img/395e120dde62bd3055c1917104f18f93_29.png)

we're going to um describe the layers，that really define，convolutional networks um so things like。

filters and max pooling which we'll have，seen from the reading。

and uh time permitting we'll talk about，how learning is a little bit different。

than what you had seen，in uh fully connected neural networks，although we'll still be doing these。

ideas of sort of gradient descent，stochastic gradient descent，and then the way that you specifically。

apply those in neural networks like back，propagation so it's not so。

different it's just that the back。

![](img/395e120dde62bd3055c1917104f18f93_31.png)

propagation looks a little bit different，okay so let's let's go ahead and start。



![](img/395e120dde62bd3055c1917104f18f93_33.png)

talking about this but let's let's also，start talking about you know why。

are we talking about convolutional。

![](img/395e120dde62bd3055c1917104f18f93_35.png)

neural networks as a particular example，um of deep learning and and the reality。

is that you know there's been，this sort of big change this big，excitement around machine learning in。

general，and deep neural nets in particular for，the past few years。

and a lot of that in some ways really，kicked off with convolutional neural。



![](img/395e120dde62bd3055c1917104f18f93_37.png)

nets although i'll add a little nuance，to that statement in a moment。

okay so there was this imagenet large，scale visual recognition challenge。

um basically the idea is that there were，tons of images that have been labeled。

with things like amazon mechanical turk，um they're in this particular challenge。

they restricted to about a thousand，categories these like the classes we've。



![](img/395e120dde62bd3055c1917104f18f93_39.png)

been talking about in classification，um the exact setup is a little bit more。

complex than what i've been describing。

![](img/395e120dde62bd3055c1917104f18f93_41.png)

if you're really interested in this i，strongly recommend you check out。

the wikipedia article is pretty cool，also there's this great，sort of um retrospective by olga。



![](img/395e120dde62bd3055c1917104f18f93_43.png)

versakovsky um，and a number of other people with，faithfully um and and i've cited that at。



![](img/395e120dde62bd3055c1917104f18f93_45.png)

the bottom of this slide as well so，anyway，there's this challenge with a thousand。

categories so that's a lot more classes，than we've typically，been dealing with and they're all these。

different image categories like is there，a strawberry is there a cow you know。

what's going on in this image，um and the idea was to，label the images correctly um that was。

the challenge given to the various teams。

![](img/395e120dde62bd3055c1917104f18f93_47.png)

um and so if you look at how um in this，case four teams performed in 2011。

so 2010 was the first year of the，getting。

![](img/395e120dde62bd3055c1917104f18f93_49.png)

over 20 of the images wrong so that's，the way you should be reading this。

vertical axis it goes from zero to one。

![](img/395e120dde62bd3055c1917104f18f93_51.png)

um and one would mean you're basically，getting everything wrong。

um and so in 2010 and 2011 the winners，of this challenge were using things that。

we haven't really talked about so much，in this class but we're really big at。

the time called support vector machines，um and then something really different。

happened in 2012 where，this um one particular submission，network。

um and it was called uh alexnet there's，a convolutional neural network around，eight layers we'll see。

what that means um shortly um it's it's，it's also i have to say about eight。

layers because the way people，count layers can be different from one。

thing to another but you get a sense of，you know how many there were there more。

than two but not yet a hundred，and it just really outperformed，everything else um so much so。

that by the next year basically，everybody，uh certainly most of the entries were。



![](img/395e120dde62bd3055c1917104f18f93_53.png)

convolutional neural networks，um and in fact in 2015 the imagenet。



![](img/395e120dde62bd3055c1917104f18f93_55.png)

winner was a much deeper convolutional，neural network having，over 100 layers by microsoft。

and so this seems like it was you know，really changing things um i think this。

paper has gotten like 60 000 citations，or something，um you know it's probably even more now。

i feel like these types of papers you。

![](img/395e120dde62bd3055c1917104f18f93_57.png)

blink and it's like a thousand more，citations，um but but it's also worth noting that。

like many things in science，um it really wasn't as much of a phase，change as it。



![](img/395e120dde62bd3055c1917104f18f93_59.png)

looks like from the outside a lot of，these tools had been building up for，years。

um so while there's this very recent ai，boom which was very much set off。

by alex ned and related work um，you know in the 60s and 80s and today。

neural networks were round and they were，very popular um。



![](img/395e120dde62bd3055c1917104f18f93_61.png)

and so the idea of a neural network，didn't start existing，and in fact the idea of a convolutional。



![](img/395e120dde62bd3055c1917104f18f93_63.png)

know in the，1980 there was something like a，commoneth this neocognotron。

um in 1989 yan lacoon and all were，looking at cob nuts for。



![](img/395e120dde62bd3055c1917104f18f93_65.png)

classifying images um they were，recognizing digits for post office use。

they were using that propagation。

![](img/395e120dde62bd3055c1917104f18f93_67.png)

um and so you know you can ask yourself，what changed from the 80s and 90s what。

really set this off and i think there，are you know quite a few different，things。



![](img/395e120dde62bd3055c1917104f18f93_69.png)

um so one is there's just better，computation in general and that's been。

the story of you know a lot of the past，few decades。



![](img/395e120dde62bd3055c1917104f18f93_71.png)

um gpus really made a huge difference，they were sort of perfectly aligned with。

the computations that people were doing，in convolutional neural nets um they，really。

massively enhanced parallelization and，then also there was just a lot more。

labeled data you know so there's things，like amazon mechanical turk。

there's lots of data on the internet for，better or for worse，um so this is an area of controversy。

sometimes that there's so many images。

![](img/395e120dde62bd3055c1917104f18f93_73.png)

that people share and they aren't，necessarily realizing that they're。

sharing it publicly and those are，getting used and swept up or maybe even。

if they're not sharing them publicly，but there's certainly a lot more labeled，image now images now。

um and that can really lend itself to uh。

![](img/395e120dde62bd3055c1917104f18f93_75.png)

to this kind of thing，okay so this is just a little like，teaser for you know why convolutional。

neural nets they're，really a big part of this ai boom that。



![](img/395e120dde62bd3055c1917104f18f93_77.png)

and a really，you know key component of that story um，but of course we also care about them。

because they can，do useful things um so there are a lot，of great potential uses of image。

classification，um the ability to detect tumors from，medical scans certainly that's something。

we would love to do we'd love to detect，different types of tumors。

um there i mean in general there are so，many things that we'd love to do。

with medical imaging and this seems to，have a lot of，um possibilities here also of course。

image searches online we really engage，with images，and autonomous driving we want to be。



![](img/395e120dde62bd3055c1917104f18f93_79.png)

and，you know do some pretty complex things，with images um and so for all of these。



![](img/395e120dde62bd3055c1917104f18f93_81.png)

reasons we'd really like the ability to，work with these kinds of data structures。

and certainly we haven't looked at。

![](img/395e120dde62bd3055c1917104f18f93_83.png)

anything that's a very，structured data set yet in this class。



![](img/395e120dde62bd3055c1917104f18f93_85.png)

we've sort of looked at individual data，points okay，so we're gonna be talking a lot about。



![](img/395e120dde62bd3055c1917104f18f93_87.png)

images today and so let's just recall，that images are made of pixels。

um so one of the big questions we'll be。

![](img/395e120dde62bd3055c1917104f18f93_89.png)

starting off with is how do i encode，this image in a way that now i can do。



![](img/395e120dde62bd3055c1917104f18f93_91.png)

learning out in the way that we're sort，of used to in this class you know we。

have to have a data point。

![](img/395e120dde62bd3055c1917104f18f93_93.png)

to，you know put it in and put it into our，classifier and so this is starting to。

get us to the point where we see oh，where are those x's going to be coming。

from they're going to be coming from the。

![](img/395e120dde62bd3055c1917104f18f93_95.png)

pixels，okay so in particular today。

![](img/395e120dde62bd3055c1917104f18f93_97.png)

we're going to focus on particularly，simple form of images images that are，gray scale。

images and in fact we're going to go，even simpler than that we're going to。

look at black and white images just for，today，that's not like you can you can't you。

can totally use other types of images。

![](img/395e120dde62bd3055c1917104f18f93_99.png)

other types of data with convolutional，neural nets this will be。

basically purely for illustration so for，instance if i had this image high。

it might be composed of a bunch of，pixels。

![](img/395e120dde62bd3055c1917104f18f93_101.png)

each pixel in general when we're looking，at grayscale images is going to take a。

value between zero and p，um again in today's particularly simple，examples。

we're going to have just zero being，black and one being white，um。

even for grayscale images you don't have，in。

![](img/395e120dde62bd3055c1917104f18f93_103.png)

your lab you're going to see p being a，more typical grayscale image value of。



![](img/395e120dde62bd3055c1917104f18f93_105.png)

okay but here we're gonna be focusing on，just these these zero。

one images again just for sort of ease，of illustration，and so if i had this image that was the。



![](img/395e120dde62bd3055c1917104f18f93_107.png)

word hi，i would encode it in zeros and ones in。

![](img/395e120dde62bd3055c1917104f18f93_109.png)

the following way，now again we still want to ask okay well，how are we going to actually。

use this image as an input for a neural，network。

![](img/395e120dde62bd3055c1917104f18f93_111.png)

um because again you know we think about，what have we been doing to our data to，turn it into。



![](img/395e120dde62bd3055c1917104f18f93_113.png)

an input to some kind of machine，learning model well again we've had。



![](img/395e120dde62bd3055c1917104f18f93_115.png)

something like x1 x2 x3 x4，and so what we can do is we can take。

this image and essentially flatten it。

![](img/395e120dde62bd3055c1917104f18f93_117.png)

and that can turn it into the x1 x2 x3，x4 and so what i mean by that。

is exactly the following i just find，some ordering of the pixels。

and i call the first one x1 and i call，one，x3 um in some senses。

you know just in terms of encoding this，the ordering isn't so important。



![](img/395e120dde62bd3055c1917104f18f93_119.png)

um in other senses it will be important，okay so at this point i have a vector of。

values i have my x1 i have my x2 i have，my x3 up to my x sub little n。

or i always i always always get this。

![](img/395e120dde62bd3055c1917104f18f93_121.png)

wrong they should be superscripts，um oh no no no they shouldn't be they。

should be subscripts so these are these，point，great okay so these are all my。

features essentially for this data point，for this image。



![](img/395e120dde62bd3055c1917104f18f93_123.png)

and so now i want to feed it into a，neural net and so let's first ask what。

would that look like with the neural。

![](img/395e120dde62bd3055c1917104f18f93_125.png)

nets that we were looking at before。

![](img/395e120dde62bd3055c1917104f18f93_127.png)

okay so previously we saw these two，layer，neural nets in this class。

and so this is the example we saw from，last week um so one thing that we've，done here。

is we put these parentheses around the，superscripts just to super emphasize。

that they were superscripts，you'll have noticed in the reading and，the labs and everything that。

eventually that just gets to be too much，to write and so we just write the。

superscripts um and so that's always a，little tricky making sure you know when。

it's a superscript and when it's a power。

![](img/395e120dde62bd3055c1917104f18f93_129.png)

um but here we're just emphasizing that，we have these two layers。



![](img/395e120dde62bd3055c1917104f18f93_131.png)

and so now we want to say okay how would，we feed an image into this well we。

totally can i mean we have our x1，through our you know number of features。

that we feed in the beginning，and so you know we already have the，ability。

to put this into a two-layer neural，network to put this image in and do，something with it。



![](img/395e120dde62bd3055c1917104f18f93_133.png)

better，essentially that we could we could do。

![](img/395e120dde62bd3055c1917104f18f93_135.png)

things to have better performance and，that's essentially what we're going to。

be focusing on so something i want to，highlight here。



![](img/395e120dde62bd3055c1917104f18f93_137.png)

is remember we had these two layers and，the first layer was constructing a set。



![](img/395e120dde62bd3055c1917104f18f93_139.png)

of features，and then the second layer this this，output layer was taking those features。

and then making some kind of，classification，and so what we're going to be focusing。



![](img/395e120dde62bd3055c1917104f18f93_141.png)

on today is we're not going to change，anything about the output layer we're。

still going to take features do some。

![](img/395e120dde62bd3055c1917104f18f93_143.png)

kind of classification with it，or regression um and and that will be，unchanged。

that will look like you know something，like maybe logistic regression。

or linear regression or what have you um。

![](img/395e120dde62bd3055c1917104f18f93_145.png)

what we're going to be focusing on，is the that hidden that input layer。

or the you know in general the build up，of the future okay so something to。

notice about all the layers that we，talked about last week is that they're，all fully connected。

so every input is connected to every，output by weight，again we're not going to change anything。

about that in the output layer，we're still going to have our usual，logistic regression。

or linear regression but we are going to，change that，so instead of having this fully。

connected situation where，every input is connected to every output。

we're going to think about you know，essentially is there anything more that。

we know about this problem if we're，looking at something like images。

and in fact there is and and in general，sort of a rule of thumb and machine。

learning is at least to get started if，you know something about the problem you，don't want to。

force your method to try to relearn it，you want to encode that。

you want to add that into the method so。

![](img/395e120dde62bd3055c1917104f18f93_147.png)

it can focus on learning the things that，are important。



![](img/395e120dde62bd3055c1917104f18f93_149.png)

and so what do we know about an image，problem，that we didn't know maybe perhaps about。



![](img/395e120dde62bd3055c1917104f18f93_151.png)

a general problem well there's a lot of，things that are very special about，images。

so one is spatial locality like let's，say that i'm looking at some kind of，self-driving car。

application and i want to detect stop，signs i want to know is there a stop，sign in this picture。

well in general i expect the stop sign，is going to be in，a bunch of pixels that are near each。

other i don't expect that the stop sign。

![](img/395e120dde62bd3055c1917104f18f93_153.png)

is going to be like up in the upper，right hand corner and also in the lower，left hand corner。



![](img/395e120dde62bd3055c1917104f18f93_155.png)

and like dispersed throughout the image，i think that you know the way that stop，same。

place all their parts are in the same，place so that's something that we have，about images。

that we would like to encode another，thing we have about images or that we，sort of know about images。



![](img/395e120dde62bd3055c1917104f18f93_157.png)

is translation and variants um so i，could have a stop sign，over on this part of the image but i。

could also have a stop sign in the，middle of the image，i could also have a stop sign in another。

part of the image and those are all stop。

![](img/395e120dde62bd3055c1917104f18f93_159.png)

signs，and i would not want。

![](img/395e120dde62bd3055c1917104f18f93_161.png)

to have a situation where i need to have，my neural network，learn a totally new representation of a。

stop sign no matter where it is，in the image i would like to say i'm，going to detect this stop sign。

and so we'd like to have a layer or a，set of features that encodes these。

principles and right now our fully，connected layer totally doesn't。

it says that pixel 20 is fundamentally，very different from pixel one。



![](img/395e120dde62bd3055c1917104f18f93_163.png)

and the pixels like in one part of the，image are totally different from the。

pixels in another part of the image and。

![](img/395e120dde62bd3055c1917104f18f93_165.png)

learns weights for those different parts，of the images，and so we need to come up with some new。

method，that's going to encode these principles，because we don't have them right now。

and that's essentially going to be the，idea of these filters，and max pooling and things like that。



![](img/395e120dde62bd3055c1917104f18f93_167.png)

okay so let's start looking at a。

![](img/395e120dde62bd3055c1917104f18f93_169.png)

in particular we're going to look at a，1d image we're going to start looking at。

a 1d image so we're just looking at like，we're，we tend to think of our images as being。



![](img/395e120dde62bd3055c1917104f18f93_171.png)

two-dimensional um but here we're going，to look at a 1d image now。



![](img/395e120dde62bd3055c1917104f18f93_173.png)

first i want to point out that a，one-dimensional signal。



![](img/395e120dde62bd3055c1917104f18f93_175.png)

is not a toy signal there are a lot of，real-life one-dimensional signals so an。

example of this is if you look at，medical time，series like measuring your heart rate，over time。

you know even measuring something like，the number of covet cases over time。

these are one-dimensional signals and in。

![](img/395e120dde62bd3055c1917104f18f93_177.png)

fact people have applied very recently，here's just，one example paper among i'm sure many um。

convolutional neural nets two，one-dimensional signals，um they might not be interpreting them。

as images so much but it's still a，one-dimensional signal and it's going to。

look like this it's just maybe not going，to be zeros and ones。

it might be something more more general，okay we see this in a lot of other areas，too so you can get。

um time series for instance um，in a lot of spatiotemporal applications，so maybe um。

i'm looking at something like monthly，temperature at a location。



![](img/395e120dde62bd3055c1917104f18f93_179.png)

you can get it in genetics so the genome，can be thought of as。

basically one-dimensional so you can get，data like that，another way that i might get a signal。

like this maybe even a zero one signal，is maybe i'm doing some astronomy。

application i point my telescope at a，particular part of the sky，and i might be interested in。

understanding is there sort of，you know uh a light in that part of the，sky maybe it's a star。



![](img/395e120dde62bd3055c1917104f18f93_181.png)

a，satellite passing through um and so i，could be。

![](img/395e120dde62bd3055c1917104f18f93_183.png)

you know just basically saying for every，maybe 10 seconds，um am i seeing you know light in that。

part of the sky，and then maybe i want to detect the，satellites because they're going to be。

passing so quickly and so they'll be，sort of ephemeral lights they'll be just。

going for you know just a moment as，opposed to a longer time so this is。

just just sort of a uh maybe a，motivating example to have in your head。

for what this 1d image might represent，okay so now what we're going to do is。



![](img/395e120dde62bd3055c1917104f18f93_185.png)

we're going to apply a filter，to this image so what i mean by a filter，here's an example。



![](img/395e120dde62bd3055c1917104f18f93_187.png)

it's just three numbers and we're going，to take a dot product，between these three numbers and。

basically every，set of three numbers in the image and，get an output um and we're going to call。

that a convolution，okay so for instance here are three，numbers in my image here's my filter，is。

i'm going to multiply the first two zero。

![](img/395e120dde62bd3055c1917104f18f93_189.png)

times negative 1。i'm going to multiply the second two，numbers 0 times 1。



![](img/395e120dde62bd3055c1917104f18f93_191.png)

and add that in i'm going to multiply，the last two numbers 1 times negative 1。

and i'm going to add that in so this is，just a dot product between the vectors 0，0 1。

and negative 1 negative 1 the filter，okay i can compute this dot product the。

whole thing is going to be negative 1，ever，heard the words convolution or，correlation。

in the past um you might be thinking hey，this this really sounds like a。

correlation it doesn't sound like maybe，the thing that i've heard of as a。

convolution in the past um and a，genuinely challenging fact of life is。

that there are just overloading of terms，in so many different areas um and so you。

should think of this as being a，convolution for the purposes。

of convolutional neural networks this is，how the term is used here。

that doesn't mean that it's always going，anything，um this is you know one of those things。

that makes you really realize you have，else，to see does that word mean the same，think。

a great example of this is the word，normal it means like a million different。

things in a million different areas，um you know across physics across。

statistics across machine learning you，know everything，um and so convolution is just one of。

those words but here's what we're going，to be meaning by convolution essentially。

taking this dot product，um and moving it along okay，so we're going to do the same thing for。

the next three set of contiguous，pixels here so we're again going to take，this dot product。

between these two values and we're going，to put that in for the output and。

just to check um could everybody respond，to me or anybody who，is up for it respond to me in the chat。



![](img/395e120dde62bd3055c1917104f18f93_193.png)

and just say what is the stock product，going to be。



![](img/395e120dde62bd3055c1917104f18f93_195.png)

awesome lots lots of，totally perfect responses everybody's，getting that this is going to be zero。

okay and then we just keep doing this so，we we go to the next three set of pixels。

we do the next three set of pixels go to，the next three set of pixels。

and so on and so on until we've gone，through every set of three contiguous。

pixels every unique set of，three contiguous pixels okay so now。



![](img/395e120dde62bd3055c1917104f18f93_197.png)

we've performed convolution and a，typical thing that we'll do at this，point。

is then you know you can think of these，as being the pre-activations。

um just like we had in our two layer，neural network we had something where。

you know we did some kind of，um you know combination some linear，combination。

of weights and our data and we got，pre-activations，and then we put them through uh one of。

these activation functions so let's say。

![](img/395e120dde62bd3055c1917104f18f93_199.png)

that in this case we'll use a reload，okay so if we do that then we recall。



![](img/395e120dde62bd3055c1917104f18f93_201.png)

that basically that's going to put an，output of zero when our input is zero or，below and it's gonna。

just put out the output again put in the，same value again if the input's above，zero。

so here we're gonna get a zero here，we're gonna get a zero we're gonna do。

zero here we'll finally get a one um and，then we'll get a bunch of zeros。

okay and so i think the the question，that we wanna ask now and this is a real。

question that again i'm asking to you，and you should。



![](img/395e120dde62bd3055c1917104f18f93_203.png)

feel very free to respond in the chat is，what does this filter do。

um you know we've applied this filter。

![](img/395e120dde62bd3055c1917104f18f93_205.png)

but why like does it actually do，anything for us，you know what does it tell us about this。

i like the description of it as finding，a lonely one，um it's it's finding an isolated one。

it's finding a one that is flanked by，two zeros in this particular case we're。

we're only looking at zero one data。

![](img/395e120dde62bd3055c1917104f18f93_207.png)

um and so basically what's happening is，we're get we're doing this convolution。

and we're gonna get a negative number or，a zero，if we don't have a one flanked by two。



![](img/395e120dde62bd3055c1917104f18f93_209.png)

zeros and we're going to get something，above zero，if we do have a one flanked by two zeros。

um you know again if you think of this，in terms of the astronomy example。

uh if we get a lot of ones you know that，could be because we're，seeing a star and it's just moving。

slowly because of the rotation of the。

![](img/395e120dde62bd3055c1917104f18f93_211.png)

earth across our telescope，um but if we get a single one you know。

maybe that's a satellite zooming across。

![](img/395e120dde62bd3055c1917104f18f93_213.png)

the sky and we want to detect those，satellites，and so we would be interested in finding。

where are these isolated ones，okay great now something that you'll，notice here。

is that if our satellite zoomed by in，the first pixel or the last pixel we，wouldn't pick it out。

right now um because what we've done is，we've had to take every。

three pixels that come together and so，we just sort of won't get things at the，very edge。

of this image you know the very at the，very ends let's start in the beginning。

um and so if we wanted to pick that out，something that we might do。

is we might add padding to both sides of，the image，and so a really typical thing to do with。

padding is to make it，zeros i can't emphasize enough how much。

everything that we're talking about is a，choice and so what you should really do。

just like everything we've talked about，so far in this class is you should ask。

yourself what are you trying to，accomplish with any particular，application。

um and then ask yourself what type of，padding or what you know。

choices in general are appropriate for。

![](img/395e120dde62bd3055c1917104f18f93_215.png)

that application but here if we wanted，to detect these satellites，say um then we might say hey zero。



![](img/395e120dde62bd3055c1917104f18f93_217.png)

padding is reasonable because we want to，be able to detect something that could。

have been at the edge like a one，at the edge okay so in this case what。

we'll do is once we've added our padding，we've added our，our zeros to the edge now we have the。

ability to apply the filter，just a little bit further so now we can，apply the filter here。

to the three pixels at the beginning，including the padded pixel and it's just，the same as before。

we just do this dot product now with the，padded pixel included，okay and then same thing at the end。

we'll just do the dot product now with，the padded pixel included because that。

lets us go a little farther and we get，out of zero，um and something you'll notice here this。

is a very typical thing to try to，accomplish with padding is that usually。

we're trying to get the image the，after convolution to be the same size as。

the image before convolution，so you can sort of say you know in some。

sense the filter is telling you what's，happening in each pixel，and so now you'll have an answer for。

each pixel essentially，and so once we've done that we're then。



![](img/395e120dde62bd3055c1917104f18f93_219.png)

going to put these these final。

![](img/395e120dde62bd3055c1917104f18f93_221.png)

pixels again through a relu，and in this case we'll just get some。

okay now so far with this filter we've，just applied it as is but we can apply，it with a bias。

um and so what we mean by that is we，take the dot product that we were taking，before。



![](img/395e120dde62bd3055c1917104f18f93_223.png)

and we just add the bias term at the end，this is essentially what we've been。

doing with biases all along。

![](img/395e120dde62bd3055c1917104f18f93_225.png)

you know we've been having um for，instance in logistic regression。

you had essentially a weight vector，which was theta and then you added this，theta naught at the end。

this is exactly like that you have this，weight vector which is described by the。

filter and then we add this bias，at the end um and so we're doing the，same thing here。

the only thing that's sort of different，is that we're moving this along。

within our data instead of just applying，it to the whole data which is what we。

sort of would have done with weight。

![](img/395e120dde62bd3055c1917104f18f93_227.png)

vectors before in the class，so here for instance we would do this。



![](img/395e120dde62bd3055c1917104f18f93_229.png)

dot product so the dot product hopefully，is pretty clearly zero，um。

and then we add the bias at the end，that's going to be one and so we would，get one out from。

this convolution，okay and then we would do the same thing，going forward um。

and we do our dot product in this case，we get out of negative one we add our。



![](img/395e120dde62bd3055c1917104f18f93_231.png)

and then we just keep doing this that，fills in all of our，numbers and finally we apply the relu。

as before in this case you see that we，get quite a lot more，non-zero numbers once we have this bias。

so this bias really does，change the kind of output that we're，okay now in general。

we don't have to have a filter that's，just made up，for nets or integers we could have。



![](img/395e120dde62bd3055c1917104f18f93_233.png)

absolutely，any real weights here so in general if，we have this。

filter that has size three so its length，weights，let's call them w one w two and w three。

again they can totally be real values，um you know the negative one one。

negative one is sort of nice for，illustration，um but we could have point nine we could。

have you know negative one point two，you have all these different um values。



![](img/395e120dde62bd3055c1917104f18f93_235.png)

bias b，something。

![](img/395e120dde62bd3055c1917104f18f93_237.png)

uh that is real valued as well and we，just do the same thing we do this dot。

product once we have our w1 w2 w3 and，our b we do this dot product with each，set of 3 pixels。

we add the bias b and we get our，convolution and then we can put this，through。

and it does not have to be a filter of，size 3 it could be a filter of size two。

it could be a filter of size four it，could be a totally different size filter。

um it's really uh a choice um。

![](img/395e120dde62bd3055c1917104f18f93_239.png)

and that is part of the sort of，architecture the building。



![](img/395e120dde62bd3055c1917104f18f93_241.png)

you know of these filters and in general，okay so in this particular case we did。

an example of size three and we saw what，you know，what what are these filters doing what。

are we accomplishing with them，now just to think for a moment。



![](img/395e120dde62bd3055c1917104f18f93_243.png)

we want to think you know what happened，here，we we could have done we could have。

taken this one dimensional image，and we could have applied a fully。



![](img/395e120dde62bd3055c1917104f18f93_245.png)

connected neural network layer to create，our features，um we could have done everything we did。

last time with the activation，with the activation function and all of。

that um and so let's ask ourselves，you know what's fundamentally changed。

here um in this particular case，supposing we did have a filter of size 3。



![](img/395e120dde62bd3055c1917104f18f93_247.png)

with a bias b um this is another real，question for the chat，how many weights will i have including。

the bias term so essentially i'm asking，how many parameters。



![](img/395e120dde62bd3055c1917104f18f93_249.png)

so in particular the number of，parameters i'm gonna have here。

as many of you are pointing out is four，because i have the three。



![](img/395e120dde62bd3055c1917104f18f93_251.png)

weights w1 w2 w3 and i have the bias b。

![](img/395e120dde62bd3055c1917104f18f93_253.png)

so even though i move those around，in the image like i'm going to move them，you know。

to the next pixel and so on i'm going to，use the same weights，every time i do that um and so。

essentially，at the end of the day you know we're，going to build up this model that。

depends on these weights，but we're going to try to then learn our。

parameters so this is what we've done a，million times now we've built up a model。

that depends on some parameters and then，we try to learn those parameters。

and here if we had this filter the，number of parameters we'd have to learn，would be four。



![](img/395e120dde62bd3055c1917104f18f93_255.png)

because it would be the three weights，that we just keep moving along and this，bias b。



![](img/395e120dde62bd3055c1917104f18f93_257.png)

okay now let's ask ourselves what if，instead，we had used a fully connected layer。

so what would a fully connected layer，look like here first of all let's notice。

that i have 10 inputs those are my，pixels，so a data point consists of 10 pixels in，this case。

um x1 x2 x3 up to x10 um in this case，this particular data point is zero zero。

one one one zero one zero zero zero。

![](img/395e120dde62bd3055c1917104f18f93_259.png)

um but i would have other data points，and things to do like that。



![](img/395e120dde62bd3055c1917104f18f93_261.png)

but the input size is 10。 and then my 10，outputs are what i get after this。

convolution and relu and so i could have，instead，had a fully connected layer with 10。

inputs and 10 outputs and so now my，question，for you which i see some of you are。

already answering which is awesome，um is how many weights including biases。

that i have for a fully connected layer。

![](img/395e120dde62bd3055c1917104f18f93_263.png)

okay lots of awesome answers here let's，let's walk，through this um for anybody who's。

immediately thinking of this or even if，you are thinking of it just to check。



![](img/395e120dde62bd3055c1917104f18f93_265.png)

your your mental map so if we had this，fully connected layer，we would have you know what we would。

have 10 inputs，we'd have 10 outputs and so for every，output，we would have to have a weight for every。

one of the inputs，and for our bias and so that means，for every one of our 10 outputs we have。

10 weights plus a bias so 11 total，weights，now we just multiply those together and。

we get that we'd have 110 weights and so，even for this super。

simple case because you know your images，generally aren't going to be。



![](img/395e120dde62bd3055c1917104f18f93_267.png)

10 pixels long and this is just going to，be you know，way more different if you get to higher。

levels of pixels but even for this very，simple case we see that there's a huge。

difference between the number of weights。

![](img/395e120dde62bd3055c1917104f18f93_269.png)

in the convolutional layer and a fully，connected layer，and the fully connected layer because。

everything has to connect to everything，else you get this，huge number of weights and biases，whereas。

with this filter we just have a very，small number of weights and biases，because we're。

reusing them essentially again and again，and again，and so if this is capable of encoding。

the things that we want。

![](img/395e120dde62bd3055c1917104f18f93_271.png)

this could potentially be a really big，savings um，we don't have to learn you know 110。

parameters now we just have to learn。

![](img/395e120dde62bd3055c1917104f18f93_273.png)

four parameters，another way to think about this again is，like in terms of that stop sign you know。

if i had to learn this fully connected，layer and i wanted to learn the kind of。

information that was in this filter i'd，have to relearn this filter for every。

single part of the image，i'd have to relearn that there could be。

a stop sign in every part of the image，and so here instead we're saying。

hey i just want to learn um this one，filter。

![](img/395e120dde62bd3055c1917104f18f93_275.png)

over the whole image and so that's where，the savings is coming from now of course。

that depends on this being the thing，that we want to learn and encapsulating。

what we're actually interested in，but if that's true then this is a really。



![](img/395e120dde62bd3055c1917104f18f93_277.png)

okay so that's a 1d example，let's let's go on to uh something that's。

a little bit more representative，of the types of images that we would um。

see in real life and and that's two，dimensions，um at least in terms of images again i。

can't emphasize enough 1d，signals absolutely occur in so many，think。



![](img/395e120dde62bd3055c1917104f18f93_279.png)

we're used to two dimensions，okay so let's look at a 2d image this is。

actually our familiar 2d image from，before that says hi。



![](img/395e120dde62bd3055c1917104f18f93_281.png)

and it's just composed of a five by five，set of pixels here，and so with our five by five set of。

pixels we're now going to apply a filter，and now because we're dealing with 2d。

images our filter will also be，two dimensional so in this case it。



![](img/395e120dde62bd3055c1917104f18f93_283.png)

happens to be a three by three filter，and the way that we're gonna apply the。

filter is very analogous to what we did，before in terms of convolution we're，gonna line it up。

with the part of the image that has the，same size a subset of that image。

and then we're going to multiply，together the values，in each pixel that aligns so in。

particular we're going to take，you know we're going to start by taking，this upper corner。

we have a one and a negative one when we。

![](img/395e120dde62bd3055c1917104f18f93_285.png)

multiply those together we get a，now we're going to take the next two。

sets of pixels that align between the，filter and the subset of the image。

we have a zero and a negative one we'll，multiply those together and we'll get a，zero。

now we'll take the next two sets of，pixels that align it's a one and a。

negative one we'll multiply those，together and we'll get a negative one。

now we'll go to the next two sets of，pixels that align we have a one and a。

negative one we multiply those together。

![](img/395e120dde62bd3055c1917104f18f93_287.png)

okay we get a zero and a one we multiply。

![](img/395e120dde62bd3055c1917104f18f93_289.png)

one and negative one is a negative 1。 we，keep doing the same thing。

and so for every one of these nine，elements，we're multiplying it together now this。

is really the same operation，as a dot product one way that you could。

think about this um as doing this dot，product is that you're flattening。

this subset of the image and you're also，flattening the filter in the same way to。

make a vector and then you're doing a，dot product between those two vectors。

but it's also perfectly legit to think，of it as just being you're multiplying。

the pixels that align in the two things，together you're，adding them all up and you're getting a。

value，in this case it happens to be negative，seven and so we'll put that down here。

and eventually we're going to fill in，something that looks like an image by。

okay and so the next thing we would do，is we'd find another unique subset of。



![](img/395e120dde62bd3055c1917104f18f93_291.png)

the image，say this one to perform this convolution，now what we could do is we could step。



![](img/395e120dde62bd3055c1917104f18f93_293.png)

through again and say，okay you know i'm multiplying a zero and。

a negative one and i get a zero and so，forth but something we might notice，about this filter。

is that it's negative ones all around，the outside and a one in the middle。

and so one way you could quickly，take，negative times the number of ones in my。

image that aren't in the middle，my image subset and then i'm going to。

add one if there's a one in the middle，so in this particular case i'll notice。



![](img/395e120dde62bd3055c1917104f18f93_295.png)

there are three ones，in my my image subset that thing that's，in the blue square。



![](img/395e120dde62bd3055c1917104f18f93_297.png)

that aren't in the middle and there's，one one in the middle so i can take，negative three plus one。

and my output will be negative two，okay so just to check on that let's say，i go to the next step。

can you tell me in the chat what is，going to be，the convolution of this filter with this。

awesome looking good，great so i think i think many of you。



![](img/395e120dde62bd3055c1917104f18f93_299.png)

four，ones that are on the outside you know，not in the center of this subset of the，image。

um and there's no one in the middle and。

![](img/395e120dde62bd3055c1917104f18f93_301.png)

so i'm going to get out，okay and then what we would do is we，would just keep applying this。

so we would say okay i've you know i've，made this convolution here，image。

that looks like my filter this next，three by three subset of the image。

i apply this filter convolution。

![](img/395e120dde62bd3055c1917104f18f93_303.png)

i get out in this case negative five，negative 2，negative 5 i just keep doing these，calculations。

is that at this point i've i've applied，this filter to my image。

and um now it's it's much more striking，than in the 1d case that i've。

dramatically reduced the size of my，image by going through this convolution。

step um i went from having a 5x5 image，to having a 3x3 image um and again。

you know there are a few things i might，be interested in here one i might be。



![](img/395e120dde62bd3055c1917104f18f93_305.png)

interested in having my output be the，same as my image in part though because。

i want to say something about the pixels，that around the outside。

you know if i want to be able to talk，about these edge pixels if i want to be。

able to you know ask if my filter，applies to them，i'm going to need to do something more。

because right now，i can't center my filter at those edge，pixels。



![](img/395e120dde62bd3055c1917104f18f93_307.png)

and so this is what padding will，accomplish，if i apply padding all around the。



![](img/395e120dde62bd3055c1917104f18f93_309.png)

outside then i can center my filter，at those edge pixels and i can pick up。

something about the edge pixels，so again it depends what you want to do。

but this would be a very typical thing，to do here，to be able to see something about those。

edge pixels，and to be able to apply our filter there，okay so once we've applied the padding。

you can go in now and there's a new，there are new sets of these three by。



![](img/395e120dde62bd3055c1917104f18f93_311.png)

three image segments，that i can apply my filter to so in。



![](img/395e120dde62bd3055c1917104f18f93_313.png)

particular this is one of them，um and it's just the same operation as。

before we say how many ones are，you know around the outside of this，little image。



![](img/395e120dde62bd3055c1917104f18f93_315.png)

segment this is sort of um subset of the，image there's one there's one inside and。

so we're going to get zero by。

![](img/395e120dde62bd3055c1917104f18f93_317.png)

now we can go to the the next step and，we can keep doing this and we can fill，in。

now an outer layer around，so we just step through we do the same。

operations as before and we just have a，padding。

![](img/395e120dde62bd3055c1917104f18f93_319.png)

and you'll notice now once we've applied，this padding，um sort of by design we now get back。

something that has the same size as our，original image so our original image was，five by five。

now that we can apply this filter with，this particular set of padding。

we can get this nice 5x5 image out now，it won't always be the case that the。



![](img/395e120dde62bd3055c1917104f18f93_321.png)

right amount of padding is just a，padding of size one that happens to be。

because of this particular size of。

![](img/395e120dde62bd3055c1917104f18f93_323.png)

filter，um but it is a very typical thing to use，an amount of padding。



![](img/395e120dde62bd3055c1917104f18f93_325.png)

that will let you get back something，that looks like the size of the original。

okay so now we said hey the usual thing，is we don't just apply convolution。

you know that's our pre-activation we，then typically will apply some。



![](img/395e120dde62bd3055c1917104f18f93_327.png)

activation function，um just like we did for you know sort of。

our fully connected neural networks that。

![](img/395e120dde62bd3055c1917104f18f93_329.png)

we were talking about before，and so now we're going to apply an。

activation function again let's just say，it's a relu，and so if we apply that um we recall。

that what happens in a relu is that，anything that is zero or below gets set，to zero。

and anything that's above zero gets set，to，whatever its value is and so in order to。

apply a reload here we can just，identify you know what is happening here。

what values are above zero and in this。

![](img/395e120dde62bd3055c1917104f18f93_331.png)

case there's actually just one，there's actually just a single value，that's above zero。

and so it'll be really easy to know what，all of the other values are。



![](img/395e120dde62bd3055c1917104f18f93_333.png)

okay so we just set everything to zero，so this is the operation or this is this，is the final。

activation values this is what we，finally get after，you know doing all of that work。

both applying the filter and then，applying a relu。

![](img/395e120dde62bd3055c1917104f18f93_335.png)

to each one of these pixels，okay and now again we can ask ourselves。



![](img/395e120dde62bd3055c1917104f18f93_337.png)

what did this filter do what was what，was this filter doing what was its what。

was the point of this filter，did it accomplish something that we can。

explain in words um again this is a，put your。

![](img/395e120dde62bd3055c1917104f18f93_339.png)

good stuff，okay it found an even more lonely pixel。



![](img/395e120dde62bd3055c1917104f18f93_341.png)

um this one was saying much like our，previous one，much like our previous filter it's，asking。

it's not a quarantined one that's，another great way to put it。

um it found a one that is surrounded by，all zeros，so we're looking for a one that's。

surrounded by all zeros，in this particular case another thing。

that people have noticed is that that's，the dot。

![](img/395e120dde62bd3055c1917104f18f93_343.png)

on the eye right because here we have um。

![](img/395e120dde62bd3055c1917104f18f93_345.png)

this this word high that's spelled out，and so essentially what we've done with。

this filter is we have，we have detected this dot it was sort of，a dot detector。

um in this case we because we have an，image and we're interpreting it as an。

image we can really think of that as，being a particular dot，um that we are detecting and that's what。

this filter has detected，now something that i think is worth is，interesting and worth noting here。

um is that we would not have detected，the dot on the eye without the padding。

um so it was specifically the padding，hey，there's there's just nothing on this。

other side of the eye essentially，um and so now we can go in and find。

things and because this was on an edge，it was something that we could really。

only detect once we had done the padding，but once we did that，we can detect that dot and another。

interesting thing about this filter is，because it's sort of center aligned。

we're seeing that um we can really，recreate exactly where that dot is。

because that's exactly the pixel where，that that one ended up being，to have。

just negative ones and ones for your，filter you don't have to have integers。

for your filter and your filter，definitely doesn't have to only do。



![](img/395e120dde62bd3055c1917104f18f93_347.png)

dot detection that was just sort of a i，think a nice illustration here。

um so in particular um you know we'll，see in a moment that you can have more，just。

recall that you can have a bias term and，that's no different，in this case you can also have a bias。

term um，even when you're in the sort of slightly，higher dimensional cases。

so now we're in this two-dimensional，case and the bias means the same thing。

in that you essentially do this thing，that is like a dot product。

you know you take your subset of your，image，you multiply each value with the。

corresponding value in the filter you，add them all up，so we have this sort of linear。

combination between the weights and the，filter，think of the elements in the filters。

being weights and the data points，even with padding and then you add the，bias at the end。

so in this particular case we would say，okay，again there's one there's a single one。

that's outside the middle one，so we're gonna get a negative one，there's a single one in the center。

for this blue image so we're gonna get，one we add those together we get zero we，add the bias two。

okay just a quick check again let's say，that i apply this filter with the bias。



![](img/395e120dde62bd3055c1917104f18f93_349.png)

to this subset of the image，what am i going to get for this output。

for the convolution just a question for，great good，stuff okay so。

most people here are saying um negative，two。

![](img/395e120dde62bd3055c1917104f18f93_351.png)

so the first thing that you do again is，you apply。

![](img/395e120dde62bd3055c1917104f18f93_353.png)

just the convolution without the bias，once you apply the convolution without。



![](img/395e120dde62bd3055c1917104f18f93_355.png)

the bias you'll get negative four，then you add the bias of two and then，you get negative two。

so now we have this negative two and，finally we're just going to fill in。

the rest using the same set of，um and without going into that i'll just，point out。

again sort of just emphasize again this，filter does not have to be。

negative ones and ones um in general，we're going to be allowing and this is。



![](img/395e120dde62bd3055c1917104f18f93_357.png)

actually pretty important that we're，going to be allowing real values。



![](img/395e120dde62bd3055c1917104f18f93_359.png)

for these filter weights so here you，might call them w1 w2 w3 up to w9。

but these are very much operating like，the thetas from before and the bias is。

like the theta naught or the w's from，before and the bias is like the w naught。

um you know we've seen this kind of，template a bunch of times before this is。

just a slightly different way of。

![](img/395e120dde62bd3055c1917104f18f93_361.png)

and it's important that these be real，valued because we're going to try to。

learn them later we're going to try to，do things like gradient descent on them，later。

and so we want them to be able to have a。

![](img/395e120dde62bd3055c1917104f18f93_363.png)

and，you'll be able to take derivatives and，have，valid values for the w's。

okay so this is this is a very general，three by three filter with a bias b。

um again you don't have to have a three，by three filter。



![](img/395e120dde62bd3055c1917104f18f93_365.png)

know，um have like a two by two filter。

![](img/395e120dde62bd3055c1917104f18f93_367.png)

so here we would just have four weights，w one w two w three w four。



![](img/395e120dde62bd3055c1917104f18f93_369.png)

i could have a four by four filter it，could go from w1 up to w16。



![](img/395e120dde62bd3055c1917104f18f93_371.png)

and certainly you know that would make，more sense as i got to，larger images images that weren't just。

five by five images but that would be，you know something that most images that。

we would encounter would probably be，bigger than five by five，uh oh。

sorry just go for it yeah the question，was just basically how do you determine。



![](img/395e120dde62bd3055c1917104f18f93_373.png)

the values of the filters，such that they allow the cnns to learn，the specific。

image properties great yeah so i think i，think the premise of this question alone。

is already a a nice point and i want to，you know abstract it。



![](img/395e120dde62bd3055c1917104f18f93_375.png)

um so we are going to determine the，weights of the filters we're going to，learn。

the weights of the filters so one the，way you can think about a lot of the，class。

is that we first start by specifying a，forward model we say for instance for。

linear regression if i have some data，and i have some parameters i can now。

decide what do i do for my prediction。

![](img/395e120dde62bd3055c1917104f18f93_377.png)

on that set of data for those parameters，once i specify that。

and i specify a loss i'm able to go back，and learn，the parameters by trying to basically。

minimize the training laws，and we're going to do the same thing，here we're going to say first we're。

going to build up this forward model，that says hey。



![](img/395e120dde62bd3055c1917104f18f93_379.png)

if i had some data and i had some，parameters，what is my label on a new data point。

going to be and so that's essentially，what we're working on right now that's。

what we're going through right now，um and then once i have done that and i，have specified a loss and。

at this point you're sort of familiar，with a lot of losses that we might。

choose like if i'm doing regression i，might do，the squared error loss if i'm doing。

classification i might do something like，you know a negative log likelihood loss。

or you know something along those lines，and then once i have that once i have。

the loss on my training data i can，minimize it and so this will be no，exception to that。

um it's always the case that the math，for minimization might look a little bit，different。

um but even then we tend to be applying，things like gradient of sentence to。

casted gradient descent for that，minimization，um and so a lot of it looks very similar。

it's just sort of like what do those，gradients，look like um and and that is exactly。

what we'll be doing here。

![](img/395e120dde62bd3055c1917104f18f93_381.png)

![](img/395e120dde62bd3055c1917104f18f93_382.png)

okay so the reality is you know we think，of all the images，we see a as being two-dimensional but。

the reality is most images that we see，um are probably best described as。

three-dimensional and the reason for，that，is that they don't just have a width and，a height which。

is what we're very used to thinking，about but they also have a depth。

because if they are in color they have，the encoding of that color so for。

instance we might have a red a green and。

![](img/395e120dde62bd3055c1917104f18f93_384.png)

a blue value，for each one of our pixels and so as。

![](img/395e120dde62bd3055c1917104f18f93_386.png)

soon as we have those three values，for each pixel we further have the depth。

and in particular if it's red green blue，that depth has size three。

and so even though when you hear 3d，image i think you tend to think like oh，something that looks 3d。

or you know has some cool property what，i really mean here is an image that。

you're familiar with like it's like the，computer screen that you have。

right now is a 3d image what you're，looking at right now。



![](img/395e120dde62bd3055c1917104f18f93_388.png)

is a 3d image just because each pixel，has these red green blue values that。



![](img/395e120dde62bd3055c1917104f18f93_390.png)

describe the color or something similar，to that，and so for that reason we often want to。

think about 3d images，um and you can think of these 3d images，as being a generalization of concepts。

that you've seen before，so when i think of a structure，that is a list of numbers i'm thinking，of。



![](img/395e120dde62bd3055c1917104f18f93_392.png)

you know a 1d image it's a vector，when i think of a structure that is a，list of list of numbers。

and they all have the same size then i'm，typically thinking of a 2d。



![](img/395e120dde62bd3055c1917104f18f93_394.png)

structure and it's a matrix so i could，have something like，um for a vector i would just have maybe。

the width of that vector or the length，of that vector，so it has one dimension and i think of a。

height，of the matrix and that describes the，matrix the size and that's two。

dimensions and now a tensor is just the，three-dimensional generalization。

i have a width i have a height but i。

![](img/395e120dde62bd3055c1917104f18f93_396.png)

also have a depth，now that's a little bit hard for me to，draw all the numbers for um。



![](img/395e120dde62bd3055c1917104f18f93_398.png)

and part of that is because again we as，humans as we said before can only see in，two dimensions。



![](img/395e120dde62bd3055c1917104f18f93_400.png)

um and so even getting into three，dimensions sometimes can be a little bit，challenging um。

but this is certainly an idea that comes。

![](img/395e120dde62bd3055c1917104f18f93_402.png)

up a lot in image processing，and beyond for images one reason that it，comes up a lot。

is what we've just seen that typically，images are expressed in a way that they，also have。

a depth specifically just because of，that color encoding。



![](img/395e120dde62bd3055c1917104f18f93_404.png)

um we'll see in a moment why we also，might care about these tensors。

um even if we were working just with，two-dimensional images it's gonna come，up。



![](img/395e120dde62bd3055c1917104f18f93_406.png)

um because tensors are so big and you，in，neural nets and convolutional neural。

nets and so on you see this word bandied，about a lot so for instance an example，of this would be。

the the software or the platform，tensorflow，so this is very common to use for，something like。

neural nets but also more general，machine learning and you can see sort of。



![](img/395e120dde62bd3055c1917104f18f93_408.png)

you know where that logo might be coming，from and why it's being called。



![](img/395e120dde62bd3055c1917104f18f93_410.png)

tensorflow and just as we had，one-dimensional filters and，two-dimensional filters we could also，have。

three-dimensional filters and so i'm，just gonna give sort of a，sort of geometric intuition for this。

rather than running through the numbers，like we did before，but it's all the same we would take our。

filter we would go to our image and we。

![](img/395e120dde62bd3055c1917104f18f93_412.png)

would say hey for this image，this。

![](img/395e120dde62bd3055c1917104f18f93_414.png)

size to align with the image，and then we would step through the。

pixels of that image or the the items，that are in，the width and the height and the depth。

the elements of the tensor，and so we would just step slowly through，just like we did before。

we would apply again this notion of a，convolution and we would get out。

again something that you know has this，width and height and depth especially if，we apply padding。

okay we would do this all throughout you，know even down at the bottom um and we，would get out。

our output okay so now i said that，there's another way that tensors arise。



![](img/395e120dde62bd3055c1917104f18f93_416.png)

and so let me mention that as well，so even if i have a two-dimensional。

image something that i might do is i，might apply multiple filters。

so maybe i apply my first filter and，it's something like uh，you know a point detector like we had。

before and maybe let's call that filter，f1 and maybe i apply another filter。

that's like an edge detector，that's we could call that f2 then maybe，i apply another filter。

which is maybe a different type of edge，detector maybe one of them is a。

horizontal edge detector and one's a，vertical edge detector，and so i have all these different。



![](img/395e120dde62bd3055c1917104f18f93_418.png)

i，put these filters together i have a，bunch of two-dimensional images。

so when i put them together i have a，depth which makes this into，in some sense a certainly a。

three-dimensional structure and you，might think of it as a three-dimensional。

and so this collection of filters in the，layer，all these different filters f1 and f2。



![](img/395e120dde62bd3055c1917104f18f93_420.png)

and f3 might be called a filter bank，and each of their outputs might be。

it's just some some terminology but we，see that this is another way that。

tensors arise so even if you're working，just with one-dimensional images or，two-dimensional images。



![](img/395e120dde62bd3055c1917104f18f93_422.png)

you might well find yourself dealing，with tensors，um and doing you know further operations。

on these tensors after this particular。

![](img/395e120dde62bd3055c1917104f18f93_424.png)

okay so at this point we we have these，filters，they detect various things in the image，potentially。

and now we want to ask what do we do，with that you know you know maybe i've，defined。

you know i've defined my filter that，detects dots or detects edges or，whatever。

it is um and it's done its work and it's，detected some dots or some edges。

and now i want to ask you know okay i've，detected these things what do i do with，might。

pull them together i might say hey in，this little area of the image。

did i detect any dots did i detect any，edges，and i sort of asked myself over this，whole area。

what did i detect and so this will be，the idea，of a max pooling layer so here's a。

two-dimensional example，you can think of this as being the，output from our previous layer so。

remember you know，one thing that we're doing in this，lecture is we're building up lots of。

layers we're not you know keeping，ourselves to just one layer，and so we're thinking of you know hey。

i've applied my convolutional layer with，its，you know filter in this case um i，applied my um。



![](img/395e120dde62bd3055c1917104f18f93_426.png)

my relu activation function and this is，what i might have gotten out and i，notice。



![](img/395e120dde62bd3055c1917104f18f93_428.png)

hey there are actually a few ones that，popped up，something was detected it would be nice。

to say hey in this little area of the，image，was anything detected and so that's what。

we're going to be doing with a max，so in particular with the max pooling，layer。

it's going to return the max of its，arguments。

![](img/395e120dde62bd3055c1917104f18f93_430.png)

so we're going to do sort of a similar，thing to what we did before we're going，to specify。

um sort of a subset of the image size，let's say，size three by three and this will often。

be a square and so we might just call it。

![](img/395e120dde62bd3055c1917104f18f93_432.png)

again，go to our image we'll take a little，subset of the image。

so here's a you know that subset that we，had before，um and we'll ask ourselves now to apply。

the max pooling layer so in the max，pulling layer we just look at the maps。

of the arguments and so in this case，when we apply our our max pooling。



![](img/395e120dde62bd3055c1917104f18f93_434.png)

instead of our filter，we're just going to get a zero because。



![](img/395e120dde62bd3055c1917104f18f93_436.png)

now we could do the same thing that we，did before we could step over by one。

and apply max pooling again and again，it's just a bunch of zeros so we're。

gonna get an output of a zero。

![](img/395e120dde62bd3055c1917104f18f93_438.png)

we could step over by one apply max，pooling again and say what's the max of。

all these numbers now we've got a one，so we're gonna output a one we could。



![](img/395e120dde62bd3055c1917104f18f93_440.png)

step over again and say what's the max，of these numbers it's 1。

and we could do the same thing we could。

![](img/395e120dde62bd3055c1917104f18f93_442.png)

step over everything you know even at，the very bottom here。



![](img/395e120dde62bd3055c1917104f18f93_444.png)

and just ask what's the the max in this，little subset of the image and certainly。

that was something that we did with the，filter was we just sort of。

you know stepped through the image um，and and asked hey if i apply this filter。

what happens and now we're saying hey if，but，you know if you think about it um kind。

of what we're doing with the max pooling，is we're asking ourselves。

did i detect something by taking the max，and asking if it's non-zero i'm sort of。

asking was there any detection and so，from that perspective。



![](img/395e120dde62bd3055c1917104f18f93_446.png)

when i just step by one i'm kind of，question，of a lot of pixels i might instead want，to just say hey。



![](img/395e120dde62bd3055c1917104f18f93_448.png)

in this little area of the image did i，detect anything now in this little area。

of the image that's separate did i，detect anything now in this area of the。

image that's separate did i detect，anything，and so i might do that instead so if i。

do that if i if i sort of skip ahead，then i'll say that i have a different，stride。

so you can think of all of the things。

![](img/395e120dde62bd3055c1917104f18f93_450.png)

that we did so far，the max pooling on this slide but also，um the filters on the previous slides is。

having a stride of one and what i mean，by stride of one，is that we looked at a subset of the。



![](img/395e120dde62bd3055c1917104f18f93_452.png)

image that fit our filter or our max，pooling，and then we stepped over one pixel and。

then we did it again，if we had a different stride we would，step over a different number of pixels。

so let's look at an example of that，instead of a stride of one。

let's instead look at a stride of three，so in this case a stride。

three would be really you know sort of，natural because our our max pooling。

has size three and so we're going to ask。

![](img/395e120dde62bd3055c1917104f18f93_454.png)

of you know one，set of the image whether something，happened and then we'll go to a。

different part of the image，so let's look at a stride of three you，know what would the output。

be like here how would things be，different if we had a stride of three。

well we'll still start in the corner of，the image and we'll say okay this is。

this is our max pooling size it's three，by three，i'm gonna apply max pooling and i'm。

going to get a zero because the max of，everything that's in that three by three，area is zero。



![](img/395e120dde62bd3055c1917104f18f93_456.png)

and now i'm gonna start stepping。

![](img/395e120dde62bd3055c1917104f18f93_458.png)

i'm gonna step by one i'm gonna step by，two i'm gonna step by three。

and now that i've made three steps，three pixels over because this is a。

stride of three i will again apply max，pooling and i will say okay for this，anything。

is there anything that's above zero in，fact there is the max of this。



![](img/395e120dde62bd3055c1917104f18f93_460.png)

and i can do the same thing in the other，direction i can say okay this is where。

you know i was applying max pulling，before and now i'm going to step by one。

i'm going to step by two i'm going to，step by three，and now i will apply max pooling again。

and i will say okay what's the max，of what we have in of the pixels that，we're seeing here。

we have a bunch of zeros but we have a。

![](img/395e120dde62bd3055c1917104f18f93_462.png)

and then finally i step by one i step by，two i step by three i could have also，stepped from above。



![](img/395e120dde62bd3055c1917104f18f93_464.png)

it'll be the same thing and now that，i've taken my stride of three。

i can again ask okay well what happens，when i do this max pooling，i get the max of all the zeros and。



![](img/395e120dde62bd3055c1917104f18f93_466.png)

okay now in this case we've dramatically，max，pooling layer that's actually something。

that we're often looking for，um so with the filtering we're sort of。

saying hey you know were there things，that happened at any of the pixels that，we have。



![](img/395e120dde62bd3055c1917104f18f93_468.png)

with max pooling we're really sort of，you know combining this information。

we're saying hey in these different。

![](img/395e120dde62bd3055c1917104f18f93_470.png)

areas did something happen，um and maybe there aren't so many areas。

as before and so we get something that's。

![](img/395e120dde62bd3055c1917104f18f93_472.png)

quite a bit smaller potentially，and you can imagine doing this to build，up larger and larger。

you can also use stride with filters we，didn't talk about that in this lecture。

but it's certainly something you can do，you could apply a filter after some，strides。



![](img/395e120dde62bd3055c1917104f18f93_474.png)

um but i think that the way that we've，talked about it is a sort of natural way。



![](img/395e120dde62bd3055c1917104f18f93_476.png)

a way that you might choose to use，strides and filters and max pooling。

something that's also worth noting is，that there are just no weights。

in max pooling um there was nothing，here that was a value that we were，interested in changing。

that we were trying to learn um we set，these sizes we set these strides。

there's there's no sort of real valued，parameter that's sitting around here。



![](img/395e120dde62bd3055c1917104f18f93_478.png)

um and so in this case we're not going，to have something that we're going to go。



![](img/395e120dde62bd3055c1917104f18f93_480.png)

back later and say okay，let's you know radiate descent our way，to learn some parameters there just。



![](img/395e120dde62bd3055c1917104f18f93_482.png)

weren't any，okay so let's let's bring this all，together then，what would a typical architecture look。

like，for convolutional knowledge well，first you have your input so here you。

can see there's sort of this picture of，a car，that could be potentially an input to a。

convolutional neural network。

![](img/395e120dde62bd3055c1917104f18f93_484.png)

and here you can see that there is a，filter，in this case in three dimensions because。

you can see that car has the three，dimensions probably because it's。

some kind of color picture so it has you。

![](img/395e120dde62bd3055c1917104f18f93_486.png)

know a depth of three for each of its，pixels，and you can see that filter going over。

it and coming out with some output in a，convolutional，and reload layer now once we have that。

convolutional and relu layer，a typical thing is to have a max pooling。

layer and you can see again that that，max pooling layer is going to，dramatically reduce。

the size of the layer that would be a，something that we might see。

now once we've done that you know maybe，we've detected edges，or we've detected dots or we've done。

whatever now we can have another，convolutional，and relu layer and that might detect。

some combination of edges there's some，combination of dots，because now each of our pixels is。

essentially a detection of an edge or a，dot so we can get these sort of。

you know slightly higher order features，now we have a max pooling layer and now。

we can detect combinations of。

![](img/395e120dde62bd3055c1917104f18f93_488.png)

combinations of edges or combinations of，that。

![](img/395e120dde62bd3055c1917104f18f93_490.png)

over time these become features that，really matter you know maybe we're，starting to detect a tire。

or we're detecting you know something，something that is actually a you know。

useful feature for what we're doing，and so we do this a bunch we do these。

layers of bunch that's sort of the dot，dot dot after the max pool。

finally eventually we have a bunch of，values，and we're going to treat those as our。

final features and so we're going to，take them out of this tensor we're going。

to flatten them into a vector，that is to say we'll just take the，values of the tensor in some order。

treat those as features in a typical，classification，and so now this finer layer is just。

exactly what we've been doing for many，classes，we have a fully connected layer。

so that could be interpreted as logistic，regression it could be interpreted if we，were doing。

just regular regression as a linear，regression in this particular case this。

is a classification problem and so we，might be doing。



![](img/395e120dde62bd3055c1917104f18f93_492.png)

um you know some form of logistic，regression in this case with multiple，classes。



![](img/395e120dde62bd3055c1917104f18f93_494.png)

so we have this fully connected layer，and then finally we apply in this case a，softmax function。

to get our prediction so because we're，using softmax our predictions will be。

sort of soft predictions they'll be，saying what's the probability of this。

being a car what's the probability of，this being a truck what's the，probability of this being a van。

or a bicycle or you know whatever the，the set of possible options。



![](img/395e120dde62bd3055c1917104f18f93_496.png)

okay and so we now just have a lot more，that's going on，in the feature learning in the previous。

class we had just one layer that was，doing the feature learning。

um it was this fully connected layer and。

![](img/395e120dde62bd3055c1917104f18f93_498.png)

there，um and and we saw what to do with that，and here there's just a much。

richer sort of set of layers that are，going into that feature learning。

um and and when we say that there's，choose，those weights later so first we build up，again this model。

and then we're going to choose the，weights and then，what hasn't changed is that that output。

layer is still，the same it's still doing classification，and still doing the thing that we saw in。

logistic regression and still doing the，thing that we saw in our neural networks。

for the output layer in our previous，neural networks lecture and so that's。

all the same it's really this feature，construction，that has changed and so we have。

specified at this point，a way to take a data point x，so that's our our image in this case um。



![](img/395e120dde62bd3055c1917104f18f93_500.png)

it's the image of a car in this，particular slide but in general it's。

you know whatever image input we have，and we specified a way to turn it into a。

prediction and we might call that neural，net，um this is a neural net um but of course。

we've seen that there were a lot of，choices that went in along the way and，say。

you know what was the architecture you，used what was um，the filter set that you used what was。

the filter bank that you used um，did you use max pooling you know what，they。

um and so there's sort of a lot more to，specify than we did，have to then we had to specify in the。

case of linear regression or logistic，regression，but once we do that we have a prediction。

it depends on the data point that we put，in and it depends on the parameters。

and so now we can go back and learn，those parameters and so let's just，briefly sort of recap。

you know how this relates to the things，that we've seen in this course there's。

there's really this familiar pattern，at this point hopefully familiar。

so in particular we start by choosing，how to predict a label it depends so。

this is the label for a particular data，point so it depends on the features of。



![](img/395e120dde62bd3055c1917104f18f93_502.png)

that data point，and it depends on the parameters in，general，so an example of this let's say we had。

our data point an example of this was，logistic regression we said for the ith。

data point we'll use logistic regression，the i，point and that might take the form of。



![](img/395e120dde62bd3055c1917104f18f93_504.png)

probabilities over particular classes，now once we take this over all of the，different points。

one through little n and once we choose，a loss。

![](img/395e120dde62bd3055c1917104f18f93_506.png)

between our prediction our guest label，and our actual label。



![](img/395e120dde62bd3055c1917104f18f93_508.png)

we can get a training loss so we can get，and then the final thing we've been。

doing is we've been coming up with ways，to choose the parameters。

to try to minimize the training laws，now we might also have a regularizer in。

here but it's still we're trying to，choose a set of parameters that minimize。



![](img/395e120dde62bd3055c1917104f18f93_510.png)

times，in this class we said okay another，option is linear regression。

we chose how to predict a label we said，we're going to use linear regression。

that tells us given a set of data，features and a set of parameters。

what is our prediction for the eighth，point we chose a loss，for instance it might be squared error。

loss in the case of linear regression，once we have that loss we can go over。

every single point not just one，particular point but one up to little n。

and we can calculate our training loss，for a particular set of parameters and。

then we can move around in the parameter，space in step three，to try to choose parameters that are。

better and our notion of better is，minimizing this thing that's like a，training loss。

and i say like just because there could，also be a regularizer there。



![](img/395e120dde62bd3055c1917104f18f93_512.png)

okay and then we did it again so all，we're doing，in neural nets and convolutional neural。

nets is setting up a，different model we're saying hey，now the way that i'm going to predict。

for the ice data point is i'm going to，and that's going to depend on some。

parameters and it's going to depend on，the data point，once i have chosen a loss and these will。

be familiar losses you know again，something like squared error loss for，regression。

or negative log likelihood loss for，classification，then i will have a training loss over。

all my points that'll be a function of，my parameters，and so i can ask myself if i move around。

in this parameter space can i do better。

![](img/395e120dde62bd3055c1917104f18f93_514.png)

can i get a lower training loss and，that's what we're doing with things like。

gradient descent and stochastic gradient，design we're just moving around and，asking hey can we get。

thing that。

![](img/395e120dde62bd3055c1917104f18f93_516.png)

is a bit different in neural nets，versus logistic regression or linear。

regression is that you can't just say，neural nets and you fully specify。



![](img/395e120dde62bd3055c1917104f18f93_518.png)

what you're doing you know as we've seen，at this point there's a lot of different。

things that you can do。

![](img/395e120dde62bd3055c1917104f18f93_520.png)

layer，fully connected you know way of，specifying the features，you could instead learn the features。

with this convolutional world net，there are actually lots of other things。

that you could do that we haven't even，talked about，um and so one difference is to fully。

specify what you're doing to fully，specify your model，to be really clear and reproducible you。

want to say，all of those details of your，architecture um and the best thing you，can do of course。

in general to be reproducible is to，okay so this is a familiar pattern and，now let's just look。

in a tiny bit more depth at what might，have changed when we're applying。

something like gradient descent or，stochastic gradient descent。



![](img/395e120dde62bd3055c1917104f18f93_522.png)

in the case of convolutional neural nets，versus the neural nets that we've。



![](img/395e120dde62bd3055c1917104f18f93_524.png)

so in order to do that we're going to，look at a particularly simple case。

just as an example we're going to look，at a regression case，with a single filter that has size 3。

we'll ignore max pooling for the moment，we'll assume that we have padding。

so that our output image from this first，layer of constructing a feature is the，same size。



![](img/395e120dde62bd3055c1917104f18f93_526.png)

as our original image and we'll assume，our data points，have dimension five they have five。



![](img/395e120dde62bd3055c1917104f18f93_528.png)

features again just for concreteness，okay so here's here's what a forward，pass aka just。

so first we're going to apply our filter，so this is what we saw before。

in um in images and now we're just，writing out the words for what that。

might look like so we're going to say，that the i。

![](img/395e120dde62bd3055c1917104f18f93_530.png)

preactivation is the application of the，filter which is given by w1。

and then we dot product that with the x，elements but they are changing。



![](img/395e120dde62bd3055c1917104f18f93_532.png)

so the i pre-activation has gotten from，the elements of x that are around i。

essentially and because this has a，filter of size 3 that's why we're。

looking at i minus one i and i plus one，and this is a one-dimensional image。

because it's just dimension five by one。

![](img/395e120dde62bd3055c1917104f18f93_534.png)

okay we apply our activation function，are，basically you know our learned features。



![](img/395e120dde62bd3055c1917104f18f93_536.png)

once we learn the w's，now we're going to have our layer that，does either the regression or the。

classification because we're doing，regression，we don't have to worry sort of about。

activation function because it's just，going to be the identity。

um so that's implicit in here and we're，just going to have this。

linear combination with the ais in this，particular，case there are no biases i'm just going。

to ignore them for the moment and then，finally we have some loss because we're。

doing regression we might choose a。

![](img/395e120dde62bd3055c1917104f18f93_538.png)

squared error loss，um but of course uh here we're getting，into this notation we've been seeing。

this class where，a2 that's just a superscript but the 2，that's a superscript outside is a square。

and so you just want to keep those。

![](img/395e120dde62bd3055c1917104f18f93_540.png)

okay so let's briefly check um，first of all what is going to be the，size，of z1 as a vector。

so once we apply this filter we get our，pre-activations，z super one is a vector what is its size。

okay great so a number of people are，saying it's five by，image，specifically because we chose enough。



![](img/395e120dde62bd3055c1917104f18f93_542.png)

image，so if we just applied a filter of size，three to our image and we didn't do any。

padding this wouldn't necessarily be the，case but because we chose enough padding。



![](img/395e120dde62bd3055c1917104f18f93_544.png)

we will get this five by one so sort of，by design，so now we apply the relu so we're gonna。

get a five by one，vector there as well finally we apply，this weeding and so we get out now。

a one by one vector because this is just，the label，for our data point in regression we're。



![](img/395e120dde62bd3055c1917104f18f93_546.png)

just giving it some label，we're assuming w2 is going to be um，basically five by one。

so this will just be a dot product and，we'll get out of label。



![](img/395e120dde62bd3055c1917104f18f93_548.png)

and then finally our loss is also a，scalar now something you might notice。

here is that three doesn't seem to，appear anywhere and that's because it's，in the filter。

so it's in the definition of zi and each，eye，we're essentially taking a dot product。

okay so now if you were doing stochastic，gradient descent，in order to try to figure out how to。

minimize you know，this um this loss over all the data，points not just a single data point but。

over all the data points，then you might do um stochastic gradient，descent try to minimize this loss。

and you might do it for both w1 and w2，so i'm saying part of the derivative for，moment。

just on w1 of course you would do both，if you're doing regular sgd but i'm just。

going to focus on the part with respect。

![](img/395e120dde62bd3055c1917104f18f93_550.png)

to w1，now just as before we can apply。

![](img/395e120dde62bd3055c1917104f18f93_552.png)

so just as we did for the case of you，know certain vanilla neural networks。

fully connected neural networks，we can apply the chain rule，and so in particular we're going to say。

okay the loss is a function of a，it's a function of both a2 and a1 but。

let's go straight to a1 you could even，apply the chain rule within。

this term but i'm just going to say it's，a function of a1 so we can take the。

derivative of the loss with respect to，a1，a1 is a function of z1 so i can take the。

derivative of a1 with respect to z1。

![](img/395e120dde62bd3055c1917104f18f93_554.png)

and z1 is a function of w1 so i can take。

![](img/395e120dde62bd3055c1917104f18f93_556.png)

okay and now we want to check that our，dimensions work out，so what is the dimension of the gradient。

of the loss，with respect to w1 can anybody say in。

![](img/395e120dde62bd3055c1917104f18f93_558.png)

okay so this one's a little bit tricky。

![](img/395e120dde62bd3055c1917104f18f93_560.png)

remember w1 we're taking a dot product，of that with a three long。

snippet of x and so w one has got to be，size，three now a way that you can think about。

these derivatives，in general is that you're taking the，derivative。

you're taking uh um this gradient of a，vector with respect to a vector。



![](img/395e120dde62bd3055c1917104f18f93_562.png)

the vector on top is going to tell you，the second，size and the vector on the bottom is。



![](img/395e120dde62bd3055c1917104f18f93_564.png)

going to tell you the first size，so because w one has length three。

we're going to have three by something，because the loss is a scalar。

so it has size one this is gonna be，three by one，of these，so z and w well w。

one is on the bottom it has length three，so it's going to be a three by something，vector。

z is on the top it has length five so。

![](img/395e120dde62bd3055c1917104f18f93_566.png)

this is going to be the length of z by，the length of a。



![](img/395e120dde62bd3055c1917104f18f93_568.png)

so it'll be a 5 by 5 vector and finally，the loss，d a is going to be the length of a by。

the length of the loss so it's going to，be a 5 by 1 vector and then you can just，check out。

you know all those inner dimensions，agree and this is something that will。

okay so let's look at what would dz dw，look like here well we already said it's。



![](img/395e120dde62bd3055c1917104f18f93_570.png)

going to be three by five，so it's going to be the three elements，if we want to fill in one of its。

elements。

![](img/395e120dde62bd3055c1917104f18f93_572.png)

that's going to be the particular，element of z，case，essentially the second element of z with，the。

now in order to calculate that it will，help us to remember what is z as a。

function of w and so here i've just。

![](img/395e120dde62bd3055c1917104f18f93_574.png)

written out that forward pass，z sub 2 as a function of the w's and the。

x's with the i is sort of filled in so，i'm taking i equals 2 here。



![](img/395e120dde62bd3055c1917104f18f93_576.png)

from what's above and so if you look，at this formula can you tell me what's。

the derivative of z2 with respect，okay great lots of great answers here，it's going to be x3。

because we just read that off straight，from the formula，you can do the same thing and it's worth。

checking for yourself，that you're going to get x2 and x1 here，and you can fill in all the other。

elements in this matrix and something，that's pretty interesting here is like。

you're seeing a wave of x's，you're getting a lot of x's repeated in。

a way that we didn't see before for，neural networks，and that's because we're moving this。

filter along in a way that we weren't，before。

![](img/395e120dde62bd3055c1917104f18f93_578.png)

five，and so what does x0 or x6 mean if x，already，if x just goes from one to five can you，tell me。



![](img/395e120dde62bd3055c1917104f18f93_580.png)

it's great it's the padding so when what，we're doing when we're adding padding。

is we're essentially increasing the size，of x just for the purposes。

of our algorithm and that's what's，happening here and that's what i mean by，x0 and x6。

i mean that we're bringing in the。

![](img/395e120dde62bd3055c1917104f18f93_582.png)

padding，then we would get a different size，derivative here and we wouldn't get。



![](img/395e120dde62bd3055c1917104f18f93_584.png)

okay so this is just to illustrate how，back propagation，is mostly the same certainly the way。

that you apply it is the same you're，just calculating these derivatives。

you're just doing gradient descent as，before for neural networks。

but the results of that are going to，look a little bit different and in，particular。

this dzdw term is going to look a little，bit different and it's worth reflecting，on that。

okay so at this point we talked about，not just neural networks of one layer。

like logistic regression or linear，regression not just neural networks of。

two layers with a fully connected，network which is what we did last time。



![](img/395e120dde62bd3055c1917104f18f93_586.png)

now，deep neural networks there are multiple。

![](img/395e120dde62bd3055c1917104f18f93_588.png)

hidden layers that construct the，features，um we've done this with a real focus on。

images um and certainly convolutional，that's are really widely used in image，processing。



![](img/395e120dde62bd3055c1917104f18f93_590.png)

um and uh and so we have we have built，up to this thing that is really，behind。

all this excitement and ai um and so。

![](img/395e120dde62bd3055c1917104f18f93_592.png)

hopefully hopefully you found that to be，an exciting thing。



![](img/395e120dde62bd3055c1917104f18f93_594.png)