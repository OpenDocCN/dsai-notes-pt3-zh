# P72：L33.3- 单图像超分辨率 - ShowMeAI - BV1Dg411F71G

So these papers I'm going through them really fast because。

We already have a very solid background with convolutions at this point we are really solid we covered a lot of topics so you have a solid foundation you are going to hear SISR a lot that it stands for single image super resolution the idea of this paper and the next one is that when you do bycuic interpolation of your low resolution image that's already a good approximation of the high resolution one so rather than taking it and pushing it through a bunch of nonlinearity try to learn the residual and what it means is that you take your low resolution image that is that is pushed through a bi linear or bi cubic interpolation and then in the end you just add it to the output of your network and then you are making the life of your network much easier so it has to just learn the difference between this image and the input image so this is another way of thinking of Y residual networks where。



![](img/ce62188592ffea17e0c10d7e2da53719_1.png)

![](img/ce62188592ffea17e0c10d7e2da53719_2.png)

![](img/ce62188592ffea17e0c10d7e2da53719_3.png)

![](img/ce62188592ffea17e0c10d7e2da53719_4.png)

![](img/ce62188592ffea17e0c10d7e2da53719_5.png)

![](img/ce62188592ffea17e0c10d7e2da53719_6.png)

![](img/ce62188592ffea17e0c10d7e2da53719_7.png)

![](img/ce62188592ffea17e0c10d7e2da53719_8.png)

Powerful and we're working in practice this is another way of seeing it when it comes to super resolution and if you do that most of these features are going to end up being zeros or close to zero and then learning then is not that hard for instance its last one has it has only a few nonzero entries Why is that because these are after value so value is going to kill most of them。



![](img/ce62188592ffea17e0c10d7e2da53719_10.png)

![](img/ce62188592ffea17e0c10d7e2da53719_11.png)

![](img/ce62188592ffea17e0c10d7e2da53719_12.png)

![](img/ce62188592ffea17e0c10d7e2da53719_13.png)

set down to zero so the idea is not that complicated but deep learning is a field of simple ideas at work in practice and once you do that you can actually learn we are actually doing the residual learning you can use a high learning grade because you can actually have gradient clipping and then you can also have multiscale training for instance if they can image a high resolution image you can scale it down by two you can scale it down by four you can scale it down by eight and these are going give you different scales that you can train the network on all of them and the second idea is that actually going deep is going to help there were some other papers before these paper that we're claiming that apparently deeper neural networks are not helping super resolution but then this paper came along and said if you do this this way you learn the residuals then it's going to actually help this is the idea of multi scale。



![](img/ce62188592ffea17e0c10d7e2da53719_15.png)

![](img/ce62188592ffea17e0c10d7e2da53719_16.png)

![](img/ce62188592ffea17e0c10d7e2da53719_17.png)

![](img/ce62188592ffea17e0c10d7e2da53719_18.png)

![](img/ce62188592ffea17e0c10d7e2da53719_19.png)

![](img/ce62188592ffea17e0c10d7e2da53719_20.png)

![](img/ce62188592ffea17e0c10d7e2da53719_21.png)

![](img/ce62188592ffea17e0c10d7e2da53719_22.png)

![](img/ce62188592ffea17e0c10d7e2da53719_23.png)

![](img/ce62188592ffea17e0c10d7e2da53719_24.png)

It's the same network so you're not training a different network for a scale of two。

 you're training your network to do all of these escapes at the same time and that's the ground truth that's what the network is that's the resolution one and that's what the network is predicting this is the low resolution images this is what the network is giving you and it's only one network for all of these scales so that's impressive。



![](img/ce62188592ffea17e0c10d7e2da53719_26.png)

![](img/ce62188592ffea17e0c10d7e2da53719_27.png)

![](img/ce62188592ffea17e0c10d7e2da53719_28.png)

![](img/ce62188592ffea17e0c10d7e2da53719_29.png)

![](img/ce62188592ffea17e0c10d7e2da53719_30.png)

You can compare it with SRCNN now this is Larryrry。

 this is Mosha but the loss function that they' are using is not a perceptual loss it's just the L2 loss so sometimes the contributions could be on the last side of deep learning it could be on the model side of deep learning so this one is on the modeling side it could be on the evaluation side etc on the data side and you can study the effect of depth yes actually going deeper is helping this network for different scales。

