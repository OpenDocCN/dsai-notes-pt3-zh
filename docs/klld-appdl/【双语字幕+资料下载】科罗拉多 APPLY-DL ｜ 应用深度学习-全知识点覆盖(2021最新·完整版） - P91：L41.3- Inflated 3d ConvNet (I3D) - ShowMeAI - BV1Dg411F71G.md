# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P91：L41.3- Inflated 3d ConvNet (I3D) - ShowMeAI - BV1Dg411F71G

![](img/a676b60b0b6a22c17077ed0876900323_0.png)

okay in that case let's move to the next，one it's covadis，action recognition cova this is latin。

for where are you going where are you，going action recognition。

from that title you think that that's a，review paper。



![](img/a676b60b0b6a22c17077ed0876900323_2.png)

and i don't usually go through review，papers because。



![](img/a676b60b0b6a22c17077ed0876900323_4.png)

that's going to give us a superficial，knowledge but this is different。

because it's introducing a new method。

![](img/a676b60b0b6a22c17077ed0876900323_6.png)

after going through，an overview of other papers it。



![](img/a676b60b0b6a22c17077ed0876900323_8.png)

introduces a new method，okay i know that last session somebody。



![](img/a676b60b0b6a22c17077ed0876900323_10.png)

that，yes there are some papers that are using，it and the problem with。



![](img/a676b60b0b6a22c17077ed0876900323_12.png)

rnns and lstns is that they are，you。

![](img/a676b60b0b6a22c17077ed0876900323_14.png)

through your convolution you get your，lstm up until this point。



![](img/a676b60b0b6a22c17077ed0876900323_16.png)

everything is uh parallel but then to go，to the next step，you need to know the outcome of your。

lstms so that's where，things are going to become sequential，and this is not parallelizable。



![](img/a676b60b0b6a22c17077ed0876900323_18.png)

in time and we know that for videos we，need them to be fast because these are。



![](img/a676b60b0b6a22c17077ed0876900323_20.png)

much bigger data sets compared to a，single image，each one of your data is going to be。



![](img/a676b60b0b6a22c17077ed0876900323_22.png)

multiple images okay，so that's your lstm the 3d content is。



![](img/a676b60b0b6a22c17077ed0876900323_24.png)

what we just covered，you just put a 3d convolution over your。



![](img/a676b60b0b6a22c17077ed0876900323_26.png)

stack of images to do your action，recognition。

![](img/a676b60b0b6a22c17077ed0876900323_28.png)

you can do two stream this one recovered，right at the beginning of this session。

so there's an image there's a。

![](img/a676b60b0b6a22c17077ed0876900323_30.png)

convolutional network and there is the，optical flows，going through a parallel convolution and。

in the end they are gonna vote。

![](img/a676b60b0b6a22c17077ed0876900323_32.png)

you can do the same thing you can，combine this idea。



![](img/a676b60b0b6a22c17077ed0876900323_34.png)

and the two stream idea and apply it for，different frames in time once you do。



![](img/a676b60b0b6a22c17077ed0876900323_36.png)

that in the end you're gonna get a bunch，of features，and on top of that you can do 3d。



![](img/a676b60b0b6a22c17077ed0876900323_38.png)

convolution so the 3d convolution idea，is coming from here，and the two stream idea is coming from。



![](img/a676b60b0b6a22c17077ed0876900323_40.png)

the previous paper，and this is the new method that this，paper is advocating。



![](img/a676b60b0b6a22c17077ed0876900323_42.png)

you have multiple images you have the，corresponding optical flows。



![](img/a676b60b0b6a22c17077ed0876900323_44.png)

you push them through 3d convolution，rather than 2d convolution。



![](img/a676b60b0b6a22c17077ed0876900323_46.png)

you push the optical flows do a parallel，3d convolution，and then you combine and i report your。



![](img/a676b60b0b6a22c17077ed0876900323_48.png)

classic，classification score so what is k k。

![](img/a676b60b0b6a22c17077ed0876900323_50.png)

is the total number of frames and n。

![](img/a676b60b0b6a22c17077ed0876900323_52.png)

frames，that you're using for your optical flow，because we know that。



![](img/a676b60b0b6a22c17077ed0876900323_54.png)

these don't have to be the same this，could be one image and then you can have。



![](img/a676b60b0b6a22c17077ed0876900323_56.png)

n this is this corresponds to l from the，previous paper，this is the number of frames that you。



![](img/a676b60b0b6a22c17077ed0876900323_58.png)

use for your optical flow so what is，this method called。



![](img/a676b60b0b6a22c17077ed0876900323_60.png)

it's going to be called i3d inflated，3d and what do we mean by inflated。



![](img/a676b60b0b6a22c17077ed0876900323_62.png)

you can treat a video or an，image a single image as a video how。

you just replicate the same image over，and over again。



![](img/a676b60b0b6a22c17077ed0876900323_64.png)

so that's gonna be a very boring video，you're just looking at one image。



![](img/a676b60b0b6a22c17077ed0876900323_66.png)

evolving over time but that's going to，be your video，and you can have a 2d convolution on。

that this is equivalent。

![](img/a676b60b0b6a22c17077ed0876900323_68.png)

to having 2d filters 10 times。

![](img/a676b60b0b6a22c17077ed0876900323_70.png)

along the time dimension and then you're，just rescaling the weights。



![](img/a676b60b0b6a22c17077ed0876900323_72.png)

by n you're just dividing by n because，you have n frames，and they're the same frame that's a。



![](img/a676b60b0b6a22c17077ed0876900323_74.png)

boring frame，and uh that's a boring video you start，with a。



![](img/a676b60b0b6a22c17077ed0876900323_76.png)

convolutional neural network perhaps，trained on，imagenet these are going to give you。



![](img/a676b60b0b6a22c17077ed0876900323_78.png)

your 2d filters，now you need to copy it you need to，inflate it。



![](img/a676b60b0b6a22c17077ed0876900323_80.png)

to three dimension how do you do it you，just copy it，and then divide each one by n that's。



![](img/a676b60b0b6a22c17077ed0876900323_82.png)

be your，sets。

![](img/a676b60b0b6a22c17077ed0876900323_84.png)

is big，it's coming from youtube videos and you。

![](img/a676b60b0b6a22c17077ed0876900323_86.png)

have many of them，but then ucf 101 is a small data set。



![](img/a676b60b0b6a22c17077ed0876900323_88.png)

you need to be able to do transfer，learning from whatever that we learned，from 2d convolutions。



![](img/a676b60b0b6a22c17077ed0876900323_90.png)

to 3d that's why you start with a 2d，convolution。

![](img/a676b60b0b6a22c17077ed0876900323_92.png)

that's going to give you a bunch of 2d，filters and then you inflate it in time。



![](img/a676b60b0b6a22c17077ed0876900323_94.png)

you just copy it n times and divide each，weight by n，and then one other modification to what。



![](img/a676b60b0b6a22c17077ed0876900323_96.png)

we saw earlier，is that you have two networks and you，train them separately。



![](img/a676b60b0b6a22c17077ed0876900323_98.png)

rather than at the same time you train，this one。

![](img/a676b60b0b6a22c17077ed0876900323_100.png)

separately this branch you train the，second branch over，time separately and then in the end you。



![](img/a676b60b0b6a22c17077ed0876900323_102.png)

vote，for the prediction at this time so is，everything clear。



![](img/a676b60b0b6a22c17077ed0876900323_104.png)

so far so is it clear how you clear。

![](img/a676b60b0b6a22c17077ed0876900323_106.png)

create inflated 3d convolutional，networks，this is good because now it's very easy，to initialize them。



![](img/a676b60b0b6a22c17077ed0876900323_108.png)

you initialize them using a 2d，convolution you initialize your weights，smartly。



![](img/a676b60b0b6a22c17077ed0876900323_110.png)

basically you are doing your transfer，learning from two dimensions to three，dimensions。



![](img/a676b60b0b6a22c17077ed0876900323_112.png)

okay in terms of architecture you're，gonna use an，inception architecture a video goes in。



![](img/a676b60b0b6a22c17077ed0876900323_114.png)

and then the only，catch is when you're doing your your uh。



![](img/a676b60b0b6a22c17077ed0876900323_116.png)

3d convolutions they don't necessarily，have to be symmetric。



![](img/a676b60b0b6a22c17077ed0876900323_118.png)

this could be a three by three，convolution in space，but then you can have a one by one。

convolution in。

![](img/a676b60b0b6a22c17077ed0876900323_120.png)

time why is that because you usually，have many more pixels than。



![](img/a676b60b0b6a22c17077ed0876900323_122.png)

time steps so you need to paste this，field of view。



![](img/a676b60b0b6a22c17077ed0876900323_124.png)

smartly so after this operation your，field of view is going to be 7 in time，and 11 by 11。



![](img/a676b60b0b6a22c17077ed0876900323_126.png)

space then you paste them smartly there，is gonna be one by one。



![](img/a676b60b0b6a22c17077ed0876900323_128.png)

three three three and then your max。

![](img/a676b60b0b6a22c17077ed0876900323_130.png)

one pixel in time and three by three，windows in space。



![](img/a676b60b0b6a22c17077ed0876900323_132.png)

then your receptive field is gonna be 11，in time and 27 by 27。



![](img/a676b60b0b6a22c17077ed0876900323_134.png)

in space so you paste them out so that，in the end。

![](img/a676b60b0b6a22c17077ed0876900323_136.png)

you don't blow out in terms of your time，dimension，and basically looking at a bunch of zero，padded。



![](img/a676b60b0b6a22c17077ed0876900323_138.png)

uh frames in your time so you just have，to pace it out in time。



![](img/a676b60b0b6a22c17077ed0876900323_140.png)

so are these parameters pretty sensitive，to the length and frame rate of the，video。



![](img/a676b60b0b6a22c17077ed0876900323_142.png)

um for a given length if you have a high，frame rate，don't mean maybe you're not zero padding。



![](img/a676b60b0b6a22c17077ed0876900323_144.png)

so much at the end there，yes that's correct okay but uh we saw。



![](img/a676b60b0b6a22c17077ed0876900323_146.png)

even in the first paper that the video，you're gonna break it down into clips。



![](img/a676b60b0b6a22c17077ed0876900323_148.png)

and age clip is probably having 199。

![](img/a676b60b0b6a22c17077ed0876900323_150.png)

frames in it okay and then in the end，your entire video you're just gonna use，these clips to vote。



![](img/a676b60b0b6a22c17077ed0876900323_152.png)

it's a bag of clips why is that because，this is gonna become。



![](img/a676b60b0b6a22c17077ed0876900323_154.png)

extremely computationally ex expensive。

![](img/a676b60b0b6a22c17077ed0876900323_156.png)

putting，a video on a gpu is gonna consume a lot。

![](img/a676b60b0b6a22c17077ed0876900323_158.png)

of memory，and your batch size is gonna be very，small it's gonna be probably one video。



![](img/a676b60b0b6a22c17077ed0876900323_160.png)

or two videos that you can fit on your，gpu so there are some。



![](img/a676b60b0b6a22c17077ed0876900323_162.png)

constraints that we have to deal with，makes sense，and then we are going to use an。



![](img/a676b60b0b6a22c17077ed0876900323_164.png)

inception module these modules that you，see here，inc are your inception module there is。



![](img/a676b60b0b6a22c17077ed0876900323_166.png)

nothing special about them，it's what we covered for 2d now you have，a third dimension。



![](img/a676b60b0b6a22c17077ed0876900323_168.png)

there is a data set introduced by these，guys。

![](img/a676b60b0b6a22c17077ed0876900323_170.png)

in another paper it's much bigger than，the benchmarks in your video data set。



![](img/a676b60b0b6a22c17077ed0876900323_172.png)

and it's going to be action classes a，list of action classes。



![](img/a676b60b0b6a22c17077ed0876900323_174.png)

and they cover person actions it's a，singular。

![](img/a676b60b0b6a22c17077ed0876900323_176.png)

like drawing drinking laughing punching，so these are your labels it could be。



![](img/a676b60b0b6a22c17077ed0876900323_178.png)

person person actions，like hugging kissing shaking hands etc。



![](img/a676b60b0b6a22c17077ed0876900323_180.png)

or it could be a human object，interaction like。

![](img/a676b60b0b6a22c17077ed0876900323_182.png)

opening a present mowing lawn washing，the dishes etc，so these are your labels there are going。



![](img/a676b60b0b6a22c17077ed0876900323_184.png)

to be 400 human action classes，in total and you're going to have 400 or，more clips。



![](img/a676b60b0b6a22c17077ed0876900323_186.png)

per class if you multiply these two，you have。

![](img/a676b60b0b6a22c17077ed0876900323_188.png)

in your data set in terms of state of，the art，we saw some of these papers already see，3d we saw it。

and we saw that to a stream fusion，we saw two stream and whenever you see i。

3d that's this method and the best，results are，coming out of pre-training on the entire。

kinetics data set there's also a mini，kinetic，data set the best ones are coming out of，pre-training。

and then training on the target data set，ucf 101 or，time，for those of you who have questions you。

can stay and ask and the ones who want。