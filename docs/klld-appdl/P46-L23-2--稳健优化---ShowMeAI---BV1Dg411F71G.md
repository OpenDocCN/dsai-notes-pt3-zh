# P46：L23.2- 稳健优化 - ShowMeAI - BV1Dg411F71G

![](img/1a2c161f894ff873025f9fd8f18df314_0.png)

so we all know whether the applications。

![](img/1a2c161f894ff873025f9fd8f18df314_2.png)

the applications are in autonomous cars，autonomous vehicles，face recognition malware detection the。



![](img/1a2c161f894ff873025f9fd8f18df314_4.png)

one for malware detection is really，interesting。

![](img/1a2c161f894ff873025f9fd8f18df314_6.png)

you are making your malware detection，system，to make a mistake and that's dangerous。



![](img/1a2c161f894ff873025f9fd8f18df314_8.png)

is that defeating the entire purpose of，coming up with an algorithm，to detect malwares or to detect。

anomalies，for instance you can have a camera in，smart cities。



![](img/1a2c161f894ff873025f9fd8f18df314_10.png)

you can have a camera that is monitoring，the traffic。



![](img/1a2c161f894ff873025f9fd8f18df314_12.png)

and you want to have an algorithm that，is，capable of detecting anomalies for，instance a car is。

driving on the other side of the road。

![](img/1a2c161f894ff873025f9fd8f18df314_14.png)

because the driver is drunk，and imagine you have an algorithm that's，going to make a mistake there。



![](img/1a2c161f894ff873025f9fd8f18df314_16.png)

or you have an adversarial attack to，that type of an algorithm。



![](img/1a2c161f894ff873025f9fd8f18df314_18.png)

okay let's now go into the details of，the，math behind this paper you have your。



![](img/1a2c161f894ff873025f9fd8f18df314_20.png)

data distribution，and a little bit of notation you have，your examples。



![](img/1a2c161f894ff873025f9fd8f18df314_22.png)

that are coming from your data，distribution and you have your labels。



![](img/1a2c161f894ff873025f9fd8f18df314_24.png)

and let's say you have k labels or 1，1000 labels，you usually have a loss function which。



![](img/1a2c161f894ff873025f9fd8f18df314_26.png)

is a function of，the parameters of your model and the，ground truth。



![](img/1a2c161f894ff873025f9fd8f18df314_28.png)

the examples and the corresponding，labels and we usually minimize the。



![](img/1a2c161f894ff873025f9fd8f18df314_30.png)

empirical risk which is basically。

![](img/1a2c161f894ff873025f9fd8f18df314_32.png)

data，and we know it by now that the objective，of coming away that were several，examples。



![](img/1a2c161f894ff873025f9fd8f18df314_34.png)

is that you take an example x it belongs，to class c one。



![](img/1a2c161f894ff873025f9fd8f18df314_36.png)

this is your input you want to find an，adversarial example。



![](img/1a2c161f894ff873025f9fd8f18df314_38.png)

that is close to x in some norm but then，you want your，adversarial example to be incorrectly。

classified。

![](img/1a2c161f894ff873025f9fd8f18df314_40.png)

as c2 rather than c1 so i went through，this because i wanted to introduce。

what is c1 what is c2 and what is x adv，and what is our x but we know what is。



![](img/1a2c161f894ff873025f9fd8f18df314_42.png)

the objective we saw it before。

![](img/1a2c161f894ff873025f9fd8f18df314_44.png)

where，this is your objective rather than，minimizing the empirical risk。



![](img/1a2c161f894ff873025f9fd8f18df314_46.png)

you add a perturbation to your input you，say x plus delta。



![](img/1a2c161f894ff873025f9fd8f18df314_48.png)

now you have a delta in your loss，function and you want to do something，with it。



![](img/1a2c161f894ff873025f9fd8f18df314_50.png)

loss，so this is acting as an adversary you。

![](img/1a2c161f894ff873025f9fd8f18df314_52.png)

want to find，delta in a set of acceptable。

![](img/1a2c161f894ff873025f9fd8f18df314_54.png)

perturbations for instance these，perturbations should be small，and at the same time you want to。



![](img/1a2c161f894ff873025f9fd8f18df314_56.png)

maximize your loss that's the objective，of the adversary。



![](img/1a2c161f894ff873025f9fd8f18df314_58.png)

and the objective of the algorithm is，in general is to try to minimize the。



![](img/1a2c161f894ff873025f9fd8f18df314_60.png)

parameters of our model and what is，s s is a set of acceptable perturbations。



![](img/1a2c161f894ff873025f9fd8f18df314_62.png)

for instance we want them to have a，maximum l infinity norm of epsilon。



![](img/1a2c161f894ff873025f9fd8f18df314_64.png)

that's an example so rather than，minimizing，that objective function now we are。



![](img/1a2c161f894ff873025f9fd8f18df314_66.png)

trying to minimize，an objective function that is trying to，be robust。



![](img/1a2c161f894ff873025f9fd8f18df314_68.png)

at the same time and there is a huge，literature on robust optimization。

so this is the first paper that is。

![](img/1a2c161f894ff873025f9fd8f18df314_70.png)

trying to relate，adversarial attacks or find the。

![](img/1a2c161f894ff873025f9fd8f18df314_72.png)

relationship between adversarial attacks，and robust optimization so the。

robustness here comes because we're。

![](img/1a2c161f894ff873025f9fd8f18df314_74.png)

looking at the，one worst case we're looking for the。



![](img/1a2c161f894ff873025f9fd8f18df314_76.png)

maximum over delta so it's，it's going to highlight the like the。

worst case scenario whereas before with。

![](img/1a2c161f894ff873025f9fd8f18df314_78.png)

empirical risk，get。

![](img/1a2c161f894ff873025f9fd8f18df314_80.png)

get average down so exactly so here you，don't have any worst case scenario。



![](img/1a2c161f894ff873025f9fd8f18df314_82.png)

because these are your actual data set，here you're sort of。



![](img/1a2c161f894ff873025f9fd8f18df314_84.png)

augmenting your data we saw this also，in this second paper of this series that，we covered。



![](img/1a2c161f894ff873025f9fd8f18df314_86.png)

with fast gradient sine method with fast，gradient sine method we were coming up。



![](img/1a2c161f894ff873025f9fd8f18df314_88.png)

with new adversarial examples，and we were then adding that to our。



![](img/1a2c161f894ff873025f9fd8f18df314_90.png)

dataset we were augmenting the data，now you can do a similar thing here you，can have it。



![](img/1a2c161f894ff873025f9fd8f18df314_92.png)

you can add a perturbation to your input，try to maximize your loss。



![](img/1a2c161f894ff873025f9fd8f18df314_94.png)

that's going to be the worst scenario，and then，try to minimize the worst case scenario。

and this way you hope that your。

![](img/1a2c161f894ff873025f9fd8f18df314_96.png)

algorithm is going to be robust，and is it the case that every single，data point。



![](img/1a2c161f894ff873025f9fd8f18df314_98.png)

x gets its own worst case perturbation，delta that。

![](img/1a2c161f894ff873025f9fd8f18df314_100.png)

when we're considering this yes exactly，okay thank you，so delta is x dependent so we came up。



![](img/1a2c161f894ff873025f9fd8f18df314_102.png)

with fast gradient sine method，we covered it for fast gradient sine，method we had。



![](img/1a2c161f894ff873025f9fd8f18df314_104.png)

l infinity and where is l infinity，coming into place。



![](img/1a2c161f894ff873025f9fd8f18df314_106.png)

now coming into the picture it's coming，into the picture，when you're defining your s you want。



![](img/1a2c161f894ff873025f9fd8f18df314_108.png)

your delta，to have a particular l infinity norm。

![](img/1a2c161f894ff873025f9fd8f18df314_110.png)

or an l infinity norm of less than or，equal to a threshold。



![](img/1a2c161f894ff873025f9fd8f18df314_112.png)

that，if you try to maximize this objective。

![](img/1a2c161f894ff873025f9fd8f18df314_114.png)

function with respect to delta，you can take a gradient step you can say。



![](img/1a2c161f894ff873025f9fd8f18df314_116.png)

x plus delta forget about the sign now，the gradient of your loss is gradient，ascent now。



![](img/1a2c161f894ff873025f9fd8f18df314_118.png)

so you're taking the step in the，direction of the gradient of your loss，function。



![](img/1a2c161f894ff873025f9fd8f18df314_120.png)

to maximize whatever whatever that's，inside that。

![](img/1a2c161f894ff873025f9fd8f18df314_122.png)

objective function but then you need the，sign because you want your perturbation。



![](img/1a2c161f894ff873025f9fd8f18df314_124.png)

to be inside your s to be，an acceptable perturbation because if。



![](img/1a2c161f894ff873025f9fd8f18df314_126.png)

you have a constraint it's a constrained，optimization，you take the gradient you compute the。



![](img/1a2c161f894ff873025f9fd8f18df314_128.png)

sign you add epsilon and that's going to，give you x，so it means that fast gradient sine，method is。



![](img/1a2c161f894ff873025f9fd8f18df314_130.png)

problem，and this is how the algorithm is going。

![](img/1a2c161f894ff873025f9fd8f18df314_132.png)

to work a batch of，inputs x is going to go in and let's say。



![](img/1a2c161f894ff873025f9fd8f18df314_134.png)

your batch size is 1 for now，so an input goes inside your algorithm，you compute your loss。



![](img/1a2c161f894ff873025f9fd8f18df314_136.png)

and then you try to maximize with，respect to delta you can maximize it to，the end。



![](img/1a2c161f894ff873025f9fd8f18df314_138.png)

do i don't know thousands of iterations，maximize it to the end and then。



![](img/1a2c161f894ff873025f9fd8f18df314_140.png)

plug that delta inside your objective，and then。

![](img/1a2c161f894ff873025f9fd8f18df314_142.png)

compute the empirical risk or you can，just take one step，trying to maximize this objective and。



![](img/1a2c161f894ff873025f9fd8f18df314_144.png)

doing，so is this clear the idea is that fast。

![](img/1a2c161f894ff873025f9fd8f18df314_146.png)

or the message is that fast gradient，sign method，is a special case of finding trying to。



![](img/1a2c161f894ff873025f9fd8f18df314_148.png)

solve the satellite problem is this，clear，that's clear okay perfect you can。



![](img/1a2c161f894ff873025f9fd8f18df314_150.png)

actually try to，solve that saddle point problem by，taking multiple steps。



![](img/1a2c161f894ff873025f9fd8f18df314_152.png)

of gradient descent or actually gradient，essence because you want to maximize，that loss。



![](img/1a2c161f894ff873025f9fd8f18df314_154.png)

but it's going to be gradient ascent it，has to be projected because。



![](img/1a2c161f894ff873025f9fd8f18df314_156.png)

we need to project into this space you，take a step but then you have to project。



![](img/1a2c161f894ff873025f9fd8f18df314_158.png)

it and so when we say that projected we，just mean that we're taking the sign。

and just multiplying by an epsilon。

![](img/1a2c161f894ff873025f9fd8f18df314_160.png)

that's within，the space we're talking about here this，s yes。



![](img/1a2c161f894ff873025f9fd8f18df314_162.png)

for fast gradient sine method yes that's，enough okay，but when you take multiple steps now you。



![](img/1a2c161f894ff873025f9fd8f18df314_164.png)

are taking multiple steps。

![](img/1a2c161f894ff873025f9fd8f18df314_166.png)

take xd plus one uh as a function of xt，so you're doing multiple steps of。



![](img/1a2c161f894ff873025f9fd8f18df314_168.png)

gradient ascent，okay but then at each time we're at each，step of your optimizer。



![](img/1a2c161f894ff873025f9fd8f18df314_170.png)

you need to project it into your space，you want to be near。



![](img/1a2c161f894ff873025f9fd8f18df314_172.png)

x and basically you want your delta to，be inside this。



![](img/1a2c161f894ff873025f9fd8f18df314_174.png)

space of acceptable perturbations，depending on the。



![](img/1a2c161f894ff873025f9fd8f18df314_176.png)

norm that you choose so that's the idea，rather than taking one。

step you can take multiple steps that pi，is a projection operator。



![](img/1a2c161f894ff873025f9fd8f18df314_178.png)

and what's the what's the x plus x，notation form x plus s。



![](img/1a2c161f894ff873025f9fd8f18df314_180.png)

is just a set it's going to be x plus。

![](img/1a2c161f894ff873025f9fd8f18df314_182.png)

delta for all delta in s okay，so it's perturbations that are close to。



![](img/1a2c161f894ff873025f9fd8f18df314_184.png)

x yeah that was a great question，so x plus s is x plus all of the deltas。



![](img/1a2c161f894ff873025f9fd8f18df314_186.png)

where delta is in s so what's the，intuition。

![](img/1a2c161f894ff873025f9fd8f18df314_188.png)

for saddle point problem let's say your，norm is an infinity norm。



![](img/1a2c161f894ff873025f9fd8f18df314_190.png)

and you try to minimize your empirical，risk and that's what you're gonna get。

and usually you're gonna end up with a。

![](img/1a2c161f894ff873025f9fd8f18df314_192.png)

couple of hard examples，like these stars and that star once you，introduce。



![](img/1a2c161f894ff873025f9fd8f18df314_194.png)

a box because now we are doing l，infinity。

![](img/1a2c161f894ff873025f9fd8f18df314_196.png)

and x plus uh s is basically this box，that you're seeing。



![](img/1a2c161f894ff873025f9fd8f18df314_198.png)

you have x plus delta and that's going，to give you the box。



![](img/1a2c161f894ff873025f9fd8f18df314_200.png)

now we are making the life of our，classifier a little bit harder it rather。



![](img/1a2c161f894ff873025f9fd8f18df314_202.png)

than finding a simple line，it has to try to find a curve trying to，respect。



![](img/1a2c161f894ff873025f9fd8f18df314_204.png)

those boundaries i think i'm one minute，over time，for those of you who have questions you。



![](img/1a2c161f894ff873025f9fd8f18df314_206.png)

are more than welcome to stay and ask，and for those of you want to leave you。

can leave so that's a great。

![](img/1a2c161f894ff873025f9fd8f18df314_208.png)

question wouldn't that line over fit the，data actually you're gonna have。



![](img/1a2c161f894ff873025f9fd8f18df314_210.png)

more data now anything，that's within these boxes is gonna be。



![](img/1a2c161f894ff873025f9fd8f18df314_212.png)

data and these are，augmented data by perturbation can i ask。



![](img/1a2c161f894ff873025f9fd8f18df314_214.png)

a，slightly unrelated question um i。

![](img/1a2c161f894ff873025f9fd8f18df314_216.png)

uh i was looking at uh this week um，this thing called stochastic forward。



![](img/1a2c161f894ff873025f9fd8f18df314_218.png)

passes，which are just essentially like leaving，dropout on。



![](img/1a2c161f894ff873025f9fd8f18df314_220.png)

during inference to get uh and then you，produce like a distribution of。



![](img/1a2c161f894ff873025f9fd8f18df314_222.png)

uh predictions instead of a single，prediction um。

![](img/1a2c161f894ff873025f9fd8f18df314_224.png)

i'm curious if something like that could，be used，to protect against adversarial attacks。



![](img/1a2c161f894ff873025f9fd8f18df314_226.png)

where instead of just，taking one taking your one prediction。



![](img/1a2c161f894ff873025f9fd8f18df314_228.png)

you sort of produce a distribution of，predictions that may be。

given that these like adversarial images。

![](img/1a2c161f894ff873025f9fd8f18df314_230.png)

are so close to，uh like they're hardly they're。

![](img/1a2c161f894ff873025f9fd8f18df314_232.png)

indistinguishable to the human eye，it seems like that might be effective uh。

i think that's a good idea。

![](img/1a2c161f894ff873025f9fd8f18df314_234.png)

you can actually try it and see whether，drop out is going to help with average。



![](img/1a2c161f894ff873025f9fd8f18df314_236.png)

examples，is this actually a defense mechanism but，you haven't heard of it。



![](img/1a2c161f894ff873025f9fd8f18df314_238.png)

being being used i don't think so。

![](img/1a2c161f894ff873025f9fd8f18df314_240.png)

okay interesting the best of my，knowledge i don't know okay，thanks so much did that answer your。

question。

![](img/1a2c161f894ff873025f9fd8f18df314_242.png)

yeah but it still seems that depending，on your training data。



![](img/1a2c161f894ff873025f9fd8f18df314_244.png)

uh even if you're perturbing and，augmenting you may，actually miss some test cases you know。



![](img/1a2c161f894ff873025f9fd8f18df314_246.png)

if you have some test cases close to the，boundary，yes that's going to happen regardless。



![](img/1a2c161f894ff873025f9fd8f18df314_248.png)

but this is not an overfit。

![](img/1a2c161f894ff873025f9fd8f18df314_250.png)

because your true data are still these，the circles these are just augmented。



![](img/1a2c161f894ff873025f9fd8f18df314_252.png)

data and your algorithm has to respect，that behavior，after doing the saddle point。



![](img/1a2c161f894ff873025f9fd8f18df314_254.png)