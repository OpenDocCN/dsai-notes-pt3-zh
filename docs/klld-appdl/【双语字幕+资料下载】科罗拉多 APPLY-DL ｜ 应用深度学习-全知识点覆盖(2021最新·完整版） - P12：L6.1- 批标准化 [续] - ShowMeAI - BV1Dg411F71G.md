# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P12：L6.1- 批标准化 [续] - ShowMeAI - BV1Dg411F71G

![](img/3f2c7619a5a495e0dd801d97904a2eb9_0.png)

last session we introduced what we mean，by covariance shift，which is basically the statistics of。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_2.png)

each layer's inputs。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_4.png)

then we said we want to do batch。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_6.png)

normalization to mitigate that effect，and then batch normalization had two，parts one was training。

and one is testing during training。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_8.png)

things are allowed to be random，so you do it is random because you are。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_10.png)

and then we said we take a mini badge。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_12.png)

we take the mean of that mini batch，subtract it from x。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_14.png)

the input to that particular layer is x，we subtract the mean and divide by the，standard deviation。

and then that epsilon is just a。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_16.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_17.png)

but then if you do that you run into，trouble，because everything that goes inside your。

activation function，is going to have a mean 0 and unit。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_19.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_20.png)

to counter that effect you multiply by，gamma，which is acting as your standard，deviation。

and then you are adding a bias which is，acting at。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_22.png)

as your mean and these are going to be。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_24.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_25.png)

and every operation is element-wise，and one thing to note is that the。

gradients of your loss function。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_27.png)

flow through mu and sigma so batch。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_29.png)

normalization is sort of anticipating，what's going to happen as the parameters，change。

then during testing and in particular。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_31.png)

inference，you need to put a single number or a。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_33.png)

single vector，for things to be deterministic not to，depend，on your mini batch that's why during。

training。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_35.png)

you keep a running average of your mean，and variance，and basically mu is that running average。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_37.png)

and sigma is that。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_39.png)

so we stopped here any questions up。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_41.png)

now this is for a fully connected。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_43.png)

network，this is for a linear。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_45.png)

combination of the input。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_47.png)

to this particular layer u is the input。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_49.png)

and w times u is x，as you can see this is a linear，combination you are just multiplying a。

vector by a matrix，what happens in the case of，convolutional neural networks。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_51.png)

for convolution the input。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_53.png)

x is gonna。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_55.png)

it's gonna have p pixels in the x。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_57.png)

dimension q pixels in the y dimension，and you're gonna have d channels or d。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_59.png)

what you do is you take the number of。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_61.png)

the size of your mini batch which is m。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_63.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_64.png)

so all of these are going to be your，data now，and the effective size of your mini，batch increases。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_66.png)

and then you do your mean and a standard，deviation on that。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_68.png)

basically batch norm is being done，per feature map so you're doing it per。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_70.png)

each dimension of your feature map。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_72.png)

so not only you do your summation，necessary for computing your mean and，variance。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_74.png)

on your mini batch on the number of，images that just went into your neural。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_76.png)

network，but also pixel wise，you are doing a summation over the，pixels as well。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_78.png)

give you give you your mean and standard。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_80.png)

deviation which is going to be in rd，so your mean and a standard deviation is，not going to be in r。

p times q times d but rather it's going。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_82.png)

to be in d，and then everything that you see here。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_84.png)

this subtraction and division，are gonna be broadcasted for those of。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_86.png)

you who know，python you know that。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_88.png)

if you subtract a vector from a matrix。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_90.png)

then the vector is going to turn into a，matrix。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_92.png)

having the same size as your x and then，everything is going to get subtracted。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_94.png)

so first your vectors are going to turn，into matrices and then。

you do your subtraction or division or。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_96.png)

multiplication，that's the concept of broadcasting is，everything clear。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_98.png)

seems okay okay perfect so what are some，of the benefits。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_100.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_101.png)

you can get away with a higher learning。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_103.png)

basically you are taking care of the，covariate shift and。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_105.png)

these inputs to your activation are not，going to have crazy values。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_107.png)

think about it if g is，a sigmoid and then you don't do batch。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_109.png)

normalization，and this x gets too big basically this。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_111.png)

input，then you're in the saturating regime。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_113.png)

of your activation function and，everything is going to turn。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_115.png)

into a constant and then its derivative，is going to be zero，so you can get away with higher learning。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_117.png)

rate，the method is now less sensitive to。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_119.png)

because we are doing in the end and，optimization if you remember the first。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_121.png)

lecture。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_123.png)

it was all about optimization methods，and optimization methods depend on the，initial condition。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_125.png)

basically the initial values of your，rates and biases。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_127.png)

and in the next topic i will talk about，how to properly initialize your neural。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_129.png)

networks，but for now batch normalization is going。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_131.png)

to make things less sensitive，to initialization because whatever your。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_133.png)

initialization is，you're subtracting the mean and the，variance。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_135.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_136.png)

things are gonna be less sensitive to，activation function，right sorry when you say initialization。

do you mean initialization of weights，or like initial training data no。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_138.png)

initialization of rates and biases，okay in the end you're going to write a。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_140.png)

loss function，and that loss function is a function of。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_142.png)

these weights and biases，and the role of training is to find the，best。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_144.png)

combination of weights and biases。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_146.png)

right but then your algorithm。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_148.png)

let's say adam has to start，with a good guess if the initial guess。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_150.png)

for these parameters are very off。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_152.png)

then there is no hope for training，if you initialize everything with zero。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_154.png)

there is no signal to propagate and then，you you're gonna。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_156.png)

get stuck at zero for instance，right and how does basketball，normalization sort of。

help you become less sensitive to that。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_158.png)

so the way it does it it's by taking，care of the covariate shifts。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_160.png)

so whatever the weights and biases are，whatever this w is。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_162.png)

you get an x and from that x you are。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_164.png)

subtracting the mean and the variables。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_166.png)

thank you so see batch normalization is，multiplication。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_168.png)

so that's why it's less sensitive to，initialization，it's going to be less sensitive to the。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_170.png)

choice of activation function，because now the input，to your g function is gonna be。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_172.png)

mostly centered around zero。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_174.png)

so these numbers are not going to get。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_176.png)

and if you take a look at for instance。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_178.png)

the sigmoid activation function。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_180.png)

it's going to stay in the regime where，it's mostly linear，it's not going to go into the non-linear。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_182.png)

parts and then。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_184.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_185.png)

why because things are random each time。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_187.png)

your neural network is sort of random，because of different means and variances。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_189.png)

so it has a similar effect to drop out，because of the randomness you're。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_191.png)

introducing，and then it preserves gradient。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_193.png)

magnitudes this is a maybe，so this needs further investigation。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_195.png)

so basically you need to be careful，write down your gradients and see。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_197.png)

benefits。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_199.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_200.png)

to see what i mean by covariate shift，first of all what is the benefit this is，mnist。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_202.png)

dataset and you are training a simple，neural network。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_204.png)

and the m is digits data set。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_206.png)

this is with this is without batch，normalization this is with batch，normalization。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_208.png)

so you're converging much faster。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_210.png)

and what's the y-axis is basically，the accuracy，on the test data so this is actually the。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_212.png)

generalization error。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_214.png)

but then to see a concept of。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_216.png)

the input to a particular activation，g is。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_218.png)

uh for instance in this case it's going，to be wu。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_220.png)

that input you can take its mean and。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_222.png)

so what we are plotting here is not。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_224.png)

median and then。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_226.png)

the upper quartile and lower quartile，and then you can just plot that。

basically we are plotting the statistics。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_228.png)

of this，during training as you can see it's，nasty it goes。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_230.png)

up and down and it's not symmetric。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_232.png)

but after bash normalization the input，to your activation is sort of。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_234.png)

you're most of the time around zero and。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_236.png)

[Music]。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_238.png)

that's basically a way to plot your，distribution。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_240.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_241.png)

half and 85 percentiles。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_243.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_244.png)

so this is covariate shift this is your。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_246.png)

you removed covariate shift by this。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_248.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_249.png)

[Music]，this is the inception network basically，google net。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_251.png)

the one that we covered last session。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_253.png)

and this is the number of training steps。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_255.png)

and the y-axis is the accuracy，and it's getting closer to i don't know，70 percent。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_257.png)

that's the inception module and this is。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_259.png)

how many how much iteration how many，iterations you have to wait，for your method to convert you this。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_261.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_262.png)

only。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_264.png)

change that you do for this red dashed，line。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_266.png)

is introduce batch normalization and you，already cut。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_268.png)

the training the amount of，training necessary i would say less than。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_270.png)

half，compared to inception。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_272.png)

then you have batch normalization with。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_274.png)

five times bigger learning rate，which is going to get you here much。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_276.png)

then you have batch normalization 30。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_278.png)

times，faster basically that's your learning，rate。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_280.png)

you can change the sigmoid this is，because we just made a claim，that bash normalization is less。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_282.png)

sensitive to activation functions，you change the activation function to。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_284.png)

sigmoid，and this is what you get and。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_286.png)

these diamond blue diamonds is just。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_288.png)

how many iterations it takes to reach，the accuracy of the inception model。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_290.png)

so it's really beneficial at that time。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_292.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_293.png)

so if you think about it these are。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_295.png)

really huge，claims to be making when you're training。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_297.png)

a neural network，can i ask a quick question sure um。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_299.png)

so beta and gamma are。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_301.png)

parameters learned on the scale of like，an entire，layer is that correct as opposed to like。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_303.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_304.png)

like in for your in，the normal situation your bias is，applied to each。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_306.png)

connection right but in this case beta。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_308.png)

applies to every single connection in a，dense layer for example。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_310.png)

no it it it is actually it has the same，size as b。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_312.png)

learning，replacing the bias okay so you have a，different one for each。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_314.png)

each connection per each layer you have。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_316.png)

a different one，but i mentioned you have a different，scalar。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_318.png)

if that's what you mean but in like a，single dense。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_320.png)

layer if you have like a bunch of，neurons。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_322.png)

each each neuron would have their own，bias right yes each output neuron。

will have its own bias basically。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_324.png)

each d is gonna have its own bias，okay oh and i see okay that notation。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_326.png)

there so each，output neuron has their own beta in this，case in their own gamma as well。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_328.png)

okay yes but these are vectorized，notation here this is a vector of the。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_330.png)

same size as b，yeah okay thank you yeah。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_332.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_333.png)

so your beta is acting the role of b，because as you subtract the mean b is。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_335.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_336.png)

disappear，to。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_338.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_339.png)

one drawback is that this is sort of，random，things that are happening during。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_341.png)

one drawback maybe is that you cannot。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_343.png)

get away with，only one sample if m is one。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_345.png)

then you're in trouble because their，standard deviation of。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_347.png)

a number is going to be zero and then。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_349.png)

so batch normalization with a batch size。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_351.png)

how close does this end up being if you。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_353.png)

sort of append a layer，onto the front of your network that does。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_355.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_356.png)

you could do that but then your mean。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_358.png)

is your parameter and then what is the，data，to train that parameter is probably this。

you could do that you can say x minus a，parameter divided by。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_360.png)

sigma squared which one this one is also，a parameter，but then you need to train this。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_362.png)

you cannot use the same loss that you。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_364.png)

have for，gamma and beta and w to train mu and。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_366.png)

sigma。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_368.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_369.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_370.png)

it seems like a lot of these，regularization techniques end up being，external to the network。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_372.png)

yes exactly。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_374.png)

so actually，this paper batch normalization。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_376.png)

they're using the inception model the，one from the previous。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_378.png)

slide and they make improvements，actually huge improvements over that。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_380.png)

![](img/3f2c7619a5a495e0dd801d97904a2eb9_381.png)

so what changes do they make they remove，dropout，altogether they say that we don't need。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_383.png)

it anymore，because batch normalization is sort of，doing the regularization。

on its own they increase their learning，rate。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_385.png)

which is this plot on the left which，means that，they don't have to look at their。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_387.png)

computer training for，i don't know。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_389.png)

14 million iterations so it's a，difference between。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_391.png)

one week versus。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_393.png)

uh three days four days，of staring at your computer and waiting，for your results。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_395.png)

they accelerate the learning rate decay，so usually when you're training your，neural networks。

as the training progresses。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_397.png)

you usually see that the loss is，dropping for some reason。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_399.png)

at those points they're reducing their，learning rate，so when they say they accelerate the。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_401.png)

learning rate decay。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_403.png)

they do it faster basically，they do these jumps faster for the，training。

there is a weight decay which is，equivalent to l2。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_405.png)

rate regularization。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_407.png)

and this was part of alexnet，and most neural networks do that there，is this weight decay。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_409.png)

and they want their weights to go，towards zero it's a usually very small。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_411.png)

parameter and they actually reduce that，even further。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_413.png)

so apparently there is no need for not，much。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_415.png)

do you remember that nasty local，response normalization。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_417.png)

so after this paper actually most of，neural networks where classification，don't use that anymore。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_419.png)

they don't use local response。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_421.png)

and they shuffle the training examples，more more thoroughly。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_423.png)

because the more random things are to，the eyes of the neural network。

and the more independent are those。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_425.png)

samples the network is gonna learn，faster。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_427.png)

how sensitive is this to batch size，so usually the way that you train your。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_429.png)

neural networks，is that you choose your m。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_431.png)

as big as possible so that it fits。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_433.png)

the data and the network itself，fits on the gpu but then how sensitive。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_435.png)

it is，uh that i don't have a definite answer。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_437.png)

to that depends on the model，that you're training so that i don't。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_439.png)

know，and these are some of the results that，you see，there is google net the inception model。

they had this resolution if you remember，224。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_441.png)

and it was an ensemble model，so they were using seven models doing，the prediction and in the end。

and they were using 144 crops，per image for things to be translation，invariant and this was their。

top five error and you can compare it to，4。9 when you do an ensemble of。

batch normalization neural networks so。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_443.png)

it's a huge gain，so bash normalization is really powerful，that's the message and it's really easy。

to implement，and it's already implemented most of，implemented in most of your。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_445.png)

neural network packages you just say i，want a batch normalization layer and put，it on top of my。

convolution so that number for，models is that independent like ensemble，models right。

yes so usually the way that they do it，is you train multiple models。

with different changes in your hyper，parameters and weight initialization。

a couple of these models not all of them，are coming from different，in the end they and some of them。

are a combination of being trained by a，learning rate five times bigger。

some of them with a sigmoid so these。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_447.png)

so minor changes but in the end，it has a huge effect from from 5。82。

because remember what is the aim here，there is this，challenge that you have to win so。

whatever changes that you make，you to your neural network in the end，that's your objective。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_449.png)

to reduce your top five error rate or。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_451.png)

and the competition is fierce so it's，not easy to improve by，such a huge margin any other questions。

are those batch norm models，including batch normalization once or，multiple times in the network。

no this is for one layer usually after，each。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_453.png)

convolution there is a patch node，so in your neural network you have，multiple layers。

and each layer usually has，a couple of convolutions after each，convolution。

there is a batch node does that answer，your question，any other questions before before i。

change the topic，just to follow up on that real quick so，in practice。

you will put like as many batch norm，layers，as there are convolution or dense layers，in your network。

essentially yes that's correct okay，some of them might not have it probably，the。

initial convolutions the one closer to，your input，because the input is already normalized。

usually your image is you take the image，subtract the mean，and then that's going to be your input。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_455.png)

to your neural network，your convolutional neural network okay。

and would that be uh be inserted before，or after max pooling or does it not make，a difference。

uh it makes a difference，and then we are gonna go over the best，place for batch norm。

in the future in some future papers，okay but for now after your convolution，you can put a batch。

any other questions see these are easy，questions，to ask and then easy to answer。

but then you have to answer them on a，computer，you might say why not put batch norm，right after you。

and then multiply it by weight，the people who wrote this paper actually，did that。

and it just doesn't work okay，sometimes the answers are as simple as，that it doesn't work。

the network doesn't converge any other，questions。

![](img/3f2c7619a5a495e0dd801d97904a2eb9_457.png)

so the next topic is gonna be about，initialization we never talked about，that。

i was waiting until this moment，what is the proper way to initialize the，neural network。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_459.png)

what are the proper initial values for，rates and biases，can anybody answer that or what should。

we take into account，when we want to answer that question you，might want the。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_461.png)

the map to be like a full rank map of，some kind，[Music]。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_463.png)

not really any other，thoughts what might go wrong，let's do it this way let's remove batch。

node let's remove g，then you have a bunch of matrices that，are being multiplied by each other。

and this multiplication，is being done，16 times let's talk about vgg16。

where you have 16 layers so you have 16，of these w's，being multiplied by each other until you。

reach your image，well on a machine it's not necessarily，precise that's one thing。



![](img/3f2c7619a5a495e0dd801d97904a2eb9_465.png)

and mathematically what can go wrong，it can blow up exactly，so whenever you see multiplication and。

you have，a lot of them being multiplied together，a lot of w's。

things could happen either those weights，have an eigenvalue of less than one。

then everything is going to collapse to，zero，by the end of your output or it's going，to explode。

yeah jacob you're right it either grows，or it shrinks，very fast so multiplication is dangerous。

so we have to be careful with，initializing，these weights properly。

there is another catch even for a single，layer，you might end up in a regime。

where g saturates what if you initialize，your weights，and then you are doing value that's your。

activation function，you get a bunch of zeros and it'll，propagate zeros forever and you won't。

get any information，exactly so two things matter，one is this g one is these guys being。

