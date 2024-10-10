# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P60：L29.3- 全卷积网络 - ShowMeAI - BV1Dg411F71G

![](img/0a47aea836e68c52212fa70458a19662_0.png)

so let's do semantic segmentation，and it's a natural continuation to。

what we just saw about transfer learning，and i mentioned the rest of this course，learning。

literally you rarely train your networks。

![](img/0a47aea836e68c52212fa70458a19662_2.png)

from scratch，because it is time consuming and you，need to have a lot of data。



![](img/0a47aea836e68c52212fa70458a19662_4.png)

and let's start with the semantic，segmentation task，some of the applications are going to be。



![](img/0a47aea836e68c52212fa70458a19662_6.png)

for robots，and for self-driving cars and what is，the task。



![](img/0a47aea836e68c52212fa70458a19662_8.png)

you have an image and in the end you。

![](img/0a47aea836e68c52212fa70458a19662_10.png)

not only want to know what is inside，that image，that's a cat that's a dog but you want。

to know where they are located。

![](img/0a47aea836e68c52212fa70458a19662_12.png)

so now our labels all are a little bit，different。

![](img/0a47aea836e68c52212fa70458a19662_14.png)

our ground truth and labor labeling task，is a little bit different previously。



![](img/0a47aea836e68c52212fa70458a19662_16.png)

labeling images was easier，why because all you needed to do is to，have a human。



![](img/0a47aea836e68c52212fa70458a19662_18.png)

take a look at this image and say there，is a cat there is a dog that's it。



![](img/0a47aea836e68c52212fa70458a19662_20.png)

but now the labeler has to go。

![](img/0a47aea836e68c52212fa70458a19662_22.png)

and color code the part where the cat is，located，sorry the dog is located the part where。



![](img/0a47aea836e68c52212fa70458a19662_24.png)

the cat is located，and i guess that's a table probably and，some other objects。



![](img/0a47aea836e68c52212fa70458a19662_26.png)

in the domain so the labeling is harder，and whenever the labeling is harder。



![](img/0a47aea836e68c52212fa70458a19662_28.png)

you're gonna have fewer data，so the size of the data for semantic，segmentation is。



![](img/0a47aea836e68c52212fa70458a19662_30.png)

smaller than image classification so，that's one problem，and that's why we are going to use。



![](img/0a47aea836e68c52212fa70458a19662_32.png)

transfer learning and the other problem，goes，when you want to deal with the neural。



![](img/0a47aea836e68c52212fa70458a19662_34.png)

network and how you want to design it，previously we only needed to worry about。

what the what of an image，what is in this image and that was，global information now we also need to。



![](img/0a47aea836e68c52212fa70458a19662_36.png)

worry about，local information and our neural network，should be able to resolve。



![](img/0a47aea836e68c52212fa70458a19662_38.png)

not only what but also where where in，the image is my cat where in the image。



![](img/0a47aea836e68c52212fa70458a19662_40.png)

is the dot，so that's a harder task for two reasons。



![](img/0a47aea836e68c52212fa70458a19662_42.png)

one you have fewer data，and the other one is that you're，interested in the where of the。



![](img/0a47aea836e68c52212fa70458a19662_44.png)

object so that's a fundamental feature，of dealing with semantic segmentation。



![](img/0a47aea836e68c52212fa70458a19662_46.png)

and all of the contributions that we are，going to see，are going to be trying to deal with。

these problems let's start with the。

![](img/0a47aea836e68c52212fa70458a19662_48.png)

first one，if we connected the fully convolutional，network。



![](img/0a47aea836e68c52212fa70458a19662_50.png)

so we want to do transparent learning，previously，it。



![](img/0a47aea836e68c52212fa70458a19662_52.png)

and look at the cat only and we would，push it through a bunch of。



![](img/0a47aea836e68c52212fa70458a19662_54.png)

up with。

![](img/0a47aea836e68c52212fa70458a19662_56.png)

our fully connected networks and，that one was going to give us this score，for。



![](img/0a47aea836e68c52212fa70458a19662_58.png)

different categories and the dominant，one was the one that we are interested。

for instance is the tabby cast。

![](img/0a47aea836e68c52212fa70458a19662_60.png)

so this paper came and said you can。

![](img/0a47aea836e68c52212fa70458a19662_62.png)

ones，as convolutions and we know that we can，do that because。



![](img/0a47aea836e68c52212fa70458a19662_64.png)

this could be a convolution and it's，looking at the entire。



![](img/0a47aea836e68c52212fa70458a19662_66.png)

image。

![](img/0a47aea836e68c52212fa70458a19662_68.png)

for the entire tensor before it so the，fully connected ones，could be treated as convolutions now you。



![](img/0a47aea836e68c52212fa70458a19662_70.png)

can take a look at your entire data set，once you treat them as convolution you。



![](img/0a47aea836e68c52212fa70458a19662_72.png)

can treat you can，take a look at your entire image you，don't have to focus on the。



![](img/0a47aea836e68c52212fa70458a19662_74.png)

image，push it through your convolutions and we，know that convolutions。

they do not depend on the resolution of，the input image。



![](img/0a47aea836e68c52212fa70458a19662_76.png)

because you have a filter and then，you're sliding it over your。



![](img/0a47aea836e68c52212fa70458a19662_78.png)

image so the size of the input image，doesn't matter for a convolution。

once you do that rather than ending up。

![](img/0a47aea836e68c52212fa70458a19662_80.png)

with a single number here you're gonna，end up with a feature map。



![](img/0a47aea836e68c52212fa70458a19662_82.png)

so previously it was one by one now you，have a feature。



![](img/0a47aea836e68c52212fa70458a19662_84.png)

map now what is interesting you can，replace the last guy where you had one。



![](img/0a47aea836e68c52212fa70458a19662_86.png)

thousand labels now you can replace it，with 21 labels，why is that because the data set that。



![](img/0a47aea836e68c52212fa70458a19662_88.png)

we're going to work with，has only 21 labels 21 of these。



![](img/0a47aea836e68c52212fa70458a19662_90.png)

cats and dogs and table etc so you don't，need all 1000 you need only 21。



![](img/0a47aea836e68c52212fa70458a19662_92.png)

up until this point of the network you，can just copy and paste from your。



![](img/0a47aea836e68c52212fa70458a19662_94.png)

imagenet network so that's just copy and，paste and reinterpreting the。



![](img/0a47aea836e68c52212fa70458a19662_96.png)

weights the fully connected layers as，convolutions，it's just a reinterpretation nothing。



![](img/0a47aea836e68c52212fa70458a19662_98.png)

fancy going on，the rest of it are going to be the ways，that we are going to learn so we are。



![](img/0a47aea836e68c52212fa70458a19662_100.png)

going to end up with 21，categories that's going to give us the，what of the image。



![](img/0a47aea836e68c52212fa70458a19662_102.png)

now we need to worry about the wear of，the image and as i said they're fully，connected layers。



![](img/0a47aea836e68c52212fa70458a19662_104.png)

we can view them as convolutions with，kernels。

![](img/0a47aea836e68c52212fa70458a19662_106.png)

that cover their in entire input regions，now let's worry about the where for the，where we have to。



![](img/0a47aea836e68c52212fa70458a19662_108.png)

go the inverse of a convolution so we，have to be convolved，and we know that the inverse of a。



![](img/0a47aea836e68c52212fa70458a19662_110.png)

convolution is not that complicated，when we were going forward we were doing。



![](img/0a47aea836e68c52212fa70458a19662_112.png)

a convolution for instance from 96，and this resolution we were going to a。



![](img/0a47aea836e68c52212fa70458a19662_114.png)

lower resolution using a convolution，but the backward pass was giving us the。



![](img/0a47aea836e68c52212fa70458a19662_116.png)

deconvolution，we were going from a lower resolution to，a higher resolution。



![](img/0a47aea836e68c52212fa70458a19662_118.png)

using a deconvolution operation and，that's going to be the backward pass。



![](img/0a47aea836e68c52212fa70458a19662_120.png)

of a convolution i'm going to give you，the exact formula for this in the next，slide but for。



![](img/0a47aea836e68c52212fa70458a19662_122.png)

now we need to up sample from a low，resolution。

![](img/0a47aea836e68c52212fa70458a19662_124.png)

feature map to a higher resolution one，and that we can do with a。



![](img/0a47aea836e68c52212fa70458a19662_126.png)

convolution with a fractional input，strike so，rather than your stride being one two or，three you're。



![](img/0a47aea836e68c52212fa70458a19662_128.png)

striding fractionally it means that，you're reusing your weights。



![](img/0a47aea836e68c52212fa70458a19662_130.png)

that's nothing but the backward，convolution and that's gonna be a，deconvolution。



![](img/0a47aea836e68c52212fa70458a19662_132.png)

these names are gonna be you're gonna，hear about these names。



![](img/0a47aea836e68c52212fa70458a19662_134.png)

in different papers interchangeably，so that's just the reverse of a。

forward and that's gonna give you the。

![](img/0a47aea836e68c52212fa70458a19662_136.png)

backward pass of the convolution so，these are nothing fancy i'm gonna give。



![](img/0a47aea836e68c52212fa70458a19662_138.png)

you the exact mathematics of it，in the next slide but for now we need to，up sample。



![](img/0a47aea836e68c52212fa70458a19662_140.png)

and that's going to give us the where，what is our evaluation matrix i'm going。

to talk about the loss function in the，next slide。

![](img/0a47aea836e68c52212fa70458a19662_142.png)

but how are we going to evaluate whether，our algorithm is doing a good job or no。



![](img/0a47aea836e68c52212fa70458a19662_144.png)

you can take a look at the pixel，accuracy。

![](img/0a47aea836e68c52212fa70458a19662_146.png)

let me bring this up n i j so we are，gonna have a matrix。



![](img/0a47aea836e68c52212fa70458a19662_148.png)

on on the rows you're gonna have，the correct class i on the j you're。



![](img/0a47aea836e68c52212fa70458a19662_150.png)

gonna have the predicted class，and that's sort of like a confusion，matrix。



![](img/0a47aea836e68c52212fa70458a19662_152.png)

and on the i j entry of that matrix。

![](img/0a47aea836e68c52212fa70458a19662_154.png)

you're computing the number of pixels，that are uh pixels of class i。



![](img/0a47aea836e68c52212fa70458a19662_156.png)

that are being predicted to be to belong，into class j。



![](img/0a47aea836e68c52212fa70458a19662_158.png)

that's going to give you an ij so you're，just counting and that's going to give。

you your pixel accuracy。

![](img/0a47aea836e68c52212fa70458a19662_160.png)

and what is ti ti taught is the total，number of pixels。



![](img/0a47aea836e68c52212fa70458a19662_162.png)

of class i so you're just summing，over j and that's going to give you a，total number of pixels。



![](img/0a47aea836e68c52212fa70458a19662_164.png)

in class i now you can have your pixel，accuracy you can define it now。



![](img/0a47aea836e68c52212fa70458a19662_166.png)

you can take a look at the diagonal of，that matrix。



![](img/0a47aea836e68c52212fa70458a19662_168.png)

you sum it and then you can divide it by，the total，number of pixels and that's going to。



![](img/0a47aea836e68c52212fa70458a19662_170.png)

give you a pixel accuracy，so this is clear you can have mean，accuracy。



![](img/0a47aea836e68c52212fa70458a19662_172.png)

again it's a diagonal divided by the，total number of pixels belonging to that，class。



![](img/0a47aea836e68c52212fa70458a19662_174.png)

this one was for one class now you can，divide it by the total number of classes。



![](img/0a47aea836e68c52212fa70458a19662_176.png)

in your entire data set and that's going，to give you your mean accuracy。



![](img/0a47aea836e68c52212fa70458a19662_178.png)

you can have intersection over union and，mean intersection over union。



![](img/0a47aea836e68c52212fa70458a19662_180.png)

this part is intersection over union and，i，is the intersection and the union there。



![](img/0a47aea836e68c52212fa70458a19662_182.png)

is a summation over j，going on in ti and these are all of the。



![](img/0a47aea836e68c52212fa70458a19662_184.png)

entries in your matrix，but you are counting the diagonal twice。



![](img/0a47aea836e68c52212fa70458a19662_186.png)

so you subtract it once，that's going to give you the union and。

mean because you're doing it over all of。

![](img/0a47aea836e68c52212fa70458a19662_188.png)

mean of，intersection over union rather than。

![](img/0a47aea836e68c52212fa70458a19662_190.png)

having one，over n cl as a weight for each one of，these。



![](img/0a47aea836e68c52212fa70458a19662_192.png)

terms in the summation you can have a，frequency weighted。



![](img/0a47aea836e68c52212fa70458a19662_194.png)

intersection over union so that's going，to give you ti，now your rate is going to be ti divided。



![](img/0a47aea836e68c52212fa70458a19662_196.png)

by the summation of tkx，rather than this is good when your data。



![](img/0a47aea836e68c52212fa70458a19662_198.png)

is imbalanced that's a good matrix，when your data is imbalanced and cross。

class you can have ti divided by this。

![](img/0a47aea836e68c52212fa70458a19662_200.png)

summation of，tk as your frequency i think i'm gonna，stop here。



![](img/0a47aea836e68c52212fa70458a19662_202.png)

and uh for those of you who have，questions you can stay and ask。



![](img/0a47aea836e68c52212fa70458a19662_204.png)

and the ones who want to leave you can，leave could you explain how。



![](img/0a47aea836e68c52212fa70458a19662_206.png)

we're recasting the con uh，sorry the fully connected layers as，convolutions。



![](img/0a47aea836e68c52212fa70458a19662_208.png)

as convolutional layers um let's take a，look at this。



![](img/0a47aea836e68c52212fa70458a19662_210.png)

256 and it's gonna have。

![](img/0a47aea836e68c52212fa70458a19662_212.png)

a height and a bit yeah before you push，it through a comp，we were fully connected what would you。



![](img/0a47aea836e68c52212fa70458a19662_214.png)

do you would flatten this，and then multiply that by the weight or，equivalently。



![](img/0a47aea836e68c52212fa70458a19662_216.png)

you couldn't flatten you could keep that，in its form。



![](img/0a47aea836e68c52212fa70458a19662_218.png)

and reshape your weights because in the，end what you're doing。



![](img/0a47aea836e68c52212fa70458a19662_220.png)

is just uh the inner product of two，tensors your filter。



![](img/0a47aea836e68c52212fa70458a19662_222.png)

as a tensor and your input features as，another tensor and you're doing an inner，product。



![](img/0a47aea836e68c52212fa70458a19662_224.png)

so you can get rid of that flattening，now you have。



![](img/0a47aea836e68c52212fa70458a19662_226.png)

a convolution with a filter size that is，equal to the entire。



![](img/0a47aea836e68c52212fa70458a19662_228.png)

input okay it means that your，convolution is going to have a kernel。



![](img/0a47aea836e68c52212fa70458a19662_230.png)

that is of a size equal to this，box here to the entire input box and。



![](img/0a47aea836e68c52212fa70458a19662_232.png)

that's how you are going to interpret，a fully connected layer as a convolution。

and the rest of them are。

![](img/0a47aea836e68c52212fa70458a19662_234.png)

the same from this point to the next one，is just easy。



![](img/0a47aea836e68c52212fa70458a19662_236.png)

and you could also think of that as like，doing，flattening the the the tensor and then。



![](img/0a47aea836e68c52212fa70458a19662_238.png)

doing the fully connected layer，and then just repackaging it back up。



![](img/0a47aea836e68c52212fa70458a19662_240.png)

into，the shape tensor you want it to be it's，but it's just easier to do it the other。



![](img/0a47aea836e68c52212fa70458a19662_242.png)

way，yes because you want it to be efficient，as well and the other point is。



![](img/0a47aea836e68c52212fa70458a19662_244.png)

i guess you're not summing and the other，point is uh。



![](img/0a47aea836e68c52212fa70458a19662_246.png)

you want it to be automatic if you have，a fully connected layer here。



![](img/0a47aea836e68c52212fa70458a19662_248.png)

then what goes in the fully connected，is has to be of a particular size after。



![](img/0a47aea836e68c52212fa70458a19662_250.png)

flattening it has to have their，size that the fully connected layer。

likes but if you interpret it as a，convolution。

![](img/0a47aea836e68c52212fa70458a19662_252.png)

you can enlarge your image and we know，that convolutions don't depend。



![](img/0a47aea836e68c52212fa70458a19662_254.png)

on the size of the input image okay，yeah so the fully connected one is a。



![](img/0a47aea836e68c52212fa70458a19662_256.png)

matrix vector multiplication，and whenever you are doing a matrix。



![](img/0a47aea836e68c52212fa70458a19662_258.png)

vector multiplication，uh the sizes need to match up otherwise。



![](img/0a47aea836e68c52212fa70458a19662_260.png)

it's a linear algebra thing it's not，gonna compute it for you it's going to，give you an error。



![](img/0a47aea836e68c52212fa70458a19662_262.png)

your code but if you treat it as a，convolution now。



![](img/0a47aea836e68c52212fa70458a19662_264.png)

convolutions don't depend on the size of，the input because，you take a filter and then you slide it。

over your image。

![](img/0a47aea836e68c52212fa70458a19662_266.png)

and that's why you have a resolution for。

![](img/0a47aea836e68c52212fa70458a19662_268.png)

this 4096 layer，there is a resolution the resolution is，not one you have a。



![](img/0a47aea836e68c52212fa70458a19662_270.png)

resolution for it because you have a，convolution you have a kernel that's。

that you're sliding over here i'm。

![](img/0a47aea836e68c52212fa70458a19662_272.png)

interpreting it as mostly just，getting rid of the sum right is that，correct you just kind of do an。



![](img/0a47aea836e68c52212fa70458a19662_274.png)

element-wise，product and then keep the dimensions the，same is that。



![](img/0a47aea836e68c52212fa70458a19662_276.png)

true you have to get rid of the，flattening step。

![](img/0a47aea836e68c52212fa70458a19662_278.png)

right yeah because if you were to sum，over that，resolution then you would get the same。



![](img/0a47aea836e68c52212fa70458a19662_280.png)

thing as you would with the fully，connected right，this summation is just what you get out。



![](img/0a47aea836e68c52212fa70458a19662_282.png)

of matrix vector multiplication，but so but if you did this thing where。



![](img/0a47aea836e68c52212fa70458a19662_284.png)

you have convolutional layers at the end，and then say in that first one of。



![](img/0a47aea836e68c52212fa70458a19662_286.png)

uh dimension with 4095 or 96 channels。

![](img/0a47aea836e68c52212fa70458a19662_288.png)

if you just each channel if you just did，like global ad，average or i guess not global average。



![](img/0a47aea836e68c52212fa70458a19662_290.png)

pooling but if you just summed up across，the the height and width of that channel。



![](img/0a47aea836e68c52212fa70458a19662_292.png)

the output would be the same。

![](img/0a47aea836e68c52212fa70458a19662_294.png)

as you would have in that 4096 vector，for the fully connected right yes。



![](img/0a47aea836e68c52212fa70458a19662_296.png)

so i think now we are confusing，the global average pooling with the。



![](img/0a47aea836e68c52212fa70458a19662_298.png)

fully connected layers，no no sorry that was just my mistake i，was just i just。



![](img/0a47aea836e68c52212fa70458a19662_300.png)

good，but the summation doesn't exist anymore。

![](img/0a47aea836e68c52212fa70458a19662_302.png)

it's just over your filter，so the way you are going to interpret，this is that you have a filter。



![](img/0a47aea836e68c52212fa70458a19662_304.png)

with a kernel size equal to the input。

![](img/0a47aea836e68c52212fa70458a19662_306.png)

resolution that's how you accompl，convolutionalize，you get rid of the flattening and then。



![](img/0a47aea836e68c52212fa70458a19662_308.png)

you have a single，kernel i mean multiple kernels actually。



![](img/0a47aea836e68c52212fa70458a19662_310.png)

4 096 kernels with a filter size that is，equal to。

![](img/0a47aea836e68c52212fa70458a19662_312.png)

the entire resolution of your input，features。

![](img/0a47aea836e68c52212fa70458a19662_314.png)

so does the resolution decrease from 256，to，4095 from that like from those two。



![](img/0a47aea836e68c52212fa70458a19662_316.png)

layers，yes and the resolution is always，decreasing。



![](img/0a47aea836e68c52212fa70458a19662_318.png)

from this to the next one to the next，one and then it's going to be equal。

and then the resolution increases again。

![](img/0a47aea836e68c52212fa70458a19662_320.png)

but what's going to happen，here is that because your input image is，bigger。



![](img/0a47aea836e68c52212fa70458a19662_322.png)

you're going to have a bigger resolution，here so the resolution that you get。



![](img/0a47aea836e68c52212fa70458a19662_324.png)

is dependent on the size of the input，image but if you have a kernel that's，the same。



![](img/0a47aea836e68c52212fa70458a19662_326.png)

height and width as that previous layer，then wouldn't the output just be the。

same height and width as well。

![](img/0a47aea836e68c52212fa70458a19662_328.png)

it's the same height and width，corresponding to this part of the image。



![](img/0a47aea836e68c52212fa70458a19662_330.png)

this one is 256 by 256 and that's going，to give you。



![](img/0a47aea836e68c52212fa70458a19662_332.png)

this size for your channel at that，kernel size。

![](img/0a47aea836e68c52212fa70458a19662_334.png)

you can apply to other regimes okay，you can also think of it this way the，the field of view。



![](img/0a47aea836e68c52212fa70458a19662_336.png)

cat。

![](img/0a47aea836e68c52212fa70458a19662_338.png)

the field of view for each single one of，these，is gonna be the cat but then if you。



![](img/0a47aea836e68c52212fa70458a19662_340.png)

choose another，point another pixel that's going to be。



![](img/0a47aea836e68c52212fa70458a19662_342.png)

another part of your image，so that's going to be a different part。



![](img/0a47aea836e68c52212fa70458a19662_344.png)