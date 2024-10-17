# P195：L85.1- 图卷积网络 - ShowMeAI - BV1Dg411F71G

I think I'm gonna move to the next one and then you can ask question at least I can start it again our problem is classifying nodes documents in a citation network and then your labels are available for a small portion of your data you have undirected graph these are your nodes you have some edges and then you can introduce the adjacency matrix if one node is adjacent to another one you're going to read off the weight on that edge connecting those two nodes and then you're going put it in this matrix and then you can create a degree matrix for a and then you can introduce the unnormalized graph lo so this is going to be clear as soon as I give you an example this is the example you have one。

2，34，5，6 so the size of your adjacency matrix is going be six by6 one is connected to two so you're going to put a one here one is connected to five you're going put a one here these are on。



![](img/5027d630fe054ae5a51234566773a24a_1.png)

![](img/5027d630fe054ae5a51234566773a24a_2.png)

![](img/5027d630fe054ae5a51234566773a24a_3.png)

![](img/5027d630fe054ae5a51234566773a24a_4.png)

![](img/5027d630fe054ae5a51234566773a24a_5.png)

![](img/5027d630fe054ae5a51234566773a24a_6.png)

![](img/5027d630fe054ae5a51234566773a24a_7.png)

![](img/5027d630fe054ae5a51234566773a24a_8.png)

![](img/5027d630fe054ae5a51234566773a24a_9.png)

![](img/5027d630fe054ae5a51234566773a24a_10.png)

![](img/5027d630fe054ae5a51234566773a24a_11.png)

waighted if they were weighted you would put the corresponding weight here and then the degree matrix you just add up the rows。

 the entries of each row so this is going to give you a two here this is going to give you a three here a two here etc and then the graph lo plusian is this matrix minus this matrix going to give you a two three negative1 negative1 etc Why do you call it graph loluian so I want you guys to click on this link and look at the interpretation of the graph lapluian as a discrete loluian operator or discrete lo plus operator。



![](img/5027d630fe054ae5a51234566773a24a_13.png)

![](img/5027d630fe054ae5a51234566773a24a_14.png)

![](img/5027d630fe054ae5a51234566773a24a_15.png)

![](img/5027d630fe054ae5a51234566773a24a_16.png)

![](img/5027d630fe054ae5a51234566773a24a_17.png)

![](img/5027d630fe054ae5a51234566773a24a_18.png)

![](img/5027d630fe054ae5a51234566773a24a_19.png)

And the intuition is if there is heat structure on the graph what is the heat you can associate heat for each one of these nodes and as soon as you have heat。

 sometimes the heat cannot transfer from one to6 but it can transfer from one to5 and that's why you're calling this graph La plusian and that's the interpretation there is heat associated to each vertex so I think I'm gonna to stop here。

 let you guys ask questions and then we can continue the rest next session So is this sort of saying that the heat since there's like a negative one at this01 location in the delta matrix that like heat is like moving away from node one towards node two actually for that one you need to look at the equation so I want you to click on that it's a little bit subtle so you cannot look at this and interpret this but the idea is that if there is heat。



![](img/5027d630fe054ae5a51234566773a24a_21.png)

![](img/5027d630fe054ae5a51234566773a24a_22.png)

![](img/5027d630fe054ae5a51234566773a24a_23.png)

![](img/5027d630fe054ae5a51234566773a24a_24.png)

![](img/5027d630fe054ae5a51234566773a24a_25.png)

![](img/5027d630fe054ae5a51234566773a24a_26.png)

![](img/5027d630fe054ae5a51234566773a24a_27.png)

![](img/5027d630fe054ae5a51234566773a24a_28.png)

![](img/5027d630fe054ae5a51234566773a24a_29.png)

![](img/5027d630fe054ae5a51234566773a24a_30.png)

![](img/5027d630fe054ae5a51234566773a24a_31.png)

![](img/5027d630fe054ae5a51234566773a24a_32.png)

Let's call the heat P1。 And there is heat at this other node P5。

 The heat is gonna get transferred from node1 to note 5。 according to the difference between the two。

 So it's gonna be P 5 minus v1。 Okay， or it's gonna be P2 minus v1 There is not gonna be any heat transfer from1 to 6 because there is no edge between them。

 as soon as you write down your math。 a little I don't know，6 lines of simple math。

 you're gonna see that the lo plus and is gonna show up。

 this matrix is gonna show up D minus a in a low plus equation。 Okay， so just read this。

 it's not difficult。 it's gonna take you exactly to the location that you need。

 I was also wondering if I could ask a question from the wine paper Sure， was much the question Yeah。

 I wasn't sure。

![](img/5027d630fe054ae5a51234566773a24a_34.png)

![](img/5027d630fe054ae5a51234566773a24a_35.png)

![](img/5027d630fe054ae5a51234566773a24a_36.png)

![](img/5027d630fe054ae5a51234566773a24a_37.png)

![](img/5027d630fe054ae5a51234566773a24a_38.png)

![](img/5027d630fe054ae5a51234566773a24a_39.png)

![](img/5027d630fe054ae5a51234566773a24a_40.png)

![](img/5027d630fe054ae5a51234566773a24a_41.png)

![](img/5027d630fe054ae5a51234566773a24a_42.png)

![](img/5027d630fe054ae5a51234566773a24a_43.png)

So when we're talking about the second order proximity and we talk about the context of other vertices so is UI bar the context of verticie V and that's just like the average of the encodings for its neighbors so I don't want you to interpret the bar here as an average so don't do that okay what I want you to do is each vertex is going to have two roles you either conditioned on it so when you are conditioning on it it's going to have the role of itself so you're going to put UI here but if you are actually writing the probability on a vertex conditioned on something else then VJ is going to act as the context of VI and because it's as the context of VI you have a different vector corresponding to that so you can think。

This way， VJ can have two identities， one is as a context of VI， for instance， as the brother of VI。

Or as I don't know Jackson himself yeah okay thank you yeah sure so I wanted to ask how I use the embeddings in a like downstream task so like in language there's a natural sequence and I learn my embeddings for a single language and then I get you know a new sentence coming in and I can just feed this into you know your current neural network or like a transformer I guess like in graphs there's no natural sequence for me to like feed it in and then on top of that every time I get a new graph I'm going to relearn the embeddings so I'll have a new set of embeddings for every single graph I see so I was kind of wondering like how you use this in down the embeddings you learn in downstream task so that's a very good question and that depend on the task that you want to do okay for instance node classification for a task like node classification your data or your notes okay and then you have label for some of your notes for。

In instance， there is a label for this particular node or another label for this guy but you have no label for the other data in your data so you can go ahead and classify this node and what is your training data is' just your embeddings for these data that you have for those nodes these are the input the output are going to be the corresponding labels and then you train a simple classifier maybe logistic regression and that once have your model you can apply that to other nodes so I guess I'm just thinking if I had you know perhaps a new graph and I can't say how many notes are going to be labeled ahead of time so I can't you know fix that so I may all have like a return network I'll be reading in the embeddings all the node that are labeled。

Do I just pick a random order to pass the nodes and the inbeddings of the nodes into the network to classify the other nodes？

So I think there is a little bit of confusion here and the confusion is what is your data and that's perfectly fine your data could be multiple graphs and then you are classifying your graphs for instance you have graph one graph2 graph3 graph four graph5 and then these are your data or your data could be the nodes in a single graph for instance the nodes on Facebook the users of Facebook or the users of YouTube okay videos on your YouTube so those types of tasks I don't need to worry about generalizing to new graphs all I'm doing is learning embeddings for this particular graph and I learn application task for the embeddings of that particular graph exactly yes for instance you have your network it's LiedIn you have your graph you know who is connected to who you know your graph structure but then you want to know should I advertise。

This particular product to this particular user or no okay that's a classification yes or no。

 you classify and then if it's yes， you show that the a show that person the add so I guess the task that I have in mind is a little strange I'm thinking of classifying a graph so someone gives me a graph and I tell you what type of graph that is Yeah I was thinking how to use the embeddings to produce that label because now I need to generalize a across graphs and I'm producing a completely different embedding for every single graph I see that should be fine that one we are gonna cover so don't worry about it Okay look at there so if your task is graph if your data or graphs graph one graph2 graph3。

 we are gonna see an example but for now if you want to actually do that task it is also possible from what we have done so far you need a representation peri graph okay。

 if you have this graph here。And you have a vector for each one of your nodes a simple idea is just to add all of them up they have the same dimension just add them up that's gonna give you a single graph single vector for your entire graph so you can think of it as global pooling okay single vector for your entire graph and then you're gonna this is your data now okay and just because like I'll be using the same process to learn the embeddings every time the hope is that when I see a new graph learn the embeddings through that particular graph and then some of the embeddings Ill have something that my classifier can still recognize Yes okay so yes with graph you have to be careful with what is our data so your data could be these nodes the red eyes or it could be the entire graph which is your data and we have methodology for both of them okay that me sense All right thank you so what haveve been done so far so far we have a graph and we were turning it turning its nodes into vectors and we were。

Wing ideas from text and textual data but then is there a way to make things deeper and perhaps use convolutions。

 perhaps have multiple layers of operations like what you do for deep learning because previously it was just a single layer and it's a linear model something like node tove it's a linear model Can we make things non- nonlinearar What is the task we still have a single graph and our data our data points are going to be the nodes in that graph and for some of the nodes we have labels for some of them we don't have any labels and that's why it's called semiupervised So we are doing semiupervised classification under the nodes of a single graph and then in the next slide I'm going extend this to multiple graphs。



![](img/5027d630fe054ae5a51234566773a24a_45.png)

![](img/5027d630fe054ae5a51234566773a24a_46.png)

![](img/5027d630fe054ae5a51234566773a24a_47.png)

![](img/5027d630fe054ae5a51234566773a24a_48.png)

![](img/5027d630fe054ae5a51234566773a24a_49.png)

![](img/5027d630fe054ae5a51234566773a24a_50.png)

![](img/5027d630fe054ae5a51234566773a24a_51.png)

As an example， you could be classifying documents in a citation network and you have labels for some of those documents。

 so a quick recap of what we covered last session， this a graph。

 a graph has a bunch of as a set of nodes， set of edges， the nodes you can have n of them。

 this is the size of your data set and then you're going to have edges that are connecting two nodes together。



![](img/5027d630fe054ae5a51234566773a24a_53.png)

![](img/5027d630fe054ae5a51234566773a24a_54.png)

![](img/5027d630fe054ae5a51234566773a24a_55.png)

![](img/5027d630fe054ae5a51234566773a24a_56.png)

![](img/5027d630fe054ae5a51234566773a24a_57.png)

![](img/5027d630fe054ae5a51234566773a24a_58.png)

And then we introduce the adjacency matrix this is gonna to be clear when I show you an example then you can define a degree matrix and a you can subtract a from the degree matrix and that's something called graph lap plusium let's see this is your adjacency matrix corresponding to this graph it is telling you that node1 is connected to node2 node one is connected to node5 if your edges where weighted you would put the weight here and for instance node2 is connected to node5 which is you're putting the one here etcter。

 so that's your adjacency matrix it says sparse matrix you're gonna to have a lot of zeros and then for D the degree matrix you are just summing up these rows and putting those numbers under the diagonal of another matrix so it's going to be two。

3，2，3，3，1。

![](img/5027d630fe054ae5a51234566773a24a_60.png)

![](img/5027d630fe054ae5a51234566773a24a_61.png)

![](img/5027d630fe054ae5a51234566773a24a_62.png)

![](img/5027d630fe054ae5a51234566773a24a_63.png)

![](img/5027d630fe054ae5a51234566773a24a_64.png)

![](img/5027d630fe054ae5a51234566773a24a_65.png)

![](img/5027d630fe054ae5a51234566773a24a_66.png)

![](img/5027d630fe054ae5a51234566773a24a_67.png)

![](img/5027d630fe054ae5a51234566773a24a_68.png)

And then you create the Laplian graph Laluian which is this term minus the other term which is going to give you this matrix here Why do you call it graph Laplian what is the interpretation where is the name coming from。

 you can have heat you can associate heat for each of these vertices。

 heat at vertex 1 heat at vertex5 etc， and then you have a heat distribution over the entire graph and then as you write down the physics of the problem like the heat is going to get transferred proportional to the difference between heat at 5 and heat at one then you are going to end up with this lapplian matrix so as you click on this link it's going to take you and give you more intuition of where the name is coming from。



![](img/5027d630fe054ae5a51234566773a24a_70.png)

![](img/5027d630fe054ae5a51234566773a24a_71.png)

![](img/5027d630fe054ae5a51234566773a24a_72.png)

![](img/5027d630fe054ae5a51234566773a24a_73.png)

![](img/5027d630fe054ae5a51234566773a24a_74.png)

![](img/5027d630fe054ae5a51234566773a24a_75.png)

![](img/5027d630fe054ae5a51234566773a24a_76.png)

![](img/5027d630fe054ae5a51234566773a24a_77.png)

![](img/5027d630fe054ae5a51234566773a24a_78.png)

![](img/5027d630fe054ae5a51234566773a24a_79.png)

We want to do semiupervised you have label for some of these data and you don't have data for the rest of them so on some of your data you have supervision on some of them you don't have classically this is what people would do they would write the loss function is a classification loss function plus a regularization term and that regularization term is going to take into account the adjacency matrix that this node is adjacent to the other node and there is gonna to be a mean squared error you have a neuraln network that is outputting a class for the data that you have a class for and for those that you don't have a class you just regularize your neural network in mean squared sense maybe an intermediate layer you take a look at that and then you try to match the features like the ideas of feature matching that we are doing for generative adversarial neural networks but then if you rewrite this in matrix format。



![](img/5027d630fe054ae5a51234566773a24a_81.png)

![](img/5027d630fe054ae5a51234566773a24a_82.png)

![](img/5027d630fe054ae5a51234566773a24a_83.png)

![](img/5027d630fe054ae5a51234566773a24a_84.png)

![](img/5027d630fe054ae5a51234566773a24a_85.png)

![](img/5027d630fe054ae5a51234566773a24a_86.png)

![](img/5027d630fe054ae5a51234566773a24a_87.png)

![](img/5027d630fe054ae5a51234566773a24a_88.png)

![](img/5027d630fe054ae5a51234566773a24a_89.png)

![](img/5027d630fe054ae5a51234566773a24a_90.png)

![](img/5027d630fe054ae5a51234566773a24a_91.png)

![](img/5027d630fe054ae5a51234566773a24a_92.png)

Again the graph laplaian is going to show up this a vector this is a matrix is the vector and in you're gonna to get a single number and X is when you are putting everything in one matrix so you are concatenulating your data and X I is the features corresponding to V like the country of the user of a Facebook out or the browser that they are using or their age group etc they could be your features this paper is telling us that you can actually use this laplaian to come up with convolution on graphs there is a theoretical motivation for the formulas that I'm writing here you can look at the paper actually in the next slide I will show you what this means I'm going to tell you what the first order approximation is and I'm going to tell you what is a spectral filters for now whenever you see the word this corresponds to the eigenvalue and eigen。



![](img/5027d630fe054ae5a51234566773a24a_94.png)

![](img/5027d630fe054ae5a51234566773a24a_95.png)

![](img/5027d630fe054ae5a51234566773a24a_96.png)

![](img/5027d630fe054ae5a51234566773a24a_97.png)

![](img/5027d630fe054ae5a51234566773a24a_98.png)

![](img/5027d630fe054ae5a51234566773a24a_99.png)

![](img/5027d630fe054ae5a51234566773a24a_100.png)

![](img/5027d630fe054ae5a51234566773a24a_101.png)

![](img/5027d630fe054ae5a51234566773a24a_102.png)

![](img/5027d630fe054ae5a51234566773a24a_103.png)

![](img/5027d630fe054ae5a51234566773a24a_104.png)

![](img/5027d630fe054ae5a51234566773a24a_105.png)

Of your Lapla but for now don't worry about the theory behind it， let's try to use it。

 you create an a tilda matrix， which is a plus identity and then d til la is very similar to D you are just summing up the rows of a tilde and then you want to have multiple layers at the first layer you have your features and this could be a vector in Rn by some dimension。



![](img/5027d630fe054ae5a51234566773a24a_107.png)

![](img/5027d630fe054ae5a51234566773a24a_108.png)

![](img/5027d630fe054ae5a51234566773a24a_109.png)

![](img/5027d630fe054ae5a51234566773a24a_110.png)

![](img/5027d630fe054ae5a51234566773a24a_111.png)

![](img/5027d630fe054ae5a51234566773a24a_112.png)

Now you want to go layer by layer because this h has a dimension， it's a matrix。

 you can multiply from right by one vector by one other matrix to change the dimension of D it's similar thing that you would do for convolutions or even fully connected networks you multiply by matrix from right and that's what you are doing here but at the same time you know that these data points they are talking to each other through the edges so the neighborhood matters the network is structure matters and the network is structure you are going to multiply these matrix from left by another matrix it looks complicated but it's actually not and I'm going to tell you in the next slide why it's not complicated actually even in this slide this is very intuitive what you're doing let's take a look at d tilde D tilde is going to be for this graph is going to be three。

4，3，4，4 and one。

![](img/5027d630fe054ae5a51234566773a24a_114.png)

![](img/5027d630fe054ae5a51234566773a24a_115.png)

![](img/5027d630fe054ae5a51234566773a24a_116.png)

![](img/5027d630fe054ae5a51234566773a24a_117.png)

![](img/5027d630fe054ae5a51234566773a24a_118.png)

![](img/5027d630fe054ae5a51234566773a24a_119.png)

![](img/5027d630fe054ae5a51234566773a24a_120.png)

![](img/5027d630fe054ae5a51234566773a24a_121.png)

![](img/5027d630fe054ae5a51234566773a24a_122.png)

![](img/5027d630fe054ae5a51234566773a24a_123.png)

![](img/5027d630fe054ae5a51234566773a24a_124.png)

As you take the square root， you're going to get a square root of three， square root of four。

 square root of three， etc， as you invert it， you're going to get one over a square root of three。

 one over a square root of four， but then you multiply this from left and right。

 so you can get rid of the square， it's one over three， one over four， one over two。



![](img/5027d630fe054ae5a51234566773a24a_126.png)

![](img/5027d630fe054ae5a51234566773a24a_127.png)

![](img/5027d630fe054ae5a51234566773a24a_128.png)

![](img/5027d630fe054ae5a51234566773a24a_129.png)

![](img/5027d630fe054ae5a51234566773a24a_130.png)

That is being multiplied by a matrix that is that has ones on the diagonal so it's not be 110010 So what are you doing for this particular node you are taking a look at yourself you are taking a look at node two node5 you direct connections and then you are just averaging out because you have one over three and then you have three neighbors including yourself so this is just an averaging you can replace this by a mean operation so you are doing mean pool based on your neighborhoods so intuitively it's very simple and what are you doing you're doing it layer wise you start with the first features you do this operation multiple times sigma here is your sigmaoid function your nonlinearity。



![](img/5027d630fe054ae5a51234566773a24a_132.png)

![](img/5027d630fe054ae5a51234566773a24a_133.png)

![](img/5027d630fe054ae5a51234566773a24a_134.png)

![](img/5027d630fe054ae5a51234566773a24a_135.png)

![](img/5027d630fe054ae5a51234566773a24a_136.png)

![](img/5027d630fe054ae5a51234566773a24a_137.png)

![](img/5027d630fe054ae5a51234566773a24a_138.png)

![](img/5027d630fe054ae5a51234566773a24a_139.png)

![](img/5027d630fe054ae5a51234566773a24a_140.png)

It could be value， it could be whatever that you want and then you keep repeating that multiple times until you feurize your graph or the nodes in your graph for some of them you have a label which you can do crossantropy loss and for some other you don't but because of this convolution these nodes are talking to each other so the information that you have the labels that you have on your Z4 which corresponds to x4 they' are going to leak into Z2 because they are connected because of the network is structure the cool thing is that these operation here you can do it once and for all this operation you can compute it once initially because you know your graph you just compute that and then in the next iterations you are just multiplying by matrices this is the first layer the second layer and then a softm that is giving you your probabilities。



![](img/5027d630fe054ae5a51234566773a24a_142.png)

![](img/5027d630fe054ae5a51234566773a24a_143.png)

![](img/5027d630fe054ae5a51234566773a24a_144.png)

![](img/5027d630fe054ae5a51234566773a24a_145.png)

![](img/5027d630fe054ae5a51234566773a24a_146.png)

![](img/5027d630fe054ae5a51234566773a24a_147.png)

![](img/5027d630fe054ae5a51234566773a24a_148.png)

![](img/5027d630fe054ae5a51234566773a24a_149.png)

![](img/5027d630fe054ae5a51234566773a24a_150.png)

![](img/5027d630fe054ae5a51234566773a24a_151.png)

![](img/5027d630fe054ae5a51234566773a24a_152.png)

And then these weights are just changing your dimension from dimension C you go to dimension H and then you go to dimension F this is the size of your features now you're gonna have a crossantropy loss on the nodes that you have a label for so this is the set of all the nodes that you have a label for and this is just a crossantropy loss you're maximizing the likelihood what is the drawback you need to do it for your entire graph so you cannot do mini batch so you cannot do mini batchching you cannot process your nodes in mini batches you have to take a look at your entire graph construct this a hat and then work with it we' are gonna to relax that assumption later these are some of the data sets these is the sizes of those data sets so it's not that huge 65000 These are the number of edges and then less than 01% of the nodes could be labeled and then you want to label the rest in a set。



![](img/5027d630fe054ae5a51234566773a24a_154.png)

![](img/5027d630fe054ae5a51234566773a24a_155.png)

![](img/5027d630fe054ae5a51234566773a24a_156.png)

![](img/5027d630fe054ae5a51234566773a24a_157.png)

![](img/5027d630fe054ae5a51234566773a24a_158.png)

![](img/5027d630fe054ae5a51234566773a24a_159.png)

![](img/5027d630fe054ae5a51234566773a24a_160.png)

![](img/5027d630fe054ae5a51234566773a24a_161.png)

![](img/5027d630fe054ae5a51234566773a24a_162.png)

![](img/5027d630fe054ae5a51234566773a24a_163.png)

![](img/5027d630fe054ae5a51234566773a24a_164.png)

![](img/5027d630fe054ae5a51234566773a24a_165.png)

Supervised fashion you can use deepW what we covered last session。

 you can use graph convolution on run networks and then these are the results of this paper so it's doing much better and it's not that bad it's really fast compared to previous state of the art and if you want to visualize one of your hidden layers like after this value you can try to visualize your features your data and then you can use something like TSNE or a simple PCA to visualize your data and then you can see that there is clear separation for your data and for this data you have it's Qa you have it's a citation network and you have seven classes so you have seven colors here and obviously this is much faster on a CPU because you can parallelize these matrix multiplication on a GPU sorry because you can parallelze these matrix multiplications so some of them you don't have any numbers on CPU because it's not even double and then you have the core。

Network that you can see that it's clearly separating your operations。Sorry。

 this is for the GPU and for the GPU they ran out of memory so they couldn't fit this matrix under GPU so that's why that number is missing anyways。

 but what is this box let's try to analyze this go into more details。And at the same time。

 try to work with multiple groupss。