# P38：L19.4- ShuffleNet - ShowMeAI - BV1Dg411F71G

so let me move to the next topic this is。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_1.png)

the last topic for small networks，and it's about shuffle net the idea is，that you have your inputs。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_3.png)

let's forget about the resolution for，now and let's just look at the channels。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_5.png)

your input is gonna have these many，channels，if you do a group convolution we just。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_7.png)

saw what is a group convolution，so you're doing your convolutions on。

different chunks of your channels，and you're doing it independently if you，do that。

you're going to end up with some，features and the features are，independent from your inputs。

if you do another group convolution，still，the features are going to be independent。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_9.png)

and then your channels are not talking，to each other，this is good if you have three gpus and。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_11.png)

you want your gpus not to，interfere with each other's jobs but，then。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_13.png)

mathematically you're losing information，because maybe。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_15.png)

the information in this part of your，input is important，for the features that you're gonna end。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_17.png)

up with here and here，so one way to fix this is to mix stuff。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_19.png)

after the first independent channels up，until here，you do a group convolution then you mix。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_21.png)

and match you say okay the first part，should go here。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_23.png)

the second part should go here the third，part should go here，for my group convolution the second。

group convolution。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_25.png)

the green ones you separate them and you，push them through different。

group convolutions with different，parameters and you do the same thing for，the blue ones。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_27.png)

now the color is changing indicating，that now you did some mix and matching。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_29.png)

for your channels now you mix things up，channel wise，now the output of these two operations。

are gonna，have information coming from different，groups。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_31.png)

but this is not an efficient way of，implementing stuff。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_33.png)

the efficient way of implementing it is，the first group convolution is the same，as before。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_35.png)

but now you shuffle your channels and，this operation is very simple。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_37.png)

i'm gonna tell you what the exact code，is gonna look like，unless you do that it looks like that is。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_39.png)

exactly the same as what you drew in，diagram，b yes but now there's an operation there。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_41.png)

gonna do，okay and then it's gonna be exactly what，you said it's gonna give you the exact。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_43.png)

same，same。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_45.png)

but implementation wise how are we gonna，implement this and，first what are the applications the。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_47.png)

applications we know，it's about robots drones smartphones etc。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_49.png)

so how do you implement channel shuffle，you have，g as your number of groups in this case。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_51.png)

you have one two，three groups n is the number of channels。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_53.png)

per group i don't know let's say you，have 10 channels，for each group and the total number of。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_55.png)

channels is going to be g，times n that's the total size of the，input channel。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_57.png)

you're going to reshape to g n，so we're just gonna do a reshape，operation in python。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_59.png)

you first do a reshape it's gonna be g n。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_61.png)

now it's a two dimensional array you，transpose that，array you flatten it so you reshape it。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_63.png)

back to one dimensional，so you start from something one，dimensional which has times。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_65.png)

size g times n you reshape it you make，it a matrix。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_67.png)

and then you flatten it back you，back，then it's going to give you a channel。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_69.png)

shuffle so it's very cheap this，operation is very cheap，and smart actually that was the micro。

structure。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_71.png)

the micro structure is going to look，like this this is what you have for a，residual。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_73.png)

connection you do one by one depth wise。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_75.png)

separable convolution and then one by，one before you do your second，convolution。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_77.png)

you do a channel shuffle and if you want，to have a different stride。

you first do your channel shuffle you do。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_79.png)

a stride of two here，and let's try it f2 here and then add，the outcomes this is when you want to。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_81.png)

reduce the resolution，this is when you want to keep the，off。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_83.png)

operation is very simple this is what，you do when you code it up。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_85.png)

and you can study the effect of，different groups，if your group size is one two three four。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_87.png)

and eight，and if you try to keep the complexity，the same you're gonna need to play。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_89.png)

around with the dimensions a little bit，and this is how it compares to vgg，google net。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_91.png)

and alexnet with different group sizes，and the complexity is going down。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_93.png)

so this is the complexity compared to，alexnet it's 38 but then you have。



![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_95.png)

similar classification error and you can，have different versions of your shuffle。

with different uh resolutions i think，i'm finished right，right on time do you have any questions。

for those of you have questions you can，stay and ask，and the ones you want to leave you're。

more than welcome to leave what are the，numbers after the like，shuffle net 0。5 shuffle one，the。

number of channels the multiplier okay，it's very similar to google maps so，they're not modifying。

vgg they're just putting it next to it，because it has similar，error is that correct exactly so they。

are putting it next to it，and as you can see here they are trying，to keep the same。

keep the computational complexity the，same，or of the same order but with different，groups。

why because then it's gonna be very easy，for them to compare to。

networks of similar size so they just，have similar sizes in terms of，parameters。

and the shuffle isn't something that's，time，yes so there is nothing learned here，it's just。

reshuffling rearranging the furniture，you first take a vector，turn it into a matrix transpose the。

matrix flatten it，does that answer your question yeah yeah，and i was so it seems like it's a。

structured it's the same order every，time it's not like a random。

thing no it's the same order nothing is，random here do you know if people have。

tried anything sort of more randomized，there or，more learned or i guess just different。

besides the sort of deterministic，shuffling，uh i think if you put a drop out right，after。

the outcome of your shuffle that's gonna，randomize stuff，haven't。

i'm sure there is a paper that does that，in a random fashion，okay but you want to have control here。

over the outcome，because in the end you want to take this，network。

and put it into production you don't，want things to be random，in production yeah i guess that makes。

sense so maybe some sort of like learned，way，learned shuffling would i it may not be。

better but it might，at least make sense i guess yeah but the，big picture is that。

no matter how you want to do it it's a，pretty efficient way of doing it but no，matter。

how you want to do it you want to mix，and match the，information across different channels if。

you take that idea home that's great，but so the thing is i feel like a normal，convolution。

sort of mixes and matches channels，anyway right if you do，a convolution it combines information to。

different future vectors，using different combinations of the，channels is is this just really。

efficient because they，can split the previous layers into like，parallel threads basically and only。

shuffle，when they want to why is it more，efficient than a regular。

channel regular convolution the answer，is，these are smaller matrices and you're。

doing smaller matrix vector，multiplication，and that's why it's more efficient well。

and this is only like applicable because，we're doing this particular we're doing。

these group convolutions，exactly and in other networks where，you're not doing a group convolution。

it's just，that's not even a it's not applicable，yes but what is the objective here。

just like reducing parameters and，guess，yes so we are looking for methods to do，that yeah。

one method was grouping the other method，was，one by one convolutions the other method。

was depth-wise separable convolutions，and this is another method channel，shuffle。

very cheap and very efficient the idea，is brilliant，this is very and it works really well i。

mean i don't，like i wouldn't i don't know why you'd，pick a google net over you know。

if it's performing about the same it has，way smaller complexity，if you look at it it has the same。

structure as google maps，with another addition the channel，shuffle but just 10 times。

less complexity yes so there's google，left there's shaft，which i mean i agree with that the same。

structure as，mobile net but yes serious is right why，would you choose google net if you have。

shuffle net here，in terms of complexity is much more，efficient and i think everything i see。

always just uses you know like vgg，and never even though it's very you know，similar。

oh there is a reason for that when we go，to transfer learning you're gonna see。

why just because there's so much for vgg，sort of，data or not data i guess but like models。

when you write a paper in deep learning，you need to be able to compare it。

with the rest of the literature and you，want to always change，small things you don't want to change。

your entire，structure because you want to do a fair，comparison。

with the rest of the literature that's，why you see vgg16 in most of the pages，yeah。

so i see so you use the vgg like，backbone and change you know the top，layers。

um okay yeah but so but couldn't you，argue that，because we have like an order of。

magnitude less complexity，that uh we can train things so much，faster。

i wonder if i wonder if the point is，that like when we get to transfer，learning。

you might want those extra parameters uh，to make your model more adaptable to，like a change。

maybe that's just a guess but isn't，transfer learning useful because。

it gives us a speed up in training and，right are we talking about transfer。

learning more and like the data set like，the data，yes that one we are going to talk about，later。

and we're going to go into more details，but usually，what you do is for instance you want to。

do object detection，you take the first few layers of vgg16，and you fix them so there is no training。

going on，and then you just change the or，fine-tune，the last layers where you have the，feature。

so does transfer learning uh so does，that term，apply to both transfer learning for like。

the parameters for a model，and transfer learning for like data。

to sort of a similar data but different，because that's how i've used it heard it，used before。

like i've only heard it in the first，case yeah but maybe it's both。

and it's not a difficult concept you are，just fine-tuning your，parameters anything to ask a little。

further why not，fine tune on top of shuffle net is like，is there some inherent reason that。

fine tuning on a larger network works，better or could you do either。

you can you definitely can if you want，to have something in production。

you want to have something more，efficient but if you want to do research，and write a paper。

that's a different story because then，you need to be able to compare to the，rest of the。

literature okay let's see at some point，maybe it'll switch to。

everyone using a different architecture，and then then you kind of modify and，adapt。

and most of these papers were written，prior to 2018。so this is pretty new not that new in。

deep learning，but still new i just had a，one other different question um about。

depth wise convolutions，um so there's in that case there's just，one filter per channel。

is that correct exactly okay there's one，filter per channel，perfect thank you okay any other。

questions。