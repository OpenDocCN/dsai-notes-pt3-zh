# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P4：L1.3- Python 列表、字典、集合和 JSON - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton， welcome to applications of Deep neural Networks with Washington University in this video we're going to look deeper into the Python programming language and see how to use lists and dictionaries。

This allows complex data structures to be created in the Python programming language。

 and it very much mirrors JO you can literally。Iulate the JsonN syntax right in Python code。

 much like you can do in jascript to build these complex structures for the latest on my AI course and projects。

 click subscribe and the bell next to it to be notified of every new video in this part。

 we're going to take a look at Python list dictionary sets and Json So if you've already worked with these topics。

 you can safely skip this section and continue onward。 Like most programming languages。

 Python does have a notion of array list dictionaries and sets What's neat about the way that Python does this。



![](img/be2c33329570c5649cb2ad3542a9f55f_1.png)

Which is pretty similar to the way that JavaScript does this。

Is the code that makes up these lists is。Often valid JSson inside a Python if you write it correctly。

 it'll always be valid JSON So what we'll see here is in Python we can have a list of values。

This is an array。 This is a predefined array。 We have strings in here， single quote， single quote。

 and we can print these out when you print out a list in Python。It usually looks like this。

 You'll have a。Open brace， close brace， and then whatever is inside of it there。Some lists。

 if you're using lumpumpy lists。 what will should we get into later。

 that will look a little more complex down there， but it'll still be basically the same thing。

 You have a number of values in there in a lot of programming languages。

 rays are of a fixed size in Python， they're not。 you can add to them。 So C do aend。Yi。

Is going to put something else into the list after the list was created。

 so that's that's kind of handy。 you can iterate over a list。

 This is a four each like they have in many programming languages。

 So this is going to loop over every value that is an S and print them out。

So there you have the the values that were in that collection or list。

 Another thing that Python has that is that is kind of handy is it will let you keep track of what value you're at in the list if you wanted to keep track of the index。

 you'd have to do something like this index equals0。Print， you'd print out the S that you have。

 and then maybe the index that it's at。And then you'd have to remember to increment that each time。

And now you could keep track of where you were in the list。

 otherwise you have no notion of where you're at in the list。

 each of these iterations of the list is。Is exactly the same in terms of knowing actually where you're at。

So we'll leave that like it is there， but here we can use something called enumeration that keeps you from having to have that other value。

So now we're looping over i comma C， I is going to be your index and C is going to be the value。

At that particular index， so now you know where you're at in this。

 this would be useful because maybe you would want to modify the collection at that particular value。

And change it to something else， We're not going to do that。

 but that is where this might be useful or if just you wanted to print numbers to go along along with these Now everything in Python is zero based lists and indexes start at zero you can also define your list by adding values to it by app to them and we add these in this this value。

 this is not typo there are meant to be two Cs， because that shows you that a list which always has the square brackets。

 can have more than one value。More than one item that has exactly the same value。

If you use something called a set， and this is very useful。

 you can use a set to eliminate duplicates。As you add these in。

 that second C doesn't get added because it says， hey， I've already got one of those。To define a set。

 you just do see equal set and then close on parentheses。 Now。

 you'll notice it does have the curly braces when it prints out。 So it's somewhat like a dictionary。

 Now， lists can have values added and removed。So here we have ABC。

 we insert A0 now notice we're inserting it at location zero， so it goes at the beginning。

 then we print it， we see that it popped into the beginning。

 then we're going to remove from C the value of B， so the collection to C we can also remove at an index so if you want to remove0 the first one that's the way that you do that。

So this is how you can very dynamically add and remove values to arrays as you go It's not like some programming languages where you define a fixed length or the array and that's it。

 Now this is kind of the neat part of this。 You can define dictionaries and hash tables and create fairly complicated。

Structures。So here I am creating a this is basically name value pairs and this is essentially dictionaries and hash tables by themselves。

 dictionaries， maps， hash tables， those names all mean very similar。

Things and are essentially interchangeable。For the most part。Here I am creating a dictionary。

 a dictionary a book， you look up a word and you find a definition。

 this is pretty much what it does here， so name is Jeff address is 123 main if I print out D so when I run this。

 first thing you're going to see is just the dictionary printed out。If I print out。

 this is how you make it look it up if I print out name。And square braces， it'll find Jeff。

And print out Jeff。This is how you check to see if something is in the dictionary or not now if you try to access something that's not in the dictionary like if I tried to print out name too。

 it's going to give an error， so you want to check for that so if name is indeed name is defined which it is age is not defined。

So be aware of that as you use dictionaries， this is a very common feature of Python that we will definitely use throughout this course You can also access the individual keys and values in this So if you run this one。

It's going to say the keys are name and address， and now notice it says that this is a dictionary keys。

 this is basically a list， you can treat it like a list or you can convert it into a list easy enough just by passing it to a list。

Values， these are the values。 So you use the keys function and the values function to gain access to the entirety of what is in a dictionary。

 You can also。Combine them， so here this is very common， you'll see a list。

And then each of these maps in here or dictionaries is essentially a record。

So it's saying in the first record， the person's name or the names， my wife and I。

 Jeff and Tracy Heaton， we have three pets， two birds and a dog named Hickory。And the pets。

 since we have multiple pets， you have to put a list in there。If it was just Winton。

 we could have just did colon and Winton so long as you define the format to be in that way。

John Smith here has one pet called Rover， since we define the format to be a list。

 we expect a list and even though he just has Rover， presumably a dog。We don't。

Need to really have the list， but it makes it convenient because we can then expect everything to be a list consistency is always a good thing。

John Doe has no pets， so I don't know what his problem is。

This is then the complete list of customers。 We can print this out。

 or we can iterate over it for each。 So this prints out the whole thing just dumps the whole thing to your to your screen or here we can loop through them。

 and maybe you could handle each one， you could count the number of pets that each person had。

 And by the way， this is kind of handy2 customer do get。 So if you do get instead of just the。

The braces。Then you can provide a default。 So the default here is no pets。

 So if there were no pets for this person， which is the case for。For J Doe。It'll simply say no pets。

 and by the way， this is where this code starts to look very much like Json。Between here。

 how you end up with code not being Json is Json requires。Quotes here if you were to change this to。

That now you're no longer valid JSO more advanced lists， this is kind to neat。

 you can zip two lists together， so here we have 1，2，3，4，5，5，432，1 for B。

 and we're going to print out the zip of A and B。 it's going to connect those two together。

Now that just gives you an object to actually see it。You do this。These are tuples。

Tups and lists are pretty similar in Python， we really won't get into the differences of what those are。

For the study of neural networks but。You can see that the first one is here， one，2，3，4，5， and then 5。

4，3，21 is the other one， so this is now created。A series of tuples together。In the list。

 so you have a list that contains the topples and then the topples are the union of those two lists。

Or the connection。Of those two lists。And you can also use it like this。

 So now you are using the X and Y。That are coming out of each of those。

 We already saw the enumeration， but that's basically just so you can track。

Which one is at each value。 So you know that one is at location zero and so on。

 This can be useful to do things like that where you want to print out what each index holds This is a comprehension in Python。

We'll use those some。🤢，Basically， what this is doing is it builds up a list on the fly for you。

 so this is saying for all the x's in 10， and whatever you put here， if you just put X here。

 it would just duplicate the list。But since it's 10。

 this creates a second list where every value is multiplied by 10。

 This is a very handy way to build up lists on the fly。

 You can also build up a dictionary on the fly。 I use this a lot when I'm dealing with CSV files。

 So when you deal with CSV files， you'll get a list of their headers。😊，So you might have column zero。

 column one， column two and column three， you might want a lookup table so that you could look up the text of call2 now this could be something like a dress or whatever。

You could pass that string in and then if it ever changes position， it'll move to the right index。

You create this lookup value。And the lookup dictionary says that column zero is zero， column1 is one。

 column 2 is two。 Now if you add something into here。Like， I don't know， just that。

Then now it's going to track those。 So column 3 got shoved over。 So it's still4。

 This is how you make your code not break when you have。Changes made to your code。

So this is very handy because now you can look up the index of that column and find out that it is。

 in fact too。 Thank you for watching this video In the next video。

 we're going to look at how to make use of files， both image and text as you import data for your deep neural networks。

 This content changes often。 so subscribe to the channel to stay up to date on this course and other topics in artificial intelligence。

😊。

![](img/be2c33329570c5649cb2ad3542a9f55f_3.png)