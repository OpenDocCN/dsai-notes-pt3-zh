# P14：L4.1- 分解、抽象与函数 - ShowMeAI - BV1Dw411f7KK

![](img/8645963f9187232ae2590185c1f36e26_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/8645963f9187232ae2590185c1f36e26_2.png)

![](img/8645963f9187232ae2590185c1f36e26_3.png)

all right everyone let's get started all。

![](img/8645963f9187232ae2590185c1f36e26_5.png)

right good afternoon on this rainy rainy，though。

![](img/8645963f9187232ae2590185c1f36e26_7.png)

okay so lecture four of six triple 1and，600 quick quick recap of what we did。

last time so last time we did a little，bit more string manipulations and then。

we saw how you can use for loops over，strings directly right so instead of。



![](img/8645963f9187232ae2590185c1f36e26_9.png)

having four loops that iterate over a。

![](img/8645963f9187232ae2590185c1f36e26_11.png)

range so 0 1 2 3 4 and so on you saw，that it was more powerful to sometimes。



![](img/8645963f9187232ae2590185c1f36e26_13.png)

use for loops that iterate over over，string objects directly so that was the。



![](img/8645963f9187232ae2590185c1f36e26_15.png)

first half of the lecture in the second，half we started looking at different。

ways that you can implement the，different different implementations to。

the same problem so we saw the problem，of finding the cube root and we saw some。

implementations we saw the guess and，check method and the approximation。

method and then we looked at what I，thought was the most powerful method。

which was the bisection method and this，one if you remember I played a game with。

someone in the audience where I got，where I guessed a number between 0 and。

100 and we saw that I was able to guess，that number really really quickly right。

using the bisection method and that's，the one that that's the method that。

you're going to implement that you are，currently implementing in your problem。

set okay so today so that that that's，sort of that sort of finishes。

introduction to some of the more basic，mechanisms in Python and today we're。

going to talk about how to structure，your programs such that you write nice。

coherent code reusable code by hiding，some away some of the details in your。

code ok and to do that we're going to。

![](img/8645963f9187232ae2590185c1f36e26_17.png)

look at these things called functions，all right so just stepping back and sort。

of getting a high-level view of how we。

![](img/8645963f9187232ae2590185c1f36e26_19.png)

write the code so far ok so so far the，way the way if you've been writing code。

for your programs is you know you open a，file you type some code to solve a。

particular problem given like in your，each file contains some piece of code no。

you have sequences of instructions that，contain maybe you know assignments loops。



![](img/8645963f9187232ae2590185c1f36e26_21.png)

conditionals and so on and so on but，really you have one file that contains。

each code and you write everything in，that in that particular file right but。

this is okay for smaller for smaller，problems that we've been seeing so far。

but when you're starting to write large，pieces of code it's going to get really。

messy really quickly okay so think about，if you are you know you want to use a。

for loop in one part of your code and，you find it useful to use that same for。

loop in another part of your code some，point in the future as you're you know。

debugging your code you might want to，change your original for loop you have。

to figure out all the other places where，you've used that type of for loop for。

example so as you're scaling your your，code you'll find it harder to keep track。

of of these details okay so this is，where functions will come into play in。

today's lecture we'll help you it okay，so if you want to be considered a good a。

good programmer in good programming，style would be to not necessarily add。

lots and lots of lines of code but，really to add more functionality to your。

programs okay so how many different，things how many different features can。

your program do rather than how long can，your code be right and that'll help you。

later on look at your code if you need，it for a future class and they'll help。

others if they want to look at your code。

![](img/8645963f9187232ae2590185c1f36e26_23.png)

later on if they find it useful okay so，today we're introducing this idea of。

functions and functions are mechanisms，to achieve decomposition and abstraction。



![](img/8645963f9187232ae2590185c1f36e26_25.png)

okay so these are two keywords here that，are going to pop up in today's lecture。

and also in in future lectures so before，I introduce decomposition and。

abstraction in the context of functions，let's first take a look at just sort of。

a real life example so let's take a，projector right I'm using one right now。

quick show of hands okay if I give you，all of the electronic components that。

are part of a projector right resistors，a fan a light bulb a lens the casing you。

know all of the different parts in it，who here would be able to build a perd。

vector do I see a hand no oh yeah nice，you can also lie I won't know the。

difference but if you can do that I，would be very impressed all right so you。

can't really put together a projector，right another show of hands if I gave。

you a projector that's fully assembled，okay and I gave you a computer for。

example who would be able to maybe，figure out within let's say an hour how。

to how to make them work together good，fair fair bit of fair bit of the class。

that's perfect that's exactly the，answers I was trying to get at here so。

none of us really know how projector，works right the internals but a lot more。

of us know how to work a projector right。

![](img/8645963f9187232ae2590185c1f36e26_27.png)

just given maybe a set of basic，instructions or just intuitively。

speaking okay so you see the projector，as sort of a black box right you don't。

need to know how it works in order to，use it right you know maybe what inputs。

it might take what's it supposed to do，at a high level right take the whatever。

is on my screen and put it up on the of，the large screen there just magnify it。

but you don't know how it does it right。

![](img/8645963f9187232ae2590185c1f36e26_29.png)

how the components work together so，that's the idea of abstraction right you。



![](img/8645963f9187232ae2590185c1f36e26_31.png)

don't need to know how the projector，works in order to use it okay as。

abstraction the other half of that was。

![](img/8645963f9187232ae2590185c1f36e26_33.png)

decomposition okay so let's say that now，given a projector I want to project a。

very very large image down on a very，large stage for example this is from one。

of the Olympics right it's a stage of，like 10 football fields something like。

that something massive right you could，build one projector that's able to。

project a very large image but that，would be really expensive and you'd have。

to build this one projector that used，for this one time right so instead what。

you could do is you could take a bunch，of smaller projectors right and feed。

different inputs to each one of them and，as you're feeding different inputs each。

one's going to show a different output，and then you're going to be able to have。

all of these different projectors，working together to solve this larger。

problem of projecting this really cool，edge on a very large stage so that's the。

idea of decomposition okay you take the。

![](img/8645963f9187232ae2590185c1f36e26_35.png)

same the same projector feed it，different inputs it does the exact same。

thing behind the scenes but it'll。

![](img/8645963f9187232ae2590185c1f36e26_37.png)

produce a different output for each one，of these different inputs so these。



![](img/8645963f9187232ae2590185c1f36e26_39.png)

different devices are going to work，together to achieve the same common goal。



![](img/8645963f9187232ae2590185c1f36e26_41.png)

that's the idea of the decomposition so，this these were applied to the problem。

of projecting large image or a projector，in general but we can apply these exact。

same concepts to programming，okay so decomposition is really just the。

problem of creating structure in your，code okay in the projector example we。



![](img/8645963f9187232ae2590185c1f36e26_43.png)

have separate devices working together。

![](img/8645963f9187232ae2590185c1f36e26_45.png)

in programming to achieve decomposition，you're dividing your code into smaller。

modules these are going to be，self-contained and you can think of them。

as sort of little mini programs right，you feed in some input to them they do a。

little task and then they give you，something back you know they go off and。

do their thing and then they give back a。

![](img/8645963f9187232ae2590185c1f36e26_47.png)

result okay these modules can be used to，break up your code and the important。

thing is that they're reusable so you，write a module once a little piece of。



![](img/8645963f9187232ae2590185c1f36e26_49.png)

code that does something once you debug，it once and then you can reuse it many。



![](img/8645963f9187232ae2590185c1f36e26_51.png)

many times in your code with different，inputs okay，benefit of this is it keeps your code。

organized and it keeps your code。

![](img/8645963f9187232ae2590185c1f36e26_53.png)

coherent okay so functions are going to，be used to achieve decomposition and to。

create structure in our code we're going，to see functions today in this lecture。

and in a few weeks you're going to，actually see when we talk about。

object-oriented programming how you can，achieve decomposition with classes and。

with classes you can create your own，object types like int sand floats you。

can create your own object types for，whatever you want but that's later okay。



![](img/8645963f9187232ae2590185c1f36e26_55.png)

so decomposition is creating structure，in your code and abstraction is is the。

idea of suppressing details so in the，projector example remember abstraction。

was you didn't need to know exactly how，the projector worked in order to use。

and it's going to be the same idea in，programming so once you write a piece of。

code that does a little task you don't，need to rewrite that piece of code many。

times you've written it once and you，write this thing called a function。



![](img/8645963f9187232ae2590185c1f36e26_57.png)

specification for it or a doc string and，this is a piece of text that tells。

anyone else who'd want to use it in the，future you know other people may be。

yourself it tells them how to use this，function what inputs does it take what's。

the type of the inputs what is the，function supposed to do and what is the。

output that you're going to get out of，it right so they don't need to know。

exactly how you implemented the function，they just need to know inputs what it。



![](img/8645963f9187232ae2590185c1f36e26_59.png)

does what's the output those three three。

![](img/8645963f9187232ae2590185c1f36e26_61.png)

things okay so these functions are then，reusable chunks of code and we'll see in。



![](img/8645963f9187232ae2590185c1f36e26_63.png)

a few examples today's lecture how how，to write some and how to call call。

functions and as we're going through，today's code I want you to sort of think。

about functions in with two different，hats on okay the first hat is from。

someone who's writing the function right，so in the projector example someone had。

to build the first projector right，someone had to know how to put all these。

components together so that's going to，be you writing a function right so you。

need to know how to make the function，work and then the other hat is you as。

someone as a programmer who's just using，the function right you're assuming it's。

already been implemented correctly and，now you're just using it to do something。



![](img/8645963f9187232ae2590185c1f36e26_65.png)

okay so these are some of the function，characteristics and we'll see an example。

on the next slide so functions going to，have a name now you have to call it。

something it's going to have some，parameters these are the inputs to the。

function you can have 0 inputs or as，many as you'd like function should have。

a doc string this is how you achieve，abstraction so it's optional but highly。

recommended this is how you tell other，people how to use your function function。

has a body which is the meat and，potatoes of the function right what it。



![](img/8645963f9187232ae2590185c1f36e26_67.png)

does and a function going to return，something it's it computes its thing and。

then it gives back spits back some，answer。

![](img/8645963f9187232ae2590185c1f36e26_69.png)

okay here's an example of a function，definition and a function call okay。

function definition is up here you know，I'll just draw here this is the function。



![](img/8645963f9187232ae2590185c1f36e26_71.png)

definition up here and this is the，function call down here so remember。

someone has to write the function you，know that that does something to begin。



![](img/8645963f9187232ae2590185c1f36e26_73.png)

with so this is how you write the，function the first is whoops the first。

is going to be this d EF keyword and de，F stands for it tells Python I'm going。

to define a function next is the name of。

![](img/8645963f9187232ae2590185c1f36e26_75.png)

the function in this case I'm calling。

![](img/8645963f9187232ae2590185c1f36e26_77.png)

the function is underscore even and the，function name should really be something。

descriptive whereas someone who's just。

![](img/8645963f9187232ae2590185c1f36e26_79.png)

using this function or looking at it can，pretty much tell what it's supposed to。

do without a lot without going a lot，farther than that than just looking at。

the name okay and then in parentheses，you give it any parameters also known as。

arguments these parameters are the，okay so this is the first line of the。

function definition and after this，everything that's going to be part of。

the function is going to be indented the，next part is going to be the dock string。

or the specification this is how we。

![](img/8645963f9187232ae2590185c1f36e26_81.png)

specification or the dock string starts，with triple quotes and ends with triple。

quotes and you can sort of think about。

![](img/8645963f9187232ae2590185c1f36e26_83.png)

this as a multi-line comment it's just，going to be text that's going to be。

visible to whoever uses the function and，it should tell them the fault the。

following things what are the inputs to，the function what is the function。

supposed to do generally and what is the，function going to give back to whoever，called it okay。

the next part is going to be the body of，the function we'll talk about what's。

inside it in the next slide and that's。

![](img/8645963f9187232ae2590185c1f36e26_85.png)

it that's all for the function，definition def blah blah blah indented。

everything inside the function okay so。

![](img/8645963f9187232ae2590185c1f36e26_87.png)

this is you writing the function，definition once the function definition。



![](img/8645963f9187232ae2590185c1f36e26_89.png)

is written you can call the function and，that's this part down here and here when。

you call a function you just say its，name and then you give it parameters and。

you give it as many parameters as the，function is expecting in this case only。



![](img/8645963f9187232ae2590185c1f36e26_91.png)

okay so what's inside the function body。

![](img/8645963f9187232ae2590185c1f36e26_93.png)

you can put anything inside the function，body you remember think of a function as。



![](img/8645963f9187232ae2590185c1f36e26_95.png)

sort of a small procedure a little mini，program that does something so you can。

do anything inside the function that you。

![](img/8645963f9187232ae2590185c1f36e26_97.png)

can do in the regular program print，things up do mathematical operations and。

so on the last line is the most，important part of the function though。

and it's this return statement that's，what we call it so it's a it's a line of。

code that starts with return which is a，keyword and then it's going to be some。

value okay notice this is an expression，here I percent 2 is equal equals 0 is an。

expression that's going to evaluate to，some value okay and as long as this part。



![](img/8645963f9187232ae2590185c1f36e26_99.png)

is something that evaluates some value，it could be anything you want and this。

line here return something tells Python，okay after you've finished executing。

everything inside the function what，value should I return and whoever called。

the function is going to get back that，value and the function call itself will。

be replaced by that value ok so let's。

![](img/8645963f9187232ae2590185c1f36e26_101.png)

I'm going to introduce the idea of scope，now okay，and scope just means is another word for。

environment so if I told you that you，can think of functions as little mini。

programs the scope of a function is，going to be a completely separate。



![](img/8645963f9187232ae2590185c1f36e26_103.png)

environment than the environment of the，main program so as soon as you make a。

function call behind the scenes what，Python says is okay I'm in the main。

program but I see a function call I'm，going to step out of this main program。

I'm going to go off into this new，environment I'm going to create entirely。

new set of variables that just exist，within this environment I'm going to do。

some computations when I see the return，I'm going to take this one return value。

I'm going to exit that environment and，then I'm going to come back to the main。

program okay so as you're entering from，one scope to another you're sort of。

passing these values back and forth so，when you're entering a scope you're。

passing a variable back into you're，passing a variable into the function and。

when the functions finished you're。

![](img/8645963f9187232ae2590185c1f36e26_105.png)

passing a value back to whoever called，it okay so once again this top part is。

the function definition and any，arguments for the function definition。

are called formal parameters and they're，called formal parameters because notice。

they don't actually have a value yet，right in the function definition you're。

sort of writing the function assuming，that in this case X is going to have。

some value but you don't know what it is，yet you only know what value X takes。

so this is your function definition and，then later on in your main program you。

might define some variable X is equal to，three and then you make a function call。



![](img/8645963f9187232ae2590185c1f36e26_107.png)

f of X here is your function call and it，says okay I'm calling F with the value。

three because X takes the value three，and then I'm going to map three into the，function the values。

our past into the function call are，called actual parameters because they're。

going to actually have a value okay，so let's step through this program this。

is the small program and see what，exactly happens behind the scenes in the。

scope and if you're just starting to，program I think it would be highly。

valuable if you take a piece of paper as，you're doing some of these exercises and。

you write down something similar to what，I'm going to go through here I think。

it'll help a lot and you'll be able to，see exactly you know step by step what。



![](img/8645963f9187232ae2590185c1f36e26_109.png)

variables take what values and which，scope you're in okay so here we go when。

the program first starts we're creating，this global scope okay it's the main。

program scope in the main program scope，the first thing that python is going to。



![](img/8645963f9187232ae2590185c1f36e26_111.png)

see is this part here de f f of X and，then some some stuff inside okay this。

tells python i have a function named x，but i don't care what's inside the code。

yet i don't care what's inside the，function definition yet because i。

haven't called the function yet right so，to python it's just some code just。



![](img/8645963f9187232ae2590185c1f36e26_113.png)

sitting in the global scope okay so，whenever you see de f you're just。

putting some code in there then you go，on to the next line x is equal to three。

so in the global scope you now have also，variable x is 3 and then the next line z。

is equal to f of X is a function call as，soon as you hit a function call you。



![](img/8645963f9187232ae2590185c1f36e26_115.png)

create a new scope a new environment，okay so we're temporarily leaving the。

global scope and sort of you know。

![](img/8645963f9187232ae2590185c1f36e26_117.png)

portaling into a new scope where we're，going to try to figure out what this。

function is going to do and what it's，going to return so the first thing you。

do is you map the parameters so X here，I'm calling f of X with 3 so the first。

thing I'm doing is I'm mapping every one，of the parameters in the definition to。

their values so the first thing I'm。

![](img/8645963f9187232ae2590185c1f36e26_119.png)

okay next line here is X is equal to X，plus 1 so we're still inside the。

we're printing this and then we're，returning X so in the scope of F X is。

equal to 4 so we're returning that value，back to whoever called it which was this。

function call within the global scope so，this part right here f of X which was。

the function call gets replaced with 4。

![](img/8645963f9187232ae2590185c1f36e26_121.png)

so inside the main program Z is equal to，4 okay and that's how we pass parameters。

into the function and we got a parameter，back from the function as soon as the。



![](img/8645963f9187232ae2590185c1f36e26_123.png)

function returns something the scope，that you were in for the function gets。



![](img/8645963f9187232ae2590185c1f36e26_125.png)

erased you forget about every variable，that was created in there delete that。

scope and you're back to wherever you，started calling it one warning though so。

what happens if there's no return，statement I said that every function has。

to return something if you don't。

![](img/8645963f9187232ae2590185c1f36e26_127.png)

explicitly put a return statement python，is going to add one for you you don't。

have to do this and it's going to，actually have returned none and oh and E。

and none is the special special type not。

![](img/8645963f9187232ae2590185c1f36e26_129.png)

none is the value for a special type，called none type and it represents the。

absence of a value okay what's that not。

![](img/8645963f9187232ae2590185c1f36e26_131.png)

not as not none is not a string exactly，it's a special special type okay so。

before we go on I wanted to go through a。

![](img/8645963f9187232ae2590185c1f36e26_133.png)

small exercise in spider just to just to，show you the difference that none and。

imprinting and returning makes so here，are two functions that I wrote one is is。

even with return that's its name so，pretty descriptive it's pretty much the。

same code we saw in the slides it just，has this extra little print thing it。

gets the remainder when I is divided。

![](img/8645963f9187232ae2590185c1f36e26_135.png)

divided by 2 and it returns whether the，remainder，is equal to zero so it'll either return。

a true or false boolean okay so my。

![](img/8645963f9187232ae2590185c1f36e26_137.png)

function call is this I'm saying is even，with return with value three when I make。

this function call this three gets，mapped into here this variable here so I。

is equal to three I'm going to print，with return and then I'm going to say。

remainder is equal to three percent two，which comes out to a value one because。

there's a remainder one and I'm going to，return whether one is equal to zero。

which is false so this this line here。

![](img/8645963f9187232ae2590185c1f36e26_139.png)

returns false but am i doing anything。

![](img/8645963f9187232ae2590185c1f36e26_141.png)

with the false not really it's just sort，of sitting in the code here okay so this。

gets evaluated to false I'm not printing，it I'm not doing any operations with it。

it's just sitting there so it won't show，up anywhere if I want the result to show。

up somewhere then I have to print it so，that's what this next line is doing okay。

so that one should be straight，straightforward is even with that。

returns a little bit trickier but not，too bad，I have print without return inside here。

and then I'm going to get a remainder is，equal to I % - and notice that I'm not。

have I don't have any return so，implicitly pythons going to add a return。

none for me like that you don't have to，add it so when I make the function call。

here it's going to do the same thing，except the return in this case is not。

going to be a boolean it's going to be，this special none right so this is going。



![](img/8645963f9187232ae2590185c1f36e26_143.png)

to get evaluated to none again I'm not，printing it out it's just sitting there。



![](img/8645963f9187232ae2590185c1f36e26_145.png)

if I were to print out the result of，that you'd be printing out this value。

none which if I run it you'll see here。

![](img/8645963f9187232ae2590185c1f36e26_147.png)

it just prints it out right there okay，so as you're doing your next piece set。

it's about functions and you're seeing，these nuns popping out in some places。

check to make sure that you've actually，returned something as opposed to just。

printed something inside the function，right like we did here。



![](img/8645963f9187232ae2590185c1f36e26_149.png)

okay alright so that's the difference，and the last thing I want to mention。

about this is even function is is how，useful it can be so notice so this is。



![](img/8645963f9187232ae2590185c1f36e26_151.png)

the function as in the slide and once，you write the function once you can use。

it many many times in your code so here，I have I'm using the function is even to。

print the numbers between 0 and 19。

![](img/8645963f9187232ae2590185c1f36e26_153.png)

including and whether the number is even，or odd so notice this piece of code here。

once I've written this function is even，looks really really nice right I have。

for all the numbers in this range if the，number I is even right this is going to。

return a true or false for all the，numbers 0 1 2 3 4 if it's true then I'm。

going to print out even and otherwise，I'm going to print out odd so if I run。

this it's going to do this 0 even 1 odd，to even and so on so notice using。

functions makes my code really，nice-looking right if I wasn't using。

functions I'd have to put these two。

![](img/8645963f9187232ae2590185c1f36e26_155.png)

lines somewhere inside here right and it，so I've said this maybe once or twice。



![](img/8645963f9187232ae2590185c1f36e26_157.png)

before in Python everything is an object。

![](img/8645963f9187232ae2590185c1f36e26_159.png)

okay，might not have meant anything back then。

![](img/8645963f9187232ae2590185c1f36e26_161.png)

but I think you're going to see what I，mean using this particular example okay。

so if if in Python everything is an，object and integers are objects floats。

are objects even functions are objects，okay。

![](img/8645963f9187232ae2590185c1f36e26_163.png)

so as you can pass objects as parameters，back and forth as function you know as。



![](img/8645963f9187232ae2590185c1f36e26_165.png)

function parameters you can also pass，other functions as parameters let's see。



![](img/8645963f9187232ae2590185c1f36e26_167.png)

what this means so we have three，function definitions here func a func B。

and func C and then I have three lines，of code here in the my main program so I。

have one called a func a one called func，B and one call to fog C let's trace。

through just like in the previous，example and see what exactly happens。

first thing I create is my global scope。

![](img/8645963f9187232ae2590185c1f36e26_169.png)

and I have three function definitions，again I don't care what's in the code。



![](img/8645963f9187232ae2590185c1f36e26_171.png)

yet because I haven't called the，functions yet okay Python just knows。

there's these functions with these names。

![](img/8645963f9187232ae2590185c1f36e26_173.png)

that contain some code after these，definitions I come to this line here。

print func a as soon as I make a，function call I'm going to create a new。

scope and I'm going to hop into there，okay inside func a I'm going to go and。

look at what func a does it doesn't take，into parameters it just prints out this。

this the this message here and then it，it leaves it's done there's no return so。

we return none so func a returns none to，whoever called it which was that line。

next line this one right here print five，plus some function call again I'm going。

to hop into funk be scope and see what，to do there so first I'm going to map my。

parameters so - whoops - gets mapped to，Y so inside funk B's scope Y is going to。

get the value - that's the very first，thing I'm doing mapping all the。

parameters then I'm going to print this，thing here and then I'm going to return。

y so inside funk B Y has the value two，and I'm returning to back to whoever。

called me okay so this is the value two，and I'm going to print five plus 2 which。

is 7 last one this is a trickiest loop，that popped up if you think you've got。

it try that exercise but otherwise，follow along print funk see funk a ok so。

I see that I am going to enter funk sees，scope so I'm going to look at funk see。

duck what funk see does first thing I do，is I'm mapping all the parameters don't。

even worry about the fact that this is a，function right now just pretend it's you。

know X or something so you say funk a is，going to get mapped to the variable Z。

inside funky so Z is Funk see just，mapping parameters from actual to formal。

then what do we do inside function C we，print out inside funky and then we。



![](img/8645963f9187232ae2590185c1f36e26_175.png)

return Z this is the cool part inside。

![](img/8645963f9187232ae2590185c1f36e26_177.png)

funky Z is funk a so if you replace Z，with funk a this here becomes return。

funk a open close parenthesis look，familiar。

![](img/8645963f9187232ae2590185c1f36e26_179.png)

we did that function call right there，right so that's just another function。

so with that being another function call。

![](img/8645963f9187232ae2590185c1f36e26_181.png)

you're going to create another scope and，you're going to pop into that one so。

we're one two I guess two scopes deep，we're trying to figure out where we're。

going so funk a scope is going to be up，here so what does funk a do it just。

prints out this and it returns none so，we're going to return none to whoever。

called us which is funky so this line，here becomes return none and so this。

line here is going to return none to，whoever called it which was this line。

down here oops I didn't mean to cross it。

![](img/8645963f9187232ae2590185c1f36e26_183.png)

up so that line here is going to print，none so it's if you just go step by step。

it shouldn't be too bad to try to map，what happens with with variable names。

and informal parameters and actual，parameters okay，that's why I highly recommend pieces of。

paper and pens one last thing I want to，mention about scope before we do another。



![](img/8645963f9187232ae2590185c1f36e26_185.png)

example so there are three sort of，situations you might find yourself in。

the first one is probably the most，typical and this is when you define a。

function and it's using a variable named，X in this case that's also defined。



![](img/8645963f9187232ae2590185c1f36e26_187.png)

outside of the function and that doesn't，matter because of the idea of scopes so。

inside the global scope you can have，variables X when you're inside a。

different scope you can have whatever，variables the variable names you want。

and when you're inside that scope Python，is going to use those variable names so。

they don't interfere with each other at。

![](img/8645963f9187232ae2590185c1f36e26_189.png)

all so in this example I've defined a，variable X is equal to 1 and then I。

increment it and that doesn't interfere，with the fact that we have a variable X。

outside this one's a little bit trickier，I define as this function G and all G。

does is access a variable X but notice，inside G I've never actually declared or。

initialized the variable X right and，this F I said X is equal to 1。



![](img/8645963f9187232ae2590185c1f36e26_191.png)

but in here I'm just sort of using X so，this does not give you an error in fact。

it's okay for you to do this in Python，Python says okay I'm in this scope but I。

don't have a variable named X so let me，just go into the scope of whoever called。

me so I'm going to just temporarily hop，out of the scope and see is there a。

variable X outside of of me and it'll，find this variable X here and it's going。



![](img/8645963f9187232ae2590185c1f36e26_193.png)

this last example here is actually not，allowed in Python similar to this one。

except that I'm trying to increment a，value of X but then I'm also trying to。

reassign it to the same value of X the，problem with that is I never actually。

initialized X inside H so if I said if，inside H I said X is equal to 1 and then。



![](img/8645963f9187232ae2590185c1f36e26_195.png)

I did X plus equals to 1 then it would，do that，I just tried to access X and then。

incremented increment it and then try to，reassign it and that actually that's。

actually not allowed in Python there's a，way around it using global variables ok。

but it's actually frowned upon to use，global variables though global variables。

are part of the readings for for this，lecture and the reason why it's not a。

great idea to use global variables is。

![](img/8645963f9187232ae2590185c1f36e26_197.png)

because global variables sort of give，you this this loophole around scopes so。

it allows you to write code that can。

![](img/8645963f9187232ae2590185c1f36e26_199.png)

become very messy ok so global using，global variables you can be inside a。

function and then modify a variable，that's defined outside of of your。

function and that sort of defeats the，purpose of functions and using them in。

writing these coherent modules that that。

![](img/8645963f9187232ae2590185c1f36e26_201.png)

that said it might it will sometimes be，useful to use global variables as you'll。



![](img/8645963f9187232ae2590185c1f36e26_203.png)

![](img/8645963f9187232ae2590185c1f36e26_204.png)

okay cool so let's go on to the last，scope example okay this slide is here。

and notice I've bolded underlined and。

![](img/8645963f9187232ae2590185c1f36e26_206.png)

italicized the Python tutor because I，find it extremely helpful so the Python。

tutor as I've mentioned in one of the，assignments is it was actually developed。

by a grad student here or post grad，student slash postdoc here and it allows。

you to go through Python paste paste，code go through it step by step like。

with each iteration it'll show you，exactly what values each variable has。

what scope you're in when scopes get，created when scopes get destroyed。

variables within each scope so pretty，much every single detail you need to。

sort of understand functions you know as，we're starting to you can see we've had。

a couple questions and these are great，questions so if you're still trying to。

understand what's going on I would，highly suggest you take a piece of code。

and just run it in the Python tutor and，you should be able to see exactly what。

happens in sort of a similar way that，I've drawn my my diagrams okay in all of。

the in all of the codes for this，particular lecture I've put links to the。

Python tutor for each one of those，exercises you can just copy and paste。

those and it'll automatically populate，it with that particular example so you。

just have to click step step-step，okay so having made my plug for python。



![](img/8645963f9187232ae2590185c1f36e26_208.png)

tutor let's go on okay，so here's an example it's going to show。

a couple things one is what happened you，know print versus return and also this。



![](img/8645963f9187232ae2590185c1f36e26_210.png)

idea you can nest functions okay，so just so you could have nested loops。

nested conditionals you can also nest，functions within functions so let's draw。



![](img/8645963f9187232ae2590185c1f36e26_212.png)

some diagrams just like before of the，scopes first thing we're going to do is。

when we write have a program we're going，to create the global scope and we're。

going to add every variable that we have，and then when we reach a function call，we're going to。

do something about that okay so the，first thing in the global scope is this。

function definition again in my global，scope I just have G as some code because。

I have not called it yet okay I only go，inside a function when I make a function。

call so G contains some code so we're，done with 75% of that of that code next。

line is X is equal to 3 so I'm making X，be a variable inside my global scope。

with value 3 and then I have this Z is，equal to G of X this is a function call。

when I see a function call I'm going to，create a new scope so here is the scope。

of G with the scope of G I'm mapping，variables to actual actual parameters to。

formal parameters so the first thing I'm，doing is I'm saying inside G what is the。

value of actual parameter X and X is，going to be the value 3 because I've。

called G of X with X is equal to 3 okay，next what I see inside this function so。

this is the inside of the function is，this bit here it's another function。

definition again since I'm just defining，the function and I'm not calling it all。

Python sees is H is some code ok I，haven't called the function H yet。

because I'm just defining it here with，DF ok so that finishes this this part。

here the next line is X is equal to X，plus 1 so inside the scope of G I'm。

incrementing X 2 before then I'm，printing out this line and then I've，reached here H。

this is actually a function call and I'm，calling H as soon as I make a function。

call I'm creating another scope so I'm，temporarily going out of the scope of G。

and going into the scope of H so Python，knows that H contains some code and now。

I can go inside H and do whatever I need，to do so the first so H doesn't have any。

parameters so I don't need to populate，anything like that in there X does does。

define a variable called X which is ABC。

![](img/8645963f9187232ae2590185c1f36e26_214.png)

it's a string and then that's all H does，what does it return none I heard。

murmuring but I think none was the was。

![](img/8645963f9187232ae2590185c1f36e26_216.png)

what you guys are saying so since，there's no return statement H is going。

to return none okay so H returns none，back to whoever called it which was this。

code inside G so that gets replaced with。

![](img/8645963f9187232ae2590185c1f36e26_218.png)

none the thing that I've H the circled。

![](img/8645963f9187232ae2590185c1f36e26_220.png)

read H here as soon as H returns we're，going to get rid of that scope all the。



![](img/8645963f9187232ae2590185c1f36e26_222.png)

variables created within it and we're，done with H so now we're back into G and。

we just finished executing this and this，got replaced with none okay we're not。

printing it out right so this doesn't，show up anywhere it's just there so。

we're finished with that line and the，next line is return X so X inside G is 4。

so 4 gets returned back to whoever，called it which was in the global scope。

here so this gets replaced with 4 so，once we've returned X we've completely。

exited out of that the scope of G and，we've come back to whoever called us。

which was global scope and we've，replaced Z is equal to G of X and that。

completely got replaced with for the。

![](img/8645963f9187232ae2590185c1f36e26_224.png)

![](img/8645963f9187232ae2590185c1f36e26_225.png)

so that's sort of showing the nested，nested functions all right just circling。



![](img/8645963f9187232ae2590185c1f36e26_227.png)

back to decomposition abstraction this，is the last slide you can see in in if。

you look at the code associated with J's，lecture there's some other examples。

where you can see just how powerful it，is to use functions and you can write a。

really clean and simple code if you，define your own functions and then just，use them later。

right and the beauty of defining your，own functions that you can use multiple。

times later is you only have to debug，the function once right，I know debugging is not your favorite。

thing but you only have to debug this，one thing once and then you can know。



![](img/8645963f9187232ae2590185c1f36e26_229.png)

that it's right and it works well you，can just use it multiple times all right。



![](img/8645963f9187232ae2590185c1f36e26_231.png)

![](img/8645963f9187232ae2590185c1f36e26_232.png)