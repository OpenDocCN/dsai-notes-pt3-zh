# P111：L14.0- 卷积神经网络架构【课程概述】 - ShowMeAI - BV1ub4y127jj

Yeah， hi， everyone。 I hope you are doing well。 I just uploaded the scores for the exam。

 I have to say I'm really positively surprised。 most of you did really well。

 So where does it leave us for the class now， So in the previous lectures。

 we covered really the basics of deep learning。 Of course there's always more to talk about。

 but I think this gives you a good foundation。 And yeah， remember。

 this is just an introductory course。 So we can't cover everything in in a single course。 But yeah。

 so in this lecture， I want to wrap up with conversion networks。

 there are some advanced concepts that are worth talking about。 And then in the next lecture。

 I want to talk about recurrent neural networks for text classification。😊。

So after the advanced concepts and the next lecture on the recurrent neural networks。

 I will then switch gears and talk about the generative models。

 so we will talk about auto encoders and generative adversarial networks and transformers。

So with that we have now this foundational deep learning stuff and then we will have also some generative modeling with deep learning hope that will give you a good yeah overview of the field overall and what does it mean for this class I mean we won't have another exam but yeah that doesn't mean you don't have to pay attention anymore because we will still have weekly quizzes and there will of course also be the class project。

However since yeah we don't have an exam anymore and we have kind of covered all the foundational skills。

 I think I will make the lectures I will at least try to make them a little bit shorter so that you have maybe more time in the week I will still aim for the 75 minutes。

 but rather below than above 75 minutes if possible。

So this lecture might be slightly I we will see how it goes。

 but I had originally like 80 slides and I think that was way too much so I cut it down to approximately 40 but yeah these topics I'm going to cover today I think really important and essential if you want to use convolution networks so I can't make it that much shorter However yeah I will focus on keeping it rather short so that you give get the introduction and maybe you can also yeah if you're interested in these topics study some of the papers I'm linking and there might be one day also a more advanced course where we can dive into these topics in more detail but with that let me get started。

Al right， let's get started by me giving you the overview of the topics I have in mind for today。

 So there are6， actually 8 topics overall I want to talk about。 So first。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_1.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_2.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_3.png)

I will start with the introduction to padding。 So padding is a concept that allows us to add pixels to the the input so that we can control the output size。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_5.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_6.png)

Of the convolution operation。 So when we have a convolutional layer。

 we can control the exact output size by using padding。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_8.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_9.png)

Then we will extend familiar concepts like dropout and batchome to the two dimensional settings when we have convols。

 So we talk about this as spatial dropout and spatial batch。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_11.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_12.png)

Then I will show you two common convolutional network architectures。

 So last week we talked about Leette 5 and Alexnet。

 which are kind of ancient architectures already in the grand scheme of things。

 today I want to talk about VGg16 and Resnet。 So they are also already like 5，6 years old。

 but they are still very yeah good in terms of the prediction accuracy on a variety of data sets。

 And I think these are nice architectures to show you that yeah by making deep new networks deeper。

 we can get slightly actually substantially better performance。

 but at some point even making these models deeper doesn't help。

 so we need have to use certain tricks and one of these tricks is implemented in Resnet。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_14.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_15.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_16.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_17.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_18.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_19.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_20.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_21.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_22.png)

Of course， there are many， many more architectures， but like I mentioned earlier。

 we can't discuss discuss here everything in this lecture。

 so I have to be a little bit selective and I think these are really good architectures to start with because they are also still very competitive in terms of the prediction performance。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_24.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_25.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_26.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_27.png)

So and then two， I would say not so important， but very interesting topics。

 so I will talk about how we can replace max pooling with convolutional layers。

 so in that way we can have a network that doesn't even have to have max pooling layers in that way。

 only having convolutional layers。

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_29.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_30.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_31.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_32.png)

But then at the end of each convolution network， as we have seen in the previous lecture。

 we always have these fully connected layers。 So the question is。

 can we also get rid of these fully connected layers？ Yes， we can。

 So that is the topic in this video where we'll talk about replacing the fully connected layers by convolutional layers as well。

 So these are kind of like thought experiments to help us also understand or think about convolution in a slightly different way than before。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_34.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_35.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_36.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_37.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_38.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_39.png)

And then here finally， the last topic is transfer learning。

 It's not very specific to convolution networks。 It's a general concept。

 It's the concept of training a network on a large data and then fine tuning it to a smaller target dataset。

 So this is especially useful if you yeah don't have a very large dataset available。 So in that way。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_41.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_42.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_43.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_44.png)

You can train your model on a larger related dataset to find its a good weight configurations。

 and then you can use that pretrain model to find unit on the dataset you care about。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_46.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_47.png)

If you would fit your model on the target dataset， you may not get good results if you don't yeah pretrained and that way we will also take a look at that。

 which can be particularly useful for your project class project why do we talk about it now that is because yeah that's something usually we often encounter in the context of yeah deep neural networks because there's the famous imagenet data consisting of millions of images So here I will show you VGG16 network pre-trained on imagenet that you can use and fine tune for your targeted assets if you are working on a image problem。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_49.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_50.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_51.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_52.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_53.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_54.png)

![](img/e03851d19ee3cb3043bd494d3a1a3ab0_55.png)

Okay， so these are the topics。 and in the next video， I will start with patting。



![](img/e03851d19ee3cb3043bd494d3a1a3ab0_57.png)