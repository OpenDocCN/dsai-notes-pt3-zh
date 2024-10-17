# P199：L85.5- 图同构网络 - ShowMeAI - BV1Dg411F71G

So this last paper is going to be a theoretical paper and it's going to help us understand and answer this question how powerful are graph neural networks in general we covered multiple different versions of graph neural networks let's see how powerful they are in practice again you have a graph it has a bunch of vertices it has a bunch of edges that's the set of vertices this is the set of edges each node could have some features to begin with and then your task could be node classification for each node you're going to have an associated label or actually for a subset of nodes you might have labels and for the rest of them you might have no labels which is going to be the semiupervised type of framework that we discussed。



![](img/12a6cee460e9fab33903e95e7ff14b22_1.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_2.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_3.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_4.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_5.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_6.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_7.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_8.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_9.png)

And then you're going to have some representations for each node in your graph and then you're going to have a neural network that is taking H of V and it's predicting its associated label you can have graph classification so for graphs。

 it matters what is your data， your data could be at the node level or it could be at the graph level。

 you can have multiple graphs and then you want to classify among graphs。

 let's say you have a set of graphs graph1 graph2 graph n and then per each graph you have a bunch of labels for graph1。

 you have label one for graph n， you have the corresponding label Yn。



![](img/12a6cee460e9fab33903e95e7ff14b22_11.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_12.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_13.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_14.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_15.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_16.png)

And then you need an entire representation for the entire graph。

 so you need to have a single representation per each graph and then you can have a neural network G that is taking a graph as an input or the featureurized or the feature representation representation vector of your graph and it's predicting its corresponding label we covered graph neural networks and the way that graph neural networks work is that they have K iterations。

 they have k layers of graph neural networks so let's set K to denote the layer to count the layer and then usually we have this framework。

 you would take a look at a node in your graph， you look at its neighbors。

 each neighbor they have some representations coming from the previous layer and then you would have an aggregate function that is going to give you a single vector corresponding to V and this is for the next layer。



![](img/12a6cee460e9fab33903e95e7ff14b22_18.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_19.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_20.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_21.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_22.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_23.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_24.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_25.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_26.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_27.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_28.png)

So you're going from the layer before to the next layer， and then you need a combined operation。



![](img/12a6cee460e9fab33903e95e7ff14b22_30.png)

You take your previous representation of your node at the previous layer and then you somehow combine this with the aggregated representation to give you the representation for the next layer and then you keep repeating that process but the question is what are the examples of these two functions aggregate and combine and to start the algorithm in the first layer your representations are going to be your actual features at that note for graph classification。

 this task up here where you're classifying graphs rather than nodes。

 you need a single vector representation so you can have a readout operation which could be a simple maximum operation max pullinging or average pullinging you take a look at the entire set of vertices in your graph and then you combine them somehow using the readout operation。



![](img/12a6cee460e9fab33903e95e7ff14b22_32.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_33.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_34.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_35.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_36.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_37.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_38.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_39.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_40.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_41.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_42.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_43.png)

The readout could be a simple summation or group level pooling we covered graph s for graph s the aggregate function was you first look at the neighbors of a node。

 you multiply that by a matrix you push that through a nonlinearity and then you do max pullinging in that neighborhood this is an example of an aggregate function for the combine in the graph s algorithm you would take the representation of your vertex from the previous layer the current aggregated representation you cancatenate them and then multiply that by another matrix so that graph s for graph convolutional networks GCN。

 you first look at a node and it neighbors， you look at the representations from the previous layer and then you do a simple averaging of those representations。

 then you multiply by a matrix and then you apply the nonlinearar。



![](img/12a6cee460e9fab33903e95e7ff14b22_45.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_46.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_47.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_48.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_49.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_50.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_51.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_52.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_53.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_54.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_55.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_56.png)

And this is aggregate and combine in one step so these two steps are just one single step in this line we are going to introduce a new algorithm it's called graph isizomorphism network how does it work you still look at a node and its neighbors you look at their representation from the previous layer and then you add them up except for the fact that you're adding a tiny variation to one so epsilon is a small number and then you take that representation and then you push it through a nonlinearar function a multilayer percept so this could be a deep network or a network with some layers。



![](img/12a6cee460e9fab33903e95e7ff14b22_58.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_59.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_60.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_61.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_62.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_63.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_64.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_65.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_66.png)

This is a generalization of what you have down here for graph s and graph convolutional neural networks。



![](img/12a6cee460e9fab33903e95e7ff14b22_68.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_69.png)

Here you had only one layer， you are going one layer deep and MLP could be multiple layers at least two for the graph representation for HG。

 you can have a readout operation for each one of your layers for layer zero。

 you can have your readout operation which could be a simple summation or pooling max pullinging layer。



![](img/12a6cee460e9fab33903e95e7ff14b22_71.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_72.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_73.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_74.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_75.png)

But then you do it for every single layer in your neural network。

 layer zero layer one until layer K and then you can'catenate them and that's going to be a representation of your entire graph it turns out that the discriminative and representational power of graph isomorphismism network is equivalent to the power of the vice filer Leman test what is the test telling us what is the WL test telling us it is answering this question are two graphs topologically identical and how does it actually proceed the test proceeds into steps you first aggregateator labels of the nodes and the neighborhoods so there's an aggregation operation and then you hash the aggregated labels into a unique new label so it's very similar to the operations that the graph neural network does and then the algorithm。



![](img/12a6cee460e9fab33903e95e7ff14b22_77.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_78.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_79.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_80.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_81.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_82.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_83.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_84.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_85.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_86.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_87.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_88.png)

Is going to decide that two graphs are non isomorphic if at some point in this iteration。

 the labels of the nodes。

![](img/12a6cee460e9fab33903e95e7ff14b22_90.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_91.png)

Between the two graphs， they differer。

![](img/12a6cee460e9fab33903e95e7ff14b22_93.png)

And at that point in time， it's going to say okay these two graphs are not topologically equivalent。

 that's a big picture of W fileler Le test， but what is the proof of this claim that the discriminative and representational power of graph isomorphism network is equal to the power of the W fileler Le test。



![](img/12a6cee460e9fab33903e95e7ff14b22_95.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_96.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_97.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_98.png)

We are not going to have time to go through the details of the proof， but I can give you a sketch。

 it has two steps， the first step of the proof， you're going to say that graphph neural networks are at most as powerful as the WL test。



![](img/12a6cee460e9fab33903e95e7ff14b22_100.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_101.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_102.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_103.png)

In distinguishing graph structure， the second step it says that under some assumptions。

 under some mild conditions， under neighbor aggregation on these operations here or up there on this neighbor aggregation operation。



![](img/12a6cee460e9fab33903e95e7ff14b22_105.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_106.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_107.png)

And under the readout function here， under some mild assumption on those operations。

 the resulting graph neuro network is going to end up being as powerful as the WL test。



![](img/12a6cee460e9fab33903e95e7ff14b22_109.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_110.png)

![](img/12a6cee460e9fab33903e95e7ff14b22_111.png)

So what does this mean it's going to be as at most as powerful as the WL test。

 let's take two graphs G1 and G2 and let's say they are not isomorphic。

 if a graph if a graph neural network is able to map G1 and G2 to different embeddings so basically takes G1 maps it to embedding H of G1 it takes G2 maps it to an embedding H of G2 if H of G1 and H of G2 end up being different then the vicepeeller lemon test is also going to decide through the process that we described up there。

 that G1 and G2 are not isomorphic。So it means that GenNNs are at most as powerful as WL test。

 but what are these mild conditions that make a graph neural network as powerful as a WL test。

 the conditions are on the functions F and p and this set being a multiet。

 you look at the neighbors of a node， each one had a representation from the previous layer and you treat this as a multiet。

 what is a multiet a multiet you can have。You can count the number of times that an element is showing up in the set。

 for instance， the same element could show up two times， so you keep the number two on a site。

And then what we have here， the function F is exactly similar to this function that you have up there。

 so as soon as function F is injective and function phi is injective。

 you satisfy condition A so you also need another condition for the entire graph or the graph readout operation So the previous step is about aggregating and updating your node or node features from one layer to the next layer。

 it's similar to this step in your graph graph s or these two steps that are present in a generic graph neural network。

 So you first aggregate combined and then you do graph readout or graph representation。

For the graph level readouts it's going to operate on the multiet again of node features so each graph is going to have a bunch of nodes and each node in that graph is going to have some features and the condition is very similar to before it has to be injective so for the details of the proof you can take a look at the paper and go into more details but this is a big picture。

What does it say in general， it says that graph neural networks are as powerful as wise filer lemon test under some mild conditions so they are as powerful as one can hope for and that's why they' are successful in practice so as soon as you work under the umbrella of aggregate combine and read out graph neural networks and in particular graph isomorphes and network。

 which is going to satisfy these two conditions， is as powerful as it can get theoretically speaking。

