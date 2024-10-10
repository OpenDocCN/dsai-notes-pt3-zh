# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P47：L24.1- 稳健优化 [续] - ShowMeAI - BV1Dg411F71G

let's get started uh let's see an，overview of where we are，we started with this paper intriguing。

properties of neural networks，and we saw that networks have some，have some blind spots。

but then to find those blunt spots and，adversarial examples，we needed to solve an optimization，said。

i'm looking for a cheaper way of，generating adversarial examples。

and it came up with the idea of gradient，sine methods，or fast gradient sine method and now。

that you have a fast method of creating，adversarial examples you can add those。

examples to your training set，or you can modify your objective，function this way that's equivalent。

so the first one was an attack the，second one is trying to mitigate the，attack。

then there were a couple of papers，claiming that，defensive distillation or actually。

distillation is a good way，to defend against adversarial examples。

this paper came along and said if i，change the objective function to，for。

finding adverse early examples to，something else then，even defensive distillation is not going，to do。

any good then we started this paper last。

![](img/04b757b540d612311280a9bf6e43b33b_1.png)

session，and this is an extension to fast，gradient sine method。



![](img/04b757b540d612311280a9bf6e43b33b_3.png)

for fast gradient sine method we are，apparently taking a step。



![](img/04b757b540d612311280a9bf6e43b33b_5.png)

in the direction of gradients gradients，of your objective function with respect，to input。

that was the observation that this paper，started with。



![](img/04b757b540d612311280a9bf6e43b33b_7.png)

and if that's the case it seems like you，are optimizing an objective。

and then we introduce a couple of，notations our last。



![](img/04b757b540d612311280a9bf6e43b33b_9.png)

function the empirical risk and then we，said。

![](img/04b757b540d612311280a9bf6e43b33b_11.png)

okay now that fast gradient sine method，is taking a step in the direction of。



![](img/04b757b540d612311280a9bf6e43b33b_13.png)

a gradient of our loss function maybe we，are actually optimizing something。



![](img/04b757b540d612311280a9bf6e43b33b_15.png)

and maybe this should be our，optimization function maybe we have a，saddle point problem。



![](img/04b757b540d612311280a9bf6e43b33b_17.png)

where the adversarial examples are being，generated。



![](img/04b757b540d612311280a9bf6e43b33b_19.png)

by maximizing our loss function with，respect to，a perturbation and this perturbation has，to be。



![](img/04b757b540d612311280a9bf6e43b33b_21.png)

in a set of allowable perturbations。

![](img/04b757b540d612311280a9bf6e43b33b_23.png)

norm，then these perturbations need to be，small enough in。



![](img/04b757b540d612311280a9bf6e43b33b_25.png)

a infinity norm or in l2 nor or in l1 or。

![](img/04b757b540d612311280a9bf6e43b33b_27.png)

etc and then we saw that yes indeed fast，gradient sine method，is trying to take a step in the。



![](img/04b757b540d612311280a9bf6e43b33b_29.png)

direction of maximizing，this loss function and our s for that。



![](img/04b757b540d612311280a9bf6e43b33b_31.png)

particular，method is defined by l infinity。

![](img/04b757b540d612311280a9bf6e43b33b_33.png)

it's going to define the boxes around，our observations，so the idea of this paper is that you。



![](img/04b757b540d612311280a9bf6e43b33b_35.png)

can have multiple iterations。

![](img/04b757b540d612311280a9bf6e43b33b_37.png)

of gradient ascent it is gradient ascent，because we want to maximize our loss。



![](img/04b757b540d612311280a9bf6e43b33b_39.png)

but then we have to project it for us to，respect，this uh condition because it's a。



![](img/04b757b540d612311280a9bf6e43b33b_41.png)

constraint optimization problem we don't，want our，perturbations to become too big so。

rather than taking。

![](img/04b757b540d612311280a9bf6e43b33b_43.png)

one step we are taking multiple steps，and after each step we are。



![](img/04b757b540d612311280a9bf6e43b33b_45.png)

x。

![](img/04b757b540d612311280a9bf6e43b33b_47.png)

of our original data point and this was，trying to give us an intuition of。

what is actually happening in practice。

![](img/04b757b540d612311280a9bf6e43b33b_49.png)

so this figure is just to give us an，intuition and the idea is that you're。



![](img/04b757b540d612311280a9bf6e43b33b_51.png)

adding，more data and you're basically，augmenting your data set。



![](img/04b757b540d612311280a9bf6e43b33b_53.png)

and now that you have more data set a，much bigger data set。



![](img/04b757b540d612311280a9bf6e43b33b_55.png)

you're gonna have to come up your，algorithm has to come up with a。



![](img/04b757b540d612311280a9bf6e43b33b_57.png)

more complicated decision boundary，for it to respect and be robust to。



![](img/04b757b540d612311280a9bf6e43b33b_59.png)

perturbations of your data points，so now if you take this data point and，perturb it a little bit。



![](img/04b757b540d612311280a9bf6e43b33b_61.png)

that decision boundary is going to，respect it if you take a data point here。



![](img/04b757b540d612311280a9bf6e43b33b_63.png)

for instance this is star，this red decision boundary is gonna，respect and it's gonna classify that。

correctly。

![](img/04b757b540d612311280a9bf6e43b33b_65.png)

fail。

![](img/04b757b540d612311280a9bf6e43b33b_67.png)

and this is going to be an adversarial，example to this classifier so let's see，some results。



![](img/04b757b540d612311280a9bf6e43b33b_69.png)

these results are a little bit different，to what you're used to。



![](img/04b757b540d612311280a9bf6e43b33b_71.png)

now you have a network that is uh，trained using projected gradient asset。



![](img/04b757b540d612311280a9bf6e43b33b_73.png)

so it's it is adversarially trained and，basically we are using this objective，function。



![](img/04b757b540d612311280a9bf6e43b33b_75.png)

attack，is more effective against a network，trained this way so our network is。

already trying to be robust。

![](img/04b757b540d612311280a9bf6e43b33b_77.png)

because we are solving this objective，function rather than the empirical risk。



![](img/04b757b540d612311280a9bf6e43b33b_79.png)

so our network is already including，these boxes，around the data and now we want to。



![](img/04b757b540d612311280a9bf6e43b33b_81.png)

attack it using different methods，you take natural images and ask the。



![](img/04b757b540d612311280a9bf6e43b33b_83.png)

adversarially trained network，to classify it it's going to give you。



![](img/04b757b540d612311280a9bf6e43b33b_85.png)

98。8 percent accuracy so this we，there is no surprise because uh。



![](img/04b757b540d612311280a9bf6e43b33b_87.png)

if you take a natural image it's already，one of these。



![](img/04b757b540d612311280a9bf6e43b33b_89.png)

images in the box it's actually this，blue dot，and we're comparing it against this。



![](img/04b757b540d612311280a9bf6e43b33b_91.png)

decision boundary the more complicated，one and it's giving us 98。8 percent。



![](img/04b757b540d612311280a9bf6e43b33b_93.png)

accuracy，so these are real images natural images。

![](img/04b757b540d612311280a9bf6e43b33b_95.png)

now you can take your images，and attack them using fast gradient sine，method。



![](img/04b757b540d612311280a9bf6e43b33b_97.png)

so for each image you're going to have，an adversarial，example you take that example and ask。



![](img/04b757b540d612311280a9bf6e43b33b_99.png)

the robust，the robustly trained network。

![](img/04b757b540d612311280a9bf6e43b33b_101.png)

to classify it and yes the accuracy is，going to drop but it's not that bad。



![](img/04b757b540d612311280a9bf6e43b33b_103.png)

if you do projected gradient ascent to，attack this network，it's going to be 93。2 percent accurate。

so this network is robust。

![](img/04b757b540d612311280a9bf6e43b33b_105.png)

that's the idea the accuracy is still，high if you do。



![](img/04b757b540d612311280a9bf6e43b33b_107.png)

more rounds of iteration basically take，more steps of your projected gradient，ascent。



![](img/04b757b540d612311280a9bf6e43b33b_109.png)

to come up with an example the accuracy，is going to drop a little bit but。



![](img/04b757b540d612311280a9bf6e43b33b_111.png)

still the network is robust and you can，do pgd with multiple restarts。



![](img/04b757b540d612311280a9bf6e43b33b_113.png)

so each time you're gonna have a random。

![](img/04b757b540d612311280a9bf6e43b33b_115.png)

restart to your initial perturbation and，as you can see these are。

becoming more costly natural images。

![](img/04b757b540d612311280a9bf6e43b33b_117.png)

there is no cost，cost to it to come up with adversarial，example you just feed in your natural。



![](img/04b757b540d612311280a9bf6e43b33b_119.png)

images，fast gradient sign method is really，cheap。

![](img/04b757b540d612311280a9bf6e43b33b_121.png)

this one is more expensive because you，have to take 40 steps this one is even。

more expensive and this one has restarts。

![](img/04b757b540d612311280a9bf6e43b33b_123.png)

for it to become a more effective attack，against this network。



![](img/04b757b540d612311280a9bf6e43b33b_125.png)

and what does this a mean a means uh，you're doing a whitebox attack it means。



![](img/04b757b540d612311280a9bf6e43b33b_127.png)

that you have，access to your network to the parameters。



![](img/04b757b540d612311280a9bf6e43b33b_129.png)

of the network to the hyper parameters，to the structure of the network so these。

are wi-fi white box attacks。

![](img/04b757b540d612311280a9bf6e43b33b_131.png)

you can have a targeted attack and the，most effective attack。



![](img/04b757b540d612311280a9bf6e43b33b_133.png)

in this result seems to be pgd，with 100 steps and 20 restarts，when you have access to the network。

itself and cw。

![](img/04b757b540d612311280a9bf6e43b33b_135.png)

is the attack from the previous paper，let's see yeah it's called cw because of。

the name of the authors，it's carlini and wagner so it's cw，it's this paper now let's go to the next。

part of these results。

![](img/04b757b540d612311280a9bf6e43b33b_137.png)

and try to interpret them a prime means。

![](img/04b757b540d612311280a9bf6e43b33b_139.png)

you have a black box attack what does it，mean。

![](img/04b757b540d612311280a9bf6e43b33b_141.png)

you have an independently trained copy，of the network and you train it。

independently you have a copy of the。

![](img/04b757b540d612311280a9bf6e43b33b_143.png)

network you train it independently，and what does b mean b is a different。



![](img/04b757b540d612311280a9bf6e43b33b_145.png)

architecture it's a totally different，architecture you use a totally different，architecture。



![](img/04b757b540d612311280a9bf6e43b33b_147.png)

to come up with attacks to come up with，perturbations of the images，so for a prime everything that。



![](img/04b757b540d612311280a9bf6e43b33b_149.png)

you see here is a black box attack and，the most effective。



![](img/04b757b540d612311280a9bf6e43b33b_151.png)

one is the steel pgd and we know that，our network is being trained。

using projected gradient ascent can i。

![](img/04b757b540d612311280a9bf6e43b33b_153.png)

ask a quick clarifying question，sure um so in this second。



![](img/04b757b540d612311280a9bf6e43b33b_155.png)

set of uh results here are the，adversarial。

![](img/04b757b540d612311280a9bf6e43b33b_157.png)

attacks being developed on the original，network，or are they being developed on this。

independently trained network。

![](img/04b757b540d612311280a9bf6e43b33b_159.png)

so they are being generated using the，independently trained network it's a。

copy of the original network。

![](img/04b757b540d612311280a9bf6e43b33b_161.png)

you don't have access to the original，network but you know that the network。



![](img/04b757b540d612311280a9bf6e43b33b_163.png)

is i don't know a google net that is，this many。

![](img/04b757b540d612311280a9bf6e43b33b_165.png)

that has this many layers and it's this，that much wide et cetera so you know the，details。



![](img/04b757b540d612311280a9bf6e43b33b_167.png)

you make a copy and you train it，yourself but if you're training the，adversarial。

i like if you're coming up with the。

![](img/04b757b540d612311280a9bf6e43b33b_169.png)

adversarial examples，on the independently trained network and。



![](img/04b757b540d612311280a9bf6e43b33b_171.png)

then attacking the independently trained，network with those adversarial examples。

shouldn't you be getting the same。

![](img/04b757b540d612311280a9bf6e43b33b_173.png)

accuracy as with，the the other set of examples where we。



![](img/04b757b540d612311280a9bf6e43b33b_175.png)

trained it no you come up with，adversarial examples，using the copy of the network but then。



![](img/04b757b540d612311280a9bf6e43b33b_177.png)

you're attacking the，target network oh okay the original one，okay。



![](img/04b757b540d612311280a9bf6e43b33b_179.png)

yes okay that makes sense thanks and so，when you say it's a copy。



![](img/04b757b540d612311280a9bf6e43b33b_181.png)

does that mean they're the exact same，structure but just trained。

sort of independently yes exactly okay。

![](img/04b757b540d612311280a9bf6e43b33b_183.png)

the exact same structure trained，independent，and i believe the data set is the same。



![](img/04b757b540d612311280a9bf6e43b33b_185.png)

day but also so that's just showing that，the slight sort of non deterministic。



![](img/04b757b540d612311280a9bf6e43b33b_187.png)

sort of structure of training doesn't，affect it as much。



![](img/04b757b540d612311280a9bf6e43b33b_189.png)

yes so in the best case scenario，if you are an adversary you want to have。



![](img/04b757b540d612311280a9bf6e43b33b_191.png)

access to the network，itself because then you're going to come，up with the most effective。



![](img/04b757b540d612311280a9bf6e43b33b_193.png)

attacks that's going to be a white box，attack for a black box attack you don't。

have access to the network but you know。

![](img/04b757b540d612311280a9bf6e43b33b_195.png)

what network，that particular company is using in，their production。



![](img/04b757b540d612311280a9bf6e43b33b_197.png)

you create your adversarial examples，using this network。



![](img/04b757b540d612311280a9bf6e43b33b_199.png)

and use that to classify to attack your，original network，does that make sense yeah and b is the。

case that yes it's a black box attack，you actually don't have any information。



![](img/04b757b540d612311280a9bf6e43b33b_201.png)

about the architecture，that they are using wouldn't you expect，that with。



![](img/04b757b540d612311280a9bf6e43b33b_203.png)

uh using b the sort of，degradation of accuracy should be much。



![](img/04b757b540d612311280a9bf6e43b33b_205.png)

lower but it's actually better than，a prime like how are they able to use。



![](img/04b757b540d612311280a9bf6e43b33b_207.png)

a totally different architecture but，then get a。

![](img/04b757b540d612311280a9bf6e43b33b_209.png)

better success rate in being adversarial。

![](img/04b757b540d612311280a9bf6e43b33b_211.png)

see this fgsm here is having 95。6。

![](img/04b757b540d612311280a9bf6e43b33b_213.png)

accuracy and this fgsm attack，is having 96 the pgd let's compare apple，to apples。



![](img/04b757b540d612311280a9bf6e43b33b_215.png)

for a prime this one is more successful，it's nothing more successful it's。



![](img/04b757b540d612311280a9bf6e43b33b_217.png)

rate，but these are actually less successful，at it at。



![](img/04b757b540d612311280a9bf6e43b33b_219.png)

attacking this network let's look at，this pgd。

![](img/04b757b540d612311280a9bf6e43b33b_221.png)

and there is another one here i guess，you can compare this to that。



![](img/04b757b540d612311280a9bf6e43b33b_223.png)

this is 89。3 this is 95。7，so it's actually these numbers are。



![](img/04b757b540d612311280a9bf6e43b33b_225.png)

higher it means that the attacks，are a black box attack is less。



![](img/04b757b540d612311280a9bf6e43b33b_227.png)

effective because then you need to look，was。

![](img/04b757b540d612311280a9bf6e43b33b_229.png)

more effective at lowering the accuracy，and the black box attack is less。



![](img/04b757b540d612311280a9bf6e43b33b_231.png)

effective so i think it should be more，clear now，yes so i don't see any contradictions so。



![](img/04b757b540d612311280a9bf6e43b33b_233.png)

does this make sense，same thing is for cw there's cw here cw。



![](img/04b757b540d612311280a9bf6e43b33b_235.png)

here you can compare apple to apples。

![](img/04b757b540d612311280a9bf6e43b33b_237.png)

this is 97 this is 94。 so a white box，attack is more effective if you have，access to the。



![](img/04b757b540d612311280a9bf6e43b33b_239.png)

original network you are going to come，up with better。



![](img/04b757b540d612311280a9bf6e43b33b_241.png)

adversarial examples more effective and，it's going to drop the accuracy more。

compared to when you don't have access。

![](img/04b757b540d612311280a9bf6e43b33b_243.png)

to it so to be fully transparent，prime。

![](img/04b757b540d612311280a9bf6e43b33b_245.png)

we don't have access to a we generate，examples。

![](img/04b757b540d612311280a9bf6e43b33b_247.png)

using a prime and we are attacking a so，you generate the example using b。

and you attack a so are we all on the。

![](img/04b757b540d612311280a9bf6e43b33b_249.png)

same page yes this table is a，slightly different compared to what we。



![](img/04b757b540d612311280a9bf6e43b33b_251.png)

are used to，because we usually attack networks and，we want。



![](img/04b757b540d612311280a9bf6e43b33b_253.png)

and the network is never trained to be，robust，now these networks are trained to be。



![](img/04b757b540d612311280a9bf6e43b33b_255.png)

robust and we are still attacking them，and same thing for here this number is。



![](img/04b757b540d612311280a9bf6e43b33b_257.png)

lower than this number，i guess uh let's look at pgd。



![](img/04b757b540d612311280a9bf6e43b33b_259.png)

4d1 b pgd41。

![](img/04b757b540d612311280a9bf6e43b33b_261.png)

a prime so this one makes sense so we，are being less effective。



![](img/04b757b540d612311280a9bf6e43b33b_263.png)

cw plus i think they don't have any，steps，probably you cannot compare these two。



![](img/04b757b540d612311280a9bf6e43b33b_265.png)

together fgsm is a little bit，out of the pattern but it's just an。



![](img/04b757b540d612311280a9bf6e43b33b_267.png)

example this is this could be，just an outlier the way the networks are。

being trained but it turns out that。

![](img/04b757b540d612311280a9bf6e43b33b_269.png)

among these methods fgsm is the most，effective one。



![](img/04b757b540d612311280a9bf6e43b33b_271.png)

at attacking our network that is trying，to be robust，when you don't have access to the。



![](img/04b757b540d612311280a9bf6e43b33b_273.png)

network and it's a black box attack，and you're using a totally different，architecture how do you get。



![](img/04b757b540d612311280a9bf6e43b33b_275.png)

a。

![](img/04b757b540d612311280a9bf6e43b33b_277.png)

so you just use the gradients of b yes，you use the，gradients of b yeah i'm still i feel，like it。



![](img/04b757b540d612311280a9bf6e43b33b_279.png)

seems like that would work less well um，but for some reason it works better i'm。



![](img/04b757b540d612311280a9bf6e43b33b_281.png)

still a little not fully understanding，why that is。



![](img/04b757b540d612311280a9bf6e43b33b_283.png)

this one is an outlier so i wouldn't，count too much on this，okay the rest of the pattern is clear。

well it could be that the any the a and，the a-prime。



![](img/04b757b540d612311280a9bf6e43b33b_285.png)

architecture are designed with this，diagram on the left where you're。



![](img/04b757b540d612311280a9bf6e43b33b_287.png)

including a region in a box around every，single example and so you're。



![](img/04b757b540d612311280a9bf6e43b33b_289.png)

training the network to recognize images，and also their neighborhoods and if b，was a。



![](img/04b757b540d612311280a9bf6e43b33b_291.png)

network which didn't train that way，where you were just。



![](img/04b757b540d612311280a9bf6e43b33b_293.png)

finding a boundary right in between，examples and not necessarily including，their neighborhoods then。



![](img/04b757b540d612311280a9bf6e43b33b_295.png)

any kind of attack could be more，effective because，uh they're just they're not built to be。



![](img/04b757b540d612311280a9bf6e43b33b_297.png)

robust to attack but we're，i thought we were still attacking a，which was trained sort of with the。



![](img/04b757b540d612311280a9bf6e43b33b_299.png)

curved line but just using examples from，b。

![](img/04b757b540d612311280a9bf6e43b33b_301.png)

uh，have an example in mind that's gonna，clarify things。



![](img/04b757b540d612311280a9bf6e43b33b_303.png)

uh and the example is for。

![](img/04b757b540d612311280a9bf6e43b33b_305.png)

a self-driving car there is a company，that has created a self-driving car or，the system behind it。



![](img/04b757b540d612311280a9bf6e43b33b_307.png)

and the vision system behind that，self-driving car。



![](img/04b757b540d612311280a9bf6e43b33b_309.png)

and let's say they are using uh resnet，100 for their vision and that one that，network。



![](img/04b757b540d612311280a9bf6e43b33b_311.png)

is trained to be robust because the，attacks。

![](img/04b757b540d612311280a9bf6e43b33b_313.png)

so that network is fixed now let's say，we are the adversary。



![](img/04b757b540d612311280a9bf6e43b33b_315.png)

and we want to attack that network we，want to，change the images that the car sees on，the fly。



![](img/04b757b540d612311280a9bf6e43b33b_317.png)

so we want to add noise to the images，that the car sees and，i don't know maybe make a mistake when。

it comes to the stop signs，and then it's going to lead to accidents。



![](img/04b757b540d612311280a9bf6e43b33b_319.png)

now what are we going to do as，adversaries there is a network that is，fixed that is mounted。



![](img/04b757b540d612311280a9bf6e43b33b_321.png)

on the machine on the car now we want to，attack it。



![](img/04b757b540d612311280a9bf6e43b33b_323.png)

let's say we are a very effective，adversary and we have access。



![](img/04b757b540d612311280a9bf6e43b33b_325.png)

to the architecture of the network and，we have access to the data that the，company used。



![](img/04b757b540d612311280a9bf6e43b33b_327.png)

to come up with that architecture that's，going to be a whitebox attack。

and that's by construction is going to。

![](img/04b757b540d612311280a9bf6e43b33b_329.png)

be the most effective one，because you have access to every single。

detail now you come up with that virtual，examples，the。



![](img/04b757b540d612311280a9bf6e43b33b_331.png)

system on the car and you're able to，lower the accuracy。



![](img/04b757b540d612311280a9bf6e43b33b_333.png)

it means that that car is sometimes，making mistakes，in recognizing stop signs it's not 100。



![](img/04b757b540d612311280a9bf6e43b33b_335.png)

effective but，you managed to hurt the system now let's，say。



![](img/04b757b540d612311280a9bf6e43b33b_337.png)

you don't have access to the，architecture you have access to the，architecture of the network。



![](img/04b757b540d612311280a9bf6e43b33b_339.png)

that is mounted on the system but you，are going to train your network，independently。



![](img/04b757b540d612311280a9bf6e43b33b_341.png)

from scratch and there are going to be，some random。



![](img/04b757b540d612311280a9bf6e43b33b_343.png)

effects going on because maybe your data，sets are different maybe the way you are。

training it is different。

![](img/04b757b540d612311280a9bf6e43b33b_345.png)

this is going to be a black box attack，but remember we are still。

attacking a network that is trying to be。

![](img/04b757b540d612311280a9bf6e43b33b_347.png)

robust and is already in production，so this is going to be black box attacks，black box attacks。



![](img/04b757b540d612311280a9bf6e43b33b_349.png)

because you don't have as much，information as white box attacks are，going to be less effective。



![](img/04b757b540d612311280a9bf6e43b33b_351.png)

and the thing is that you cannot compare，this 96 to that 98 i guess there was a。



![](img/04b757b540d612311280a9bf6e43b33b_353.png)

mistake here，we should compare fgsm to fgsm，and now you see that this is less。



![](img/04b757b540d612311280a9bf6e43b33b_355.png)

effective you should compare pgd，to pgd we should compare apples to。



![](img/04b757b540d612311280a9bf6e43b33b_357.png)

apples so it's the same attack，but you came up with these attacks using。



![](img/04b757b540d612311280a9bf6e43b33b_359.png)

your own version of the network but then，things could be even。



![](img/04b757b540d612311280a9bf6e43b33b_361.png)

worse your life as an adversarial，as an adversary could be even more，complicated。



![](img/04b757b540d612311280a9bf6e43b33b_363.png)

maybe you don't even have access to the，architecture that you are using maybe。

they are using inception maybe they are。

![](img/04b757b540d612311280a9bf6e43b33b_365.png)

using resnet，100 you can on your own computer。

![](img/04b757b540d612311280a9bf6e43b33b_367.png)

come up with inception you train，inception on your own data。



![](img/04b757b540d612311280a9bf6e43b33b_369.png)

you generate some images or the，perturbations to the images，and then you attack your original。



![](img/04b757b540d612311280a9bf6e43b33b_371.png)

network does that make sense now，i want to hear yeah i think yes it makes，sense。



![](img/04b757b540d612311280a9bf6e43b33b_373.png)

if you ignore that uh fgsm line，i think it makes sense but that one is。



![](img/04b757b540d612311280a9bf6e43b33b_375.png)

still confusing me but，but this could also be reasonable。



![](img/04b757b540d612311280a9bf6e43b33b_377.png)

you're right because you don't have，enough information，this one should be lower or should be。



![](img/04b757b540d612311280a9bf6e43b33b_379.png)

higher the thing is that we don't know，maybe our inception network is a more。



![](img/04b757b540d612311280a9bf6e43b33b_381.png)

powerful network that those guys are，using in production。



![](img/04b757b540d612311280a9bf6e43b33b_383.png)

i wouldn't read too much into this if，this could be an outlier or this could，just be。

a phenomena because of the type of a。

![](img/04b757b540d612311280a9bf6e43b33b_385.png)

network that they're using，and we should remember that these，adversarial。



![](img/04b757b540d612311280a9bf6e43b33b_387.png)

examples are general we saw that。

![](img/04b757b540d612311280a9bf6e43b33b_389.png)

in the first paper and that's why there，are serious problems，regardless of the architecture and。



![](img/04b757b540d612311280a9bf6e43b33b_391.png)

regardless of your training data，your universal so their generic examples，i think。



![](img/04b757b540d612311280a9bf6e43b33b_393.png)

we spent a good amount of time，understanding this table。



![](img/04b757b540d612311280a9bf6e43b33b_395.png)

and now it should make sense everything，should be clear，this is a similar table to the previous。

one for the previous one we were using，epsilon this epsilon here to be 0。03。

here we are using a bigger epsilon and，as you can see these numbers drop，from 98 to 87。

 so now we are，making the space of perturbations a，little bit bigger。

and now these attacks are becoming even，more successful，and by the way the network the robust。

network，is trained using epsilon being，0。3 and we were attacking it with the，same magnitude。

of an attack in this table here we are，attack，these are bigger perturbations so does。

this make sense and a nat here is a copy，of the original network。

trained on natural examples so if you，train on natural examples they are going，to be less effective。

and let's see how important is this，epsilon，when it comes to attacks i'm going to。

take a look at the blue，curves and this is epsilon the network，that is mounted on the。

car is trained using projected gradient，ascent，with epsilon of 0。3 so that's this，horizontal line。

so attacks with the epsilon less stuff，less than that number are less effective。

compared to when you increase the，magnitude of your attack so it's the，story of this。

this table compared to this table and，you see the，so that one goes for l infinity nor you。

can change the，to l to norm these are for mnist you are，gonna have a similar pattern。

now your epsilon is i don't know around，eight and you are，having a network that is trained on r。

c410 this is l，infinity norm l two norm and the blue，curve is the one that i'm interested in，about。

this paper before i move so just make，sure as a as epsilon gets。

super high the image becomes just pretty，much noise at some point right so it。

makes sense why would drop to，almost zero yeah so if given enough，noise。

any system can break but these are smart，noise，each image is gonna have its。

