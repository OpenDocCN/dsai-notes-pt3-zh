# P68：L32.3- 金字塔场景解析网络 - ShowMeAI - BV1Dg411F71G

![](img/0fe36ce64326eea289a3012a7b2cca5b_0.png)

so let's introduce a new data set that's，ade。

![](img/0fe36ce64326eea289a3012a7b2cca5b_2.png)

20k it contains 150。

![](img/0fe36ce64326eea289a3012a7b2cca5b_4.png)

star slash objects sorry professor i had，a，question on the last slide okay um so。

this they just dropped this into，like other networks we've seen uh and。

they just replaced the upsampling，right and then and all these comparisons，yeah opening this point。

is a pre-trained network on imagenet for，instance，but then from this point on it's what。

you're going to learn，that's where the transfer learning is，going up okay cool so you transfer your。

learning up until this point，and then you let the network train the，rest of it。

while fine-tuning these weights as well，but the big idea is these indices and，how you up sample。

it's different from the convolutions，okay thanks，okay perfect so this new data set has。



![](img/0fe36ce64326eea289a3012a7b2cca5b_6.png)

a lot of stuff and objects for for，instance for。

![](img/0fe36ce64326eea289a3012a7b2cca5b_8.png)

comparison pascal voc have 21。

![](img/0fe36ce64326eea289a3012a7b2cca5b_10.png)

of，image level descriptors like this is an。

![](img/0fe36ce64326eea289a3012a7b2cca5b_12.png)

airport terminal this is the bedroom etc，but let's look at the。



![](img/0fe36ce64326eea289a3012a7b2cca5b_14.png)

predictions of a fully convolutional，network on this data set。

this is the ground truth and let's take。

![](img/0fe36ce64326eea289a3012a7b2cca5b_16.png)

a look at the mistakes，that the fully connection that fully，convolutional network is going to make。



![](img/0fe36ce64326eea289a3012a7b2cca5b_18.png)

this is a bolt the ground truth is the，boat the prediction of a fully，convolutional network。



![](img/0fe36ce64326eea289a3012a7b2cca5b_20.png)

is a car and that's a mismatch，relationship。

![](img/0fe36ce64326eea289a3012a7b2cca5b_22.png)

you're gonna have confusion among，categories。

![](img/0fe36ce64326eea289a3012a7b2cca5b_24.png)

that's a sky scraper according to the，ground truth，a fully convolutional network is making，mistakes。



![](img/0fe36ce64326eea289a3012a7b2cca5b_26.png)

between the skyscraper and building。

![](img/0fe36ce64326eea289a3012a7b2cca5b_28.png)

and you can have inconspicuous classes，for instance that's the kilo the pillow。



![](img/0fe36ce64326eea289a3012a7b2cca5b_30.png)

and，the fully convolutional network is not，seeing the pillow it's just seeing。



![](img/0fe36ce64326eea289a3012a7b2cca5b_32.png)

the entire thing at the bed and what do，you think the problem is，with the network why is the network。



![](img/0fe36ce64326eea289a3012a7b2cca5b_34.png)

making this mistake，that's a bolt but it's classifying it as，a car。



![](img/0fe36ce64326eea289a3012a7b2cca5b_36.png)

any ideas maybe a imbalance in the。

![](img/0fe36ce64326eea289a3012a7b2cca5b_38.png)

training classes uh maybe but that's not，the answer i'm looking for。



![](img/0fe36ce64326eea289a3012a7b2cca5b_40.png)

is it that the boat um，requires information from elsewhere in，this image like。



![](img/0fe36ce64326eea289a3012a7b2cca5b_42.png)

you would know it's a boat because，there's water in this scene and。



![](img/0fe36ce64326eea289a3012a7b2cca5b_44.png)

if the network isn't um，incorporating that knowledge then it's，not gonna。



![](img/0fe36ce64326eea289a3012a7b2cca5b_46.png)

know the significance of it as a boat，versus a car yes。



![](img/0fe36ce64326eea289a3012a7b2cca5b_48.png)

perfect so that's a perfect answer the，context matters，the context of the image matters and the。



![](img/0fe36ce64326eea289a3012a7b2cca5b_50.png)

network is correctly identifying，what they're here but then for some，reason it is thinking。



![](img/0fe36ce64326eea289a3012a7b2cca5b_52.png)

that a car can be sitting on water there，were a couple of other answers from。



![](img/0fe36ce64326eea289a3012a7b2cca5b_54.png)

justice for instance our receptor feels，small。

![](img/0fe36ce64326eea289a3012a7b2cca5b_56.png)

that could also be an answer because the，receptive bill is going gonna correspond，to。



![](img/0fe36ce64326eea289a3012a7b2cca5b_58.png)

your field of view and it's gonna，incorporate the context so the context，matters。



![](img/0fe36ce64326eea289a3012a7b2cca5b_60.png)

scale and location in the image the，scale。

![](img/0fe36ce64326eea289a3012a7b2cca5b_62.png)

matters also but this boat has the same，scale as，it's it's actually a big part of the。



![](img/0fe36ce64326eea289a3012a7b2cca5b_64.png)

image，so you should be able to identify that，and so yes。



![](img/0fe36ce64326eea289a3012a7b2cca5b_66.png)

and jacob is saying it's not using the，context around the boat so the context，matters。



![](img/0fe36ce64326eea289a3012a7b2cca5b_68.png)

so how do you incorporate context，information。

![](img/0fe36ce64326eea289a3012a7b2cca5b_70.png)

one option was what we have been，covering so far。

![](img/0fe36ce64326eea289a3012a7b2cca5b_72.png)

with attributes convolutions because，that's going to increase the field of，view。



![](img/0fe36ce64326eea289a3012a7b2cca5b_74.png)

the other one is pyramid pulling，so you take your image you push it。

through your cnn you get a bunch of。

![](img/0fe36ce64326eea289a3012a7b2cca5b_76.png)

future maps，and previously what we were doing we，were just pulling everything。



![](img/0fe36ce64326eea289a3012a7b2cca5b_78.png)

to a single vector and then using that，single vector。



![](img/0fe36ce64326eea289a3012a7b2cca5b_80.png)

of sample to give us the global，information what you can do now。



![](img/0fe36ce64326eea289a3012a7b2cca5b_82.png)

is divide your feature map into four，components for instance。



![](img/0fe36ce64326eea289a3012a7b2cca5b_84.png)

and then pull per each uh，sub feature map so you divide it into，four。



![](img/0fe36ce64326eea289a3012a7b2cca5b_86.png)

and then you pull the first one you，paste it here，you pull the second one and this could。



![](img/0fe36ce64326eea289a3012a7b2cca5b_88.png)

be either average cooling or，max pulling you can then pull here paste。



![](img/0fe36ce64326eea289a3012a7b2cca5b_90.png)

it here etc，you can divide your input feature map，into。



![](img/0fe36ce64326eea289a3012a7b2cca5b_92.png)

nine smaller regions and then in each of，those regions。



![](img/0fe36ce64326eea289a3012a7b2cca5b_94.png)

you do the cooling and you can do the，same thing for。



![](img/0fe36ce64326eea289a3012a7b2cca5b_96.png)

a higher resolution partition，of your feature map and then you do your。

pooling then there is going to be a。

![](img/0fe36ce64326eea289a3012a7b2cca5b_98.png)

convolution here，that's just a one by one convolution。



![](img/0fe36ce64326eea289a3012a7b2cca5b_100.png)

and that's going to take a high，dimensional，vector and make it low dimensional so。



![](img/0fe36ce64326eea289a3012a7b2cca5b_102.png)

it's going to do a dimensionality，reduction for us，the one by one convolutions and then。



![](img/0fe36ce64326eea289a3012a7b2cca5b_104.png)

you're going to stack them together，you're going to copy what you had from，your cnn。



![](img/0fe36ce64326eea289a3012a7b2cca5b_106.png)

and then you do your convolution so，that's a way to，give you global context information at。



![](img/0fe36ce64326eea289a3012a7b2cca5b_108.png)

multiple resolutions，and in terms of training this network uh，again。



![](img/0fe36ce64326eea289a3012a7b2cca5b_110.png)

you're gonna run into trouble when you，sit behind your computer and try to，train it。



![](img/0fe36ce64326eea289a3012a7b2cca5b_112.png)

one way is to initialize better one way，is to do batch normalization。



![](img/0fe36ce64326eea289a3012a7b2cca5b_114.png)

drop out all sorts of techniques and the，other one is to have a。

new branch for your loss function and。

![](img/0fe36ce64326eea289a3012a7b2cca5b_116.png)

then this loss function is going to，control，the weights that are deeper into your。



![](img/0fe36ce64326eea289a3012a7b2cca5b_118.png)

network，and then it's a matter of balancing that，loss with a loss weight。



![](img/0fe36ce64326eea289a3012a7b2cca5b_120.png)

for instance you can have a weight of，zero，on loss two it means that you are not。



![](img/0fe36ce64326eea289a3012a7b2cca5b_122.png)

going to have this，uh auxiliary loss and that's going to。



![](img/0fe36ce64326eea289a3012a7b2cca5b_124.png)

give you this accuracy，pixel accuracy and mean intersection，over union。



![](img/0fe36ce64326eea289a3012a7b2cca5b_126.png)

and you can actually find the best alpha，and apparently the best alpha for this。

data set this network。

![](img/0fe36ce64326eea289a3012a7b2cca5b_128.png)

structure is going to be 0。4 that's，giving you the best result。



![](img/0fe36ce64326eea289a3012a7b2cca5b_130.png)

and the way you determine alpha is using，your validation data set。

and then you can apply to cityscapes，it's doing a pretty good job。

you can apply to pascal vlc it's doing a，much better，job compared to the baseline the。

baseline is confusing，parts of the cow for some other class，and it's missing。

some part of the table with the，background this network is getting them，correctly。

so it's actually able to take care of，confusion in your categories so now it's。

correctly classifying everything as a，skyscraper this is now a boat and that's，a pillow。

and the context matters and in terms of，numbers，you can compare only one context which。

is just having the one by one，convolution here basically your bin size。

being one by one so your entire feature，do，your pooling on that or you can have，multiple of them。

one by one two by two three by three，six by six etc and up until this point。

it's b1 so you only have one context，one global context and these are your，results。

and max pooling and average pooling are，doing，them，as soon as you introduce your context at。

different scales，it's going to do a better job and then，this dr stands for dimensionality，reduction。

how important are these one by one，convolution to reduce the damage。

and apparently they are really important，both computationally。

and also giving you better results pixel，accuracy and，mean intersection over here what is the。

message the，take home message from these sorts of，papers，is that what you see in terms of your。

models，and the choice of the models is not uh，it's not by chance the way you design，your networks。

there is a lot of intuition going behind，it it's not the black box。

if one network is doing a better job，than the other one，it's because they identify the problem。

in their data set，and then they try to fix it so these，design choices are not random。

these are smart choices for instance，attributes convolutions。

these are smart choices because you want，to solve，a problem with your network you want to。

give it context you want to，give it a higher field of view so no，these neural networks are not black。

boxes there is a lot of intuition right，behind it，any questions before i move to the next，paper。

so this um this diagram i'm uh，it seems that the height and width are a。

little like not drawn to scale，right because if i understand it，correctly that red。

the sort of single uh b1 should is the，same height and width as。

they're all the same height and width，they're just split differently right uh。

no what you get here are your results，after the pulling，you create a bin basically you put a。

grid on your original，feature map and then you pull per bin，you pull your first bin and put it here。

correct，these don't have the same resolution so，you need to do an up sampling。

to be able to contact me am i answering，your question or，yeah i think that makes sense so you you。

up sample differently based on your bin，size，is that yes exactly okay is this。

yes go ahead i was going to ask is this，pyramid module，does this only exist at sort of like the。

bottom，of the u like only before，we start up sampling or is this exist。

like further back in the network as well，are there multiple，no it's just after your feature map up。

until this point，you take a vgg or some other network，that is already trained but then you put。

this uh pulling at the end okay before，your app stop sampling and then。

concatenation and then other convolution，to give you，your final prediction and then when。

they're up sampling，that this uh this sort of top arrow um，the shortcut arrow that's indicating the。

what we talked about in the previous，paper with，uh the max pool or the the pooling，indices。

is that or is that just using this，previous feature map and then，concatenating it。

no it's just a copy and paste it's like，um okay，when they up sample do they do the the。

index like the pooling index or do they，do it by doing，uh like deconvolutions no they don't。

they don't use that okay they just use a，deconvolution，or this up sampling here is just the。

simple obstacle you just，increase your resolution copy and paste，from the low resolution to be high。

resolution，yeah okay so no they are not using uh，the indices，in this paper but you could after that。

concatenation i guess you could，like when you're because when they，concatenate that's still not。

the the full resolution of the image，they still have to，increase the resolution some after that。

right yes so you could use that but。