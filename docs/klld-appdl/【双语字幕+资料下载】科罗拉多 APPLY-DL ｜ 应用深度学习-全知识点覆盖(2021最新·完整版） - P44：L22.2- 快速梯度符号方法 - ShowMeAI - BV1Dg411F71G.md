# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P44：L22.2- 快速梯度符号方法 - ShowMeAI - BV1Dg411F71G

okay so far so good now last session i，had this question，and one of you was thinking ahead i was。

saying，uh i think we can fix this if during，training，you keep adding these adversarial，set。

using these adverts several examples，then your network is going to become，robust，and。

can somebody mention the catch what's，the problem seems really expensive。

it seems like you have to fully train to，get a model，to then it's also fully trained to find。

the adversarial attacks，then go back and fully train that's an，amazing answer。

and that's correct that's 100 correct as，an answer，so yes you have to train your network。

find adversarial example，add that to the training and then，retrain and finding all of。

each one of these adversarial examples，is not cheap so you have to solve an，optimization problem。

okay but maybe there is a cheaper way to，generate adversarial examples。

and that's going to be the topic of the，next paper there is also but before we，go into that。

let's understand uh why adversarial，examples，exist in the first place i want you to，brainstorm。

and tell me why would that happen，why would adversarial examples exist so，your。

mind first i mean there's always going，to be boundaries between。

these regions uh in your in your range，right there's always going to be。

something that's close to being in，both classes okay but does it have to do。

anything with neural networks，in general what you're saying could be。

applicable to other methods as well，sure yeah i mean i think i think people，people。

or those there was that dress that no，one could decide what color it was a few，years ago。

so so you are saying it doesn't have to，do it doesn't have anything to do with。

neural networks yeah i think that there，are for any sort of classifier i think，that there's。

there's going to be something that is，difficult to classify，so now you're saying some images are。

difficult to classify，and because they are on the boundary on，the on the boundary of our decisions。

and a small perturbation might push it，to the other side of the boundary。

but if you look at it these are targeted，attacks，regardless of the image you're gonna be。

able to fool your network one hundred，percent，regardless of where you're imaging okay。

there is a comment from，for，certain patterns in the image and these，slide perturbations。

disturb these patterns，yes but i'm looking for a mathematical，idea making the neural network less。

sensitive，and that's why adversarial examples，exist is that what you're saying。

is there something could it be because，our neural networks are highly，non-linear。

that was my first thought was that the，domain of，all images is super high dimensional and。

so we're doing all of this convolution，and non-linearity because optimizing。

over that would be really hard and then，there's all of these local，minima and maxima and extrema。

if you change a few pixels here or a，cluster of pixels there or a line of，pixels over there，the。

classifier is giving you and it's yeah，it's what you were saying。

maziar about the non-linear thing is，like the driving factor there and。

the activations so you mentioned the，non-linearity，you mentioned high dimensionality and。

these are two different things，so rush is mentioning activations and，brandon is saying。

does it change the last surface to where，a new class is shifted。

so brandon is basically saying the last，surface matters，so the answer is it could be all of the。

above that are contributing，we don't know there could be a simple，explanation。

or some complicated explanation like the，manifold is too complicated and then a。

small perturbation is going to shift you，often manifold because this is going to。

be a manifold in a high dimension，high dimensional space and jacob is，saying is this similar to the。

initialization of weights，where the eigenvalues can be forced to，blow up shrink。

if they are not initialized correctly，that would also be an explanation。

because yes what you're talking about，now is the condition number of your，weights。

weight matrix you can also define the，condition number for，a neural network a nonlinear function。

these，could be an explanation and actually，their，papers trying to explain。

they come up with a hypothesis like you，guys were doing，and try to justify the hypothesis but。

the next paper is，very nice it is saying that that pattern，could have a very simple explanation and。

this could happen，even to linear models so yes，non-linearity might be a factor。

but even linear models are going to，suffer from，the existence of adversarial examples，and。

this observation is going to help them，come up with a cheaper way。

of creating adversarial examples and，we're going to see how。



![](img/4acd3f587914119178a089089d2c33b1_1.png)

input。

![](img/4acd3f587914119178a089089d2c33b1_3.png)

the image that we are interested in eta，is going to be our perturbation。

and x tilde is going to be the。

![](img/4acd3f587914119178a089089d2c33b1_5.png)

adversarial input our adversarial，example so，that was our notation the observation or。



![](img/4acd3f587914119178a089089d2c33b1_7.png)

at least what，we have in mind is that if the，perturbation is small。



![](img/4acd3f587914119178a089089d2c33b1_9.png)

then the classifier should assign the，same classes，for the same class to extill the annex。

that's what we expect from。

![](img/4acd3f587914119178a089089d2c33b1_11.png)

a robust neural network or a robust，classifier，let's do some linear algebra and we are。



![](img/4acd3f587914119178a089089d2c33b1_13.png)

now in the realm of linear networks。

![](img/4acd3f587914119178a089089d2c33b1_15.png)

there is no non-linearity no activation，we are going to take sex tilde，multiplied by a weight。

it's basically the dot product of two，vectors，and you can expand it this way it's。



![](img/4acd3f587914119178a089089d2c33b1_17.png)

gonna be w transpose，x plus w transpose eta and now if you。



![](img/4acd3f587914119178a089089d2c33b1_19.png)

subtract，the term on the left from the term on，the right these are。

how your activations are growing that's，the rate that's the growth rate of your，activation。



![](img/4acd3f587914119178a089089d2c33b1_21.png)

now let's do this let's set eta to be，the sine of your。



![](img/4acd3f587914119178a089089d2c33b1_23.png)

w times epsilon and epsilon was the，maximum，what is the infinitive norm of eta these。

values are either positive or negative，it's either plus one or negative one so。

the norm of this is going to be，epsilon so the infinity norm of the，perturbation is。

epsilon this particular perturbation now，let's look at this，growth growth rate expand the terms。

this is our inner product we know that，eta，was the sine of wi times epsilon。

so whenever you multiply this sine of a，number by itself that's going to give，you the absolute value。

so that's the absolute value times。

![](img/4acd3f587914119178a089089d2c33b1_25.png)

epsilon and let's say the average value。

![](img/4acd3f587914119178a089089d2c33b1_27.png)

our，weights is m now you have n of those，you get n times m times epsilon and as i。

said m is the average magnitude。

![](img/4acd3f587914119178a089089d2c33b1_29.png)

of an element of the weight vector and，one of you mentioned high dimensionality。



![](img/4acd3f587914119178a089089d2c33b1_31.png)

our images are high dimensional and even，for this linear model。



![](img/4acd3f587914119178a089089d2c33b1_33.png)

the dimension is gonna come into play if，n is huge，we are in trouble yes the perturbation。



![](img/4acd3f587914119178a089089d2c33b1_35.png)

could be small，of the order of epsilon the perturbation，to your image。



![](img/4acd3f587914119178a089089d2c33b1_37.png)

but the perturbation of the activations。

![](img/4acd3f587914119178a089089d2c33b1_39.png)

is gonna have is gonna have a huge norm，because of the high dimensionality so it，is clear。



![](img/4acd3f587914119178a089089d2c33b1_41.png)

so a small perturbation to our image，could lead to a large，perturbation of our activations because。



![](img/4acd3f587914119178a089089d2c33b1_43.png)

of the high dimensionality，regardless of how small your epsilon is，okay now that we see。

we went through that observation that，this could even happen。



![](img/4acd3f587914119178a089089d2c33b1_45.png)

to linear models we can try to replicate，the same idea。



![](img/4acd3f587914119178a089089d2c33b1_47.png)

for non-linear models and come up with a，method that's。



![](img/4acd3f587914119178a089089d2c33b1_49.png)

that the paper is calling fast gradient，sci method，of generating adversarial examples now。



![](img/4acd3f587914119178a089089d2c33b1_51.png)

you can generate your adversarial，examples on the fly，let's say theta are the parameters of。

your model these are。

![](img/4acd3f587914119178a089089d2c33b1_53.png)

the weights and biases of your network x，is the input to the model。



![](img/4acd3f587914119178a089089d2c33b1_55.png)

y is the target associated with x and，you're gonna have a cost function。



![](img/4acd3f587914119178a089089d2c33b1_57.png)

j you can do a similar thing to what we，did up there。



![](img/4acd3f587914119178a089089d2c33b1_59.png)

we can take a look at the gradient of，your loss function，with respect to the inputs for the。



![](img/4acd3f587914119178a089089d2c33b1_61.png)

linear case that's just going to be your，w，because when you take the derivative of。



![](img/4acd3f587914119178a089089d2c33b1_63.png)

your loss function with respect to x，and w is going to come out so now this，is a generalization。



![](img/4acd3f587914119178a089089d2c33b1_65.png)

of the linear model j could be，non-linear，and there could be a neural network with。



![](img/4acd3f587914119178a089089d2c33b1_67.png)

multiple layers inside it，but you look at the gradients with，respect to the input。



![](img/4acd3f587914119178a089089d2c33b1_69.png)

you take the sign because we are taking，the sign here，and then we are multiplying by epsilon。



![](img/4acd3f587914119178a089089d2c33b1_71.png)

so the infinity norm，of this eta is going to be epsilon same。



![](img/4acd3f587914119178a089089d2c33b1_73.png)

argument holds here these are just，positive and negative。



![](img/4acd3f587914119178a089089d2c33b1_75.png)

ones so let's see what it gives us you，have a classifier，that is correctly classifying your panda。



![](img/4acd3f587914119178a089089d2c33b1_77.png)

as a panda，with 57 percent confidence you add a，small。



![](img/4acd3f587914119178a089089d2c33b1_79.png)

this is our epsilon and you add the，sine of the gradient of your loss。



![](img/4acd3f587914119178a089089d2c33b1_81.png)

function and the resulting image，is going to be the perturbed one is。



![](img/4acd3f587914119178a089089d2c33b1_83.png)

going to be classified as a given。

![](img/4acd3f587914119178a089089d2c33b1_85.png)

with 99。3 confidence and this is a cheap，way of finding adversarial examples。



![](img/4acd3f587914119178a089089d2c33b1_87.png)

this is very cheap this operation we are，getting it for free，when you do back propagation not only。



![](img/4acd3f587914119178a089089d2c33b1_89.png)

x，with respect to your parameters you get，it with respect to x。



![](img/4acd3f587914119178a089089d2c33b1_91.png)

in one pass so this is very cheap this，is a very。

![](img/4acd3f587914119178a089089d2c33b1_93.png)

neat way of coming up with adversarial，examples unlike a previous one。

that you needed to have you needed to，solve an optimization problem。

this one is very cheap how does the sign。

![](img/4acd3f587914119178a089089d2c33b1_95.png)

work with multiple channels，because shouldn't it just be like，negative one or one we should make a。

binary，uh i don't see any problem with the，channels。



![](img/4acd3f587914119178a089089d2c33b1_97.png)

see whenever you have a function j，that is going from a tensor it's taking。



![](img/4acd3f587914119178a089089d2c33b1_99.png)

as input as a tensor，and in that tensor you have your，number。



![](img/4acd3f587914119178a089089d2c33b1_101.png)

the gradient of that scalar loss value。

![](img/4acd3f587914119178a089089d2c33b1_103.png)

is gonna have the same dimension as x so，this is going to have。



![](img/4acd3f587914119178a089089d2c33b1_105.png)

as many channels as your inputs so this，is also going to be a tensor。

and that's why simply you can add them，together and this sign。



![](img/4acd3f587914119178a089089d2c33b1_107.png)

is done point wise for every single，pixel。

![](img/4acd3f587914119178a089089d2c33b1_109.png)

and channel value it's going to be the，sign of that does that answer your，question。



![](img/4acd3f587914119178a089089d2c33b1_111.png)

yeah that makes sense thanks so that's，how the gradient works。



![](img/4acd3f587914119178a089089d2c33b1_113.png)

the gradient of a scalar valued function，with respect to the input is going to。

have the same dimension as the input it。

![](img/4acd3f587914119178a089089d2c33b1_115.png)

has the same shape，so if if eta is just plus n minus ones。



![](img/4acd3f587914119178a089089d2c33b1_117.png)

how can this um this like error image，um the the nematode image how。

how does that have multiple colors in it，is it because each channel。



![](img/4acd3f587914119178a089089d2c33b1_119.png)

is either a plus or a negative one and，if you combine like plus one red。



![](img/4acd3f587914119178a089089d2c33b1_121.png)

and negative one blue and positive one，yellow you get，different colors yes exactly okay that。



![](img/4acd3f587914119178a089089d2c33b1_123.png)

goes back to saurish's question，so it's not black and white because，there's color channels okay。



![](img/4acd3f587914119178a089089d2c33b1_125.png)

okay so far so good um back here now，that you know that there is a cheap way。



![](img/4acd3f587914119178a089089d2c33b1_127.png)

of generating adversarial examples you。

![](img/4acd3f587914119178a089089d2c33b1_129.png)

your，training data and try to make your，network more robust。



![](img/4acd3f587914119178a089089d2c33b1_131.png)

or equivalently you can modify your，loss function you're gonna put the。



![](img/4acd3f587914119178a089089d2c33b1_133.png)

weight of alpha and one minus alpha，with。

![](img/4acd3f587914119178a089089d2c33b1_135.png)

x being your trending data and y being，the corresponding label。



![](img/4acd3f587914119178a089089d2c33b1_137.png)

and one minus alpha of the times you're，just。

![](img/4acd3f587914119178a089089d2c33b1_139.png)

including an adversarial example in your，training set you're augmenting your data。

that's your new loss function and doing。

![](img/4acd3f587914119178a089089d2c33b1_141.png)

that you're going to be able to make，your network more robust。

at least to the examples generated this。

![](img/4acd3f587914119178a089089d2c33b1_143.png)

way using fast gradient sign method，and this one is cheap brandon has a。



![](img/4acd3f587914119178a089089d2c33b1_145.png)

question is there a method to find a，perturbation。

![](img/4acd3f587914119178a089089d2c33b1_147.png)

that allows you to classify a particular，class，so now you're talking about targeted。



![](img/4acd3f587914119178a089089d2c33b1_149.png)

examples targeted adversarial attacks，you。

![](img/4acd3f587914119178a089089d2c33b1_151.png)

you're just trying to confuse a network，to some other class。



![](img/4acd3f587914119178a089089d2c33b1_153.png)

but what we saw in the previous paper，was the targeted attack。



![](img/4acd3f587914119178a089089d2c33b1_155.png)

you fix the label and you want to，make your network to commit a mistake to。



![](img/4acd3f587914119178a089089d2c33b1_157.png)

that particular class，yes there is a method i can send you one，paper on that there are papers that。



![](img/4acd3f587914119178a089089d2c33b1_159.png)

extended this idea does that answer your，question okay perfect，but yeah that's a great point this is。



![](img/4acd3f587914119178a089089d2c33b1_161.png)

untargeted unlike the previous one that，was targeted，this one is untargeted but let's dig a。



![](img/4acd3f587914119178a089089d2c33b1_163.png)

little bit deeper，so what i'm including here is slightly。



![](img/4acd3f587914119178a089089d2c33b1_165.png)

different from what you see in the paper，and i encourage you to read the paper i，think。



![](img/4acd3f587914119178a089089d2c33b1_167.png)

the approach the way that i'm，approaching it here might be easier for，our class。



![](img/4acd3f587914119178a089089d2c33b1_169.png)

it might be more convincing let's take a，look at j。



![](img/4acd3f587914119178a089089d2c33b1_171.png)

tilde and what we are going to do is，going to take this，j term and do a taylor expansion on。



![](img/4acd3f587914119178a089089d2c33b1_173.png)

x on this entry when you do your taylor，expansion。

![](img/4acd3f587914119178a089089d2c33b1_175.png)

you're gonna end up with j of theta and，x and y，and there is one minus alpha here there。



![](img/4acd3f587914119178a089089d2c33b1_177.png)

is alpha here，these two are equal so you get a one，value。



![](img/4acd3f587914119178a089089d2c33b1_179.png)

and that's going to be j of theta x and，y and now you need，to write the rest of your taylor。



![](img/4acd3f587914119178a089089d2c33b1_181.png)

expansion for，this term you get 1 minus alpha epsilon。



![](img/4acd3f587914119178a089089d2c33b1_183.png)

sine of your gradient and that's going，to be your，perturbation now you need the first，order term。

in your taylor expansion and that's。

![](img/4acd3f587914119178a089089d2c33b1_185.png)

going to be the gradient，of x at that point this is around the，point that you're doing your taylor。



![](img/4acd3f587914119178a089089d2c33b1_187.png)

expansion so what i'm writing here is，just a，first order approximation of j tilde，using，that。



![](img/4acd3f587914119178a089089d2c33b1_189.png)

the next term is equality it's not any，you don't do any approximation there。



![](img/4acd3f587914119178a089089d2c33b1_191.png)

it's going to be this term plus 1 minus，alpha，epsilon and whenever you have the sine，of a vector。

multiplied by that vector you get the，absolute values because of the transpose。



![](img/4acd3f587914119178a089089d2c33b1_193.png)

you have a summation，and that's going to be l1 norm is this，clear what i just did。



![](img/4acd3f587914119178a089089d2c33b1_195.png)

this is not in the paper so i want you，to ask questions if you，if there is any mistakes here let me。



![](img/4acd3f587914119178a089089d2c33b1_197.png)

know if there is any confusion，please let me know that makes sense okay。



![](img/4acd3f587914119178a089089d2c33b1_199.png)

perfect so，what we are doing with adversarial，training we are sort of regularizing。



![](img/4acd3f587914119178a089089d2c33b1_201.png)

it's as if you're regularizing with，respect to your，the gradient of your loss function and。

this is a trade-off between，regularization and no regularization is。



![](img/4acd3f587914119178a089089d2c33b1_203.png)

alpha if alpha is one，you are not doing any regularization and。



![](img/4acd3f587914119178a089089d2c33b1_205.png)

if alpha is，slightly less than one you're doing more，regularization etc okay。



![](img/4acd3f587914119178a089089d2c33b1_207.png)

of。

![](img/4acd3f587914119178a089089d2c33b1_209.png)

our linear regression here or logistic，regression let's take a look at logistic，regression。



![](img/4acd3f587914119178a089089d2c33b1_211.png)

for logistic regression this is going to，be your loss function，and i'm going to tell you why for now。



![](img/4acd3f587914119178a089089d2c33b1_213.png)

just take me，just believe me and then i'm going to go，into more details here。



![](img/4acd3f587914119178a089089d2c33b1_215.png)

this is going to be your cost function，of。

![](img/4acd3f587914119178a089089d2c33b1_217.png)

j with respect to x once you do the，derivation，that's the term that you're going to end。



![](img/4acd3f587914119178a089089d2c33b1_219.png)

up with and now，let's take the l one norm of this term。



![](img/4acd3f587914119178a089089d2c33b1_221.png)

here，y is a value that is either one。

![](img/4acd3f587914119178a089089d2c33b1_223.png)

or negative one so now it's different，from what we saw before，we usually set y to be either zero or。



![](img/4acd3f587914119178a089089d2c33b1_225.png)

one now our y is either plus one or，negative one。

![](img/4acd3f587914119178a089089d2c33b1_227.png)

1。so the absolute value of these terms are。

![](img/4acd3f587914119178a089089d2c33b1_229.png)

going to be the absolute value of your，weights。

![](img/4acd3f587914119178a089089d2c33b1_231.png)

so the l1 norm of this gradient is just，the l1 norm of your weight。

because of the linearity in our model so，what you're seeing up there is just。

l1 regularization of your lost function。

![](img/4acd3f587914119178a089089d2c33b1_233.png)

and it's basically a generalization of。

![](img/4acd3f587914119178a089089d2c33b1_235.png)

what you have with l1 regularization，for logistic to a non-linear neural。

network when you do adversarial training。

![](img/4acd3f587914119178a089089d2c33b1_237.png)

so other serial trending is nothing but，a generalization。



![](img/4acd3f587914119178a089089d2c33b1_239.png)

of l1 regularization approximately，now let's go into more details of why。



![](img/4acd3f587914119178a089089d2c33b1_241.png)

logistic regression loss looks like that，and why the derivatives are like that so。

that was the big picture。

![](img/4acd3f587914119178a089089d2c33b1_243.png)

as i said our y is gonna have either a，value of negative one。



![](img/4acd3f587914119178a089089d2c33b1_245.png)

or one in our logistic regression setup，we are gonna say that p of y。



![](img/4acd3f587914119178a089089d2c33b1_247.png)

being equal to one is the sigmoid of a，linear，function and the sigmoid is going to。



![](img/4acd3f587914119178a089089d2c33b1_249.png)

squash values from negative infinity and，positive infinity to a value between。



![](img/4acd3f587914119178a089089d2c33b1_251.png)

negative one and one，sorry between zero and one it's going to，turn it into a probability。

now let's take a look at the actual。

![](img/4acd3f587914119178a089089d2c33b1_253.png)

formulation of sigma，of y hat that's just the definition of。



![](img/4acd3f587914119178a089089d2c33b1_255.png)

our sigma，of logistic function now if you multiply，the numerator and。



![](img/4acd3f587914119178a089089d2c33b1_257.png)

denominator by exponential of y-hat。

![](img/4acd3f587914119178a089089d2c33b1_259.png)

you get exponential of y-hat exponential，of y hat，and that's just one so you have two。

different formulations。

![](img/4acd3f587914119178a089089d2c33b1_261.png)

for your sigmoid function now let it，let's see what is the。



![](img/4acd3f587914119178a089089d2c33b1_263.png)

value of one minus sigma y hat because，that's gonna be p，of y equal to negative 1。 that's going。



![](img/4acd3f587914119178a089089d2c33b1_265.png)

to be，1 plus exponential i'm using this term，here，to write the fraction here because if。

you divide that term by this term it's，going to give you the 1 and the rest of。



![](img/4acd3f587914119178a089089d2c33b1_267.png)

it is just a sigmoid，negative 1 divided by this it's just，your sigmoid。



![](img/4acd3f587914119178a089089d2c33b1_269.png)

now let's cancel out a couple of terms，and you're going to end up with that。



![](img/4acd3f587914119178a089089d2c33b1_271.png)

and this is just from the second，definition of sigmoid。



![](img/4acd3f587914119178a089089d2c33b1_273.png)

this is just sigma of negative y so the，final objective was 1 minus sigma of y，hat is equal to。



![](img/4acd3f587914119178a089089d2c33b1_275.png)

sigma of negative y hat so that's what i，wanted to get at。



![](img/4acd3f587914119178a089089d2c33b1_277.png)

it means that p of y being equal to the，other class，which is 1 minus sigma of the first，class is。



![](img/4acd3f587914119178a089089d2c33b1_279.png)

sigma of negative of your inputs now you，see why we were。



![](img/4acd3f587914119178a089089d2c33b1_281.png)

doing it this way why our values should，be either plus one or negative one。



![](img/4acd3f587914119178a089089d2c33b1_283.png)

because this value here is exactly the，value that，you have here and y being equal to one。



![](img/4acd3f587914119178a089089d2c33b1_285.png)

there is a one that's being multiplied，by this term，it means that you can explain your。



![](img/4acd3f587914119178a089089d2c33b1_287.png)

probability，as sigma of y times the other term。

![](img/4acd3f587914119178a089089d2c33b1_289.png)

is it clear so far and all we did was，use this problem。



![](img/4acd3f587914119178a089089d2c33b1_291.png)

this property of one minus sigma，is just sigma of negative of the。



![](img/4acd3f587914119178a089089d2c33b1_293.png)

argument now what is our loss function，we want to maximize our likelihood or。



![](img/4acd3f587914119178a089089d2c33b1_295.png)

equivalently minimize the negative，of the log of the likelihood and this is，our objective function。



![](img/4acd3f587914119178a089089d2c33b1_297.png)

and x and y have the data distribution，you take the negative sign。



![](img/4acd3f587914119178a089089d2c33b1_299.png)

you put it here use the log properties，it's going to give you log of 1 over p。



![](img/4acd3f587914119178a089089d2c33b1_301.png)

of y this is the same exponential value，that's the log and here we are using the。



![](img/4acd3f587914119178a089089d2c33b1_303.png)

formula for p of y，that's going to give you 1 over this。



![](img/4acd3f587914119178a089089d2c33b1_305.png)

term and the entire fraction you can，write it as 1 plus exponential of，negative y。



![](img/4acd3f587914119178a089089d2c33b1_307.png)

of w transpose x plus b now we're going，to define a function。



![](img/4acd3f587914119178a089089d2c33b1_309.png)

eta or that's just，just。

![](img/4acd3f587914119178a089089d2c33b1_311.png)

the soft plus function and z in our case，is going to be negative y times w。



![](img/4acd3f587914119178a089089d2c33b1_313.png)

transpose x plus b that's our soft plus，function，and the derivative of self plus is just。



![](img/4acd3f587914119178a089089d2c33b1_315.png)

sigmoid，you can write the math down it's very，easy it's just simply so now i gave you。



![](img/4acd3f587914119178a089089d2c33b1_317.png)

what i owed you，i owed you why our loss function is like，this。



![](img/4acd3f587914119178a089089d2c33b1_319.png)

now you see why there is a log term the，same log term is here。



![](img/4acd3f587914119178a089089d2c33b1_321.png)

and then you have one plus exponential，of negative y w transpose x plus b。



![](img/4acd3f587914119178a089089d2c33b1_323.png)

that's our cost function，and the gradient depends on sigma and we，see why。



![](img/4acd3f587914119178a089089d2c33b1_325.png)

and the rest of it is just chain rule so，now we had an overview of logistic，regulation。

okay now let's say you have a problem，that is try to distinguish，three from sevens that's a。

classification，let's say this is your plus example，that's your，minus example seven is the negative。

example，we know that we need to take a look at w，if you want to pair two things。

that's our weight for the logistic，regression we know that we need to take。

a look at the sign of the weight，that's the sign of the weight and you，see there is nothing。

indicating in this perturbation that is，indicative of three or seven。

so it's not telling us whether we are，whether this perturbation has anything，to do with our data。

our targets so the network is making，very not the network the logistic，regression is making。

very small errors on this problem but，once you add that，it's going to confuse the network。

totally it's going to make 100，errors this perturbation so even a，single。

a simple logistic regression is going to，get confused you can，also take a look at your weights the。

ones that are，trained without regularization this is，without adversarial training these are。

your weights，and and if you train it with adversarial，training。

your weights are gonna have a different，pattern i think we are。

right on time for those of you who have，questions you're more than welcome。

to stay and ask and for those of you who，want to leave we can leave，those adversarially trained um。

weights where your cursor is right now，just appear to be，more i guess close to gray which is。

like close to zero i'm guessing so is，that what you were saying is，the logistic regression is almost。

equivalent to，l1 normalization or regularization yes，what l1 regularization does is trying to，small。

right square sound is small yes okay and，so those ones on the left。

are not because you have a lot of black，and a lot of white which is like really，positive。

and really negative exactly okay yes，you're exactly seeing the effect here。

because of this what are we seeing down，in um，in diagram d with like the the。

the images with like the the grayness in，the background，well what are you saying is this uh。

image here three added to the，perturbation，so it's b plus c that's giving you d but。

then to human eye we know that，this is seven that's a three tower well。

this league regression is confusing at，100 percent，this has a high accuracy here but it has。

a very low。