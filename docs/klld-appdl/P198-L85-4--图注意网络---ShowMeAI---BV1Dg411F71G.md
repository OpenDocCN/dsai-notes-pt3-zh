# P198：L85.4- 图注意网络 - ShowMeAI - BV1Dg411F71G

You can extend this idea to graph attention networks these are the type of data that you're gonna to see corea sites here PM。

 you can have graphs which would be 3D meshes social networks telecommunication networks biological networks brain connectomes etc and then you can do graph attentional layers you have some vector representations for your nodes you are going to be F dimensional you have n nodes you have F as the size of your features and then you want to go to the next layer and give you some other features in another dimension you can do that by some weight matrices and then you can do self-at and self-at these types of concepts we saw before in terms of text so it's just a quick recap of the same framework applied to graph type of data first you need to know what is this score between onen and the other node and it's going to give you your attention coefficient。



![](img/b443e1809832f3613afde1d21e9c0409_1.png)

![](img/b443e1809832f3613afde1d21e9c0409_2.png)

![](img/b443e1809832f3613afde1d21e9c0409_3.png)

![](img/b443e1809832f3613afde1d21e9c0409_4.png)

![](img/b443e1809832f3613afde1d21e9c0409_5.png)

![](img/b443e1809832f3613afde1d21e9c0409_6.png)

![](img/b443e1809832f3613afde1d21e9c0409_7.png)

![](img/b443e1809832f3613afde1d21e9c0409_8.png)

![](img/b443e1809832f3613afde1d21e9c0409_9.png)

![](img/b443e1809832f3613afde1d21e9c0409_10.png)

![](img/b443e1809832f3613afde1d21e9c0409_11.png)

![](img/b443e1809832f3613afde1d21e9c0409_12.png)

This is a number from negative infinity to positive infinity you can do mask attention so that you are not paying attention beyond your neighbors maybe you want to pay attention to yourself and your immediate neighbors or you want to pay attention to yourself and two steps away from yourself and the rest of them you can mask so dont you don't pay attention to them and then you need to turn these numbers into actual numbers that add up to one because you have a budget of one for your attention how much node I is paying attention to node J for your scores you can take the representation of x y concatenate them so basically you're concatenating these two vectors multiply that by a matrix by a vector that's going to give you a single number and then that's your score once you have your score you push it through yourselfm you're going to add up to one and then you spread that budget of one of attention among your neighbors。



![](img/b443e1809832f3613afde1d21e9c0409_14.png)

![](img/b443e1809832f3613afde1d21e9c0409_15.png)

![](img/b443e1809832f3613afde1d21e9c0409_16.png)

![](img/b443e1809832f3613afde1d21e9c0409_17.png)

![](img/b443e1809832f3613afde1d21e9c0409_18.png)

![](img/b443e1809832f3613afde1d21e9c0409_19.png)

![](img/b443e1809832f3613afde1d21e9c0409_20.png)

![](img/b443e1809832f3613afde1d21e9c0409_21.png)

![](img/b443e1809832f3613afde1d21e9c0409_22.png)

![](img/b443e1809832f3613afde1d21e9c0409_23.png)

![](img/b443e1809832f3613afde1d21e9c0409_24.png)

![](img/b443e1809832f3613afde1d21e9c0409_25.png)

And then you push it through your nonlinearity。Visually speaking this is what happens you take H it's node I node J you multiply by the same matrix。

 you come up with a how much you need to pay attention。

 this is the leak value that you see up here you push it through yourm and that's going to give you your attentions you can have multi head attention like what you have for your text which is very simple you just concatenate multiple of these representations together and that's going to increase the size of your feature and then for the final layer you don't want the feature size to increase you want to keep it the same so rather than concatenulating for the final layer you just do averaging and then perhaps you want to get the probability out visually speaking this is what happens H1 is paying attention to itself through multiple heads this is one this is another head this is another head you's paying attention to H2 H3 H4 H5 h6 and then it's going to the next stage to give you。



![](img/b443e1809832f3613afde1d21e9c0409_27.png)

![](img/b443e1809832f3613afde1d21e9c0409_28.png)

![](img/b443e1809832f3613afde1d21e9c0409_29.png)

![](img/b443e1809832f3613afde1d21e9c0409_30.png)

![](img/b443e1809832f3613afde1d21e9c0409_31.png)

![](img/b443e1809832f3613afde1d21e9c0409_32.png)

![](img/b443e1809832f3613afde1d21e9c0409_33.png)

![](img/b443e1809832f3613afde1d21e9c0409_34.png)

![](img/b443e1809832f3613afde1d21e9c0409_35.png)

![](img/b443e1809832f3613afde1d21e9c0409_36.png)

![](img/b443e1809832f3613afde1d21e9c0409_37.png)

![](img/b443e1809832f3613afde1d21e9c0409_38.png)

representation for H1 prime and then graph attention networks you can use them for both transductive and inductive and then you can use it for representations and visualizations of your graph I think I'm going stop here and let you guys ask questions I had a couple of question on the previous the one of the induction paper think it was the previous one Yes so how about this we go backward we go from graph attention to the previous paper and then the previous ones Any questions from this like Okay perfect so what's the question about this it confused about what makes it good for dynamic graphs and compared comparison to the previous papers because if the graph is changing what you have to around the algorithm to get the correct embedding because the nodes change the labels so that's actually a very good question inductive versus transductive you learn your parameters。



![](img/b443e1809832f3613afde1d21e9c0409_40.png)

![](img/b443e1809832f3613afde1d21e9c0409_41.png)

At some point in time somebody gave you a graph and you use that graph to learn your parameters。

 you learn these ws but once you learn it you learned it。

 you learn it forever now let's say a new user gets added to your graph you don't have to retrain all you need to do is take that guy and see take a look at its neighbors so this new node is going to have an effect on its neighbors and you use that to update their representations and then as soon as the representation of one of these nodes change you look at its neighbors and you update the representation of those guys so it's just one pass that you go through your data and update the representation of each of one of your nodes。

So you don't do retraining that's the whole point doesn't answer your question Yeah that makes a lot of sense actually I had another one on this paper unless somebody else want to ask a question I guess you can go ahead cool so I'm bit confused about the the features part so say one node can have multiple features whether talking about like people's height or number of friends something like that so is the embedding vector or the correspond to those features or how does it work exactly with the features。

Yes， so if you have features to start with， if you have input features you can build upon them if you start with something that is just one hot vectors you are not making any assumptions about the notes there are just different ideass different people you don't know what features they might have but sometimes you might have features like in the case of the age you might know the age category of your users these guys yan that guys old etc you could perhaps know their sex you could perhaps know their web browser what they're using you could have different sorts of information so you can put that in a vector and that could be your initial point for the rest of your convolution so you don't have to start with one hot vectors you can start with more information you can also start with a degree of that note that could be one other feature does that answer your question Yeah definitely so it looks like the embedding。

Yeah。Method that we're doing here is more it has more information than what we did before with the degree matrix yes。

 it is more flexible it means that you can start from nothing or you can start from some information some features to begin with makes sense。

But if you don't have any information their first layer is going to be your embedding anyways。

 so as soon as you multiply a 1 hardd vector by a matrix you're picking up one of its rows or one of its columns and that could be your node representation so this is a deeper version of what we were doing with the random block type of node representations。

Because of an linearity and multiple layers， any other questions？

