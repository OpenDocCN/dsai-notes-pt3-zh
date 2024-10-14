# 【双语字幕+资料下载】Python 3全系列基础教程，全程代码演示&讲解！10小时视频42节，保证你能掌握Python！快来一起跟着视频敲代码~＜快速入门系列＞ - P30：30）类介绍 - ShowMeAI - BV1yg411c7Nw

![](img/8f475afeed4834135683e6ace5e6dd24_0.png)

Welcome back everyone， my name is Brian， we're going to continue our journey into Python3。 we've been saying for 30 some odd videos now that we're going to talk about classes and well。 today is the day we're going to start talking about classes。Before we dive too deep。 we've got some fundamental concepts we need to cover。 First and foremost。

 you've heard of OOP or object oriented programming。 This is the cornerstone to that。 Basically a class is a blueprint or creating objects。 You'll hear people say classes and objects interchangeably and there two different things。 A class is a blueprint or a plan。On how an object should be created。

The object is when Python or another language actually creates the object or the instance of that class。From the blueprint that we're going to make。Classes are also a big， big topic。Way bigger than we can cover in the single video。 so we're going to split this up into multiple videos。 Let's dive in and take a look。

![](img/8f475afeed4834135683e6ace5e6dd24_2.png)

All right， classes can get very， very complex， we're going to create a simple class。![](img/8f475afeed4834135683e6ace5e6dd24_4.png)

So I'm going to just paste comment， create a class。We're going to do this in a separate file。 but you can do it in all in one file as you're going to see in future videos but I just want to show you kind of the real world approach to how people do this So I'm going to make a new file。

 We're going to call this file cat。 Py because we're going to make our own cat class here。I'm going to paste in some notes。The cat class。Self is the first parameter。 I want to put that right there， because people often forget this。 If you're from another language。 it is equal to the this in another language。 And what are we talking about here。

This is why people get。Class an object Confuse。 The class is a blue print or how the object will be created。 Once the object is created， it becomes an instance。 So I'm going to put that。If we're in an instance， because you can to have multiple instances。 as you're going to see in this video， we'll make multiple cats and you want to refer to the current instance you need to this or in Python self。

So， people often think that self。And class are the same thing， and they're not。 They're two different things。Whenever hear class， it's the blueprint。 So let's make the blueprint。对。That's it。 It's really that simple。 Now we're going to have to add some attributes here。 So I must say name equals。Just blank。And it's go ahead and say age equals。

 And everybody kind of has their own way of doing this。 This is simply how I do it。 Feel free to adopt your own style or your own company standard。 whatever you're working with here。 But this is how I do it。 I want to know the variables。 And whenever you see a class and you see this indentation， think scope。

 So these exist inside of the cat scope。 In each instance of these will have independent variables that are not shared。 Although you can show them， we'll talk about that in another video。I know you're probably sick of hearing me say， we'll talk about that in another video。 but there's a lot to coding。 so can't cover it all in one。So now we're going to say de in knit。 Now。

 remember， the double underscore means it's something baked into Python。This is the constructor。And what I mean by constructor is。This is called when we make an instance of this class so we can execute code。 think of this like the main function for a class here。As soon as Python creates an instance of CA。 we will run this function automatically， you can feel free to。Omit this。

 and that's called the default constructor where you just simply don't have one。Or you can actually define it yourself。 Now， remember， I said。Self is the first per。 so we need to say self。It is the first parameter we need to have。 is it reference to the current object。Now I'm going to just paste in some notes here。Basically。

 just stating the obvious self is required， other parameters are optional。And let's go ahead and fill this out because we want to reference the current object or to say self dot。Name equals the name parameter。And then from here， it just simply becomes a lesson in copy and pace because we want to do the rest of these。So we're just simply initializing these variables。It's going to copy and paste these out。

 maybe there we go。So we're saying the self name， this guy is equal to the parameter or actually the argument name。Age， age， color， color becomes pretty self explanatory。Now I'm going to print out something just so we know it was constructed。And I'm just going to say the constructor for self name。And from here， it's actually fairly simple。

 We can just define any real code or functions that we want， for example， we can say。Deaf Neow。And if you do this， you're going to get really confused when nothing works。 Remember。 you have to have self as the first parameter there。Otherwise。 you're just simply going to have a bad time。 Nothing's going to work right。

 Indentation may drive you crazy。 Remember， you just want to line up with your current scope。 So class scope， function scope， so on and so on。And then， I'm just going to say。Print F。Let's go ahead and say。Self name and meow。 And I'm going to speed this up just a little bit because we've covered functions before。 But the main takeaway here is you have a blueprint and you can define what this object once it's created。

 is done。 Now notice how I've just intermixed those。 We're defining a blueprint。 but we're also defining the behavior of the object once it's created。This is why people get things so horribly confused。Go ahead。Make a sleep function。And let's just go a little crazy here。 Let's go ahead and say。Hungry， and。Get rid of this。

Or X in range。 I don't want to do anything too drastic。 Just 5。 then we're going to say self dot miow。 So when we say self。 remember。 we're taking the current instance of this blueprint， whatever's running a memory。 And we're going to call this function。 So if you have two cats， we're taking one of them and say。

 make that cat now Miow， and we're going to call this function over here。So it becomes very simple how you can work in your own class。Now， from here， I'm just going to say。Go ahead and。Add a couple more just to show that you can do some stuff here。And I want to add just one more。We're going to say description。

 and here I want to print some stuff out， so。We're going to print out the color out because I want to know what color this cat is。Is a say is a opera English here？So we're saying the name is a color。At。妈妈，Who is。Years old。Pretty simple little function， but basically what we're trying to demonstrate here is you can do pretty much anything you want。 you can have functions call functions， you can do hardcore math。

 you can actually create instances of other classes， do pretty much anything you want。 but now we have fully defined a blueprint for a cat。And this cat will have a constructor where we're setting the variables and it will meow sleep。 be hungry and meow a lot of times because that's what cats do， and we can make it eat。

 and we can get a description of that cat。So far， our class doesn't do anything。 It's because we haven't created an instance of this yet。 Remember the class is just a blueprint。 Now we've got to actually create an object that we can work with or an instance。 So let's flip back to our file here。 First thing we need to do is import it so we can actually work with it。

Now we have to import this because it's in another file if it was in the same file。 we wouldn't have to import， but let's go ahead and go。Import。At。And now we can just work with that directly， or if we really wanted to。 we could say something like this from。At。Import， and then we can import the cat class。

 So now what we can say is from the cat file， importm this block of code。 And when we go in here。 it is the cat class。 So if you had multiple classes in here， it would only import cat。 whereas import cat would import everything in that file。![](img/8f475afeed4834135683e6ace5e6dd24_6.png)

So that's why you're going to see those two out in the wild there。![](img/8f475afeed4834135683e6ace5e6dd24_8.png)

Now the important part， let's go ahead and use the class。 Now， when I say use a class。 what we're really doing is we're going to create instances of that class。 I want to make a function called test。Now you may be wondering why don't we have a self here。 you've been saying self over and over again because we're not in a class。

 we don't have a current object。So there's no current object or no current instance。 We're running right on the global scope。 We simply don't need it。 And if we try to use it。 really all we're doing is creating a parameter that we'll have to give some object to that doesn't exist。 so would make no sense。So if that sounded confusing。

 it's because it makes no sense to put self there。So we're going to say B equals cat。 Now。 you notice from other languages， you would have to put like new。 You don't have to do that with Python。 It does it automatically。 You do need the brackets， so。Now we need to give it a name。An age。And give a color。If you're wondering how I got those。

 it's because we define this in our file in our constructor， it needs a name。Age and color。 Not we did not call self because Python does this automatically。 What is' happening under the hood is it saying， make an instance of the cat class and then invisibly。It's putting self right there。Or X， that instance of that class。 We don't have to do it。

 Python does it for us。 That's one of the hidden little gotchas。 You may look at the sink of。 where is self coming from， Python does it for you。All right。 so we've got this cat。Let's make another cat here。And let's call this。Beello， this was one of my cats。 He was a really great cat。 I miss him so much。And he was a black cat。

 A lot of people don't like black cats。 They think they're bad luck。 But this is like the best cat I've ever， ever had in my life。 So we've got two instances B and C。 and they are two different things。Let's go ahead and print out。Description for B。And the description for C。And we could take this out just a little bit further if we wanted to。

 we can say see Miow。And if you're wondering， yes， you could give it a more complex variable name。 you could actually call it kit cat or Deer or whatever you wanted。Let's go ahead and call the sleep。C is going to be hungry。As the cat was always hungry。And then we're going to say， you know what。 bees， not hungry bees going to eat。And if。Name。EqualsAnd we've done this before in another tutorial。

 but just in case。We're checking to see if Python is running this。Directly， and if it is。 we want to run some code。 Now， I've said this is the main function。 We don't actually have to have a function called main。 What we can do is， well， anything we want。 And this is kind of the beautiful thing about Python。 I'm going to say X。At。

And we're going to give it a name of test， notice how age and color already have a default value。 and so we don't have to have them， but we do have to have a name。We covered all that in our functions video。I going to go ahead and print out。X。I'm not going to call this test function just yet， I want to show you something O。

Name E White is not fine。 What did we screw up here。Let's go in here。 We are on Cat do Py line 7。Well。Interesting。Name white is not defined。Aim white is not defined。What do you think is going on here， So we have line 12。color white， that's what we're missing here。I was handing at some type of object that didn't exist。So if you ever run into that is not defined。

 kind of a little bit of explanation on the fly， that's why we simply， instead of a string。We were trying to hand it an object simple enough fix。 But for a moment。 just kind of threw me for the loop。All right， now let's clear this out and run this again。There we go。 So you're going to see this and you're going to think you have an error。

 But really what's going on here is it's telling us。Underscore cat name of the file。Dot。Hat so we can actually go in here， go in here and we can see exactly what it's doing and then object。 So now we have an object we're working with object oriented programming or an instance of that object。And it is located at this。 Now， this looks really confusing at this。

This is actually a memory location。 So if you're coming from a language like C or C++ something that actually where you play around with the memory directly。 this is the memory location。That is really cool。 so now we can know what's going on here。Let's flip back here， and let's actually just。Brenent out。He and right。There we go。Let's clear this and let's call our test function as well。 And let's see this whole thing in action。

So， now we know。Our horrible boofup in our code here is fixed。 We know that class works。 and we can start making more instances of it。So popquiz。 how many instances of this class are we creating？Soid three， you're correct。1。2 and3。Let's go ahead and run this， see it in action。All right， so scroll all the way up。 Actually。

 I'm just going to bring this whole thing up here。So we have。Cat， cat object at this location。And then you see the constructors firing off for kittca and Othello。 So the constructor's called。 even though we don't call it， it's called automatically。 Think of that like the main function for a class。And if you're confused about what that is。

Wick recap， it's a deaf underscore in it。 That is our constructor。Plipping back to the output here。 you can see now we have a cat object at this location and a cat object at that location and you don't have to memorize these numbers。 but if you just kind of look at the last few characters here you can see they're in different locations that's how you know they're different objects。Because Python has created three different objects at three different memory locations。

And we can treat them independently。 Kit cat is a tabby cat whos1 years old or fellow is a black cat who is six years old。 This is the cornerstone of object oriented programming。 and then we can work with those objects directly and do pretty much anything we want。So。Major takeaways from this video。We are covering object oriented programming and we're talking about classes。

 which are the blueprints for objects。![](img/8f475afeed4834135683e6ace5e6dd24_10.png)

![](img/8f475afeed4834135683e6ace5e6dd24_11.png)