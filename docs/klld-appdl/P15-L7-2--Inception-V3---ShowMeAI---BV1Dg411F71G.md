# P15：L7.2- Inception-V3 - ShowMeAI - BV1Dg411F71G

so i guess you remember the inception，architecture，it's the paper that we covered。

from google and it was being called，they introduce batch normalization，because that was a。

novel technique that was discovered，after they wrote a paper，therefore they are just going to use。

batch normalization technique in that。

![](img/34ccfef675ba495b1330fec2d0b35b73_1.png)

paper and what are some other changes，that they make to their architecture。

things are only three by three，convolutions，with different strides so whenever your。

stride is bigger than，one you're reducing your number of，pixels。

from one layer to the other that's why，this is gonna have a different pixel，from uh it's 147。

yes so it has to do with the boundary，of your image or the boundary of your，layer so you're losing。

two points one from left one from right，and there is a bunch of other，convolutions。

and here is where the contributions are，they are going to use three inception，modules。

on top of that five other type of，inception modules，then another two inception modules。

so global average pulling and if you，remember it was introduced in the，networking network paper。

then there are these logits and then you，do a soft max，to give you the classifiers to turn your。

numbers your logics。

![](img/34ccfef675ba495b1330fec2d0b35b73_3.png)

into probabilities you do a soft max，so what are these inception modules。

this is the first one and this，in the first，sessions we said that a five by five，convolution。

has the same receptive field，as two three by three convolutions，stacked on top of each other。

in a deep fashion so this is the first，three by three convolution。

and each one of these guys are gonna be，strided by one，so it's gonna give you this is the first。

number this is the second number as you，stride it to the，right this is the third number as you。

stride it to the right，stride it right and up that's what you，get and so on。

and then on top of that you have another，three by three convolution with filter，size three。

so they have the same receptive field，and that's the size of the。

receptive field it's gonna be five by，five one，so the idea is that you can。

replace a five by five convolution，by two three by three convolutions is。

stacked on top of each other，so you're just adding the number of。

layers that you have and that's what，and the rest of it we know from the，previous architectures。

and these one by one convolutions are，just to reduce the dimension，and in the end you're just gonna。

concatenate the filters，and you have three of them three，and the idea is that you want to，decrease。

the amount of computations that you make。

![](img/34ccfef675ba495b1330fec2d0b35b73_5.png)

two three by three convolutions is，cheaper than，one five by five convolution。



![](img/34ccfef675ba495b1330fec2d0b35b73_7.png)

computationally，so what is the other change this is。



![](img/34ccfef675ba495b1330fec2d0b35b73_9.png)

happening towards the end of the network。

![](img/34ccfef675ba495b1330fec2d0b35b73_11.png)

and then you are going to use five of，these inception modules，and the idea is that a seven by seven。

conclusion，you can replace it by one by seven，seven by one one by seven and。

seven by one so this is just，a seven by seven convolution it has the，same receptive field。

but it has less parameters，the fig the plot that you see here is。

for a one by three and then on top of，that is three by one，and in the end you have three by three。

as your receptive field，any questions so far so a bunch of your。



![](img/34ccfef675ba495b1330fec2d0b35b73_13.png)

seven by seven convolutions you are，replacing them。



![](img/34ccfef675ba495b1330fec2d0b35b73_15.png)

![](img/34ccfef675ba495b1330fec2d0b35b73_16.png)

is two of these types of。

![](img/34ccfef675ba495b1330fec2d0b35b73_18.png)

you keep，one by three three by one and you have，three by three and then you do one by。

three and three by one on top of that，rather than stacking them on top of each。

other you can put them next to each。

![](img/34ccfef675ba495b1330fec2d0b35b73_20.png)

here you are stacking two a one by three。

![](img/34ccfef675ba495b1330fec2d0b35b73_22.png)

and then a three by one convolution，on top of each other now you are putting，them next to each other。



![](img/34ccfef675ba495b1330fec2d0b35b73_24.png)

what happens to striding and pulling。

![](img/34ccfef675ba495b1330fec2d0b35b73_26.png)

when you want to reduce the number of，your pixels。

![](img/34ccfef675ba495b1330fec2d0b35b73_28.png)

this is how you do it these two are the，same things，but you are looking at them from。

different perspective，so this is where you put your strides。



![](img/34ccfef675ba495b1330fec2d0b35b73_30.png)

there's a strike two there's a strike。

![](img/34ccfef675ba495b1330fec2d0b35b73_32.png)

i think we are one minute over time for，those of you want to leave。



![](img/34ccfef675ba495b1330fec2d0b35b73_34.png)

you are more than welcome to leave i'm，gonna be around for those who have a。



![](img/34ccfef675ba495b1330fec2d0b35b73_36.png)

i had a quick unrelated question。

![](img/34ccfef675ba495b1330fec2d0b35b73_38.png)

last，architecture for the uh one of the，models that we studied，the layer before the output layer。

was like a one by one by 1024。

![](img/34ccfef675ba495b1330fec2d0b35b73_40.png)

or so so i was just wondering is there a，difference with like。



![](img/34ccfef675ba495b1330fec2d0b35b73_42.png)

number，of classes that you're trying to predict，or it doesn't pose a problem if you're。

like trying to predict three classes，but then the layer before that has like。



![](img/34ccfef675ba495b1330fec2d0b35b73_44.png)

4 000，uh in length so you mean for instance。

![](img/34ccfef675ba495b1330fec2d0b35b73_46.png)

here，48 and then you have 1 000。

![](img/34ccfef675ba495b1330fec2d0b35b73_48.png)

yeah so no it doesn't matter。

![](img/34ccfef675ba495b1330fec2d0b35b73_50.png)

what you're gonna do in in the end it's，just a matrix multiplication。



![](img/34ccfef675ba495b1330fec2d0b35b73_52.png)

to change from this huge dimension to，maybe three here。



![](img/34ccfef675ba495b1330fec2d0b35b73_54.png)

![](img/34ccfef675ba495b1330fec2d0b35b73_55.png)