# P33：L9.1- Python类与继承 - ShowMeAI - BV1Dw411f7KK

![](img/240a848cb170b6031b7dbcf28d6b132b_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/240a848cb170b6031b7dbcf28d6b132b_2.png)

![](img/240a848cb170b6031b7dbcf28d6b132b_3.png)

all right everyone let's get started。

![](img/240a848cb170b6031b7dbcf28d6b132b_5.png)

so so today's this is going to be the，section second lecture on。

object-oriented programming so just a，quick recap of last time on Monday we。

saw we were introduced to this idea of，object-oriented programming and we saw。



![](img/240a848cb170b6031b7dbcf28d6b132b_7.png)

these things called abstract data types，and these abstract data types we。



![](img/240a848cb170b6031b7dbcf28d6b132b_9.png)

implemented through Python classes and。

![](img/240a848cb170b6031b7dbcf28d6b132b_11.png)

they allowed us to create our own data，types that sort of abstracted a general。

object of our choosing right so we've，used lists before for example but with。

abstract data types we were able to，create objects that were of our own。



![](img/240a848cb170b6031b7dbcf28d6b132b_13.png)

types we saw the coordinate example and，then at the end of the class we saw the。



![](img/240a848cb170b6031b7dbcf28d6b132b_15.png)

fraction example so today we're going to，talk a little bit more about。

object-oriented programming and classes，we're going to see a few more examples。

and we're going to talk about a few，other nuances of classes talk about。

information information hiding and class，variables and in the second half of the。

lecture we're going to talk about the，idea of inheritance so we're going to。

use object-oriented programming to sort，of simulate how to simulate how real。

life works so in real life you have，inheritance and in in object-oriented。

programming you can also simulate that，okay so the first few slides are going。

to be a little bit of recap just to make，sure that everyone's on the same page。

before I introduce a couple of new。

![](img/240a848cb170b6031b7dbcf28d6b132b_17.png)

concepts related to classes so recall，that when in the last lecture we we。

talked about writing code from two，different perspectives right the first。

was from someone who wanted to implement，a class so implementing the classmate。



![](img/240a848cb170b6031b7dbcf28d6b132b_19.png)

defining your own object type so you，define the object type when you define。

the class and then you decided what data，attributes you wanted to define your。

object so what what data makes up the。

![](img/240a848cb170b6031b7dbcf28d6b132b_21.png)

object what is the object okay in，addition to data attributes we also saw。

these things called methods and methods，were ways to tell someone how to。

use your data type so what are ways，that's that someone can interact with。

the data type okay so that's from the，point of view of someone who wants to。

write their own object type，so you're implementing you're，implementing a class and the other。



![](img/240a848cb170b6031b7dbcf28d6b132b_23.png)

perspective was to write code from the，point of view of someone who wanted to。

use a class that was already written，okay so this involved creating instances。



![](img/240a848cb170b6031b7dbcf28d6b132b_25.png)

of objects so you're using the object，type once you created instances of。

objects you're able to do operations on，them so you're able to see what methods。



![](img/240a848cb170b6031b7dbcf28d6b132b_27.png)

whoever implemented the class added and，then you can use those methods in order。

to do operations with your instances so。

![](img/240a848cb170b6031b7dbcf28d6b132b_29.png)

just looking at the coordinate example，we saw last time a little bit more in。

detail about what that meant so we had a，class definition of an object type which。

included deciding what the class name，what the class name was and the class。



![](img/240a848cb170b6031b7dbcf28d6b132b_31.png)

name basically told Python what type of，an object this was okay in this case we。

decided we wanted to name a coordinate，we wanted to create a coordinate object。



![](img/240a848cb170b6031b7dbcf28d6b132b_33.png)

and the type of this object was，therefore going to be a coordinate we。



![](img/240a848cb170b6031b7dbcf28d6b132b_35.png)

define the class in the sort of general，way okay so we needed a way to be able。



![](img/240a848cb170b6031b7dbcf28d6b132b_37.png)

to access data attributes of any。

![](img/240a848cb170b6031b7dbcf28d6b132b_39.png)

instance so we use this self variable，okay and the self variable was we we。

used to refer to any instance to the，data attributes of any instance in a。

sort of general way without actually，having a particular instance in mind。

okay so whenever we access data，attributes we would say something like。

self dot to access a data attribute，you'd access the attribute directly with。



![](img/240a848cb170b6031b7dbcf28d6b132b_41.png)

self dot X or if you wanted to access a，method you would say self dot and then。



![](img/240a848cb170b6031b7dbcf28d6b132b_43.png)

the method name for example distance and，really the bottom line of the class。



![](img/240a848cb170b6031b7dbcf28d6b132b_45.png)

definition is that your class defines，all of the data so data attributes and。

all of the methods that are going to be，common across all of the instances so。

any instance that you create of a。

![](img/240a848cb170b6031b7dbcf28d6b132b_47.png)

particular object type that instance is，going to have。



![](img/240a848cb170b6031b7dbcf28d6b132b_49.png)

this exact same structure okay the，difference is that every instances。

values are going to be different so when，you're creating instances of classes you。

can create more than one instance of the，same class so we can create a coordinate。



![](img/240a848cb170b6031b7dbcf28d6b132b_51.png)

object here using this syntax right here，so you say the type and then whatever。

values it takes in and you can create。

![](img/240a848cb170b6031b7dbcf28d6b132b_53.png)

more than one coordinate object each，coordinate object is going to have。

different data attributes sorry it's，going to have different data attribute。

values okay every coordinate object is，going to have an X value and a Y value。

but the x and y values among different，instances are going to are going to vary。

okay so that was that's the difference，between defining a class and looking at。

a particular instance of class so，instances have the structure of the。

class so for a coordinate and in all，instances have an x value and a Y value。

but the actual values are going to vary，between the different instances okay。

so ultimately why do we want to use，object-oriented programming so so far。

the examples that we've seen are word，numerical right a coordinate a fraction。

but object or using object-oriented，programming you can create objects that。

mimic real-life so if I wanted to create，objects of an object that defined a cat。

in an object that defined a rabbit I，could do that with object-oriented。

programming I would just have to decide，as a programmer what data and what。

methods I'd want to assign to to these，to these groups of objects okay so using。

object-oriented programming each one of，these is considered a different object。

and as a different object I can decide。

![](img/240a848cb170b6031b7dbcf28d6b132b_55.png)

that a cat is going to have a name an，age and maybe a color associated with it。

and these three here on the right each，one of these rabbits is also an object。

and I'm going to decide that I'm going，to represent a rabbit by just。



![](img/240a848cb170b6031b7dbcf28d6b132b_57.png)

agent and a color okay and with，object-oriented programming I can using。

these using these attributes I can sort。

![](img/240a848cb170b6031b7dbcf28d6b132b_59.png)

of group these three objects together。

![](img/240a848cb170b6031b7dbcf28d6b132b_61.png)

I'm grouping sets of objects that are，going to have the same attributes。

together and attributes this is also a，recap of last time come in two forms。

right data attributes and procedural，attributes so the data attributes are。

basically things like are basically。

![](img/240a848cb170b6031b7dbcf28d6b132b_63.png)

things that define what the object is so，how do you represent a cat as an object。

and it's up to you as the programmer to，decide how you want to do that for。

coordinate it was pretty pretty，straightforward you had an X and a。



![](img/240a848cb170b6031b7dbcf28d6b132b_65.png)

y-value if we're representing something，more abstract like an animal then maybe。



![](img/240a848cb170b6031b7dbcf28d6b132b_67.png)

I would say well I'm going to represent，an animal by an age and a name okay so。

it's really up to you to decide how you。

![](img/240a848cb170b6031b7dbcf28d6b132b_69.png)

want to represent what data attributes。

![](img/240a848cb170b6031b7dbcf28d6b132b_71.png)

you want to have to have to represent。

![](img/240a848cb170b6031b7dbcf28d6b132b_73.png)

your object with procedural attributes，were also known as methods and the。

methods are essentially asking what can，your object do okay so how can someone。

who wants to use your object how can。

![](img/240a848cb170b6031b7dbcf28d6b132b_75.png)

someone interact with it so for a，coordinate we saw that you can find the。

distance between two coordinates maybe，for more abstract animal object you，sound。



![](img/240a848cb170b6031b7dbcf28d6b132b_77.png)

okay by maybe printing to the screen or，something like that。



![](img/240a848cb170b6031b7dbcf28d6b132b_79.png)

okay this slides also a recap of how to，create a class just to make sure。

everyone's on the same page before we go，on so we defined a class using this。

class keyword and we said class the name，of the class so now we're going to。

create a more abstract animal class，we're going to see in the second half of。

the lecture what it means to put，something else in the parentheses but。

for now we say that an animal in an。

![](img/240a848cb170b6031b7dbcf28d6b132b_81.png)

animal is an object，in Python so that means it's going to be。



![](img/240a848cb170b6031b7dbcf28d6b132b_83.png)

it's going to have all of the properties，that any other object in Python has and。

as we're creating this animal we're，going to define how to create an。



![](img/240a848cb170b6031b7dbcf28d6b132b_85.png)

instance of this class so we say de f，and this init was the special method。

that told Python how to create an object，inside the parentheses remember we have。

the self which is a variable that we，used to refer to any instance of the。

class okay we don't have a particular，instance in mind we just want to be able。

to refer to any instance okay so we use，this self variable and then in here and。

then the second parameter here is going，to represent what other data we use to。

initialize our object with so in this，case I'm going to say I'm going to。

initialize an animal object with an H。

![](img/240a848cb170b6031b7dbcf28d6b132b_87.png)

okay so when I create an animal I need，to give it an age inside the init are。



![](img/240a848cb170b6031b7dbcf28d6b132b_89.png)

any initializations that i want to make，so the first thing is I'm going to。

assign an instance variable age so this，is going to be the data attribute age to。



![](img/240a848cb170b6031b7dbcf28d6b132b_91.png)

be whatever's passed in and then I'm，also making another assignment here。

where I'm assigning the data attribute，name to be none originally later on in。



![](img/240a848cb170b6031b7dbcf28d6b132b_93.png)

the code when I want to create an animal，object I say the class name and then I。

pass it in whatever parameters it takes，in this case the age and I'm assigning。



![](img/240a848cb170b6031b7dbcf28d6b132b_95.png)

![](img/240a848cb170b6031b7dbcf28d6b132b_96.png)

it to this instance here okay alright so。

![](img/240a848cb170b6031b7dbcf28d6b132b_98.png)

now we have this class animal we've done，the first part here which is to。



![](img/240a848cb170b6031b7dbcf28d6b132b_100.png)

initialize the class right so we've told，Python how to create an object of this。

type there's a few other methods here。

![](img/240a848cb170b6031b7dbcf28d6b132b_102.png)

that I've implemented next - we call，getters and the two after that we call。

setters and getters and setters are very。

![](img/240a848cb170b6031b7dbcf28d6b132b_104.png)

commonly used when when it when when，implementing a class so getters。

essentially return the values of any of。

![](img/240a848cb170b6031b7dbcf28d6b132b_106.png)

so if you look carefully yet age is just。

![](img/240a848cb170b6031b7dbcf28d6b132b_108.png)

returning self dot age and get name just，return self name so they're very simple。

methods similarly set agents that name。

![](img/240a848cb170b6031b7dbcf28d6b132b_110.png)

we're going to see what this what this，funny equal sign is doing here in the。

next couple of slides but setters do a，very similar thing where they're going。

to set the data attributes to whatever。

![](img/240a848cb170b6031b7dbcf28d6b132b_112.png)

is passed in okay so those are getters，and setters and then the last thing down。

here is this STR method and this STR，method is used to tell Python how to。

print an object of this type animal so，if you didn't have this STR method if。

you remember from last lecture what ends，up happening is you're going to get some。

message when you print your object that，says this is an object of type animal at。

this memory location which is very，uninformative right so you implement。

this method here which tells python how，to print an object of this type okay so。

the big point of this slide is that you，should be using getters and setters you。

should be implementing getters and，setters for your classes and we're going。

to see in the next couple of slides why。

![](img/240a848cb170b6031b7dbcf28d6b132b_114.png)

exactly but basically they're going to，prevent bugs from from coming into play。



![](img/240a848cb170b6031b7dbcf28d6b132b_116.png)

later on if someone decides to change，the implementation so we saw how to so。

the previous slide this slide here shows，the implementation of the animal class。



![](img/240a848cb170b6031b7dbcf28d6b132b_118.png)

and here we can see how we can create an，instance of this object so we can say a。

is equal to animal 3 so this is going to，create a new animal object with an age。

of 3 and we can access the object，through the variable a dot notation。

recall is a way for you to access data，attributes and methods of a class okay。

so you can say a dot age later on in，your program and that is allowed it'll。

try to access the age data attribute of。

![](img/240a848cb170b6031b7dbcf28d6b132b_120.png)

this particular instance of the class a，so this is going to give you 3 however，it's actually not rec。

to access data attributes directly so。

![](img/240a848cb170b6031b7dbcf28d6b132b_122.png)

this is the reason so you're going to，see on the next slide the reason why。

we're going to use getters and setters，instead you should use the get age。

getter method to get the age of of the，animal so this is going to return also。



![](img/240a848cb170b6031b7dbcf28d6b132b_124.png)

three so these are going to do the same，thing and the reason why you'd want to。

use getters and setters is this idea of，information hiding okay so the whole。

reason why we're using classes and，object-oriented programming is so that。

you can abstract certain certain data，from the user okay one of the things you。

you should be abstracting is these these，data attributes so users shouldn't。

really need to know how a class is，implemented they just they should just。



![](img/240a848cb170b6031b7dbcf28d6b132b_126.png)

know how to use the class okay so，consider the following case let's say。

whoever wrote the animal class wants to，change the implementation and they've。

decided they don't want to call the data，attribute age anymore they want to call。

it years okay so when they initialize an，animal they say self dot years is equal。



![](img/240a848cb170b6031b7dbcf28d6b132b_128.png)

to age so an animal still gets，initialized by its age and the age gets。

passed into a data attribute named years，okay since I'm implementing this class I。

want to have a getter which is going to，return self dot years so I'm not。

returning self age anymore because age，is no longer the data attribute I'm。

using so with this new implementation if，someone was using if someone was using。

this implementation and was accessing，age directly as as accessing the data。

attribute age directly with this new，implementation they'd actually get an。

error right because this animal that，they created using my old implementation。

no longer has an attribute named age and，so python is going to spit out an error。

saying no attribute found or something，like that okay if they were using the。

getter a dot get age the person who，implemented the class re-implemented get。

age to work correctly right with their，new data attribute years as opposed to。

age so if I was using the getter，get age I wouldn't have run into the bug。

okay so things to remember use getters，and right getters and setters for your。

classes and later on in your code use，getters and setters to prevent bugs and。

and to promote easy to maintain code。

![](img/240a848cb170b6031b7dbcf28d6b132b_130.png)

okay so information hiding is great but，having said that pythons actually not。

very great at information hiding okay，Python allows you to do certain things。

that you should never be doing okay so，the first we've just seen so it's 2x the。

first is to access data attributes from，outside of the class okay so if I were。

to say a dot age Python allows me to do，that without using a getter and setter。

Python also allows you to write to data。

![](img/240a848cb170b6031b7dbcf28d6b132b_132.png)

attributes from outside the class so if，I implemented the class animal assuming。

that age was a number an integer and all，of my methods work as long as age as an。

integer but someone decided to be smart，and outside of the class set age to be。

infinite as a string that might cause，the code to crash okay，Python allows you to do that but now。



![](img/240a848cb170b6031b7dbcf28d6b132b_134.png)

you're breaking the fact that age has to，be an integer right so now the methods。

should probably be checking the fact。

![](img/240a848cb170b6031b7dbcf28d6b132b_136.png)

that age is an integer all the time the，other thing that you're allowed to do is。

to create data attributes outside of the，class definition okay，so if I wanted to create a new data。

attribute called size for this，particular instance Python also allows。

me to do that and I can set it to。

![](img/240a848cb170b6031b7dbcf28d6b132b_138.png)

whatever I want so Python allows you to，do all these things but it's actually。

not good style to do any of them so just，don't do it all right so the last thing。

I want to mention the last thing about，class is before we go on to inheritance。

is this idea called default arguments。

![](img/240a848cb170b6031b7dbcf28d6b132b_140.png)

and default arguments are passed into，methods and since methods or functions。

you can also pass in default arguments，to functions，so for example this setname method had。

self and then this new name is equal to，this empty string here okay we haven't。

seen this before but this is called a，default argument and you can use the。

the first way is so we can create a new，instance of an animal type object with。

this line here a is equal to animal 3，and then we can say a dot set name so。

this calls the setter method to set the，name and notice we've always said that。



![](img/240a848cb170b6031b7dbcf28d6b132b_142.png)

you have to put in parameters for。

![](img/240a848cb170b6031b7dbcf28d6b132b_144.png)

everything other than self ok but here，we have no parameters passed in but。

that's ok because new name actually has，a default argument ok so that tells。

Python if no parameters passed in for，this particular formal parameter then。

use whatever is up here by default so if，I haven't passing the parameter a。

detonate a dot set name sorry a dot set，name is going to be setting the name to。

the empty string because that's what the，default parameter is so in the next line。

when I print a dog get name this is just。

![](img/240a848cb170b6031b7dbcf28d6b132b_146.png)

going to print the empty string ok if。

![](img/240a848cb170b6031b7dbcf28d6b132b_148.png)

you do want to pass in a parameter you，can do so as as as normal so you can say。

is equal to animal 3 a dot set name and，then pass in a parameter here and then。

new name is going to be assigned to，whatever parameters passed in like that。

whatever you pass in overrides the，default argument and everything is is。

good so when I print a dot get name this，is going to print out the name that you。



![](img/240a848cb170b6031b7dbcf28d6b132b_150.png)

that you've passed in questions about。

![](img/240a848cb170b6031b7dbcf28d6b132b_152.png)

what if you don't provide a default，value for for new name if you don't。

provide a default argument for a new，name and you do this case here then。

that's going to give you an error so，python is going to say something like。



![](img/240a848cb170b6031b7dbcf28d6b132b_154.png)

expected one argument god zero or。

![](img/240a848cb170b6031b7dbcf28d6b132b_156.png)

![](img/240a848cb170b6031b7dbcf28d6b132b_157.png)

okay all right so let's move on to this，idea of hierarchies okay so the great。

thing about object-oriented programming。

![](img/240a848cb170b6031b7dbcf28d6b132b_159.png)

is that it allows us to add layers of，abstraction to our code right so we。

don't need to know how very very，low-level things are implemented in。

order to use them and we can build up，love we can build up our code to be more。



![](img/240a848cb170b6031b7dbcf28d6b132b_161.png)

and more complex as we use up these，different these different abstractions。

so consider every one of these things on，this slide as being a separate object。

right every one of these things is can。

![](img/240a848cb170b6031b7dbcf28d6b132b_163.png)

according to our implementation of an，animal the one thing that an animal has。

is an age okay and that's probably true，right every one of these things has an。

age but now I want to build up on this，and create separate groups right and。

each one of these separate groups that I，create on top of animal is going to have。

its own functionality right they're，going to be a little bit more specific。

and more specialized so I can create，these three groups now a cat a rabbit。

and a person group and for example so，they're all animals right they all have。

an age but for example maybe a person's，going to have a list of friends where as。

a cat and a rabbit do not maybe a cat，has a data attribute for the number of。

lives they have left right whereas a，person in a rabbit do not okay so you。

can think of adding these more，specialized adding more adding，functionality to each one of these。

subgroups okay so we're going to be more，and more specialized but all of them。

retaining the fact that they are animals。

![](img/240a848cb170b6031b7dbcf28d6b132b_165.png)

they all have an age for it，sample so on top of these we can add。

another layer and say that a student is，a person and is an animal okay but in。

addition to having an age and maybe also，having a list of friends a student might。

also have a major or they're pretty，young so maybe their favorite you know。



![](img/240a848cb170b6031b7dbcf28d6b132b_167.png)

their favorite subject in school so so，that's the general idea of of。

hierarchies okay so we can sort of，abstract the previous the previous slide。

into this one and say that we have，parent classes and child classes。

okay the animal class is like our parent，inheriting from the animal class we have。

these child classes or subclasses okay，whatever an animal can do a person can。

do whatever an animal can do a cat can，do and whatever an animal can do a，rabbit can do okay。

that is have an age and maybe some，really basic functionality but between。

person cat and rabbit they're going to，be varying wildly as to the kinds of。

things that they can do right but they，can all do whatever animal can do so。

child classes inherit all of the data，attributes and all of the methods or。



![](img/240a848cb170b6031b7dbcf28d6b132b_169.png)

behaviors that their parents classes。

![](img/240a848cb170b6031b7dbcf28d6b132b_171.png)

have but child classes can add more，information like for example a person。

can have a list of friends where as a，general animal will not it could add。



![](img/240a848cb170b6031b7dbcf28d6b132b_173.png)

more behavior like maybe a cat can climb，trees whereas people and rabbits cannot。

or you can also override behavior so in，the previous one we had animal person。

student so maybe we have an animal，doesn't speak at all but a person can。

speak so that's added functionality to，the person and maybe a person can only。

say hello but then when we talk to a，student we can override the fact。

override the speak method of a person，and say that a student can say you know。

I have homework or I need sleep or，something like that okay so we have the。

same speak method for both person and，student because they can both speak but。

student will override the fact that they，say hello with something else okay。

so let's look at some code to put this，into perspective so we have this animal。

class which we've seen before this is，the parent class okay it inherits from。

object which means that everything that，a basic object can do in Python and an。

animal can do which is things like，binding variables you know very low。

level things okay we've seen the init，we've seen the two getters the setters。

and the string method to to print an，object of type of animal all right now。

let's create a subclass of animal we'll，call it cat okay we create a class named。

cat in parentheses instead of putting，object we now put animal and this tells。

python that cat is going cats parent，class is animal so everything that an。

animal can do a cat can do so that，includes all of the attributes which was。

age and name and all of the methods so，all the getters the setters the str the。

init everything that the animal had now，the cat has the cat class has in the cat。

class we're going to add two different，two more methods though they the first。

to speak so when so so speak is going to，be a method that's going to just take in。

the self okay no other parameters and，all it's doing is printing me out to the。

screen very simple okay so this through，the speak we've added new functionality。

to the to the class so an animal，additionally through this STR method。

here we're overriding the animal STR，okay so if we go back to the previous。

slide we can see that an animal the，animals STR had animal plus the name。

plus the age here whereas the cats STR，now says cat name and the age okay so。



![](img/240a848cb170b6031b7dbcf28d6b132b_175.png)

this is just how I chose to implement，this okay so here I've overridden the。

STR method of of the animal class，notice that this class doesn't have an。

in it and that's okay because pythons，actually going to say well if there's no。

in it in this particular method sorry in，this particular class then look to my。

parents and say do my parents happen in，it and if so use that in it so that's。

actually true for any other methods so，the idea here is when you have。

hierarchies you have a parent class you，have a child class you can have a child。

class that child class and so on and so，on so you can have multiple levels of。

inheritance what happens when you create，an object that is of type something。

that's that's been of a type that's the，this the child class of a child class of。

a child class right what happens when，you call a method on that object。

well python is going to say does the，method as a method with that name exist。

in my current class definition and if so，use that but if not then look to my。

parents do my parents know how to do，that right do my parents have a method。

for whatever I want to do if so use that。

![](img/240a848cb170b6031b7dbcf28d6b132b_177.png)

if not look to their parents and so on，and so on so it's you're sort of tracing。

back up your ancestry to figure out if，you can do this this method or not so。

let's look at a slightly more，complicated example we have a class。

named person it's going to inherit from，animal inside this person I'm going to。

create my own I'm going to create an，init method and the unit method is going。

to do something different than what the，animal's init method is doing it's going。

to take in self as usual and it's going，to take into parameters as opposed to。

one a name and an age first in the init，methods doing is its calling the animals。

init method why am i doing that well I，could theoretically initialize the the。

name and the age data attributes that，animal initializes in this method but。

I'm using the fact that I've already，written code that initializes those two。

data attributes so why not just use it，okay so here this says I'm going to call。

the class animal I'm going to call it，init method and I'm going to leave it up。



![](img/240a848cb170b6031b7dbcf28d6b132b_179.png)

to you - not you as the class but I'm，talking to as as program is running I'm。

going to leave it up to you to figure，out how to initialize an animal with。

with this particular age and what to，name it so Python says yep I know how to。

do this so I'm going to go ahead and do，that for you so now it says person is an。



![](img/240a848cb170b6031b7dbcf28d6b132b_181.png)

animal and I've initialized the age and，the name for you the next thing I'm。

doing in the unit is I'm going to set，the name to whatever name was passed in。

okay so when the init notice I can do，whatever I want including calling。

function calling methods and then the，last thing I'm doing here is I'm going。

to create a new data attribute for a，person which is a list of friends okay。

so an animal didn't have a list of，friends but a person is going to the。

next four methods here are this one's a，getter so it's going to return the list。

of friends this is going to append a，friend to the end of my list I'm making。

I want to make a note that I actually，didn't write a method to remove friends。

so once you get a friend they're friends，for life，but that's okay the next method here is。

speak which is going to print hello to，the screen and the last method here is。

going to get the age difference between，two people so that just basically。

subtracts their age and says it's a five，year age difference or whatever it is。

and down here I have an STR method which，I've overridden from the animal which。

instead of animal colon name it's going。

![](img/240a848cb170b6031b7dbcf28d6b132b_183.png)

so we can run this code，person here so I'm going to run this，code and what did i do I created a new。

person I gave it a name and an age I，created another person then name in an。

age and here I've just run some methods，on it which was get name get age get。

name get age for each of the two people，so that printed jack is thirty Jill is。

twenty five if I print p1 this is going，to use the STR method of person so it's。

going to print person ： their name and，then their age P 1 dot speaks just says。

hello and then the age difference，between p1 and p2 is just five so that's。

just subtracting and then telling。

![](img/240a848cb170b6031b7dbcf28d6b132b_185.png)

printing that up to the screen okay so，that's my person let's add another class。

this class is going to be a student and，it's going to be a subclass of person。

since it's a subclass of person it's，going to a student is going to inherit。



![](img/240a848cb170b6031b7dbcf28d6b132b_187.png)

all the attributes of a person and，therefore all the attributes of an。



![](img/240a848cb170b6031b7dbcf28d6b132b_189.png)

animal the init method of a student is，going to be a little different from the。

one of a person we're going to give it a，name an age and a major notice we're。

using default arguments here so if I，create a student without giving it a。

major the major is going to be set to。

![](img/240a848cb170b6031b7dbcf28d6b132b_191.png)

none originally once again this line，here person dot in it self name age。

tells python hey you didn't already know，how to initialize a person for me with。

this name in this age so can you just do。

![](img/240a848cb170b6031b7dbcf28d6b132b_193.png)

that and Python says yes I can do that。

![](img/240a848cb170b6031b7dbcf28d6b132b_195.png)

for you and so that saves you maybe like，five lines of code just by calling the。

init method that you've already written，through person okay，so student has been initialized to be a。

person and additionally we're going to，set another data attribute for the，student to be the major。

and we're going to set the major to be，nun the student is going to get this，Center here。

the setter method which is going to，change the major to whatever else they。



![](img/240a848cb170b6031b7dbcf28d6b132b_197.png)

want if they want to change it and then，I'm going to override the speak method。

so the speak method for the person，recall just said hello a student is。

going to be a little bit more complex，I'm going to use the fact that someone。

created this random class okay so this，is where we can write more interesting。



![](img/240a848cb170b6031b7dbcf28d6b132b_199.png)

code by using by reusing code that other，people have written so someone wrote a。

random class that can do cool things，with random numbers so if I want to use。

random numbers in my code I'm going to，put this import random at the top of my。

code which essentially brings in all of，the methods for the random class one of。

the methods being this random method so，random open closed parenthesis is random。

method from the random class and this，essentially gives me a number between 0。



![](img/240a848cb170b6031b7dbcf28d6b132b_201.png)

and 1 including 0 but not including 1 ok，so this random number I get here is。

going to help me write my method for，speak where it's going to with Quarter。

25 percent probability it's either going，to say I have homework I need sleep I。

should eat or I'm watching TV ok，so student is going to say one of those。

four things and the last thing I'm doing，down here is overriding the STR method。

so let's look at the code I'm going to，comment this part out and uncomment the。

student and see what we get ok so here I，am creating the student I'm creating one。

student whose major is yes name is Alice，and ages 20s 2 is going to be another。

student named Beth age 18 and the major，is going to be none because I didn't。

pass in any major here so by default，using the default argument it's going to。

be none if I print s1 as 2 that's going，to print out these 2 things over here。

and then I'm going to get the students，to speak and if I run it multiple times。

you can see that it's going to print，different things each time so I need。

sleep I have homework I need sleep I。

![](img/240a848cb170b6031b7dbcf28d6b132b_203.png)

have homework yeah so every time it's，going to print something different okay。

okay last thing we're going to talk，about in this class is an idea of or in。

this lecture is the idea of a class，variable so to illustrate this I'm going。

to create yet another subclass of my，animal called a rabbit so class。

variables so so far we've seen sorry let，me back up so so far we've seen instance。

variables right so things like self dot，name self dot age those are all instance。

variables so they're variables that are，specific there are common across all of。

the instances of the class right every，instance of the class has this。

particular variable but the value of the，variable is going to be different。



![](img/240a848cb170b6031b7dbcf28d6b132b_205.png)

between all of the different instances，so class variables are going to be。

variables whose value is whose values，are shared between all of the instances。

in the class so if if one instance of，the class modifies this class variable。

that any other instance of the class is，going to see the modified value so it's。

sort of shared among all of the。

![](img/240a848cb170b6031b7dbcf28d6b132b_207.png)

different instances so we're going to，use class variables to keep track of。



![](img/240a848cb170b6031b7dbcf28d6b132b_209.png)

rabbits，okay so we're creating this class rabbit，tag is equal to one we haven't seen。

something like this before so tag is our，class variable class variables are。

typically defined inside the class，definition but right but outside of the。



![](img/240a848cb170b6031b7dbcf28d6b132b_211.png)

init so tag is going to be a class，inside the in it this tells us how to。

create a rabbit object so I'm going to，give itself as usual an age and then two。

parents don't worry about the two，parents for now inside the in it sorry。

inside the in it I'm going to call the，init of the animal because just to do。

less work Python already knows how to。

![](img/240a848cb170b6031b7dbcf28d6b132b_213.png)

initialize an animal for me so let's do，that so that's going to set the two data。

attributes name and age I'm going to set，the data attributes for parent one。

parent two for a rabbit to be whatever，is passed in and then this is where I'm。

going to use this class variable so I'm，creating this data attribute instance。

variable particular to a specific，instance called our ID okay and I'm。

assigning this this instance variable to，the class variable and I access class。

variables using not self but the class，name so in this case rabbit tag so。

initially tag is going to be 1 and then，the init is going to increment the tag。

by 1 here okay so that means that from，now on if I create any other instances。

the other instances are going to be，accessing the updated value of tag。

instead of being one so let's do a quick，drawing to show you what I mean so let's。

so initially tag is going to be one okay，and then I'm going to create a new。

rabbit object so this is as I'm calling，the code okay so let's say this is a。

rabbit object oh boy okay，r1 you know I actually googled how to。

draw a rabbit but that didn't help at，all okay so r1 is going to be a new。

rabbit that we create initially what，happens is when I first create this new。

rabbit it's going to access the class，variable which is current value is。

one so when I create the rabbit ID the，rabbit ID R 1 dot R ID this is going to。

get the value 1 and according to the，code after I set the rabbit ID to。

whatever tag is I'm going to increment，the tag so this is going to say okay now。

that I've said it I'm going to go back，up here and increment the tag to be 2。

okay let's say I create another rabbit，object okay all right there that's the。

sad rabbit R to the ID of R 2 is going，to be what well according to the way we。

inst the way we create a new rabbit，object is it's going to access whatever。

the value of tag is which is a class，variable it was changed by the previous。

creation of my rabbit so now I'm going，to access that right so the value is。

going to be 2 and according to the code，the next thing I do after I create after。

I create the instance our ID is I'm，going to increment tag so I'm。

incrementing the class variable to be 3，so notice that all of my instances are。



![](img/240a848cb170b6031b7dbcf28d6b132b_215.png)

accessing this shared sort of the shared，sort of resource the shared variable。

called tag so as I'm creating more and，more rabbits they're all going to be。

incrementing the value of tag because，it's shared among all of the instances。

and so the so this value this this tag，class variable sort keeps track of how。

many different instances of a wrap of，how many different instances of rabbits。

I've created throughout my entire，program so the big idea here is that。



![](img/240a848cb170b6031b7dbcf28d6b132b_217.png)

class variables are shared across all，the instances so they can all modify。

them but these are IDs right these，instance variables are only are only for。

that particular instance so R 2 can't，have access to our IDs our ones ID value。

nor could change it but it won't change，so so that's that's how the init method。

works of rabbit okay so we have these，tags that keep track of how many rabbits。

we've created we have a couple of get we，have some getters here to get all the。

parents so now let's add a somewhat more，interesting function oh I just want to。

mention when I'm getting the r ID I'm，actually using this cool Z fill function，here。

which actually pads the beginning of any，number with however many zeros in order。

to get to that number here so the number，one becomes zero zero one and so on so。

it ensures that I have this nice-looking。

![](img/240a848cb170b6031b7dbcf28d6b132b_219.png)

sort of ID type thing that's always，three digits long so let's try to work。

with this rabbit object let's define，what happens when you add two rabbits。

together okay in this class not in the。

![](img/240a848cb170b6031b7dbcf28d6b132b_221.png)

real world okay so if I want to use the，plus operator between two rabbit。

instances I have to Inc implement this，underscore underscore add underscore。

underscore method so all I'm doing here，is I'm returning a new rabbit object。

okay whoops sorry about that and let's，recall the init method of the rabbit。

okay so when I'm returning a new rabbit，object I'm returning a new rabbit object。

that's going to have an age of zero self，so the rabbit object I'm calling this。

method on is going to be the parent of，the new OP of the new rabbit and other。

is going to be the other parent of the。

![](img/240a848cb170b6031b7dbcf28d6b132b_223.png)

new rabbit okay so if we look at the。

![](img/240a848cb170b6031b7dbcf28d6b132b_225.png)

this part here I'm creating three，rabbits r1 r2 and r3 notice this class。

variable is is working as expected，because the IDS of each of my rabbits。

increments as I create more rabbits so，we have zero zero one zero zero two zero。

zero three if I print r1 and r2 and r3，that was these three lines over here the。

parents of r1 and r2 are none because，that's just the default the default。

argue but yes the default arguments for，creating a rabbit to add two rabbits。

together I use the plus operator between，two rabbit objects and on the right here。

I'm testing rabbit addition and I can，print out the the IDs of all my rabbits。

and notice that when I've created this，new rabbit R for the idea of it still。

kept incrementing so now the idea of the，fourth rabbit is double double of four。

and then when I get our forced parents，they are as as we want them to be so r1。



![](img/240a848cb170b6031b7dbcf28d6b132b_227.png)

in our to the other thing I want to do，is to compare two rabbits so if I want。

to compare two rabbits I want to make，sure that their parents are the same so。

I can compare the parent of the first，parent of the first rabbit with the。

first pair of the second rabbit and the，first parent of the second parent of the。

first rabbit to the first second parent。

![](img/240a848cb170b6031b7dbcf28d6b132b_229.png)

of second rabbit or getting the，combinations of those two so that's what。

these are these two boolean's are doing，so these are going to tell me these are。

going to be boolean values either true，or false and I'm going to return either。

way they have the same parents of that，type or the same parents criss-crossed。

okay so here notice that I'm actually。

![](img/240a848cb170b6031b7dbcf28d6b132b_231.png)

comparing the IDS of the rabbits as，opposed to the rabbit objects directly。

okay so if instead of doing instead of，comparing the IDS in here I was。

comparing the parents themselves，directly what would end up happening is。

this function this method EQ would get，called over and over again because here。

we have parents that are rabbits and at，some point the parents of the very very。

first rabbits ever created by this。

![](img/240a848cb170b6031b7dbcf28d6b132b_233.png)

program are none，and so when I try to call when I try to，call the parent one of none that's going。

to give me an error okay something like，an attribute error where it doesn't nun。



![](img/240a848cb170b6031b7dbcf28d6b132b_235.png)

doesn't have a this parent attribute so，that's why I'm comparing IDs here okay。

and the code in the lecture here shows，you some tests about whether rabbits。

have the same parents and I've created，new rabbits here r3 and r4 the addition。

of those two and our five and our six。

![](img/240a848cb170b6031b7dbcf28d6b132b_237.png)

are going to have the same parents down，here true but our foreign our six don't。

okay so just to wrap it up，object-oriented programming is the idea，of correcting creating your own。

collections of data where you can，organize the information in a very。

consistent manner so every single type，of object that you creative of this。

particular type that you create sorry，every object instance of a particular。

type is going to have the exact same，data attributes and the exact same。

methods okay so this really comes back，to the idea of decomposition and。

abstraction in programming all right。

![](img/240a848cb170b6031b7dbcf28d6b132b_239.png)

![](img/240a848cb170b6031b7dbcf28d6b132b_240.png)