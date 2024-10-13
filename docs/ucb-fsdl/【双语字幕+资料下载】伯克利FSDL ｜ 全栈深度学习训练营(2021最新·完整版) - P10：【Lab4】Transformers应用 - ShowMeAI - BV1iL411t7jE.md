# 【双语字幕+资料下载】伯克利FSDL ｜ 全栈深度学习训练营(2021最新·完整版) - P10：【Lab4】Transformers应用 - ShowMeAI - BV1iL411t7jE

![](img/392cf1605a1627f98975b05d76f36c39_0.png)

okay so lab four，is going to be about recognizing，synthetic sequences。

same same ones that as before but this，time with transformers，okay so we're going to introduce line。

cnn transformer class and the，transformer lit model class，let's talk about the line cnn。

transformer so in lab 3，if you remember we trained a line cnn，which is。

a cnn that takes an image of a line of，text，and then basically applies a sliding，window。

produces outputs we ran those outputs，through an lstm，and then we trained it with ctc loss and。

that worked pretty well i think the best，we got is like maybe，around 17 percent character error rate。

on the validation set um in this lab，we're going to do，very similar thing we're still going to。

use the line cnn architecture，but we're going to send it through。

transformer decoder layers instead of，the lstm model，and we're going to train it with just。

what we'll talk about in a second okay，so。

![](img/392cf1605a1627f98975b05d76f36c39_2.png)

where is the line scene on transformer，so we go into lab 4。



![](img/392cf1605a1627f98975b05d76f36c39_4.png)

we go into text recognizer we go into，models，and now we find the new one which is。



![](img/392cf1605a1627f98975b05d76f36c39_6.png)

![](img/392cf1605a1627f98975b05d76f36c39_7.png)

so first there's a class called，positional encoding。



![](img/392cf1605a1627f98975b05d76f36c39_9.png)

which is what it sounds like it's，kind of strange that pytorch doesn't。



![](img/392cf1605a1627f98975b05d76f36c39_11.png)

uh generate square subsequent mask so，that's that triangular。



![](img/392cf1605a1627f98975b05d76f36c39_13.png)

attention mask that kind of masks out，the future。

![](img/392cf1605a1627f98975b05d76f36c39_15.png)

and then here's the main class line cnn。

![](img/392cf1605a1627f98975b05d76f36c39_17.png)

this stuff is the same as online cnn，lstm。

![](img/392cf1605a1627f98975b05d76f36c39_19.png)

um we instantiate the underlying line，cnn model，and then we have a couple more a couple。

of new classes。

![](img/392cf1605a1627f98975b05d76f36c39_21.png)

one is the embedding class which we'll，use to。

![](img/392cf1605a1627f98975b05d76f36c39_23.png)

embed our target characters，right so we're predicting from an image，to a string of characters。



![](img/392cf1605a1627f98975b05d76f36c39_25.png)

we're embedding the target characters，with this embedding layer。

and then the fully connected layer is。

![](img/392cf1605a1627f98975b05d76f36c39_27.png)

going to be kind of at the output，we have a positional encoder we have，just this。

triangular mask that we're going to。

![](img/392cf1605a1627f98975b05d76f36c39_29.png)

reuse so we can just kind of instantiate，it here。

![](img/392cf1605a1627f98975b05d76f36c39_31.png)

and then we have the transformer decoder，which is using the pytorch transformer，decoder model。



![](img/392cf1605a1627f98975b05d76f36c39_33.png)

which takes a transformer decoder layer，and has，a num uh takes a parameter for the。



![](img/392cf1605a1627f98975b05d76f36c39_35.png)

number of layers，so by default we are using four，transformer layers and each layer。



![](img/392cf1605a1627f98975b05d76f36c39_37.png)

has four attention heads and the，dimensionality。

![](img/392cf1605a1627f98975b05d76f36c39_39.png)

of the transformer layer output is 128。so when we take a forward pass。

the input is x which is the image，batch size by height by width but，there's a new input which is。

actually y which is actually，the output we're supposed to predict，right and it takes，length。

sub y and each element of that sequence，is uh an integer between 0。

and c minus 1 where c is the number of，classes or the number of our characters。

what we produce and forward is a tensor，that's batch size，by the number of classes by sequence。



![](img/392cf1605a1627f98975b05d76f36c39_41.png)

length，logits so x is the image input we run it，through line cnn，that turns it into batch size by。

embedding size by sequence，x sequence or s of x the sequence，dimension，of this line cnn。

we just kind of normalize it a little，bit it's done in the transformer，literature so we do it here。

then we send it through this positional。

![](img/392cf1605a1627f98975b05d76f36c39_43.png)

encoder，so we add the position。

![](img/392cf1605a1627f98975b05d76f36c39_45.png)

basically to the sequence，then we take y which is actually the，output we're supposed to predict。

we run that through the embedding we run。

![](img/392cf1605a1627f98975b05d76f36c39_47.png)

it through a positional encoder。

![](img/392cf1605a1627f98975b05d76f36c39_49.png)

we apply the mask to it so that adds，a future masking and then we use the，transformer decoder。

to run y x and y mask through it。

![](img/392cf1605a1627f98975b05d76f36c39_51.png)

which produces the output which we，additionally just run through，last fully connected layer and that。



![](img/392cf1605a1627f98975b05d76f36c39_53.png)

gives us our sequence，to train it we use the transformer lip。



![](img/392cf1605a1627f98975b05d76f36c39_55.png)

model，which is in lit models transformer，there's nothing too fancy in here we are。

back to using cross entropy loss as our，loss function。



![](img/392cf1605a1627f98975b05d76f36c39_57.png)

we're not using ctc laws，we're still using character error rate。



![](img/392cf1605a1627f98975b05d76f36c39_59.png)

for our metrics，and we're actually going to i forget if，we did this。



![](img/392cf1605a1627f98975b05d76f36c39_61.png)

![](img/392cf1605a1627f98975b05d76f36c39_62.png)

okay we did it yes we're going to ignore，the start token and the padding token。



![](img/392cf1605a1627f98975b05d76f36c39_64.png)

in calculating the error rate okay，so to take a training step we just have。

our x the image y the true sequence，from the batch we run，x the image and y up until the last。



![](img/392cf1605a1627f98975b05d76f36c39_66.png)

um character through the model，and then we compute the loss on what's。



![](img/392cf1605a1627f98975b05d76f36c39_68.png)

output，and the ground truth starting from the，first。



![](img/392cf1605a1627f98975b05d76f36c39_70.png)

not from the zeroth token but from the，first token until the end，and the idea there is like well the。

model is supposed to predict，one step ahead basically from what it，sees and so we have to。

compute the loss on you know uh，offsetting the ground truth by one，it's。



![](img/392cf1605a1627f98975b05d76f36c39_72.png)

i think covered in the reading this week。

![](img/392cf1605a1627f98975b05d76f36c39_74.png)

okay and then validation we do the same，thing and then we also calculate。

the actual character error rate now to，do that we need，not just the logit but we actually need。



![](img/392cf1605a1627f98975b05d76f36c39_76.png)

the the prediction of the model，so if you remember in the ctc lit model。



![](img/392cf1605a1627f98975b05d76f36c39_78.png)

in order to make a prediction，we had to do this greeted decoding right。



![](img/392cf1605a1627f98975b05d76f36c39_80.png)

of the lock probabilities。

![](img/392cf1605a1627f98975b05d76f36c39_82.png)

in transformer we have to do something，similar like there's a，separate step to predict the function。



![](img/392cf1605a1627f98975b05d76f36c39_84.png)

or the method is is in the model so，let's look at line scene and transformer。

predict method so we take an image，this time we don't take the ground truth。



![](img/392cf1605a1627f98975b05d76f36c39_86.png)

label because we don't know it and we，output，a tensor of basically sequence lengths。

like same thing that the ground true，same same shape as the ground truth。



![](img/392cf1605a1627f98975b05d76f36c39_88.png)

right。

![](img/392cf1605a1627f98975b05d76f36c39_90.png)

and uh what we do is we run the image，through the cnn，position encoding then，up。

incrementally right so they they start，as just，all padding it's like a vec it's a。



![](img/392cf1605a1627f98975b05d76f36c39_92.png)

vector basically of all padding tokens，except the first token is set to be the，start token。

which lets transformer know that that's，the start of the sequence，and then we do a loop。

where basically for each element in the，output sequence，we take uh the current。

encoded image and we take，the all the tokens that have been，predicted so far。

which starts with just the start token，run them through the embedding run them，through the position。

coding and then run them together with，the image，through the transformer decoder。

and that gives us the output which our，logits，then we take the arg max to the to take。

the maximally certain prediction，and we put that as another output token。

so we start with just the start token，and then we predict the next token and。

then we take the first two tokens，and we predict the third token and so on，and we actually do it。

for just max output length but if you，want to speed this up in the homework。

you can actually stop decoding the first，time we produce，a padding token or the untoken。

the end sequence token and that will。

![](img/392cf1605a1627f98975b05d76f36c39_94.png)

speed up this predict method。

![](img/392cf1605a1627f98975b05d76f36c39_96.png)

so that's basically all there is to it，to train this we do python run，experiment。

i find that you have to run it for more，epochs so i just set it to 40。

run it on gpu some number of workers，em this lines same as we trained the ctc，loss on。

model class 19 and transformer i said。

![](img/392cf1605a1627f98975b05d76f36c39_98.png)

12，just just for the heck of it you can set。

![](img/392cf1605a1627f98975b05d76f36c39_100.png)

it to whatever you want，um there's a couple of things i'm，forgetting to do conda activate fsdl。



![](img/392cf1605a1627f98975b05d76f36c39_102.png)

text recognizer 2021 and then go into，lab form，so it loads the data this is the model，there's 1。

9 trainable params，that's more than in the lstm model，and then it starts training and for me。

after 40 epochs i got 17 character error，rate，which is basically the same as what we。

got with the lstm and ctc model，in the homework you can just try，different hyper parameters as in。

you know different window width window，you can add command line flags here。

so that you can set some of，these transformer specific variables。

and like i mentioned you can speed up，the predict method，that's all there is to it you guys have。

any questions about this lab。