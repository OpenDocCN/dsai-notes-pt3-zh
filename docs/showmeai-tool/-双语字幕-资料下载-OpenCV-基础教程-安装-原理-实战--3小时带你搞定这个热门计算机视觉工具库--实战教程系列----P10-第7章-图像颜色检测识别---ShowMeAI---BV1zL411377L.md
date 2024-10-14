# 【双语字幕+资料下载】OpenCV 基础教程，安装、原理、实战， 3小时带你搞定这个热门计算机视觉工具库！＜实战教程系列＞ - P10：第7章：图像颜色检测识别 - ShowMeAI - BV1zL411377L

![](img/07947795d9caed2cc20e4ef5ab09c052_0.png)

![](img/07947795d9caed2cc20e4ef5ab09c052_1.png)

。So here we are importing our library and we are importing an image in the resources folder by the name Labo。pG。So we are just displaying it using the IM show function and we are adding a delay so that it stop。 it does not disappear。So this is our image， so our task will be to detect the orange color in this image。So first， we are going to convert this into HSV space， so we will say image。

HSV is equals to now as you remember， we have been using the CVT color to convert it into grayscale。 so we will use the same function， C2。Color to convert it into HSV。 so we will say that we want to convert our image and we want it to be c2 dot color。Color underscore。BGR to HSV。So this will convert the image into HSV， we can copy this。

 and then we can check out our new image。So here we have our new image， which is the HSV。 and I did not write a new name that's why it's overr HSV。So this is the original and this is the HSV， so now we need to define some color values。 some ranges in which we want our color to be so we will define the hue。

 the saturation and the value limits and within that limit if the image region falls within that color range we will grab that so let's do that。SoBut one thing to note is that we do not actually know what are the minimum and maximum values that we need for this particular orange color。

 so what we are going to do we are going to introduce something known as track bars that will help us play around with the values in real time so that we can find the optimum minimum and maximum values of our color。So to introduce track bars， we are going to create。Let's create it on the top。Here。

 so we are going to create a new window by， let's say by the name track bars。 so we will say c2 dot named window， we will call it track。Mars and。Then we are going to resize it so that it is not。We're looking and we will write here track。Bs now this name should be the same， so just keep in mind not to do any spelling mistakes here and then we need to define the size。

 let's say 640 by。2，40。Then we are going to create our first track bar， CB2 dot。Create now we are using the create track bar function。 Now keep in mind that the T here is capital so first we will define what value are we going to change using this track bar so。This is just a name so we can write anything。So the first value we will be changing will be the h minimum。

And next we are going to define which window are we going to put this track bar on so we have already named our window as track bars so we are going to use that now we have to define the the current value so when the script runs what will be the initial value that it will run with so we will put it at0 and what will be the maximum value of our h now as you know here has a maximum value of 360 now but we do not have 360 here in。

Open C， we have till 1，79， which is basically 1，80 values。So we will put 179 and at the end we have we have to call a function which will run every time something changes in the track bar so every time the user changes the track bar it will call this function but we are going to get the values in another way I will show how we will use that later on but for now we do have to define this function so but we can say this is an empty function and。

At the top， we can define。Empty。And we can say that just pass。That's it。So that will pretty much do nothing， so that's how you create the track bar so all you need to do now is to run and see what happens。Whoopps。Okay， so once we run it， we are getting this error which say c2。t resize。 it's not actually resize， it's resize window。So we will resize window and let's play that again。

And we should have a yeah， we have the track bar here so we have the h minimum and you can see that the value is basically going okay。 we are missing yeah we just need to put here something it will take in an argument and that's it。We will run that again and if we use the trackbar again。 so now you can see that the U value is moving around。And the minimum is zero and the maximum is 179。

So how many values do we need， we need six values because we will have h minimum， then h maximum。 then saturation minimum， saturation maximum and value minimum and value maximum。 so we will copy this。A couple of times。And we will just change this to Max。And then we will change this to。Sauration。Sauration and again， we will change this to max。

And minimum will stay the same。 This will be value。 This will be value， and this will be max。So now these values they range from  zero to2，5，5。So we will write 255 and the initial values。 we will keep them the same， but for the maximums we will keep them at maximum。 so here we will put 179 here we will put 255 and here we will put 255。So if we run that now。

 we will have six track bars that we can move around。So that is good。😔，Yeah， that's pretty much good。 So what we will do next is we are going to read these trackbar values so we can apply on our image。So here we are going to get our values using the get track bar position function。 so we will say our edge minimum basically is equals to C2。CV2 dots gets。Track bar。Position。

 there you go。So then we will write which which value are we talking about now the spelling here have to be exactly the same。 so we will write this here and then we are going to say to which track bar window does it belong？

So our window name is track bars。 So I'm going to copy this。And I will paste this here。So to confirm。 we can just print。Edge underscore minimum。Now， in order to get the value。What we need to do is we need to put it in a loop because we have to run it again and again to keep getting that value。 So instead of the image we will have to change it to a webcam or。

Just add a loop so we can write here while。Shiwu。We want this to keep running。And we will put this in as well。 so instead of adding complexity。 we can just put one here and that should do it。So right now we can see the value is0。And then if we change it， you can see the value keeps changing。Right。So next。

 we are going to apply this to all of them。And we will copy this so that we have all the values。 so we will do it again five times。And this time around， this will be max。Then minimum and max and then minimum and max。Then we will have the saturation。Okay。 then we have the saturation， then the value。And then the value。So that is about that。

 and then we will write here max and here will be saturation。Sauration， and then max。Here will be minimum value， and then value。And then， max。So we can print all of them out just to see just to make sure that if it is correct。 we will just say H minimum。Then。Hdge， maximum。Then we will say S minimum。S maximum than value。Value。

 minimum and value。Maximum。So let's see how that works out。😔，So there we have it 017902550 and 255。 so if I change my values you can see the track bar actually changes these values in real time。So now that we have these minimum and maximum ranges of the hue saturation and value。 we will use these values to filter out our image so that we get that particular image in that range。

Particular color in that range。 so now we will create a mask， we will say that the mask。Is equals to Cv2 dot in range。So we are creating a mask that is in the range of these colors。 So which image are we talking about， We are talking about the。HSV image and then we have to give it the minimum and the maximum range。

 so we will say this is the lower limit and we will say。This is the upper limit。Now we need to define this lower and upper limit， so we will right here， let's do the lower first。 lower is equals2。We will create a Ny array， so let me just add that here。Import nuy。As MP。Now down here， we are going to add a N array so N。Dot array。

And then we are going to create the minimum array， so which is edge minimum。And then we have S minimum。And then we have the value minimum。唔发。他就没了么。The same way we are going to do for the maximum， so we will say upper is equals to nu pi dot array and we will add our maximum limits。Which is Em。Then， S max。And then， vmax。Okay， so this will give us the mask。

 so basically what it will do， it will filter out and give us the filtered out image of that color。So let's see how that looks like。Or no need to copy that。 we can just paste this here and we can say this is the mask and this will be。😔，Mask。So let's run that and there we have the mask here we have the original image and here we have the track bar。

So if I move this around， you can see how。The value of how the image changes。So we want to keep all the colors that we don't want as black and we want to keep the color that we need in white。 So if I was to detect the orange。I would say that is pretty much good。So I recommend keep changing the values， try to keep it smoother and smoother。Eventually。

 you will get some good results。 So now that we have these。These values。 what we can do is we can put them as our initial values。 so we have 019 110 to 4153 and 255 so we can go back here。We can still open up our track bar。And we can go up here。Let me keep it on the side， and I can just。See what it is。

 so this is zero and then this is 19， this is 110。And this one is 2，40。Then we have 153。And then 255。 So now if I run this again by default， I will get the mask。![](img/07947795d9caed2cc20e4ef5ab09c052_3.png)

Right， and next what we can do。![](img/07947795d9caed2cc20e4ef5ab09c052_5.png)

Is we can get our result， which will be our original image。 so instead of getting this black and white mask， we can get the actual colored parts。 the orange color over here。So how we can do that is by creating using this mask。 we will create a new image so we can say image。Results。Is equals2。

We are going are going to use the and operation， so we have the bitwise。And Op。 which will add two images together to create a new image。It is basically checking both the images and wherever the pixels are both present。 it will take that as a yes or as a one。And it will store that in the new image。

 So what it does is we are going to say that we have our。Original image that we want to use。And our new image will be also like our original image， but with a mask applied。Which is our mask。 which is。The one we created before。So let's look at the image result。Image result。 and we should change the name here。

![](img/07947795d9caed2cc20e4ef5ab09c052_7.png)

Let's run that。And there you go。 So now we have the colored image， So if you did not get that。 basically we are we are checking these two images。![](img/07947795d9caed2cc20e4ef5ab09c052_9.png)

The mask and the original image， and we are checking wherever we have these white pixels we are getting from this image and creating a completely new image from it。![](img/07947795d9caed2cc20e4ef5ab09c052_11.png)

So that is what we are doing。So one thing we can do here is to add our function from our previous chapter in which we joined the images so that we don't have to play with all these images again and again。 so if we go back to。Our previous chapter， we have the stacking function。

 we can copy that and bring it here。Yeah， let's bring it here and then now we can go down。 this is the by the way， the tracking function， so sorry the stacking function。 so it is stack images。So we can go down and instead of showing all these images separate。 we can just show the stacking image。What we can say is that。Sttapped。Or we can say I M G stock。

 I M D stack is equal still。Now we have to write our function， which is。Stock images。We have to define the scale， the scale。 Let's keep it at 0。6。 And then we have to define the array of images。 So we are going to。Put here。We are going to put here the images that we need， so we can put。Two images and then two images。 Okay。

 so we will create IMG and then IM G HSV。 And then in the new role， we can create。We can add the mask and then the image。Result。And then we just need to display the final image。So we can stay say start。Images and we will write here IMD style。So let's remove all of these and we can play again。

And there you go so now so now we have a neat image with all these images stacked up and showing us the values altogether。 so now we can have the track part on one side and we can see the results directly applied in real time。So， let's。Check what the results are。 and yeah so。So that's how you can detect colors。

![](img/07947795d9caed2cc20e4ef5ab09c052_13.png)