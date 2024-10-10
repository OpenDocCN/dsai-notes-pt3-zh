# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P13：L6.2- Kaiming参数初始化 - ShowMeAI - BV1Dg411F71G

![](img/2a83c3d6bd56a9e9b9fc12c277006098_0.png)

so this next paper assumes that you are。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_2.png)

going to use。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_4.png)

a rectifier a relu activation function，so they introduce a new activation。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_6.png)

function parametric value。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_8.png)

and this is parametric value，where a is a parameter that you're going。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_10.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_11.png)

and if you write it in a functional form，this is what you get。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_13.png)

this is the maximum of zero and y i。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_15.png)

ai you can learn it and that's called。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_17.png)

parametric value。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_19.png)

if it's a constant usually。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_21.png)

a small constant that's going to be，called leaky value if it's a constant。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_23.png)

and you are not training it。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_25.png)

and here i is different channels。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_27.png)

so per each channel you can have a，different ai。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_29.png)

how do you train it because these have，to be trained。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_31.png)

you take the gradient of your loss，function with respect to this parameter，and use momentum method。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_33.png)

to train this so what happens。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_35.png)

reduces your top five。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_37.png)

from 13。34。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_39.png)

to 12。75 when you are doing it channel，wise and you're。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_41.png)

training it channel wise，if you have a single a for all of your。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_43.png)

channels，this is the top five that you get now。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_45.png)

for leaky value with this particular，parameter。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_47.png)

that's what you get you have a better，top one but a worse。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_49.png)

and this paper is about this type of。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_51.png)

activation functions，so the initialization of your rates and。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_53.png)

biases depends on the activation。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_55.png)

so what should we take into。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_57.png)

a good indicator is gonna be the。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_59.png)

of the response in each layer。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_61.png)

that's the central idea of this paper。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_63.png)

basically if this is your xl。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_65.png)

l is your layer l could be。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_67.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_68.png)

all of your image not all of your image。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_70.png)

that particular，window of the image that you're sliding。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_72.png)

over your，this。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_74.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_75.png)

so what is going to be the size of this。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_77.png)

it's gonna have k by k pixels。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_79.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_80.png)

and then it's gonna have c channels。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_82.png)

and then n is going to be k。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_84.png)

and the rest of it is just matrix。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_86.png)

multiplication。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_88.png)

is that clear this is another way of。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_90.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_91.png)

k is your filter size and n is the，number of connections，of a response so it's basically k。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_93.png)

squared。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_95.png)

so you have this image let's say this，screen is our image。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_97.png)

we take a particular window，that is k by k of the image。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_99.png)

and each pixel we know it's c，dimensional it can have red green blue，or if you are。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_101.png)

in one of your layers it could be。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_103.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_104.png)

so you are taking a cube here，and putting everything inside one vector。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_106.png)

xl。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_108.png)

that are of the same size and you're。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_110.png)

just multiplying that particular window。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_112.png)

by that kernel that you have，and that's going to be the inner product。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_114.png)

of two vectors，now you have multiple inner products。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_116.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_117.png)

therefore it's just a matrix product，so this is the number of filters the。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_119.png)

and your wl。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_121.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_122.png)

is d by n now。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_124.png)

and yl is going to be the response at。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_126.png)

the pixel，of the output map so what did we just do。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_128.png)

we want to know what is the value of，this pixel。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_130.png)

in the output map and each pixel is，going to be a vector。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_132.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_133.png)

so what you do is just multiply。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_135.png)

this weight which is d by n by a vector，that's n by，one and that's going to give you a。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_137.png)

vector that's in rd，so this guy is in rd and bias is in rd。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_139.png)

that's going to give you the value of。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_141.png)

so please ask questions if it's not。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_143.png)

clear so when you're breaking，when you're breaking your like window。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_145.png)

down you just stack it sort of，by columns or by rows or some sort of，predetermined。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_147.png)

yes but it doesn't really matter yes，because in the end，you're going to compute the inner。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_149.png)

product and the inner product has a，summation。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_151.png)

okay so the order doesn't matter as long，as you're consistent。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_153.png)

it doesn't matter whether it's robust，column wiser。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_155.png)

but the idea is that you get a window。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_157.png)

by c and then you。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_159.png)

flatten the flatten it out。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_161.png)

in the end you're gonna get a single。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_163.png)

but then we know what its size is is k，squared by c。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_165.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_166.png)

so i want this to be as clear as，possible。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_168.png)

if you have any questions i want all of。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_170.png)

this is a nice way to think about，convolutions。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_172.png)

it's nothing but a vector。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_174.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_175.png)

what，slides over the entire window to give，you your spatial。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_177.png)

like representation so yl。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_179.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_180.png)

being outputted from your convolution，so the input to the convolution is x the。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_182.png)

the input to the convolution is x the。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_184.png)

output of convolution is y，and it's just one of the pixels in the。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_186.png)

output，which is going to be d dimension the，dimensions of y。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_188.png)

are then the dimensions of the number of，channels in your next input。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_190.png)

exactly ah right exactly and d，is basically the number of filters that，you have。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_192.png)

yes okay so you have every。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_194.png)

matrix vector multiplication。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_196.png)

is just d。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_198.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_199.png)

so sorry you said while becomes one by d。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_201.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_202.png)

so how are these layers related to each。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_204.png)

other this is very important，the outputs of the previous layer。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_206.png)

is going to go through a non-linearity，and that's going to give you the input。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_208.png)

to this layer，is that correct this is value。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_210.png)

so the output of the previous layer。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_212.png)

is going to go through a non-linearity，and that's going to give you。

the current input to your neural network。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_214.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_215.png)

same thing happens for yl it goes，through a non-linearity，and then it's become it's going to。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_217.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_218.png)

is that clear and how are the dimensions，related。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_220.png)

the number of output channels from the，previous layer。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_222.png)

is equal to the number of input channels。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_224.png)

now for this layer，so these are just a bunch of identities。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_226.png)

cl is equal to dl minus 1。xl is a non-linearity applied to yl。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_228.png)

minus 1。so i'm going to ask a question is it，clear and then i need you to write。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_230.png)

yes or no or answer yes or no。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_232.png)

is everything clear yep。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_234.png)

okay perfect i don't want you to get。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_236.png)

so what are we gonna do now as i said we，are going to take a look at the variance，of the response。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_238.png)

basically variance of yl what happens to。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_240.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_241.png)

you are doing matrix vector，multiplication。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_243.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_244.png)

over n basically of the size n，it means that you are going to have an l。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_246.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_247.png)

and the variance of the bias is just，that's what you assume and then you。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_249.png)

assume bl is independent from wl。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_251.png)

times x these are the assumptions that，you make，so you're going to have a summation of。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_253.png)

similar things，and that's why you get n l times。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_255.png)

variance of w，alexa and wl is just。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_257.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_258.png)

uh one of the rows of this big wl，capital wl okay perfect。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_260.png)

how do we make the assumption that the，weights are。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_262.png)

that's an assumption that you make，because。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_264.png)

this is under your control because what，is the final aim you want to initialize。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_266.png)

these weights so we are gonna initialize，it with a random number。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_268.png)

that has mean zero that's a great，question。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_270.png)

but then it's under your control，so you have full control over the mean。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_272.png)

of your，weights and it's a good assumption you。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_274.png)

have a normal with mean zero and some。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_276.png)

variance，and you sample from that to initialize，your rates。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_278.png)

so that assumption you make and this is，just an identity。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_280.png)

so i want you to this is an exercise the，variance of two random variables。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_282.png)

is equal to that。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_284.png)

and if you just google variance of the，product of two random variables this is。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_286.png)

gonna，show up as one of the formulas。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_288.png)

so what is the what is the spectra of，that matrix。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_290.png)

look like we are going to take a look at，that。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_292.png)

just，inner products and then you're just。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_294.png)

multiplying things，okay this is a particular entry of this。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_296.png)

which is going to be a random variable。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_298.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_299.png)

okay so what happens，the mean of these wls the entries of。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_301.png)

your，filters we assumed it to be zero。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_303.png)

value。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_305.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_306.png)

this is not true the。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_308.png)

second moment of xl is not equal to the，variance of xl。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_310.png)

because you are using this relu，non-linearities。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_312.png)

so this is your xl and there is no，guarantee that it has a mean zero。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_314.png)

it's coming out of a non-linearity，if it had mean zero this would be true。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_316.png)

this would be equality，but now it's inequality because。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_318.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_319.png)

zero。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_321.png)

so what are we doing what is yl it's a，random element of yl。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_323.png)

wl is a random element of this matrix，and xl is a random variable representing。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_325.png)

your inputs，so this is to explain the notation up。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_327.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_328.png)

i think i'm going to stop here we are，one minute over time。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_330.png)

if there are any questions please feel，free to ask，and for those of you who want to leave。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_332.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_333.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_334.png)

our is there anything um，i guess there's always square um filters。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_336.png)

has there ever been like non-square，filters so you have like a k by。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_338.png)

some other value。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_340.png)

you could but the convention is they，usually assume they are equal。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_342.png)

but that's perfectly fine，you can have different filter sizes。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_344.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_345.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_346.png)

because if you think about it things are，symmetric。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_348.png)

left or，right so if you rotate a。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_350.png)

an image whatever that's inside that。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_352.png)

image which could be a dark is it still，a dock。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_354.png)

okay so things are symmetric，around your pixel that's why they。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_356.png)

usually assume。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_358.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_359.png)

any other questions i had a quick，question about。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_361.png)

uh dropout so from a couple lectures ago，um and specifically so。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_363.png)

the sort of like last step。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_365.png)

um in dropout is after you've，trained you uh。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_367.png)

you update your weights by multiplying，by that like probability whatever drop。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_369.png)

dropout probability you had。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_371.png)

um and my question was just in most。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_373.png)

software for building neural networks is。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_375.png)

that just implicitly done，during training that at the last sort of。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_377.png)

step of training，they'll update the weights one last time，or is that an。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_379.png)

action that is usually carried out，every time when you're doing an。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_381.png)

inference。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_383.png)

for you mean there is a discrepancy，between training and，because。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_385.png)

we talked about for dropout that after。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_387.png)

you've that your weights for testing，weights。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_389.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_390.png)

like the average。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_392.png)

yes and i was just curious if that's a，like during training in most software's。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_394.png)

did they do that step for you no，so now during training things are fine。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_396.png)

because you just multiply by。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_398.png)

a random vector that's bernoulli，and then it's going to kill some of your。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_400.png)

outputs some of them，okay that's during training but during。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_402.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_403.png)

you have to shrink your weights，basically by the probability of those。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_405.png)

guys being absent or present。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_407.png)

and will that be done every time in an，inference，like each time in france what happens is。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_409.png)

that，you already have your rates and biases。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_411.png)

trained the rates of your neural network。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_413.png)

and then you can just give it to，somebody else，but yeah as you give it to somebody else。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_415.png)

you have to tell them what is your peak，the capability of dropping a neural，network okay so that。



![](img/2a83c3d6bd56a9e9b9fc12c277006098_417.png)

there is，you can do it the same way that you did。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_419.png)

it okay。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_421.png)