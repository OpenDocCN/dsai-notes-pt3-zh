# P86：L40.1- Focal Loss - ShowMeAI - BV1Dg411F71G

let's get started then so let's see what，we have been doing，so far uh we started with one stage。

detectors，and then the first paper that we covered，was overfeed。

it was almost around the same time that，uh alexnet came out for classification。

so even from that time people were，thinking about object detection，and then after a while we saw。

yellow you only look once and the idea，was that you want，to divide your image into s by s grid。

and each grid is going to be predicting，a box，and a confidence and at the same time a。

class probability map，and in the end it's just a matter of，multiplying these two to give us the。

boxes，after non-maximum separation but then it，was a matter of training it。

and there there were some issues，that we needed to take into account one。

of them was properly weighting these，loss functions all of them are，regression loss there is no。

classification loss，and then also we have to be careful with，the height and the width。

of our boxes because these were with，respect to the entire image，is height and width that was yellow。

then ssd came along and said you can，actually look at multiple。

feature maps then it's going to give you，more boxes，to work with you can also change your。

loss function，and actually put a classification loss，in the form of soft max。

and then again you have to properly，weight these two loss functions。

and these are the only changes compared，to yellow，and they got very good results much。

better than faster our cnn and yellow，both in terms of speed and then uh，accuracy。

mean average precision then you alone，nine thousand，came along this is gonna be yolo version。

two you're gonna hear about version 2，also，and then they started competing with ssd。

and they said if we，include the ideas that are included in，faster or cnn。

and ssd actually by the way there was，another idea in，ssd and that was anchor boxes similar to。

faster or sienna，if you include anchor boxes you can，improve their the mean。

average precision but then they said，actually if you choose your anchor boxes。

according to some clustering algorithm，from，your training data and there is nothing。

wrong with doing that because，you know your boxes from your training，data so you're not cheating。

you can actually use that and then，that's going to give you much better。

performance and then you can get rid of，the anchor boxes，and use these priors and then there were。

some other modifications like using，batch norm，using pass through layer which is going，to combine。

two feature maps together so it's just a，matter of reshaping one of the feature，maps from an。

earlier layer and then concatenating it，with the，next layers feature map and use that for，detection。

so this is up until this point is gonna，give you，your low version 2 again and one other。

modification is that now your only your，network is only responsible。

for predicting small modifications，to some boxes that are coming out of，your clustering。

so these are small modifications，compared to，a box the coordinates of the box this is，yolo version 2。

and then what makes it yellow 9000 is，that you can actually predict 9000，classes，of them。

is for classification and that's，imagenet data，and that has fine details for its labels。

and the other one is coco which has big，categories like cat dog。

car airplane etc and then in imagenet，you have，persian cat tabby cat by biplane。

jet etc so one idea is to combine these，two data sets，the other one is to use hierarchical。

classification，basically you start with an object，then you go to the animal branch and，then animal。

being the cut in the dark category and，then，you keep building up until you reach the。

leaf for instance you're going to reach，the probability of it being a。

norfolk terrier condition on it being a，terrier，and then this is going to give you the。

entire probability for that，note in your tree and then the rest of，it is just a matter of training。

you jointly train your classification，and detection algorithm。

on this date any question so far it was，just a quick recap，of what we covered for one stage。

detectors and it's supposed to give us，the big picture，okay so i'm gonna introduce a new loss。

function。

![](img/96181912cdb98e5d08d9369d267826d4_1.png)

in this paper for call loss for dense，object detection。



![](img/96181912cdb98e5d08d9369d267826d4_3.png)

and then we're to see why you need a new，loss function。



![](img/96181912cdb98e5d08d9369d267826d4_5.png)

and why is it necessary so there is，going to be a huge imbalance。



![](img/96181912cdb98e5d08d9369d267826d4_7.png)

in your trending data when it comes to，classification，many of the boxes are very easy to。



![](img/96181912cdb98e5d08d9369d267826d4_9.png)

classify，they either correspond to big objects，in your image which are easy to classify。

or most of them are gonna be background。

![](img/96181912cdb98e5d08d9369d267826d4_11.png)

therefore you're gonna have a class，imbalance when it comes to training。



![](img/96181912cdb98e5d08d9369d267826d4_13.png)

so this paper says the main problem。

![](img/96181912cdb98e5d08d9369d267826d4_15.png)

with one stage detectors lagging，behind two stage detectors is exactly。



![](img/96181912cdb98e5d08d9369d267826d4_17.png)

because of this class impala，if we can fix that we are going to be，able to get good accuracy。



![](img/96181912cdb98e5d08d9369d267826d4_19.png)

out of us out of our classifier so one，idea to take care of class in balance。

and for now let's assume you have two。

![](img/96181912cdb98e5d08d9369d267826d4_21.png)

classes plus one and minus one，is that you can have an alpha，coefficient。



![](img/96181912cdb98e5d08d9369d267826d4_23.png)

it's going to be alpha and one minus，alpha in your loss and，alpha for instance could be the ratio of。

the ones，and the other one is the ratio of，negative ones。



![](img/96181912cdb98e5d08d9369d267826d4_25.png)

in your data set this is how you're，gonna define alpha and，one minus alpha but then apparently。



![](img/96181912cdb98e5d08d9369d267826d4_27.png)

that's not enough，you can have your cross entropy loss and。



![](img/96181912cdb98e5d08d9369d267826d4_29.png)

then you can have one alpha here，to take care of the class imbalances and，then。



![](img/96181912cdb98e5d08d9369d267826d4_31.png)

you can you have two options for，choosing alpha。

![](img/96181912cdb98e5d08d9369d267826d4_33.png)

one is what i just said you look at your，training data，and count the number of times in your。



![](img/96181912cdb98e5d08d9369d267826d4_35.png)

training data you have easy examples，and how many times you have hard。

examples and then set alpha according to。

![](img/96181912cdb98e5d08d9369d267826d4_37.png)

that rule，your other option is to use your，validation data。



![](img/96181912cdb98e5d08d9369d267826d4_39.png)

to set alpha properly basically train，your algorithm multiple times。



![](img/96181912cdb98e5d08d9369d267826d4_41.png)

on your training data and look at the，performance。

![](img/96181912cdb98e5d08d9369d267826d4_43.png)

of different alphas on your validation，data and choose the best one。

but apparently that's not enough and。

![](img/96181912cdb98e5d08d9369d267826d4_45.png)

there is actually one easier way of，taking care of that，and that's just by multiplying your log。



![](img/96181912cdb98e5d08d9369d267826d4_47.png)

probability on one minus p to the power。

![](img/96181912cdb98e5d08d9369d267826d4_49.png)

gamma what it does is let's take a look，at gammas different gammas。



![](img/96181912cdb98e5d08d9369d267826d4_51.png)

if gamma is zero you're going to get the，cross entropy loss，and that's this blue curve and all of。



![](img/96181912cdb98e5d08d9369d267826d4_53.png)

these examples that you're gonna see，here they're gonna correspond to easy，examples。

they're the ones that are having a high，probability which means that you can。

actually classify them very easily。

![](img/96181912cdb98e5d08d9369d267826d4_55.png)

these are easy examples and you want to，downgrade them if you play around with。



![](img/96181912cdb98e5d08d9369d267826d4_57.png)

gamma and if you make it larger and，larger，then your curves are going to go down，and down it goes to。

red and yellow then to purple london to。

![](img/96181912cdb98e5d08d9369d267826d4_59.png)

the green，and then you are putting a very small，way on the easy examples。



![](img/96181912cdb98e5d08d9369d267826d4_61.png)

so that's another tool that's going to，help you，take care of easy example okay by。



![](img/96181912cdb98e5d08d9369d267826d4_63.png)

modifying your loss function，any questions so far but this was for。



![](img/96181912cdb98e5d08d9369d267826d4_65.png)

classes，it's the same thing you can have，multiple alphas and you can have，multiple。



![](img/96181912cdb98e5d08d9369d267826d4_67.png)

gammas any questions so in terms of，network。

![](img/96181912cdb98e5d08d9369d267826d4_69.png)

what they're using actually we covered，this network，it's feature parameter network and it。

was a two-stage detector。

![](img/96181912cdb98e5d08d9369d267826d4_71.png)

at that time you can modify it to become，one stage detector。



![](img/96181912cdb98e5d08d9369d267826d4_73.png)

an，image pyramid basically images at，multiple scales，you can use the features and try to。



![](img/96181912cdb98e5d08d9369d267826d4_75.png)

make these features stronger by having，an encoder and decoder structure。



![](img/96181912cdb98e5d08d9369d267826d4_77.png)

and then these features are going to，give you these feature maps are going to，with。



![](img/96181912cdb98e5d08d9369d267826d4_79.png)

and then each feature map is going to，predict a class。



![](img/96181912cdb98e5d08d9369d267826d4_81.png)

and a bounding box for each anchor box，so you're gonna have a anchor boxes and。



![](img/96181912cdb98e5d08d9369d267826d4_83.png)

then，you're gonna have k classes that's for，the classification。



![](img/96181912cdb98e5d08d9369d267826d4_85.png)

subnet for the bounding box subnet，you're gonna have，a anchor boxes and each one is going to。



![](img/96181912cdb98e5d08d9369d267826d4_87.png)

have four coordinates or，adjustment to those anchor boxes so。



![](img/96181912cdb98e5d08d9369d267826d4_89.png)

that's your network，that's your loss function and then in，one round you can train。



![](img/96181912cdb98e5d08d9369d267826d4_91.png)

both your classifier and bounding box，regressor。

![](img/96181912cdb98e5d08d9369d267826d4_93.png)

using a multi-task loss function and in，the end，the question is what alpha should i use。



![](img/96181912cdb98e5d08d9369d267826d4_95.png)

and what gamma should i use，it's exactly what you're going to do on，your validation data。



![](img/96181912cdb98e5d08d9369d267826d4_97.png)

you look at average precision and these，are coco，style average precision 50 is when you。



![](img/96181912cdb98e5d08d9369d267826d4_99.png)

have，your intersection over union to be 50，percent。



![](img/96181912cdb98e5d08d9369d267826d4_101.png)

or 75 percent for average precision，75。 you look at those numbers you keep。



![](img/96181912cdb98e5d08d9369d267826d4_103.png)

battering alpha，these are your alphas and then you're，gonna choose the best one i guess the。



![](img/96181912cdb98e5d08d9369d267826d4_105.png)

best one，is 0。9 or i think。

![](img/96181912cdb98e5d08d9369d267826d4_107.png)

31。1 is the biggest but then there is，some this discrepancy here。

for average precision 50 this is the。

![](img/96181912cdb98e5d08d9369d267826d4_109.png)

biggest one so，probably we're gonna choose 0。75 okay。



![](img/96181912cdb98e5d08d9369d267826d4_111.png)

you choose your alpha，that's your optimal alpha and then you，keep varying your gamma。



![](img/96181912cdb98e5d08d9369d267826d4_113.png)

yes so these are different alphas and，then you keep varying your gamma。



![](img/96181912cdb98e5d08d9369d267826d4_115.png)

and it turns out that this combination，is giving you the best，so that's what you're going to choose。



![](img/96181912cdb98e5d08d9369d267826d4_117.png)

you set your gamma to be 2 you set your，alpha to be。



![](img/96181912cdb98e5d08d9369d267826d4_119.png)

0。25 and you can actually have different，versions of this，retina network by changing the depth of。



![](img/96181912cdb98e5d08d9369d267826d4_121.png)

your network being 50 or 101 these are，resonance。

![](img/96181912cdb98e5d08d9369d267826d4_123.png)

and then you can have multiple skates，for your images，and obviously if you have a higher。



![](img/96181912cdb98e5d08d9369d267826d4_125.png)

depth and a higher scale that method is，going to be very。



![](img/96181912cdb98e5d08d9369d267826d4_127.png)

time consuming but it's going to be the，most accurate so there is a trade-off，between speed and。

accuracy how does it compare to the rest，of the，methods out there like faster or cnn，plus plus。

we didn't cover it but i'm sure you have，the background to read that paper on，your own。

faster our cnn would feature private，network this one we，covered and some other networks these。

are two stage methods，and in terms of one stage methods you，have yellow version two。

it's the previous paper we covered ssd，we didn't cover，dssd and this is retina net it's doing。

the best，except for the large images which is，competitive，and as a whole if you look at coco style。

average precision，on one axis and the other one to be your，inference time，right。

up to the left up sorry so you want to，push these curves，up you have two different versions of。

your network，and then different depth and resolution，and you can see that this is doing the。

best in terms of cocoa style，average precision if you believe that，that's a good metric。

compared to the rest of the landscape，this is a very good，of，now in terms of inference speed。

and average precision any questions，before i move to the next paper，okay the question is did a。

not make it into the last chart，and which one is a so yeah i noticed it，didn't have a marker on that。

chart it looks like that's because the，time is 25 milliseconds，oh okay so it's off to the left okay。

super fast so it's super fast，and it says it's not plotted i see now，thanks。

