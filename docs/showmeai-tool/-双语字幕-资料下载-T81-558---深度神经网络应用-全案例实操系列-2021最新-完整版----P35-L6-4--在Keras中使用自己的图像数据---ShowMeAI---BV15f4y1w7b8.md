# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P35：L6.4- 在Keras中使用自己的图像数据 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton， welcome to applications of Deep neural Networks with Washington University。 so most of the image examples that we've seen so far like the Menst and CFFAR were loading digits。 using convenience methods that CAs provide you。This certainly makes for short code and relieves you of the drudgery of loading these images in yourself。 but it's important that you know how to take raw images。

 raw JpeEgs and PGs and actually get those into your own projects。 We're going to learn how to do that in this video for the latest on my AI course and projects。 click subscribe in the bell next to it to be notified of every new video。 Now to do this with your own images， let's take a look first at what this looks like when youre using convenience methods。



![](img/aa5872116e23663fcd5ec6ce107ce8b1_1.png)

So if you look inside Tensorflow Carra's data sets。 this basically gives you access to a lot of data sets that are already built into Cars。 and they're quite easy to get access to just Google this Tensorflowlow Carras data sets and you'll see an entire list there's I think under 10 but close to 10 different data sets that are built into Cars for your use。 we're using the C4R 10 and we're going to also use nuumpy just to help us take a look but let's look at what it looks like when we actually load it。

 So we run this and if you did not previously use this data。 you might see a little download bar as it goes to actually access it because these datas are not all built into Cars。 it downloads into a temporary directory for you but basically you've got this low data command and that hides everything that's going on and in many of these data sets Cars will actually split it into train and test for you and like we've seen。Before in previous videos for this course， the reason that they split the train and test for you is they want to have consistent train and test results because these data sets were often used with academic papers and you truly want to compare your results to those who have gone before you Now there's not a lot of active research going on in CFR 10 really anymore it's been it's been used pretty much to death and they've got very good results on it you'll probably for a modern paper want to look at a more。

Current data set and that。Lots of interesting stuff going on with image。 Ne right now。 we'll see about that one in the next part。 So if we now look at the shape of one of these。 So X train， we got x train， Y train。 So this is your predictors。 This is the expected outputs。 the Y， and then similarly for test。 the shape of this。

 the format that you need to get your images into to actually make use of them。In Kiaz。Is a lumpy tensor。 I call this a tensor because its， it's more than a matrix。 It's a higher dimension matrix。 There's 50000 rows in the training set。 and then it's 32 by 32 for each image。This is how large icons were back on classic windows and Mac systems just to give you an idea。

 And then there's a color depth of three。 So these are very small low resolution images and we saw them in the previous section when we were looking at Resnet this is the form that you've got to get your images into So you'll load your JpeGs and PGs into memory process them。

 you'll want to get them to all the same size because you need to have some way that you reshape your images so that they're all in the same size。 that's very common in the sort of computer vision space if you want to handle images of different sizes。 you'll need to do something in your preprocessing if you're presenting to the neural network for prediction to resize it to an appropriate shape And if you think about a lot of the self-driving car and other computer vision robotics。 you're going to always be dealing with consistent sizes for your image。

Because your video feed is going to be flowing through some sort of a camera that is going to have a consistent resolution。 Now， if you're writing a web application， like we'll see later in this course。 and you're getting all sorts of pictures uploaded to you。 Like there is a fairly famous one by Microsoft that would tell you what breed of dog you had。

 you would have to scale those images to a consistent size deal with the vary aspect ratios as well as the various sizes of it。 and we'll see， we'll see how to do that， because our training sets for some of these when we download ping and Jpeg files from Caal competitions and other image databases。

 They're all different sizes。 So this is the target。 You want to get all your images into essentially X by y by three by the color depth。 This3。 that's going to usually either be a three or a1。 You do have sometimes4 for that。 But and that's a mask to show you what parts of the image to clip out。

 But usually you're not sending。The mask or the alpha channel off to computer vision。 Let's look at what an individual element looks like。 So there's 50000 of these。 Well。 if you take the first image in this， it's just going to be 32 by 32 by3。 but this is what it looks like。 I'm not pretty not the shape。 I could look at the shape of it。

 it would be be 32323。 you can see that basically it's a bunch of rows and columns。 So this is a single row。 And then inside of that row。 you have the individual colors。 Those are RGb values。 That's the three you have the three color channels。 and this is red。 green and blue。 They range between 0 and 255。 That's another thing you'll often see scale 0 to 255 is okay for neural networks。

 they can deal with that， but you're going to get better results。 if you scale it between 0 and1。 that's quite popular。 even more popular is negative 1 to1 because now it's centered about 0。 So we'll see how to do that。 Now all these numbers here。 this is not all 50000 elements。 this is just one。 And it doesn't show you M is not be。Does thattt dot when there's too many。

 that's just one image。 What we need to do is see how we can take a bunch of images that we have as training。 I've put these on the web。 Well I didn't put them here。 they were on Wikipedia before I ever found them so that basically we can run this either from Google coabab or locally and it's always going to find those images if you want to use your own local images。 which normally you will。 we'll see examples of that。

 in the next module when we get into the GNs for now。 we're just going to use them directly off the internet so that it's convenient we don't have to worry about where these images are actually residing。 So we're going to get all of these images。 we're going to try to ultimately get them to this format that we saw above here the 50000 by 32 by 32 by3 because then it's ready to go into Cars。 Carass is ready to deal with that。 So let's look at what we have here Now I have this function here called make square。

 This is just about as primitive as you can get as far as make square。Look at basically any image。 and you want to make it square。 There's several ways that you can go about doing this。 The most simple is you just chop off whatever the long side is。 So if something's not square。 It means that either it's more wide or it's more tall， whatever it's more of if it's more tall。

 you cut off something from the bottom。 if it's more wide， you cut off something from the right。 That is just about as primitive as you can do it， but this gives you a good starting point。 That's a favored one that I have for some of the assignment。 So you may see that。 I will probably ask you to do a more advanced making of a square。

 the assignment will describe that exactly。 But what we're doing here to do this。 We have to find out， is it more tall or is it more wide。 Are there more rows or they're more column and what I do then is I basically crop off whatever extra we have of that and I return the image you've got to deal with these two separately。 more rows。 So I'm just basically taking the amount。

Extra space that we have and I am trying to kind of center where I grab it so that I don't just chop off all from the right。 I try to chop off on both sides。 That is one technique that you can use。 So we'll go ahead and run this， but we're downloading these URLs part right here where we have response equals request URL that's getting them across the Internet。 If these files are already on your hard disk， you don't need this。

Nor do you need this bytes I O part of it， you need this。 And that would a stream across the Internet that's going to to pull that for you and load actually loads it in。 You would still have that if you're using the disk。 First。 we make it square that changes the aspect ratio of it。

 changes the size of whichever size was the longest。 Then we're going to resize this to the image height and width that we have specified。 and we're going to use antiallaing that's a image size changing technique that fills in additional It kind of averages values near to the edges of things to make the image overall look nicer。 And then we add the image to the training data list。 Now。

 it's important that list is just a normal Python list。So we're adding all these lumpumpy arrays into a Python list。 that's not going to work。 That's a hybrid almost of。Python list and nuy tensors。 So you want。 you want to do this to actually reshape the thing so that it is the image heighthen width that we've defined previously and the channels that's going to be three。

 We also do this to put everything in the range of negative one to 1 and center it about 0。 So we'll run that。 And now if we look at the training data。 it is truly all nuy。 Now this look very much like this。 The difference is this containing there's just a square bracket here。 Where it says array out here。 that array means nuy。And notice these are in zero to 255。Down here。

It's all lumpumpy。It is a one， two， three，4 d tensor。And these are between negative one and 1 now at this point。You have a lumpumpy tensor， a 40 array。 essentially that is ready to go。 You can train on this。 That is your X。 your while contain labels。 or it depends on what you're trying to do with your images。We'll see though， with images。

 you don't always just do classic classification and regression。 And the very next part。 when we look at something called Yo， you'll see that you we'll do a whole mix of regression and classification all at once。 which is really what's the nice， awesome thing about neural networks compared to more traditional models。 Now， once you've got this all set up and your nice 4D matrix。

 you might want to save this because it takes a while to crunch through all those images and process them。 believe me， when we get into the next part when we deal withganNs and we're dealing with tens of thousands of images that you're going pull into your Google Drive。

 you want to crunch through that once and not have to do that every single time。 This is normally when you pickle something， Pickle is the standard way to take a Python object and just store it away in a binary form so you can recall it real easily。 however， we are going to save it as nuy's own format。 because these。😊。This's not that big of a file that we have with just these couple of images， but believe me。

 when we get into the GNs and bigger training data。You're going to have a multi gigabyte file。 sometimes even bigger。 So you'll want to save it in something that can deal with that large of a file。 And since you're dealing with nuumpy， let's just store it as a nuumpy file and MPy。 It's a lot like pickle except it's just for nuumpy。 We run this and see that it is now saved it。

 You pass the filing without the extension， it puts the dot My on there。 If you did put an MPy B do nuy nuumpy。 So don't， you don't want two of those。 So now we can deal with our own images。 And this is important because it's boring to use the minced digits and the C far in even minced fashion。You want to do this stuff on your own images。 That's when this stuff really gets fun。

 And just to peek ahead into the next part， you can see I am using my own images。 Well talk about this one in the next part。 Thank you for watching this video。 Now that you've seen how to load images that are outside of the Kiras package。 We'll use this in the next few videos for more examples。 This content changes often。

 So subscribe to the channel to stay up to date on this course and other topics and artificial intelligence。😊。![](img/aa5872116e23663fcd5ec6ce107ce8b1_3.png)