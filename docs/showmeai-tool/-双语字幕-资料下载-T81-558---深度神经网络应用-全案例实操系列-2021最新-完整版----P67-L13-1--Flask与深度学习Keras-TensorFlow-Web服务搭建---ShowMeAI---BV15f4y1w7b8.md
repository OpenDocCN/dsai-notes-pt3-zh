# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P67：L13.1- Flask与深度学习Keras／TensorFlow Web服务搭建 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton welcomed to applications of deep neural networks with Washington University In this video。

 we're going to see how you can use something called flask for Python。

 and that will allow you to deploy a Psyit learn model or a neural network that you've created with Kiras。

To your own web server or even to the cloud for the latest on my AI course and projects。

 click subscribe in the bell next to it to be notified of every new video。

 Now Flask is one of those things that does not work particularly well in a Jupiter notebook。

 nor does it work particularly well in Google coab because Google coabab is based on Jupiter notebooks。

 usually you're going to run these flask applications through a command prompt or something such as that。

 And that's the case that we'll be doing here。 I'm going to show you one application of flask。

 where we'll run it actually out of a browser， but flask is meant to be on the receiving end of browsers not to be ran from one。

 So flask is a web server。 Basically， it lets you take your Python applications and turn them into web server web service applications In this case。

 we're going to create an API endpoint。 So application programming interface API and we will receive requests from other locations。

 these could be other programs。 These could be web sites themselves。

 whatever you're going to get a HttP or。😊。

![](img/5296890b8c9d0dcc242ead17d46b9fee_1.png)

Ht Tps request。 it's going to come in and you're going to service it with a neural network and return the results back。

 Now， this is showing you how to do this in flask。 Flask is a development platform。

 Mean it's not meant really for production。 Now that being said a lot of people do use flask in production。

 but it's not really intended。 There's something else called gunnaorn。 gunnaorn。

 this is the more production ready。 So if you're truly going to deploy this in some way。

 I suggest using gunnaorn because it works very well handlinging lean simultaneous requests coming in。

 So if you need to run two neural networks at the same time because you've got two requests coming in for potentially two different customers。

 you don't want to have to wait till one ends。 like you would have to do because of the global instruction lock that is inherent in Python and therefore in flask。

 I do have a link to a flask quick start if you want to read through that。

 not specific to neural networks。 So this is our first flask application。 I will run it from Jupiter。

 It's typically not a good idea， but it's a good example。

 if I were one of these crazy Internet channels。I'm blowing things up。

 I would say don't try this at home。 But you won't lose a finger doing this。

 I guarantee you create a new flask instance。 And this is important。

 This means it's going to service the root of the URL。 it is going to run off of local host。

 So if you are running this in a production environment。

 You probably have W Wheton research co or whatever your name is。

 And it would probably be on 80 and not 9000。 although often you deploy these as Docker images。

 So typically you would go ahead and put this on 9000 And then you would just map that to whatever actual port you wanted to go to when you run this。

 it's going to be running here。 So let's go ahead and run it。 Now notice little star is going。

 I should probably wait for that to finish。 Well， that would be a long wait。

 Its it's sitting there waiting for our connections coming in。

 So this is one of the reasons it not conducive to Jupiter notebooks。

 I can't do a run all and just run all the cells in here because it would get stuck and stop there。

 when you're done with it， you just click the box and stop it。

 but let's go ahead and look at the web server that's actually running。 So here this actually。

Sent a HP request from this tab to this tab。 and I got the result back。

 Now we'll see how to actually deploy this to the cloud。

 and I truly will be able to access this as a scalable web service。

 but for now it's simply running on my local instance here。 and you can see the log coming in。

 It simply says a get request came in。 You'll see these favorite icons all the time unless you put I usually put a favorite icon in there just so that the browsers quit pesting me about it。

 but that is something that you really don't need for a web service because this in this part。

 we're not going to see any Gi whatsoever。 We'll create a web application later and react to actually access this。

 But for now， this is just API endpoint。 Let's go ahead and stop this。

 And now we're going to run the miles per gallon neural network that we created earlier。

 We're gonna train one save it to a binary file to an H5 file load it and we're going to create a flask application that expects input like this。

 you give it number of cylinders displacement horsepower。

And it will predict how many miles per gallon that car is going to have。 Now。

 I will show you how to access this web service in several different ways。

 We're gonna to see how to access it in pure Python。

 We're going to see how to access it also from a very powerful utility called postman Postman。

 let me just literally copy and paste that into it and send it to the web service。 First。

 let's see what the web service actually looks like。 Now， this is the training。

 typicallyy you are not going to train a neural network inside of a web service。 never say never。

 there are applications where you'll do this。 but usually you're going to train the neural network somewhere。

 then transfer that train neural network saved as an H5 file or later a protocol buffer。

 We'll see that too。 and actually deploy it into the cloud or somewhere else here you can do the training in Jupyter notebook。

 No problem。 This is just like what we've seen before。 I have essentially the autompg file。

 We're going to load it。 We're going to train it。 We're going to train it。

 We handle the missing values in horsepower。 This is all just training。

 So let's go ahead and train this。Now， if you forgot to stop your web server up there。

 that'll be an endless star and it trains it and it's done。 So we essentially now need to save it。

 which is done here。 Well， let's do a sanity check and make sure that the root mean square errors about what we would expect and it's not a good that I've seen three。

3 is about what you usually get on this but I don't care the goal here is really to test deployment。

 So we're going to save it to an H5 file put in that DNA folder that I have。

 that's where all the temporary neural networks are saved to。

 It's not saved not to get tub so you won't see anything there。

 but this is where you put all the neural networks at least in my class that you train。

 So the files there。 this is also quite handy So we're going to post and get back up here。

 We're going to post this to the web application。 Well。

 what happens if they put something in here that is not part of the set like the color of the car Who cares The color of the car is nothing to do with miles per gallon or they forget to tell you something really important like weight。

 those are errors。 Also what happens if the weight is outside of this bounds。

 What if you give it a car that weighs 50000 and it's bad。

So what we do here is I perform a quick analysis of the data。 Let me just run this。

 So you see what it produces。 Look at this。 This is a nice Python。

 and also Json Matt of all of these fields。 So we know that we need each of these fields。

 And these are the men and max。 in the train data。 You don't want to exceed the trained data set size。

 neural networks don't do well with that。 So if you gave it one cylinder。

 it goes all polynomial on you。 And you know what polynomials look like as they get outside of the range。

 they very quickly go to positive and negative infinity。 depending on polynomial。

 neural networks do much the same。 So you， you need to be careful outside of the range of neural networks。

 This， I also use to test it。 So let's go ahead and run this just to see the result。

 So this is a car that we're going to test it with。 And that's what our output result is。

 We'd like to be able to get the same value through the web application。

 And the web application We'll start it from the command prompt in a moment。

 But this is this is what it looks like。 So here is。😊，The expected values。

 That's that little map that we generated back in the source code。 And notice here is the route。

 We're not putting this at the root Later on when we create a full blown web application and not just an API endpoint。

 we're gonna have several of these endpoints。 Some will be Gi。 Some will be the backend API。

 This is calculate miles per gallon。 So what we now need to do is we deal with Json。

 Json is essentially jascript object notation。 What is really cool about Python is Python uses nearly the same syntax is Json。

 This is essentially Json up here。 The only thing you have to be careful with in Json。

 you can't put single tick marks in there JSson requires that to be quote。

 so you can create maps and lists essentially jascript object notation in Python that's not valid Json。

 if you use the single tick we load the model Never train your model here。 It might take too long。

 I mean you don't want to retrain the model Every time your web application boots up For one thing neural networks or stochastic。

 You might get a different result each time。 that drives your customer。Czy。

 If every Why am I getting a different miles per gallon。 Oh， yeah， we must have rebooted the server。

 No， don't do that。 Trust me， I worked for the life insurance industry。

 Our clients would not be happy with that answer。 Now。

 when we get a request in on API miles per gallon， I usually put all my endpoints under API and we're only accepting posts。

 I harvest this Json from it。 I'm going keep a list of the errors that I have。

 hopefully that will remain an empty list。 But now I'm going to go through this expected map that I built up here。

 And I'm going to one by one， make sure that nothing is out of range。

 I'm also going to look for unexpected fields error， and if one is missing， I also track that too。

 trust me on this one。 When you deploy these applications when you're working as a data scientist or AI engineer。

 especially if you're in a global company， you'll have requests coming in at all hours。

 and you will have I T professionals， who are not as versed in data science or machine learning as you receiving requests。

 If your program just blows up because some clients sent in。

Bad number they'll call you or they'll call somebody on your team。

 Good error messages are the best antidote against late night pager calls and cell phone calls。

 believeve me， I've gotten many of them in my career。

 if the person who is handling production support that night sees a ray out of bounds in line 30 Python blew up。

 they're going to essentially call you if this is one of these I people that does not like Python thinks no Js rules the world'll be extra snarky So you'll get the call and you'll have to go and debug it。

 Now on the other hand， if your program produces this nice error that says undefined field。

 b bla blah they can go look at the Json message coming in and they can deal with it The person who is on 24 error support can deal it and believe me that's a good thing often they're in the time zone that matches what that client was So unless unless you want errors propagating that look unprofessional So Python hard errors try to always guard against that so that you're checking for that good production practice。

 I check to see how many errors I have and if。There are errors。

 Then what I'm going to do is return them as another Json message。

 So you always want to put some sort of ID here。 I'm just putting a grid。

 we'll see what that looks like in a moment， but every transaction needs to have a globally unique I at least I think it's a good idea and here all we're doing is I create a very simple nuy array 1 row 7 columns there's seven inputs to this。

 This is essentially instead of having a CSv file， We're literally creating this on the fly and I put in all those values。

 So it's row 0 because there's only one row， and all those columns。

 I just know that that's the order that I trained them in and this corresponds to that last example that we ran back in the Jupiter notebook。

 I fill all these values in I call model predict。 I extract the miles per gallon and I form my response。

 which is going to be the I and notice this is almost json。

 This is Python object notation which is very similar to jascript object notation。

 This all comes in and you will send that result back to the user or you're going to send this。

 Now it won't。And user seeing this。 It's going to be some other machine calling this。

 And it probably gets promptly put onto a web application。 This is essentially software as a service。

 So now let's， let's get that running， and let's try to call it。 Now。

 that's my Jupiter notebook terminal。 We'll let that remain running。 I'm opening another one。

 and let's make it bigger。 We've got plenty of screen space。

 All the Python scripts are in a directory called Py in my class。

 And we're going to run the MPG server。 These other servers will run as we progress in the class。

 and this is running。 You might get some firewall errors like this。 Windows does similar。

 I'm on a Mac。😊，So this is up and running。 So let's hit this with Postman。 Now。

 Postman is a great little tool。 I give you a screenshot that basically shows what you want to be sending it。

 So let's go ahead and change this to API MPG。 You can follow the screenshot that I have in the notebook to set this up correctly。

 I am going to move over here to body。 Now I had this previously set up for an image。

 So let's go ahead and set that to raw。Change that to Json。 We'll go back to here。

 This is what we want to send it。 This is literally what goes across the wire。

 We put that in and then click send and notice miles per gallon is 23 for this particular car。

 We could make this a four cylinder car and see what that does。 It's going to change。

We could do something bad， like drop weight out of there completely。

And you'll get one of those errors。Missing value weight。 Always give descriptive errors。

 Don't give Microsoft errors where it's just a stream of numbers。 All right， now。

 neural networks are all about images。 So I've got to show you how to do one of these as an image。

 So let's go back to the notebook。 And I'm going to also show you how you can do one of these purely from Python。

 So we're going to use the requests object that lets us do HP。

 notice this is just like what I did in postman。 So now we're going to do a programmatically outside of postman。

 Now I could do endless。 I could show you how to do this in Ph P。

 I could show you how to do this in Json all different languages。 Well， assuming I know the language。

 But let's just run it and you see the result comes back here 23 miles per gallon。 just like before。

 there's that unique identifier that I was telling you about。 So now let's do this as an image。

 Iage is a little bit trickier， but not much。 It's all sort of the same thing。

 We're going to use the image server。 and we're going to literally post the image across H TDP。

 so that we're。😊，Receiving it on the website。 So on the website。

 I do put in this piece here where these are the only valid formats it takes。 Really。

 I could probably even make that smaller。 I mean， really P G Jpeg and Jpeg and G。 uses gs anymore。

 Some people and I put in the image with in height。

 Now we're training this neural network back in the Jupyter notebook。 This is mobilenet。

 So we used mobilenet。 This is a pretrained neural network that we talked about before。

 it's a very common one just Google mobilenet there's all about it。

 and it recognizes 10 different images。 and what I do here is basically I bring up mobile net。

 I'm actually not loading a saved neural network。 This is inside of Kis actually So this that's why we don't have to train this network。

 It's transfer learning。 It's already there for us。 The route is going to be API image。

 We're going to check to make sure that an image was actually posted。 if not we have an error。

 This is a multipart upload。 So if you've ever done HtTP program。

Web programming anytime you upload a file to a web application that's called multipart。

 that's the method that it's doing。 We use exactly the same thing。

 We make sure that it's one of the accepted file formats。

 This is how we make sure that the name matches what we consider a secure name You can see how a few things commented out and if you log entries that was just when I was debugging things We essentially this part here is pretty important。

 This is how I'm bridging from the multipart upload into a nuy buffer that the neural network can actually take。

 and then we resize it to the right size clipping for antialliasing。

 this also assumes that these images don't have alpha channels。

 if you upload an alpha channel and it'll have an issue。

 I'll show you how to take care of that later。 we do any preprocessing and then we predict and we decode the predictions。

 We're going to get the first item out of there。 the first name and we're going to return a Json that has all of the probabilities that we expected returning that is。

In the Json， you' see you'll see the message in a moment and then we return the response。

 So let's get this guy running。 I'm going to break out of MPG server。

 and I am going to run image server。 same sort of thing as the MPG server。

 Always say yes to the firewall。 unless it's a virus asking you， then say no。

 problem is hard to know。So let's go ahead。 I'm going to change this to API image。

 We're going to use form data。 It's already here from when I was testing it。

 and essentially I'm using a picture of my dogg from the class page that you have here at JP he's in the image directory and I am going to go ahead and run that make sure that you specify that as a file that does a multipart upload we'll click send and there's that pre that I showed you before it thinks he's a boxer。

 he's an English bulldog。 It's not my neural network blame the creators of mobilenet。

 although boxer is bulldogs， he's not any of these， he's definitely not a French bulldog。

 he takes great offense to being confused for the smaller French Bulldogs He's a broed English Bulldog All right and he's definitely not a gigantic bull messsteef So that is how you basically do that。

 You can also send this image request with Python with any programming language really like I said this is the relatively。

Poull command to do that you're going to post it to images This is the key part right here that's how you pop a JpeEg over Python and send it in it is named image that's critical because that is the label that my program is expecting on the receiving side so let's go ahead and run that and same sort of thing So anyway this is your introduction into APIs and we'll see how to hook those APIs up into other things and also how to put them into the cloud for high scalability This content changes often so subscribe to the channel to stay up to date on this course and other topics and artificial intelligence。



![](img/5296890b8c9d0dcc242ead17d46b9fee_3.png)