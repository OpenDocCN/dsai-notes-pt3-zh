# P18：【Lab7】段落识别 - ShowMeAI - BV1iL411t7jE

hi everyone today we're doing lab seven，paragraph recognition。

special thanks to soar chandra for work，on this lab，in this lab we will do a couple of。

things we'll move from training on，synthetic lines，to training on real handwriting lines。

this will be introduced，in the i am lions data module we'll move，from training。

on just lines to training on whole，paragraphs and introduce the i and，paragraphs data module。

as well as the im synthetic paragraph，data module，will automatically save the best model。

from a set of experiments，and we'll also introduce the paragraph，text recognition class。

to load the model and run inference that，we can use in production。

so before we get started we're using，slightly newer versions of pytorch，lightning。

and wnb so just make sure to run，make pip tools to update your setup。

and we're also using git lfs to store，the model weights，there's a few new files there's a folder。

called artifact，paragraph text recognizer we have the，config，model pi torch weights and the command。

that was used to generate it，we have i am paragraphs i am synthetic，paragraphs。

and i am original and synthetic，paragraphs in the data sets，we have a new model called resna。

transformer and we have this new module，called paragraph text，recognizer as well as in the training。

we have safe best model so the first，thing we introduce，is this resna transformer which is。

the same transformer model as line cnn，transformer，but instead of using our kind of。

homebrewed line cnn，we're using the torch vision provided，resnet，so we can check it out in resna。

transformer。pie，so it's lab 7 text recognizer models，but instead of the line cnn for the。

encoder we're using the resnet，and we're using the torch vision models，resnet18。

we're not using pre-trained weights uh，we could but，our data is pretty different than，natural images。

it's all grayscale images so we might as，well just train it from scratch。

and then we'll exclude the last two，layers of，the resnet which average pool over the，whole image。

and then add a linear layer to go to，imagenet classes，so instead of doing that we'll just，output。

batch size by resonant dimension which，is 512，by the kind of height and width of。

what the resnet outputs which actually，reduces it by，a factor of 32 of the input image size。

because it goes through，a number of strike two cons，this，resnet transformer is。

so yeah we run the input through resnet，which actually we need to duplicate the，number of channels。

in the input data because resnet expects，three channel input images we have one，channel input images。

so we just replicate it across that，dimension，and then we generate the。

resonant dimensional output we project，it to，the embedding size output so that it，matches our。

decoder transformer would that expect，and furthermore we encoded，or we positioned and code this。

resnet output and there's one thing，special about that，which is that we're using the positional。

class which is also new so let's take a，look at that，so we actually um add 2d encodings。

so in a normal transformer positional，encoding you have a sequence。

that you are adding positional encoding，to，but here we have basically a。

two-dimensional sequence right also，known as an image，and so we want to add two-dimensional。

position one coatings so that's an，encoding that respects the x-axis。

and the y-axis and that's what we do，here，if you want details of this you can read。

the code you can also read。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_1.png)

a paper that，describes our handwriting recognition。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_3.png)

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_4.png)

over at turnitin written by sumitsang，so you can get the pdf there，okay so that is。

basically that for resna transformer，there's a new data called ion lines we。

actually introduced it in the previous，lab but we didn't train on it。

so just in case you forgot what it looks。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_6.png)

like we can look at it using this，zero three look at ion lines notebook。

and it's you know real handwriting from，a number of different writers。

and i am lines this is line based data。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_8.png)

long so we can train on，this data set python training run，experiment。

we'll lock the wnb we'll use all the，gpus，and um we can use line cnn transformer。

we can use resnet transformer。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_10.png)

and if we use resnet transformer。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_12.png)

so you got one decrease of validation，loss a little bit of a plateau and then，a second decrease。

and the loss goes down to 0。2，the character error rate goes down to，around 9。4 percent，loss。

and the and the character error rate。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_14.png)

might keep improving，further we cut it off here so we got，final test character air rate of 11。7。

percent which is pretty decent，you can get down to like five percent，character error rate。

um with this setup you just have to kind，of tweak the parameters。

so now that we confirmed that i am lines，works let's。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_16.png)

move on to whole paragraphs and to look，at the paragraphs，we have a new data set called i am。

paragraphs we can look at it，in this notebook so，a thousand images in train，260 and val 230 and test。

and each image is 576 by 640，pixels and the max，sequence length is 682。 so let's take a。

look at some training images，so this is the label start token and，token。

and then the text and there's a new line。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_18.png)

character basically that we render here，and our transformer model will actually，learn to reproduce。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_20.png)

so this is the palace cinema at buckley，near chester。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_22.png)

will be okay great and then there's data，augmentation you can see the。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_24.png)

um the text region kind of moves around，the image。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_26.png)

and is like skewed and there's contrast，changes and stuff like that in testing。

none of that happens it's always。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_28.png)

perfectly centered，and the contrast is not really messed，with，same as ein lines okay。

so that is i am paragraphs and there's，another data set，we introduced because there's actually。

not that，much data here right um，we made a synthetic paragraph data we。

called it i am synthetic paragraphs，you can take a look at the file if you，want。

but here we basically just generate our，own paragraphs，lines，so we just stitch together lines any。

number of lines，up to some number and then we generate，the label。

and we encode it or you know we position，the resulting paragraph somewhere in the。

image so this gives our model like a lot，more data to kind of。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_30.png)

let's go back to the readme，so we have i am paragraphs with the test，you know with the actual。

original data we have im synthetic，paragraphs which we can also use for。

beefing up our training data set and，then at training time we want to use，both of them。

right we want to use both the synthetic，paragraphs and the real paragraphs。

so we have an i am original and，synthetic paragraphs data set，which is here text recognizer data。

i am original in synthetic paragraphs，and this is kind of interesting we。

basically just instantiate both the ion，paragraphs and the ion synthetic，paragraphs。

and then prepare both of them set up，both of them，and then in our own setup we say concat，data set。

the the two of them and concat dataset，is something that torch gives us。

so it's basically just all you have to，do，and things just work so that's quite，nice。

if we train on it，am original in synthetic paragraphs with，um it will eventually get down to。

17 test air raid，and that's in just a thousand epochs。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_32.png)

this is actually on 8 20 80 tis so this，is quite，and it looks like it would keep。

improving if we kept the training but we，just cut it off at around a thousand。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_34.png)

epochs and we're logging the predictions，so we can take a look。

they will not work in union if physical，power spiritual power，and visionary power okay and then this。

is the prediction，they will not work in union physical，power spatial following vision and power。

is not united。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_36.png)

so it's basically perfect here，and that's on the validation set and。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_38.png)

some test examples，so he put up for the night at the，admiral's head，comma that famous okay。

so he put up for the right at the。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_40.png)

admiral roles，period head so there's some mistakes but，overall it's。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_42.png)

it's really great um。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_44.png)

yeah so that is。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_46.png)

around 17 character error rate，okay so let's say we've ran some number，of experiments。

and so we have um our runs。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_48.png)

we have our project we have the user，we now have a script called，trainingsafebestmodel。pi。

where we can run it give it the entity，so that's the，and then the data class that it trained，on。

and it will look in the project find the，best run by validation loss。

and you can overwrite override the，metric that you used to find the best，model。

by providing metrics you could find the，best model by validation。

character error rate or test character，rate or whatever you want。

but either way it will actually query，wnb，to you so，after you have saved the best model it，will。

or you know it finds the best model and，it saves it to，a new location which is in text，recognizer。

artifact paragraph text recognizer，and now we store config json，the pi torch weights and the command。

that was used to，generate it the conflict json is just，all the。

basically hyper parameters that we use，to，train it not all of these are actually。

kind of hyper parameters for the model，it's just all the argument，command line arguments that are。

run experiment that pi script accepts，which includes some pythorgs lightning。

training things like gradient clip valve，stuff like that but it also includes our。

actual hyper parameters like，like a transformer number of heads，transformer dimension and so on。

so the idea is we're able to recreate，this exact model，if we check out you know the git commit。

that generated it and run this command，we should get this exact model back with。

and the reason we save it there is，because we also introduce，text recognizer paragraph text。

so this module is basically for，recognizing，text in an image um，the。

data that we need to kind of know about，so that we have the mapping of，indices to characters。

we get the transform that we，use to train so that means like how do，we actually convert。

a python imaging library image to a，pytorch tensor，we load the config we instantiate。

the model with the config and the lid，model，with the config and the weights。

that we stored and then we switch the，model into evaluation mode so that like，dropout。

just in general everything is in，evaluation mode and gradients aren't。

computed and so on and then we have a，predict method，which takes an image file name opens the，image。

our model expects，transforms it to a tensor runs it，through the model，to。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_50.png)

a string then returns the string，and then we can look at those，predictions in a notebook called。

and here we go so these are trane veils，trained val samples so。

i read as it is with so much of our life，already in a predetermined groove。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_52.png)

and then the model read one s it is。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_54.png)

with so much of our life already in the，predetermined grove，and so on it's pretty close this is。

train volley so this is，stuff that the model has seen in。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_56.png)

so these images the model has never seen。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_58.png)

i read she was engaged to nigel had been，for two years，sometimes they talked on the theme of。

when we get married，she was engaged to uggid had been for，though years，behalf。



![](img/fbe43c373add6ec80e9d3cdcb887fd9c_60.png)

of once we go married so this is like，17 character error rate you can tell，it's not。

super great um and we are able to get，much better，we can get some 10 percent character。

error rate if we，if we train more and with different，hyper parameters。

so one interesting failure mode by the，way of the model，is repeating lines so。

here it's i guess it says gay went out，to the waiting taxi，and then found that in the excitement of。

meeting gavin，she had left her son okay but then here，it says going。

after okay whatever in the excitement of，meeting and then the excitement of，meeting again。

and then she and then it repeats the，next line repeats the next line and so，on。

so this is due to the transformer，obviously uses attention，and the problem with the tension might。

be that，it actually gets a little confused about，where it's supposed to look next。

and so it just looked at this line but，then i might actually look at the same，line again。

so in order to fix this perhaps we could，mess with our position，encoding and try to make it a little。

different so that it's kind of like，the positions are more different as you，go down。

um we could also just increase the，number of heads or the number of layers。

but we can mess with hyper parameters。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_62.png)

and try to，make this a little better okay so no，files，maybe try training this yourself and the。

next time we're going to add tests for，this new recognizer class。

we'll add some other tests and as was。

![](img/fbe43c373add6ec80e9d3cdcb887fd9c_64.png)

so that is it for lab seven paragraph。