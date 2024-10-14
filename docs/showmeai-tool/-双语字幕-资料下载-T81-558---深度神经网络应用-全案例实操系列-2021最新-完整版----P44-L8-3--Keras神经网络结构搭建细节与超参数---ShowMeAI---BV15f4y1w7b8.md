# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P44：L8.3- Keras神经网络结构搭建细节与超参数 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton。 welcome to applications of deep neural networks with Washington University。 In this video， we're going to answer a question that I'm sure has been bothering you the entire semester。 How do you know how many layers to use in your neural network。 How do you know how many neurons to use in your neural network。😊。

This is a big enough question that we're going to spend the next two videos talking about it for the latest on my AI course and projects click subscribe and the bell next to it to be notified of every new video hyper is's really no easy answer to this one As we've gone through the various modules looking at neural networks you'll see that we have various layers activation types。

 different ways to do normalization different activation functions all kinds of things you can adjust on your neural network neural networks a lot on its own those are referred to as are the weights of the neural network However hyper are not learned as part of the neural network training it's up to you the neural network practitioner to actually specify these So specifying which activation functions you want what sort of regularization you want all this kind of thing you need to specify as the neural network practitioner Now in the next part we'll see how to use something called Bayesian optimization to help us fine tune the neural network。



![](img/6ffb2dddbc647a884212a626611b3856_1.png)

But even then there's some degree still of decision， at least on your part。 to decide which hyperparameters you're going to optimize and how you want to optimize them in this part。 I'm going to take you through the major hyperparameters。 layer types and other things that we've gone through up to this point and if you that we havent just so that you're aware of them So Kira's layer as you build up the neural network。

 you'll see that the various examples add different sorts of layers onto the neural network listed here are all of the layer types that you can add into that sequence that you are building for the neural network and ultimately perhaps putting into a model if you're using the functional API activation this is a layer that allows you to specify the activation function I don't tend to use this a whole lot I tend to specify the activation function as part of the parameters for the denses and other types of layers but you can break this out。

The activation comes just after a layer activity regularization。 This allows you to add L1 and L2 outside of a layer。 Again， L1 and L2。 as far as activity and kernel can be added to the individual layer types such as dense。 but you can specify this outside of the layer as well。 if you find that to be more express it。

 The dense layer。 This is the workhorse of tabular data for sure。 this is mostly what your neural network is made up of if you're doing tabular data。 If you're doing images and other things， you'll still have dense layers。 If you're dealing with non dense layers like the LSTM layers and the convolution layers。

 you'll typically have to flatten。 That's a layer type down here。 before you feed things into the dense layer。 Dropout layer allows you to use dropout regularization。 you specify a percentage usually relatively low。 maybe 5，10，20%。 that is the。😊。Of neurons in that layer that are randomly disabled during training。

 Dropout has no effect when you're actually running the neural network。 when you're scoring the percent of neurons that you're going to drop out is not a learn parameter。 You have to specify that when you're building up your neural network。 Flten is used to usually used right before dense layer or right before the output that is crunching。

 the multidimensional tensors that are not vectors like the matrices and cubes down to a vector that can be passed into a layer that's not designed to handle something more than one dimension。 input is the input layer that is where data comes into your neural network。

 This can be specified as a parameter for the dense or other layers。Lambda layers。 I really haven't used these a great deal， but you can basically specify a Python Lambda function to do some transformation to the data as it goes through masking layers。

 Again， this is something I have not used and all really in in cares。 but it is available It's dealing with time stepss。 I'm guessing this has some utility when you're dealing with LSTms in recurrent neural networks。 same thing for the permute。 that can be used to add some randomization and changing to a given pattern。

 I'm not entirely sure if the permute。 I don't believe the permute is random。 So like I just said。 permute。 that's a way to change around the dimensions of a layer as it's going through。 This works pretty similar to reshape。 I usually use reshape rather than permute。 I have not used permute a great deal。 repeat vector is a way to duplicate things。

 have not used that a great deal。 reshape。 I've used that a great deal that lets you change the structure of things as they're going through。😊，For example， you had the RGB values in different orders than the neural network expected Permute would probably be a very good choice for that reshape is just more changing what the actual shape is without necessarily ordering things too much spatial dropout is dropout used for convolution layers I have not used these a great deal activation functions。

 very important topic in neural networks The thing to remember with activation functions is there is a lot of history here neural networks have been around for a long time and various activation functions have been。Added over the years， some of these are not used all that much in the modern era of deep learning。

 You'll also notice that I have advanced activation functions down here as well。 advanced activation functions are ones that are actually modified as the fit occurs。 The regular activation functions， they are just part of the training process。 but the training process is not affecting any parameters inside of the actual activation function。

 So the softm activation function， you typically see that on the output layer of a multiclass classification。 This ensures that all of the outputs from the neural network， some to one。 So they're essentially probabilities not at a lot of tuning here。 either you're using softmax or you're not。 if you're using multiclass classification。

 likely you're using softm。 Now， A lot of these come from various papers that are being reproduced with care as an EU as one of those。 That's the exponential linear unit I've seen。That in a couple of papers with Gs and other things I have not worked with these a great deal。

 something that I'm meaning to work with more。 they do seem to potentially in theory anyway。 have some advantages perhaps over re scaled exponential unit is similar to ELU except it's scaled by a numeric value that is another hyperparameter that you have to specify by what you want to to scale it by scaling factors simply multiplied by the SL So plus this is more of a historic one I have not seen this one used a lot in later papers not to say it isn't same thing for soft sign rectified linear unit Rlu that is absolutely the workhorse of deep learning other than perhaps leaky re which receive further down hyperbolic tangent not used a whole lot。

 I see those in LSTMs and they were very popular in hidden layers before RE came on strong Sigmoid。 same thing。Common in classic neural networks for hidden layers not used a whole lot in hidden layers in modern neural networks。 However， sigmoid is still very common for a logistic regression output neural network。 which is basically a binary classifier classifying between two things hard sigmoid I haven't seen this used a lot recently。

 it works just like the sigmoid function， the sigmoid function is expensive to calculate because there's two EP functions in it。 the hard sigmoid is more of an approximation of the sigmoid of the logistic。 So it's potentially cheaper to compute。 maybe on mobile devices， this might be a good idea。 I have not dealt with it a great deal exponential。

 This is another one that I have not worked with a great deal， but it's a base Eactation function。 at least according to the documentation in Kis linear。 This is used a lot。 particularly for regression neural networks on the output layer I don't think you would necessarily see it anywhere other than the output layer unless。Just doing something very custom and you need to basically pass through the activation function on something so that it does not make any changes。

 leaky re is a variant of of it allows a very small gradient So it has some special rules on the gradients during training This is a very popular one I've used it to some degree have not really seen a great deal of improvement within it in all cases Preu I I have had some good results with this's there's an alpha term in the leaky re that you normally have to specify the pre you can actually learn that So that's that's a good thing L1 L2 and dropout I don't see L1 and L2 in practice used a great deal in deep learning L2 for sure L1 not as much for especially in vision networks where I don't think you really want to drop inputs like drop an individual pixel so I don't see L1 used a great deal。

L2 might have some value but dropout is really the workhorse of these deep neural networks the papers that I read in particular you can figure out the dropout percentage using some of the Bayesian optimization that I will show you in the next part batch normalization I have been playing with that to some degree and have been using it more and more it's pretty handy it can typically in practice at least I've observed allow me to increase my learning rate to values that would have caused instability in the past So if you set your learning rate too high typically you will cause overflows in some of the back propagation steps and even forward propagation steps depending on your activation functions so that will cause NANs not in numbers and pretty much collapse your training So batch normalization can be quite useful for that and also as a combat to the vanishing gradient problem where your gradients。

to go to zero and nothing， nothing learns you've also got various training parameters that you need to make use of in particular batch size and learning rate。 mini batches are very popular in deep learning。 So usually this value is 32 or lower for the batch size learning rate also also usually pretty small unless you're using batch normalization。

 but you need to kind of play with the learning rate and batch normalization to。See how small you can to see how small it's necessary to make the learning rate Learn rate too small will cause the neural network to simply not learn or too high will cause your neural network to quickly destabilized。

 So if you see the neural network reporting NA AN for the error function。 it's usually because your learning rate is too high。 I almost always specify learning rates as powers of 101 E negative 10， so。10 to the power of1 times 10 to the power of negative3 in that case。

 Now this function that I have here， we will make more use of these。 We will make a lot more use of this in the next section。 but let's go ahead and just do a quick look at how we can try out some of these hyperparameter。 I'm going go ahead and run this that loads a classification job that I want to do。

 it's using that simple data set that we looked at before。 This evaluates the neural network。 Now this is using bootstrapping like we saw before。 splits is how many bootstrapping splits we actually want。 I'm using two just so that it runs relatively quickly， but you can experiment with that。 again。

 when we're tuning hyperparameter， sometimes there's parameters usually not very many that go into tuning the hyperparameters or almost hyperparameter squares。 but that would be one of them that you would need to set as you're searching。 This is another one。

 So what I'm basically doing here is allowing these values to be。As I'm trying to make the very complex neural network hyperparameters numeric and a vector。 So dropout would be the first value of the four that we're tuning at once。 Learn rate is the learning rate for the neural network。

 neuron percent is just what percentage of these 500 do we want to use and neuron shrink is what should the layer shrink by each time。 So we start out with however many neuron percent we have for that neuron count。 and then we shrink it by that value each time。 So it could be like 0。8。 if you want to use 80% on your next one。 And you can see here that it basically builds up so long as each new layer has a neuron count of 25 and is less than 10 Good run this So does's going。

 It takes a few moments to actually score and it will be made use of in the next part because believe me  for Bayesian optimization。 It's very valuable to have your neural network hyperpara is just one vector。 You put quite a few additional hyperparameters in here And if you're dealing with a vision network。probably want to do convolution layer count and other things so this is still running I'll go ahead and oh just finished ignore that error I will fix that that simply was trying to time how long it took this is a log loss of 0。

7 and we'll see that in the next part we actually tune that to get down to 0。59 which is a much better log loss ignore the negatives I'll explain in the next part what that's necessary that's just so that we can optimize it because it wants to maximize the number and you don't try to maximize a log loss you try to minimize it。



![](img/6ffb2dddbc647a884212a626611b3856_3.png)

Well those are the hyperparameters that make up a neural network and it probably seems intimidating to try to optimize these on your own we'll see in the next video that we can use Bayesian hyperparameter optimization to let machine learning do a lot of this work for us this content changes often so subscribe to the channel to stay up to date on this course and other topics and artificial intelligence。

