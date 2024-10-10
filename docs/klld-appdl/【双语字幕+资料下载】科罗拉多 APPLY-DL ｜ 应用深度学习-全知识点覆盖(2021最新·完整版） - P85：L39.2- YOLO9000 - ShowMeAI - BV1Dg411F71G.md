# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P85：L39.2- YOLO9000 - ShowMeAI - BV1Dg411F71G

![](img/a0f07b058f18c9a979f28bfbe458d7ba_0.png)

and can you alone 9000 and it was a，bunch of。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_2.png)

little improvements to yellow so the，next three papers i'm gonna go through。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_4.png)

them really fast because these are small，ideas，these are not big ideas but these are。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_6.png)

ideas that already exist and you already，learned about them，one impressive thing about yolo 9000。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_8.png)

is that it has a very large vocabulary，it's 9 000 object categories so it can，be take over。

9000 object categories what you saw。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_10.png)

previously what there，was 30 objects or it could be 80 objects。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_12.png)

this is 9000 objects，the question is how do they do it the，other one is。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_14.png)

faster stronger etc but let's see why，some of the improvements are very simple。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_16.png)

improvements，you do batch norm and then you increase，your mean average over precision。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_18.png)

mean average precision sorry the other，observation is that，done，on images that are 224 by 224。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_20.png)

that's useful for your classification，but then when you were doing testing。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_22.png)

you would apply the same convolutional，network。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_24.png)

on higher resolution images the idea is，that it's better to，train your classifier on the high。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_26.png)

resolution images to begin with。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_28.png)

so if you do that you're gonna get 69。5，then we saw a bunch of other ideas the。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_30.png)

major one is anchor boxes we saw that，anchor boxes was helping faster our cnn。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_32.png)

and it was helping，and it was helping ssd so the idea was。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_34.png)

that let's use that，and let's see what we come up with and，then they had a drop。

in their mean over mean average，precision，then they change their network and they。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_36.png)

get 69。6，and then they go ahead and say let's，choose our。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_38.png)

anchor boxes in a smarter way maybe，using k，means and have some priors on those，bounding boxes。

and then do location prediction i'm。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_40.png)

gonna tell you what is dimension priors，what is location prediction。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_42.png)

precisely then you get a huge boost and，then there is no need for anchor boxes。

because these dimension priors。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_44.png)

are going to be your anchor boxes then，we are going to learn about pass-through。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_46.png)

that improve it a little bit then you，look at multiple scales，like what ssd was doing and then you。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_48.png)

have your high resolution detector，in the end you get 78。6 so the point was。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_50.png)

that yes ssd is good but we can be，better，with some modifications with some。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_52.png)

adjustment to the network，and to the framework so these are not，big adjustments these are。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_54.png)

small adjustments but once you do them。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_56.png)

one after another it's gonna yield a，huge benefit，so what is dimension cluster you look at。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_58.png)

your training data，the boxes in your training data you look，at the coordinates。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_60.png)

you do clustering on them and then these，are going to be your。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_62.png)

default boxes so you do a clustering on，the coordinates of the boxes in your。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_64.png)

training data the blue one corresponds，to the boxes in。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_66.png)

cocoa microsoft cocoa and the white ones，correspond to pascal vlc and they are，pretty similar。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_68.png)

but slightly different in terms of size，scale aspect ratio。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_70.png)

but then these are going to be your，dimension dryers and then what you do is。

just you do k-means clustering。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_72.png)

these are gonna give you a better prior，compared to anchor boxes。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_74.png)

so that's why you remove anchor boxes，and for clustering the distance that you，use。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_76.png)

is not the euclidean distance but it's，coming from，intersection over unit so for doing k。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_78.png)

means you need a distance，to do clustering and that distance is，this distance。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_80.png)

because we know intersection of the，union is important okay that's one，change。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_82.png)

you do location prediction you have a，box，and then what you do is you look for。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_84.png)

the。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_86.png)

of your cell cx and cy and then you want，to know what is the center，of your box and then rather than。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_88.png)

learning that distance，you learn t x and t y and you push them。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_90.png)

through a sigmoid，what else these are gonna give you your，centers and then for。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_92.png)

bit and the height you just do it，relative to your。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_94.png)

your，bounding boxes and then for object ness。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_96.png)

or confidence that there is an object in，this box，you do the same thing rather than。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_98.png)

predicting this you predict t，o so rather than predicting this term。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_100.png)

b h b y etc you are predicting t。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_102.png)

o t h t w t，y and t x the rest of them you know c。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_104.png)

x and c y is the offset from the，coordinate，of the actual image this is what the，network predicts。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_106.png)

and pw and ph are。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_108.png)

coming from these priors which could act，as your anchor box，okay so you are just making tiny。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_110.png)

adjustments to the anchor box，the other change was dark net i'm gonna。

tell you what is darkness in the last。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_112.png)

paper，the other changes pass through layer，what happens in the pass through layer。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_114.png)

you want to look at smaller scales and，smaller objects as well。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_116.png)

so you take a feature map from a lawyer。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_118.png)

by，512 you can rearrange your tail。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_120.png)

your terms to make it 13 by 13 by。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_122.png)

2048 basically you are dividing this by，two dividing that by two and。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_124.png)

pushing those terms to your feature maps，that's gonna give you 13 by 13。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_126.png)

and this number is just four times 512，and then you just concatenate it。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_128.png)

with the next layer so that's a pass，through layer。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_130.png)

and the cool thing about 9000 and the，cool method is this hierarchical，classification。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_132.png)

this is a fine-grained type of a dog you，can say。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_134.png)

i have norfolk carrier what is the，probability of being it being a norfolk，carrier。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_136.png)

condition that i know that it's interior，then you multiply that by。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_138.png)

dog，and then we know that huntington it's。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_140.png)

gonna end up being a mammal，object。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_142.png)

so you break down your probabilities，that way，and that's gonna enable you to do fine。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_144.png)

fine-grained，predictions and what you do is these are，all soft max so you have different。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_146.png)

softmax，per each node of your tree so you can，create a tree。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_148.png)

starting from a physical object and then，going down to。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_150.png)

then，in the end you have your leaf in your。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_152.png)

tree and then maybe in，one of your data sets one of the objects，your algorithm is not sure。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_154.png)

what type of a drug it is but at least，it can tell you that that's a dog。



![](img/a0f07b058f18c9a979f28bfbe458d7ba_156.png)

and in some cases it's gonna know it's a，norfolk carrier dog and then it's gonna。

classify this as a norfolk。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_158.png)

terrier dot okay but then you don't have，enough data in cocoa，combine。

the two data sets cocoa and imagenet so，the blue ones that you see are in coco，these are big classes。

chat dot car airplane house plant，in imagenet you have fine fine details。

fine grain details for instance a，persian cat or a tabby cat，or a biplane jet airbus stealth fighter。

etc，so you combine the two and then you do，joint classification and detection。

on imagenet data and on cocoa data，and for that you it's a paragraph in the，paper。

you can read that in the end that's，going to enable you to do 9000，predictions okay tiny details。

but in the end it's going to give you a，huge performance gain，and a lot of objects that you can。

predict yeah take a look at the images，in the paper but now you can see that，that's a。

type of a dolphin and this is the skin，dive and these are not，part of the labels that you're gonna。

find in cocoa，this special type of a dolphin that's a，skin dye。

probably the category that you have in，coco is that that's a person。

okay so this is really impressive being，able to do 9 000，categories locating them and classifying。

them i'm going to stop here，and if there are any questions we can，discuss it the next two papers are。

really quick。