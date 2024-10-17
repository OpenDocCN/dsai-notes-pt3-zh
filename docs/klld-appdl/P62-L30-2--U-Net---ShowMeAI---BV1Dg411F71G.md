# P62：L30.2- U-Net - ShowMeAI - BV1Dg411F71G

let's talk about unit i know that some，of you know about it already。

but you're using it in a different，context you're not using it for。



![](img/9970c132ebdce7eb0f9b8352988bd343_1.png)

image segmentation and actually unite，was introduced to do image。

segmentation what's going to happen is，you start with an，image and then you are careful with your。

strides and，uh whenever you see an arrow that is，blue that's going to be a three by three。

convolution，so you do one three by three convolution，another one then you do。

a max pooling we just tried up two and，that's gonna，give you less resolution so another。

resolution is this，vertical size then you do a bunch of，other convolutions。

uh max link with a stride too，a bunch of other striding a bunch of，other convolutions is writing。

object，that's the one of the problem the rest，of it you have to，you do。

up convolution another up convolution a，bunch of other convolutions etc。

but then we saw this idea in the，previous paper as well，we need to keep the local information。

but the difference is that，you take the local information from your。

input and copy and paste it and this is，just a copy and paste operation。

and you just concatenate channel wise，and this goes back to the previous。

question so you just concatenate，channel wise and this is gonna copy the，local information。

and you do that for different uh at，different resolutions，paste。

you copy and paste you copy and paste，and then the rest of it is。

straightforward and that's why it has，the name of the you，met because it's u-shaped so is the。

picture clear，so we saw the same idea in the previous，paper as well。

because we want to keep the locality so，now let's go into the math。

because i promised you to give you the，exact formula for，deconvolution now we're going to see it。



![](img/9970c132ebdce7eb0f9b8352988bd343_3.png)

here but let's，start with the convolution and write it，down expand it in terms of its。

terms you want to know the value of the，outputs of a 3x3 convolution，at pixel location x y and。

the channel location l so that's what，you want to do。



![](img/9970c132ebdce7eb0f9b8352988bd343_5.png)

no you take a that's the input，it's going to depend on x y and some。

channels so for x you go one lead。

![](img/9970c132ebdce7eb0f9b8352988bd343_7.png)

one step to the left one pixel to the，left one pixel to the right。



![](img/9970c132ebdce7eb0f9b8352988bd343_9.png)

and one pixel up one pixel down，one pixel to the left up corner one，pixel to the。

right up corner etc and that's how this，summation is being formed so that's。



![](img/9970c132ebdce7eb0f9b8352988bd343_11.png)

gonna take，a small three by three window of your，input。



![](img/9970c132ebdce7eb0f9b8352988bd343_13.png)

and then it's going to sum over them，after multiplying by matrix。

after multiplying by a scalar and then，you are going to have，l different filters and k is just。

going to be your inner product，that's why you have this summation so。

that's a three by three convolution，expanded out，what is a two by two max pulling if you。

expand it out，because the stride is two you're gonna，put a two here。

because you're gonna jump uh every two，pixels，so that's why you have a two here and。

then the rest of it you are taking a，window of size two by two and that's why，here。

and you find a maximum if you want to do，average building you're going to find a，mean。

here that's your max pooling with a，stride of two that's how you。

reduce the resolution and what is up，convolution now，you're just reusing your weights and。

that's why it's called fractional，we write it convolutions so let's see。

we know that our stride is going to be 2，because we want to，upsample and we want to know the value。

at this location，2x plus 0 or 1。 so you want to know your，value。

what you have is you have only one pixel，of it，so what you're gonna do is you're gonna。

use your weights actually you reuse it，you start with one pixel and that one，pixel。

is gonna output two pixels for you，actually four pixels for you。

so there is only a single pixel here at。

![](img/9970c132ebdce7eb0f9b8352988bd343_15.png)

the input layer，the summation over k is nothing，complicated。



![](img/9970c132ebdce7eb0f9b8352988bd343_17.png)

you are just doing the inner product and，then you're，reusing the same weights on the same。

input pixel to give you the output。

![](img/9970c132ebdce7eb0f9b8352988bd343_19.png)

so is this clear and as you can see it's，going to have the same this w is going。



![](img/9970c132ebdce7eb0f9b8352988bd343_21.png)

to be the same as the original w，that's actually the back propagation。

algorithm through these two channels，if you have a convolution that had a，stride of two。



![](img/9970c132ebdce7eb0f9b8352988bd343_23.png)

then uh this two by two armed outcome，is just the inverse of a three by three。



![](img/9970c132ebdce7eb0f9b8352988bd343_25.png)

convolution，with a stride of two so you need to ask，me a question if。

something is unclear so the main，mechanism of getting，two pixels out is because you're doing。



![](img/9970c132ebdce7eb0f9b8352988bd343_27.png)

it or for four pixels you're doing it，for，multiple values of your weights and then。



![](img/9970c132ebdce7eb0f9b8352988bd343_29.png)

keeping the pixel value the same，right so you have the same pixel you，have four different，different。

values and then that's going to give you，four different pixels up。

and just make sure k is the channel，right yes so，k is a channel and l is also your，channel so。

channel wise things are not complicated，it's just a matrix vector。



![](img/9970c132ebdce7eb0f9b8352988bd343_31.png)

multiplication but pixel wise you have，four weights that are being multiplied。



![](img/9970c132ebdce7eb0f9b8352988bd343_33.png)

by the same pixel，yeah that makes sense yeah so i promise，i'm gonna give you the exact formula。

that's it。

![](img/9970c132ebdce7eb0f9b8352988bd343_35.png)

that's a deconvolution so once you see，the map you see that these are not，complicated stuff。

but when you try to visualize it it's，going to be more complicated to be sure。

and we saw the same thing deconvolution，when we wanted to do，visualization of the features in our。

neural networks that was a couple of，sessions ago so that's the operation。

and this is exactly what you're gonna，see what is coded if you use tensorflow，by torch etc。

under the hood that's what's happening，okay，so i owed you two things one was what is，a deconvolution。

then i owed you one other thing and，that's the last function，what is the last function for image。

segmentation，this is your last function forget about，w for now。

so let's set that to be one you want to，increase the probability of。



![](img/9970c132ebdce7eb0f9b8352988bd343_37.png)

that pixel being correctly。

![](img/9970c132ebdce7eb0f9b8352988bd343_39.png)

labeled so this is the ground truth，label，and you want to increase this，probability or。

equivalently you want to increase the，log of that probability，or you want to decrease the negative。

sign，of that log of the probability so you。

![](img/9970c132ebdce7eb0f9b8352988bd343_41.png)

have a pixel that pixel has a couple of，options it could be，belonging to a cat or a dog or。

an airplane or the background what，you're gonna do is you're gonna increase。



![](img/9970c132ebdce7eb0f9b8352988bd343_43.png)

the probability of this pixel belonging，to the ground truth。



![](img/9970c132ebdce7eb0f9b8352988bd343_45.png)

which in your case might be a cat so you，want to increase the probability of that，pixel。

being a cat and what is this let me just，bring up what l is so l is the true。



![](img/9970c132ebdce7eb0f9b8352988bd343_47.png)

label，for each pixel and how do you get your，max。

![](img/9970c132ebdce7eb0f9b8352988bd343_49.png)

and it's gonna be pixel wise so that's，your soft max and this is the output of，your network。

and why do you need a w here you don't，in general you don't need it。



![](img/9970c132ebdce7eb0f9b8352988bd343_51.png)

for image segmentation we can set that，to be one but because，our application area is a biomedical。

these boundaries really matter，between yourself so you want to really，focus on the boundary。

and identify where your boundaries are，and the other problem was that，have。

more data of a particular class compared，to the other one that's why you're gonna，introduce this w。



![](img/9970c132ebdce7eb0f9b8352988bd343_53.png)

the first term is gonna take care of the，imbalances in your classes，so that's gonna be your class。

frequencies and，when you have training data you have。



![](img/9970c132ebdce7eb0f9b8352988bd343_55.png)

these statistics you can simply compute，them you can know what is the class，frequencies。



![](img/9970c132ebdce7eb0f9b8352988bd343_57.png)

so that's not tough that part we know，chose。

![](img/9970c132ebdce7eb0f9b8352988bd343_59.png)

for w0 and sigma squared in terms of，pixels，and d1 and d2 are the distance to the。



![](img/9970c132ebdce7eb0f9b8352988bd343_61.png)

border of the nearest cell，if the distance is really far you don't，want to give。

much weight to the probabilities and，that exponential term。



![](img/9970c132ebdce7eb0f9b8352988bd343_63.png)

in collaboration with this negative sign，and the square term is going to do that，for us。



![](img/9970c132ebdce7eb0f9b8352988bd343_65.png)

if b is big the exponential of negative，small，and you're going to have the other term。

is the distance to the order of the，second。

![](img/9970c132ebdce7eb0f9b8352988bd343_67.png)

nearest cell and whenever you're doing，training you know these statistics。



![](img/9970c132ebdce7eb0f9b8352988bd343_69.png)

because you know the ground truth，the other thing that they do in the，paper。



![](img/9970c132ebdce7eb0f9b8352988bd343_71.png)

is rather than zero padding on your，original image，you're gonna do a reflection padding so。



![](img/9970c132ebdce7eb0f9b8352988bd343_73.png)

whatever that you have here is，the mirror image of it that you copy and。



![](img/9970c132ebdce7eb0f9b8352988bd343_75.png)

paste to give you the correct resolution，and the rest of it are just results this。

is the ground truth。

![](img/9970c132ebdce7eb0f9b8352988bd343_77.png)

that's the original image somebody gave，us the labels with a。



![](img/9970c132ebdce7eb0f9b8352988bd343_79.png)

biomedical pho was doing the labeling，for us，and this is the output of the algorithm。



![](img/9970c132ebdce7eb0f9b8352988bd343_81.png)

ground through，i mean background versus not background。



![](img/9970c132ebdce7eb0f9b8352988bd343_83.png)

and this w the plot here is，exactly w so you're giving more emphasis。



![](img/9970c132ebdce7eb0f9b8352988bd343_85.png)

to the boundaries，that's why you're introducing this way，function let's see some other results。

this is some other cells，from another data set the yellow line，that you see is somebody doing the。

labeling for us and the prediction of，the model is here，the green one similarly here and in。

terms of numbers，unit is doing very good compared to the，previous state of the art。

but there is also something very，essential when you，work in fields that lack data like，biomedical。

is that you need to do a lot of data，augmentation so without data。

augmentation they couldn't write this，paper they do shift and rotations。

and they also have some methods to make，sure that their algorithm is robust to，deformation。

and gray value variation so these are，all data augmentation techniques。

any questions i have one question，which may have to do with uh what you，talked about uh。

with this like mirrored padding um but，their final output map，is a lower resolution than their input。

image，and i guess i thought the goal was to，like produce，something of the exact same resolution。

exactly so this is gonna be the exact，same resolution，that's the input that's the outputs。

that's where the，that's the area of the image okay and，you want to get the same。

image here but then on the boundaries，you're going to run into trouble。

because the field of view of this box is，bigger than，and that's where they've just mirrored。

it and flipped it yes，okay okay i see and they're doing，mirroring，and flipping because of their。

their，application domain it's a zero padding，wouldn't work in that sense。

okay did that one thing also that's，that's key is，it's tiled so i think you run it four。

times on like the input image and then，combine the output，because each one is like a subset of。

your image that you run it on，oh yes that's another thing uh，you don't take the entire image and。

input it you take，small types of it yeah thank you sir and，then you'll combine those like。

segmentation maps at the end，sort of that's because these pixels are，sort of independent。

actually the algorithm is treating them，as independent because of the summation，here。

and yeah yeah i think you you do just，add at the end to get your segmentation，maps uh。

in the like overlapping regions exactly，yeah，thank you anything i had a oh sorry。

yes go ahead i was going to ask about，the the distance functions。

because i've used unit before and ended，up using doing like uh，using uh a hyper parameter for the。

weights that i kind of just picked，um so i'm just curious if you go a。

little more in depth into these，distances and，you're taking per pixel the distance to。

the next nearest cell is that correct，exactly yes and so you end up but you，end up getting like zero。

for the interior it looks like from that，map it's gonna be，very close to zero it's not exactly zero。

but it's gonna be very close，so what you're doing is taking a pixel。

and measuring its distance to the，boundary，and the boundary is the next pixel and，that's gonna be b1。

and d2 is gonna be the distance of this，pixel and，not this cell but the cell next to it，that's d2。

and the idea is that near the boundaries，you care a lot about your probabilities。

being correct so you give them more，weight so that's the idea，yeah another interpretation i had was。

because there's way less boundary pixels，uh you don't want your network to like，forget them right。

it's the same thing yes and then these，uh sorry the nearest cell。

is of the same class or does it matter，the class of，like if you have two like yellow cells。

next to each other do you treat them as，different cells or the same one。

no they don't have to be the same just，to the next and it says here to the，nearest cell。

or to the second year so the type，doesn't matter，any other questions so is everything。

clear okay perfect。