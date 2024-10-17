# P37：L19.3- MobileNetV2 - ShowMeAI - BV1Dg411F71G

![](img/71c16285620ea7fb65e093b615ad5e63_0.png)

okay let's move on to the version two of，mobile labs。



![](img/71c16285620ea7fb65e093b615ad5e63_2.png)

so these are tiny improvements on the，structure of mobile lens，the idea is that you want to have。



![](img/71c16285620ea7fb65e093b615ad5e63_4.png)

residual connections okay，and then the question is where are you。



![](img/71c16285620ea7fb65e093b615ad5e63_6.png)

gonna put the residual connection are，you gonna take，the output of this block and then put a。



![](img/71c16285620ea7fb65e093b615ad5e63_8.png)

residual connection from this，big block to the next big block these，are your expansion layers。

or are you gonna go from where you had a。

![](img/71c16285620ea7fb65e093b615ad5e63_10.png)

smaller number of channels，there。

![](img/71c16285620ea7fb65e093b615ad5e63_12.png)

and it turns out comparing different，structures it's better to go from。



![](img/71c16285620ea7fb65e093b615ad5e63_14.png)

the narrow or your bottleneck to。

![](img/71c16285620ea7fb65e093b615ad5e63_16.png)

the other bottleneck using a residual，connection，so previously it was going from the，bigger channel。



![](img/71c16285620ea7fb65e093b615ad5e63_18.png)

to the bigger channel and that's why，they are calling it inverted。

so what are we doing there is a one by，one convolution that's gonna help you。



![](img/71c16285620ea7fb65e093b615ad5e63_20.png)

change the dimensionality from small，dimensions to a larger dimension。



![](img/71c16285620ea7fb65e093b615ad5e63_22.png)

then you do a channel wise or depth wise，convolution here 3x3 to give you。



![](img/71c16285620ea7fb65e093b615ad5e63_24.png)

the other one this is the output after，this convolution，now you do another one by one。



![](img/71c16285620ea7fb65e093b615ad5e63_26.png)

convolution to reduce the dimension，now this block and that block have the。



![](img/71c16285620ea7fb65e093b615ad5e63_28.png)

same dimensionality you can add them，together to put your shortcuts。

and this is exactly the operations that。

![](img/71c16285620ea7fb65e093b615ad5e63_30.png)

are happening you start with a。

![](img/71c16285620ea7fb65e093b615ad5e63_32.png)

tensor that has h times w times k，as its size then you do a one by one，convolution。



![](img/71c16285620ea7fb65e093b615ad5e63_34.png)

you do a relu non-linearity with a，little catch。

![](img/71c16285620ea7fb65e093b615ad5e63_36.png)

i'm gonna tell you what israeli 6 then，you expand it，by a factor of t that's the output it。



![](img/71c16285620ea7fb65e093b615ad5e63_38.png)

has more channels，now that's going to be the input to the。



![](img/71c16285620ea7fb65e093b615ad5e63_40.png)

next operation the depth-wise，s。

![](img/71c16285620ea7fb65e093b615ad5e63_42.png)

you do another value so whenever you do，a stride，your resolution is going to drop and the。



![](img/71c16285620ea7fb65e093b615ad5e63_44.png)

number of channels is still the same as，before，now we are here you take that as input。



![](img/71c16285620ea7fb65e093b615ad5e63_46.png)

you do a linear，2d convolution and then that's what you，get in the end。



![](img/71c16285620ea7fb65e093b615ad5e63_48.png)

and k prime and k are the same they have，the same size，and what is the computational cost if。



![](img/71c16285620ea7fb65e093b615ad5e63_50.png)

you write it down，that's going to be your computational，cost it's a function of your expansion。



![](img/71c16285620ea7fb65e093b615ad5e63_52.png)

factor，t the size of your input，to the block which is h times w times k。

so it makes sense and these are coming。

![](img/71c16285620ea7fb65e093b615ad5e63_54.png)

from the operations that you're doing，there is k nine is coming because you。



![](img/71c16285620ea7fb65e093b615ad5e63_56.png)

have three by three，convolutions that's going to give you a，9 and then k。

prime is the output that's the。

![](img/71c16285620ea7fb65e093b615ad5e63_58.png)

computational cost and this is value 6。basically the idea is that you want to。



![](img/71c16285620ea7fb65e093b615ad5e63_60.png)

cap your activation，at a particular value for your，activations。



![](img/71c16285620ea7fb65e093b615ad5e63_62.png)

not to become too big so you are killing，your activation at that point and that's。



![](img/71c16285620ea7fb65e093b615ad5e63_64.png)

the exact，formula for railw6 the macro structure。

![](img/71c16285620ea7fb65e093b615ad5e63_66.png)

of mobilenet another look at mobilenet，but with different strides。



![](img/71c16285620ea7fb65e093b615ad5e63_68.png)

this is exactly what we have up there，the stride is one，but if the strike is two you don't put。



![](img/71c16285620ea7fb65e093b615ad5e63_70.png)

the residual connection，so that's the only difference you still。



![](img/71c16285620ea7fb65e093b615ad5e63_72.png)

have that linear operation，you have your depth wise convolution，with a stride of two。



![](img/71c16285620ea7fb65e093b615ad5e63_74.png)

rather than a stride of one and then you，still have that one by one convolution。

you don't have the residual connection，so kevin is asking why not some other，number。



![](img/71c16285620ea7fb65e093b615ad5e63_76.png)

ten or five you could that's a valid，question。

![](img/71c16285620ea7fb65e093b615ad5e63_78.png)

why value 6 why not value 5 why not，value 10。it doesn't really matter that's a great。

question i don't have an answer to you。

![](img/71c16285620ea7fb65e093b615ad5e63_80.png)

have to，write the code and see does it answer，your question sorry if i missed this but。



![](img/71c16285620ea7fb65e093b615ad5e63_82.png)

going back to the dimensions，i thought the the initial input and the，final output。



![](img/71c16285620ea7fb65e093b615ad5e63_84.png)

should match to be able to add them yes，so sometimes they match。



![](img/71c16285620ea7fb65e093b615ad5e63_86.png)

and then you can add them sometimes they，don't match，and then you're not gonna add so it。



![](img/71c16285620ea7fb65e093b615ad5e63_88.png)

depends on your choice of s and，uh t it depends on the choice of s and k。



![](img/71c16285620ea7fb65e093b615ad5e63_90.png)

prime to be exact because t we are，taking care of it。



![](img/71c16285620ea7fb65e093b615ad5e63_92.png)

yeah，it depends on k prime and s you're right，that's why here。



![](img/71c16285620ea7fb65e093b615ad5e63_94.png)

there is no residual connection because，if you want to add the residual，connection then you need to。



![](img/71c16285620ea7fb65e093b615ad5e63_96.png)

uh make the resolution higher or，actually lower。

![](img/71c16285620ea7fb65e093b615ad5e63_98.png)

net，this is how it occurs for mobilenet you，have the depth-wise。



![](img/71c16285620ea7fb65e093b615ad5e63_100.png)

adding。

![](img/71c16285620ea7fb65e093b615ad5e63_102.png)

a one-by-one convolution here and you，are adding the residual connection。

basically you are doing uh i think it。

![](img/71c16285620ea7fb65e093b615ad5e63_104.png)

was omar last session，we'll ask this question why don't you。



![](img/71c16285620ea7fb65e093b615ad5e63_106.png)

just do a one by one convolution first，and then you do depth twice a variable。

convolution and then another one but on，convolution。



![](img/71c16285620ea7fb65e093b615ad5e63_108.png)

that's exactly what they're doing in，mobile net version two，but in mobile net version one this is。



![](img/71c16285620ea7fb65e093b615ad5e63_110.png)

what they were doing so you，the。

![](img/71c16285620ea7fb65e093b615ad5e63_112.png)

low dimensional one to add a residual，connection now what is the landscape。

of different small networks i'm gonna，tell you about shuffle net and nas net。

later on but now mobile net version one，are these blue，circles the x axis is multiply at。

in terms of millions the y axis is a，is the accuracy now you're starting to，see a pareto。

frontier so that's a parallel frontier，whenever you have，multi-objective optimization you're。

going to end up with a pareto frontier，that's the part of frontier for，mobilenet。

version one and these are all version 2，with different resolutions。

and i'm going to tell you what is nas，net and，shuffle net next and the timing。

on cpu is 75 milliseconds，for processing the input image and，the accuracy is actually pretty good if。

you look at it，it's comparable to the rest of the，landscape，now here is the question should we put a。

shortcut，between bottom next the smaller ones or，should we put a bottleneck between the。

expansion layers，here and the next one or should we，forget about residual connections all，together。

the residual connections are gonna give，you this red curve in terms of top，accuracy。

and this is during training steps in，millions，this is the if you put the shortcut，between expansions。

this is the accuracy that you get and if，you put shortcut between bottlenecks。

the network behaves better so not only，it's cheaper，but also it's doing better in terms of。

accuracy and conversions，any questions these papers have small，ideas。

like rail u6 was a small idea and the。