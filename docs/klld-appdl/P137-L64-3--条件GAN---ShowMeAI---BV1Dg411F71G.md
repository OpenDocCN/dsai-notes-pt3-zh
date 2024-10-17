# P137：L64.3- 条件GAN - ShowMeAI - BV1Dg411F71G

You're gonna see applications of GNs when you go to conditional GNs it has a lot of applications there and the idea of a conditional GNs is for instance。

 you have a text and you want to condition on that generate an image for instance you can have a low resolution image and you want to generate a high resolution image or you want to generate samples that are all zeros if you are doing Mnes all ones all twos so you're conditioning on some information you want to do image to image translation those sorts of applications This is the objective function that we just saw for generative adversary and neural networks for conditional the idea is very simple you just condition so rather than having x you have some extra information Y and you just condition on y how do you code it and the application as I mentioned is one to many mapping so these are not functions you have one input and they are not a single unique answer so these are。

I post problems one input can map into multiple outputs like when you when you are doing translation there is no good answer one French sentence can have multiple good translations so these are one to many mappings I guess this is going be more clear this figure if I show you show you an example let's say this is your example you want to generate samples that look like zero all the time you want to generate samples that look like one two three etc and the label is going to be a one heart vector it' it's going to be one whenever you're at the particular location that you're interested in。



![](img/00a00399f41432cc7d81460747236ad2_1.png)

![](img/00a00399f41432cc7d81460747236ad2_2.png)

![](img/00a00399f41432cc7d81460747236ad2_3.png)

![](img/00a00399f41432cc7d81460747236ad2_4.png)

![](img/00a00399f41432cc7d81460747236ad2_5.png)

![](img/00a00399f41432cc7d81460747236ad2_6.png)

You're interested in number zero location one in your vector is going to be one if you're interested in number seven location8 is going be one in your vector and the rest of them are going be zero okay perfect that' your additional information your generator not only takes as input some noise it's going to take as input your label and one I want to generate zeros or I want to generate force you push them through your neural network and then in the end you're going to get a fake image you take that fake image in addition to their real image in addition to the label and you push them through basically you're concatenating this information concatenate them multiply them by a bunch of weights and then give us the probability of this term being this image being real or fake okay and then you can train it it's the same objective as before the other application is when you're doing tagging so somebody gives us an image。



![](img/00a00399f41432cc7d81460747236ad2_8.png)

![](img/00a00399f41432cc7d81460747236ad2_9.png)

![](img/00a00399f41432cc7d81460747236ad2_10.png)

![](img/00a00399f41432cc7d81460747236ad2_11.png)

![](img/00a00399f41432cc7d81460747236ad2_12.png)

![](img/00a00399f41432cc7d81460747236ad2_13.png)

![](img/00a00399f41432cc7d81460747236ad2_14.png)

![](img/00a00399f41432cc7d81460747236ad2_15.png)

![](img/00a00399f41432cc7d81460747236ad2_16.png)

![](img/00a00399f41432cc7d81460747236ad2_17.png)

![](img/00a00399f41432cc7d81460747236ad2_18.png)

![](img/00a00399f41432cc7d81460747236ad2_19.png)

And we want to put some tags on that so yes we want to generate tags for our images somebody gives us an image and we want to tag it。

 we want to generate taxi passenger line transportation station and this is a one too many mapping somebody gives us the image of a food and we want to say this is a chicken cooked cookie house made etc So these are the generated tags。

 these are the real tags these are your data and so how are we going formulate this problem what we are conditioning on is now the image so these red texts are what you're conditioning on now this is your why these is your noise you push it through your neural network and that's going to give you the corresponding tag you take the tag you take a real tag this is the fake one。

 this is the real one and then you condition and the image because that's your why now。



![](img/00a00399f41432cc7d81460747236ad2_21.png)

![](img/00a00399f41432cc7d81460747236ad2_22.png)

![](img/00a00399f41432cc7d81460747236ad2_23.png)

![](img/00a00399f41432cc7d81460747236ad2_24.png)

![](img/00a00399f41432cc7d81460747236ad2_25.png)

![](img/00a00399f41432cc7d81460747236ad2_26.png)

![](img/00a00399f41432cc7d81460747236ad2_27.png)

![](img/00a00399f41432cc7d81460747236ad2_28.png)

![](img/00a00399f41432cc7d81460747236ad2_29.png)

![](img/00a00399f41432cc7d81460747236ad2_30.png)

You push it through your discriminator and that's gonna to give you a probability and once the training is done you can generate tags for images okay any questions so when you say take the real image or take the real tag then you have to I guess just pick one at random from that class the real tag is the data that you have for instance for this example you know your tags you know the input image so you know your why you know Montana tram in Verno etc these are your real tags and these you're going encode them as word vectors okay so these are vectors that's the real tag the fake tag is coming out of your generator which could be initially it could be really bad for instance these could be a chicken okay but now it's getting much better transportation is good you take that you take Montana and then the discriminator has to discriminate between the two and then。



![](img/00a00399f41432cc7d81460747236ad2_32.png)

![](img/00a00399f41432cc7d81460747236ad2_33.png)

![](img/00a00399f41432cc7d81460747236ad2_34.png)

![](img/00a00399f41432cc7d81460747236ad2_35.png)

![](img/00a00399f41432cc7d81460747236ad2_36.png)

![](img/00a00399f41432cc7d81460747236ad2_37.png)

![](img/00a00399f41432cc7d81460747236ad2_38.png)

![](img/00a00399f41432cc7d81460747236ad2_39.png)

![](img/00a00399f41432cc7d81460747236ad2_40.png)

![](img/00a00399f41432cc7d81460747236ad2_41.png)

Once the training is done this is a harder task for the discriminator it gets harder and harder Okay does that answer your question I had question do you have to run it several times to get several tags and you use some threshold to know if it doesn't select anything or does it output some fairly number of tags automatically So the way that is' going to work the theorem that I just showed you was assuming that if I give you D if I give you G you're going to give me D so you're going to do an entire optimization process and if I give you the optimal D you're going to give me the optimal G but in practice there is going be some hyperparameter that you need to tune for how many rounds are you going to train D for how many rounds are you going to train G So these are very good questions and these are technical questions that once you sit behind the computer you're going learn。



![](img/00a00399f41432cc7d81460747236ad2_43.png)

![](img/00a00399f41432cc7d81460747236ad2_44.png)

![](img/00a00399f41432cc7d81460747236ad2_45.png)

![](img/00a00399f41432cc7d81460747236ad2_46.png)

![](img/00a00399f41432cc7d81460747236ad2_47.png)

![](img/00a00399f41432cc7d81460747236ad2_48.png)

![](img/00a00399f41432cc7d81460747236ad2_49.png)

![](img/00a00399f41432cc7d81460747236ad2_50.png)

![](img/00a00399f41432cc7d81460747236ad2_51.png)

![](img/00a00399f41432cc7d81460747236ad2_52.png)

![](img/00a00399f41432cc7d81460747236ad2_53.png)

About them only through experience Okay， I hope that answers your that answers your question Actually。

 for those of you who want to leave， you can leave and for those of you who want to stay and ask questions I'll be around quick question So sort of what you were saying with the blue labels here was it originally we think about like an image is our input in the label is our conditional and now we're sort of swapping roles but we can do the same thing I that correct that's correct So usually what happens is that X goes in So it's the other way around of your generator X goes in and then the corresponding label is gonna come out of your neural network and that's where classification。

 Now it's different the label goes in and you're gonna generate an image corresponding to that label So yes。

 you're right you're switching the role of your images and labels。



![](img/00a00399f41432cc7d81460747236ad2_55.png)

![](img/00a00399f41432cc7d81460747236ad2_56.png)

![](img/00a00399f41432cc7d81460747236ad2_57.png)

![](img/00a00399f41432cc7d81460747236ad2_58.png)

![](img/00a00399f41432cc7d81460747236ad2_59.png)

![](img/00a00399f41432cc7d81460747236ad2_60.png)

![](img/00a00399f41432cc7d81460747236ad2_61.png)

![](img/00a00399f41432cc7d81460747236ad2_62.png)

![](img/00a00399f41432cc7d81460747236ad2_63.png)

![](img/00a00399f41432cc7d81460747236ad2_64.png)

And could you also have your label be like in this case。

 we're producing a fake image and a fake tag from a label or from an image。 But in the text scenario。

 could we also have this label be。

![](img/00a00399f41432cc7d81460747236ad2_66.png)

![](img/00a00399f41432cc7d81460747236ad2_67.png)

![](img/00a00399f41432cc7d81460747236ad2_68.png)

Just some encoded like sentence from the sort of like language models we've seen earlier Yes absolutely and given a text now you're generating images so the architecture and the way that you want to interpret this depends on the application okay but all of them are going to fall under the under the umbrella of conditional Gs so you're always conditioning on something Okay thanks yeah any other questions。



![](img/00a00399f41432cc7d81460747236ad2_70.png)

![](img/00a00399f41432cc7d81460747236ad2_71.png)

![](img/00a00399f41432cc7d81460747236ad2_72.png)

![](img/00a00399f41432cc7d81460747236ad2_73.png)

![](img/00a00399f41432cc7d81460747236ad2_74.png)

![](img/00a00399f41432cc7d81460747236ad2_75.png)

So I didn't quite understand the last part about how many times you have to run it。 So for example。

 if you we look at the first image and it produces taxi， passenger line transportation， etc cetera。

 do we get this collection of ws after putting the image and one。



![](img/00a00399f41432cc7d81460747236ad2_77.png)

![](img/00a00399f41432cc7d81460747236ad2_78.png)

![](img/00a00399f41432cc7d81460747236ad2_79.png)

![](img/00a00399f41432cc7d81460747236ad2_80.png)

I guess I like Montana， do we get， for example， taxi when we put Montana and then we get passenger when we put time？



![](img/00a00399f41432cc7d81460747236ad2_82.png)

So I guess what you are not understanding is the one to many relationship so for this image there could be many good tags okay for this image there could be many good tag but during training you are going to process them one at a time so you're going to take this you're going to take water and you're going to take the generated tag from your generator and these are going to be the input to your discriminator so these are going to be processed one at a time or if you want to batch them they're going to be processed in batches and there could be a case that water is being paired with a long river is being paired with lay etc okay all of these could happen。



![](img/00a00399f41432cc7d81460747236ad2_84.png)

![](img/00a00399f41432cc7d81460747236ad2_85.png)

![](img/00a00399f41432cc7d81460747236ad2_86.png)

![](img/00a00399f41432cc7d81460747236ad2_87.png)

![](img/00a00399f41432cc7d81460747236ad2_88.png)

![](img/00a00399f41432cc7d81460747236ad2_89.png)

![](img/00a00399f41432cc7d81460747236ad2_90.png)

![](img/00a00399f41432cc7d81460747236ad2_91.png)

Did that answer a question， Yeah， definitely definitely yeah yeah。



![](img/00a00399f41432cc7d81460747236ad2_93.png)