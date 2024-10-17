# P31：L17.1- SqueezeNet - ShowMeAI - BV1Dg411F71G

now we are in the small network regime，where the objective is not only to get。

as much accuracy as possible，but at the same time to be efficient in，terms of。

memory and computation and so far we saw，two methods of doing it。

one is knowledge distillation where you，have a huge network，and you distill the knowledge into a。

smaller network，and basically you're training your small，network using the data generated。

from the giant network the other one is，you start with a pre-trained network you，first prune it。

you retrain then you quantize it then，you retrain，and then you use huffman coding to store。

your numbers your centroids more，efficiently and then you end up with a。

compressed network which you can employ，on your，devices on your smaller devices any。

questions about these two frameworks，okay there is another approach is that。



![](img/84c29e1b71173ec19b48121e368702b7_1.png)

you start with a network and you try to，design it，efficiently from scratch you don't start。



![](img/84c29e1b71173ec19b48121e368702b7_3.png)

from a pre-trained network，but you start with a network，that is small already and then try to。

optimize that and train that network and。

![](img/84c29e1b71173ec19b48121e368702b7_5.png)

there are a bunch of rules that we're，going to follow，for designing such a network and one of。



![](img/84c29e1b71173ec19b48121e368702b7_7.png)

them i'm sure you're going to guess，how can we make neural networks actually。

convolutions more efficient what is the，computational bottleneck，when it comes to convolution can。



![](img/84c29e1b71173ec19b48121e368702b7_9.png)

somebody answer，memory bandwidth i'm actually looking，for。



![](img/84c29e1b71173ec19b48121e368702b7_11.png)

another answer in terms of，mathematically，what is the most computational number of，parameters。

and the number of parameters are。

![](img/84c29e1b71173ec19b48121e368702b7_13.png)

governed by what，okay that's great one of them is the，number of channels。



![](img/84c29e1b71173ec19b48121e368702b7_15.png)

that you have basically the number of，feature maps that you have，that's correct size of the image is。

important，what else and the size of the kernel，exactly。



![](img/84c29e1b71173ec19b48121e368702b7_17.png)

so the bigger the size the more，parameters you're going to need。



![](img/84c29e1b71173ec19b48121e368702b7_19.png)

the bigger the number of feature maps，the more parameters you're going to need。

so this paper is based on those。

![](img/84c29e1b71173ec19b48121e368702b7_21.png)

observations it's very similar to the，observations that we made。

earlier when we were doing inception in。

![](img/84c29e1b71173ec19b48121e368702b7_23.png)

certain modules and how can we reduce，the number of feature maps。



![](img/84c29e1b71173ec19b48121e368702b7_25.png)

we can do dimensionality reduction and，how do we reduce the dimension。

one by one convolutions exactly so let's。

![](img/84c29e1b71173ec19b48121e368702b7_27.png)

try to do that，in this paper let's say x is the input，to a layer。



![](img/84c29e1b71173ec19b48121e368702b7_29.png)

of your of a convolutional layer x is an，input。

![](img/84c29e1b71173ec19b48121e368702b7_31.png)

it has height and width and channel we，do the convolution，and we end up with y the output of the。



![](img/84c29e1b71173ec19b48121e368702b7_33.png)

convolutional layer，and let's say we are doing padding，appropriately。



![](img/84c29e1b71173ec19b48121e368702b7_35.png)

so that we are going to end up with this，same height and width。



![](img/84c29e1b71173ec19b48121e368702b7_37.png)

and we are not doing any striding and we，are going to end up with。

f feature maps from c we are going to f。

![](img/84c29e1b71173ec19b48121e368702b7_39.png)

the size of your convolution，the first thing to note is that its。



![](img/84c29e1b71173ec19b48121e368702b7_41.png)

of，you can。

![](img/84c29e1b71173ec19b48121e368702b7_43.png)

slide over your image so it doesn't，depend on h and w，but the size of the weights。

depends on the input channels and the。

![](img/84c29e1b71173ec19b48121e368702b7_45.png)

number of output channels，we're still doing a matrix，multiplication from c to f。



![](img/84c29e1b71173ec19b48121e368702b7_47.png)

so there are a couple of strategies that，this paper follows，one is that it's going to replace three。



![](img/84c29e1b71173ec19b48121e368702b7_49.png)

by three filters，one。

![](img/84c29e1b71173ec19b48121e368702b7_51.png)

strategy two is the most important one，you decrease the number of input，channels。



![](img/84c29e1b71173ec19b48121e368702b7_53.png)

whenever you have a three by three，convolution before you do your three by。

three convolution you decrease the。

![](img/84c29e1b71173ec19b48121e368702b7_55.png)

number of input channels，using a one by one convolution strategy，strategy three。



![](img/84c29e1b71173ec19b48121e368702b7_57.png)

you down sample late in the network and，by down sampling i mean。



![](img/84c29e1b71173ec19b48121e368702b7_59.png)

using strides this will allow your，maps。

![](img/84c29e1b71173ec19b48121e368702b7_61.png)

this is for you to increase the accuracy，so the paper is going to follow three，strategies。



![](img/84c29e1b71173ec19b48121e368702b7_63.png)

and all of those strategies are gonna，show up in the fire module。

at least the first two are gonna show up。

![](img/84c29e1b71173ec19b48121e368702b7_65.png)

in the fire module so don't be afraid of，the word fire，i don't know why they're using it but。



![](img/84c29e1b71173ec19b48121e368702b7_67.png)

what's gonna happen is that you first，squeeze the dimension the number of。



![](img/84c29e1b71173ec19b48121e368702b7_69.png)

channels，using one by one convolutional filters。

![](img/84c29e1b71173ec19b48121e368702b7_71.png)

here this length that you are seeing。

![](img/84c29e1b71173ec19b48121e368702b7_73.png)

if we go back to the math on top as size，c so this is a c dimensional vector。



![](img/84c29e1b71173ec19b48121e368702b7_75.png)

this is another c dimensional vector and，let's say you have f of them。



![](img/84c29e1b71173ec19b48121e368702b7_77.png)

one two three of them so we're going to，introduce a notation。



![](img/84c29e1b71173ec19b48121e368702b7_79.png)

s one by one is the number of，filters that you're gonna have number of，one by one filters。



![](img/84c29e1b71173ec19b48121e368702b7_81.png)

in this case you have three filters and，this three corresponds to that。

f up there that's the number of filters。

![](img/84c29e1b71173ec19b48121e368702b7_83.png)

that you have and the vector size，is corresponding to this c here the。



![](img/84c29e1b71173ec19b48121e368702b7_85.png)

number of channels，input channels you first squeeze now。



![](img/84c29e1b71173ec19b48121e368702b7_87.png)

you're reducing the dimension to three，you do a relu and then you do your，expansion。



![](img/84c29e1b71173ec19b48121e368702b7_89.png)

here is where strategy one，couple of。

![](img/84c29e1b71173ec19b48121e368702b7_91.png)

your or a handful of your convolutions。

![](img/84c29e1b71173ec19b48121e368702b7_93.png)

three by three convolutions with one by，one convolutions，and the other one is that you're keeping。



![](img/84c29e1b71173ec19b48121e368702b7_95.png)

three by three convolution，a little bit more notation e one by one。



![](img/84c29e1b71173ec19b48121e368702b7_97.png)

is the number of one by one convolutions。

![](img/84c29e1b71173ec19b48121e368702b7_99.png)

in the expansion layer so we have four，of them now，e three by three is the number of three。



![](img/84c29e1b71173ec19b48121e368702b7_101.png)

by three convolutions，in the expansion layer and s one by one，was。



![](img/84c29e1b71173ec19b48121e368702b7_103.png)

the number of one by one convolutional，filters。

![](img/84c29e1b71173ec19b48121e368702b7_105.png)

in the squeeze part of the network so，that's a fire module。



![](img/84c29e1b71173ec19b48121e368702b7_107.png)

that's a definition of a fire module and，this is what i was just explaining s 1。



![](img/84c29e1b71173ec19b48121e368702b7_109.png)

by 1 is the number of 1 by 1 filters，e 1 by 1 e 3 by 3 and according to，strategy。



![](img/84c29e1b71173ec19b48121e368702b7_111.png)

2 we want s 1 by 1。

![](img/84c29e1b71173ec19b48121e368702b7_113.png)

to be less than because we want to，decrease the number of。



![](img/84c29e1b71173ec19b48121e368702b7_115.png)

inputs to 3x3 channels this has to be，less than the number of filters。



![](img/84c29e1b71173ec19b48121e368702b7_117.png)

that you have in the expansion layer so，you first squeeze，and then you expand so it's very similar。



![](img/84c29e1b71173ec19b48121e368702b7_119.png)

to inception so，let's see some results you start with a，vanilla squeeze net。



![](img/84c29e1b71173ec19b48121e368702b7_121.png)

and then you're gonna end up with these，accuracies and that's the model size。



![](img/84c29e1b71173ec19b48121e368702b7_123.png)

and simple bypass and complex bypass are。

![](img/84c29e1b71173ec19b48121e368702b7_125.png)

just residual connections the simple，bypass is just，you're adding x plus to d plus the。



![](img/84c29e1b71173ec19b48121e368702b7_127.png)

output of your，block for complex you are first，multiplying by a matrix because the。



![](img/84c29e1b71173ec19b48121e368702b7_129.png)

to，match the dimensions the idea is that。

![](img/84c29e1b71173ec19b48121e368702b7_131.png)

simple bypass also works，what is the overall architecture what we，covered here。



![](img/84c29e1b71173ec19b48121e368702b7_133.png)

for the fire module is a micro。

![](img/84c29e1b71173ec19b48121e368702b7_135.png)

structure this is the macro structure of，the network，at the macro level you first do a。



![](img/84c29e1b71173ec19b48121e368702b7_137.png)

convolution and then you do max pooling，with the stride of two。

then you do a bunch of fire modules and。

![](img/84c29e1b71173ec19b48121e368702b7_139.png)

another maxwell link，fire module another max pooling and a，stride f2。



![](img/84c29e1b71173ec19b48121e368702b7_141.png)

fire module a convolution you end up，with 1000。

![](img/84c29e1b71173ec19b48121e368702b7_143.png)

outputs and then you do global average，pooling and then self max，so the ideas of this paper are very。



![](img/84c29e1b71173ec19b48121e368702b7_145.png)

similar to inception okay let's compare，it to alexnet。



![](img/84c29e1b71173ec19b48121e368702b7_147.png)

alexnet when you don't do any，compressions at all and you use data，type of 32。



![](img/84c29e1b71173ec19b48121e368702b7_149.png)

that's the size of your model 240 and，then。

![](img/84c29e1b71173ec19b48121e368702b7_151.png)

the reduction in model size with respect，to alexnet，is one because alex and it is going to。

be our baseline。

![](img/84c29e1b71173ec19b48121e368702b7_153.png)

we are comparing everything to alexnet，alexnet compares to。



![](img/84c29e1b71173ec19b48121e368702b7_155.png)

compared to alexnet has a reduction of，one and these are the top one and top，five accuracy。



![](img/84c29e1b71173ec19b48121e368702b7_157.png)

that you achieve on imagenet you can do。

![](img/84c29e1b71173ec19b48121e368702b7_159.png)

svd singular value decomposition and can，somebody explain what that is，so the matrices in your。



![](img/84c29e1b71173ec19b48121e368702b7_161.png)

convolutions basically whatever weights，that you have。



![](img/84c29e1b71173ec19b48121e368702b7_163.png)

you can decompose it using a singular，value decomposition，it's going to be our orthogonal matrix。



![](img/84c29e1b71173ec19b48121e368702b7_165.png)

times a diagonal matrix，times the same orthogonal matrix。



![](img/84c29e1b71173ec19b48121e368702b7_167.png)

transpose or it could be，an orthonormal matrix times a diagonal。



![](img/84c29e1b71173ec19b48121e368702b7_169.png)

matrix，times another matrix that is still，orthonormal and then what you do is that。



![](img/84c29e1b71173ec19b48121e368702b7_171.png)

those diagonal entries，are going to correspond to your singular。

values and they're going to be a square。

![](img/84c29e1b71173ec19b48121e368702b7_173.png)

root of your，eigenvalues and then you keep the，maximum of them maybe the first and。



![](img/84c29e1b71173ec19b48121e368702b7_175.png)

maximums，are gonna be explaining most of your，matrix。



![](img/84c29e1b71173ec19b48121e368702b7_177.png)

and that's the way that you're gonna，compress your matrix is that clear。



![](img/84c29e1b71173ec19b48121e368702b7_179.png)

okay perfect so you do svd yes it's very，similar to pca，and you reduce you compress your network。



![](img/84c29e1b71173ec19b48121e368702b7_181.png)

from 240，to 48 you do five times reduction。

![](img/84c29e1b71173ec19b48121e368702b7_183.png)

but then you lose accuracy then if you，do network pruning。



![](img/84c29e1b71173ec19b48121e368702b7_185.png)

it's the paper from last session only，network pruning is gonna，give you nine times reduction same。



![](img/84c29e1b71173ec19b48121e368702b7_187.png)

accuracy as before，you can do deep compression it's exactly。



![](img/84c29e1b71173ec19b48121e368702b7_189.png)

what we saw，last session that's gonna give you 35，times reduction。



![](img/84c29e1b71173ec19b48121e368702b7_191.png)

in your model size same accuracy now，let's see what the squeeze net。



![](img/84c29e1b71173ec19b48121e368702b7_193.png)

is going to buy us squeeze net without，any compression。



![](img/84c29e1b71173ec19b48121e368702b7_195.png)

using 32 bits is still gonna give us，a huge reduction basically 50 times，reduction。



![](img/84c29e1b71173ec19b48121e368702b7_197.png)

slightly better accuracy actually for。

![](img/84c29e1b71173ec19b48121e368702b7_199.png)

top one error or top one accuracy it's，gonna give you a slightly better，accuracy。

and then what you do is you're gonna do。

![](img/84c29e1b71173ec19b48121e368702b7_201.png)

deep compression on the squeeze net，and that's gonna give you a huge。



![](img/84c29e1b71173ec19b48121e368702b7_203.png)

this，table is that deep compression。

![](img/84c29e1b71173ec19b48121e368702b7_205.png)

and what we just saw with fire module。

![](img/84c29e1b71173ec19b48121e368702b7_207.png)

are two orthogonal approaches they are，not complementary，you can do one and then do the other one。

on top of the。

![](img/84c29e1b71173ec19b48121e368702b7_209.png)

first one they are not redundant because，they are two totally different，approaches。



![](img/84c29e1b71173ec19b48121e368702b7_211.png)

so you can start with a network that is，already squeezed and then compress it。



![](img/84c29e1b71173ec19b48121e368702b7_213.png)

even further we are gonna introduce some，metal parameters，because we are going to have different。



![](img/84c29e1b71173ec19b48121e368702b7_215.png)

devices and we want to be able to，control，the size of the model using some meta，parameters。



![](img/84c29e1b71173ec19b48121e368702b7_217.png)

and you're going to see what they are so，what we are going to do。

is introduce e i it's equal to base e，i'm gonna explain what that is and then，we are gonna increment。



![](img/84c29e1b71173ec19b48121e368702b7_219.png)

the number of fire modules，actually the number of expand filters。

the number of expand filters by this。

![](img/84c29e1b71173ec19b48121e368702b7_221.png)

increment，every frequency that's just a constant。

![](img/84c29e1b71173ec19b48121e368702b7_223.png)

fire modules what do i mean every i，don't know every two fire module。



![](img/84c29e1b71173ec19b48121e368702b7_225.png)

skip one escape fire three at this fire，module。

![](img/84c29e1b71173ec19b48121e368702b7_227.png)

increase the number of expand filters，in this fire module then skip fire five，in fire six。



![](img/84c29e1b71173ec19b48121e368702b7_229.png)

increase the number of expand filters。

![](img/84c29e1b71173ec19b48121e368702b7_231.png)

basically the number of filters that you，have in this green，curve by increment so increment is going。



![](img/84c29e1b71173ec19b48121e368702b7_233.png)

to be a parameter，it's going to be a hyper parameter and，what is e i e i。

is basically the number of one by one，and number of three by three，together。

it's whatever that you have in this，green curve that's e，i what is b base e is the number of。

expand filters in the first fire module，you start with base e that's the number。

of filters that you have here，that's your base and then you keep。

incrementing it i don't know every two，fire modules or every three fire module，and how do you。

should be，three by three filters and how many of，them should be one by one filters。

you're gonna define another hyper，parameter another meta parameter。

and that's gonna be your percentage it's，the percentage of three by three。

that's a meta parameter and then one，minus percentage，after d by 3 is one by one and then if。

you add these two together that's going，to give you back，ei and we are going to introduce another。

meta parameter and that's squeeze ratio，how much you want to squeeze。

and that's basically defining the number，of one by one，convolution that's the ratio of one by。

one convolutions，and the number of expand filters so are，we okay，in terms of definitions so what i'm。

doing now is defining，a couple of concepts one is increment e。

which is how much you want to increment，the number of your，expand filters and we are introducing。

percentage and squeeze ratio it's，nothing hard it's just definitions。

of how we want to parameterize the，structure of，our network what is it going to buy you。

it's going to help you control the size，of your models，4。8 13 19 so you can control it you can。

control the size，and of course if you increase the，capacity of your model。

you're gonna end up with a higher，accuracy and what we are，changing here is the squeeze ratio on。

top that's the squeeze ratio，and the axis and the the vertical axis，is just。

the accuracy that you're gonna achieve，and that's just the corresponding。

model size what we're gonna change on，the figure on the right，is the percentage of three by three。

filters so on the figure on the right we，are changing this parameter。

and on the figure on the left we are，changing sr，and with these two parameters you can，on the。

target device you can choose either this，model or that model，or the other model does this make sense。

okay perfect，are there any questions before i move to，the next slide。

so in a uh sort of big picture the the，idea of squeezing and expanding。

isn't anything new but is is sort of the，novelty of this paper the。

the ratios of everything that they，introduce one of the novelties is these。

meta parameters definitely，how you parameterize your model and in，terms of the fire module。

i don't know whether this paper came，first or the inception，paper came first but the ideas are very。

similar the idea of using one by one，convolutions，to do dimensionality reduction and then。

combining one by one and three by three，convolution but the inception module had，something more。

it was doing some pulling some five by，five convolutions and then it was doing。

