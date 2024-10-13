# 【双语字幕+资料下载】伯克利FSDL ｜ 全栈深度学习训练营(2021最新·完整版) - P4：【Lab2】CNN 和数据实验 - ShowMeAI - BV1iL411t7jE

![](img/c6447571d36e972507177863ebd07405_0.png)

so um the lab today，is about convolutional neural nets and，also we're going to make some。



![](img/c6447571d36e972507177863ebd07405_2.png)

![](img/c6447571d36e972507177863ebd07405_3.png)

so really don't have slides for it it's，more of。

![](img/c6447571d36e972507177863ebd07405_5.png)

the github readme，so it's linked to from the course，so what we're going to do is we want to。

use a simple convolutional network，to recognize first e，first amnest and then e-m-ness。

characters and now we want to construct，a synthetic data set of em-ness lines。

just to move us you know closer to that，sequence processing that we're gonna do，next week。

so before you begin make sure to do the。

![](img/c6447571d36e972507177863ebd07405_7.png)

lab setup。

![](img/c6447571d36e972507177863ebd07405_9.png)

which i can do here，so it's that you know set up where you，get clone，and then pip install。

pytorch lightning and then you're able，to。

![](img/c6447571d36e972507177863ebd07405_11.png)

and if you are running on your own。

![](img/c6447571d36e972507177863ebd07405_13.png)

machine instead of colab，which i actually am here just make sure，to get full。

to get the latest changes and you should，now see this lab2 directory that you，didn't previously have。



![](img/c6447571d36e972507177863ebd07405_15.png)

so the first thing i want to do is，introduce us to uh，emnest so as you remember you know。

mnist is the digits you know there's 10，digits um handwritten and that actually，stands for mini nist。

and nist is the national institute of，standards and technology。

so mini nist is mini because it only has，digits，but the original nist also had，characters。

so emnist is extended mnist which，which is like a repackaging of the。

original data set which also contains，the letters as well as the digits but。

it's now in the mnist format，that young lacoon kind of popularized。

so there's your papers with code about，it but we can take a look at the data。

in notebooks um 01 look at。

![](img/c6447571d36e972507177863ebd07405_17.png)

because every time you go to collab it's，ephemeral there's no。

you can save the the collapse to github，yeah you can save it you can save it to。

google drive but i don't actually think，it preserves the file system。

that you have i'm i might be wrong about，it but i don't think it preserves the，file system。

uh it takes like just a couple of，seconds to to clone them，sorry i have to find where i installed。

oh yeah content there we go um，so lab two there's the old text，recognizer that we remember。

the training run experiment so we，remember these two，but now there's also notebooks and。

there's two notebooks in it，unfortunately we can't run them as，notebooks。



![](img/c6447571d36e972507177863ebd07405_19.png)

in collab so that's，that's that sucks what you can do is you，can look at the notebooks。



![](img/c6447571d36e972507177863ebd07405_21.png)

so if you just want to like follow along，and look at them。



![](img/c6447571d36e972507177863ebd07405_23.png)

you can just load them in github and，that renders it quite nicely。

or you can set up you know your own，machine，and i'll actually share instructions on。

how to set up a google cloud platform，machine um if you want to do that。

but there's a trick with google cloud，platform which is that if you sign up，with your berkeley。edu。

email you really won't be able to launch，gpus because at least as far as i，understand like。

all of us belong to the berkeley kind of，workspace，and that has that workspace has no quota，for gpus。

and i don't know how to increase it，because i don't know who's responsible，at berkeley。

so if you sign up for google cloud，platform sign up with your personal，email。

i'll share a document on how to do that。

![](img/c6447571d36e972507177863ebd07405_25.png)

later but for now i'll just actually，show it，um in github because the i already ran。

the notebook and this is the output，so to look at the em this data we're，going to。

import a new data module called emnist。

![](img/c6447571d36e972507177863ebd07405_27.png)

so this is a new，data class so last week we only have the，base data module and mnist we now。



![](img/c6447571d36e972507177863ebd07405_29.png)

also have em nist e and then，these are actually extra for next week。

we it has a mapping and then a split of，the train valentes，um and if we look at if we just。

instantiated call prepare data and setup，so this is the pattern for like all of，our data modules。

prepare data downloads data from，somewhere and then set up，splits it into trainval test and then。

print data，where is it，yeah this uh daundered under wrapper，that's like reproduce right this is a if。

you overwrite this method on any python，class，then this is you return a string。

from this method that's the string that，will get printed if you print the object。

so that's what we do here and we just，print the number of classes and now，there's 83 classes。

actually，are right so there's four of these，special tokens which we'll talk about。

next week when we talk about sequence，processing but for now let's ignore them。

then there's the mnist digits then，there's uppercase letters，and then there's lowercase letters。

and then additionally i've added space，exclamation mark quotation mark you know，hashtag。

and all these different basic，punctuation marks，so these are kind of for the future but。

they're not part of em nest，what's part of em nist is just these，classes。

but we already include them in the，mapping it's just，you know there's not going to be。

examples of them，there's 260 000 images，in train each image is，of dimension 1 by 28 by 28。

why is there that extra one the reason，is because，it's the number of channels so it's a。

grayscale image there's only one channel，but for example an imagenet this would。

be three because you would have red，green and blue，so this is what pytorch expects so this。

is what we give it，and then around 60 000 validation 60 000，um to get a。

say okay data is our em-ness class，test data loader is a data loader that，returns。

test data if we wrap it in，an iterator then，we can call next，with it and that will return a single。

batch of data basically，and then we can print the shape the d，type data type。

and then basically some statistics about，this data，this is always useful to do just to make。

sure that your data is kind of what you，expect and it's like，um yeah i expect this to be a flow。

between zero and one，and here for example the max is one if i，saw that the max was。

255 or something then i would，then i would know that i probably forgot。

to you know do some processing，so this looks good to me 128 is the，batch size by default。

and so what we can do now is we can，actually just print uh or plot rather，some of these。

images and uh the title of each subplot，is going to be the label，right so this is 9，this is l 8 1。

9 7 capital z capital w，and this is supposed to be 2 but it，really is going to be hard to recognize。

that as a two，at least for me okay and then what we，can do now is we can actually train。

a base uh cnn model，and there's a couple of ways we can do，it we can do it in the notebook。

and uh we can just import python's，lightning，import our cnn model which we'll take a。

look at in a second，and import our base lit model，instantiate the cnn model instantiate。

the lib model with the cnn model，instantiate the the trainer give it a，gpu。

say it's going to train for like five，epochs maximum。



![](img/c6447571d36e972507177863ebd07405_31.png)

and then fit the lid model on the data，that will start training it'll print you。



![](img/c6447571d36e972507177863ebd07405_33.png)

know what the mod looks like，and it'll eventually get to like 80，accuracy。

uh you know if we train longer it'll go，higher but whatever um，and then we can actually ignore that。

we can look at another random sample，of data and then this time we can both。

look at the correct label and also the，predicted label，so the code for that is here um。

but basically by applying the model to，the image we get，logit by taking the，of the。

class that has the highest activation，and then we can look up the label of，that class in the。

mapping of the data set and we simply，show it。

![](img/c6447571d36e972507177863ebd07405_35.png)

what it is so on this set of test data，it's actually。



![](img/c6447571d36e972507177863ebd07405_37.png)

you know fully correct so that kind of，gives us confidence，so this is one way to train but you know。

i really don't like training in the，notebook this is really just useful for。



![](img/c6447571d36e972507177863ebd07405_39.png)

saying to checking but if we want to，train，last week we can still you know in，collab or。

on our computer in the terminal run，python，training run experiment and then give it。

all the things that we care about as，command line arguments，so one thing we care about is max epochs。

gpu，let's actually ignore that for now the，data class is going to be。

em nist the model class is going to be，cnn so let's go，so the first thing it does is it'll。

download the data set，and this will have this will also happen，each time you launch a collab。

so that's another slightly annoying，while it does that we can take a look at。

our new model called cnn so from last，week you might remember our mlp model。

still here now we also have a cnn，and the cnn model is really a very like，lynette like model。

there's going to be one conf，block two another one，a max pool and then a couple of fully。

and the forward method is just apply the，block，apply max pool apply the drop out，flatten everything。

apply fully connected value and then，another fully connected，so i said it's a conf block so what's a。

conf block，i also defined that here and so you'll，notice this is also an nn module。

just like the overall cnn is an n module，and so this is really，a powerful thing about you know how。

pytorch，is built is that you can use what's，basically a model，as part of a different model right so。

this is like cnn is a bigger model，of which some part of is a comp block。

which is in itself a model right that，has a forward method，and an init method and everything and。

just，applies a conf and then applies a volume，it looks like it's going pretty well。

so one thing i mentioned in the readme，is this num workers argument so that can，really speed up。

training and what it does is basically，we want the gpu to be as busy as，possible，date。

the data is getting loaded onto it right，so each batch of data，has to be loaded onto the gpu while。

that's happening the gpu is not，processing，if to load a batch of data on the gpu。

requires processing of that data，on the cpu then actually，you know the gpu has to wait for the cpu。

to like finish processing data，then put a batch on the gpu by adding，this num workers argument。

we essentially start separate processes，that are able to prefetch the data and。

pre-process it in separate cpu threads，such that there's always a queue of you。

know batches ready to be put on the gpu，so the gpu spends less time waiting。

so that's a helpful flag to start adding，and you usually want to set it to the。

number of cpus on your，four，on on the collab and then another thing，i want to talk about。

that's kind of useful is this overfit，batches，flag and so if i give this to，um on the command line。

if i uh use a float between zero and one，then it'll say like you know only use，this。

this fraction of the data only use that，test，also test on that same set of data。

if i say some number of integers like，two or greater，um then it's actually like this like，be。

trained on and the reason this is useful，is because，you actually want to see your model，overfit。

on just a you know a limited number of，batches like two batches。

because if your model can't overfit on，this limited amount of data then it，possibly can't represent。

so i'm going to put overfit batches 2，i'll put that num workers in there。

and i'm actually going to boost the，now，going to be just these two batches so it。

used to be five but i'm going to boost，it over 250，okay so it's learning pretty quickly。

it's now getting to be，97 accurate 98，accurate 99 accurate so i feel good that，this model。

that we have is actually able to learn，on this data because it's able to，overfit。

to just a couple of batches and josh is，going to talk more about this method。

of basically debugging neural networks，in his lecture，a few weeks from now but it's something。

that you can start using，you know already um，okay and then i'm gonna explain what the。



![](img/c6447571d36e972507177863ebd07405_41.png)

homework is and then take questions，after that。

![](img/c6447571d36e972507177863ebd07405_43.png)

![](img/c6447571d36e972507177863ebd07405_44.png)

in the cnn。pie that we looked at。

![](img/c6447571d36e972507177863ebd07405_46.png)

so there's our conf block and there's，our cnn，architecture so just mess。

you know edit it to to improve it in，some ways，so one thing you should definitely do is。

edit the conf block，to be more of a resonant block right as，shown in this image from lecture。

so right now it just does a convent。

![](img/c6447571d36e972507177863ebd07405_48.png)

value can you make it do，this like identity residual connection，and another con。

and then part of the resnet paper is，actually a thing called batch norm i。

didn't really talk about it，but if you want to add that you're，welcome to。

you can take a look at the official，resnet pytorch implementation。



![](img/c6447571d36e972507177863ebd07405_50.png)

for uh basically how to do it，we have a max pool in here and as，as we covered with josh uh it's been。

falling out of favor。

![](img/c6447571d36e972507177863ebd07405_52.png)

in in favor of a strided convolution so，you can try removing it and adding a。



![](img/c6447571d36e972507177863ebd07405_54.png)

strata convolution，there's some command line arguments for。



![](img/c6447571d36e972507177863ebd07405_56.png)

the comp dimension and the fully，connected dimension you can add more。



![](img/c6447571d36e972507177863ebd07405_58.png)

and i think a really cool one to add，would be，like right now there's two comp blocks。

it'd be cool to add，a command line argument for the number，of comp blocks。

right and then dynamically create。

![](img/c6447571d36e972507177863ebd07405_60.png)

as many comp blocks as the as you，requested on the command line，so if you do like a couple of these。

then you just paste what you did in。

![](img/c6447571d36e972507177863ebd07405_62.png)

grade scope you explain what you did and。

![](img/c6447571d36e972507177863ebd07405_64.png)

so the last thing i want to talk about。

![](img/c6447571d36e972507177863ebd07405_66.png)

today when it comes to the lab，is making a synthetic data set，so we're looking at like single。

characters still，but we know that our goal is to be able，to recognize。

whole you know paragraphs of text so，next week we're going to take a step，towards it。

and recognize lines of text like，recognize all the text within a line of，text。

and to this week we'll just make our，data set，for doing that okay so it's a notebooks。



![](img/c6447571d36e972507177863ebd07405_68.png)

so we do our standard imports this time，we import a new data set called。



![](img/c6447571d36e972507177863ebd07405_70.png)

and the idea is that we want to be able。

![](img/c6447571d36e972507177863ebd07405_72.png)

to create basically lines like this，um and part of what we need to do is，first we need to generate。

sentences that are realistic right，because，we're kind of working our way up to。

recognizing real english language，handwriting，so the first thing we're going to do is。

we're going to synthetically generate，english language sentences and then，create。

you know fake handwritten lines from，them。

![](img/c6447571d36e972507177863ebd07405_74.png)

so we made this thing called sentence，generator you can take a look at it。



![](img/c6447571d36e972507177863ebd07405_76.png)

it's in data sentence generator，it uses a data set called the brown，collection，of basically text。

and we have like a pretty lightweight，sampler of，uh strings of text of some max length。

from it so if i say sense generate，sentence generator dot generate max，length 16。

it will generate sentences of，up to that length but most of them will，be shorter right so here's。

four that i got and we can，create uh an amnes lines data set，it's first loads mnist。

the data set that we just looked at and，the mapping is the same as the mnist，mapping。

but it also has these parameters called，max length so that's the maximum number，of characters，like。

minimum overlap between characters next，to each other，and then max overlap um so that's like。

how much can they overlap，right there's some code you're welcome，to take a look at。

but what it does is it basically，generates，things like this so the first one i say。

um maxline 16 max overlap zero so that，means there will be no overlap between，characters。

each character will have its full width，there's a special token p which we use，for padding。

so our sentence generator，the max length is 16 the sense it，actually generates is going to be up to。

16，so just to be uh to have，inputs of equal size we're going to pad。

the rest of it with the special padding，token。

![](img/c6447571d36e972507177863ebd07405_78.png)

so here are some sentences in the data，set and then here's what the。



![](img/c6447571d36e972507177863ebd07405_80.png)

input images looks like look like so，it's literally。



![](img/c6447571d36e972507177863ebd07405_82.png)

sampling characters from mnist and then，putting them next to each other。



![](img/c6447571d36e972507177863ebd07405_84.png)

and this doesn't look so bad，but we can make it more difficult we can。

say okay how about max length 34。

![](img/c6447571d36e972507177863ebd07405_86.png)

characters and then the the characters，can overlap。



![](img/c6447571d36e972507177863ebd07405_88.png)

by up to a third so we can create that，and now it's starting to look more like，at least my。



![](img/c6447571d36e972507177863ebd07405_90.png)

handwriting you know kind of like a very，poor handwriting，um that's going to be a challenge for。



![](img/c6447571d36e972507177863ebd07405_92.png)

our model and we can make it more，difficult yet，so take a look at this data set there's。

no homework associated with it，it's something we're going to be using。

more next week but i just wanted to，introduce it。

![](img/c6447571d36e972507177863ebd07405_94.png)

that is about it that's all that's in，the readme，so i look forward to what you guys do in，the blob。



![](img/c6447571d36e972507177863ebd07405_96.png)

um you know make it more of a resnet。

![](img/c6447571d36e972507177863ebd07405_98.png)