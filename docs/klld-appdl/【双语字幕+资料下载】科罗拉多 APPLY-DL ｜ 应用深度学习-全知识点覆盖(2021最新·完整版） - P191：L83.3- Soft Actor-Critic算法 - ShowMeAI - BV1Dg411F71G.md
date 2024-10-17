# P191：L83.3- Soft Actor-Critic算法 - ShowMeAI - BV1Dg411F71G

I guess it's a good time to cover the last paper in reinforcement learning in this course they feel is huge。

 there is no way that we can we are able to cover everything but we covered a good deal of topics let's go back to model3 deep reinforcement learning you have two different frameworks one was policy optimization the other one was value optimization using your Q networks the policy optimization they suffer because you need to have you need to collect a lot of observations so you need to interact with your environment a lot it has a very high sample complexity the value type of frameworks they are very sensitive to the choice of your hyperparameter so you need to do a lot of hyperparameter tuning so is there a way to benefit from the best of the two worlds and that's the topic of softactive critic the quick recap of the notation so that the notation is in place。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_1.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_2.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_3.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_4.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_5.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_6.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_7.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_8.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_9.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_10.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_11.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_12.png)

You have an infinite horizon mark of decision process S is your state space。

 it could be continuous A is your action space it could be continuous you have your transition probability that takes you from a pair of a state and an action to the next state you have some reward it's bounded reward so you're not going to collect infinite reward for some of your actions or minus infinite penalty so it's bounded this is that state marginal of the trajectories this is a distribution that we never see when your coding on your computer this is just for mathematical convenience that we carried around this is based on your policy and then you can have a similar probability for your actions pairs of state and action What we are going to do here is maximum entropy reinforcement learning What is that previously your objective was to maximize your。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_14.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_15.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_16.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_17.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_18.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_19.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_20.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_21.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_22.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_23.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_24.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_25.png)

futureture reward now you're incorporating directly that you want to maximize the entropy as well in your objective。

 So one thing to mention this is different from what you are doing here here you are maximizing your expected reward but then to encourage exploration you would just add the entropy。

 the gradient of the entropy so what we are doing here is totally different So what you' are doing here is directly incorporating that entropy inside your objective。

 so it's going to be part of your re you're updating your reward。

 you're going end up having the Q function but it's going to be a different Q function that you are used to it's going to be a soft Q function and I'm going to tell you what that is you are still going to have that beman equation but then you have to prove that yes。

 you have a beman equation for this problem and let's say Tal pi is your beman backup operator we're going to use it。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_27.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_28.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_29.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_30.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_31.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_32.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_33.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_34.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_35.png)

Then the beman backup operator that's the definition that's your reward plus gamma of expected future values and this is a soft state value function why is it soft where is the word soft coming from it's coming from this entropy so it's showing up in your queue or in your V so this is the extra term that is complicating the mathematics a little bit but then yes go ahead so is the reason that and I don't know if you' explain this later but is the reason that Q is considered soft the same reason that V is considered soft exactly yes because look at V V for the next state there is some log of the policy that is going to go inside V of the next state now you are going to need some lemma these types of lemma we just use them for usual reinforcement learning。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_37.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_38.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_39.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_40.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_41.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_42.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_43.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_44.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_45.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_46.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_47.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_48.png)

You have to prove them actually so in the appendix of the paper you can find a proof for soft policy evaluation which says that if you keep repeating this process over and over again。

 if you keep applying your beman backup operator over and over again you're going to converge to your soft queue value and then you're going to need to prove these lemma as well soft policy improvement what is that if you minimize the KL dirgence between the new policy that you're looking for and this exponential term if you minimize that it's going to give you a new policy and that new policy has a higher soft value compared to the old policy so you need to prove that as well where is this exponential coming in it's coming in because of the KL dirgs there are some log terms in there and because of the log term coming up from your entropy so if you read the proof you're going to see where exactly that exponential is coming in and then you're going to be able to write down your soft policy。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_50.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_51.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_52.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_53.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_54.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_55.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_56.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_57.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_58.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_59.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_60.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_61.png)

eration so a policyeration is what you need is the first step before you can do policy optimization What is that what is the theoryem telling us and it's going to be based on these twolemmas that if you keep repeating this process soft policy evaluation and then soft policy improvement one step of that one step of this one step of that。

 one step of this that algorithm is going to converge and it's going to give you a policy pi is star that is the best regardless of the other policy and there are some constraints on what type of policies what properties this capital pi has so for that you need to read the paper well you' are going to use it in practice to give us the soft actorc algorithm what is that you're going to use neuron networks because we are doing deep reinforcement learning you're gonna have one neuron network for your value function so you're gonna have one neuron network for your soft value function takes your state as an input and is going to give you the corresponding value say scalr you're gonna have another neuron。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_63.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_64.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_65.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_66.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_67.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_68.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_69.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_70.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_71.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_72.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_73.png)

![](img/5e8255c4c44a9aa2541fe1fea094aef9_74.png)

Nework for your soft queue to approximate this other function here and then you're going to have yet another neural network which is going to give your policy and then you're going to have multiple objective functions and where are they coming from from these theorems and this mathematics and those definitions what is that the objective function for psi for this value is coming from this definition v minus the expected value of your actions we respect your policy assuming that you know theta and phi we can write down that objective and minimize it for your Q it's very similar to before you have your Q network and then you have some target you don't mean a squared error。

 where is the target coming from it's coming from your reward which is here and it's basically what you have in your beman equation it's your new beman equation so this lemma here corresponds to your beman equation your updated beman equation and it's coming from your beman backup operator。



![](img/5e8255c4c44a9aa2541fe1fea094aef9_76.png)

Here you're assuming that you know yoursi or the same way that you had an exponentially moving average for your target you can have the same thing here and this is the first paper that we covered there is some Q network the policy this is where the neat stuff is going to happen you have an objective the K divergence between your policy and you're optimizing over fees and it's coming from this Le up there the cool thing here is that you can not only model the mean of your policy you can model its variance you can model its statistics using the reparameterization trick and the reparameterization trick we saw it when we were doing generative networks variational autoenrs or GNs we saw the reparameterization trick it's showing up here again that's where you're putting your neuraln network so you can basically model the mean and the variance of。

ormal distribution by two neural networks and then this last function here is very interesting。

 Once you write down once you expand the k dirgence， there is some log of that probability。

 your policy and then you can you can keep sampling from the state and your epsilon your noise push it through the definitions of your policy that's going to give you the first objective。

 this is fully differentiable。 the other one is very interesting。

 This is also fully differentiable because Q is fully differentiable So now your queue is helping you train your policy and we saw this behavior before where we were doing deep deterministic policy gradient where your Q network was helping you train new and it was possible because Q was differentiable So you have a similar behavior here actually soft a critic is a generalization of that This is the algorithm So there is no need for me to go through it you have your。

Environment you keep you take your actions based on your policy。

 you create your dataset once you have your dataset， you keep optimizing these objectives。

 you optimize your value， you optimize your cu and you optimize your policy and then you keep a moving average of your size and if you want to compare it the soft actor critic to the rest of the algorithms on a humanoid problem this is deep deterministic policy gradient the green one and you're reporting the average return this is the performance this one we covered the proximal policy optimization PPO is this brown line here and the soft actor critic is converging much faster giving you much better return I think it's a good time to stop and let you guys ask questions and for those of you want to leave you can leave I'm curious so sort of I guess to like solve the problems model free。

Do you sort of pay in terms of。Like lots of parameters。

 given that you have these three networks here， does that end up being very sort of costly parameter wise？

So yes you have a lot of parameters you're right so you're parameterizing your value function Q function and your policy。

 but we were doing it anyways with other frameworks with proximal policy optimization or deep deterministic policy gradient you are at least parameterizing your pi and Q so the only additional thing that you're parameterizing in this is this V which I guess should be okay so no we have been doing it for all of these methods as well。

But the cool thing here is that this is not deterministic your policy is no longer deterministic anymore and that is what is helping this framework explore the environment better so sounds's like a better exploration exploitation sort of Yes ratio yeah interesting but there is also another problem here you don't know what is your alpha these are again your higher parameters that you need to find tune but it turns out that there are some studies in the paper that this framework is not that sensitive to the choice of alpha。

Is that the only I mean， besides like you know， general optimization hyperparameters is that the only hyperparameter within sort of this framework no there are actually more there is okay these learning rates there is but sort of exponential yeah。

 but those are within sort of like the optimization framework I guess yeah then those would be there for any like gradient descent you know any optimization method。

Yes， and the other thing that we didn't cover that much in this course is your reward for some of the problems like Atari games。

 You know your reward。 It's being written on top of your screen or for a game like go or ches。

 you know your reward。 But when you go into more realistic settings like what we covered in the previous paper with real robots。

 then defining this are， you have some flexibility there。 So reinforcement learning is cool。

 But it's very hard to get it to work in practice。 Thank you。 Yeah， sure。

