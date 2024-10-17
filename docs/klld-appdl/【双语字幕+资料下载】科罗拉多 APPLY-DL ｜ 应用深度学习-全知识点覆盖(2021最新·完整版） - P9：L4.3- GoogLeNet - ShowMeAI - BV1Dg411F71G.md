# P9：L4.3- GoogLeNet - ShowMeAI - BV1Dg411F71G

![](img/c53323974854ad9abb40546a34fc5897_0.png)

okay let's move on going deeper with。

![](img/c53323974854ad9abb40546a34fc5897_2.png)

this is the ideas of google net，and we are gonna learn about inception。

as you can see this paper is also being，written around the same time，2014 and 15。

at that time they were not sure whether，to use，convolution five by five convolutions or。

three by three convolutions，or one by one convolutions or seven by。

and the question is which one which one，are we gonna use，which one is better than the other the。

so you use them all you take your，and then you're going to end up with a。

bunch of channels i don't know maybe 15，then you do a three by three convolution。

you end up with 25 channels，you do a 5 by 5 convolution，with a different number of filters and。

you end up with 50，channels at the same time you do a，and the idea is that just concatenate，these。

across your channel dimension，and that's how you use it all at the。

same time that you're doing one by one，convolution you're doing three by three，and five by five。

the cool thing is that the next layer is，gonna combine all of these together。

so this is the idea of the inception。

![](img/c53323974854ad9abb40546a34fc5897_4.png)

module，but what is the problem there with the。

![](img/c53323974854ad9abb40546a34fc5897_6.png)

naive version，dimensions don't seem to match when you。



![](img/c53323974854ad9abb40546a34fc5897_8.png)

concatenate those filters，i think one by one three by three and，five by five are。

fine you can just concatenate them，because you are doing it channel wise。



![](img/c53323974854ad9abb40546a34fc5897_10.png)

and the dimension of the inputs。

![](img/c53323974854ad9abb40546a34fc5897_12.png)

is gonna remain the same i mean，the resolution of the input is gonna，remain the same。



![](img/c53323974854ad9abb40546a34fc5897_14.png)

the number of channels change even for，max pooling。



![](img/c53323974854ad9abb40546a34fc5897_16.png)

if the stride is one you are not，changing your resolution，yeah so that's fine the resolution is。

the same and then you are concatenating，a bunch of images。



![](img/c53323974854ad9abb40546a34fc5897_18.png)

on top of each other or next to each，other。

![](img/c53323974854ad9abb40546a34fc5897_20.png)

so that's fine what's the problem，yes jacob that's a good point。

it's going to create a lot of channels。

![](img/c53323974854ad9abb40546a34fc5897_22.png)

when you concatenate，and the problem。

![](img/c53323974854ad9abb40546a34fc5897_24.png)

is that these convolutions are not cheap，operations，so at the same time the paper wanted to，go deep。

they wanted to increase the capacity of。

![](img/c53323974854ad9abb40546a34fc5897_26.png)

the network。

![](img/c53323974854ad9abb40546a34fc5897_28.png)

at the same time they wanted to，care about the computational complexity。

one way to decrease the com the，computational complexity，is to reduce the dimension first so you。



![](img/c53323974854ad9abb40546a34fc5897_30.png)

use a one by one convolution，and you reduce the number of channels。



![](img/c53323974854ad9abb40546a34fc5897_32.png)

first，and then you do a convolution three by。

![](img/c53323974854ad9abb40546a34fc5897_34.png)

three one。

![](img/c53323974854ad9abb40546a34fc5897_36.png)

you reduce the dimension and then you。

![](img/c53323974854ad9abb40546a34fc5897_38.png)

in the end the dimensions are gonna，match and then you concatenate your。



![](img/c53323974854ad9abb40546a34fc5897_40.png)

that one also works there is no problem，with that，it's just computationally more expensive。

than this one，and there are some results in the paper，that show that。

this one is as good as the other one but。

![](img/c53323974854ad9abb40546a34fc5897_42.png)

i think we are one minute over time if。

![](img/c53323974854ad9abb40546a34fc5897_44.png)

there are any questions，feel free to ask if you want to leave，your more than welcome to leave。



![](img/c53323974854ad9abb40546a34fc5897_46.png)

data augmentation with the covariance。

![](img/c53323974854ad9abb40546a34fc5897_48.png)

matrix，so you take every single pixel which is，a，three-dimensional vector and you put all。



![](img/c53323974854ad9abb40546a34fc5897_50.png)

of those in a matrix，and then you make the covariance matrix，from that matrix。



![](img/c53323974854ad9abb40546a34fc5897_52.png)

and that's the covariance between each，pixel。

![](img/c53323974854ad9abb40546a34fc5897_54.png)

so i think it's yes go ahead，i think it's the covariance between the。



![](img/c53323974854ad9abb40546a34fc5897_56.png)

rgb，about。

![](img/c53323974854ad9abb40546a34fc5897_58.png)

uh maybe i don't understand covariance，as much as i。



![](img/c53323974854ad9abb40546a34fc5897_60.png)

thought i did um but like if you had，say an n by n matrix if you wanted to。

find the covariance matrix，you would just multiply like。



![](img/c53323974854ad9abb40546a34fc5897_62.png)

a by a transpose right，so yes that's what you do you multiply a。



![](img/c53323974854ad9abb40546a34fc5897_64.png)

by a transpose，second order moment but let's just，believe it that。



![](img/c53323974854ad9abb40546a34fc5897_66.png)

you multiply your vector by its，transpose，it's gonna give you a three by three。



![](img/c53323974854ad9abb40546a34fc5897_68.png)

matrix，is that correct yeah and that's what i，was saying and you have to do a，summation。

over that yeah your data and your pixels，the summation is going to be over x y，which is your pixels。

and your data points what do you mean in。

![](img/c53323974854ad9abb40546a34fc5897_70.png)

your data points how about your pixels，were your，data points or are you doing it across。



![](img/c53323974854ad9abb40546a34fc5897_72.png)

images，it has to be across images and across。

![](img/c53323974854ad9abb40546a34fc5897_74.png)

because it has to be consistent whatever，transformation that you're doing。

it has to be consistent across a single。

![](img/c53323974854ad9abb40546a34fc5897_76.png)

image，and it has to be consistent across all，of your images。



![](img/c53323974854ad9abb40546a34fc5897_78.png)

so you you iterate through every single，image，and then you iterate through every pixel。



![](img/c53323974854ad9abb40546a34fc5897_80.png)

and you do that vector multiplication to，create a three by three matrix，pixel。

and then every single image your，iteration is actually your summation。



![](img/c53323974854ad9abb40546a34fc5897_82.png)

so yes okay you do your summation。

![](img/c53323974854ad9abb40546a34fc5897_84.png)

over your data point i，basically this is image 10 that's your i。



![](img/c53323974854ad9abb40546a34fc5897_86.png)

pixel i don't know 12 and pixel，13 i x and y that's your summation and。



![](img/c53323974854ad9abb40546a34fc5897_88.png)

then you multiply your vector，by itself transpose okay，and in the end you just have one。



![](img/c53323974854ad9abb40546a34fc5897_90.png)

three by three matrix and that's what，you find the eigenvalues and，eigenvectors for。



![](img/c53323974854ad9abb40546a34fc5897_92.png)

exactly so then because it's just one，matrix。

![](img/c53323974854ad9abb40546a34fc5897_94.png)

one covariance matrix everything is，going to be consistent，and it's added the same eigenvector and。



![](img/c53323974854ad9abb40546a34fc5897_96.png)

eigenvalue everywhere。

![](img/c53323974854ad9abb40546a34fc5897_98.png)

and essentially it's like the average，covariance，of a pixel between channels。

it is actually the average it's it's the。

![](img/c53323974854ad9abb40546a34fc5897_100.png)

covariance across your，data。

![](img/c53323974854ad9abb40546a34fc5897_102.png)

okay we are being a little bit sloppy，here it's not，one vector times the other transpose。

there is some mean that you have to，subtract etc。

![](img/c53323974854ad9abb40546a34fc5897_104.png)

but you get the idea yeah okay。

![](img/c53323974854ad9abb40546a34fc5897_106.png)

and to compute the mean you do the same，thing yes，it's the mean of your pixels across the。

image and across the。

![](img/c53323974854ad9abb40546a34fc5897_108.png)

data how do you compute the mean value。

![](img/c53323974854ad9abb40546a34fc5897_110.png)

i mean you just sum up across all pixels，and then divide by your number of pixels。

exactly so you have to do the same thing，with your covariance。



![](img/c53323974854ad9abb40546a34fc5897_112.png)

![](img/c53323974854ad9abb40546a34fc5897_113.png)