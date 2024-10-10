# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P6：L3.2- Network in Network - ShowMeAI - BV1Dg411F71G

so there is this paper networking，network，which i really like and it started，many of the ideas。

that modern neural networks are using，but it's not getting as many attention。

as the other ones are getting，because there is this challenge，in computer vision on imagenet dataset。

and the papers that do a great job and，beat，the other neural networks on that。

challenge are gonna get cited，without anybody reading them okay，but this net this paper。



![](img/bfecd65cbcef25806c305b49184bf6df_1.png)

has very nice ideas that other paper in。

![](img/bfecd65cbcef25806c305b49184bf6df_3.png)

uh one of them was this。

![](img/bfecd65cbcef25806c305b49184bf6df_5.png)

they wanted to put a network the the，general idea is that they wanted to put。



![](img/bfecd65cbcef25806c305b49184bf6df_7.png)

a network inside another neural network，so they started with a linear，convolution layer。

which is basically you have a filter you，dot product it with，that portion of your image or that。

portion of your input，and then in the end you're gonna get a，neuron here sitting here。



![](img/bfecd65cbcef25806c305b49184bf6df_9.png)

they said between this layer and the，other one，we want to put a neural network and they。

an mlp a multi-layer perceptron a。

![](img/bfecd65cbcef25806c305b49184bf6df_11.png)

fully connected neural networks so there，is nothing special there。

it's the basic the most basic type of。

![](img/bfecd65cbcef25806c305b49184bf6df_13.png)

neural network that they can find，they wanted to put it here and they。



![](img/bfecd65cbcef25806c305b49184bf6df_15.png)

later on they understood that what they，were doing，so many modern networks used one by one。

convolution for。

![](img/bfecd65cbcef25806c305b49184bf6df_17.png)

various reasons for various reasons but，these guys wanted to have a networking。



![](img/bfecd65cbcef25806c305b49184bf6df_19.png)

network，and how does it work you have an input，batch。



![](img/bfecd65cbcef25806c305b49184bf6df_21.png)

centered at location i and j so this is，your input batch。



![](img/bfecd65cbcef25806c305b49184bf6df_23.png)

center that location i and j，and then you put everything inside the，vector so。



![](img/bfecd65cbcef25806c305b49184bf6df_25.png)

that's input patch you're putting it，inside a vector。



![](img/bfecd65cbcef25806c305b49184bf6df_27.png)

and then correspondingly you're gonna。

![](img/bfecd65cbcef25806c305b49184bf6df_29.png)

have a bunch of weights。

![](img/bfecd65cbcef25806c305b49184bf6df_31.png)

that's your filter，and then you multiply these two together，add them up。



![](img/bfecd65cbcef25806c305b49184bf6df_33.png)

add the bias do your value。

![](img/bfecd65cbcef25806c305b49184bf6df_35.png)

activation rectify，rectified linear units which is just。



![](img/bfecd65cbcef25806c305b49184bf6df_37.png)

maximum of these guys and zero，and as i said many of most of the。



![](img/bfecd65cbcef25806c305b49184bf6df_39.png)

operations in deep learning are just，point wise。

![](img/bfecd65cbcef25806c305b49184bf6df_41.png)

this is just a number，it is either positive or negative if it，is positive you keep it if it is。



![](img/bfecd65cbcef25806c305b49184bf6df_43.png)

negative you ignore，it that's going to be your value，and that's going to give you your first，layer。

the output of your first layer and what，is k here。

![](img/bfecd65cbcef25806c305b49184bf6df_45.png)

k is indexing the channel so，that's one of your filters you can have，multiple filters。



![](img/bfecd65cbcef25806c305b49184bf6df_47.png)

so this is one filter if you add another，filter that's gonna give you another。



![](img/bfecd65cbcef25806c305b49184bf6df_49.png)

dimension here on the channel dimension，so you're increasing the channel。

dimension k is counting the channels。

![](img/bfecd65cbcef25806c305b49184bf6df_51.png)

now you can put everything channel wise。

![](img/bfecd65cbcef25806c305b49184bf6df_53.png)

in a vector that's going to give you。

![](img/bfecd65cbcef25806c305b49184bf6df_55.png)

for instance f1 which is a vector，now you multiply it by a bunch of，weights at the bias。



![](img/bfecd65cbcef25806c305b49184bf6df_57.png)

value that's going to give you the next，layer and so on，that's what they wanted to do but。

in the end it ended up being just a one。

![](img/bfecd65cbcef25806c305b49184bf6df_59.png)

by one convolution，so the idea of one by one convolution。



![](img/bfecd65cbcef25806c305b49184bf6df_61.png)

was first introduced in networking，network。

![](img/bfecd65cbcef25806c305b49184bf6df_63.png)

to the best of my knowledge what is the，other idea。



![](img/bfecd65cbcef25806c305b49184bf6df_65.png)

so that's their network a bunch of。

![](img/bfecd65cbcef25806c305b49184bf6df_67.png)

networking networks，in the end if you remember we had fully，connected layers。



![](img/bfecd65cbcef25806c305b49184bf6df_69.png)

![](img/bfecd65cbcef25806c305b49184bf6df_70.png)

they said those fully connected layers，are not necessary。



![](img/bfecd65cbcef25806c305b49184bf6df_72.png)

you can just average out these are your，filters。

![](img/bfecd65cbcef25806c305b49184bf6df_74.png)

out，that's going to give you a number you。

![](img/bfecd65cbcef25806c305b49184bf6df_76.png)

put it here，the second channel is going to give you。



![](img/bfecd65cbcef25806c305b49184bf6df_78.png)

an average you put it here the third one，here and then。



![](img/bfecd65cbcef25806c305b49184bf6df_80.png)

the last guy here so rather than。

![](img/bfecd65cbcef25806c305b49184bf6df_82.png)

flattening out a convolution，you just average it and then put it。



![](img/bfecd65cbcef25806c305b49184bf6df_84.png)

![](img/bfecd65cbcef25806c305b49184bf6df_85.png)

different dimensions，and then the rest of it is just。



![](img/bfecd65cbcef25806c305b49184bf6df_87.png)

one layer of。

![](img/bfecd65cbcef25806c305b49184bf6df_89.png)

soft max which is going to give you the，probabilities and then you can do your，classification。



![](img/bfecd65cbcef25806c305b49184bf6df_91.png)

so the idea of global average pulling，and one by one convolutions was。



![](img/bfecd65cbcef25806c305b49184bf6df_93.png)

introduced in this paper，one cool thing about global average。



![](img/bfecd65cbcef25806c305b49184bf6df_95.png)

pooling，is that you are getting rid of those。

![](img/bfecd65cbcef25806c305b49184bf6df_97.png)

fully connected layers in the end。

![](img/bfecd65cbcef25806c305b49184bf6df_99.png)

and it has another application，this is good for stopping regularization。



![](img/bfecd65cbcef25806c305b49184bf6df_101.png)

so it's gonna do regularization for us，another application is that now。



![](img/bfecd65cbcef25806c305b49184bf6df_103.png)

this averaging is gonna get rid of the。

![](img/bfecd65cbcef25806c305b49184bf6df_105.png)

here so the dimensions of the image，doesn't matter。



![](img/bfecd65cbcef25806c305b49184bf6df_107.png)

that much anymore so it has two，have any。

![](img/bfecd65cbcef25806c305b49184bf6df_109.png)

questions i would be happy to answer，about dropouts。



![](img/bfecd65cbcef25806c305b49184bf6df_111.png)

about one by one convolution and about，global average pooling，and if anybody wants to leave you're。



![](img/bfecd65cbcef25806c305b49184bf6df_113.png)

more than they'll continue，thank you professor。

![](img/bfecd65cbcef25806c305b49184bf6df_115.png)

no problem so would you mind just uh。

![](img/bfecd65cbcef25806c305b49184bf6df_117.png)

once。

![](img/bfecd65cbcef25806c305b49184bf6df_119.png)

yes of course thank you。

![](img/bfecd65cbcef25806c305b49184bf6df_121.png)

so in the end of whatever operations，that you had you're gonna end up with a。



![](img/bfecd65cbcef25806c305b49184bf6df_123.png)

tensor okay and your tensor。

![](img/bfecd65cbcef25806c305b49184bf6df_125.png)

is gonna be。

![](img/bfecd65cbcef25806c305b49184bf6df_127.png)

it's gonna have a height it's gonna have，a，width and it's gonna have the number of。



![](img/bfecd65cbcef25806c305b49184bf6df_129.png)

channels that you have，one channel two channel three channel up。



![](img/bfecd65cbcef25806c305b49184bf6df_131.png)

![](img/bfecd65cbcef25806c305b49184bf6df_132.png)

the thing is that you take one of these，channels。

![](img/bfecd65cbcef25806c305b49184bf6df_134.png)

and then you average those numbers。

![](img/bfecd65cbcef25806c305b49184bf6df_136.png)

and put those numbers here and your，averaging is going to be 1。



![](img/bfecd65cbcef25806c305b49184bf6df_138.png)

![](img/bfecd65cbcef25806c305b49184bf6df_139.png)

and then the summation over，whatever pixel value that you have here。



![](img/bfecd65cbcef25806c305b49184bf6df_141.png)

does that make sense yeah and。

![](img/bfecd65cbcef25806c305b49184bf6df_143.png)

and you're using um so like throughout，the whole，network you're using these one by one，convolutions。



![](img/bfecd65cbcef25806c305b49184bf6df_145.png)

and then global average pooling is just，this last sort of。



![](img/bfecd65cbcef25806c305b49184bf6df_147.png)

step exactly okay so you have regular，convolution here。



![](img/bfecd65cbcef25806c305b49184bf6df_149.png)

and then one by one calculations here，and then a regular convolution one by。



![](img/bfecd65cbcef25806c305b49184bf6df_151.png)

one regular，one by one and in the end average。

![](img/bfecd65cbcef25806c305b49184bf6df_153.png)