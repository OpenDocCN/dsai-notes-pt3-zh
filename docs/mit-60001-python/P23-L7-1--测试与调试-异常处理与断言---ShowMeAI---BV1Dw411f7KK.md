# P23：L7.1- 测试与调试、异常处理与断言 - ShowMeAI - BV1Dw411f7KK

![](img/b5da9e0adfa2d119ba2532092d29ebda_0.png)

The following content is，Commons license。Your support will help，continue to offer high quality。

To make a donation， or，from hundreds of MIT courses，at ocw。mit。edu。



![](img/b5da9e0adfa2d119ba2532092d29ebda_2.png)

![](img/b5da9e0adfa2d119ba2532092d29ebda_3.png)

PROFESSOR： All right， everyone。Good afternoon。Let's get started。



![](img/b5da9e0adfa2d119ba2532092d29ebda_5.png)

So today's lecture will be on，exceptions and assertions。



![](img/b5da9e0adfa2d119ba2532092d29ebda_7.png)

So before we begin， let's start，back to real life for a second。



![](img/b5da9e0adfa2d119ba2532092d29ebda_9.png)

So I've made soup before。Perhaps you've made soup before。



![](img/b5da9e0adfa2d119ba2532092d29ebda_11.png)

Let's say you're making，And it turns out that bugs，from the ceiling。Quick question to the audience。



![](img/b5da9e0adfa2d119ba2532092d29ebda_13.png)

What do you do if you，AUDIENCE： [INTERPOSING VOICES]。



![](img/b5da9e0adfa2d119ba2532092d29ebda_15.png)

PROFESSOR： All right。One one at a time。

![](img/b5da9e0adfa2d119ba2532092d29ebda_17.png)

Anyone have any idea？AUDIENCE： Eat it。PROFESSOR： Eat it。You want to eat it Anyway OK。

We're going for an analogy，I don't know what you'd do，I guess you just release，and they'd complain。

 but。OK。What else？AUDIENCE： [INAUDIBLE]，PROFESSOR： Cover the soup。That's a good suggestion。

So you can cover the，Sometimes you'd have to，right， to check to，To taste it， add things。

So bugs might fall，But covering the，AUDIENCE： Debug it。PROFESSOR： Debug it。I wish I had something。

That's a good answer。Yeah。AUDIENCE： Take all the，so there's no-- nothing，PROFESSOR： So take all。

so there's nothing，That's sort of the，like doing a mass cleaning，That's a good。

That's sort of eliminating，AUDIENCE： Decide，and declare it a feature。PROFESSOR： Decide。

and declare it a feature。That's probably what a lot，Cool。So I wish computer debugging。

So what did we decide？Well we could check，Keep the lid closed， that，And cleaning your kitchen。

The equivalent of，was to just throw，I would take a mop，but yeah， that works too。So we can draw some。

with computer programming。So checking the soup is really，You have a soup you，Test it。

Make sure there's no bugs。Continue on。Keeping the lid closed。It's sort of this idea。

So make sure that bugs don't，Sometimes you have。

![](img/b5da9e0adfa2d119ba2532092d29ebda_19.png)

to make sure that the soup，So that's equivalent to，So try not to have bugs。

but they might show up anyway。Cleaning the kitchen is，of the bugs in the first place。

This is actually really，But you can still try to do it。OK。So let's talk a little。



![](img/b5da9e0adfa2d119ba2532092d29ebda_21.png)

so far in 60001 600。So you expect， really，you maybe do a little debugging，and it's perfect。Right？

You just nailed it。But in reality you write this，and you go to run，Right？

It's happened to me many times。It's happened to you many times。



![](img/b5da9e0adfa2d119ba2532092d29ebda_23.png)

That's the reality。OK。So today's lecture will go，and debugging and how you can，when you're writing。

like this little girl here。Disappointed beyond belief。All right。So at the heart of。

starting with a defensive，OK。And this comes back to，and abstraction that we talked。

did the lecture on functions。Right？So try to start out with two。



![](img/b5da9e0adfa2d119ba2532092d29ebda_25.png)

If you write your code，documenting each，you're more likely to understand，later on and you'll be。

it a lot easier。Speaking of testing，once you've written a，you still have to test it。

And the process of，coming up with inputs。Figuring out what，And then running your program。

Does the output that the program，If it does， great， you're done。But if it doesn't， you have。



![](img/b5da9e0adfa2d119ba2532092d29ebda_27.png)

And the debugging step，And it's really just figuring，or why the program didn't。



![](img/b5da9e0adfa2d119ba2532092d29ebda_29.png)

expected it to give。So as I mentioned， the，is to do defensive，you want to set yourself up。

Which really comes，that the code you，So write as many，Document what the functions do。

Document their constraints。And it'll make your life a，when you have to debug it。When do you want。

Well first you have to make，So eliminate syntax errors，which， by the way， Python。

Once you've ensured that，then you want to come，So this is pairs，for what you expect。

Once you have your test cases，you can start doing tests。So there's three general classes。

The first is called。

![](img/b5da9e0adfa2d119ba2532092d29ebda_31.png)

And if you've written functions，makes sure that， for example，to the specifications。

So you do this multiple times。As you're testing each，At that point， you do，Come up with a test case。

And run all of the different，to make sure that，you don't re-introduce new bugs。



![](img/b5da9e0adfa2d119ba2532092d29ebda_33.png)

had already run。So you do this a bunch of times。You do a little bit，a little bit of regression。

At some point， you're ready，Which means， test your，Does the overall program work？So this is the。

all of the individual，And integration testing，that the interactions between，works as expected。

If it does， great， you're done。

![](img/b5da9e0adfa2d119ba2532092d29ebda_35.png)

But if it doesn't，to go back to unit testing， and，So it's really a。



![](img/b5da9e0adfa2d119ba2532092d29ebda_37.png)

So what are some，The first， and this is probably。

![](img/b5da9e0adfa2d119ba2532092d29ebda_39.png)

that involve numbers，some natural boundaries for，sorry。So for example， if I have，and it compares if。

then some natural boundary，is if x is less than，x is equal to y。Maybe throw in less than，or equal to。

 and so on。

![](img/b5da9e0adfa2d119ba2532092d29ebda_41.png)

So that's just sort of an，It's possible you have some，are no natural partitions。In which case。

 you might，and then the more，do， the greater the likelihood，But there's actually two more。

And one is black box，is glass box testing。

![](img/b5da9e0adfa2d119ba2532092d29ebda_43.png)

In black box testing，you have the specifications，So that's the docstring。All you're looking at is。

up with some test，In glass box testing，itself and you're，with some test cases that hit。



![](img/b5da9e0adfa2d119ba2532092d29ebda_45.png)

through the code。Let's look at an example。

![](img/b5da9e0adfa2d119ba2532092d29ebda_47.png)

I'm finding the square root of，given by this epsilon。And the idea here，give you how this。

The idea is that you're，based on the specification。



![](img/b5da9e0adfa2d119ba2532092d29ebda_49.png)

And the great thing，is that whoever implements。

![](img/b5da9e0adfa2d119ba2532092d29ebda_51.png)

in whatever way they wish， they，that can use bisection。



![](img/b5da9e0adfa2d119ba2532092d29ebda_53.png)

The test cases that you come，are going to be，No matter what the。



![](img/b5da9e0adfa2d119ba2532092d29ebda_55.png)

So for this particular，We check the boundary，we can check some number。



![](img/b5da9e0adfa2d119ba2532092d29ebda_57.png)

we can check maybe irrationals，So when either epsilon is，is really small， or x is really。

and all the possible。

![](img/b5da9e0adfa2d119ba2532092d29ebda_59.png)

So the important thing，is that you are doing you are，on the specifications only。Glass box testing。

 you're，to guide your test cases。

![](img/b5da9e0adfa2d119ba2532092d29ebda_61.png)

So if you have a piece，with a test case that goes，combination of input-- of，through the code。

 then that test，The problem with this is，for example。Every single possible。

is maybe the code not going，going through once，going through three times， four，Right？

Which could be a。

![](img/b5da9e0adfa2d119ba2532092d29ebda_63.png)

So instead there are，for when you're dealing with，So for branches， when you're，it's important-- you。

all of the parts，So make sure you，goes through each part，For for loops， make sure。

the loop is not entered at all，time， and when the loop is，than once。For while loops。

except that make sure，cover all of the possible ways，So if the while loop condition。

there's a break inside，So in this example， we have，This is its specification and。

that someone decided to，So a path complete，that you want to，goes through each one。

So if x is less than，is less than minus 1。So that's good。And otherwise， which means pick，So 2。

So 2 and minus 2，Yield path complete-- yields，But notice that while we've，through this code， we've。



![](img/b5da9e0adfa2d119ba2532092d29ebda_65.png)

Minus 1。So this code incorrectly，as returning minus，So for glass box，making sure you're going。



![](img/b5da9e0adfa2d119ba2532092d29ebda_67.png)

through the code，sure you hit upon any，So in this case， for，is a boundary condition。



![](img/b5da9e0adfa2d119ba2532092d29ebda_69.png)

So you've created a test suite，chances are you found a bug。What do you do now？All right。

Quick sort of detour into。

![](img/b5da9e0adfa2d119ba2532092d29ebda_71.png)

The history of debugging。So 1947， this，And it was a computer that was。



![](img/b5da9e0adfa2d119ba2532092d29ebda_73.png)

It could do things like，Things like multiplication，And take the log of，So faster than a。

But pretty slow for，And a group of，on running a，that was supposed to find。

And among them being this-- one，Grace Hopper。And they found that，working correctly。

So they went through all of the，in the computer， and，in panel F relay 70， where。

Just sitting in there。I think it was dead，But it was a moth that was。

And I don't know if you can read，They made a note，that says， first actual。

Which I think is really cute。So they were literally doing，Right。So you won't be doing。

You'll be doing a virtual kind，Which， again， is not that fun。But you still have to do it。

So debugging， as you might have，sets， has a bit of a，And obviously your goal is。

and in order to achieve that，There are some tools which，There are some tools。

or whatever ID you've been，I know some of you have been，is awesome。The print statement can also。

But over above，really important to，as you're trying to，I want to talk a little。

and how you can use them，Python tutor， if you，you might not be able to use it。If you don't know how。

you don't need to learn。But print statements，and you can always put，And they're really good。

So good places to。

![](img/b5da9e0adfa2d119ba2532092d29ebda_75.png)

are inside functions。Inside loops， for example，what are the loop values，functions return what values。

So you can make sure that，the correct values，between parts of your code。I will mention that you。

method when you're debugging。Which is interesting。So if you take a，find approximately the。

Print out what values you--，All of the possible--，values at that，If everything is。

to be at that point in your，That means the code，That means that-- however， that，has a bug， right？

So since you've put a print，and you think that，then put a print statement，And see if the values are。

And if they are， great。Then put a print，So in this way you could，to pinpoint a line， or a set。

that that's giving，So the general debugging steps。

![](img/b5da9e0adfa2d119ba2532092d29ebda_77.png)

Don't ask what is wrong，part of the testing。So your test cases would have，The debugging process。

how the result took place。And since programming is--，is， sort of， is a science， you，as well。

So look at all the data，Figure out a hypothesis。Maybe say， oh， maybe I'm。



![](img/b5da9e0adfa2d119ba2532092d29ebda_79.png)

in lists， for example。Come up with an experiment，And then pick a，you can test your。

So as you're debugging， you。

![](img/b5da9e0adfa2d119ba2532092d29ebda_81.png)

And these error，pretty easy to figure out。And they're really easy，So for example， accessing things。

give you index errors。Trying to convert， in this，gives you type errors。Accessing variables that。

gives you name errors。And so on and so on。And syntax errors are，if you forget a parentheses。



![](img/b5da9e0adfa2d119ba2532092d29ebda_83.png)

or something like that。So error messages are，The Python interpreter，and then you can。

Logic errors are，And logic errors are，be spending the most time on。For which I would recommend。

Take a nap， go eat。Something。Sometimes you'd have，throughout the code，sit down with a piece of。

you want to solve the problem。And if you look up the term，went up on that one--，That is an actual。



![](img/b5da9e0adfa2d119ba2532092d29ebda_85.png)

And it's when a programmer，to a rubber ducky。That's me on the left explaining，You should always--。

Or code to anyone else，who doesn't really，Because that'll force you to，really closely。

And as you're doing that，And I figured out my problem。



![](img/b5da9e0adfa2d119ba2532092d29ebda_87.png)

So just go back to the basics。

![](img/b5da9e0adfa2d119ba2532092d29ebda_89.png)

Quick summary of dos and don'ts，So don't write the，test the entire program， and。

I know this is really，and I do it all the time。But don't do it。Because you're，a lot of bugs and。

hard to isolate which bugs，And it'll lead to a lot，Instead do unit testing。So write one function。

 test the，make sure it works，and so on and so on。

![](img/b5da9e0adfa2d119ba2532092d29ebda_91.png)

Do a little regression，testing， a little，and it's a lot more systematic，And it'll cut down on your。



![](img/b5da9e0adfa2d119ba2532092d29ebda_93.png)

If you're changing your，be changing your code as，remember to back up your code。

So if you have a version，don't just modify that，[INAUDIBLE] you've got terabytes。

it won't hurt to just，Document maybe what worked，And then make another copy， and。



![](img/b5da9e0adfa2d119ba2532092d29ebda_95.png)

So that's sort of a，to testing and debugging。The rest of the class will，or on errors that you。

So when your functions--，or when you run your，the program execution，Maybe it encountered。

of some unexpected condition。And when that happens，So the error is，And it's called an exception。

to what was expected。To what the program expected。So all of these errors，about in the previous。

examples of exceptions。And there are actually，of exceptions， which you'll。



![](img/b5da9e0adfa2d119ba2532092d29ebda_97.png)

and also in 60002。

![](img/b5da9e0adfa2d119ba2532092d29ebda_99.png)

So how do we deal，In Python， you can actually。

![](img/b5da9e0adfa2d119ba2532092d29ebda_101.png)

So if you know that a piece of，For example， here I'm dealing，And users are really，You tell them to。

they might give you their name。Nothing you can do about that。Or is there？Yes there is。

So in your program you can，that you think might，that might give you an error an，So you say try colon。

 and，that you think might。

![](img/b5da9e0adfa2d119ba2532092d29ebda_103.png)

If none of these lines of code，then great。Python doesn't do anything else。It treats them as just。

were part of a regular program。But if an error does，if someone doesn't，but puts their name。



![](img/b5da9e0adfa2d119ba2532092d29ebda_105.png)

to raise an error，And at that point，is there an accept statement？And if so， this except statement。

And it's going say，but I know how to handle it。I'm going to print out。



![](img/b5da9e0adfa2d119ba2532092d29ebda_107.png)

So if we look at code--，as in the slides-- and there's，So if I run it and I，it's going to run fine。

But if I run it and，it's going to give，Now if I run the same，try-- with a try except block。I run it。

 if I give it，But if I'm being a cheeky，automatically this would。



![](img/b5da9e0adfa2d119ba2532092d29ebda_109.png)

in the previous，But in this version，the programmer，or caught the，out this nicer looking message。

So bug in user input is nicer，A lot easier to read。So any problematic，you can put in a。

handle whatever errors might，This except block is going to，And you can actually get。

and catch specific。

![](img/b5da9e0adfa2d119ba2532092d29ebda_111.png)

In this case， I'm saying，for example， if the user，of an integer-- do this， which。

If the user inputs a，we're doing a divided by b， so，error。In that case we're going to。

the 0 division error，to print this other，So each-- so you can think of。



![](img/b5da9e0adfa2d119ba2532092d29ebda_113.png)

as sort of if else。

![](img/b5da9e0adfa2d119ba2532092d29ebda_115.png)

except for exceptions。So we're going to try this。But if there's a，Otherwise， if there's a。

And otherwise do this。So this last except，to be for any other，So if it's not a value error。



![](img/b5da9e0adfa2d119ba2532092d29ebda_117.png)

we're going to print，I couldn't even try to，try to make the program，besides those two。

So a lot of the time you're just，But there's other blocks that，And these are more。

talk about them anyway。

![](img/b5da9e0adfa2d119ba2532092d29ebda_119.png)

So you could have an else block。And an else block is，when the code in the，without raising an error。

And you can also，which is always executed。

![](img/b5da9e0adfa2d119ba2532092d29ebda_121.png)

If the code in the try block，if you raised an，a different kind of exception，in any of these cases。

is always going to get executed。And it's usually used，Like if you want to print。

or if you want to close a。

![](img/b5da9e0adfa2d119ba2532092d29ebda_123.png)

So。

![](img/b5da9e0adfa2d119ba2532092d29ebda_125.png)

We've encountered errors。We've caught them。What else can we do with，Three other things。

So one is if we've。

![](img/b5da9e0adfa2d119ba2532092d29ebda_127.png)

we can just fail silently。What this means is，and you just substitute whatever。



![](img/b5da9e0adfa2d119ba2532092d29ebda_129.png)

you for some other value。That's not actually，That's a bad idea。Because suddenly the user thinks。

and they think everything's，but then they get，as an output， which is far，So it's not really a。

user's values with anything。In the context-- so this is，In the context of a function，Well。

 if you have a，for example， let's say，trying to get the square，And let's say the user。

you're trying to find the square，And let's say the user，Well， if the user gives。



![](img/b5da9e0adfa2d119ba2532092d29ebda_131.png)

your function could return，means， well if the number，then return 0。Or minus 1。Or minus 100。

Just pick any value，represents some error value。

![](img/b5da9e0adfa2d119ba2532092d29ebda_133.png)

This is actually not a good，on in your program， if，now you have to do a check。And the check is。

 well if，is minus 1 or，Otherwise， do this。So you you're，because now you always have to，value。

Which makes the。

![](img/b5da9e0adfa2d119ba2532092d29ebda_135.png)

The other thing we can do is we，So this is how you create。



![](img/b5da9e0adfa2d119ba2532092d29ebda_137.png)

with exceptions。So in Python， signaling，means raising your，So so far we've just seen。

which means they，and then you deal with them。But in this last case， you're。

As a way to use that exception，So in Python， you raise，using this raise keyword。



![](img/b5da9e0adfa2d119ba2532092d29ebda_139.png)

And then some sort，like "user entered a negative。

![](img/b5da9e0adfa2d119ba2532092d29ebda_141.png)

A lot of the time we're，So if the number is less than，something is wrong。



![](img/b5da9e0adfa2d119ba2532092d29ebda_143.png)

The key word， the name，some sort of descriptive string。



![](img/b5da9e0adfa2d119ba2532092d29ebda_145.png)

So let's see an example of。

![](img/b5da9e0adfa2d119ba2532092d29ebda_147.png)

I have this function，It takes in two，And it's going to，going to contain the，in L1 divided by。

So I have a for loop here。For index in range length L1。So I'm going through every。

I'm going to try here。I'm going to try，So I think that this line，So I'm going to put。

The error I think，is a 0 division error，when an element and L2 is 0？



![](img/b5da9e0adfa2d119ba2532092d29ebda_149.png)

And when an element，going to append this，So NAN， as a string， you，and it stands for not a number。

So then I can continue。

![](img/b5da9e0adfa2d119ba2532092d29ebda_151.png)

with these not a numbers。If an element and L2 is 0。And otherwise， if there's，but there's another。

then I'm going to，And say， for any，just raise a value error。Which says， "get ratios was。



![](img/b5da9e0adfa2d119ba2532092d29ebda_153.png)

So here I'm sort of，into my one value error。So later on in my program，and do something with it。

Here's another。

![](img/b5da9e0adfa2d119ba2532092d29ebda_155.png)

So let's say we're were，We have a list of lists。Where we have the，first name and last name， and。

So we currently，And what I want to do，which is the same things，But I'm adding an extra--。

at the end of the list，is the average of，Or all of their-- yeah，So let's look at the code。

This is the function that，is this whole list here。I'm creating a new list。

And then I'm going for every，I'm appending element，to be this first list here。

So it's going to be the，Element at 1， which，And then the last thing I'm，The function call being。

is all of the grades， and，We're going to see three，This is the first one。It simply takes the。

and divides it by the。

![](img/b5da9e0adfa2d119ba2532092d29ebda_157.png)

If these students，and they've taken all of the，Because length of grades，greater than 0。

But what if we have a。

![](img/b5da9e0adfa2d119ba2532092d29ebda_159.png)

didn't show up for any tests？Then we have no record。



![](img/b5da9e0adfa2d119ba2532092d29ebda_161.png)

No record of grades，So they're going to，So if we run this function。



![](img/b5da9e0adfa2d119ba2532092d29ebda_163.png)

we're actually going to get a，trying to divide by length of，So what can we do？Two things。

 two options here。One is we can just flag the，So here there's a new average。



![](img/b5da9e0adfa2d119ba2532092d29ebda_165.png)

that's going to try to，as the previous one。And it's going to catch。



![](img/b5da9e0adfa2d119ba2532092d29ebda_167.png)

![](img/b5da9e0adfa2d119ba2532092d29ebda_168.png)

And when it catches it， it's，And when we run it， we're，no grades data，" which is fine。

And we're going to get this，So everyone else's grades，and for this last，That's because， when we。

if this is a function， remember，This function in this。



![](img/b5da9e0adfa2d119ba2532092d29ebda_170.png)

didn't return anything。So it returns a none。So for the averages for，the average is going to be。

didn't have any grades，And yeah， so that's，So that's our first option，and print a message。

The other option is to，So this is where you replace the，And if you do。



![](img/b5da9e0adfa2d119ba2532092d29ebda_172.png)

then this should be documented，So when you write the，you would say if the list is。

So this is the exact，We have a try and an except，We also print a，And then we return the 0。

So we still flag the error，we get a 0， because we've。



![](img/b5da9e0adfa2d119ba2532092d29ebda_174.png)

to just leaving it blank。So those are exceptions。Last thing we're going，are these things。

And assertions are good example，In that， you have，at the beginning of，Or at the end of functions。

And assert statements，that the assumptions，are exactly what the，So if we have a。

it's supposed to take in。

![](img/b5da9e0adfa2d119ba2532092d29ebda_176.png)

then the assert，that the function takes in an，Here's an example。This is the same average，Here。

 instead of，we're going to use，And the assert statement we're，At the beginning of。

And the key word is assert。The next part of the assert，So we expect that the length。

So has to be greater than 0。And then we have a，represents what do you print out，So if you run the。



![](img/b5da9e0adfa2d119ba2532092d29ebda_178.png)

a list that is empty，so the assert is，going to print out an assertion，If the assert is false， the。

It stops right there。Why does it behave this way？Well， assertions are，that preconditions and。

are exactly as you expect。So as soon as an，the function's going to，This is useful because。

from propagating bad values。So as soon as a precondition，as you enter a function。

went wrong in your program。And the program is going，So instead of，throughout the。

getting an output that，and then you having to trace，gave this bad value， you'll get。

assert being false，So it'll be a lot，where the bug came from。And you won't have to。



![](img/b5da9e0adfa2d119ba2532092d29ebda_180.png)

So this is basically，you really want to spot the bugs，And exceptions are good，when the user supplies。

but assertions are，that the types and other-- the。

![](img/b5da9e0adfa2d119ba2532092d29ebda_182.png)

maybe other conditions，are being held as the。

![](img/b5da9e0adfa2d119ba2532092d29ebda_184.png)

So the keyword，that the invariants on。

![](img/b5da9e0adfa2d119ba2532092d29ebda_186.png)

And that's it。Great。Thanks。

![](img/b5da9e0adfa2d119ba2532092d29ebda_188.png)

![](img/b5da9e0adfa2d119ba2532092d29ebda_189.png)