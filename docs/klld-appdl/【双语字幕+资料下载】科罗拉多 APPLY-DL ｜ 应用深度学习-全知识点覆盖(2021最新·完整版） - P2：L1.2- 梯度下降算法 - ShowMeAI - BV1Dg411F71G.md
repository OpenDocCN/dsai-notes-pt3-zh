# P2：L1.2- 梯度下降算法 - ShowMeAI - BV1Dg411F71G

![](img/a0b313688aaa5693b64432d8cb007a1b_0.png)

so。

![](img/a0b313688aaa5693b64432d8cb007a1b_2.png)

what are the algorithms that we use we，usually have a，have an objective function and in。



![](img/a0b313688aaa5693b64432d8cb007a1b_4.png)

machine learning and deep learning，that's a convention that you like to。



![](img/a0b313688aaa5693b64432d8cb007a1b_6.png)

minimize。

![](img/a0b313688aaa5693b64432d8cb007a1b_8.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_9.png)

this is equivalent sometimes maximizing。

![](img/a0b313688aaa5693b64432d8cb007a1b_11.png)

the likelihood，but here we want to minimize the loss。



![](img/a0b313688aaa5693b64432d8cb007a1b_13.png)

the thing is that this loss function is，coming from。



![](img/a0b313688aaa5693b64432d8cb007a1b_15.png)

huge data sets。

![](img/a0b313688aaa5693b64432d8cb007a1b_17.png)

the problem with loss functions that are，coming from huge data sets is that。



![](img/a0b313688aaa5693b64432d8cb007a1b_19.png)

it's gonna be very expensive to evaluate。

![](img/a0b313688aaa5693b64432d8cb007a1b_21.png)

that's why in deep learning you take it。

![](img/a0b313688aaa5693b64432d8cb007a1b_23.png)

and if you take a look at mini batch of，data you're doing your summation on a。



![](img/a0b313688aaa5693b64432d8cb007a1b_25.png)

subset of your data，it means that you always have access to。



![](img/a0b313688aaa5693b64432d8cb007a1b_27.png)

noisy estimates。

![](img/a0b313688aaa5693b64432d8cb007a1b_29.png)

of your loss function there is usually a，summation over your，entire data set but now you are doing。



![](img/a0b313688aaa5693b64432d8cb007a1b_31.png)

your summation over a mini batch over a，subset。

![](img/a0b313688aaa5693b64432d8cb007a1b_33.png)

that's why j we are using it to denote。

![](img/a0b313688aaa5693b64432d8cb007a1b_35.png)

an estimate and noisy estimate of our，objective function。



![](img/a0b313688aaa5693b64432d8cb007a1b_37.png)

and usually this noise is coming from，mini batching。



![](img/a0b313688aaa5693b64432d8cb007a1b_39.png)

we are going to do gradient descent，to optimize our loss functions。



![](img/a0b313688aaa5693b64432d8cb007a1b_41.png)

but because we are using a noisy，estimate of the loss function。



![](img/a0b313688aaa5693b64432d8cb007a1b_43.png)

that's that's why it's called the，stochastic gradient descent。



![](img/a0b313688aaa5693b64432d8cb007a1b_45.png)

always your gradients are going to be，approximate，they're going to be a stochastic they're。



![](img/a0b313688aaa5693b64432d8cb007a1b_47.png)

so this is gradient decent the。

![](img/a0b313688aaa5693b64432d8cb007a1b_49.png)

parameters of that，deep model these functions。

![](img/a0b313688aaa5693b64432d8cb007a1b_51.png)

f1 f2 f l minus 1 and fl，are parametrized by a bunch of weights。



![](img/a0b313688aaa5693b64432d8cb007a1b_53.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_54.png)

and we call those parameters we put all，of them in a list。



![](img/a0b313688aaa5693b64432d8cb007a1b_56.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_57.png)

function，[Music]，for the estimate of the objective。



![](img/a0b313688aaa5693b64432d8cb007a1b_59.png)

function that's going to be。

![](img/a0b313688aaa5693b64432d8cb007a1b_61.png)

our gradient sitting here。

![](img/a0b313688aaa5693b64432d8cb007a1b_63.png)

in the direction of the gradient。

![](img/a0b313688aaa5693b64432d8cb007a1b_65.png)

and then we keep going down basically we，are going downhill。



![](img/a0b313688aaa5693b64432d8cb007a1b_67.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_68.png)

this is the learning rate that's the，direction。

![](img/a0b313688aaa5693b64432d8cb007a1b_70.png)

and you are doing gradient decent，because of the negative sign here you，are descending。



![](img/a0b313688aaa5693b64432d8cb007a1b_72.png)

and this is stochastic because you're，using j。

![](img/a0b313688aaa5693b64432d8cb007a1b_74.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_75.png)

can i ask you a quick question about j，yes。

![](img/a0b313688aaa5693b64432d8cb007a1b_77.png)

so j is an estimate of the objective。

![](img/a0b313688aaa5693b64432d8cb007a1b_79.png)

function because，we're only training on a subset of data。



![](img/a0b313688aaa5693b64432d8cb007a1b_81.png)

is that why or，within that subset are we doing。

![](img/a0b313688aaa5693b64432d8cb007a1b_83.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_84.png)

so it's an estimate because，take a look at your data in many batches。



![](img/a0b313688aaa5693b64432d8cb007a1b_86.png)

let's say you are doing mean squared，error that's your objective。



![](img/a0b313688aaa5693b64432d8cb007a1b_88.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_89.png)

if you are doing a regression you are，doing a summation。



![](img/a0b313688aaa5693b64432d8cb007a1b_91.png)

over your entire data set，of the errors that you are making of the。



![](img/a0b313688aaa5693b64432d8cb007a1b_93.png)

square。

![](img/a0b313688aaa5693b64432d8cb007a1b_95.png)

of the errors okay，but now that's your f the summation over。



![](img/a0b313688aaa5693b64432d8cb007a1b_97.png)

your entire data set，j is gonna be a summation over a。



![](img/a0b313688aaa5693b64432d8cb007a1b_99.png)

sub-sample，of your data set maybe and that would。

![](img/a0b313688aaa5693b64432d8cb007a1b_101.png)

just be a random sub sample，exactly okay so it's going to be a。



![](img/a0b313688aaa5693b64432d8cb007a1b_103.png)

random sub sample of your data set。

![](img/a0b313688aaa5693b64432d8cb007a1b_105.png)

so per each iteration，of your stochastic gradient descent you，subsample your data set。



![](img/a0b313688aaa5693b64432d8cb007a1b_107.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_108.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_109.png)

out of those millions per。

![](img/a0b313688aaa5693b64432d8cb007a1b_111.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_112.png)

you take a sub sample of 256。

![](img/a0b313688aaa5693b64432d8cb007a1b_114.png)

that's the size of your mini batch，and then you do the。



![](img/a0b313688aaa5693b64432d8cb007a1b_116.png)

mean squared error on that subsample，on 256 data points。



![](img/a0b313688aaa5693b64432d8cb007a1b_118.png)

so that's going to be a noisy estimate。

![](img/a0b313688aaa5693b64432d8cb007a1b_120.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_121.png)

and perish iteration you subsample。

![](img/a0b313688aaa5693b64432d8cb007a1b_123.png)

a mini batch okay thank you。

![](img/a0b313688aaa5693b64432d8cb007a1b_125.png)

there is a question from brandon do you，always want to，do random batches or can you do。



![](img/a0b313688aaa5693b64432d8cb007a1b_127.png)

sequential patches。

![](img/a0b313688aaa5693b64432d8cb007a1b_129.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_130.png)

of the errors that you are making per。

![](img/a0b313688aaa5693b64432d8cb007a1b_132.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_133.png)

and why is there a summation because the，underlying assumption。



![](img/a0b313688aaa5693b64432d8cb007a1b_135.png)

is that your data are iid。

![](img/a0b313688aaa5693b64432d8cb007a1b_137.png)

independently and identically，distributed so your data are independent，from each other。



![](img/a0b313688aaa5693b64432d8cb007a1b_139.png)

and they have the same distribution i，don't know in the case of。



![](img/a0b313688aaa5693b64432d8cb007a1b_141.png)

regression you are making a normal，assumption。

![](img/a0b313688aaa5693b64432d8cb007a1b_143.png)

or a gaussian assumption all of your，data points are gaussian。



![](img/a0b313688aaa5693b64432d8cb007a1b_145.png)

they are independent because they are。

![](img/a0b313688aaa5693b64432d8cb007a1b_147.png)

independent you have a product。

![](img/a0b313688aaa5693b64432d8cb007a1b_149.png)

but then you take a log of the，likelihood。

![](img/a0b313688aaa5693b64432d8cb007a1b_151.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_152.png)

because log of product is the summation。

![](img/a0b313688aaa5693b64432d8cb007a1b_154.png)

of the log。

![](img/a0b313688aaa5693b64432d8cb007a1b_156.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_157.png)

have a summation and you want those，batches to be random。



![](img/a0b313688aaa5693b64432d8cb007a1b_159.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_160.png)

you want your samples to be random。

![](img/a0b313688aaa5693b64432d8cb007a1b_162.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_163.png)

so yeah matthew that's where i was going，with the next part of。



![](img/a0b313688aaa5693b64432d8cb007a1b_165.png)

brandon's question can you do sequential，patches，for any reason there is this idea of。



![](img/a0b313688aaa5693b64432d8cb007a1b_167.png)

curriculum learning。

![](img/a0b313688aaa5693b64432d8cb007a1b_169.png)

where you want to feed your algorithm，do。

![](img/a0b313688aaa5693b64432d8cb007a1b_171.png)

hard example mining maybe your algorithm，is really good at solving simple。



![](img/a0b313688aaa5693b64432d8cb007a1b_173.png)

examples，but then it's making mistakes on some，hard。



![](img/a0b313688aaa5693b64432d8cb007a1b_175.png)

subset of your data set that's what，people call。

![](img/a0b313688aaa5693b64432d8cb007a1b_177.png)

so that's gradient descent now that we。

![](img/a0b313688aaa5693b64432d8cb007a1b_179.png)

have an understanding of it then we are，going to do back propagation。



![](img/a0b313688aaa5693b64432d8cb007a1b_181.png)

you have a loss function j or an，approximate estimate of your loss。



![](img/a0b313688aaa5693b64432d8cb007a1b_183.png)

and let's say your theta is d。

![](img/a0b313688aaa5693b64432d8cb007a1b_185.png)

dimensional。

![](img/a0b313688aaa5693b64432d8cb007a1b_187.png)

and your loss is a single value it's，value。

![](img/a0b313688aaa5693b64432d8cb007a1b_189.png)

so your j function is going from r d to，from d dimensional stuff to。



![](img/a0b313688aaa5693b64432d8cb007a1b_191.png)

one-dimensional stuff。

![](img/a0b313688aaa5693b64432d8cb007a1b_193.png)

the cool thing about back propagation i，have a tutorial online i'm not gonna go。



![](img/a0b313688aaa5693b64432d8cb007a1b_195.png)

through back propagation in this course。

![](img/a0b313688aaa5693b64432d8cb007a1b_197.png)

is that you can take derivatives of。

![](img/a0b313688aaa5693b64432d8cb007a1b_199.png)

very easily it's very cheap to find a，derivative。

![](img/a0b313688aaa5693b64432d8cb007a1b_201.png)

it's as cheap as a forward evaluation of。

![](img/a0b313688aaa5693b64432d8cb007a1b_203.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_204.png)

so that's what the gradient is it's a。

![](img/a0b313688aaa5693b64432d8cb007a1b_206.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_207.png)

and it's one back propagation and it's，super fast。

![](img/a0b313688aaa5693b64432d8cb007a1b_209.png)

some people might say stochastic，gradient design is stupid，you're just taking a gradient of your。



![](img/a0b313688aaa5693b64432d8cb007a1b_211.png)

loss function and then you take，steps in that direction that's a stupid。



![](img/a0b313688aaa5693b64432d8cb007a1b_213.png)

algorithm，why don't you use more smart algorithms。

![](img/a0b313688aaa5693b64432d8cb007a1b_215.png)

why don't you use second-order，derivatives why don't you use。



![](img/a0b313688aaa5693b64432d8cb007a1b_217.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_218.png)

you need the hessian then and what is，the problem。

![](img/a0b313688aaa5693b64432d8cb007a1b_220.png)

the problem lies in back propagation。

![](img/a0b313688aaa5693b64432d8cb007a1b_222.png)

if you want to compute the hessian which，is a function from rd。



![](img/a0b313688aaa5693b64432d8cb007a1b_224.png)

to the matrices because the hessian is a。

![](img/a0b313688aaa5693b64432d8cb007a1b_226.png)

you need to do d iterations of back，propagation。

![](img/a0b313688aaa5693b64432d8cb007a1b_228.png)

then that's slow computing these。

![](img/a0b313688aaa5693b64432d8cb007a1b_230.png)

j functions because these are，deep and white neural networks are，expensive。



![](img/a0b313688aaa5693b64432d8cb007a1b_232.png)

let alone doing it d times and d is，usually in the order of millions of。



![](img/a0b313688aaa5693b64432d8cb007a1b_234.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_235.png)

that's why second order derivatives and，second order。



![](img/a0b313688aaa5693b64432d8cb007a1b_237.png)

algorithms are out of the picture，when you do deep learning when you do。



![](img/a0b313688aaa5693b64432d8cb007a1b_239.png)

training，so we have to live with first order。

![](img/a0b313688aaa5693b64432d8cb007a1b_241.png)

derivative，first order derivatives only gradients。

![](img/a0b313688aaa5693b64432d8cb007a1b_243.png)

no more hessians，so if that's the case。

![](img/a0b313688aaa5693b64432d8cb007a1b_245.png)

then how can we make gradient descent。

![](img/a0b313688aaa5693b64432d8cb007a1b_247.png)

there is this idea of momentum。

![](img/a0b313688aaa5693b64432d8cb007a1b_249.png)

where you say in the previous iteration。

![](img/a0b313688aaa5693b64432d8cb007a1b_251.png)

i'm going to keep that velocity，multiplied by a。

![](img/a0b313688aaa5693b64432d8cb007a1b_253.png)

number maybe i'm going to keep 90。

![](img/a0b313688aaa5693b64432d8cb007a1b_255.png)

percent of that velocity，momentum。

![](img/a0b313688aaa5693b64432d8cb007a1b_257.png)

[Music]，then add the new gradient with our。

![](img/a0b313688aaa5693b64432d8cb007a1b_259.png)

that's going to give us the updated，velocity。

![](img/a0b313688aaa5693b64432d8cb007a1b_261.png)

or the new direction and we take a step。

![](img/a0b313688aaa5693b64432d8cb007a1b_263.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_264.png)

it's as if you're rolling a ball in a，valley，and then the ball as it goes it's gonna。



![](img/a0b313688aaa5693b64432d8cb007a1b_266.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_267.png)

so this algorithm is gonna make gradient，descent faster。



![](img/a0b313688aaa5693b64432d8cb007a1b_269.png)

but it's a little bit careless because，you might。

![](img/a0b313688aaa5693b64432d8cb007a1b_271.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_272.png)

because of the momentum you're going too，fast。

![](img/a0b313688aaa5693b64432d8cb007a1b_274.png)

that's why people came up with the idea，of it's like it's actually nestroff who。

came up with the idea of nestor of。

![](img/a0b313688aaa5693b64432d8cb007a1b_276.png)

accelerated gradient the idea is that。

![](img/a0b313688aaa5693b64432d8cb007a1b_278.png)

rather than taking your derivative at。

![](img/a0b313688aaa5693b64432d8cb007a1b_280.png)

the current position，look ahead before you make your decision。



![](img/a0b313688aaa5693b64432d8cb007a1b_282.png)

what do i mean by look ahead forget。

![](img/a0b313688aaa5693b64432d8cb007a1b_284.png)

about this part，you have theta t plus one is equal to，theta t。



![](img/a0b313688aaa5693b64432d8cb007a1b_286.png)

minus gamma vt minus one。

![](img/a0b313688aaa5693b64432d8cb007a1b_288.png)

so you look ahead you put that term，here that's where you evaluate your，gradient。

and then you make your decision you。

![](img/a0b313688aaa5693b64432d8cb007a1b_290.png)

compute the gradient that's when you，make your decision to commit。

then that's going to be your gradient。

![](img/a0b313688aaa5693b64432d8cb007a1b_292.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_293.png)

this is more prudent because now you're，looking ahead。



![](img/a0b313688aaa5693b64432d8cb007a1b_295.png)

updating your gradient and then adding。

![](img/a0b313688aaa5693b64432d8cb007a1b_297.png)

and that's going to be your gradient。

![](img/a0b313688aaa5693b64432d8cb007a1b_299.png)

decent，that's going to be the great the，direction that you want to。



![](img/a0b313688aaa5693b64432d8cb007a1b_301.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_302.png)

so it's always a good idea to look ahead。

![](img/a0b313688aaa5693b64432d8cb007a1b_304.png)

and then decide rather than decide and，commit now and then。



![](img/a0b313688aaa5693b64432d8cb007a1b_306.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_307.png)

that's the intuition behind nestor of，accelerated gradient，so what i'm talking about in these。



![](img/a0b313688aaa5693b64432d8cb007a1b_309.png)

slides are，writing your compiler。

![](img/a0b313688aaa5693b64432d8cb007a1b_311.png)

which is basically most of them are。

![](img/a0b313688aaa5693b64432d8cb007a1b_313.png)

and in the deep learning literature it's，usually one of these algorithms。



![](img/a0b313688aaa5693b64432d8cb007a1b_315.png)

that they use to train their。

![](img/a0b313688aaa5693b64432d8cb007a1b_317.png)

models to train their deep models。

![](img/a0b313688aaa5693b64432d8cb007a1b_319.png)

the next algorithm is adequate，what is the problem with what we saw so，far。



![](img/a0b313688aaa5693b64432d8cb007a1b_321.png)

is that the learning rate you have to。

![](img/a0b313688aaa5693b64432d8cb007a1b_323.png)

you have to choose a learning rate and，live with it and usually。



![](img/a0b313688aaa5693b64432d8cb007a1b_325.png)

the way that you set these。

![](img/a0b313688aaa5693b64432d8cb007a1b_327.png)

parameters usually these are called，hyper parameters of our model，whatever that has to do with the。



![](img/a0b313688aaa5693b64432d8cb007a1b_329.png)

compiler。

![](img/a0b313688aaa5693b64432d8cb007a1b_331.png)

the way that you set it is usually using。

![](img/a0b313688aaa5693b64432d8cb007a1b_333.png)

your validation data set so so far we，talked about training data set。



![](img/a0b313688aaa5693b64432d8cb007a1b_335.png)

we talked about testing。

![](img/a0b313688aaa5693b64432d8cb007a1b_337.png)

and then the hyper parameters are going，to be。

![](img/a0b313688aaa5693b64432d8cb007a1b_339.png)

set using a validation。

![](img/a0b313688aaa5693b64432d8cb007a1b_341.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_342.png)

i don't know metric your evaluation。

![](img/a0b313688aaa5693b64432d8cb007a1b_344.png)

metric which could be your accuracy，and choose whatever learning rate that's。



![](img/a0b313688aaa5693b64432d8cb007a1b_346.png)

going to give you the best，accuracy on the validation data set and。



![](img/a0b313688aaa5693b64432d8cb007a1b_348.png)

once you do that the，next step is testing and then the next，step is。



![](img/a0b313688aaa5693b64432d8cb007a1b_350.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_351.png)

so the way that you set these lambdas is。

![](img/a0b313688aaa5693b64432d8cb007a1b_353.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_354.png)

is that you're trying for。

![](img/a0b313688aaa5693b64432d8cb007a1b_356.png)

multiple times one algorithm is grid，search。

![](img/a0b313688aaa5693b64432d8cb007a1b_358.png)

you put a grid on this learning rate，and then find the best one that's the。



![](img/a0b313688aaa5693b64432d8cb007a1b_360.png)

fastest and that's giving you the most，accurate result。



![](img/a0b313688aaa5693b64432d8cb007a1b_362.png)

and as you can see this is not cheap。

![](img/a0b313688aaa5693b64432d8cb007a1b_364.png)

because now you have to train your model。

![](img/a0b313688aaa5693b64432d8cb007a1b_366.png)

thousands of times to find what is the。

![](img/a0b313688aaa5693b64432d8cb007a1b_368.png)

it would be good if you could make。

![](img/a0b313688aaa5693b64432d8cb007a1b_370.png)

the learning rates adaptive the rest of，the methods that i'm gonna cover are。



![](img/a0b313688aaa5693b64432d8cb007a1b_372.png)

trying to make，eta adaptive the learning rate to be。



![](img/a0b313688aaa5693b64432d8cb007a1b_374.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_375.png)

for add a graph this is just our，gradient let's call it g。



![](img/a0b313688aaa5693b64432d8cb007a1b_377.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_378.png)

the idea is that this is the same，gradient dc that you have。



![](img/a0b313688aaa5693b64432d8cb007a1b_380.png)

here it's theta t plus 1 is equal to，theta t。

![](img/a0b313688aaa5693b64432d8cb007a1b_382.png)

minus our eta is now adaptive。

![](img/a0b313688aaa5693b64432d8cb007a1b_384.png)

times the gradient but how do you make。

![](img/a0b313688aaa5693b64432d8cb007a1b_386.png)

you take a running average it's not。

![](img/a0b313688aaa5693b64432d8cb007a1b_388.png)

actually a running average it's the，average，of the gradients multiplied by each。



![](img/a0b313688aaa5693b64432d8cb007a1b_390.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_391.png)

and the entries of that matrix are from，time 1，up until the current time。

that could be a matrix we don't care。

![](img/a0b313688aaa5693b64432d8cb007a1b_393.png)

about the matrix，we care about the diagonal of that。



![](img/a0b313688aaa5693b64432d8cb007a1b_395.png)

matrix over time，and these are just gradients per each，time。



![](img/a0b313688aaa5693b64432d8cb007a1b_397.png)

and then we are multiplying them，pointwise。

![](img/a0b313688aaa5693b64432d8cb007a1b_399.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_400.png)

these are vectors as you can see the，gradient is a vector in。



![](img/a0b313688aaa5693b64432d8cb007a1b_402.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_403.png)

there are various ways of defining the，product。

![](img/a0b313688aaa5693b64432d8cb007a1b_405.png)

here the product is every entry squared，that's what we're doing here there's a。



![](img/a0b313688aaa5693b64432d8cb007a1b_407.png)

square term，in g that's why you do。

![](img/a0b313688aaa5693b64432d8cb007a1b_409.png)

[Music]。

![](img/a0b313688aaa5693b64432d8cb007a1b_411.png)

the square root of that is quarter，that is trying to give us an adaptive。



![](img/a0b313688aaa5693b64432d8cb007a1b_413.png)

and it's adapting to the previous。

![](img/a0b313688aaa5693b64432d8cb007a1b_415.png)

if i were if we were in class i would。

![](img/a0b313688aaa5693b64432d8cb007a1b_417.png)

ask what is the problem with this method，and can anybody answer what is the。



![](img/a0b313688aaa5693b64432d8cb007a1b_419.png)

problem with this method。

![](img/a0b313688aaa5693b64432d8cb007a1b_421.png)

yeah the question is we still set an，initial，learning rate that's correct you set an，initial。



![](img/a0b313688aaa5693b64432d8cb007a1b_423.png)

eta but that's gonna adapt。

![](img/a0b313688aaa5693b64432d8cb007a1b_425.png)

as you go along the method it's gonna。

![](img/a0b313688aaa5693b64432d8cb007a1b_427.png)

so this method is less sensitive to，learning rate。

![](img/a0b313688aaa5693b64432d8cb007a1b_429.png)

compared to gradient descent，but that's correct you still need to set。



![](img/a0b313688aaa5693b64432d8cb007a1b_431.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_432.png)

what is the other problem we'd have some，problems like numerically。



![](img/a0b313688aaa5693b64432d8cb007a1b_434.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_435.png)

that's a good point that's why you have，this epsilon term here。



![](img/a0b313688aaa5693b64432d8cb007a1b_437.png)

and this epsilon is usually said to be，10 to the power negative eight。



![](img/a0b313688aaa5693b64432d8cb007a1b_439.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_440.png)

so any other problems that you see，is it less efficient as we continue to。



![](img/a0b313688aaa5693b64432d8cb007a1b_442.png)

learn and learn because the sum，[Music]，over all of the taus gets longer and。



![](img/a0b313688aaa5693b64432d8cb007a1b_444.png)

longer that's a good point。

![](img/a0b313688aaa5693b64432d8cb007a1b_446.png)

so g squared is a positive number，and you keep adding positive numbers。



![](img/a0b313688aaa5693b64432d8cb007a1b_448.png)

together。

![](img/a0b313688aaa5693b64432d8cb007a1b_450.png)

and towards the end of the end of the，training。

![](img/a0b313688aaa5693b64432d8cb007a1b_452.png)

this g is gonna be very huge。

![](img/a0b313688aaa5693b64432d8cb007a1b_454.png)

it means that your learning rate is，going to get smaller and smaller。

and in the end you are not optimizing at。

![](img/a0b313688aaa5693b64432d8cb007a1b_456.png)

all，basically that term is going to be zero。

![](img/a0b313688aaa5693b64432d8cb007a1b_458.png)

and then you're going to be stuck，so the algorithm is going to stop，prematurely。



![](img/a0b313688aaa5693b64432d8cb007a1b_460.png)

so what can we do to fix it，you can keep a running average rather。



![](img/a0b313688aaa5693b64432d8cb007a1b_462.png)

than，averaging over from time zero up until，now。

![](img/a0b313688aaa5693b64432d8cb007a1b_464.png)

you can sum the most recent gradient。

![](img/a0b313688aaa5693b64432d8cb007a1b_466.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_467.png)

and i'm gonna say why it's called at a。

![](img/a0b313688aaa5693b64432d8cb007a1b_469.png)

delta in a。

![](img/a0b313688aaa5693b64432d8cb007a1b_471.png)

but add a delta is going to do a running，average。

![](img/a0b313688aaa5693b64432d8cb007a1b_473.png)

of these gradient squares so if you，think about it you're doing a running。



![](img/a0b313688aaa5693b64432d8cb007a1b_475.png)

average，you keep lambda sorry gamma。

![](img/a0b313688aaa5693b64432d8cb007a1b_477.png)

of the previous average and you add your。

![](img/a0b313688aaa5693b64432d8cb007a1b_479.png)

gradient that's going to give you the。

![](img/a0b313688aaa5693b64432d8cb007a1b_481.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_482.png)

say。

![](img/a0b313688aaa5693b64432d8cb007a1b_484.png)

this is just defining what is delta，delta t。

![](img/a0b313688aaa5693b64432d8cb007a1b_486.png)

is theta t plus 1 minus theta t that's，the definition。



![](img/a0b313688aaa5693b64432d8cb007a1b_488.png)

and then you set your delta t which is。

![](img/a0b313688aaa5693b64432d8cb007a1b_490.png)

this term here，to be eta divided by your running，average。



![](img/a0b313688aaa5693b64432d8cb007a1b_492.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_493.png)

the problem is that with other delta the。

![](img/a0b313688aaa5693b64432d8cb007a1b_495.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_496.png)

this has a different unit compared to，eta。

![](img/a0b313688aaa5693b64432d8cb007a1b_498.png)

you keep a running average of your delta。

![](img/a0b313688aaa5693b64432d8cb007a1b_500.png)

and then the update of your delta t is，going to be that running average。



![](img/a0b313688aaa5693b64432d8cb007a1b_502.png)

root mean squared error divided by the，root mean squared error of gt。



![](img/a0b313688aaa5693b64432d8cb007a1b_504.png)

times gt this term here is just a root。

![](img/a0b313688aaa5693b64432d8cb007a1b_506.png)

mean squared error，and that's going to be your delta t and，that's going to be adaptive。



![](img/a0b313688aaa5693b64432d8cb007a1b_508.png)

at the delta and the cool thing is that，all。

![](img/a0b313688aaa5693b64432d8cb007a1b_510.png)

eta is gone。

![](img/a0b313688aaa5693b64432d8cb007a1b_512.png)

if any of you want to leave you are more。

![](img/a0b313688aaa5693b64432d8cb007a1b_514.png)

than welcome to leave and if you have，questions。

![](img/a0b313688aaa5693b64432d8cb007a1b_516.png)

you can ask questions you mentioned。

![](img/a0b313688aaa5693b64432d8cb007a1b_518.png)

a tutorial about uh back propagation，um and i'm interested in that will that。



![](img/a0b313688aaa5693b64432d8cb007a1b_520.png)

be linked on the。

![](img/a0b313688aaa5693b64432d8cb007a1b_522.png)

um online，i can send you the link to that tutorial，to back propagation。



![](img/a0b313688aaa5693b64432d8cb007a1b_524.png)

um i'm sorry i think i missed it when。

![](img/a0b313688aaa5693b64432d8cb007a1b_526.png)

you said it but what's the target，looking operator。



![](img/a0b313688aaa5693b64432d8cb007a1b_528.png)

in ad grid or adagrad。

![](img/a0b313688aaa5693b64432d8cb007a1b_530.png)

say the gang what is the target，like operator in ada grad the two。



![](img/a0b313688aaa5693b64432d8cb007a1b_532.png)

the circle with a dot inside what does，that denote。



![](img/a0b313688aaa5693b64432d8cb007a1b_534.png)

this dot inside is element-wise products，okay so it's oh it's just a dot product。



![](img/a0b313688aaa5693b64432d8cb007a1b_536.png)

yeah it's not a dot product it's。

![](img/a0b313688aaa5693b64432d8cb007a1b_538.png)

so you have two vectors here and here。

![](img/a0b313688aaa5693b64432d8cb007a1b_540.png)

and you are multiplying them one by one，the output is still a vector it's not a，number。



![](img/a0b313688aaa5693b64432d8cb007a1b_542.png)

oh the output of that something oh i see，what you're saying。



![](img/a0b313688aaa5693b64432d8cb007a1b_544.png)

oh yeah yes you take it okay yeah i got，it。

![](img/a0b313688aaa5693b64432d8cb007a1b_546.png)

yes so blake sent us a link and thank，you it's the hadamard，product so you're doing point-wise。



![](img/a0b313688aaa5693b64432d8cb007a1b_548.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_549.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_550.png)

so these are element-wise squares，element-wise products。



![](img/a0b313688aaa5693b64432d8cb007a1b_552.png)

if you have x1 x2 x3 up until xn。

![](img/a0b313688aaa5693b64432d8cb007a1b_554.png)

and you have y one y two up until y n。

![](img/a0b313688aaa5693b64432d8cb007a1b_556.png)

you are doing x one times y one x two，times y two and in the end。



![](img/a0b313688aaa5693b64432d8cb007a1b_558.png)

x n times y n any other questions so，there is a question。



![](img/a0b313688aaa5693b64432d8cb007a1b_560.png)

in the adap delta method what is g，squared。

![](img/a0b313688aaa5693b64432d8cb007a1b_562.png)

so g squared is exactly what you see，here。

![](img/a0b313688aaa5693b64432d8cb007a1b_564.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_565.png)

if you have x1 x2 up until xn that's。

![](img/a0b313688aaa5693b64432d8cb007a1b_567.png)

your vector，then it's going to be x1 squared x2。

![](img/a0b313688aaa5693b64432d8cb007a1b_569.png)

squared up until xn squared，the output is a vector still so。



![](img/a0b313688aaa5693b64432d8cb007a1b_571.png)

e is your expectation。

![](img/a0b313688aaa5693b64432d8cb007a1b_573.png)

is the average is the running average。

![](img/a0b313688aaa5693b64432d8cb007a1b_575.png)

and it's just a notation，the running average of g squares at time。



![](img/a0b313688aaa5693b64432d8cb007a1b_577.png)

t，is equal to gamma running average of g。

![](img/a0b313688aaa5693b64432d8cb007a1b_579.png)

squared at time t minus one。

![](img/a0b313688aaa5693b64432d8cb007a1b_581.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_582.png)