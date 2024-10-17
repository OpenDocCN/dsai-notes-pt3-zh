# P55：L28.1- 有限样本表示性 [续] - ShowMeAI - BV1Dg411F71G

We are still trying to visualize and understand neural networks in particular convolutions and try to visualize and understand them。

Last session we had some discussions about the results of this paper and I think it's a good idea to at that so whatever are we think there was this trend in deep learning that neural networks generalize really good from training to testing。

 but people were spectacle。And the reason was that these neural networks are heavily parameterized it means that they are intuitively able to overfi the data。

 the training data and there is no reason for them to generalize to unobserved observations but then people came around and they try to justify it they said maybe neural networks generalize well because there is something special about their architecture maybe there is something special about convolutions that' preventing them from overfitting and this paper came around and said okay let's assume you're right let's assume that the model architecture in itself is a sufficient regularizerizer so it's gonna to prevent overfitting let's assume that's correct and now let's create a counterex to that and the counterex is this fitting random labels and random observations should be really hard because this is just noise。

you are trying to fit and fitting a noise is really difficult。

 And if there is something special about neural networks architecture。

 they shouldn't be able to fit noise。 But what happened is that they train this network on random labels and even random pixels。

 Yes， it is harder to fit them。 it's going to take longer but eventually you're going to overfit noise What does it mean it means that there is nothing special about a neural network architecture preventing it from overfitting So that couldn't be an explanation So there is nothing special about neural network architecture or it isn't sufficient it isn't a sufficient regularizer There was another explanation。

 which was saying that neural networks generalize because we regularize them either explicitly or implicit but then the same thing happens when you do regularization。

 you're still able to overfit noise you're able to overfit noise。

 It means that even explicit regularization。 It isn't sufficient。

For controlling the generalization error， it means that they can still overfi even in the presence of random crops and VTK and these sorts of explicit regularizations there is an implicit regularization that one seems to be helping more and that's when you are having a validation data set and you take a look at your error on the validation data and whenever it starts to go up。

 you stop your algorithm， you stop the training as soon as you see that your error on the validation data is going up for a couple rounds of training。

 you're gonna stop it and say let's stop here the network is overfitting that one seems to be helping the most but then the paper took it even further it said yes。

 that's a counter example this is another counter example but actually neural networks are able to overfi and that proof I can give you a neural network with two layers。

With a radio activation and given enough capacity it's going to overfi and that's proof that neural networks can overfit indeed so that's an impressive paper any questions about this before I move on to the next one。

So the next paper is going to be the last paper that we cover when it comes to visualization and understanding。

 but I want to make sure that everything is clear before I move on， okay perfect。

