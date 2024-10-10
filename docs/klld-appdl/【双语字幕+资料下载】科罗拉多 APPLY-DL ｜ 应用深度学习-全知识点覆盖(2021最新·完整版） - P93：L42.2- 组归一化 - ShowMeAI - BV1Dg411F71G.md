# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P93：L42.2- 组归一化 - ShowMeAI - BV1Dg411F71G

[Music]，we learned about batch normalization，very early in the semester there are。

other types of normalizations，putting，group normalization here as the last。



![](img/83ba17850318b0e304d7ea01fdccaf58_1.png)

slide for a video，that。

![](img/83ba17850318b0e304d7ea01fdccaf58_3.png)

yes it is really powerful and it's going，to give you a state of the art results。

for as long as your batch size is，reasonable，at least 32 images you're processing 32。

images at a time，but then when you go to problems。

![](img/83ba17850318b0e304d7ea01fdccaf58_5.png)

such as object detection segmentation。

![](img/83ba17850318b0e304d7ea01fdccaf58_7.png)

or when you go to videos usually your，batch size is around，two you cannot process more than two。



![](img/83ba17850318b0e304d7ea01fdccaf58_9.png)

videos it's not gonna，fit on your gpu your batch size is small。



![](img/83ba17850318b0e304d7ea01fdccaf58_11.png)

either because it doesn't fit on your，make，if you remember when we were doing，object detection。

we are processing two images at a time。

![](img/83ba17850318b0e304d7ea01fdccaf58_13.png)

but in each image，you have multiple bounding box uh。



![](img/83ba17850318b0e304d7ea01fdccaf58_15.png)

proposal purpose regions it was our，choice，but sometimes it is not our choice we。

are limited by the constraints，of the memory in our gpu etc so。



![](img/83ba17850318b0e304d7ea01fdccaf58_17.png)

small，for instance when we were doing object，detection we were doing transfer。



![](img/83ba17850318b0e304d7ea01fdccaf58_19.png)

learning，we trained our network on imagenet，we had the batch norm on so it was，training。



![](img/83ba17850318b0e304d7ea01fdccaf58_21.png)

those gammas and sigmas they shoot，unscathed in your batch node。

we're training them but then when you。

![](img/83ba17850318b0e304d7ea01fdccaf58_23.png)

were doing transfer learning to your，object detection，you were fixing those parameters you。



![](img/83ba17850318b0e304d7ea01fdccaf58_25.png)

were freezing them，when you were doing transfer learning so，those two parameters are not going to be。



![](img/83ba17850318b0e304d7ea01fdccaf58_27.png)

learned anymore，why because your batch sizes are small，because your data set is。



![](img/83ba17850318b0e304d7ea01fdccaf58_29.png)

smaller et cetera so you are freezing，those parameters and there is no reason，that those shift。

and scale that you learned on imagenet。

![](img/83ba17850318b0e304d7ea01fdccaf58_31.png)

is going to be the correct ones for，pascal voc。

![](img/83ba17850318b0e304d7ea01fdccaf58_33.png)

or microsoft cocoa okay it would be，good to have a normalization method，that's batch independent。

those statistics that you obtain are，independent of your batches。



![](img/83ba17850318b0e304d7ea01fdccaf58_35.png)

group normalization is one such method，what is the effect。



![](img/83ba17850318b0e304d7ea01fdccaf58_37.png)

if you have 32 batches 32 images，per each worker it could be per each。

gpu so each worker here is a gpu if you。

![](img/83ba17850318b0e304d7ea01fdccaf58_39.png)

have 32 for your batch size，you're getting very good error rates。



![](img/83ba17850318b0e304d7ea01fdccaf58_41.png)

and this is for imagenet and this is，just an experiment to show。



![](img/83ba17850318b0e304d7ea01fdccaf58_43.png)

size，and let's track the blue curve if you，use 16。

![](img/83ba17850318b0e304d7ea01fdccaf58_45.png)

for your bag size you're still not bad。

![](img/83ba17850318b0e304d7ea01fdccaf58_47.png)

but as you go to lower path sizes or，smaller bite sizes。



![](img/83ba17850318b0e304d7ea01fdccaf58_49.png)

your error rate is gonna go up，significantly okay if you process two。



![](img/83ba17850318b0e304d7ea01fdccaf58_51.png)

images period gpu then in the end，your error rate is around 35 percent，compared to 24 percent。

but then group normalization is not that，sensitive to，the batch size and but if your batch is。

big enough batch normalization is still，better than group normalization。



![](img/83ba17850318b0e304d7ea01fdccaf58_53.png)

but what is this group normalization and，how does it compare to the rest of the，normalizations。



![](img/83ba17850318b0e304d7ea01fdccaf58_55.png)

that exist in the literature this is a，very good plot，each image is gonna have a height and a。

bit dimension，that's our z axis in this plot it's，going to have a。



![](img/83ba17850318b0e304d7ea01fdccaf58_57.png)

c dimension the channel and it's going，to have a bash dimension。



![](img/83ba17850318b0e304d7ea01fdccaf58_59.png)

what batch normalization does it's going，to，compute the averages the status，statistics mean。

and standard deviation by。

![](img/83ba17850318b0e304d7ea01fdccaf58_61.png)

looping over the bash dimension and the，height and the。



![](img/83ba17850318b0e304d7ea01fdccaf58_63.png)

dimension so the resolution so i noticed，to be。

![](img/83ba17850318b0e304d7ea01fdccaf58_65.png)

one and you are not running into trouble，in your codes，it's because there is still a height and。

a width dimension。

![](img/83ba17850318b0e304d7ea01fdccaf58_67.png)

that you are computing your statistics，from otherwise。



![](img/83ba17850318b0e304d7ea01fdccaf58_69.png)

the variance of if you didn't have this，height and width，the variance of a single batch is going。

to be zero，and you're dividing by zero in your，batch normalization and you would。



![](img/83ba17850318b0e304d7ea01fdccaf58_71.png)

run into a lot of trouble so yes you can，have batch size of。



![](img/83ba17850318b0e304d7ea01fdccaf58_73.png)

one for images if you have a third，dimension the height and width and the。

beat so that's batch normalization，there is layer normalization this one is，not going to。

be sensitive to your batch size because。

![](img/83ba17850318b0e304d7ea01fdccaf58_75.png)

you are computing your statistics，across the channel dimension and the。



![](img/83ba17850318b0e304d7ea01fdccaf58_77.png)

height and the width dimension，you compute the statistics and then you，divide you。



![](img/83ba17850318b0e304d7ea01fdccaf58_79.png)

subtract the mean from each pixel in，this image，and then divide by the standard。



![](img/83ba17850318b0e304d7ea01fdccaf58_81.png)

deviation that's going to be layer，normalization but，layer normalization is not going to give。



![](img/83ba17850318b0e304d7ea01fdccaf58_83.png)

you good performance for images it is，usually，used for recurrent run letters there is。

instance normalization，this is when your statistics are coming。



![](img/83ba17850318b0e304d7ea01fdccaf58_85.png)

from batch size being one，so from one instance this is exactly，what what they just described here。



![](img/83ba17850318b0e304d7ea01fdccaf58_87.png)

because you have a third dimension the，height and the width the dimension of，the pixels。

you can compute your mean and a standard，deviation without this height and width，you're into drop。



![](img/83ba17850318b0e304d7ea01fdccaf58_89.png)

and what is group normalization it's，something between。



![](img/83ba17850318b0e304d7ea01fdccaf58_91.png)

and actually before i go there the，applications of instant normalization。



![](img/83ba17850318b0e304d7ea01fdccaf58_93.png)

is for generative others or neural，networks，we are probably going to cover them in，the next semester。



![](img/83ba17850318b0e304d7ea01fdccaf58_95.png)

so that's a technique for gas and then，there is group normalization。



![](img/83ba17850318b0e304d7ea01fdccaf58_97.png)

it is something between layer nor，and instance norm you create a bunch of。



![](img/83ba17850318b0e304d7ea01fdccaf58_99.png)

groups，per your channel dimension for instance，in this case you have two groups。



![](img/83ba17850318b0e304d7ea01fdccaf58_101.png)

and each one has three members per the，channel dimension。



![](img/83ba17850318b0e304d7ea01fdccaf58_103.png)

and then you compute your statistics，here that's grouped by，group normalization and it seems to be。

effective but。

![](img/83ba17850318b0e304d7ea01fdccaf58_105.png)

let's go through batch normalization and。

![](img/83ba17850318b0e304d7ea01fdccaf58_107.png)

master，perspective i'm gonna go through it，really fast because these we covered。



![](img/83ba17850318b0e304d7ea01fdccaf58_109.png)

you want to normalize your x i your，input。

![](img/83ba17850318b0e304d7ea01fdccaf58_111.png)

so you're gonna subtract the mean and，you're gonna divide by the standard。

deviation and this is gonna happen。

![](img/83ba17850318b0e304d7ea01fdccaf58_113.png)

regardless of the method this is your，normalization scheme。



![](img/83ba17850318b0e304d7ea01fdccaf58_115.png)

x is your feature what is i，i is a multi-dimensional index。



![](img/83ba17850318b0e304d7ea01fdccaf58_117.png)

and it's going to index the n dimension，the batch dimension，it's going to index the channel。



![](img/83ba17850318b0e304d7ea01fdccaf58_119.png)

the b，and n is your batch axis is the channel，axis。



![](img/83ba17850318b0e304d7ea01fdccaf58_121.png)

h is the height axis and w is the v，taxes。

![](img/83ba17850318b0e304d7ea01fdccaf58_123.png)

so you have multiple axis here you，compute the mean and a standard，deviation。

for all of these methods you compute the。

![](img/83ba17850318b0e304d7ea01fdccaf58_125.png)

mean over，a subset of these points per each。

![](img/83ba17850318b0e304d7ea01fdccaf58_127.png)

pixel and you compute the standard，deviation the only difference。



![](img/83ba17850318b0e304d7ea01fdccaf58_129.png)

between these methods is s i okay，use。

![](img/83ba17850318b0e304d7ea01fdccaf58_131.png)

to compute your mean and a standard，deviation and what is m。



![](img/83ba17850318b0e304d7ea01fdccaf58_133.png)

m is the size of its i m is the size of，this set，so what is s i for batch normalization。



![](img/83ba17850318b0e304d7ea01fdccaf58_135.png)

your k，it's the set of all of the k's and your，k is going to be a。



![](img/83ba17850318b0e304d7ea01fdccaf58_137.png)

similar vector to i to your index it's，going to have k。



![](img/83ba17850318b0e304d7ea01fdccaf58_139.png)

n k c k h k w，and then you are fixing the k。

![](img/83ba17850318b0e304d7ea01fdccaf58_141.png)

c dimension k c should be equal to i c，and the rest of them are free。



![](img/83ba17850318b0e304d7ea01fdccaf58_143.png)

so given ic you can compute this uh。

![](img/83ba17850318b0e304d7ea01fdccaf58_145.png)

s i set and that's going to give your，batch node，what does this mean you're computing。

your statistics。

![](img/83ba17850318b0e304d7ea01fdccaf58_147.png)

mean and sigma over all of the other，dimensions。

![](img/83ba17850318b0e304d7ea01fdccaf58_149.png)

other than c you're computing a launch n。

![](img/83ba17850318b0e304d7ea01fdccaf58_151.png)

h and w so that's exactly，what is being denoted here in this case，ic was one。



![](img/83ba17850318b0e304d7ea01fdccaf58_153.png)

but your ic could be this is slice，and then you are doing your statistics。

you are computing your statistics on，this，index so that's patch norm layer norm。



![](img/83ba17850318b0e304d7ea01fdccaf58_155.png)

the set is different，s i is going to be different now you are，fixing your i。



![](img/83ba17850318b0e304d7ea01fdccaf58_157.png)

n dimension it's better to think of it，this way that now you are computing your，statistics。



![](img/83ba17850318b0e304d7ea01fdccaf58_159.png)

over the channel dimension of the height，and the width damage，so these two dimensions these three。



![](img/83ba17850318b0e304d7ea01fdccaf58_161.png)

dimensions for instance norm you're，fixing，two indices and then you're computing。



![](img/83ba17850318b0e304d7ea01fdccaf58_163.png)

your statistics on the rest so you're，completing your statistics over。



![](img/83ba17850318b0e304d7ea01fdccaf58_165.png)

your pixels only and then for all of，these methods，including group normalization you're。



![](img/83ba17850318b0e304d7ea01fdccaf58_167.png)

going to do a shift and scale，these are going to be some additional。



![](img/83ba17850318b0e304d7ea01fdccaf58_169.png)

parameters gamma and beta，and these are per channel so these are，vector。



![](img/83ba17850318b0e304d7ea01fdccaf58_171.png)

that have the dimension of your channel，of the channel dimension。



![](img/83ba17850318b0e304d7ea01fdccaf58_173.png)

and we know why we add them because，after you subtract the mean and divide，by the standard deviation。



![](img/83ba17850318b0e304d7ea01fdccaf58_175.png)

then everything is going to be mean zero，and they're gonna have a standard，deviation of one。



![](img/83ba17850318b0e304d7ea01fdccaf58_177.png)

so you want to add some parameters to be，learned for group norm your si is going，to change。



![](img/83ba17850318b0e304d7ea01fdccaf58_179.png)

you fix the batch dimension so you are，not doing any。



![](img/83ba17850318b0e304d7ea01fdccaf58_181.png)

statistics along your batch dimension，but then you are turning your。



![](img/83ba17850318b0e304d7ea01fdccaf58_183.png)

kc and ic and you are doing it per group，g is going to be the number of groups。



![](img/83ba17850318b0e304d7ea01fdccaf58_185.png)

that you have for instance it could be，32 groups。

![](img/83ba17850318b0e304d7ea01fdccaf58_187.png)

in our case it was two group c over g is，going to give you the number of channels。



![](img/83ba17850318b0e304d7ea01fdccaf58_189.png)

per group in this case you have three，channels，per group and you have two groups and。

this is just telling you that。

![](img/83ba17850318b0e304d7ea01fdccaf58_191.png)

i'm doing my summation over all of。

![](img/83ba17850318b0e304d7ea01fdccaf58_193.png)

casey's that satisfy this property i，have within my groups，and it's better to think about it this。



![](img/83ba17850318b0e304d7ea01fdccaf58_195.png)

way that you're doing your summation，over the，height and the width dimension as well，as a group。



![](img/83ba17850318b0e304d7ea01fdccaf58_197.png)

of c over g channel a group of three，channels。

![](img/83ba17850318b0e304d7ea01fdccaf58_199.png)

in the example level how do you code it，in terms of law。



![](img/83ba17850318b0e304d7ea01fdccaf58_201.png)

you can have a similar code in pytorch，or mxnet，or chainer etc you need to give it the。



![](img/83ba17850318b0e304d7ea01fdccaf58_203.png)

gamma and beta these are the ship，and scale epsilon is just small number。



![](img/83ba17850318b0e304d7ea01fdccaf58_205.png)

because we don't want to divide by zero，and。

![](img/83ba17850318b0e304d7ea01fdccaf58_207.png)

you compute your mean and，command。

![](img/83ba17850318b0e304d7ea01fdccaf58_209.png)

and then you're gonna tell it which，dimension you're computing those。

statistics from and you reshape it and。

![](img/83ba17850318b0e304d7ea01fdccaf58_211.png)

then multiply gamma and alpha，so that's how you're going to implement。



![](img/83ba17850318b0e304d7ea01fdccaf58_213.png)

that and it's just a matter of reshaping，your inputs basically you're dividing。

your channel dimension。

![](img/83ba17850318b0e304d7ea01fdccaf58_215.png)

and then you're dividing it into a g。

![](img/83ba17850318b0e304d7ea01fdccaf58_217.png)

and c divided by g so you're adding one，dimension to your tensor。



![](img/83ba17850318b0e304d7ea01fdccaf58_219.png)

and then you do your averaging over this，dimension c over g，h and w and then you reshape it back so。



![](img/83ba17850318b0e304d7ea01fdccaf58_221.png)

what is the effect，if you apply it on imagenet this is bash。



![](img/83ba17850318b0e304d7ea01fdccaf58_223.png)

norm this is layer norm，this is instance norm this is group norm。

and each one of them is going to lose。

![](img/83ba17850318b0e304d7ea01fdccaf58_225.png)

some accuracy for you it's going to give，you a higher error。



![](img/83ba17850318b0e304d7ea01fdccaf58_227.png)

instance norm is the worst layer norm is，still not that great but group norm is。



![](img/83ba17850318b0e304d7ea01fdccaf58_229.png)

not losing that much，it's losing only 0。5 percent。

![](img/83ba17850318b0e304d7ea01fdccaf58_231.png)

but as you change your batch size from，32。

![](img/83ba17850318b0e304d7ea01fdccaf58_233.png)

to 16 to 8 then you're gonna see the，advantage，from group norm for smaller batches you。

can apply to detection，and segmentation so that was a，classification task。

this is the detection and segmentation，now the cool thing is that for。

cocoa you can let this be time gamma be，learned，from cocoa dataset previously if you。

were using batch norm，you have to fix you have to freeze gamma。

and beta now you can let them be learned，and then you can apply that to video。

data and it's a video classification，task and kinetics data，and then you can process smaller number。

of clips，per gpu if you use batch node you're，going to have a significant。

drop in your performance but if you use，group norm for these small clip sizes。

these are basically your back sizes，these two curves are on top of each，other。

more or less and the variations that，you're seeing is because of。

noise in the training any questions so，we learned two powerful techniques today。

one was the non-local operations，non-local blocks，and the other one is that it's not。

always the case that batchmore，is the best method that's gonna depend，on your。

network and your batch sizes if your，device challenges are small。

and you're dealing with images and your，task is probably detection segmentation，or video。

perhaps going with norm is a better，choice compared to passion，and just uh i guess maybe clarify。

that's normal all or sorry uh larger，batches are always，advantageous just because it uh。

allows more parallelization so you can，speed up training，is that correct yes as long as you can。

put them on your gpu，yeah or gpu yes okay because you can，parallelize them and process them。

they can do data parallelism that's one，reason the other reason is。

probably the gradient estimates that，you're gonna get is gonna be more，accurate。

but at the same time it's a trade-off，it's always a trade-off if your batch，size is too big。

you are reducing a lot of the noise and，we know that these noises are。

usually useful for your neural network，to regularize，because it's not always the case that。

you want to push your，loss function to its global minima，you want to find good local minima。

that's going to help your network，generalize，on your test data and usually the noise。

the regularization that's，introduced because of the noise in your，batches and in your gradients。

they're helpful but sometimes they can，hurt if the batch serve is very small。

they can start to hurt and this can，happen because of your video。

your videos are going to be a bunch of，images，and we know that that's just more memory。

because these are bigger，they consume bigger chunks of your，memory per。

each data point maybe the entire dataset，is smaller，but each data point is heavy in terms of。

its memory，consumption so next section we are going，to do 3d data these are going to be。

point cloud data，have，any structure so far our data has a，structure there's a batch dimension a。

channel dimension height and width，dimension and we can put that。

on a grid the point cloud they're not，gonna have any，grid it's just gonna be a set up a bunch。

of points，in your space and i think with that i'm，gonna finish。

today's session i'm gonna be around if。