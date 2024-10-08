# 【双语字幕+资料下载】CS231n进阶课 ｜ 深度学习与计算机视觉(2019·全22讲) - P15：L15- 目标检测 - ShowMeAI - BV13P4y1t7gM

all right well look welcome back to，all right well look welcome back to，lecture 15。

uh today we're going to talk about，object detection um so as a reminder。

that last time we were talking about，this task of，understanding and visualizing what's。

going on inside our convolutional neural，networks，and we talked about a lot of different。

techniques for doing exactly that like，looking at nearest neighbors in feature，space。

by looking at maximum activating patches，or using guided back propagation or。

other techniques to compute saliency，maps on our features，and we talked about methods for。

generating images like these，synthetic images via gradient descent or。

these uh this task of feature inversion，um and of course we also saw that a lot。

of these same techniques that could be，used for understanding cnns。

could also be used for sort of making，fun artwork with convolutional neural，networks。

so we saw the deep dream and the style，artistic style transfer algorithms。

as mechanisms as mechanisms for，generating artwork with，neural networks and now today we're。

going to talk about something maybe，a little bit more practical which is a。

new core computer vision task of，object detection so basically the main。

computer vision task that we've talked，about so far in this class。

is something like image is something，like image classification，right so an image classification of。

course we know that a single，image is coming in on the left we。

process it with our convolutional model，and it outputs uh some cl some category。

label for the overall image，like maybe classifying it as a cat or，dog or car。

just giving we're in image，classification we're just giving a，single category label。

attached to the entire image as a whole，and this has been a really useful。

this is a really useful task that has a，ton of applications for a lot of，different settings。

and it's also been a really useful task，for under for kind of stepping through。

the whole deep learning pipeline，and understanding how to build and train。

convolutional neural network models，but it but it turns out that this image，classification task。

is only one of many different types of，tasks that people in computer vision，work on。

so there's a whole hierarchy out there，of different types of tasks that people。

work on in computer vision，that try to identify objects and images，in different sorts of ways。

and in particular in today's lecture and，in the next lecture on monday。

we'll talk about different types of，computer vision tasks that involve。

identifying spatial extents of objects，in images，so for of course for the classic image。

classification task，we're simply assigning a category label，to the overall image。

and we're not saying at all which pixels，of the image correspond to the category，label。

which is attaching a single overall，label to the image，now other types of computer vision tasks。

actually want to go farther，and not just give a single overall，category label but actually want to。

label different parts of the image，with different categories that appear in，the image so。

between today's lecture and next lecture，we'll talk about all of these different，tasks。

but the one that i want to focus on，today is the task of object detection。

which is kind of which is sort of a，super core task in computer vision。

that has a ton of useful applications so，what is object detection。

uh object detection is a task we're，going to input a single rgb image。

and the output is going to be a set of，detected objects，that for each object in the scene we。

want our model to identify all of the，all of the interesting objects in the，scene。

so for each of so for each of the，objects that we detect we're going to，output several things。

one is a category label giving the，category of，the of the detected object and the other。

is a bounding box，giving the the spatial extent of that，object in the image。

so uh with on the category labels just，like with image classification。

ahead of time we're going to pre-specify，some set of categories，that the data that the model will be。

aware of um so，in something like remember in something，like cpar classification our model is。

aware of，10 different categories for cfr cfr10 in，something like imagenet classification。

our model is aware of a thousand，different categories，well for object detection we'll also be。

aware of some fixed set of categories，ahead of time，and then for each of our detected。

objects we're going to output some，did，with image classification but now the。

interesting part is this bounding box，that it's going where the model needs to。

output a box telling us the location of，each of the detected objects in the，image。

and these bounding boxes we can prim we，usually parametrize，with four numbers um the that's that's。

like the x and y giving the center of，the box，in pixels and the width and the height。

giving the and w and h giving the width，and the height of the box again measured，in pixels。

um so you could imagine you know models，that produce sort of arbitrary boxes。

with arbitrary rotations，but for the standard object detection，task we usually don't do that。

and instead usually only define boxes，only output boxes that are aligned to。

the to the axes of the input image so，that means that whenever we're working，with bounding boxes。

we can always define a bounding box，using just four real numbers。

so now this this seems like a relatively，small change compared to image，be。

we're just now we need to just output，these boxes in addition to the category，labels。

well it turns out that that adds a lot，of complication to the problem。

so a couple of the a couple of the types，of problems that we need to deal with。

once we move to object detection，well one of the biggest ones is this，idea of multiple outputs。

that with image classification our model，was always outputting a single output，for every image。

which was a single category label but，now with image classification。

we need to output potentially a very we，need to output a whole set of detected，objects。

and each object each image might have，different numbers of detected objects。

might have different numbers of objects，in it that we need to detect。

so now somehow we need to build a model，that can output a variably sized number，of detections。

which turns out to be quite challenging，of course there's another problem。

here which is that for each object in，this set we need to produce two types of，outputs。

one is this category label that we're，very familiar with and the other is this。

bounding box object so now we need some，other way to deal with。

processing bounding boxes inside of our，network and then another kind of。

computational problem with object，detection is that it typically。

requires us to work on relatively high，resolution images，so for something like image。

classification it turns out that，relatively low resolution images of like。

two to four by two to four pixels，tends to be enough spatial resolution。

for most of the image classification，tasks that we wanna perform。

but now for object detection because we，want to identify a whole。

a whole lot of different objects inside，the image now we we need enough spatial。

resolution on each of the objects that，we want to detect，so that means that the overall。

resolution of the image needs to be，needs to be much higher so as a concrete。

example for object detection models，it's more common to work on images of。

resolution something like a，rather on the order of like 800 by 600，pixels。

so that's like a lot larger image，resolution compared to，compared to image classification so that。

means we can use fewer images per batch，we need to train longer we need to。

use multi distributed gpu training and，that's kind of a computational issue，that makes。

object detection much much more，challenging，okay but i but i think that object。

detection is a really useful problem，right i think there's a lot of cases。

where we want to build systems that can，recognize stuff，in images but actually needs to say。

where it is in the image，so one example might be something like a。

self-driving car that if you're built if，you're building a vision system for a，self-driving car。

it needs to know where all the other，cars are around it in space so therefore。

it becomes really critical，that it can not only just assign single，category labels to images。

but actually uh detect whole sets of，objects and actually say where they are，in space。

so this is so basically after image，classification i think object detection，is maybe the number two。

most core problem in computer vision，these days，okay so then with all that in mind let's。

consider a simpler problem forget about，let's forget for a second about this，this。

set this this problem of producing a set，of outputs and let's think about how we。

might approach this problem，if we just wanted to detect a single，object in the image。

well it turns out that detecting a，single object in the image，we can actually do with a relatively。

straightforward architecture，so here we might imagine taking in our，image on the left。

and assuming that there's only one，object in the image passing it through。

our favorite convolutional neural，network architecture，uh like an alex now or vgg or some kind。

of resnet，that would eventually result in some，vector representation of the image。

and now from that vector representation，we could have one branch that does image。

classification that is saying，what is in the image and this would look。

very much like all of the kinds of image，far，that it's going to output a score per。

category and that's going to be trained，with a softmax loss，on the ground truth category and this is。

basically the same as the image，classification model that we've seen，many times。

but now the new part is that we could，imagine the second attaching the second，branch。

that that also inputs this uh this，vector representation of the image。

and now has a fully connected layer to，go from maybe 40 96 dimensions。

in that final vector representation to，four real numbers，giving the x giving the coordinates of。

the bounding box of that one object，and now this these box coordinates we。

can imagine training with some kind of，regression loss，like a l2 like the l2 difference but。

like the l2 difference between，um this set of four numbers giving the，box that we actually output。

and the set of four numbers giving the，actual coordinates of the box that we，were supposed to detect。

um and then then we could imagine，trading this the second where branch。

with an l with some kind of l2 loss or，other kind of regression loss on real，numbers。

and now the problem is that we've got，two loss functions right because we're。

asking our model to predict two，different sorts of things，one is the category label and one is the。

the bounding box location，and for each of these two things we have，an associated loss function。

but in order to compute gradient descent，we actually need to end up with a single，scalar loss。

we don't know how to deal with sets of，losses so the way that we，overcome this is just add up the。

different losses that we have in this，network，potentially as a weighted sum to give。

our final our final loss，and now this is a weighted sum because，we might need to tune the relative。

importance，of this softmax loss and this regression，loss um to make sure that they don't。

overpower each other in the overall，weighted sum，loss and now this idea of taking。

multiple loss functions，right now now this idea is that we've。

got one network and we want to train one，network to do multiple different things。

so then we attach one loss function to，each of the different things that we。

want our network to predict，and then we sum them up with a weighted。

sum and this turns out to be a pretty，general construction that applies。

whenever you want to train neural，networks that to output multiple sorts，of things。

and this general construction is called，a multi-task loss because um or we want。

to train our network to do sort of，multiple different tasks，all at once but we need to boil it down。

to a single loss function for training，at the end，um and now uh as kind of kind of a cap。

now to kind of see how you might work on，this in practice，um this this backbone network this this。

cnn would often be maybe pre-trained for，imagenet classification。

and then you would sort of fine-tune，this whole network for，uh for doing this this multitask。

localization problem，and this seems like kind of a silly，approach for detecting objects and。

images right it's very straightforward，we're just basically attaching an extra。

fully connected layer at the end of the，network to predict these box coordinates。

but this this relative relatively simple，approach actually works pretty well。

if you know that you only need to detect，one object in the image。

um and for example and actually this，particular approach to uh，to localizing objects and images was。

actually used，in way back in the alex net paper when，they had some tasks where they want to。

classify and also give a bounding box，for the one classification decision that，they make。

so this is actually a reasonable，approach if you know that you only need，to detect。

one object in the image but of course we，know that real images might have。

multiple objects that we need to detect，so this this relatively simple situation。

is not going to work for us in general，and to kind of imagine what this looks，like well we need we。

in general different different images，might have different numbers of objects，that we need to detect。

so for this cat image maybe there's only，one object in there the cat that we need，to detect。

so then we need to predict only four，numbers coming out of our network which。

are the four bounding box coordinates of，the one cat bounding box。

um but now for this middle image maybe，there's three objects we want to detect。

two dogs and one cat so now we need to，predict 16 numbers uh actually i can't i。

can't add right that's only 12 numbers，right 3 times 4 is only 12。 so that's a，bug on the slide。

um that's what happens when you make，slides very fast you have some bugs on，there。

um but uh right so in this case we need，to have our network only output 12。

i'll put 12 numbers and for this this，image of all these adorable ducklings。

floating around in the water with their，mom，there's like a lot of ducks in here i。

can't even count them there's like way，too many，um but basically this means that we need。

our network to output a whole lot of，duck，guck and maybe a goose but there's，actually no goose here。

um so then we need to output maybe lots，of different numbers from our neural，network model。

so then we need some some mechanism that，allows our model to output。

variable numbers of objects for each for，each different image that we might see。

so there's a relatively simple way to do，this which is called a sliding window。

approach to object detection，here the idea is that we're going to，train we're going to have a cnn。

a convolutional neural network and we're，going to train it to do classification。

but now this this cnn that's doing，classification is going to categorize。

a window or sub-regions or sub-windows，of our input image，and now for each sub-window that we。

apply it to it's going to output a，category，it's going to output if we want to。

detect c different categories，we're actually going to output a，decision over c plus one outputs。

where we add a new output for a special，background category，so that means that if we then basically。

this is a this is an image we，are reducing this problem of detection。

down to an image classification problem，so then all we need to do is apply this，classification cnn。

to many many different regions in the，input image and for each region。

that classification cnn will tell us，either is this a dog or a cat。

or is this some background regen where，there is no object that we care about。

um so then you could imagine if we，applied this uh this uh，this sliding window cnn object detector。

to this blue region in the input image，well there's no，object is precisely localized by this。

blue bounding box，so in this so for this image region our，detector should say。

background to mean that there is no，bounding box in this image region。

then we slide our region over and then，image，and this one it should say that there's。

a dog here because this is a this is，about this is a region that is well，localized with um。

with that box and then this one would，also be a dog this one should be a cat。

and then that basically we take this we，take this object detector。

and we slide it over different regions，in the input image and for each of those。

regions we run the cnn on that region，and it tells us whether it's an object。

or whether it is background okay so this，seems like a relatively simple approach。

to doing object detection，but there's a problem let's think about，are。

in an image of size h cross w um and，hint it's going to be a lot。

right so if there's h cross if if we，have an input image of size capital h。

cross capital w then consider a box of，size lowercase h，cross lowercase w now the number of。

positions that we can put this in，well there's capital w minus lowercase w，plus one。

possible uh position x position so we，could put this box，and similarly for the number of y。

positions that we can put this box，so that means that the number of，positions we can put this box in。

is this uh this quadratic equation that，depends both，depends on the the the product of。

capital w and capital h，but but but in fact this is even worse，because we need to consider。

not just boxes of a fixed size we need，to consider all possible boxes of all，possible sizes。

and all possible aspect ratios so if we，sum this thing up over all。

all lowercase w and all lowercase h over，all possible sizes that are less than，the full image size。

then we get this this quartic expression，that sort of，depends on the fourth power of the。

number of pixels in the image or rather，the square of the number of pixels in，the image but。

it's like h squared times w squared so，that's like really really bad。

and how bad is this well if we have，something like an 800 by 600 image。

then it comes out that there's some that，there's about like 58 million different，bounding boxes。

that we could about imagine evaluating，inside this 800 by 600 image。

so if we wanted to do some kind of dense，sliding window approach，and actually apply our cnn sliding。

window classifier，on each one of these possible image，regions this is going to be absolutely。

completely infeasible，there's like no computational way that，we could run our object。

our cnn forward pass 58 million times，just for one image we'd be waiting。

forever for any detections that we，wanted to come out，yeah is there a question yeah the。

question is that even if you could do，this and you had like infinite compute。

you'd probably end up identifying the，same object，over and over again with sort of。

slightly offset windows，and yeah that's exactly correct um，that'll actually turn out to be a。

problem not just for this sort of um，impossible to implement version of。

object detection but that'll actually be，a problem for other uh。

real types of architectures as well so，we'll talk about this idea of non-max。

suppression in a little bit，that can overcome that problem okay so，work。

so we need to do some other approach to，object detection well that brings us to。

this idea of a region proposal，so here the idea is maybe if there's no。

way that we can possibly evaluate the，object detector on every possible region，in the image。

maybe we can have some external，algorithm that can generate a set of，candidate regions for。

candidate regions in the image for us，such that the，the candidate regions gives a relatively。

small set of regions per image，but which are have a high probability of。

covering all the objects in the image，so one of the so there's there's a there，bunch of。

different papers proposing different，mechanisms for generating these，candidate regions。

um called region proposals and i don't，really want to go into any of the。

details of exactly how they work，because spoiler alert eventually they'll。

be replaced by neural networks too，but um for now what you can kind of，these。

sort of early approaches to region，proposals would perform some kind of，image processing based on。

the input image and maybe look for blob，blob type regions in the image or look。

for edges in the input image，or use other kind of low-level image，processing cues to look for image。

regions，that have a high probability of，containing objects so one of these very。

famous methods for region proposals，was this method called selective search。

so selective search was some kind of，algorithm that you could run。

on a cpu and it would give you about 2，000 object proposals，per image in a couple of seconds of。

processing on a cpu，and these 2 000 object proposals that it，would region proposals that it would。

output，would have a very high probability of，covering all of the all of the。

interesting objects that we cared about，in the image，okay so that gives us so then once we。

have this idea of region proposals，it gives us a very straightforward way。

to actually train a practical object，detector，with deep neural networks so that that，brings us to。

the the very famous paper um very famous，method called rcnn，which the r stands for region based this。

is a region-based convolutional neural，network system，for object detection and this is like。

one of the most influential papers i，think in deep learning that came out in，back in cdpr2014。

and since then it's sort of been very，very impactful overall。

so here the but the way that it works is，actually pretty straightforward in a way。

so then what we're going to do is going，to we're going to start with our input，image。

and then we're going to run our um，region proposal method，like selective search so then selective。

search will give us something like 2000，re candidate region proposals in the。

image that we need to evaluate，here we're only showing three because i，can't fit 2000 on the slide。

and then for each of these candidate，image regions on these candidate image。

these region proposals could all be，different sizes and different aspect，ratios in the image。

but then for each of those region，proposals we're going to，warp the that region to a fixed size of。

something like two to four by two to，four and then for each of those warped，image regions。

we're going to run them independently，through a convolutional neural network。

and then that convolutional neural，network will output a classification，score。

for each of these regions um so then，again this classification score。

will tell us um will be a classification，over c plus one categories。

so it will tell us whether or not that，region is a background region with no，object。

or whether it actually should or if it's，not a background region。

then what is the actual image label that，it the category label that region should，be assigned。

and you could imagine sort of training，this thing now using sort of all the。

standard machinery that we know for，training，uh classification networks um and this。

will actually work pretty well，but now there's there's a slight problem，here which is that um。

what happens if the region proposals，that we get from selective search。

do not exactly match up to the objects，that we want to detect in the image。

right because here the entire mechanism，of the bounding the all of the bounding。

boxes are just coming out of this sort，of black box selective search method。

and there's no learning happening that，actually outputs the boxes，so to overcome that problem we're。

actually going to actually，use kind of a multi-task loss similar to，this very simple。

mechanism we saw earlier and now um each，of these in，now this cnn is actually going to output。

an additional thing which is，a transformation that will transform the，region proposal box。

into the final box that we actually want，to output for that object of interest。

um and now this is uh and now because a，bounding box actually is is specified。

or and another thing to i mean one thing，to point out here is this this idea of。

bounding box regression，we're not inventing a box from scratch，instead we just want to modify。

the region proposal that we were given，as input because hope because we think。

that the region proposal was probably，pretty good，but we just might need to tweak it a。

little bit to cause it to fit better the，object that we，that we were looking at and now because。

a bounding box is，can be parametrized with a sequence of，four numbers then we can also。

parametrize a delta on top of an，existing boundary box，also using a sequence of four numbers so。

there's a lot of different，parameterizations of these bounding box。

transformations that you'll see people，use，but i think the most common one is is。

this that i put on the slide here，so here the idea is that if we're given，a region proposal that has。

its center at pxpy and has a height and，width ph and bw，and then if we out if our if our uh。

comnat is outputting a transformation，giving four numbers t x t y t h and t w。

then we are going to output then our，final output box，is going to somehow combine the。

transformation that our cnn outputs，and the coordinates of the region。

proposal that we were given as input，and and the the parameterization here is。

going to be relative to the overall box，size in translation，so that means that if if now then the x。

coordinate of our output bounding box，will be um t x time will be the original。

out the original x coordinate of the of，the region proposal，plus the x transform times the width of。

the box，so that means that if we and，parametrizing these things relative to。

the input bounding box size，kind of makes it work out because of the。

fact that we had to warp the original，image regions before feeding them into，the cnn。

so that kind of means that these，transformations that we're outputting。

are kind of invariant to the fact that，we had to warp the original input，regions。

so what that means here is that if we，were to output like a tx of zero。

that means leave the original region，proposal alone in，x position that means it was pretty good。

and if we output tx equals one，that means i want to shift over the，region proposal by an amount in x。

equal to the width of the of the image，region um and then，we use a similar transform for。

transforming things in the vertical，direction，and now for the scale it's going to be。

logarithmic so then um we're going to，scale up the width or the height of the。

of the of the region proposal according，to by，exponentiating that transform and then。

multiplying that and again this makes it，sort of scale and variant to the fact。

that we had to warp the input regions，before feeding them to original cnn。

okay so that gives us our our full that，gives us our first full，object detection method using。

convolutional neural networks，so now the pipeline at test time looks，something like this。

that will be given a single rgb image，and then we'll run this。

selective search algorithm on the input，image on cpu，to generate something like 2000 region。

proposals and now for each of those，regent proposals，we'll resize them to some fixed size。

like two to four by two to four，and then run them independently through。

our com net to predict both a，classification score of a category，versus background。

as well as this be box transform that，will transform the the coordinates of。

the original region proposal，and now um and then now because now at，some。

some finite set of boxes to use maybe in，our downstream application。

so there's a lot of different ways that，we can do that，that kind of depend on exactly the。

application that you're using here，so one idea that you might use is that。

right you want to somehow use the，predicted scores for all the region。

proposals to output some small finite，set of boxes，for the for the image um so one idea。

here is that maybe if，maybe you always want to output like 10，objects per image um you don't really。

care what the categories are，then you could imagine thresholding，based on the background score and。

output the 10 region proposals that had，the lowest background score。

and maybe this would be that this would，for，for your final prediction another option。

here would be to set，a threshold per category right because，our classification network is actually。

outputting a full distribution giving us，a score for background as well as a。

score for each of the categories，so another option here is to set some，threshold。

up where for each category such that if，the classification score for the。

category is above the threshold，then we output the box as a final as a，final detection。

otherwise we don't emit the box and the，exact，and the exact mechanisms of exactly how。

you convert these scores into final，detections，kind of depends on exactly what。

downstream application you're working at，yes yeah so uh these these combinations，all share weights。

so uh these con these combats we use the，exact same combination with the exact，same weights。

and we just apply it to each image，region that is coming out of our region，proposal mechanism。

yeah um because if they didn't share，weights it wouldn't really work out。

because we might have slightly different，num well，we might have different numbers of。

region proposals for each image，um and even if we did have a fixed。

number of like 2000 proposals per image，it would be sort of infeasible to train。

2000 separate comnets for each region，proposal，and it wouldn't really make sense，looking。

trained we just want to train them to，what，whether there's an object essentially。

cropped in that region yes，yes so i haven't really told you about，the training of this。

um because there's there's a couple of，subtleties in exactly how you train this，thing。

um but kind of to imagine how you might，train this thing um you're gonna form，batches。

where the batches consist of image read，different image regions from the same。

image or maybe different image regions，across different images。

so then when you when you when you run，this thing at training time it's。

basically going to have a batch of image，regions，and then for each of those image regions。

it's going to output a classification，score，as well as these bounding box，transformation parameters。

and then you'll you'll use this idea of，multi-task loss to compute a single loss。

that sums both the regression loss and，the classification loss。

and then you'll back propagate into the，weights of the cnn and make a gradient，step。

but there's a little bit of subtlety，here in exactly how you decide which，region proposals should be。

considered objects versus background but，i'll kind of gloss over that hear that。

here for the sake of simplicity，yeah the question is do you input the，the rotation to the comnet。

or the location so yeah we actually do，not input the location of the box to the，comnet。

because this should be somehow，translation invariant that maybe。

um and scale invariant as well because，maybe a cat in the upper left-hand。

part of the image should look the same，as a cat in the lower right hand part of，the image。

so we actually do not input the location，information usually here。

and actually if you look back at the way，that we parameterized this box，transformation。

this box transformation was，work，even though we're not putting in the。

location information because the way，that we're parametrizing these。

transformations is kind of invariant to，the location and scale of the box in the，image。

yeah yeah the question is how do you，choose that the size at which you warp，the boxes。

um and usually that's tied like this you，have the same hyper parameter when。

you're doing image classification，right so you know whenever we do image。

classification you always um build a cnn，that operates on some fixed image，resolution。

and then you have to warp your images to，fit that fixed image resolution。

and it's exactly the same thing here，except now we're warping image regions。

rather than warping full images，um so that would that would be a hyper。

parameter um but in general what we tend，to do for detection is use the same。

image resolution for that warping，as we would have done in a，classification case instead。

right so for classification networks we，usually use image resolution of two to。

four by two to four during training，so then for detection we'll also warp，four。

okay um but now so then then once we，have our now oh yeah another question。

yeah so this question of like these k，proposals or these thresholds。

um these would be used only during，testing um so during training。

you would always train on all of the，potential region proposals。

and then these thresholds these top k，those would be thresholds that you set，at test time。

um and so you so the way that you would，choose those thresholds is usually by。

tuning on some validation set，um for your for your downstream，application but those thresholds or。

those top k doesn't，doesn't enter into the training process，at all for this network。

okay any more questions on this rcn，okay so then um once we've got our now。

okay so then um once we've got our now，that we've got an algorithm that can so。

basically this is a this is a practical，algorithm that can input an image。

and then output a set of bounding boxes，for all the objects detected in that，image。

so then um of course we need some way to，evaluate our results。

to say whether or not the boxes that we，output are actually similar to the boxes。

that we should have output，so we can write some performance number。

that we can put in a paper and make it，bold to show that we're better than，other people。

so then we need some mechanism so，basically in order to do that。

we need some mechanism that can compare，two bounding boxes，so suppose that in this image of this。

adorable puppy，that the green box is the true box that，the map that the system should have。

output for this image，um and suppose that our and these things，will never be perfect so suppose。

that our algorithm outputs this blue box，then we need some way to compare。

um whether or not our blue box matches，the green box，and because these are all real numbers。

then it will never match exactly，so the way that we normally compare two，sets of bounding boxes。

is with a metric called intersection，over union all，usually evaluated as iou um you'll。

sometimes also see this call，called the jaccard similarity or jaccard，index in other situations。

but for object detection it's we usually，call it iou and the way that we。

the way that we um compute this is it's，a similarity measure between two boxes。

and it's basically the way we compute it，is exactly what the name is saying。

so you compute the intersection of the，two boxes which is again a box。

shown here in this reddish orange color，on the slide and then you separately，compute the union。

of the area of the union of the two，boxes which is this purple region。

uh actually the purple region together，with the orange region shown on the，slide。

and then the intersection over union is，just the ratio of the the intersection，region。

to the union region um and then for for，this example our intersection。

intersection over union is something，like 0。54，so this will always be a number between。

zero and one right because we know that，if the two boxes coincide perfectly。

then the intersection is equal to the，union so then this ratio is one。

and if the two boxes are completely，disjoint and don't overlap at all。

then they're in then their intersection，will be zero and their union will be。

non-zero so this will be a ratio，so this will give a ratio of zero um so。

this intersection of reunion is always a，number between zero and one。

where higher numbers mean a better match，between the two bounding boxes。

and to kind of give you a sense for what，people usually look at these iou numbers。

is that iou greater than 0。5 is usually，considered like，an okay decent kind of match between two。

bounding boxes，so for this green box and this blue box，here these have an iu of 0。54。

so it's like it's not perfect but it，kind of got the general gist of where。

the object was supposed to be，so that's kind of what an iou of 0。5，usually looks like。

and now an iou of 0。7 is usually like，pretty good，like maybe we made some slight errors。

and we cut off a little bit of the，bounding box，but overall we did a pretty good job at。

localizing the object，and now any any kind of iou greater than，0。9。

is like nearly perfect so actually um if，you flip between these i actually had to。

like reduce the width of the lines to，cause you to be able to see any gap。

between these two boxes now once we move，to 0。9，um and in fact for a lot of sort of real。

applications um depending on the，resolution of your image，um 0。9 might be like only a couple。

pixels off of the true box，so basically you'll almost never get iou，of one um so iou 0。

9 is usually like an，almost perfect sort of threshold，so then this iou metric is something。

that we use all over the place whenever，we need to compare，two bounding boxes but now now there's。

actually another problem that was，pointed out a little bit earlier。

which is that actually these these，practical object detection methods。

will often output a set of overlapping，boxes，um that output like many overlapping box。

boxes that are all kind of around，the same objects so as for this um。

these are not real object detections i，just kind of made these up to put on the，slide。

but for this example of these two，puppies in the image，then an object detector usually will not。

output exactly one box，per up per per uh per object instead，objectors will usually output。

like a whole bunch of a whole bunch of，boxes that are all kind of like grouped，very near。

each uh each object in the image that we，actually care about，so then we need some kind of mechanism。

to get rid of these overlapping boxes，and the way that we use the way that we。

do that is by post-processing the boxes，coming out of our object detection，system。

using an algorithm called non-max，suppression or nms，um and this is there's a lot of。

different ways you can implement non-max，suppression，but the simplest way is this with this。

fairly straightforward greedy algorithm，so um for now basically we've got our。

obj the native outputs from object，detector，is this whole set of boxes in in the，region and。

in the image and for each of those boxes，we have some probability。

that it is uh each that is each of our，categories so for each of these four，boxes that are being out。

output by the detector um we have like，different probabilities that each of。

those boxes are a dog as coming out of，the classification scores。

so then the greedy algorithm for non-max，suppression，is that first you select the highest。

scoring box in this case，is the blue box that has the highest，probability of dog as output by the。

classifier，and then you compute the intersection，over union between that highest scoring，box。

and each other box in the it that was，output by the detector，and by and by construction because we。

started with the highest scoring box，each of these other boxes will have。

lower scores than the one that we that，we're looking at here，and then we compute the intersection。

over union between that highest scoring，box，and all the other boxes which we've，computed here。

and then we're going to set some，threshold often something like 0。7，relatively high。

and say that if we if our detector，output two different boxes，that have it that had an intersection。

over union greater than this threshold，then it's likely that they did not。

correspond to different objects，it's likely that they were we think that。

instead they were probably just kind of，duplicate detections，that fired multiple boxes on the same。

object so then any boxes that have iou，greater than that threshold。

with our highest scoring box will simply，eliminate，so now in this example the the blue box。

and the orange box，have an iou of 0。78 so then we will，eliminate the orange box。

and then after eliminating the orange，box we'll then，go back to step one and we'll choose the。

next highest scoring box that was output，by the detector which in this case is，the purple box。

with a p of dog at 0。7。5 and we'll then，again compute the iou between。

that next highest box and all the other，lower scoring boxes，so in this case there remains only one。

lower scoring box which is the，yellow box and these have an iou of 0。74。

so then we would eliminate the the，yellow box and the final，outputs from our object detector would。

be these two um these this blue box and，this purple box，that are now um fairly separated and。

don't have high overlap，okay so this seems like a pretty，reasonable algorithm and basically all。

object detectors that you'll see out in，kind of，on this non-max suppression algorithm to。

eliminate shared detections，but there's kind of a subtle problem，with non-neck suppression。

is that it's it's going to get us into，are，a lot of images in objects in the image。

that have high overlap，um so this is kind of and we don't，actually have a good solution for this。

right now as a community in computer，vision，so this is actually a big failure mode。

of object detectors right now，is when you've got like really really。

crowded images with lots and lots and，lots of objects that are all highly，highly overlapping。

and then it becomes very very difficult，to tell the difference between。

very close boxes that are actually，different objects versus very close。

boxes that are duplicate detections of，the same object，so this is somewhat of a bit of an open。

challenge i think in object detection，right now，but people are working on it it's an，exciting field。

okay so then another thing we need to，talk about is we've talked about a way，to compare。

individual boxes using this iou metric，but we also need some kind of overall。

performance metric to tell us，how well our object detector is doing on，the test set overall。

right so um this actually was a fairly，trivial thing to do for。

image classification task right because，for image classification。

um for every object in a test set we，would take the argmax score and then。

check whether or not it was equal to the，true label and then we could just。

compute an accuracy on the test set，and for image classification this simple。

accuracy metric was like really easy to，compute，and let us tell whether or not one image。

classification model was doing better，than another，well now now this task of object。

detection actually complicates things a，lot，and the the metric that we use and we，need some。

again some metric that kind of，quantifies the overall performance of，the model on the test set。

and because detection is a much more，complicated problem unfortunately the，metric we use to。

compare these things is a little bit，hairy so i'll try to walk you through it。

a little bit to get a sense of what it's，computing，but basically now suppose we've trained。

an object detector and we want to get a，single number to put in our paper to。

tell us how well does this object，detector do on this data set，well now what we're going to do is。

compute some metric called mean average，precision，and this is basically the standard。

metric that everyone on object detection，uses to compare their object detectors。

and now to do it what we're going to do，is first run our trained object detector。

on all of the images in the test set and，then we'll use non-max suppression to。

eliminate these duplicate detections on，the test set，so this will so then after this we'll be。

left with a bunch of detected boxes，for each up for each image in the test。

set and for each of those boxes we'll，have a classification score。

for each of the categories that we care，about and now for each category we're。

going to separately compute，a number called the average precision。

which tells us how well are we doing，overall on just this one category。

and if you're familiar with these，metrics then the average precision is。

the area under the precision recall，curve，but in case you're not familiar with。

that we can step through it a little bit，more，so then what we're going to do is then。

for each category that we care about，then we're going to sort all of the。

detections on the test set by their，classification score，and we'll do this independently per。

category so then um here the boxes in，blue，are meant to represent all of the。

detections that were output，by our detector on all of the images，across the entire test set。

so that means that maybe the highest，scoring probability of dog regen。

across the entire test set had p dog，equals 0。99，the second highest scoring dog region。

across the entire test set，was p dog equals 0。95 and so on and so，forth。

and now and now the green the orange，boxes represent all of the ground truth。

dog dog regions on the test set，and now what we're going to do is we're，object。

our detected uh regions in or in sorted，order of their score，and for each region we're going to try。

to match it with a ground truth region，um using some iou threshold often 0。5 is，a common uh。

common choice so then suppose that our，highly confident dog detection with p，dog equals 0。99。

it actually does indeed match some，ground truth dog in that image，with an iou greater than 0。

5 well then，in that case，then we're going to flag that detection，as a true positive。

and say that that was a correct，detection and now，for that and then for that correct，detection。

it lets us compute one point on a，precision recall curve，so then now now that we've sort of now。

we're considering only the top scoring，detection coming out of our model。

so then the precision is the fraction of，our detections that are actually true。

and the recall is the fraction of the，out of the ground truth that we。

hit so then in this case um we were，considering only the top detection。

so our precision is one out of one，hundred percent，and our recall is one-third because。

among the set of detections we're，considering，we cover one-third of the of the true。

ground truth detections，so that gives us one point on a curve，where we're going to plot precision。

versus recall，and that we then then then we'll repeat，this process for the next uh for the。

next detection，in our ground truth and suppose that our，second highest scoring dog region。

also matches some ground truth now this，gives us another point on the precision，recall curve。

now we're considering two detections，both of which were true positives so our，precision is one。

and um we've got and of the three ground，truth regions，then we're hitting two of them so our。

recall is 0。67，so this lets us plot a second point on，the precision recall curve。

now suppose that this third region，actually was a false positive。

and did not match any region any ground，truth region in its image。

this would give us another point on the，precision recall curve。

and then again suppose the next one is，another false positive this gives us。

another point on the precision recall，curve，and then suppose this final one was。

indeed a true positive，that um is uh again match this this uh，this final true ground truth region。

so then for this final one then our，precision is three out of five because，of the five detections。

um we consider three of them as true，positives and then our recall is 100，because we got。

all of the we hit all of the the ground，truth regions，so then once we plot all of those。

precision recall these points on the，precision recall curve，then we can plot the full curve and then。

compute the area under that curve，and the area under that curve will have。

to be a number between 0 and 1，where 0 means we like did terribly and。

1 means we did really well and this area，under the curve is called will be the。

average precision for that category，so now for this for this case for this。

for this objective texture，our dog average precision will be 0。86。

and now it's interesting to think about，what do these ap numbers mean like this。

is not a very intuitive metric at all，well what this means is that well first。

think about how could you possibly get，ap of 1。0 well in order to get ap，1。

0 that means that we would have had，we would have had to not have all of our，before。

all of our false positives so the only，way we can get ap 0，ap 1。0 is if um all of the top。

output detections from our model were，all true positives，and we did not have any duplicate。

detections and we did not have any false，positives，and they all match the ground truth some。

ground truth region with at least iou，0。5，um and so this is going to be very very。

hard to get and in practice you'll like，you'll never get object detectors that，actually get ap 1。0。

and you might be wondering like why do，we use this complicated ap metric for。

evaluating object detectors，and that's because for different，applications you might want to。

have different choices about you might，want a different trade-offs between how，many objects you hit。

and how many objects you miss so for，some applications like maybe in，self-driving cars。

it's really important that you not miss，any cars around you um so you want to。

have you want to make sure you have um，maybe very high you，know not not miss anything but maybe in。

not so，bad and you just want to make sure that，all of your detections are indeed true。

so different use cases kind of require，different thresholds and different。

trade-offs between precision and recall，but by computing this average precision。

metric it kind of summarizes all，possible points on this trade-off，between precision and recall。

so that's why people tend to use this，metric for evaluating object detection。

but of course this was only the dog，average precision so in practice we'll。

repeat this whole procedure for every，object category，and then get an average precision for。

each category and then compute the mean，average precision as the average across，all the categories。

okay so that was a lot of work just to，evaluate our object detector um。

but it actually gets a little bit worse，because uh right because of the way we。

computed this mean average precision，it didn't actually care about localizing。

boxes really really well，right because remember when we were，matching the detected boxes to the。

ground truth boxes，we only used an iou of 0。5 so it didn't，actually matter that we get really。

really accurate detections，so in practice we'll also then tend to，repeat this whole procedure for。

different iou thresholds，and then take an average over all of。

these different mean average precisions，computed at different iou thresholds wow。

so that was kind of a disaster that's a，lot of work just to evaluate your object，detector。

um but i thought it was kind of useful，to walk through this in detail because。

this is actually how people evaluate，these things in practice。

and whenever you read um image whenever，you read object faction papers。

they'll always kind of report this mean，average precision number but it's。

actually kind of hard to find a，definition of what it actually is if。

you're reading papers so i wanted to，kind of walk through this very，explicitly。

with any questions on this computation，or the metric，okay but then forget about the metric。

let's go back to let's go back to object，detection methods，so at this point we've got this this。

rcnn which is this，region-based convolutional neural，network and it worked pretty good for。

detecting objects but there's kind of a，problem here，which is that it's actually pretty slow。

right because um，if we're trying basically we need to run，our，our forward pass of our object texture。

for each region proposal that's coming，out of our region proposal method。

um for something like selective search，there's going to be like 2 000 region，proposals。

so that means to actually process an an，image for object detection。

we're going to have to do like 2 000，forward passes of our cnn。

um so that's actually going to be like，pretty expensive um，right that's not going to run real time。

if we have to do 2000 forward passes of，our cnn for every image that we want to，process。

so we need to come up with some way to，make this process faster。

and the way that we make the way that，people have made this process faster。

is basically to swap the cnn and the，warping，and and that will basically allow us to。

re-share a lot of computation across，different image regions。

so how does that work well if we kind of，take this this rcnn method。

actually nowadays people call it slow，rcnn just because it's like so slow。

and then the alternative method is of，course faster cnn，so fast rcnn basically is going to be。

the same as slow rcn except we're going，to swap the order of convolution。

and region warping so now we're going to，take the input image，and process the whole image at a high。

resolution with a single convolutional，neural network，and this is going to be no fully。

connected layers just all convolutional，layers，so the output from this thing will be a。

convolutional feature map，giving us convolutional features for the，entire high resolution image。

and as for a bit of terminology this，confident that we run，the the that we run the image on is。

often called the backbone network，and this could be like an alexnet or a。

bgg or a resnet or whatever your，favorite classification architecture is。

um this will be called the backbone and，now we're still going to run our region。

proposal method like selective search to，get region proposals on the raw input，image。

but now rather than rather than cropping，the pixels of the input image。

instead we're going to project those，region proposals onto that convolutional，feature map。

and then apply cropping now on the，feature map itself，rather than on the raw pixels of the。

image so we'll do this cropping and，resizing on the features that are coming。

out from the convolutional backbone，network，and then we're going to run a little。

tiny light pretty lightweight per region，network，that will output our classification。

scores and our bounding box regression，transforms for each of these detected，regions。

and now this is going to be very fast，because um most of the computation。

is going to happen in this backbone，network and the per region network that，we run。

per region is going to be very very，relatively small and relatively。

lightweight and very very fast to run，so if you imagine doing something like。

fast rcnn with an alex not，then the backbone that is going to be。

all of the convolutional layers of the，alexnet，and this per region network will just be，end。

so these are really relatively fast to，compute even if we need to run them for。

a large set of regions，and then for something like residual，networks then we'll take basically the。

last convolutional stage and run that as，the purge region network。

and then we'll use all of the rest of，the network as this backbone network。

so then we're saving computation here by，doing most of our computation is going。

to be shared among all of our region，proposals，in this backbone network okay but then。

there's a question of exa，what does it mean exactly to crop these，features um because。

in order to back propagate we need to，actually back propagate into the weights。

of the backbone network as well，so we need to crop these features in a。

way that is differentiable and that ends，up being a little bit tricky。

so one way that we can crop features in，a differentiable way，is this operator called roi pool a。

region of interest，pooling so then here we have our input，image and some region proposal that has。

been computed on that input image，and then we're going to run the backbone。

network to get these convolutional image，features across the entire input image。

and just to put some numbers on this，thing um this the the the input image。

might have three channels rgb，with spatial size 640x480 and then the。

convolutional features might have，five 12 dimensional features with，spatial size of 20x15。

and now because this network is fully，convolutional then each point in this。

convolutional feature map，corresponds to points in the input image。

so then what we can do is just project，that region proposal，onto the feature map instead and then we。

can snap that feature but，what after we do that that uh that。

projection the region proposal might not，perfectly align，to the grid of the convolutional feature。

map so the next step was we can snap，that grid to the convolutional feature，map。

and then divide it up into sub regions，uh say we want to do two by two pooling。

then we would divide that snapped uh，region proposal into rough。

into roughly equal two by two regions as，close as we can get。

keeping on a line to grid cells and then，perform max，pooling within each of those regions um。

so then the，the this blue region would be like a two，by two by five。

twelve and then we'll do max pooling，within that two by two region，to output a single five twelve。

dimensional vector in the pooled output，and then for the green region it's going。

to have a spatial size of three by two，and with five dimensional five 12。

dimensional vectors at each point，and then we'll do a spatial uh max。

pooling again to give us a single 5 12，dimensional，vector coming out of that green region。

um so what this，what this does is that this means that，um even though our input region，proposals。

might have different sizes then the，output of this roi，pool operator is always going to be a。

tensor of the same fixed，size which means that we can then feed，it to these downstream。

cnn layers that are going to do this per，region computation，um so this will all work out and now we。

can back propagate through this thing，um by simply like in the way that we。

would normally back propagate through，max pooling，so when we get upstream gradients for。

the region features then we'll propagate，them down，into the corresponding regions in the。

image features，and then when we're training on batches，containing many many regions for the。

same image，then we'll end up getting gradients over，mo over most of the entire uh。

image feature map this is a little bit，complicated，but now there's a slight problem is that。

there's a bit of misalignment in these，features，because of the snapping and because of。

the fact that these uh green and blue，regions are could be different sized。

so there's a slightly more complicated，version of this that people use。

sometimes called roi align that i think，i don't want to go into in deep。

in detail due to time constraints but，basically it avoids snapping。

and instead uses bilinear interpolation，to make everything uh，really nicely aligned so you can go。

through these uh，maybe maybe later on your own but the，idea here is that with roi align。

it's very simple similar we're doing a，sort of cropping in a differential way。

but we're having better alignment，between the input features and the，output features。

okay so then this gives us a fast rcnn，here on the left，and slow rcnn right on here on the right。

and then basically the difference，between them is that we've swapped the，order of convolution。

and uh and cropping and warping and now，faster cnn is much faster。

because it can share computation across，all of these different image。

image proposal regions and how much，faster is fast rcn you might ask。

well we can look at the training time as，well as the inference time。

um so for training for training rcnn，took something like 84 hours on whatever。

this is a couple years ago，so it's really old gpus and if we train，faster cnn on the same。

uh same gpu setup then it's something，like 10 times faster to train overall。

and now at inference time um fast rcnn，is like，a lot lot faster than our cnn because。

we're sharing a lot of computation，across these different image regions。

but now an interesting thing is that，once we have fast rcnn，then actually most of the time in fast。

rcnn，is spent computing those region，proposals because remember that those。

region proposals that we're kind of，depending on，were being computed by this sort of。

heuristic algorithm called selective，search，that runs on the cpu okay and and now。

once we have fast rcnn，then something like almost 90 percent of。

the runtime is just being taken up by，computing these region proposals。

so then of course um you remember that，these were being done by this like this，heuristic algorithm。

so um let because we're sort of deep，learning practitioners we just want to。

replace everything with deep neural，networks，so instead we want to find some way to。

actually compute the region proposals as，well，using a convolutional neural network in。

a hopefully a way that'll，that'll be efficient and this will then。

hopefully improve the runtime overall of，these object detection systems。

so the the the method that does that is，then called faster rcnn。

because it's even faster than faststar，cnn these guys，these authors were like really really。

creative with their names，but the idea here now is that we want to，eliminate。

this heuristic algorithm called，selective search and instead train，a convolutional neural network to。

predict our region proposals for us，and the way that we're going to do that。

is it's going to be very similar to this，fast rcnn algorithm that we just saw。

except after we run the backbone network，then we're going to insert another。

little tiny network called a region，proposal network，or rpn that will be responsible for。

predicting region proposals，so the the pipeline here is that we'll。

have our input image we'll run the input，image through the backbone network to。

get our image level features，we'll take the image level features pass。

them to the region proposal network here，on the left，to get our region proposals and then。

once we have the region proposals，then we'll do everything the same as。

fast star cnn so we'll take our region，proposals to differentiable cropping on，the image features。

and then do a per region little parisian，networks to predict our final，classification。

and uh bounding box uh transformations，so now the only new part here is this，region proposal network。

and then the question is like how can we，use a convolutional neural network。

to output region proposals in a，trainable way，so then then we need to dive into a。

little bit the architecture of this，region proposal network，so again just because we're relying on。

this same backbone network then we take，our original，input image and then feed it through our。

backbone network to get these image，features at a relatively high resolution。

maybe again looking again like 512 by 20，by 15 in the same example。

and now the idea is that again we recall，that，these convolutional image features。

coming out of the backbone network are，all kind of aligned，to positions in the input image so then。

what we can do is at each point in this，convolutional feature map。

we can imagine an anchor box that is um，some bounding box of a fixed size。

a fixed aspect ratio but it just slides，around and we place an anchor box。

at every position at every uh position，in this convolutional feature map。

coming out of the backbone network and，now our task is to train a little。

convolutional neural network，that will classify these anchor boxes as，either containing an object。

or not containing an object so then this，will be a binary classification problem。

that we so we need to output a a a，a a positive score and a negative score。

for each of these region proposals，or for each of these anchor boxes and，because there's one。

anchor box per point in this image level，features，then we can output these positive and。

negative scores，with just another convolutional layer by，by maybe attaching a single one by one。

convolution，that just outputs a score for yes，a positive negative score for whether or。

not that and corresponding anchor，should contain an object or should not，contain an object。

and then we could train this thing using，a softmax loss，with two two categories uh yes being。

there should be an object here，and no being there's no object here。

but of course um these anchor boxes，might actually be pretty，poor fit to any objects that might。

actually appear in the image，so we're going to use a familiar trick，and in addition。

to a a score for each of these anchor，boxes，we will also output a box transform for，each of these。

positions in the convolutional feature，map that will give us a transformation。

that transforms the anchor box the raw，anchor box into，some actual region proposal that we're。

going to use，um so then here the anchor box is maybe，shown in green and then the actual。

region proposal box is going to be shown，in yellow，and then these region this uh these box。

transforms can be trained using a，regression loss，just like we saw for the that was used。

but um of course this is not complicated，but um of course this is not complicated。

enough um oh and again again we can，predict these coordinates for the b。

these are these values for the box，transforms with just another，convolutional layer。

um and of course this was not，complicated enough already so in，practice um。

using one anchor box of a fixed scale，and size，per position in the convolutional。

feature map is usually not，expressive enough to capture all the，types of objects that we want to。

recognize so in practice instead，we'll typically use a set of k different，anchor boxes。

of different scales and sizes and aspect，ratios at every point in this，convolutional feature map。

but again oh yeah question oh yeah so，the question is for anchor is an object，should it be k or 2k。

yeah it's a bit of an implementation，detail so the original paper has 2k。

so there they output at a score a，positive score and a negative score and，use a soft max loss。

and you could you do something what，we've done equivalently is output a，single score。

where pl where plus is where high values，of plus means that it's positive。

high values of negative means that it's，not an object and use a logistic，regression loss instead。

but these are pretty much equivalent and，it doesn't really matter which one you，do。

but you're right that actually most，actual implementations will usually。

output an explicit positive score，an explicit negative score per anchor，and then use a soft max loss。

but you could use logistic regression，and output one score it doesn't really，matter。

okay um but then um right so then the，k，anchors at every position in every。

position in the feature map and the，sizes，and aspect ratios of these anchors will。

all be hyper parameters，so like how many anchors you use and，what is the scale and size of these。

anchors these are all hyper parameters，that you need to set for object，detection。

so that's a little bit of a mess，okay so then um that gives us kind of，this full faster rcnn method。

that actually now has four different，losses that we need to train this thing，for。

so then in the region proposal network，we have two losses，we have this classification loss that is。

classifying the the anchor boxes as，being object or not object，we have the regression loss in the。

region proposal network which is，outputting transformations from the raw，anchor positions。

into the region proposal positions okay，and then we have all the stuff from。

fast rcnn which means that for each of，the anchor or for each of the region。

proposals coming out of the region，per，region network on each of the proposals。

which then gives us two more losses，so one is the object classification loss。

that tells us whether each proposal what，is its object category or whether or as，a background。

and this final object regression loss，that is going to regress again。

from the region proposal output from the，rpn to the final box that we'll output。

from the object detector，so this is kind of a mess and there's a。

lot and there's even more details that i，didn't have time to go into。

but there's actually turns out object，detection is a pretty complicated topic，to get to work。

okay but once you actually do all this，then faster rcnn is like really really，fast。

so then because we've eliminated this，this bottleneck of computing region，proposals on the cpu。

and instead we're just computing region，proposals using this like really really，tiny。

convolutional network on top of the，image features that means that this。

thing is like really fast and actually，can run，in real time um so faster rc9 on a gpu。

is something like 10 times faster than，fast rcnn，and spp net is a different method that。

we don't have time to talk about，but it's kind of in between fast and，rcnn。

okay so then faster rcnn is usually，called a，two-stage method for object detection。

because there's kind of like，two conceptual stages inside the method。

one is this first stage in blue where we，run one network on the entire image。

so that's we're running these，convolutions to give us the，convolutional features for the image。

and then we're running the region，proposal network which is again a couple，convolutional layers。

that gives us these these detection，these region proposals，and now once we've got these region。

to run，once per region and these second stage，is going to then output these final。

classification scores and regression，parameters，for each region that we output but then。

there's a question here which is like do，we really need the second stage。

and it kind of seems like we could，actually get away with using just the，first stage。

and just ask this first stage to do，everything，and that would kind of simplify the。

system a little bit and make it even，these，separate computations per region that we，want to work on。

so that that gives us then basically，this works，and we can use a there's methods for。

object detection，called single stage object detection，which basically look。

just like the rpn in faster rcnn，except that rather than classifying the，anchor boxes as。

object or not object instead we'll just，make a full classification decision。

for the category of the object right，here so now，suppose that we want to classify suppose。

again we have c，object categories that we want to，classify now。

when producing outputs for the anchors，now again we've got maybe 20 by 15，spatial size。

in our image feature map we've got k，anchor boxes at each position in the。

feature map and now for each of those，anchor boxes，we want to directly output，classification scores。

for the c categories and for the，background category and again we can，just do this again。

directly using a convolutional layer or，a couple convolutional layers。

and then you sort of train this thing up，and now rather than using a binary。

or two class loss in the rpn instead you，just directly use your full，classification loss。

and you still output these box，transforms one per anchor，but actually it tends to work a little。

bit better if you use，a a slightly if you actually output a，separate box transform per。

category and this is called a category，specific regression，as opposed to category agnostic。

regression where you're just outputting，one box transform that is supposed to。

work for any categories，and that last and this uh this category，of。

specialize its behavior a little bit to，uh，different uh two different categories。

um okay so this basically this object，detection，is like really really complicated and。

there's a lot of different choices that，you need to make，when doing object detection right like。

you've got，these different kind of meta algorithms，um like，faster rcnn is this two-stage method。

you've got these single-stage methods，like ssd，um and you've got sort of hybrid。

approaches like rfcn that we didn't have，time to talk about，so that's kind of one major choice you。

need to make when you're doing object，detection，there's another choice you need to make。

which is like what is the architecture，of the underlying backbone network。

and that affects the performance as well，so all of the，network architectures that we've talked。

about for classification we can also use，for object detection。

and now there's a bunch of other choices，as well like what is the image。

resolution what is the cropping，resolution，how many anchors per how many anchors do。

we use what are the size of the anchors，what are the iou thresholds that we use。

there's like a whole bunch of hyper，parameters that go into this。

and it's really really hard to like get，fair comparisons between different，object detection methods。

due to all of these massive numbers of，need to，and choices that you need to make but。

there's actually a one really great，paper from，two years ago in 2017 that tried really。

hard to just like，they basically like re-implemented all，object detection methods that they that。

were available at the time，and they tried to do a really fair，head-to-head comparison of all these。

different choices that you can make in，object detection，so i'd really recommend reading this。

2017 paper，um if you want to get some more insight，onto some of the trade-offs of these。

different choices，um but basically they produce this，amazing plot in the paper。

that kind of like each point here is a，trained object detector，and the x-axis gives us the speed at。

test time on a gpu，and the y-axis gives us the overall mean，average precision。

which is this performance metric that we，said we can compute for object detection。

and now the color of each point is，corresponds to the backbone。

the architecture of the backbone network，whether it's like an inception network。

or a mobile net or a resnet or a vgg，and now the shape of each dot gives the，meta architecture。

that is whether it's a two-stage method，like faster rcnn or a single-stage，method like ssd。

and kind of the takeaways here are that，the two-stage methods。

tends to work better right when you use，two-stage methods，then it allows the network to have sort。

of multiple glimpses at the image，information，and that tends to make performance work。

better but they're a lot slower，because you need to run different you。

need to run computation independently，for each region proposal that you want，to consider。

now a second takeaway is that these，single stage methods are tend to be a，lot faster。

because they don't have any computation，per region，instead they're just sharing all。

computation across the entire image，so they tend to be a lot faster but they。

tend to be less accurate，because they get less opportunities to，kind of look at the raw image。

information，and the other takeaway is that bigger，networks tend to work better。

so as you if you look at if you compare，using a tiny network like a mobile net。

to a very large network like a resnet，101 or，an inception resnet v2 then as you use。

larger backbone networks，okay，so those are kind of the takeaways that。

you should have about these different，high level choices in object detectors。

but it turns out that this paper was，from 2017，and now is 2019 and this is a fast。

moving field so like，there have been some changes since then，so um i've tried so let's let's look at。

what is kind of，the current state of the art on this，task well first off。

we need to uh shrink the chart in order，to fit the current state-of-the-art。

methods on the on the chart here so then，basically since 2017 gpus have gotten，faster and people。

have figured out more tricks to get，object detectors to train better。

so one trick is that um we can just，train our networks longer，and uh that tends to make them work。

better because as gpus get faster we can，afford to train them for longer。

and another thing is that there's a some，trick called，um feature pyramid network so we don't。

have time to get into that gives us kind，of a multi-scale feature representation，in the backbone。

and if you combine those two approaches，then you get a pretty big performance，boost。

so this green dot here is now faster，rcnn with resnet 101 feature。

pyramid network and it gets 42 mean，average precision um，um this cocoa data set um with a runtime。

of only 63 milliseconds at test time，um things and if you use an even bigger。

network like res next 101，then it works even better um single，stage methods have gotten quite a lot。

better as well，since uh 2017 and in 2017 single stage，methods tended to work a lot worse than。

two-stage methods，but nowadays um single-stage methods are，almost as good as two-stage methods。

um so then the kind of one of the state，one of these state-of-the-art，single-stage methods。

is actually very competitive in，performance to two-stage methods now。

another thing is that very very big，models tend to work even better，so this is now 152-layer resnext。

trained for using this feature pyramid，network approach and trained for a very，long time。

and now it gets all the way up to a 49，mean average precision。

and if you do some additional tricks at，test time like，ru at test time you run the image at。

multiple scales and multiple sizes and，multiple orientations，and you kind of ensemble all of these。

predictions at test time you can get，even better import，improvement and if you train a lot of。

data and，train a bunch of models on a lot of data，and ensemble all the predictions。

then you can get even better performance，um so the current state of the art i。

checked on the the leaderboard for this，data set right before this lecture。

was all the way up to 55 mean average，precision which is a pretty massive jump。

over the state of the art just in 2017，was 35。so this is like super active area of。

research and we just，don't have time to get into all the，tricks that are necessary to achieve。

these high results，but there's a lot of literature that you，how，how things are working okay but then。

basically there's a whole lot of stuff，going on in these object detection，methods。

so my general advice is like don't try，to implement them yourself。

because there's like way too much stuff，going on in these things and you're。

gonna get it wrong and you're not gonna，match these performance。

so like really don't try to implement，these things yourself，unless you're working on assignment 5 in。

which case you will，implement an objection from scratch，so hopefully we'll be able to make it in。

a way that's reasonably easy for you to，understand，but in practice if you do find yourself。

needing to use object detection in，practice for some real application。

you really should not implement it，yourself just because there's way too，many tricks involved。

um so in practice there's a a couple，like there's a bunch of really high。

quality open source code bases，that do optic detection now and if you。

find yourself needing to do objection in，practice，you should really consider building on。

top of one of these um so，google has this tensorflow object，detection api that implements pretty。

much all of these different object，detection methods in tensorflow。

and facebook has this uh of course we，like pytorch in this class。

so um facebook just released a like just，released like a month ago，um a brand new object detection。

framework called detectron 2，which implements all of these all of，these numbers in。

in pi torch and in fact if we look back，at these chart，um these like purple dots and these。

green dots all of these new dots，were actually pre-trained models that，are available，in detectron 2。

 so you can actually this，uh this orange star dot is not in，detectron 2。

but other than that this purple dot like，you can just download the code and，download the model。

and get that really complicated uh，purple dot over there，so that's what i would recommend you to。

do in practice if you find yourself，needing to do object detection so today。

i know we've covered a lot but um i，thought it was important that we try to，get a sense of。

how things work in object detection so，we talked about these different methods。

for up for object detection，moving from slow rcnn to fast star cnn，to faster rcnn。

and then moving from there even to these，single stage methods that are really，fast。

um so that gives us our quick like one，lecture overview of object detection。

um hope i didn't lose too many people on，that because i know it was a lot of，material。

but um next time we'll talk about even，more of these localization methods。

and we'll talk about um probably some，more object detection stuff。

and some some methods for segmentation。

![](img/e91b9fb1f9103a59971853202e55bba0_1.png)

![](img/e91b9fb1f9103a59971853202e55bba0_2.png)