# P23：L11- 压缩与激活 - ShowMeAI - BV1Dg411F71G

![](img/2a478ccbde3374f78e207ac29ff6f98a_0.png)

there is this paper squeeze and。

![](img/2a478ccbde3374f78e207ac29ff6f98a_2.png)

excitation network，it's getting very good results in the，challenge。



![](img/2a478ccbde3374f78e207ac29ff6f98a_4.png)

and the idea is very neat so they，submitted their work to。



![](img/2a478ccbde3374f78e207ac29ff6f98a_6.png)

imagenet challenge and they're getting，very good，results and why is that this is an。

overview of the paper，in one plot there is some transformation，which takes a tensor and maps it into。

another tensor，there is the squeeze part there is the，excitation part。

and there is a scaling part so you are，doing some transformations。

after your convolution or it could be，any other operations that you have here。

and remember whenever we are doing these，we are talking about blocks。

it's not the entire network it's just a，block，that you can take and put it inside your。

neural network so it's just a building，block，of your network so let's go into a，little bit of。

the details and see what actually is，squeeze what is，excitation and what is the scaling so。

for that we are going to need some。

![](img/2a478ccbde3374f78e207ac29ff6f98a_8.png)

notation x is our input tensor it has a，height it has a width and it has a bunch，of channels。

u is the output of our transformation，that's the height that's the width。



![](img/2a478ccbde3374f78e207ac29ff6f98a_10.png)

that's the channel width and that's our，transformation，and as you know each network if it's a。

residual network，that transformation is going to be。



![](img/2a478ccbde3374f78e207ac29ff6f98a_12.png)

different from，if you have inception so don't worry，about this transformation。

but all you need to know is that you're，transforming your input to。

you there is this nice way to think，about convolutions，so so far we have learned a lot of nice。

ways to think about convolutions，each paper was thinking differently you。



![](img/2a478ccbde3374f78e207ac29ff6f98a_14.png)

are looking at the same object from，different lenses。



![](img/2a478ccbde3374f78e207ac29ff6f98a_16.png)

this is another lens let's say v，is going to be the filters。



![](img/2a478ccbde3374f78e207ac29ff6f98a_18.png)

of your channel and you're going to have，c filters。



![](img/2a478ccbde3374f78e207ac29ff6f98a_20.png)

v1 up until vc and vc are just，the parameters of the c filter。



![](img/2a478ccbde3374f78e207ac29ff6f98a_22.png)

so you have a filter that's going to，output the outputs。



![](img/2a478ccbde3374f78e207ac29ff6f98a_24.png)

tensor u and that's our u we are，breaking it down，channel wise so what is going to be the。

dimension of u1，it's going to be h times w so that's，going to be。

like an image it has a bunch of pixels，same thing here you see。



![](img/2a478ccbde3374f78e207ac29ff6f98a_26.png)

the final channel is going to have a，bunch of pixels。



![](img/2a478ccbde3374f78e207ac29ff6f98a_28.png)

so how do we get uc out from a，convolution，you take each one of these for instance，v1。

and you convolve it with x and the，convolution operation is just a。



![](img/2a478ccbde3374f78e207ac29ff6f98a_30.png)

summation，over the channels of two by two，convolutions，so now this probably you know how to do。

the convolution，okay it's just the inner product of vc，times xs a small window of xs。

and then you take that small window and，then you，slide it over your input now。

vc you can also break it down，into vc1 up until this c prime，and each filter is now gonna have it's。

gonna be in。

![](img/2a478ccbde3374f78e207ac29ff6f98a_32.png)

r h by w each one of these terms，so that's another way to think about。



![](img/2a478ccbde3374f78e207ac29ff6f98a_34.png)

convolutions and that's your input，x any questions before i are going to。



![](img/2a478ccbde3374f78e207ac29ff6f98a_36.png)

squeeze，so that was a simple transformation that，was a convolution transformation。



![](img/2a478ccbde3374f78e207ac29ff6f98a_38.png)

so you transform x to u through the，convolution。

![](img/2a478ccbde3374f78e207ac29ff6f98a_40.png)

but i included this math here because，it's a nice way to think about，convolution。

it's a different way to think about it，so what is this quiz doing。

it's nothing but the global averaging so。

![](img/2a478ccbde3374f78e207ac29ff6f98a_42.png)

it's global average pooling，it's going to give you z which is。



![](img/2a478ccbde3374f78e207ac29ff6f98a_44.png)

the squeezed vector and it's going to be。

![](img/2a478ccbde3374f78e207ac29ff6f98a_46.png)

c dimensional and for those of you who，don't know what is。



![](img/2a478ccbde3374f78e207ac29ff6f98a_48.png)

pooling，that's the exact formulation you divide，by。



![](img/2a478ccbde3374f78e207ac29ff6f98a_50.png)

the number of pixels in your image and，then you do a summation over the pixels。



![](img/2a478ccbde3374f78e207ac29ff6f98a_52.png)

and that's going to give you a vector in，rc because each one of。



![](img/2a478ccbde3374f78e207ac29ff6f98a_54.png)

these terms are c-dimensional excitation，is just a fully connected network you。



![](img/2a478ccbde3374f78e207ac29ff6f98a_56.png)

take z，you linearly transform it with a matrix，you do a non-linearity on top of that。

you linearly transform。

![](img/2a478ccbde3374f78e207ac29ff6f98a_58.png)

the output of delta and then you do，sigmoid，sigmoid is going to give you a number，between 0 and 1。



![](img/2a478ccbde3374f78e207ac29ff6f98a_60.png)

so it's sort of like an attention，mechanism。

![](img/2a478ccbde3374f78e207ac29ff6f98a_62.png)

now you're trying to pay attention to，channel wise to read channel should i。



![](img/2a478ccbde3374f78e207ac29ff6f98a_64.png)

pay more attention and these attention，rates are。

![](img/2a478ccbde3374f78e207ac29ff6f98a_66.png)

a number from zero to 1。 that's，excitation。

![](img/2a478ccbde3374f78e207ac29ff6f98a_68.png)

usually w1 is gonna reduce the dimension。

![](img/2a478ccbde3374f78e207ac29ff6f98a_70.png)

so you go from something c dimensional，to something that's c over r dimensional。



![](img/2a478ccbde3374f78e207ac29ff6f98a_72.png)

you reduce a dimension，and then you expand it with w2 so that。



![](img/2a478ccbde3374f78e207ac29ff6f98a_74.png)

you end up with，c a vector that is c dimensional。

![](img/2a478ccbde3374f78e207ac29ff6f98a_76.png)

in the end after this operation scaling。

![](img/2a478ccbde3374f78e207ac29ff6f98a_78.png)

you take the inputs at a particular，channel，basically you take one of these slices。

and then you multiply it by the，corresponding，attention so that's going to give you sc。



![](img/2a478ccbde3374f78e207ac29ff6f98a_80.png)

times uc，sc is a scalar per each of these that's，just a scalar。



![](img/2a478ccbde3374f78e207ac29ff6f98a_82.png)

you are multiplying a scalar by a matrix，and。

![](img/2a478ccbde3374f78e207ac29ff6f98a_84.png)

there is no confusion there how to，multiply a scale by a matrix every。



![](img/2a478ccbde3374f78e207ac29ff6f98a_86.png)

entry is going to become multiplied by，sc。

![](img/2a478ccbde3374f78e207ac29ff6f98a_88.png)

and that's scaling any questions so far，and that's going to be x that's going to，give you your，layer。



![](img/2a478ccbde3374f78e207ac29ff6f98a_90.png)

and the next layer you probably want to，do the same thing or you want to do，something different。

but this is just a single block of the。

![](img/2a478ccbde3374f78e207ac29ff6f98a_92.png)

entire network，the question is how are we going to。



![](img/2a478ccbde3374f78e207ac29ff6f98a_94.png)

incorporate it into different models，what if your underlying model is an。



![](img/2a478ccbde3374f78e207ac29ff6f98a_96.png)

inception module，you have x you do the inception module，on top of it and then you take。



![](img/2a478ccbde3374f78e207ac29ff6f98a_98.png)

xtilda out how do you incorporate，squeeze and excitation。



![](img/2a478ccbde3374f78e207ac29ff6f98a_100.png)

in an inception you are you do your，inception stuff，you take the output so the inception is。



![](img/2a478ccbde3374f78e207ac29ff6f98a_102.png)

just your transformation，that's f transformation the rest of it。



![](img/2a478ccbde3374f78e207ac29ff6f98a_104.png)

is a global，average pulling a fully connected a relu。



![](img/2a478ccbde3374f78e207ac29ff6f98a_106.png)

a fully connected a sigmoid and then you，scale，so the operations that you are seeing。



![](img/2a478ccbde3374f78e207ac29ff6f98a_108.png)

here are exactly the operations that you，are seeing，with squeeze excitation and scaling。



![](img/2a478ccbde3374f78e207ac29ff6f98a_110.png)

that's how you incorporate，squeeze and excitation in an inception。



![](img/2a478ccbde3374f78e207ac29ff6f98a_112.png)

module，how would you do it with residual，connections。



![](img/2a478ccbde3374f78e207ac29ff6f98a_114.png)

that's a usual residual connection what，you do is you do your。



![](img/2a478ccbde3374f78e207ac29ff6f98a_116.png)

residual which is a non-linear part of，the，resnet and then you do your global fully。



![](img/2a478ccbde3374f78e207ac29ff6f98a_118.png)

connected value fully connected sigmoid，you scale you add it to your residual。



![](img/2a478ccbde3374f78e207ac29ff6f98a_120.png)

and then you add the input to the，output after the scaling that's how you，incorporate。



![](img/2a478ccbde3374f78e207ac29ff6f98a_122.png)

squeeze and excitation inside a resnet。

![](img/2a478ccbde3374f78e207ac29ff6f98a_124.png)

so you as you can see you can do it for，different models that's an。

idea you can apply that you can apply to。

![](img/2a478ccbde3374f78e207ac29ff6f98a_126.png)

different，network structures so that's a hyper，idea。



![](img/2a478ccbde3374f78e207ac29ff6f98a_128.png)

so let's see how it performs and let's，go through these papers。

we cover dresnette now you are seeing it。

![](img/2a478ccbde3374f78e207ac29ff6f98a_130.png)

here，and that's now a good idea to wrap our，head around。



![](img/2a478ccbde3374f78e207ac29ff6f98a_132.png)

how these networks are comparing to each，other resnet 152。



![](img/2a478ccbde3374f78e207ac29ff6f98a_134.png)

is giving you an error rate。

![](img/2a478ccbde3374f78e207ac29ff6f98a_136.png)

or a top one error rate up to any three。

![](img/2a478ccbde3374f78e207ac29ff6f98a_138.png)

when you use 224 by 224 images，when you use a higher resolution image。



![](img/2a478ccbde3374f78e207ac29ff6f98a_140.png)

the error is going to go down，so higher resolution helps resnet 200。



![](img/2a478ccbde3374f78e207ac29ff6f98a_142.png)

200 layers of residual connections，that's the performance inception v3。



![](img/2a478ccbde3374f78e207ac29ff6f98a_144.png)

we covered it inception v4 we covered it，in class。

![](img/2a478ccbde3374f78e207ac29ff6f98a_146.png)

inception resnet v2 we covered it last，session。

![](img/2a478ccbde3374f78e207ac29ff6f98a_148.png)

so that's how it's come how it compares，to the，previous state of the art so each one of。

these simple ideas，was improving the state of the art it。



![](img/2a478ccbde3374f78e207ac29ff6f98a_150.png)

was pushing the envelope，res next we covered it is doing even，better。



![](img/2a478ccbde3374f78e207ac29ff6f98a_152.png)

densenet attention 92 we didn't cover it，in class。

![](img/2a478ccbde3374f78e207ac29ff6f98a_154.png)

very deep polynet we didn't cover it。

![](img/2a478ccbde3374f78e207ac29ff6f98a_156.png)

pyramid net we didn't cover，dpn we didn't cover but as you can see。

each one of them is improving the state。

![](img/2a478ccbde3374f78e207ac29ff6f98a_158.png)

of the art，now squeeze and excitation network is，beating all of them。

so that's a very good top five error and，there are some methods that are even。



![](img/2a478ccbde3374f78e207ac29ff6f98a_160.png)

beating，squeeze and excitation network nas net。

![](img/2a478ccbde3374f78e207ac29ff6f98a_162.png)

is coming from automatic machine，learning we are going to cover that。



![](img/2a478ccbde3374f78e207ac29ff6f98a_164.png)

it's neural architecture search and net，is for net，that's how good it's doing and squeeze。



![](img/2a478ccbde3374f78e207ac29ff6f98a_166.png)

and excitation net，they。

![](img/2a478ccbde3374f78e207ac29ff6f98a_168.png)

change post challenge that would have uh。

![](img/2a478ccbde3374f78e207ac29ff6f98a_170.png)

improved the accuracy so usually，the way that things work is that they。



![](img/2a478ccbde3374f78e207ac29ff6f98a_172.png)

submit their work，so i'm not sure exactly what they。



![](img/2a478ccbde3374f78e207ac29ff6f98a_174.png)

changed but that doesn't really matter，much probably they trained it，differently probably。



![](img/2a478ccbde3374f78e207ac29ff6f98a_176.png)

they had different english，initialization for debates and biases，maybe they were。



![](img/2a478ccbde3374f78e207ac29ff6f98a_178.png)

using different model ensemble，but what i want you to take away from，this paper。



![](img/2a478ccbde3374f78e207ac29ff6f98a_180.png)

is this big idea of squeeze excitation，and scale。

![](img/2a478ccbde3374f78e207ac29ff6f98a_182.png)

and you're paying different attention，with that scaling，operation to different channels you're。



![](img/2a478ccbde3374f78e207ac29ff6f98a_184.png)

channel，than another channel and the network is。

![](img/2a478ccbde3374f78e207ac29ff6f98a_186.png)

going to decide that，on its own does that answer your，question i tried。



![](img/2a478ccbde3374f78e207ac29ff6f98a_188.png)

yeah no that's good thank you so now，let's take a lot of these。



![](img/2a478ccbde3374f78e207ac29ff6f98a_190.png)

a bunch of these famous networks like，resnet50。

![](img/2a478ccbde3374f78e207ac29ff6f98a_192.png)

resnet res next vgg，patch norm inception these are the，original。



![](img/2a478ccbde3374f78e207ac29ff6f98a_194.png)

top one and top five errors reported in，the paper。

![](img/2a478ccbde3374f78e207ac29ff6f98a_196.png)

this is their own reimplementation this，is the number of flops。



![](img/2a478ccbde3374f78e207ac29ff6f98a_198.png)

that it takes floating point operations，after adding resnet yes you get some，improvements。



![](img/2a478ccbde3374f78e207ac29ff6f98a_200.png)

which is great and the cool thing is，that，these operations squeeze excitation，scale。

are not adding much more operations。

![](img/2a478ccbde3374f78e207ac29ff6f98a_202.png)

so these networks are going to be as，fast as the previous ones。



![](img/2a478ccbde3374f78e207ac29ff6f98a_204.png)

slightly more costly computationally。

![](img/2a478ccbde3374f78e207ac29ff6f98a_206.png)

but more accurate significantly more，accurate，and why is it not costly because the。

only operation that you are doing is。

![](img/2a478ccbde3374f78e207ac29ff6f98a_208.png)

just a bunch of，summations a bunch of matrix vector，multiplications。



![](img/2a478ccbde3374f78e207ac29ff6f98a_210.png)

and a scalar being multiplied by a，matrix。

![](img/2a478ccbde3374f78e207ac29ff6f98a_212.png)

so these are the added flops and like，any other network this one also。



![](img/2a478ccbde3374f78e207ac29ff6f98a_214.png)

different。

![](img/2a478ccbde3374f78e207ac29ff6f98a_216.png)

output the output could be a goldfish it，could be a pug it could be a plane it，could be a cliff etc。



![](img/2a478ccbde3374f78e207ac29ff6f98a_218.png)

you are plotting the activity of these，channels。

![](img/2a478ccbde3374f78e207ac29ff6f98a_220.png)

what are you plotting you are plotting，these excited ones。



![](img/2a478ccbde3374f78e207ac29ff6f98a_222.png)

basically the attention early on in the，layers，you don't see much difference in the，activities。

but as you go deeper inside the network。

![](img/2a478ccbde3374f78e207ac29ff6f98a_224.png)

these activities are becoming more，discriminative。

![](img/2a478ccbde3374f78e207ac29ff6f98a_226.png)

so you're starting to see the difference，between a goldfish and a pot in the。



![](img/2a478ccbde3374f78e207ac29ff6f98a_228.png)

activities of these networks，after the excitation so now you're，visualizing。



![](img/2a478ccbde3374f78e207ac29ff6f98a_230.png)

it's giving you a means of visualizing，what's inside what's happening inside，your network。

we're gonna cover a lot more。

![](img/2a478ccbde3374f78e207ac29ff6f98a_232.png)

visualization but this is the first time，that you're visualizing something inside。



![](img/2a478ccbde3374f78e207ac29ff6f98a_234.png)

your convolution，the cool thing about these attention，mechanisms is that。



![](img/2a478ccbde3374f78e207ac29ff6f98a_236.png)

it's easy to visualize them and this is，the first time that you're seeing。



![](img/2a478ccbde3374f78e207ac29ff6f98a_238.png)

attention in this class i think we are，one minute over time，for those of you who have questions you。



![](img/2a478ccbde3374f78e207ac29ff6f98a_240.png)

are more than welcome，to stay and ask and for those of you who，want to leave。



![](img/2a478ccbde3374f78e207ac29ff6f98a_242.png)

you can leave i had a quick question um。

![](img/2a478ccbde3374f78e207ac29ff6f98a_244.png)

not for many of today's material but，just from something from the last slide。



![](img/2a478ccbde3374f78e207ac29ff6f98a_246.png)

there was a graph in there that was，showing the。

![](img/2a478ccbde3374f78e207ac29ff6f98a_248.png)

the drop in error as learning progresses。

![](img/2a478ccbde3374f78e207ac29ff6f98a_250.png)

and i noticed that，we didn't see any of those sort of，sudden drop-offs。



![](img/2a478ccbde3374f78e207ac29ff6f98a_252.png)

um in the error like we had been seeing，for other，sort of like learning progressions。

uh i don't know if so yeah that that，chart right there um in other charts。

like that we had seen this sort of like，it would be a slow，descent and then we'd have a sharp drop。

and then like a slow descent and then a，sharp drop，yes so there that's a good question。

there are a couple of ways，to do your learning rate schedule，the big idea with your learning rate is。

that you want to start big，because you want to learn faster and，then you want to gradually，it。

is to do it step wise like after，4d epochs lower，the learning rate by a half and then。

you're gonna see a sudden jump，and then after 60 epoch 60，do another step and that's going to give。

you that step behavior，another way of doing that is to decrease，your learning rate。

smoothly from 20 up until 60 either，linearly either exponentially。

so there are various ways of doing it，and that's called learning grade，schedule。

so they're using a different learning，grade schedule okay，and this one's just more continuous sort。

of instead of yes。