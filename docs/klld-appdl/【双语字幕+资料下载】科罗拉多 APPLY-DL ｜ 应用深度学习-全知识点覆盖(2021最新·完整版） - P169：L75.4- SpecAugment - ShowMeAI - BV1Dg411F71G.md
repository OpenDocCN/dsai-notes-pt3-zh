# P169：L75.4- SpecAugment - ShowMeAI - BV1Dg411F71G

In that case let's move on， this paper is gonna to be very fast。

 this is about data augmentation we know that data augmentation helps images it helps text is it going to help speech as well for the cases when you have a smaller data sets smaller size dataset sets maybe for English you have a lot of speech data but for other languages maybe you don't have as much data we are going to take a look at our log my Spectrogram that's our data this is without any augmentation and we are going to do three types of data augmentation one is time warping what is that you pick six points six anchor points on your spectrogram and then you are going to take one of these points at random in between in between and then you are going to shift it to the left or to the right and that's going to warp your speech and this is going to have some parameters like Tau is the size of your spectrogram。



![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_1.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_2.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_3.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_4.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_5.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_6.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_7.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_8.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_9.png)

W is going be the time war parametermeter， It's a hyperparameter that you choose and a W is just some random number。

 Its uniform from zero to w and it's going to tell you how much you want to go left or right that's warping in terms of implementation at least in Tensorflow there is this sparse image warp there is this function that you can use you apply it on your data set what next frequency masking is that you're gonna mask visually speaking it's very simple you are going mask this part of your frequency but then when you want to implement it。

 you want to mask F consecutive frequencies so this is going be the size F this is F that you choose at random from a uniform distribution and F is a hyperparameter that you choose capital F F0 is where you're gonna cut and new is the number of male frequency channels but visually speaking。



![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_11.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_12.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_13.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_14.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_15.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_16.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_17.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_18.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_19.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_20.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_21.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_22.png)

It's not that hard that's what you're doing You can do time masking you mask a portion of your time What happens if you don't have data in that regime and then you're going to have different types of augmentation policies you can do this multiple times for instance you can mask multiple frames and these are your data sets like library speech basic library speech double switch or mild switch or strong and you can do different types of masking on them W is for warping F is for frequency the hyperparameters of your frequency Tu is for your tau masking time masking MF is the number of frequencies that you're going mask one to the probability of doing that mask or not doing it and mt is the number of time mask that you're going to apply in the end you're going to get some figures like this you can do multiple of them and these are the type of augmentations。



![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_24.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_25.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_26.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_27.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_28.png)

![](img/6eaeb94bacae4f8d3d1b3b1bb6170842_29.png)

are going to happen to your data I think I'm going to stop here and the rest of it I'm going to cover next session or those of you have questions I'll be around。

