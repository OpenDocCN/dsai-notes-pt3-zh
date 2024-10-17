# P90：L41.2- 三维卷积网络 - ShowMeAI - BV1Dg411F71G

![](img/2f5c51e98c1be94bb3eb8be576e5288c_0.png)

okay now we want to still，incorporate the time and one idea is how，about looking at 3d convolutions。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_2.png)

tree time as if it's another dimension，like x and y，pure space and what are the applications。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_4.png)

you can have applications in search，recommendation。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_6.png)

ranking you can have action recognition，this one is my favorite anomaly，detection。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_8.png)

for instance you have a lot of cameras，monitoring our roads。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_10.png)

every day and this could be useful for，smart cities。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_12.png)

and maybe some drunk driver，is driving under one side of the road，and you want to。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_14.png)

be able to detect that from your cameras，that are already mounted。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_16.png)

from infrastructure side of things there，is not much to change。

the infrastructure is already there it's。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_18.png)

just you have the data and being able to，work with the data。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_20.png)

the other one is activity understanding，what is this video doing。

what is this person in this video doing。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_22.png)

etc you can do it for search，and as soon as you get the features out，of your video。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_24.png)

you can answer questions like this how，similar are these two videos together。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_26.png)

and once you are able to answer that，question you can use that。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_28.png)

to rank your videos according to a，search and then，return the results for instance what。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_30.png)

i'm watching，does。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_32.png)

you have a height and a width you have a，kernel，of size k by k and you're going to take。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_34.png)

that kernel and，slide it over your image that's going to，give your output of the convolution。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_36.png)

to the accomplish we saw this idea in，the first paper。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_38.png)

i think and what we were doing then。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_40.png)

was take as input all of your frames，all of your l frames for your time and。

then the way that you're sliding this is。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_42.png)

you're sliding it，only in 2d because as soon as you slide，this window。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_44.png)

over your image the third dimension the，time dimension is just。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_46.png)

multiplying your inputs with this filter。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_48.png)

and that's just a simple dot product and，just averaging it，and that's going to give you the output。

of this convolution。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_50.png)

can have a 2d convolution on multiple，state。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_52.png)

another idea is to have 3d convolution，you have。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_54.png)

k by k that's your filter size in，space and then you have another filter，size in time。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_56.png)

in。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_58.png)

2d over your images you are sliding it，over the three dimension the third，dimension as well。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_60.png)

so this is being slid all over the，three dimensions so this is clear this。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_62.png)

has much less parameters，compared to that one assuming that you。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_64.png)

have the same，l this one has much more dramatic so，these papers are not difficult。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_66.png)

that's why i'm going through them faster，than usual because we have a。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_68.png)

strong background by now about，convolutions，this is the entire macro structure。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_70.png)

of your 3d convolutional network there，are。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_72.png)

and their pooling convolution pooling，etc they in the end are fully connected。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_74.png)

and all of these convolutions that you，are seeing，three。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_76.png)

this case three and d is three can i ask，real quick um。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_78.png)

so that means that each each kernel is，essentially。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_80.png)

across，is looking at three frames in the time，dimension。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_82.png)

exactly yes okay and then at the same，time like that's still taking into，account。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_84.png)

it will like it there would be a third，dimension that's taking into account the。

three different channels。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_86.png)

for rgb for our fourth dimension yes so。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_88.png)

the rgb you can think of it as，you can have three channels here it。

could be a fourth dimension but they。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_90.png)

cannot plot it，yeah but it's very similar if you map。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_92.png)

your。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_94.png)

pixel dimension is your l dimension，that could be your channel dimension and。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_96.png)

it's all of your channels，point。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_98.png)

your right is looking at three time，steps。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_100.png)

or three previous frames but as you keep，stacking，these convolutions on top of each other。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_102.png)

then we know that its field of view is，increasing even in time so the next one。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_104.png)

if that one is also a，three by three convolution that one is。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_106.png)

gonna have a receptive field of five，in time so it's looking at five time，frames。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_108.png)

okay now let's look at some results。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_110.png)

and every column is a different data set，we know about sports 1 million we know，about。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_112.png)

ucl and these are some other data sets，there is one from upenn。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_114.png)

this row is different methods and these，are the results，from those papers these are the。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_116.png)

competitive state of the art at that，time。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_118.png)

for that data set and c 3d is，convolutional 3d is this paper。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_120.png)

because，it has less parameters compared to a 2d，convolution。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_122.png)

and we know that sports 1 million is a，huge data set，okay so more parameters a bigger data。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_124.png)

cell is probably，giving you better results here but then，for the smaller ones。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_126.png)

you are getting pretty good result out，of c3d，this one is only looking at red green。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_128.png)

blue channel，and we learned from the previous paper，that you can actually include optical。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_130.png)

flow etc，some other features and that's going to，improve your performance。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_132.png)

let's visualize some video clips let's，take a network。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_134.png)

a 2d network trained on imagenet and，let's take this，c 3d and these are going to be your。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_136.png)

feature extractors，so one is the method from this paper the。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_138.png)

other one is a network triangle imagenet，now what you're going to do is take each，one of your clips。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_140.png)

and either push it through the network，trend by imagenet。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_142.png)

or trained by uh 3d convolutions。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_144.png)

here，is ucf 101 and each color is a different。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_146.png)

class it's one of these 101 classes，so imagenet could be your feature。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_148.png)

extractor or c3d could be your feature，extractor。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_150.png)

each point is a clip in your data set，you can use tsme to visualize it in 2d。



![](img/2f5c51e98c1be94bb3eb8be576e5288c_152.png)

and you can see that c3d is。

![](img/2f5c51e98c1be94bb3eb8be576e5288c_154.png)

able to separate these classes better，compared to images let's compare it to，the other。

state of the art c3d could be your，feature extractor，you can have one network or multiple，networks。

voting at the same time and that's，giving you this much accuracy。

and if you include other features it's，going to give you 90，accuracy and in terms of runtime you can。

compare it with other methods，see 3d is your benchmark so it's runtime，is one。

and the other ones are these much slower，and it's faster because convolutions are，efficient。

both in terms of parameters and in terms。