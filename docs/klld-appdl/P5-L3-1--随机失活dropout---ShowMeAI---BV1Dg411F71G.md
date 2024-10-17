# P5：L3.1- 随机失活dropout - ShowMeAI - BV1Dg411F71G

okay let's get，started last session we talked about，the first paper that started it all，started the。

field of deep learning as we know it，today，we talked a little bit about，convolutions。

we talked about the type of loss，function that we are going to use and。

there are some methods that i'm not，covering from the paper，i will cover them in other papers。

through the means of studying other，papers，for instance they were using drop out。

and they were using activation functions，like relu，rectify rectified linear units。

they were using data augmentation which，i didn't cover from the paper。

but i will cover them through the means。

![](img/2e147076f781266bf2b61eab4417f21d_1.png)

let's talk about dropout first，uh so what is dropout，there are two objectives。

when you do drop out in deep learning，one is to prevent your models from。



![](img/2e147076f781266bf2b61eab4417f21d_3.png)

overfitting，and what is overfitting over fitting，happens when you are，[Music]。

basically your model is too powerful，that it's gonna memorize your training。

data so it's going to do a perfect job，on your training data but who cares，about the training data。

we want to take our algorithm the one，that comes out of。



![](img/2e147076f781266bf2b61eab4417f21d_5.png)

deep learning and put it into production，so our algorithm should be able to do a。

good job actually on the。

![](img/2e147076f781266bf2b61eab4417f21d_7.png)

so if your model does a great job，on your training data but does very。

and usually convolutional neural，networks。

![](img/2e147076f781266bf2b61eab4417f21d_9.png)

are less prone to overfitting because of，the weight sharing idea。



![](img/2e147076f781266bf2b61eab4417f21d_11.png)

so you are sharing the same filter，which is for instance three by three or，eleven by eleven。



![](img/2e147076f781266bf2b61eab4417f21d_13.png)

and you're sliding it over your image，because of the weight sharing idea those。

are less prone to overfitting。

![](img/2e147076f781266bf2b61eab4417f21d_15.png)

but the densely connected ones，the ones that you usually put at the end，of your。



![](img/2e147076f781266bf2b61eab4417f21d_17.png)

neural network to extract your features，those are prone to。



![](img/2e147076f781266bf2b61eab4417f21d_19.png)

overfitting so dropout is going to take。

![](img/2e147076f781266bf2b61eab4417f21d_21.png)

another objective is to combine，multiple models together，in a smart way so usually。

when people report their accuracy，for their evaluation metric，they usually combine multiple models。

together they have an。

![](img/2e147076f781266bf2b61eab4417f21d_23.png)

ensemble of models so ensembling is a，great idea，for your model to be able to generalize。



![](img/2e147076f781266bf2b61eab4417f21d_25.png)

to your test data and，actually in production the idea is that，you're gonna have。

multiple models maybe thousands of，models，do the same task and then they are gonna，vote。

is this image a cat is this image a dark，and then the consensus is gonna be。

the output of the ensemble model。

![](img/2e147076f781266bf2b61eab4417f21d_27.png)

so dropout is a way of ensembling，in a smart way we're gonna see why it is。



![](img/2e147076f781266bf2b61eab4417f21d_29.png)

smart，so you have two objectives when you do。

![](img/2e147076f781266bf2b61eab4417f21d_31.png)

![](img/2e147076f781266bf2b61eab4417f21d_32.png)

the network on the left is a standard，these are the inputs and these are the，neurons。



![](img/2e147076f781266bf2b61eab4417f21d_34.png)

so the input could be，that particular portion of the image，that you have or it could be。



![](img/2e147076f781266bf2b61eab4417f21d_36.png)

the dimensions so think of this as input，dimensions。



![](img/2e147076f781266bf2b61eab4417f21d_38.png)

and the neuron is gonna。

![](img/2e147076f781266bf2b61eab4417f21d_40.png)

be the output of multiplying a bunch of，weights，by your input dimensions adding them up。



![](img/2e147076f781266bf2b61eab4417f21d_42.png)

basically it's a dot product and then。

![](img/2e147076f781266bf2b61eab4417f21d_44.png)

putting and putting the output here，after pushing it through a non-linearity。

so this is going to give you a neuron。

![](img/2e147076f781266bf2b61eab4417f21d_46.png)

that's going to give you another neuron，and so on and they have different。



![](img/2e147076f781266bf2b61eab4417f21d_48.png)

weights as you can see，okay that's how to visualize a neural，what dropout does is gonna drop。



![](img/2e147076f781266bf2b61eab4417f21d_50.png)

![](img/2e147076f781266bf2b61eab4417f21d_51.png)

and it's gonna drop at random，some of the neurons it means that now，you have。



![](img/2e147076f781266bf2b61eab4417f21d_53.png)

less weight to do your summation on，what is the idea the idea is that a。



![](img/2e147076f781266bf2b61eab4417f21d_55.png)

single neuron，should be able to do its job。

![](img/2e147076f781266bf2b61eab4417f21d_57.png)

![](img/2e147076f781266bf2b61eab4417f21d_58.png)

this is what people call co-adaptation，you don't want your neurons to co-adapt。



![](img/2e147076f781266bf2b61eab4417f21d_60.png)

you don't want them you want them to be，independent。



![](img/2e147076f781266bf2b61eab4417f21d_62.png)

![](img/2e147076f781266bf2b61eab4417f21d_63.png)

so that's why it's going to help with。

![](img/2e147076f781266bf2b61eab4417f21d_65.png)

the other aspect was ensembling。

![](img/2e147076f781266bf2b61eab4417f21d_67.png)

each one of these guys。

![](img/2e147076f781266bf2b61eab4417f21d_69.png)

is going to be a neural net on its own，with less weights and biases。

so it has much fewer rates and biases，and less neurons，it's definitely a weaker neural network。



![](img/2e147076f781266bf2b61eab4417f21d_71.png)

but at each iteration you're gonna，kill some of these neurons at random。



![](img/2e147076f781266bf2b61eab4417f21d_73.png)

so you have thousands of，uh or millions of these uh，small neural networks that are being。



![](img/2e147076f781266bf2b61eab4417f21d_75.png)

and now you need to on to form your，ensemble in the end，and how are we going to do that is。



![](img/2e147076f781266bf2b61eab4417f21d_77.png)

coming up，so there are two objectives one is。

![](img/2e147076f781266bf2b61eab4417f21d_79.png)

preventing overfitting，in that sense it's just a regularization。



![](img/2e147076f781266bf2b61eab4417f21d_81.png)

the other one is you want to combine，exponentially。



![](img/2e147076f781266bf2b61eab4417f21d_83.png)

many different neural nets and these are。

![](img/2e147076f781266bf2b61eab4417f21d_85.png)

the type of the neural net architectures。

![](img/2e147076f781266bf2b61eab4417f21d_87.png)

can i ask a quick question sure um，so when you say like these are if you're。

viewing each neuron as sort of an，independent。

![](img/2e147076f781266bf2b61eab4417f21d_89.png)

uh neural network you mean that in the，sense that。

![](img/2e147076f781266bf2b61eab4417f21d_91.png)

different，layer types and it's like own sort of。

![](img/2e147076f781266bf2b61eab4417f21d_93.png)

structured neural network not just like，one sort of。



![](img/2e147076f781266bf2b61eab4417f21d_95.png)

type of layer connected like over and，over again if that makes sense。



![](img/2e147076f781266bf2b61eab4417f21d_97.png)

uh like it's not just one of these，just，only convolutional layers and then。



![](img/2e147076f781266bf2b61eab4417f21d_99.png)

another neuron is only，like fully connected layers so what i'm。



![](img/2e147076f781266bf2b61eab4417f21d_101.png)

talking about here in this slide is very，generic，so it could be a convolutional neural。



![](img/2e147076f781266bf2b61eab4417f21d_103.png)

net it could be recurrent it could be，lstm。

![](img/2e147076f781266bf2b61eab4417f21d_105.png)

it could be fully connected it could be，whatever，okay and it could be any combination of。



![](img/2e147076f781266bf2b61eab4417f21d_107.png)

any of those layer types in one model，yes exactly okay cool thank you but the。



![](img/2e147076f781266bf2b61eab4417f21d_109.png)

idea is general，okay some point in your training you're。



![](img/2e147076f781266bf2b61eab4417f21d_111.png)

gonna kill，your neurons okay basically perish data。



![](img/2e147076f781266bf2b61eab4417f21d_113.png)

point that goes in，that data point is going to see a。



![](img/2e147076f781266bf2b61eab4417f21d_115.png)

okay at random。

![](img/2e147076f781266bf2b61eab4417f21d_117.png)

![](img/2e147076f781266bf2b61eab4417f21d_118.png)

so here is another way of looking at the，same topic。



![](img/2e147076f781266bf2b61eab4417f21d_120.png)

so this neuron for instance this one。

![](img/2e147076f781266bf2b61eab4417f21d_122.png)

is gonna be present with probability p。

![](img/2e147076f781266bf2b61eab4417f21d_124.png)

perish round of training，so each data point is going to come in，and it's either c this。



![](img/2e147076f781266bf2b61eab4417f21d_126.png)

is that is either going to see this，neuron or is not gonna see this。



![](img/2e147076f781266bf2b61eab4417f21d_128.png)

through，it or it's absent it has to go through。

![](img/2e147076f781266bf2b61eab4417f21d_130.png)

another route。

![](img/2e147076f781266bf2b61eab4417f21d_132.png)

that's during training but at testing，you don't want things to be random。



![](img/2e147076f781266bf2b61eab4417f21d_134.png)

you don't want to combine you want to，combine multiple。



![](img/2e147076f781266bf2b61eab4417f21d_136.png)

neural network architectures together。

![](img/2e147076f781266bf2b61eab4417f21d_138.png)

and the way that the paper is doing it，is keeping all of these neurons so this。

neuron is going to be always。

![](img/2e147076f781266bf2b61eab4417f21d_140.png)

present so all of the neurons are going，to be present。



![](img/2e147076f781266bf2b61eab4417f21d_142.png)

in the end but then you are going to。

![](img/2e147076f781266bf2b61eab4417f21d_144.png)

![](img/2e147076f781266bf2b61eab4417f21d_145.png)

by the same ratio by the same。

![](img/2e147076f781266bf2b61eab4417f21d_147.png)

the question is is applying dropout to a。

![](img/2e147076f781266bf2b61eab4417f21d_149.png)

large，neural network equivalent to the idea of。

![](img/2e147076f781266bf2b61eab4417f21d_151.png)

ensembling，yes so it's equivalent to the idea of，ensembling。



![](img/2e147076f781266bf2b61eab4417f21d_153.png)

but it's approximate ensembling and the，ensembling is happening here。



![](img/2e147076f781266bf2b61eab4417f21d_155.png)

when you're keeping all of your neurons。

![](img/2e147076f781266bf2b61eab4417f21d_157.png)

but then you are scaling down your，weights by probability。



![](img/2e147076f781266bf2b61eab4417f21d_159.png)

so it's the expectation of your。

![](img/2e147076f781266bf2b61eab4417f21d_161.png)

neural network but you're doing it，in an approximate way so it's。



![](img/2e147076f781266bf2b61eab4417f21d_163.png)

approximate expected value of，you get。

![](img/2e147076f781266bf2b61eab4417f21d_165.png)

is an ensemble and as i said the idea of，a dropout。



![](img/2e147076f781266bf2b61eab4417f21d_167.png)

is that each hidden unit basically each，one of these guys。



![](img/2e147076f781266bf2b61eab4417f21d_169.png)

![](img/2e147076f781266bf2b61eab4417f21d_170.png)

has to be able to work independently，it shouldn't rely on the neural network。



![](img/2e147076f781266bf2b61eab4417f21d_172.png)

![](img/2e147076f781266bf2b61eab4417f21d_173.png)

group。

![](img/2e147076f781266bf2b61eab4417f21d_175.png)

in your class in each session，i would randomly associate you with。



![](img/2e147076f781266bf2b61eab4417f21d_177.png)

another team，and team members this way you don't。

![](img/2e147076f781266bf2b61eab4417f21d_179.png)

learn to rely on person x all the time。

![](img/2e147076f781266bf2b61eab4417f21d_181.png)

or you do some of the work the other，person is going to do。



![](img/2e147076f781266bf2b61eab4417f21d_183.png)

some part of the some other parts of the，work but you depend on each other。



![](img/2e147076f781266bf2b61eab4417f21d_185.png)

that's called co-adaptation，in our neural network we don't want that。



![](img/2e147076f781266bf2b61eab4417f21d_187.png)

to happen，during a single back propagation pass。

![](img/2e147076f781266bf2b61eab4417f21d_189.png)

still。

![](img/2e147076f781266bf2b61eab4417f21d_191.png)

updated or，they are excluded so they are going to。

![](img/2e147076f781266bf2b61eab4417f21d_193.png)

be excluded，because they are absent for that。

![](img/2e147076f781266bf2b61eab4417f21d_195.png)

they are absent it means that their。

![](img/2e147076f781266bf2b61eab4417f21d_197.png)

rates are going to be zero。

![](img/2e147076f781266bf2b61eab4417f21d_199.png)

and they are not going to get updated，does that answer your question。



![](img/2e147076f781266bf2b61eab4417f21d_201.png)

john okay perfect，so now let's get into the math how do，you actually。



![](img/2e147076f781266bf2b61eab4417f21d_203.png)

write down the math and how do you，implement it，let's say l denotes the number of hidden。



![](img/2e147076f781266bf2b61eab4417f21d_205.png)

layers，in your neural network basically this is。

![](img/2e147076f781266bf2b61eab4417f21d_207.png)

![](img/2e147076f781266bf2b61eab4417f21d_208.png)

so that's l and，little l is gonna say this is the first。



![](img/2e147076f781266bf2b61eab4417f21d_210.png)

layer this is the second layer this is，the third layer。



![](img/2e147076f781266bf2b61eab4417f21d_212.png)

that's the index of your layer。

![](img/2e147076f781266bf2b61eab4417f21d_214.png)

what you are seeing here in neuron。

![](img/2e147076f781266bf2b61eab4417f21d_216.png)

is a non-linearity applied on。

![](img/2e147076f781266bf2b61eab4417f21d_218.png)

a hidden z，so that's yl it's a non-linearity。

![](img/2e147076f781266bf2b61eab4417f21d_220.png)

and what is zl it's a dot product，between your rates and your inputs。



![](img/2e147076f781266bf2b61eab4417f21d_222.png)

so if these are your inputs and these，are your weights the arrows。



![](img/2e147076f781266bf2b61eab4417f21d_224.png)

![](img/2e147076f781266bf2b61eab4417f21d_225.png)

and then adding them up together，that's going to give you a single number，and then you can add。



![](img/2e147076f781266bf2b61eab4417f21d_227.png)

![](img/2e147076f781266bf2b61eab4417f21d_228.png)

that's gonna be your neuron sitting here，that's the eighth neuron basically here。



![](img/2e147076f781266bf2b61eab4417f21d_230.png)

this is the first neuron second neuron，third neuron。



![](img/2e147076f781266bf2b61eab4417f21d_232.png)

fourth neuron fifth neuron and。

![](img/2e147076f781266bf2b61eab4417f21d_234.png)

![](img/2e147076f781266bf2b61eab4417f21d_235.png)

that's a typical neural network on the，left。

![](img/2e147076f781266bf2b61eab4417f21d_237.png)

![](img/2e147076f781266bf2b61eab4417f21d_238.png)

at layer l you're gonna sample，from a bernoulli distribution basically。



![](img/2e147076f781266bf2b61eab4417f21d_240.png)

you have a coin，that you flip it and then with，probability p。



![](img/2e147076f781266bf2b61eab4417f21d_242.png)

it's going to be one with probability，one minus p is going to be zero。

that's your bernoulli distribution and。

![](img/2e147076f781266bf2b61eab4417f21d_244.png)

they are independent。

![](img/2e147076f781266bf2b61eab4417f21d_246.png)

and at layer l you get，for instance one two three four five，numbers。



![](img/2e147076f781266bf2b61eab4417f21d_248.png)

some of them are zero some of them are。

![](img/2e147076f781266bf2b61eab4417f21d_250.png)

![](img/2e147076f781266bf2b61eab4417f21d_251.png)

the idea is that you multiply your input，by these random numbers so it means that。

the neuron is going to be。

![](img/2e147076f781266bf2b61eab4417f21d_253.png)

some of them are going to be absent some，of them are going to be present。



![](img/2e147076f781266bf2b61eab4417f21d_255.png)

![](img/2e147076f781266bf2b61eab4417f21d_256.png)

the question is how do you pick p，usually a good number。



![](img/2e147076f781266bf2b61eab4417f21d_258.png)

![](img/2e147076f781266bf2b61eab4417f21d_259.png)

[Music]，and。

![](img/2e147076f781266bf2b61eab4417f21d_261.png)

for the intermediate layers a good p is，0。5 basically half of the times。



![](img/2e147076f781266bf2b61eab4417f21d_263.png)

you keep the neuron half of the times，you。

![](img/2e147076f781266bf2b61eab4417f21d_265.png)

exclude it。

![](img/2e147076f781266bf2b61eab4417f21d_267.png)

a good one is probably 0。8。85。9。

![](img/2e147076f781266bf2b61eab4417f21d_269.png)

so it's not that sensitive to the choice。

![](img/2e147076f781266bf2b61eab4417f21d_271.png)

of p，that's why i'm saying a good number is，usually。



![](img/2e147076f781266bf2b61eab4417f21d_273.png)

0。5 but the way that you。

![](img/2e147076f781266bf2b61eab4417f21d_275.png)

these are hyper parameters of your model，the way yet the way that you set them is。



![](img/2e147076f781266bf2b61eab4417f21d_277.png)

usually using cross validation，you take a look at your validation data，and choose the best p。



![](img/2e147076f781266bf2b61eab4417f21d_279.png)

![](img/2e147076f781266bf2b61eab4417f21d_280.png)

![](img/2e147076f781266bf2b61eab4417f21d_281.png)

so now that you killed some of your，neurons and you kept。



![](img/2e147076f781266bf2b61eab4417f21d_283.png)

other ones the rest of it is the same as，before。

![](img/2e147076f781266bf2b61eab4417f21d_285.png)

and because some of these guys are zero，we go back to your question what happens。



![](img/2e147076f781266bf2b61eab4417f21d_287.png)

in back propagation，you are multiplying your weight by zero，so that weight doesn't exist。



![](img/2e147076f781266bf2b61eab4417f21d_289.png)

so in your back propagation that way it。

![](img/2e147076f781266bf2b61eab4417f21d_291.png)

is not going to update，because it is absent for instance this，weight is absent。



![](img/2e147076f781266bf2b61eab4417f21d_293.png)

![](img/2e147076f781266bf2b61eab4417f21d_294.png)

and the rest of it is just applying the。

![](img/2e147076f781266bf2b61eab4417f21d_296.png)

the question is can you explain point。

![](img/2e147076f781266bf2b61eab4417f21d_298.png)

and how this is accomplished by the。

![](img/2e147076f781266bf2b61eab4417f21d_300.png)

dropout technique。

![](img/2e147076f781266bf2b61eab4417f21d_302.png)

so yes that one we haven't yet covered，so damien is asking about。



![](img/2e147076f781266bf2b61eab4417f21d_304.png)

this part how do you approximately，combine exponentially many。



![](img/2e147076f781266bf2b61eab4417f21d_306.png)

i will explain that later so so far we，are doing training，and each data point is gonna see a new。



![](img/2e147076f781266bf2b61eab4417f21d_308.png)

model。

![](img/2e147076f781266bf2b61eab4417f21d_310.png)

when it goes through our neural network，so during training each one of these，guys learn to be。



![](img/2e147076f781266bf2b61eab4417f21d_312.png)

independent or as independent as。

![](img/2e147076f781266bf2b61eab4417f21d_314.png)

let's take a look at it visually this。

![](img/2e147076f781266bf2b61eab4417f21d_316.png)

is the l before the activation。

![](img/2e147076f781266bf2b61eab4417f21d_318.png)

![](img/2e147076f781266bf2b61eab4417f21d_319.png)

of 1 and your。

![](img/2e147076f781266bf2b61eab4417f21d_321.png)

previous neurons coming from the，previous layer。

![](img/2e147076f781266bf2b61eab4417f21d_323.png)

and the one here stands for because。

![](img/2e147076f781266bf2b61eab4417f21d_325.png)

you're multiplying b，by one so that's how you get your。



![](img/2e147076f781266bf2b61eab4417f21d_327.png)

neuron is neuron at layer l。

![](img/2e147076f781266bf2b61eab4417f21d_329.png)

plus one that's your standard neural，network。

![](img/2e147076f781266bf2b61eab4417f21d_331.png)

and visually you're gonna create some，random numbers here。



![](img/2e147076f781266bf2b61eab4417f21d_333.png)

they are either one or zero and you，multiply it。

![](img/2e147076f781266bf2b61eab4417f21d_335.png)

to get your y tildes so that's how you，kill your neurons。



![](img/2e147076f781266bf2b61eab4417f21d_337.png)

if this number is zero y three hat is，gonna be，zero it means that you're crossing it。



![](img/2e147076f781266bf2b61eab4417f21d_339.png)

out。

![](img/2e147076f781266bf2b61eab4417f21d_341.png)

the question is how do you average it。

![](img/2e147076f781266bf2b61eab4417f21d_343.png)

out，how do you average multiple neural，networks out。



![](img/2e147076f781266bf2b61eab4417f21d_345.png)

you do it in expectation。

![](img/2e147076f781266bf2b61eab4417f21d_347.png)

and the way it happens is that half of，the times or。



![](img/2e147076f781266bf2b61eab4417f21d_349.png)

p ratio of the times p。

![](img/2e147076f781266bf2b61eab4417f21d_351.png)

some of the weights are present and one，minus p percent of the time it doesn't，it's not present。



![](img/2e147076f781266bf2b61eab4417f21d_353.png)

the expected value is gonna be p times。

![](img/2e147076f781266bf2b61eab4417f21d_355.png)

the weight during testing you don't want，things to be random，and that's how you do the averaging and。



![](img/2e147076f781266bf2b61eab4417f21d_357.png)

that's how i answer your question damian。

![](img/2e147076f781266bf2b61eab4417f21d_359.png)

this is how you combine exponentially。

![](img/2e147076f781266bf2b61eab4417f21d_361.png)

different neural network architectures。

![](img/2e147076f781266bf2b61eab4417f21d_363.png)

and i'm gonna show you empirically why。

![](img/2e147076f781266bf2b61eab4417f21d_365.png)

![](img/2e147076f781266bf2b61eab4417f21d_366.png)

there is another technique in the paper，and that's max nor normalization。



![](img/2e147076f781266bf2b61eab4417f21d_368.png)

it's basically weight clipping you don't，want your rate to become。



![](img/2e147076f781266bf2b61eab4417f21d_370.png)

too big that's another technique for，regularizing neural networks so i highly。



![](img/2e147076f781266bf2b61eab4417f21d_372.png)

encourage you guys，to read these two papers especially。



![](img/2e147076f781266bf2b61eab4417f21d_374.png)

![](img/2e147076f781266bf2b61eab4417f21d_375.png)

there is a nice i would say。

![](img/2e147076f781266bf2b61eab4417f21d_377.png)

that tells you how drop out when you。

![](img/2e147076f781266bf2b61eab4417f21d_379.png)

apply it，to linear regression is to be equivalent。

![](img/2e147076f781266bf2b61eab4417f21d_381.png)

to reach regression and range regression，is basically。



![](img/2e147076f781266bf2b61eab4417f21d_383.png)

regularizing your your weights。

![](img/2e147076f781266bf2b61eab4417f21d_385.png)

so it's actually doing a regularization。

![](img/2e147076f781266bf2b61eab4417f21d_387.png)

for us。

![](img/2e147076f781266bf2b61eab4417f21d_389.png)

![](img/2e147076f781266bf2b61eab4417f21d_390.png)

so they apply the method drop out，to multiple types of neural networks and。



![](img/2e147076f781266bf2b61eab4417f21d_392.png)

in different domains。

![](img/2e147076f781266bf2b61eab4417f21d_394.png)

which is the topic of our course so far。

![](img/2e147076f781266bf2b61eab4417f21d_396.png)

they apply to speech text and genetics。

![](img/2e147076f781266bf2b61eab4417f21d_398.png)

that's why i mentioned that these types，of methods are，universal you can apply to any type of。



![](img/2e147076f781266bf2b61eab4417f21d_400.png)

neural network that you have。

![](img/2e147076f781266bf2b61eab4417f21d_402.png)

and these are different data sets and，list。

![](img/2e147076f781266bf2b61eab4417f21d_404.png)

is the digits data set street view，house numbers are the numbers that are。



![](img/2e147076f781266bf2b61eab4417f21d_406.png)

coming from google。

![](img/2e147076f781266bf2b61eab4417f21d_408.png)

taking images google earth。

![](img/2e147076f781266bf2b61eab4417f21d_410.png)

these are low resolution images and they。

![](img/2e147076f781266bf2b61eab4417f21d_412.png)

have 10 labels and 100 labels。

![](img/2e147076f781266bf2b61eab4417f21d_414.png)

respectively there is imagenet，which is a huge data set and the，resolution is bigger。



![](img/2e147076f781266bf2b61eab4417f21d_416.png)

it's 256 by 256。 there is timid it's a。

![](img/2e147076f781266bf2b61eab4417f21d_418.png)

data set for，speech and reuters。

![](img/2e147076f781266bf2b61eab4417f21d_420.png)

is a data set for text and the other one，is for genetics。



![](img/2e147076f781266bf2b61eab4417f21d_422.png)

this is the size of the training data。

![](img/2e147076f781266bf2b61eab4417f21d_424.png)

and they apply the method on all of，these。

![](img/2e147076f781266bf2b61eab4417f21d_426.png)

and as you can see some of these，[Music]。

![](img/2e147076f781266bf2b61eab4417f21d_428.png)

data sets are really small compared to，one and a half，million 1。2 million these are small data。



![](img/2e147076f781266bf2b61eab4417f21d_430.png)

sets，so it's very important for us to。

![](img/2e147076f781266bf2b61eab4417f21d_432.png)

regularize our method otherwise neural。

![](img/2e147076f781266bf2b61eab4417f21d_434.png)

and this is what you get this is the，the classification error during，training for。

different types of models，is gonna end up being a better number，and it's gonna converge faster。

with dropout compared to beat up，dropouts，so it's a very effective way of。

is there ever a reason not to use，sometimes you want to take derivatives。

of your neural network with respect to，inputs，with those derivatives but other than，that i would say。

no it's a good idea to use it all the，time，is there an advantage of starting。

with a higher number of neurons and，using dropout，that's a good question i would say the，advantage。

your question is yes sort of addressing，problem one maybe a smaller model，is gonna not overfit。

with a lower number of neurons probably，it's gonna be less prone to overfitting。

but then you are not combining many，different models if you use a single。

with a smaller number of neurons the，question is，how are you approximately combining many。

different models，one way of combining it was，during testing perish data point，you look at a random。

model take a look at the predictions，then get another data set get another。

data point push it through another，random model that's going to give you，another。

prediction and keep doing that for i，don't know，maybe 10 times and then average the。

and then your test classification error，on the average is going to be this。

and this is basically a monte carlo，model averaging，we are just monte carlo averaging our。

outputs our predictions，and yes if you do it enough times，maybe 120 times。

you might get a better model compared to，weight scaling because this line is，great scaling。

but as you can see this is within the，so this is actually a very good way of。

averaging neural networks，in the end you keep all of your weights，but then you，question。

um so when we're referring to，when we're talking about dropout as a，method for。

combining different models，network，models that internally，may also use dropout and then we're。

using dropout，to combine these models into some like，ensemble supermodel is that correct。

uh that's sort of correct yes，so you start with a huge model that's。

if you do that that's going to give you，and during training these guys have to，do good jobs。

this is smaller neural networks and they，are random，in the end you average them this way。

does that answer your question yeah i，guess i guess i'm a little confused if。

we're saying that each neuron，inside of each neuron we might have like，three convolutional layers。

neuron，this whatever you do whether it's a，convolution or anything，okay okay each neuron is a linear。

combination of，the input to the neura okay that makes，sense to me i guess i was just getting a。

little confused with the word，model and no here it is a model it's，just a。

this is just a neuron okay and，mathematically this is what it is。

yeah yeah that is exactly so there is no，other way of interpreting it。

that's the implementation this is not a，recurrent neural network this is not a，convolution this is。

this is just linear combinations of your，inputs，that's the bias so there is a question。

my understanding is that applying，dropout inherently，creates lots of models because they are。

not the same，since each of them have randomly dropped，neurons，exactly so that's a correct。

interpretation，so any other questions feedback，do you have to maintain independence，between neurons。

or does drop out prevent co-adaptation，due to drop neurons，so dropout is actually gonna prevent。

co-adaptation，so it's gonna maintain independence for，us and as you can see the title of the。

paper is improving neural networks by，preventing，co-adaptation of feature detectors so。

that's exactly what it's doing，does that answer your question perfect，any other questions。

is there a way to reproduce neural，networks，measure，i'm gonna answer john's question first。

i'm not sure probably you can take a，look at one of the neurons。

and see how it behaves during training，with dropout versus without dropout。

and now let's go back to parker's，question，is there a way to reproduce neural。

networks trained using dropout，i don't know what you mean by reproduce。

okay i'll expand on that so let's say，i'm using dropout i'm randomly killing，off。

neurons to create a model and i'm，happy with that model but now somebody，else wants to take the。

data set that i started with and，reproduce，that model so is there a way since the，way。

to reproduce that process，using like a random generator seed now i，see what you're saying。

so there are two things that are，happening here，one is during training things are random。

you are correct but during testing，it's when you want to give your model to，somebody else。

things are deterministic so you keep all，of the，parameters but then you weight them。

okay so the model that you share with，others and you put in production is this。

after the training is done this is what，okay so i would share my weights and the。

the probability that i chose，exactly okay thank you，so no during testing things are not。

random you're deterministic，for how many iterations do you train a，certain dropout network。

before moving to another，every single data point that goes in，is gonna see a random net。

so every time you push a，data point inside your neural network，a random number is gonna generate。

and then a random set of your neurons，are going to be，dropped out of your neural network，i。

started with many people think of，dropout as a regularization technique。

and they don't know about the second，point that you are actually。

approximately combining exponentially，many different neural networks together。

and the key point is here，and many of you are asking questions。

whether this is actually deterministic，or no，is it a stochastic neural net no。

so that one is gonna be deterministic so。