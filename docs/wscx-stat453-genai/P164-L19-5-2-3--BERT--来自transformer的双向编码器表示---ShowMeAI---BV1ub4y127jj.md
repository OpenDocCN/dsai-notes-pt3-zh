# P164：L19.5.2.3- BERT- 来自transformer的双向编码器表示 - ShowMeAI - BV1ub4y127jj

Yeah， so in the previous video we discussed G version 1。

 which was a unidirectional transformer model where the pretrain task was the next word prediction。

 so it was processing the inputs in a left word fashion like from left to right and Bt is transformer that is a bidirectional one。

 so B stands for bidirectional encoder representations from transformers。



![](img/47dfa79930295ce943a8c8b46af04439_1.png)

So BRT was developed around 2018 by Google research and like I said before the main concept is this bidirectional nature。

 so the bidirectional pretraining using masking that is not going from left to right。

 but it's just randomly masking it's essentially a very simple concept I will have a slide on that illustrating how that works So the main architecture is essentially identical to the original Transer and GP so both both based on the original transformer paper with a multihead attention and so forth except。

Now that they have the spy direction。

![](img/47dfa79930295ce943a8c8b46af04439_3.png)

![](img/47dfa79930295ce943a8c8b46af04439_4.png)

![](img/47dfa79930295ce943a8c8b46af04439_5.png)

![](img/47dfa79930295ce943a8c8b46af04439_6.png)

![](img/47dfa79930295ce943a8c8b46af04439_7.png)

![](img/47dfa79930295ce943a8c8b46af04439_8.png)

![](img/47dfa79930295ce943a8c8b46af04439_9.png)

![](img/47dfa79930295ce943a8c8b46af04439_10.png)

![](img/47dfa79930295ce943a8c8b46af04439_11.png)

![](img/47dfa79930295ce943a8c8b46af04439_12.png)

![](img/47dfa79930295ce943a8c8b46af04439_13.png)

![](img/47dfa79930295ce943a8c8b46af04439_14.png)

![](img/47dfa79930295ce943a8c8b46af04439_15.png)

![](img/47dfa79930295ce943a8c8b46af04439_16.png)

![](img/47dfa79930295ce943a8c8b46af04439_17.png)

![](img/47dfa79930295ce943a8c8b46af04439_18.png)