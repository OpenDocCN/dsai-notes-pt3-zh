# P18：L9.1- 恒等映射 - ShowMeAI - BV1Dg411F71G

last session we talked about，resnets and we saw that these shortcut，connections are gonna。

help us a lot when it comes to training，deeper neural networks。

now let's try to expand on that and go a，little bit into，more details this is the next paper by。

the same authors。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_1.png)

and they actually want to go even deeper，experiment with very deep networks like。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_3.png)

1 000 layers deep and see what happens，this is the original network or the。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_5.png)

original building block，of a residual network the feature maps。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_7.png)

from the previous layer goes in，then you do a convolution you do a batch。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_9.png)

nor，then a value non-linearity。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_11.png)

then you do a another convolution then a，batch norm，then you add it to xl。

using the addition operation then you do。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_13.png)

a non-linearity and then that's going to，be your。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_15.png)

xl plus one what this paper is proposing，is that there should be。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_17.png)

no non-linearity or no operations。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_19.png)

on the shortcut branch all you can do is，just an addition，so there shouldn't be any value here。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_21.png)

there shouldn't be any，batch norm on the main branch on the，shortcut branch and this is actually the。

main branch where the。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_23.png)

information is flowing from one layer to，the other one，so i remember one of you asked me what。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_25.png)

is the proper way of applying，batch norm and non-linearity，on top of a convolution it was one of。

the first sessions。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_27.png)

that one of you asked me about it and i，promised that we are going to go。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_29.png)

and study it more carefully this is，where we are doing that，so the order is batch norm value weight。

batch number value weight and then you，add it to，the residual connection why is this。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_31.png)

important let's take a look at the，training loss。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_33.png)

and the test error the original resnet，if you try to train it this is going to。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_35.png)

be the curve，that you get during your training。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_37.png)

as the iterations of your stochastic，gradient descent。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_39.png)

are progressing this is the curve that，you get for，training actually this is the curve that。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_41.png)

you get for testing，and this is what you get for training。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_43.png)

error basically your last function，this simple modification。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_45.png)

of doing batch gnome value and then your，convolution。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_47.png)

is gonna drop the error rate the test，error rate significantly。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_49.png)

at the same time your network is trading，better now let's see why that's the case。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_51.png)

this is a typical form this is actually，the general form that is gonna cover，both。

a and b cases you have yl。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_53.png)

then you do some function of xl，and then you add it back to a neural，network。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_55.png)

it's actually a neural network block and，then you take the output which is yl。

you push it through a non-linearity and，you get xl plus one，which is going to be ready for the next。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_57.png)

layer now let's see。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_59.png)

some particular form of hnf if h。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_61.png)

is the identity and f is value，you get the original configuration of，resnet back，it。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_63.png)

if h is identity that's just xl plus，the residual and then f is going to be。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_65.png)

the value here，and that's the addition so that's the，original configuration。

now let's assume that both f and h，are identity and see what happens we。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_67.png)

know that it's not identity，we know that there is some non-linearity。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_69.png)

there but let's assume both of them are，identity because we want to go towards。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_71.png)

this formula，they are。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_73.png)

both identity you get x l，plus one is equal to h l。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_75.png)

plus caliographic f now you can，do the iteration and go deeper and see，what happens i don't know。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_77.png)

five layers deeper or what happens at，the final layer。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_79.png)

xl is going to be equal to xl plus a，summation of。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_81.png)

these caliographic f's of course with，different parameters but。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_83.png)

another。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_85.png)

f and you can see that the information，is flowing from a very low level。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_87.png)

in your neural network to very deep，inside your neural network。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_89.png)

so there is still this identity，structure，so there is still this shortcut path。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_91.png)

from a very i don't know let's call the，shallow。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_93.png)

layer of your network to the very deep，ones，same thing happens when you do the。

gradients you are doing the。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_95.png)

gradient of your loss with respect to xl，that's going to be the gradient of loss。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_97.png)

with respect to，x capital l the derivative of。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_99.png)

x capital l with respect to x，l and then you're going to use this。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_101.png)

formula this term we can keep it。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_103.png)

on one side and then there is a one here，plus the derivative of this term with，respect to xl。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_105.png)

now this guy has the same structure as，the forward path now。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_107.png)

remember you know this from because now，you're going you're back propagating the，errors。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_109.png)

this time you know if you multiply it by，one，that's gonna be this term plus。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_111.png)

some non-linearity so you still have the，structure that the information。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_113.png)

is flowing from high up in your network，from very deep layers to the ones that。

are closer to your image，so is everything clear any questions so，far。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_115.png)

now let's see what happens if this，doesn't happen。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_117.png)

what if h xl，is just a parameter lambda。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_119.png)

l times xl so some parameter。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_121.png)

is being multiplied by your excel，this is not even non-linear this is just。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_123.png)

a new linear operation，you're just multiplying it by a scalar，let's see what happens。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_125.png)

you're gonna do the same exercise as we，just did，that's what you get for xl plus one if。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_127.png)

you do your iterations，to go deeper that's what you get there。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_129.png)

are some terms that are being multiplied，by。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_131.png)

well，so these terms we are gonna call that f，hat。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_133.png)

so that's going to give you f hat which，is just a non-linearity。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_135.png)

we don't care that much about it but，what we care is here，and we know that whenever you are。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_137.png)

multiplying a lot of numbers together，two things can happen they are either，gonna explode。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_139.png)

or they are gonna vanish so it's either，gonna explode，in the forward path or vanish what。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_141.png)

happens to the backward path，this is what happens rather than having，a one here。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_143.png)

you have a bunch of numbers that are，being multiplied together。

so these are problematic if you have a。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_145.png)

non-linearity。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_147.png)

that term over there the product of，lambdas is just uh can you，you can approximate it by their。

derivative，of the nonlinear function so you can。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_149.png)

approximate it by the derivative of this，h that's a first order approximation but。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_151.png)

that's going to give you the idea，what happens when you have a non-linear。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_153.png)

case and that's the reason，why the order matters of your operations。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_155.png)

and it really matters that you don't，have any。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_157.png)

any operations on the main path where，the information，is flowing basically on the shortcut and。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_159.png)

that's why you get a better test error，and training behavior any questions so，far so you mentioned。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_161.png)

uh in the previous session，that whatever what about other。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_163.png)

frameworks，what about other blocks。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_165.png)

or other formulation you said maybe you，can put a weight，on excel what happens what if you put a。

drop out，here to drop the information from。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_167.png)

flowing，from one layer to the other one and the，objective is that。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_169.png)

you want to make your network deeper or，you want to force it to go through。

the complicated path what happens in，those cases，this is the original one this is what，you have here。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_171.png)

we're just removing batch norms what if，you do this。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_173.png)

what if you keep half of the input，on your shortcut basically multiply xl，by 0。5 multiply。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_175.png)

the other branch of your neural network。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_177.png)

by 0。5 basically keep half of the，xl and half of the other information，that's coming from the。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_179.png)

more complicated route add them up，together，and get a player non-linearity and see。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_181.png)

what happens，that could be one option this could be。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_183.png)

another option，you put a one by one convolution on top，of your。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_185.png)

xl you push it through sigmoid sigmoid。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_187.png)

is a number between zero and one，so that's sort of a probability it's，like this。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_189.png)

but now these are being learned these，two parameters。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_191.png)

you multiply the sigmoid one。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_193.png)

by the complicated route and the，shortcut route you multiply it by one，minus sigmoid。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_195.png)

and then you push it through you add it，and then you do the，non-linearity this is called exclusive。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_197.png)

gating，and there are actually some papers where，doing that and this paper is。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_199.png)

studying all of those cases and which，one is better you can forget about。

multiplying by a sigmoid and just。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_201.png)

keep one minus sigma here and basically，it's called。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_203.png)

shortcut only gating you can put a one，by one convolution maybe you want to。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_205.png)

change the dimension from xl to the，other one，this is actually the second case。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_207.png)

in resnet where you have the convolution，shortcut you can actually have a dropout。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_209.png)

there，this one is going to sort of have a。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_211.png)

stochastic nature，for your shortcuts sometimes the，shortcuts are there。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_213.png)

sometimes they are not and you want the，network to depend。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_215.png)

less on the shortcut connections，and basically make it force it to go，through the non-linearities。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_217.png)

so the paper studies all of these。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_219.png)

and because of the reason that i just，explained here，none of them is performing as good as。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_221.png)

having nothing，to interfere with the linear dynamics so，basically the linear part of your neural。

network has to be，interfere。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_223.png)

with that dynamics and the paper also，studies different。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_225.png)

configurations of weights and batch，norms this is the original one。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_227.png)

weight patch non-value weight patch norm，weight。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_229.png)

added patch no value you can have weight，batch norm value weight passion or value。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_231.png)

add it back，or you can have value weight patch no，railways。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_233.png)

and this is the proposed one that is，actually performing the best。

so the order matters batch norm value，weight passion of radio waves。

any questions yes they is there some，intuitive，reasoning as to why they're um。

that order matters um or is it just，trial and error，most of it is trial and error and at the。

same time you can do these sorts of，analysis，to give you a justification for why this，is happening。

for some of them i have a reason for，instance，as you can see it's always weight and。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_235.png)

batch norm，so there is always your batch norm on，top of weight。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_237.png)

so that's the case all the time for，these two cases。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_239.png)

we know it's not gonna perform because，there is some。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_241.png)

obstacle on the shortcut path，these ones are there seems to be no，obstacle。

on the shortcut path but then it's just，a matter of，which operation are doing first and。

could you maybe reiterate，uh it's still not fully clear to me from，that analysis。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_243.png)

how you know that there shouldn't that，the the shortcut should be，you know fully linear we know that。

when you go from layer xl to one layer，on top of it。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_245.png)

there is a linear structure okay，that we know but now we want to do the，same thing。

we want the information from neared our。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_247.png)

image，to go very deep inside our neural，network。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_249.png)

and we want that linear connection to，still exist，and that's what's happening here you go。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_251.png)

from basically you can go from your，image。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_253.png)

to the last layer directly through a，shortcut。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_255.png)

if you have no non-linearity on h，and f so this analysis is from one layer，to the next one。

this analysis is from one layer to ten，layers，next。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_257.png)

and if there is slight thing there is a，slight。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_259.png)

change even a linear one，it's not going to give you what you want。

because the information is not flowing。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_261.png)

directly from，one layer to 10 layers deeper。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_263.png)

down the network because there's some，stuff blocking the way。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_265.png)

does it answer your question yeah that，makes a lot of sense。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_267.png)

ones，the analysis that we applied here。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_269.png)

is gonna explain why these ones are just，trial and error。



![](img/4a4d024a0a4b499b4e7a7301d81e6acf_271.png)