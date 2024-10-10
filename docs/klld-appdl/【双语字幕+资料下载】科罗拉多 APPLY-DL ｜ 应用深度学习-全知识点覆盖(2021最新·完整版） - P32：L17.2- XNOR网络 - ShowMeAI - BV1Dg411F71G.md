# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P32：L17.2- XNOR网络 - ShowMeAI - BV1Dg411F71G

![](img/dcea48a3ac4055614224c1aca4422e5b_0.png)

let's move on i remember it was last，session，that one of you mentioned can we，actually store。



![](img/dcea48a3ac4055614224c1aca4422e5b_2.png)

the weights in lower bits rather than 32，can we do it in 16 bits rather than 16。

can we do it in eight。

![](img/dcea48a3ac4055614224c1aca4422e5b_4.png)

so this paper takes it to the extreme it，says i'm gonna store the weights。



![](img/dcea48a3ac4055614224c1aca4422e5b_6.png)

in a binary basically zero one one zero，or one in a single bit。

and then we're gonna see where the name，xnor，comes in as we go into details but we。



![](img/dcea48a3ac4055614224c1aca4422e5b_8.png)

are using binary convolutions now，we are binarizing our network so here is，a big picture。



![](img/dcea48a3ac4055614224c1aca4422e5b_10.png)

you have an image you have a bunch of，filters and，let's look at this part of the network。



![](img/dcea48a3ac4055614224c1aca4422e5b_12.png)

there is the input and there is the，weights，and the weights are convolutional。



![](img/dcea48a3ac4055614224c1aca4422e5b_14.png)

weights it means that you're gonna keep，sliding them over these，inputs tensor with a standard。



![](img/dcea48a3ac4055614224c1aca4422e5b_16.png)

convolution，everything is 32 bits let's assume，that's 32。



![](img/dcea48a3ac4055614224c1aca4422e5b_18.png)

your input is 32 and your weights are，being represented。



![](img/dcea48a3ac4055614224c1aca4422e5b_20.png)

in 32 bits the operations that you're，gonna do，are gonna be addition subtraction and，multiplication。



![](img/dcea48a3ac4055614224c1aca4422e5b_22.png)

you're multiplying two numbers together，and then you're adding your。



![](img/dcea48a3ac4055614224c1aca4422e5b_24.png)

your numbers uh together because you're，doing a dot product，of your filter and the input and that's。



![](img/dcea48a3ac4055614224c1aca4422e5b_26.png)

going to be our baseline，everything is going to be 1 because，that's our baseline in terms of memory。



![](img/dcea48a3ac4055614224c1aca4422e5b_28.png)

and computation，and that's our baseline accuracy we are，going to do。

two steps one is binarize the weights。

![](img/dcea48a3ac4055614224c1aca4422e5b_30.png)

weights，and the inputs binarizing the weight，means that you're gonna end up with。



![](img/dcea48a3ac4055614224c1aca4422e5b_32.png)

either one or negative one，you have only two values it's either one，or a negative one。



![](img/dcea48a3ac4055614224c1aca4422e5b_34.png)

and if that's the case when you multiply。

![](img/dcea48a3ac4055614224c1aca4422e5b_36.png)

this binary weight and your input the，only operations that you're going to do。

is addition and subtraction there is not。

![](img/dcea48a3ac4055614224c1aca4422e5b_38.png)

going to be any multiplication because，you're either，positive or negative and then you are。



![](img/dcea48a3ac4055614224c1aca4422e5b_40.png)

adding a positive and a negative number，is that clear so it doesn't make sense。



![](img/dcea48a3ac4055614224c1aca4422e5b_42.png)

to multiply，negative 1 by negative。

![](img/dcea48a3ac4055614224c1aca4422e5b_44.png)

0。21 you can just use，addition instead rather than doing the。



![](img/dcea48a3ac4055614224c1aca4422e5b_46.png)

multiplication，in terms of memory saving you're going，to save 32。



![](img/dcea48a3ac4055614224c1aca4422e5b_48.png)

in terms of computational saving you're，gonna save by two，the other step is to actually binarize。



![](img/dcea48a3ac4055614224c1aca4422e5b_50.png)

your inputs as well，as you can guess you're gonna lose some。



![](img/dcea48a3ac4055614224c1aca4422e5b_52.png)

accuracy here，but you're gonna have a lot of，computational savings。



![](img/dcea48a3ac4055614224c1aca4422e5b_54.png)

because rather than doing addition and，subtraction you're doing x nor operation。

and these are much faster。

![](img/dcea48a3ac4055614224c1aca4422e5b_56.png)

okay let's go into more details that's，the big picture this middle row seems，very。



![](img/dcea48a3ac4055614224c1aca4422e5b_58.png)

suspect to me because didn't we show。

![](img/dcea48a3ac4055614224c1aca4422e5b_60.png)

that if we quantize too much we lose，accuracy when we were doing like deep，concussion。



![](img/dcea48a3ac4055614224c1aca4422e5b_62.png)

two sessions again but this is like，this is actually different from what we。



![](img/dcea48a3ac4055614224c1aca4422e5b_64.png)

are doing what we did in the deep，comparison，it seems like an even more extreme。

version of quantization。

![](img/dcea48a3ac4055614224c1aca4422e5b_66.png)

um just just recasting things based on，whether they're positive or negative。



![](img/dcea48a3ac4055614224c1aca4422e5b_68.png)

i guess is how they did it here uh，you're very close yes，some some threshold not really we're。

gonna see how things work。

![](img/dcea48a3ac4055614224c1aca4422e5b_70.png)

but once i go through the details you're，gonna see that the method is totally，different。

okay over there you were doing pruning。

![](img/dcea48a3ac4055614224c1aca4422e5b_72.png)

first and then you were，quantizing but that quantization was i。



![](img/dcea48a3ac4055614224c1aca4422e5b_74.png)

think that's the wrong name for it，it was just parameter sharing we're。

finding the centroids and then。

![](img/dcea48a3ac4055614224c1aca4422e5b_76.png)

and there is also another question from，cooper is this starting from the first，layer。



![](img/dcea48a3ac4055614224c1aca4422e5b_78.png)

yes so it's going to start from the，first layer actually not the input image。

we are not binarizing the input image。

![](img/dcea48a3ac4055614224c1aca4422e5b_80.png)

okay that was my question because then，you'd have to like，map it somehow to negative values as。



![](img/dcea48a3ac4055614224c1aca4422e5b_82.png)

well i guess yes，okay but you're under right points。



![](img/dcea48a3ac4055614224c1aca4422e5b_84.png)

when uh you mentioned map it to negative，values。

![](img/dcea48a3ac4055614224c1aca4422e5b_86.png)

when we actually binarize the input we，are gonna，normalize the input basically subtract。



![](img/dcea48a3ac4055614224c1aca4422e5b_88.png)

the mean so you're gonna have some，numbers，but let's see how we're gonna do it。



![](img/dcea48a3ac4055614224c1aca4422e5b_90.png)

first what are the applications，it's gonna have some applications in，virtual reality。



![](img/dcea48a3ac4055614224c1aca4422e5b_92.png)

augmented reality and the smart variable，devices，because now these networks are really。



![](img/dcea48a3ac4055614224c1aca4422e5b_94.png)

small these are the applications，let's see the math that's our input it，has c。



![](img/dcea48a3ac4055614224c1aca4422e5b_96.png)

channels and the resolution is w。

![](img/dcea48a3ac4055614224c1aca4422e5b_98.png)

in and h in weight and height so that's，that's our input tensor this is our。



![](img/dcea48a3ac4055614224c1aca4422e5b_100.png)

weight for a single，filter we're gonna have multiple filters，this is just one filter。



![](img/dcea48a3ac4055614224c1aca4422e5b_102.png)

it has the same number of input channels，as your。

![](img/dcea48a3ac4055614224c1aca4422e5b_104.png)

height，for the filter size and usually with w。

![](img/dcea48a3ac4055614224c1aca4422e5b_106.png)

h。

![](img/dcea48a3ac4055614224c1aca4422e5b_108.png)

input what we are going to do is we are，going to approximate。



![](img/dcea48a3ac4055614224c1aca4422e5b_110.png)

w by a scalar times a binary weight，so it's going to be alpha times b and。



![](img/dcea48a3ac4055614224c1aca4422e5b_112.png)

it's going to be an approximation，because we have some constraints on b it。



![](img/dcea48a3ac4055614224c1aca4422e5b_114.png)

has to be a binary，matrix and alpha still could still be a，32。



![](img/dcea48a3ac4055614224c1aca4422e5b_116.png)

bit float number so alpha is okay but b，we are gonna binary and as i said b is，allowed to take only。

positive and negative values it's either。

![](img/dcea48a3ac4055614224c1aca4422e5b_118.png)

plus one or negative one，that's our binary future and alpha is，our scaling factor。



![](img/dcea48a3ac4055614224c1aca4422e5b_120.png)

and what's going to happen to，convolutions we just saw it up there，that there is no need to do any。



![](img/dcea48a3ac4055614224c1aca4422e5b_122.png)

multiplication when i was explaining，you only need to do addition and。



![](img/dcea48a3ac4055614224c1aca4422e5b_124.png)

subtraction because these values are，either，one or negative one positive or negative。



![](img/dcea48a3ac4055614224c1aca4422e5b_126.png)

and you're going to end up with a bunch，of additions and subtractions。

so your convolutions are going to be。

![](img/dcea48a3ac4055614224c1aca4422e5b_128.png)

very simple you don't need to do any，multiplication and that's how you're，saving。



![](img/dcea48a3ac4055614224c1aca4422e5b_130.png)

2x in terms of computation now let's，flatten。

![](img/dcea48a3ac4055614224c1aca4422e5b_132.png)

these matrices actually these tensors，and turn them into an array or two，arrays。



![](img/dcea48a3ac4055614224c1aca4422e5b_134.png)

of n dimensions and now because we are，flattening。

![](img/dcea48a3ac4055614224c1aca4422e5b_136.png)

the dimension is going to be c by w by，h so this is clear we just flattened two，tensors。



![](img/dcea48a3ac4055614224c1aca4422e5b_138.png)

perfect we are gonna write an objective，function because we want w。



![](img/dcea48a3ac4055614224c1aca4422e5b_140.png)

to be as close as possible to alpha b so，let's just。



![](img/dcea48a3ac4055614224c1aca4422e5b_142.png)

expand this you say w minus alpha b。

![](img/dcea48a3ac4055614224c1aca4422e5b_144.png)

transpose times w minus alpha b，and expand things out you're gonna get，alpha squared。



![](img/dcea48a3ac4055614224c1aca4422e5b_146.png)

term，you're gonna get negative to alpha w。

![](img/dcea48a3ac4055614224c1aca4422e5b_148.png)

transpose times b that's gonna give you，this term plus w transpose times w。



![](img/dcea48a3ac4055614224c1aca4422e5b_150.png)

transpose，coming from this stair so we just，expanding things out。



![](img/dcea48a3ac4055614224c1aca4422e5b_152.png)

let's look at b transpose b b is just a，bunch of。

![](img/dcea48a3ac4055614224c1aca4422e5b_154.png)

happen，an element is either one and it's gonna，get multiplied by。



![](img/dcea48a3ac4055614224c1aca4422e5b_156.png)

one or it's a negative one and it's，gonna get multiplied by。



![](img/dcea48a3ac4055614224c1aca4422e5b_158.png)

negative one and regardless of what the，value is you're going to end up with a 1。

in the end and then because of the。

![](img/dcea48a3ac4055614224c1aca4422e5b_160.png)

transpose here you're doing a summation，over a bunch of ones that's going to。



![](img/dcea48a3ac4055614224c1aca4422e5b_162.png)

give you n，so this term is just n this other term。

![](img/dcea48a3ac4055614224c1aca4422e5b_164.png)

we are going to assume that we know w，since w is known that's just a constant。



![](img/dcea48a3ac4055614224c1aca4422e5b_166.png)

and let's call the constant to be c，now what we want to do is to find the，arg mean。



![](img/dcea48a3ac4055614224c1aca4422e5b_168.png)

basically minimize that objective，function and find。



![](img/dcea48a3ac4055614224c1aca4422e5b_170.png)

the best beta and alpha let's look at，beta let's solve the problem one at a。

time let's try to find beta。

![](img/dcea48a3ac4055614224c1aca4422e5b_172.png)

this is just a constant we don't care，find。

![](img/dcea48a3ac4055614224c1aca4422e5b_174.png)

beta now the only term that's a function，of beta is this term。



![](img/dcea48a3ac4055614224c1aca4422e5b_176.png)

and alpha we assume is always positive，minimizing。

![](img/dcea48a3ac4055614224c1aca4422e5b_178.png)

j is equivalent to maximizing，w transpose b and these are just，constants so this is equivalent to。



![](img/dcea48a3ac4055614224c1aca4422e5b_180.png)

maximizing，that。

![](img/dcea48a3ac4055614224c1aca4422e5b_182.png)

this has to be either positive or，negative beta it has to be plus one or，negative one。



![](img/dcea48a3ac4055614224c1aca4422e5b_184.png)

and as you mentioned the solution to，that maximization problem。

is very simple if you want to maximize。

![](img/dcea48a3ac4055614224c1aca4422e5b_186.png)

this whenever a weight is positive，whenever a weight is positive make your。



![](img/dcea48a3ac4055614224c1aca4422e5b_188.png)

beta，to be plus one and whenever that's，negative。

![](img/dcea48a3ac4055614224c1aca4422e5b_190.png)

make that turn positive make the，multiplication positive，then that's how you're maximizing your。



![](img/dcea48a3ac4055614224c1aca4422e5b_192.png)

objective function，so the solution to this problem is，trivial whenever your rate is positive。



![](img/dcea48a3ac4055614224c1aca4422e5b_194.png)

b1 bi is plus one whenever it's negative，multiplied by negative one so that the。

entire product is positive and then，you're adding a bunch of positive。



![](img/dcea48a3ac4055614224c1aca4422e5b_196.png)

numbers and that's how things are going，to get maximum so beta star。



![](img/dcea48a3ac4055614224c1aca4422e5b_198.png)

is just the sine of w i think we are out，of time，for those of you who have questions。



![](img/dcea48a3ac4055614224c1aca4422e5b_200.png)

you're more than welcome to stay and ask，and for those of you who want to leave。

you are more than welcome to leave uh so。

![](img/dcea48a3ac4055614224c1aca4422e5b_202.png)

i have a quick question well i'm not，really sure what it is actually。



![](img/dcea48a3ac4055614224c1aca4422e5b_204.png)

um um i covered binary connect，um from bengio and two other people at，the uh。



![](img/dcea48a3ac4055614224c1aca4422e5b_206.png)

montreal lab and they did something so，the paper came out almost the same month。



![](img/dcea48a3ac4055614224c1aca4422e5b_208.png)

as this one，and they did something very similar and，i saw that this paper。



![](img/dcea48a3ac4055614224c1aca4422e5b_210.png)

discussed what they did and then they，came out with a new paper，like some some time later and they。



![](img/dcea48a3ac4055614224c1aca4422e5b_212.png)

didn't even cite this paper，but they they like it seemed like they，implemented the same thing。



![](img/dcea48a3ac4055614224c1aca4422e5b_214.png)

yes so that one i'm not sure but，most of these topics in deep learning。



![](img/dcea48a3ac4055614224c1aca4422e5b_216.png)

are happening in a fast pace，so it's very hard to keep track of who。



![](img/dcea48a3ac4055614224c1aca4422e5b_218.png)

did what and who did first and etc，but you're right this paper came after。



![](img/dcea48a3ac4055614224c1aca4422e5b_220.png)

binary connect and there are some，differences，yeah this this one and that one they're。



![](img/dcea48a3ac4055614224c1aca4422e5b_222.png)

very interesting papers，yeah just because they're they're able，to so like go。



![](img/dcea48a3ac4055614224c1aca4422e5b_224.png)

so far with the simple simplification of，the weights。



![](img/dcea48a3ac4055614224c1aca4422e5b_226.png)

yeah this is a great paper can i ask um，for this uh this approach they're just，taking a pre-trained。



![](img/dcea48a3ac4055614224c1aca4422e5b_228.png)

alex net model and then altering their，weights。

![](img/dcea48a3ac4055614224c1aca4422e5b_230.png)

according to this process is that，correct actually。



![](img/dcea48a3ac4055614224c1aca4422e5b_232.png)

there is some training steps going on，okay。

![](img/dcea48a3ac4055614224c1aca4422e5b_234.png)

how，the training is gonna go but the way，that the training goes。



![](img/dcea48a3ac4055614224c1aca4422e5b_236.png)

is that in the training step you keep w，around because you want to do your back。



![](img/dcea48a3ac4055614224c1aca4422e5b_238.png)

propagations correctly，but then every time that you do your。



![](img/dcea48a3ac4055614224c1aca4422e5b_240.png)

back propagation you do this step，you find your beta star and then you，find your alpha star。



![](img/dcea48a3ac4055614224c1aca4422e5b_242.png)

there is actually training going on here，because without training if you buy in a，rise and。

an alex net you're going to lose，everything and you just take the，pre-trained。

thing and you just binarize the you。

![](img/dcea48a3ac4055614224c1aca4422e5b_244.png)

could do that you could warm start your，training。

![](img/dcea48a3ac4055614224c1aca4422e5b_246.png)

but if you start with a with alexnet you，binarize it，you lose the entire information without。

training that's gonna be，outputting garbage okay okay and just on，your forward pass。



![](img/dcea48a3ac4055614224c1aca4422e5b_248.png)

you use this alpha b matrix instead，but when you back propagate you're。



![](img/dcea48a3ac4055614224c1aca4422e5b_250.png)

updating w，exactly when you do back propagation you，do w。



![](img/dcea48a3ac4055614224c1aca4422e5b_252.png)

okay when you do forward propagation you，use alpha star and b star。



![](img/dcea48a3ac4055614224c1aca4422e5b_254.png)

okay cool and that's the in the end，that's the，model that you're gonna put on your。



![](img/dcea48a3ac4055614224c1aca4422e5b_256.png)

device you use alpha star and b。

![](img/dcea48a3ac4055614224c1aca4422e5b_258.png)