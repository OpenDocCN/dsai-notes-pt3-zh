# P16：L8.1- Inception-V3 [续] - ShowMeAI - BV1Dg411F71G

![](img/f4b93c38cb2648887cbd799201d326a5_0.png)

so last session we covered。

![](img/f4b93c38cb2648887cbd799201d326a5_2.png)

uh a little bit of the inception。

![](img/f4b93c38cb2648887cbd799201d326a5_4.png)

architecture and different types of。

![](img/f4b93c38cb2648887cbd799201d326a5_6.png)

or different variants of doing inception。

![](img/f4b93c38cb2648887cbd799201d326a5_8.png)

for instance two three by three，convolutions，stacked on top of each other is gonna。



![](img/f4b93c38cb2648887cbd799201d326a5_10.png)

have，same。

![](img/f4b93c38cb2648887cbd799201d326a5_12.png)

size of a receptive field as a five by，five convolution。



![](img/f4b93c38cb2648887cbd799201d326a5_14.png)

but it's gonna be cheaper so why not use。

![](img/f4b93c38cb2648887cbd799201d326a5_16.png)

so you you can just stack three by three，convolutions on top of each other and，just use that。



![](img/f4b93c38cb2648887cbd799201d326a5_18.png)

for more efficient neural networks。

![](img/f4b93c38cb2648887cbd799201d326a5_20.png)

the other one is one by。

![](img/f4b93c38cb2648887cbd799201d326a5_22.png)

n and n by ones are gonna turn out，to have the same receptive field as n by，m's。



![](img/f4b93c38cb2648887cbd799201d326a5_24.png)

and these are also cheaper because you，have one less for loop。



![](img/f4b93c38cb2648887cbd799201d326a5_26.png)

you have one for loop here another one，here but it then it's stack on top of，each other。



![](img/f4b93c38cb2648887cbd799201d326a5_28.png)

and the other one was that now that you，know，that you can use one by n and n by one。



![](img/f4b93c38cb2648887cbd799201d326a5_30.png)

convolutions，it means that you can just rather than。



![](img/f4b93c38cb2648887cbd799201d326a5_32.png)

stacking on top of each other you can，just put them next to each other and，they concatenate them。

so these were the observations that they。

![](img/f4b93c38cb2648887cbd799201d326a5_34.png)

made in that paper，to improve the accuracy of their model。



![](img/f4b93c38cb2648887cbd799201d326a5_36.png)

then the question is，how are we going to deal with layers。



![](img/f4b93c38cb2648887cbd799201d326a5_38.png)

like this，where you are reducing the number of。

![](img/f4b93c38cb2648887cbd799201d326a5_40.png)

their resolution size or basically your，grid size，how are we gonna deal with that how are。



![](img/f4b93c38cb2648887cbd799201d326a5_42.png)

we gonna change 17 to eight then。

![](img/f4b93c38cb2648887cbd799201d326a5_44.png)

the idea is you can use it this way，there are two ways these two are just。



![](img/f4b93c38cb2648887cbd799201d326a5_46.png)

two ways of looking at the same thing，basically the one on the right says that，you are going from。



![](img/f4b93c38cb2648887cbd799201d326a5_48.png)

resolution 35 by 35 to 17 by 17。but how do you actually do it you you do。



![](img/f4b93c38cb2648887cbd799201d326a5_50.png)

it using strikes，your pulling is gonna have a stride of，two。



![](img/f4b93c38cb2648887cbd799201d326a5_52.png)

then you do a one by one convolution to，reduce the dimension。



![](img/f4b93c38cb2648887cbd799201d326a5_54.png)

basically reduce the number of channels，and then you do a stride of two。



![](img/f4b93c38cb2648887cbd799201d326a5_56.png)

you do the same thing here so this is a，typical example，of how do you how you would reduce the。



![](img/f4b93c38cb2648887cbd799201d326a5_58.png)

grid size from one layer to the other，one，and if you compare to the one on the。



![](img/f4b93c38cb2648887cbd799201d326a5_60.png)

left these are basically very similar。

![](img/f4b93c38cb2648887cbd799201d326a5_62.png)

stride two，here strike two and then there is no one。



![](img/f4b93c38cb2648887cbd799201d326a5_64.png)

by one convolution，so this branch is just left out。



![](img/f4b93c38cb2648887cbd799201d326a5_66.png)

any questions so far there is another，modification。



![](img/f4b93c38cb2648887cbd799201d326a5_68.png)

and that has nothing to do with the with，the structure。



![](img/f4b93c38cb2648887cbd799201d326a5_70.png)

of the neural network it has to do with，the loss，it has to do with the way that you。



![](img/f4b93c38cb2648887cbd799201d326a5_72.png)

formulate your loss function，but let's remind how a typical loss，function works。



![](img/f4b93c38cb2648887cbd799201d326a5_74.png)

for a deep neural network let's say，x is your training example that's the。



![](img/f4b93c38cb2648887cbd799201d326a5_76.png)

input that's one image，and k is the corresponding label。



![](img/f4b93c38cb2648887cbd799201d326a5_78.png)

which could be one up until k capital k。

![](img/f4b93c38cb2648887cbd799201d326a5_80.png)

so in the case of imagenet，you're gonna have 1000 labels capital k。



![](img/f4b93c38cb2648887cbd799201d326a5_82.png)

is 1000。and what you do is in the last layer，there is a linear。



![](img/f4b93c38cb2648887cbd799201d326a5_84.png)

layer that is turning your 2048。

![](img/f4b93c38cb2648887cbd799201d326a5_86.png)

dimensions，and projecting it into 1000。

![](img/f4b93c38cb2648887cbd799201d326a5_88.png)

and then on top of that you're going to，apply a softmax。



![](img/f4b93c38cb2648887cbd799201d326a5_90.png)

so this is the input to the softmax and，the output is going to have the same，size。



![](img/f4b93c38cb2648887cbd799201d326a5_92.png)

but what is a soft max so far we were，not covering it and i think now it's a，good time to cover it。



![](img/f4b93c38cb2648887cbd799201d326a5_94.png)

so the softmax is going to take。

![](img/f4b93c38cb2648887cbd799201d326a5_96.png)

these logics z k's which are，the outputs of your linear layer the。



![](img/f4b93c38cb2648887cbd799201d326a5_98.png)

last linear layer，and then it's going to turn that into，probabilities it's going to take z k。



![](img/f4b93c38cb2648887cbd799201d326a5_100.png)

take the exponential and divide it by，the summation so this guy is going to，normalize。



![](img/f4b93c38cb2648887cbd799201d326a5_102.png)

it exponential is going to make sure，that，things are positive and then once you。



![](img/f4b93c38cb2648887cbd799201d326a5_104.png)

divide by the x，the summation over the exponentials of。



![](img/f4b93c38cb2648887cbd799201d326a5_106.png)

all the other classes，you are turning the output into a。



![](img/f4b93c38cb2648887cbd799201d326a5_108.png)

probability，now they're gonna sum to one if you put，a summation here over。



![](img/f4b93c38cb2648887cbd799201d326a5_110.png)

k the numerator and denominator are，gonna cancel out and then you're gonna。



![](img/f4b93c38cb2648887cbd799201d326a5_112.png)

get a one，so now this is a probability is that，clear yes no。



![](img/f4b93c38cb2648887cbd799201d326a5_114.png)

okay perfect and let's say q，is gonna denote your ground truth。



![](img/f4b93c38cb2648887cbd799201d326a5_116.png)

distribution，what is the ground truth you know what。



![](img/f4b93c38cb2648887cbd799201d326a5_118.png)

is the corresponding k，if it's。

![](img/f4b93c38cb2648887cbd799201d326a5_120.png)

the image of a tiger you know that。

![](img/f4b93c38cb2648887cbd799201d326a5_122.png)

the corresponding label is gonna be a，tiger，so you're gonna pick one of these let's，say the 100th。



![](img/f4b93c38cb2648887cbd799201d326a5_124.png)

type。

![](img/f4b93c38cb2648887cbd799201d326a5_126.png)

tiger and let's call that kstar that's，your ground truth okay a star is the，ground truth。



![](img/f4b93c38cb2648887cbd799201d326a5_128.png)

is one of these numbers for instance for，the case of tiger it's 100th one。



![](img/f4b93c38cb2648887cbd799201d326a5_130.png)

your k is gonna be a delta d。

![](img/f4b93c38cb2648887cbd799201d326a5_132.png)

rock function what is that if k，is equal to k star if you are at the，true label。



![](img/f4b93c38cb2648887cbd799201d326a5_134.png)

you get a one otherwise it's zero and if，you add it over k's you see that that's。



![](img/f4b93c38cb2648887cbd799201d326a5_136.png)

that adds to one so that's actually a，distribution。



![](img/f4b93c38cb2648887cbd799201d326a5_138.png)

and it's peaking at one of your correct，labels at k star so what is our loss。



![](img/f4b93c38cb2648887cbd799201d326a5_140.png)

function then，this part you know from the first slide，you know that。



![](img/f4b93c38cb2648887cbd799201d326a5_142.png)

you are going to maximize the likelihood，this is the likelihood。

maximizing the likelihood is equivalent。

![](img/f4b93c38cb2648887cbd799201d326a5_144.png)

to maximizing the log of the likelihood。

![](img/f4b93c38cb2648887cbd799201d326a5_146.png)

because log is increasing is uniformly，increasing function。



![](img/f4b93c38cb2648887cbd799201d326a5_148.png)

so it doesn't change the maximum value，and then in machine learning we usually，like to minimize。



![](img/f4b93c38cb2648887cbd799201d326a5_150.png)

that's why you multiply by a negative，sign that's going to give your。



![](img/f4b93c38cb2648887cbd799201d326a5_152.png)

negative log likelihood basically you，want to increase the likelihood of the，correct label。



![](img/f4b93c38cb2648887cbd799201d326a5_154.png)

so that part we know from the first，slide，and this and this is pretty intuitive if。



![](img/f4b93c38cb2648887cbd799201d326a5_156.png)

you increase the probability of the，correct one，because everything has to add up to one。



![](img/f4b93c38cb2648887cbd799201d326a5_158.png)

you're decreasing the probability of the，other ones。



![](img/f4b93c38cb2648887cbd799201d326a5_160.png)

so there is that constraint implicitly，in your model，so that's doing the correct thing and if。

you write。

![](img/f4b93c38cb2648887cbd799201d326a5_162.png)

the cross-entropy diff definition this，is just a notation for cross-entropy。



![](img/f4b93c38cb2648887cbd799201d326a5_164.png)

between two distributions h of q，and p and what i'm writing here is just。



![](img/f4b93c38cb2648887cbd799201d326a5_166.png)

the definition，of cross-entropy so you take the，expected value。



![](img/f4b93c38cb2648887cbd799201d326a5_168.png)

basically this is your expected value of，the log of the。



![](img/f4b93c38cb2648887cbd799201d326a5_170.png)

distribution log of p and because。

![](img/f4b93c38cb2648887cbd799201d326a5_172.png)

q is a delta function most of the times，it's zero，it's only one when k is equal to k star。



![](img/f4b93c38cb2648887cbd799201d326a5_174.png)

this summation is going to collapse into，the term that you have on the right。



![](img/f4b93c38cb2648887cbd799201d326a5_176.png)

so cross entropy loss function is，equivalent to。

![](img/f4b93c38cb2648887cbd799201d326a5_178.png)

negative log likelihood so do you have，any questions，a。



![](img/f4b93c38cb2648887cbd799201d326a5_180.png)

single you have multiple labels per，image，you mean you have multiple correct。



![](img/f4b93c38cb2648887cbd799201d326a5_182.png)

labels yes，yes that's right objects in your maybe。

![](img/f4b93c38cb2648887cbd799201d326a5_184.png)

there's a tiger there's a dog and a，cat simultaneously in your image that's，what you're saying。



![](img/f4b93c38cb2648887cbd799201d326a5_186.png)

yes the answer is no you cannot use this，even if you change q it doesn't sort of。



![](img/f4b93c38cb2648887cbd799201d326a5_188.png)

work，no because of this assumption that。

![](img/f4b93c38cb2648887cbd799201d326a5_190.png)

you're saying that the probabilities，have to add up to one，but then your probabilities are not。

going to add up to one because there are。

![](img/f4b93c38cb2648887cbd799201d326a5_192.png)

two objects，the way that you fix that the fix is，very simple you use a seek point。



![](img/f4b93c38cb2648887cbd799201d326a5_194.png)

ah okay thank you because the，probability of your dog and cat。



![](img/f4b93c38cb2648887cbd799201d326a5_196.png)

if you have two of them in your image，they don't have to necessarily add up to。



![](img/f4b93c38cb2648887cbd799201d326a5_198.png)

one because with probability。

![](img/f4b93c38cb2648887cbd799201d326a5_200.png)

i don't know 0。9，the object on the left could be either a。



![](img/f4b93c38cb2648887cbd799201d326a5_202.png)

dog，or a window okay。

![](img/f4b93c38cb2648887cbd799201d326a5_204.png)

and then the probability of the object，on the lower left of your image。



![](img/f4b93c38cb2648887cbd799201d326a5_206.png)

could be either a cat or a bird，so they don't have to add up to one so。



![](img/f4b93c38cb2648887cbd799201d326a5_208.png)

this assumption doesn't work anymore，but that's a great question and there。



![](img/f4b93c38cb2648887cbd799201d326a5_210.png)

are actually sometimes that you want to，identify multiple objects in your image。



![](img/f4b93c38cb2648887cbd799201d326a5_212.png)

we're going to cover that later on in，the course any other questions。



![](img/f4b93c38cb2648887cbd799201d326a5_214.png)

loss，sometimes you hear the negative，likelihood loss。



![](img/f4b93c38cb2648887cbd799201d326a5_216.png)

but these are equivalent why because。

![](img/f4b93c38cb2648887cbd799201d326a5_218.png)

your ground truth has a delta dirac，distribution okay so far so good。



![](img/f4b93c38cb2648887cbd799201d326a5_220.png)

the paper didn't do anything special，it's just。

![](img/f4b93c38cb2648887cbd799201d326a5_222.png)

what has been around forever what，changed，did they make they observed that。



![](img/f4b93c38cb2648887cbd799201d326a5_224.png)

sometimes，these neural networks are gonna overfit，because。



![](img/f4b93c38cb2648887cbd799201d326a5_226.png)

the way that this loss function is，working is that it's pushing。



![](img/f4b93c38cb2648887cbd799201d326a5_228.png)

the correct label or the logit，of the correct label to go to infinity。



![](img/f4b93c38cb2648887cbd799201d326a5_230.png)

and the other ones go to zero。

![](img/f4b93c38cb2648887cbd799201d326a5_232.png)

so there is a huge gap in the，logit space between z k。



![](img/f4b93c38cb2648887cbd799201d326a5_234.png)

z k star and other z k's so one of them，is going to go to infinity and the other。



![](img/f4b93c38cb2648887cbd799201d326a5_236.png)

ones are gonna go to zero，so this has two problems one is that。



![](img/f4b93c38cb2648887cbd799201d326a5_238.png)

it's gonna make the learning difficult，when you take the gradients the other。



![](img/f4b93c38cb2648887cbd799201d326a5_240.png)

one is that，it helps your model overfit。

![](img/f4b93c38cb2648887cbd799201d326a5_242.png)

if you give enough capacity to your，neural network。



![](img/f4b93c38cb2648887cbd799201d326a5_244.png)

as you are doing here it might actually，push zk to be infinity。



![](img/f4b93c38cb2648887cbd799201d326a5_246.png)

and then it turns out that it's，overfitting it's memorizing your，training data。



![](img/f4b93c38cb2648887cbd799201d326a5_248.png)

so the idea is that you can replace the，label。

![](img/f4b93c38cb2648887cbd799201d326a5_250.png)

the correct label with something random，maybe a uniform distribution so what。



![](img/f4b93c38cb2648887cbd799201d326a5_252.png)

this does，is that let's say you pick the image of，a，tiger most of the times epsilon is a。

small number。

![](img/f4b93c38cb2648887cbd799201d326a5_254.png)

most of the times the correct label，associated with this is going to be the，underlying truth。

the ground truth it's gonna be tiger but，then sometimes。



![](img/f4b93c38cb2648887cbd799201d326a5_256.png)

you say that's not a tiger。

![](img/f4b93c38cb2648887cbd799201d326a5_258.png)

you say my ground truth is，just something random that's a bird or，that's a。



![](img/f4b93c38cb2648887cbd799201d326a5_260.png)

that's a window that's a door so，sometimes you trick your model。



![](img/f4b93c38cb2648887cbd799201d326a5_262.png)

you give it the wrong data so let's just，do that，basically with probability epsilon。



![](img/f4b93c38cb2648887cbd799201d326a5_264.png)

you're replacing the，ground truth with something random and u。



![](img/f4b93c38cb2648887cbd799201d326a5_266.png)

is uniform，it's a uniform distribution so equally，probably you're gonna associate a random。



![](img/f4b93c38cb2648887cbd799201d326a5_268.png)

label to your data your input image，so let's just do that let's take q prime。



![](img/f4b93c38cb2648887cbd799201d326a5_270.png)

and put it here in place of q，this is called label smoothing it's sort，of regularizing。

your neural network but the，regularization is happening at the end。

at the last layer of your neural network，so we know how to regularize the other，layers。

sometimes we are using dropouts，sometimes we are using batch，normalization。

this is the last layer that you're，regularizing it，so if you take q prime and put it。

here in place of，q you have one minus epsilon，q so that's gonna give you 1 minus，epsilon。

h of q and p and h，we know that's the definition plus，epsilon h of u and p。

so sometimes it's q sometimes it's u，with epsilon，being a small number now let's use the。

definition of，h u and p h u m p，the cross entropy is just the kl，divergence。

of the uniform distribution and the，underlying，probability basically the probability，that the model。

predicts plus h of u，but let's look at this objective，function what are we minimizing。

with respect to can anybody answer，we are minimizing this loss with respect，to what。

the parameters of your neural network，and the parameters of the neural network。

are affecting what term here is it，affecting q or is it affecting p so it's，affecting p。

so you are minimizing this loss with，respect to p，correct yes that's correct so you're。

doing it with respect to p，now your objective function if you are，minimizing with respect to p。

this term depends on p this term doesn't，depend on p，it means that its derivatives are zero。

with respect to p，it means that this term doesn't have any，effect on your loss function。

so we can simply drop that and as i said，u is a uniform distribution。

so what you're doing is just trying to，regularize p to move towards the。

uniform distribution it means that，you're trying to avoid，some of your z k's to be going towards。

infinity and the other one's going，towards zero，so you're trying to push everything，towards normal。

but you don't do it aggressively you do，it for a very small epsilon。

so that's how you're regularizing and kl，divergence is just，measuring the distance between two。

distributions，so you're trying to minimize the，distance between two distributions。

so that's another change that the paper，makes，and then they are going to report some。

very good results in their paper，any questions and h is just the entropy，h of u is just h of u and u。

so we learned about a lot of concepts，one is how cross-entropy what is the。

definition of cross-entropy，that's the definition how is it related，to。

likelihood that's how it's related under，this assumption，and how we're gonna do label smoothing。

and what's the definition of kl，basically kl you can define it to be h，of u and p。

minus h of u and h of u is just，h of u and u so everything is consistent，is everything clear。

and any questions regularization is very，important，in round networks and we saw that all。

over the place，starting from alex net paper up until，even this one。

so from the beginning of your neural，network until the end you're doing，regularization。

okay if there are no questions so the，structure is clear yes，sometimes you're making some。

contributions，on the neural network，construction side of things sometimes，you're doing。

contributions if you write a paper on，the loss。