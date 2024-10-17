# P63：L30.3- DeepLab - ShowMeAI - BV1Dg411F71G

![](img/ca705cddd608659356300fa580b109b6_0.png)

at least cover part of it so there are，in general。

![](img/ca705cddd608659356300fa580b109b6_2.png)

three channel ranges when you want to do，semantic segmentation。



![](img/ca705cddd608659356300fa580b109b6_4.png)

one is the one that we talked about，after your convolutions you're going to，end up with a。

reduced resolution the other problem we，noticed it in the failure results that。



![](img/ca705cddd608659356300fa580b109b6_6.png)

the first paper was reporting，that there were objects at multiple。



![](img/ca705cddd608659356300fa580b109b6_8.png)

scales some of them very，small some of them very big and it's，another challenge。



![](img/ca705cddd608659356300fa580b109b6_10.png)

and the other one is the localization，accuracy and we saw that in unit you。



![](img/ca705cddd608659356300fa580b109b6_12.png)

functions，to weight your pixels and that's，happening because of your neural network，being。



![](img/ca705cddd608659356300fa580b109b6_14.png)

actually convolutional neural networks，are invariant to。



![](img/ca705cddd608659356300fa580b109b6_16.png)

shifts and uh and their locally，translation in varying because of the。



![](img/ca705cddd608659356300fa580b109b6_18.png)

max pooling operation，actually。

![](img/ca705cddd608659356300fa580b109b6_20.png)

start working with at risk convolutions，so what is that and why is it important。



![](img/ca705cddd608659356300fa580b109b6_22.png)

of。

![](img/ca705cddd608659356300fa580b109b6_24.png)

our down sampling from 32，to 8。 how does it actually do it if you。



![](img/ca705cddd608659356300fa580b109b6_26.png)

want to do your original down sampling，and this is your image，if you down sample and remember down。



![](img/ca705cddd608659356300fa580b109b6_28.png)

sampling is because of stride，it's not because of max pooling it's not。



![](img/ca705cddd608659356300fa580b109b6_30.png)

because of convolution it's because of，your stride，so if you strive by two that's going to。



![](img/ca705cddd608659356300fa580b109b6_32.png)

be half the resolution of the original，image，if you do a convolution with a kernel of，seven。



![](img/ca705cddd608659356300fa580b109b6_34.png)

that's your candle and it's just a，random candle for visualization purposes。



![](img/ca705cddd608659356300fa580b109b6_36.png)

or illustration purposes then you，convolve this kernel with that image。

you're to end up with a bunch of。

![](img/ca705cddd608659356300fa580b109b6_38.png)

features and if you up sample these，you're going to see that your。



![](img/ca705cddd608659356300fa580b109b6_40.png)

information is lost at these points，so it's not smooth what you can do is，you take that image。



![](img/ca705cddd608659356300fa580b109b6_42.png)

and you introduce some zeros in your，filter。

![](img/ca705cddd608659356300fa580b109b6_44.png)

and that's why it's called atrocious，convolution，that's a french word and this stands for。



![](img/ca705cddd608659356300fa580b109b6_46.png)

holes you're introducing holes，in your filter you take that and the。



![](img/ca705cddd608659356300fa580b109b6_48.png)

rate at which you're introducing，holes is true you do your actual，convolution with a stride of one。



![](img/ca705cddd608659356300fa580b109b6_50.png)

and then you're gonna lose less，information and that's how you're gonna。



![](img/ca705cddd608659356300fa580b109b6_52.png)

end up with your down sampling rather，than being 32 it's gonna be eight。



![](img/ca705cddd608659356300fa580b109b6_54.png)

times，but what is the exact formula for the，attributes convolution it's not。



![](img/ca705cddd608659356300fa580b109b6_56.png)

complicated，you have your pixel this is your pixel，and then you're gonna。



![](img/ca705cddd608659356300fa580b109b6_58.png)

skip two pixels and then you skip two，other pixels。



![](img/ca705cddd608659356300fa580b109b6_60.png)

and then you do the same thing for going，down you skip two pixels two pixels and。

then you're covering a larger window。

![](img/ca705cddd608659356300fa580b109b6_62.png)

of your original image and that's gonna，be，what is getting multiplied by your。



![](img/ca705cddd608659356300fa580b109b6_64.png)

current and that，r is gonna be your rate prime so what is，nice is that you're gonna have the same。



![](img/ca705cddd608659356300fa580b109b6_66.png)

number of parameters and the same，computation，for an actual convolution i guess we are，out of time。

we are gonna continue this next session。

![](img/ca705cddd608659356300fa580b109b6_68.png)

and for those of you have questions you，can stay and ask and，want to have classes and have all their。



![](img/ca705cddd608659356300fa580b109b6_70.png)

meetings they can leave any questions。

![](img/ca705cddd608659356300fa580b109b6_72.png)

yeah thanks thanks that's so cool to，do because i used unit for work a little。



![](img/ca705cddd608659356300fa580b109b6_74.png)

bit ago and didn't understand it as，in-depth as，like now because of all the background。

we have so that's that's cool。

![](img/ca705cddd608659356300fa580b109b6_76.png)

yeah that's awesome yeah i wish i knew，about the the distance functions i。

wonder if i would have gotten。

![](img/ca705cddd608659356300fa580b109b6_78.png)

better results uh and that was the，application。

![](img/ca705cddd608659356300fa580b109b6_80.png)

in。

![](img/ca705cddd608659356300fa580b109b6_82.png)

in x-rays so it was really close yeah，to that paper yeah yeah that's why i。

think it worked well that domain it。

![](img/ca705cddd608659356300fa580b109b6_84.png)

seems to work really well on，on these mostly black images you know，with not much。



![](img/ca705cddd608659356300fa580b109b6_86.png)

and data augmentation is really，important yeah，for me because of it was a robotic。



![](img/ca705cddd608659356300fa580b109b6_88.png)

surgery and there was requirements on，how the image was taken so，the scale wasn't as or the yeah the。



![](img/ca705cddd608659356300fa580b109b6_90.png)

translation wasn't important for me，because they were always relatively。



![](img/ca705cddd608659356300fa580b109b6_92.png)

centered but the rotation yeah was key，because it could be you know any sort of，degree。



![](img/ca705cddd608659356300fa580b109b6_94.png)

yeah i see yeah like cool it's cool to。

![](img/ca705cddd608659356300fa580b109b6_96.png)