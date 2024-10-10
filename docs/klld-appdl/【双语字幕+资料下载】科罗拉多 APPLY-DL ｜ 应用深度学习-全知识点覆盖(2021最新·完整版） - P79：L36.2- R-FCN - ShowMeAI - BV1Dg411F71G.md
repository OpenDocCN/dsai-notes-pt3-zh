# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P79：L36.2- R-FCN - ShowMeAI - BV1Dg411F71G

![](img/da6bb82600ae28d5a3393986b1198c39_0.png)

so what else can we do，to improve the performance of the，algorithm so far。

let's go back to this picture we took，care of the region proposals we took，care of warping。

we are sharing a lot of computations in，our cnns，we got rid of this pair class support。

vector machines，what else can we do to improve the，performance。

we can go here and we see that there are，some computations here，that probably we can save and there。

there are actually，more computations here these are fully，connected networks。

in your fast or cnn and it would be good，to share computations even after。

even after these convolutional feature，maps in this，greg box we know that most of the。

computations are shared，and only one image goes in but then，you're going to have。

multiple uh regions of interest that you，are then pulling，pushing them through convolutions and。

then getting yourself max and，bonding boxes but it would be good if，you could share。

computations here but there is a problem。

![](img/da6bb82600ae28d5a3393986b1198c39_2.png)

there is a dilemma，and the dilemma is that in image，classification。



![](img/da6bb82600ae28d5a3393986b1198c39_4.png)

we are looking for translation in，variance。

![](img/da6bb82600ae28d5a3393986b1198c39_6.png)

but in object detection translation，matters，so it's going to be translation variance，because。



![](img/da6bb82600ae28d5a3393986b1198c39_8.png)

that object could be located in，different parts of your image。



![](img/da6bb82600ae28d5a3393986b1198c39_10.png)

and if you shift your image a little bit，and you're still using the old bounding，boxes。



![](img/da6bb82600ae28d5a3393986b1198c39_12.png)

you're making error so the idea is that，you want to，replace the fully connected networks。



![](img/da6bb82600ae28d5a3393986b1198c39_14.png)

with convolutional networks，because that's going to be much faster，but then there is a problem。



![](img/da6bb82600ae28d5a3393986b1198c39_16.png)

because convolutional net neural，networks are translation invariants so，to fix that problem。



![](img/da6bb82600ae28d5a3393986b1198c39_18.png)

maps。

![](img/da6bb82600ae28d5a3393986b1198c39_20.png)

you're going to have a positive position，sent to sensitive score maps。

because you want to be sensitive to。

![](img/da6bb82600ae28d5a3393986b1198c39_22.png)

translation，to the position in your image you have a，convolution it's going to give you a。



![](img/da6bb82600ae28d5a3393986b1198c39_24.png)

bunch of feature maps，you take those feature maps you're going，to have a convolution。



![](img/da6bb82600ae28d5a3393986b1198c39_26.png)

that's going to increase the size of，your feature map，to be k squared by c plus one。

c is the number of classes one is the，background。

![](img/da6bb82600ae28d5a3393986b1198c39_28.png)

and k is the size of your。

![](img/da6bb82600ae28d5a3393986b1198c39_30.png)

this，that the entire thing but then you're。

![](img/da6bb82600ae28d5a3393986b1198c39_32.png)

gonna interpret each part differently，you're gonna interpret this yellow part，as。



![](img/da6bb82600ae28d5a3393986b1198c39_34.png)

top left then top center so that one is，gonna correspond to。



![](img/da6bb82600ae28d5a3393986b1198c39_36.png)

top left top center and this one is，bottom right，and each one is color coded。

appropriately what you're going to do is，when you're doing your pulling you only，pull。



![](img/da6bb82600ae28d5a3393986b1198c39_38.png)

from the features that you associated，with top left。



![](img/da6bb82600ae28d5a3393986b1198c39_40.png)

so you're only going to pull here and，put your values here，and then in the end there is going to be。



![](img/da6bb82600ae28d5a3393986b1198c39_42.png)

a voting and then there is going to be a，soft match，giving you the classes there is no need。

for a fully connected network。

![](img/da6bb82600ae28d5a3393986b1198c39_44.png)

so yeah this is score maps they are，coming out of your。



![](img/da6bb82600ae28d5a3393986b1198c39_46.png)

feature maps out of a convolution okay，and we are focusing only on the。



![](img/da6bb82600ae28d5a3393986b1198c39_48.png)

fast rcnn part of our network we know，that there is going to be a region。

proposal network that's proposing，regions for。

![](img/da6bb82600ae28d5a3393986b1198c39_50.png)

the detection network but that part，is what we just covered in the previous。



![](img/da6bb82600ae28d5a3393986b1198c39_52.png)

paper so that part is the same as before，the contributions are here you want them。



![](img/da6bb82600ae28d5a3393986b1198c39_54.png)

to be，you want your convolutions to be，position sensitive to be sensitive。



![](img/da6bb82600ae28d5a3393986b1198c39_56.png)

these are。

![](img/da6bb82600ae28d5a3393986b1198c39_58.png)

left，relatively speaking on the top center。

![](img/da6bb82600ae28d5a3393986b1198c39_60.png)

etc so let's be a little bit more，precise，about what's happening mathematically。



![](img/da6bb82600ae28d5a3393986b1198c39_62.png)

you can divide，each of your regions of interest into k，by k bins。



![](img/da6bb82600ae28d5a3393986b1198c39_64.png)

for instance you can have three by three，beans。

![](img/da6bb82600ae28d5a3393986b1198c39_66.png)

now if your region of interest has size，w by。

![](img/da6bb82600ae28d5a3393986b1198c39_68.png)

h each one of your bins is going to be，of size，w by k and h by k now what you need to。



![](img/da6bb82600ae28d5a3393986b1198c39_70.png)

know，is the pooled response in the i j。

![](img/da6bb82600ae28d5a3393986b1198c39_72.png)

pin for the seed category so what you，want to know。



![](img/da6bb82600ae28d5a3393986b1198c39_74.png)

is the response in the i，j bin for one of these。

![](img/da6bb82600ae28d5a3393986b1198c39_76.png)

slices for one of the c categories。

![](img/da6bb82600ae28d5a3393986b1198c39_78.png)

and we know that you're gonna have ks，squared，times c plus one position sensitive，score maps。



![](img/da6bb82600ae28d5a3393986b1198c39_80.png)

and you can each element of that is，going to be z。

![](img/da6bb82600ae28d5a3393986b1198c39_82.png)

i j and c for that particular class，and let's say x 0 y 0 is the top left，corner。



![](img/da6bb82600ae28d5a3393986b1198c39_84.png)

n is the number of pixels in each pin，then you can actually。



![](img/da6bb82600ae28d5a3393986b1198c39_86.png)

know what is the xy coordinates of the i，j spin and that's going to give you x。



![](img/da6bb82600ae28d5a3393986b1198c39_88.png)

that's going to give you the y，coordinate，each one is going to have a size of w。



![](img/da6bb82600ae28d5a3393986b1198c39_90.png)

divided by k，for x and the other one is going to have，a step size of。



![](img/da6bb82600ae28d5a3393986b1198c39_92.png)

h over k and all of these x and y's are，going to be within that pin。



![](img/da6bb82600ae28d5a3393986b1198c39_94.png)

now here is the key to translating this，figure。

![](img/da6bb82600ae28d5a3393986b1198c39_96.png)

the response at the i j，bin for class c is going to be the，summation。



![](img/da6bb82600ae28d5a3393986b1198c39_98.png)

of all of the pixels within that pin，and they are coming from your position。



![](img/da6bb82600ae28d5a3393986b1198c39_100.png)

sensitive score maps and that's why x0，and y0 matter。



![](img/da6bb82600ae28d5a3393986b1198c39_102.png)

because it's going to give you the top，left corner，that you're going to start with and then。

you're going to divide it by n。

![](img/da6bb82600ae28d5a3393986b1198c39_104.png)

because it's average pooling and that's，how you get your。



![](img/da6bb82600ae28d5a3393986b1198c39_106.png)

responses what you can do now is you，vote。

![](img/da6bb82600ae28d5a3393986b1198c39_108.png)

out，or you can take the maximum so these are，position sensitive scores。



![](img/da6bb82600ae28d5a3393986b1198c39_110.png)

and in the end you're going to have a，soft max predicting your classes so is，everything clear。



![](img/da6bb82600ae28d5a3393986b1198c39_112.png)

the entire idea was you wanted to，replace your fully connected。



![](img/da6bb82600ae28d5a3393986b1198c39_114.png)

networks with convolutions because they，are more efficient，but the problem with convolutions was。



![](img/da6bb82600ae28d5a3393986b1198c39_116.png)

that their translation invariant，and you want to make them sensitive to。



![](img/da6bb82600ae28d5a3393986b1198c39_118.png)

the position，you want to make them somehow，translation variant and that's how。



![](img/da6bb82600ae28d5a3393986b1198c39_120.png)

you're going to do it，you're going to say it matters to me，whether we are on the top left corner of。

our feature map。

![](img/da6bb82600ae28d5a3393986b1198c39_122.png)

in the region of interest or top row，center corner etc。



![](img/da6bb82600ae28d5a3393986b1198c39_124.png)

so all that's happening is that。

![](img/da6bb82600ae28d5a3393986b1198c39_126.png)

you are pulling pair each，sub-block of your channels here and then，you're just。



![](img/da6bb82600ae28d5a3393986b1198c39_128.png)

putting them putting those values here，any questions。



![](img/da6bb82600ae28d5a3393986b1198c39_130.png)

so could you repeat that last thing you，just said because，it seems sort of just like a max pooling。

i'm。

![](img/da6bb82600ae28d5a3393986b1198c39_132.png)

struggling to see the the differences so，no it's not a max building。



![](img/da6bb82600ae28d5a3393986b1198c39_134.png)

it's uh an average building or an，average pooling yeah，happening so your average pulling only。



![](img/da6bb82600ae28d5a3393986b1198c39_136.png)

on the part，that corresponds to the features color，coded by this yellow or。



![](img/da6bb82600ae28d5a3393986b1198c39_138.png)

this blue color dark blue color，oh so it's like a it's like an average。



![](img/da6bb82600ae28d5a3393986b1198c39_140.png)

pulling over the channels，instead of the the spatial dimension。



![](img/da6bb82600ae28d5a3393986b1198c39_142.png)

no it's actually the spatial dimension，it's x and y within that b。



![](img/da6bb82600ae28d5a3393986b1198c39_144.png)

what is channel specific see what do you，need in the end。



![](img/da6bb82600ae28d5a3393986b1198c39_146.png)

you're gonna need c is gonna count，numbers，from one up until c plus one so it's。



![](img/da6bb82600ae28d5a3393986b1198c39_148.png)

gonna do the slices of this，feature map for you and these are，actually called responses。



![](img/da6bb82600ae28d5a3393986b1198c39_150.png)

so you are doing a c of those c，plus one of those that's what c is。



![](img/da6bb82600ae28d5a3393986b1198c39_152.png)

counting then you know，then you need to know what value。



![](img/da6bb82600ae28d5a3393986b1198c39_154.png)

you are putting inside each one of these，bins what is the i。



![](img/da6bb82600ae28d5a3393986b1198c39_156.png)

j entry of this what is the first，and first what is the first and second。

what is the first and the last。

![](img/da6bb82600ae28d5a3393986b1198c39_158.png)

what value are going are you gonna put，on the top left of this。

and the value that you're getting it's，gonna be a single value，and it's gonna come out of doing an。



![](img/da6bb82600ae28d5a3393986b1198c39_160.png)

average，over these score maps and the yellow。

![](img/da6bb82600ae28d5a3393986b1198c39_162.png)

ones are coming from doing an，average on the yellow。



![](img/da6bb82600ae28d5a3393986b1198c39_164.png)

slices of your position sensitive score，so there is a single value。



![](img/da6bb82600ae28d5a3393986b1198c39_166.png)

peri channel per each，get it。

![](img/da6bb82600ae28d5a3393986b1198c39_168.png)

so is this clear now yeah thank you，and once you get these nine numbers in。



![](img/da6bb82600ae28d5a3393986b1198c39_170.png)

the end you want to have a single number，to push through your softmax and then。



![](img/da6bb82600ae28d5a3393986b1198c39_172.png)

these guys are gonna vote，you can for instance add them up and the。

one that's dominating is gonna give you。

![](img/da6bb82600ae28d5a3393986b1198c39_174.png)

more contribution to yourself max，it means that the positions matter now。



![](img/da6bb82600ae28d5a3393986b1198c39_176.png)

boxes，it's the same it's the same as before in，the end you're gonna end up with some。



![](img/da6bb82600ae28d5a3393986b1198c39_178.png)

numbers，squared。

![](img/da6bb82600ae28d5a3393986b1198c39_180.png)

because you need k squared of them，and there is four coordinates for each。



![](img/da6bb82600ae28d5a3393986b1198c39_182.png)

bounding box and then you can do a，bounding box regression，so these bounding boxes are also。



![](img/da6bb82600ae28d5a3393986b1198c39_184.png)

position sensitive for instance in this，case you're gonna have，nine of them times four coordinates。



![](img/da6bb82600ae28d5a3393986b1198c39_186.png)

and that's gonna be the output in the，end and how does it compare。



![](img/da6bb82600ae28d5a3393986b1198c39_188.png)

now you can see the difference between，faster or cnn。



![](img/da6bb82600ae28d5a3393986b1198c39_190.png)

and rfcnn we know that for this one i，need to go back，to this figure the depth of this network。

and the amount of computation that you，are not sharing。



![](img/da6bb82600ae28d5a3393986b1198c39_192.png)

when you are using faster or cnn is 10，with rf cnn。



![](img/da6bb82600ae28d5a3393986b1198c39_194.png)

you don't need to do any non-shared，operations，and that's going to save you both in。

training time and in testing time，and it's going to give you slightly。

better accuracy not accuracy mean，average over in average precision and，then you can。

also play around with the number of。

![](img/da6bb82600ae28d5a3393986b1198c39_196.png)

region of interest and this goes back to，the question that we had on the previous，paper。

about how many region of interest this，network is going to propose to us。



![](img/da6bb82600ae28d5a3393986b1198c39_198.png)

and how that's gonna affect the accuracy，you see that uh。



![](img/da6bb82600ae28d5a3393986b1198c39_200.png)

going to 2000 region of interest，is not even possible for faster or cnn。

it's too computationally expensive，but at least here you are getting some。

results and apparently it's not helping。

![](img/da6bb82600ae28d5a3393986b1198c39_202.png)

that much，apparently going 300 region of interest，was enough。



![](img/da6bb82600ae28d5a3393986b1198c39_204.png)

but the more important fact is the，training the trending and，testing time you're saving a lot of。

computations i think you're finishing，right on time，for those of you who have questions。

you're more than welcome to stay and ask，i'll be around and the ones who want to。

