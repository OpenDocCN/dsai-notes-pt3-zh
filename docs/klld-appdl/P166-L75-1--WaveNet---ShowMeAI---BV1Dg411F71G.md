# P166：L75.1- WaveNet - ShowMeAI - BV1Dg411F71G

So far we were doing discriminative models somebody would give us speech and the task was turning that speech into transcription。

 transcribe your audio we saw only one example for generative type of models generating speech or speech synthesis this is another one previously we were using a Gaussian mixture model when we were working with GRU gated recurrent units the idea here is can you actually treat wave in a discrete fashion and use softmax that's the big idea this is your wave Per time step like the time step here you have a continuous variable and that's why people said maybe a Gausian mixture model is a good model for this can we actually treat these continuous signal and discrete and use Somax that's your waveform and your task is generative given the history gene the next。



![](img/5de85f53e24c9a3e69b42554ccc50d04_1.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_2.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_3.png)

This one we are gonna model by a stack of convolutional layers Xt is a sample from your audio and we want to put a categorical distribution over the next value you cannot use any type of convolution because this is a predict next word predict next sample we are going to use causal convolution which is not going to look into the future is's always going to look into the past and this is going to have a receptive field of five why because one。

2，3，4，5 samples in your input are impacting your output and where is this5 coming from you have one。

2，3，4 layers your filter size is two for each one of these guys your filter size is two and that's how you're going to get five I there a way to look far into the past is there a way to increase the receptive field and for those of you who took part one you know that for。



![](img/5de85f53e24c9a3e69b42554ccc50d04_5.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_6.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_7.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_8.png)

Semantic segmentation， we were using a technique called dilated convolutions or At convolution。



![](img/5de85f53e24c9a3e69b42554ccc50d04_10.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_11.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_12.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_13.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_14.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_15.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_16.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_17.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_18.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_19.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_20.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_21.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_22.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_23.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_24.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_25.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_26.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_27.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_28.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_29.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_30.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_31.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_32.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_33.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_34.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_35.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_36.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_37.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_38.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_39.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_40.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_41.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_42.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_43.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_44.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_45.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_46.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_47.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_48.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_49.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_50.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_51.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_52.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_53.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_54.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_55.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_56.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_57.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_58.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_59.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_60.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_61.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_62.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_63.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_64.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_65.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_66.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_67.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_68.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_69.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_70.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_71.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_72.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_73.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_74.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_75.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_76.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_77.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_78.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_79.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_80.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_81.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_82.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_83.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_84.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_85.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_86.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_87.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_88.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_89.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_90.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_91.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_92.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_93.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_94.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_95.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_96.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_97.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_98.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_99.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_100.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_101.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_102.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_103.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_104.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_105.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_106.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_107.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_108.png)