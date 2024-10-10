# 【双语字幕+资料下载】科罗拉多 APPLY-DL ｜ 应用深度学习-全知识点覆盖(2021最新·完整版） - P69：L32.4- DeepLab v3+ - ShowMeAI - BV1Dg411F71G

![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_0.png)

let's move to the next one because i，want to finish the segmentation today。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_2.png)

and then，move on to the next topic in the next，session so，we saw an encoder decoder architecture。

when we were doing u-net。

![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_4.png)

and those were doing very good we saw a，spatial，pyramid cooling when we were considering。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_6.png)

deep lab，now the idea of this paper is deep lab，version three plus。

is that you're gonna use both of them，you're gonna use，spatial pyramid pooling and then you are。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_8.png)

gonna use encoder decoder architecture，so you have some encoder you have some。

decoder here you're gonna have some，encoder，you're gonna have spatial pyramid。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_10.png)

pooling but then you're gonna have，less of those shortcut connections。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_12.png)

rather than having them at every layer，you're going to have few of them to copy。

and paste your information。

![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_14.png)

this is going to help you preserve，local information and the spatial。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_16.png)

pyramid building is going to give you，context，and these are with actress convolutions。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_18.png)

to be more exact about，about the architecture you have an image，you have an。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_20.png)

encoder you have a decoder the encoder，is going to have atrocious convolutions。

with different rays you can have one by，one convolution three by three。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_22.png)

convolution with a rate of six，rate of 12 rate of 18 and you can。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_24.png)

pull your image entirely you can，concatenate them，you do a one by one convolution to。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_26.png)

reduce the dimension that's the encoder，this is the encoded information now then。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_28.png)

you have，your decoder which is going to take the，output of your。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_30.png)

attributes convolution it's going to do，a dimensionality reduction。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_32.png)

what you do now is concatenate the，output of your encoder。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_34.png)

and the output of your previous layers，in the decoder。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_36.png)

so up until this point we are here so，this part，is the copy and paste from this layer to。

the next one，from the encoder to the decoder and this，arrow up there。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_38.png)

is this arrow here and the rest of it，you're going to do a concatenation。

and then you're going to do a three by。

![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_40.png)

three convolution your sample，and then you do your predictions and，then they're gonna have。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_42.png)

as their backbone the exception。

![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_44.png)

was，was an efficient network architecture，and we covered it。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_46.png)

when we were doing image classification，but it's an exception with a。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_48.png)

with the pulling layers being replaced，by，separable convolutions with a stride or。



![](img/cb931a2ed6f7a1d3a42ba1a442427ebd_50.png)

two so rather than pulling you're gonna，do completion so that's the only change。

and here are some predictions of the，model qualitatively and quantitatively。

and you can study the effect of the one，by one convolution，in the decoder how important that is，what。

what is a good dimension for you to，reduce to，apparently 48 is the best one it's，giving you the best。

mean intersection over union and you can，study，the effect of this three by three。

convolution how many of them do you need，to have so，two layers of that three by three and，256。

channels is giving you the best and，there is a debate between taking。

uh one convolution from one layer to the，next one，which one should we take and apparently。

taking comp two is the best i think，uh we are out of time for those of you。

who have a question you can stay and ask，for those of you want to leave with me i。

was wondering if you go back to the，pyramid i'm still trying to gain like an，intuition of how this。

so what i'm trying to like imagine and i，don't know if you could tell me if this。

is like correct or not，is what this is doing essentially is，taking the right half of the u。

and like squishing it down and doing all，of your different，sort of spatial things on the same。

feature vector，right because you're doing it sort of，taking all the information and then。

taking substance the information，and then combining um is that sort of a。

decent way to think about it，so you are doing your pulling at，multiple different states。

one of your pooling is pulling the，global information，which is the red one the other one is，left。

top right lower left lower right of your，feature map，and for the other ones you get the idea。

so it's global information，local information on the top left，upright etc。

and so on and then you concatenate all，of that information together yeah。

whereas with like a u-net you're you're，taking the up-sampled version。

of your global information to get more，localized，right because you're taking like you're。

up sampling first，and then doing another uh convolution，but here you're saying。

rather than having them sort of，crosstalk you're doing it all um。

just like separately yeah so for your，unit，you wanted to extract more local，information。

from one layer to the next one or at，least try to lose as little as possible。

because the boundaries matter to you but，here it's not a matter of boundaries。

it's a matter of context why would the，network why would the network think that，an object。

on water should be classified as a car，because it hasn't seen maybe it's seeing。

a house here and it's confusing it，because if you only pull the global，information。

and it's looking at this part but if you，pull on this local part of your image。

you're going to see more of the water。