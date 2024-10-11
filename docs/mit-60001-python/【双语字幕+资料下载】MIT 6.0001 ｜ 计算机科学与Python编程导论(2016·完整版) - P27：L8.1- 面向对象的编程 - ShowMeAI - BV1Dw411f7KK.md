# 【双语字幕+资料下载】MIT 6.0001 ｜ 计算机科学与Python编程导论(2016·完整版) - P27：L8.1- 面向对象的编程 - ShowMeAI - BV1Dw411f7KK

![](img/c047e8807cc5ce0daca4ea1054f34ab3_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_2.png)

![](img/c047e8807cc5ce0daca4ea1054f34ab3_3.png)

all right everyone let's get started so。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_5.png)

today's lecture and Wednesdays lecture，we're going to talk about these this。

thing called object-oriented programming，and if you haven't programmed before I。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_7.png)

think this is a fairly tough concept to，grasp but hopefully with with many many。

examples and just by looking at the code，from available F from the lectures。

you'll hopefully get the hang of it，quickly so let's talk a little bit about。

objects and we've seen objects in Python，so far objects are basically data in。

Python so every object that we've seen，has a certain type okay that we know。

behind the scenes though every object，has these two additional things one is。

some data representation so how Python，represents the object in just behind the。

scenes and what are different ways that。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_9.png)

you can interact with the object okay so，for example every one of these is a。

different object for example this is the，number 1234 it's a specific object that。

is of type integer the number 5 is a，different object that's of type integer。

and so on we've seen floats we've seen。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_11.png)

strings we've seen lists lists and，dictionaries are more complicated object。

object types sorry but every object has，a type some sort of way that it's。

represented in Python and some ways that，we can interact with them ok so the idea。

behind object-oriented programming is，first of all everything in Python is an。

object we've said that before and in，this lecture I think we'll really get at，what that means。

so we've seen strings integers，dictionaries lists those are all objects。

when we did functions we saw that we，could pass as a parameter another。

function so functions were also objects，in Python so literally everything in up。

in Python is an object so what are the。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_13.png)

kinds of things we can do with objects，well once you have a type you can create。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_15.png)

a new object that is of some type and，you can create as many，object as you'd like of that particular。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_17.png)

type right an integer five an integer，seven those all work in a program once。

you have these once you've created these，new objects you can manipulate them so。

for a list for example you can append an，item to the end of the list you can。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_19.png)

delete an item remove it concatenate two，lists together。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_21.png)

so that's ways that you can interact，with objects and the last thing you can。

do is you can destroy them so in with，lists we saw explicitly that you can。

delete elements from a list or you can。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_23.png)

just forget about them by sort of，reassigning a variable to another value。

and then at some point Python will will，collect all of these dead objects and。

reclaim the memory so let's continue。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_25.png)

exploring what objects are so let's say，I have these two separate objects one is。

a blue car one is a pink car so objects，are really data abstractions so these。

two cars can be created by the same，blueprint okay this is a blueprint for a。

car and if an object is the data，abstraction there's two things that this。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_27.png)

abstraction is going to capture the，first is some sort of representation。

what is going to represent the car what，data represents a car object and the。

second is what are ways that we can，interact with the object so if we think。

about a car blueprint some general，representation for a car could be the。

number of wheels it has the number of，doors it has maybe its length maybe its。

height so this is these are all this is，all part of what data represents the car。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_29.png)

okay the interface for the car is what，are ways that you can interact with it。

so for example you could paint a car，right so you could change its color you。

could make you could have the car make a，noise and different cars might make。

different noises or you can drive the，car right so these are all ways that you。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_31.png)

can interact with a car whereas the，representation are what makes up the car。

what abstraction data abstractions make，let's bring it a little closer to home。

by looking at a list so we have this。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_33.png)

data type of list right we've worked，with lists before the list with elements。

1 2 3 and 4 is a very specific object。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_35.png)

that is of type list okay again we think，about it in terms of two things one is。

how what is the data representation of a，list so how does behind the scenes how。

does Python see lists and the second is，how do you interact with lists so what。

are ways that you can manipulate a list。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_37.png)

object once it's created so behind the，scenes you have a list L which is going。

to be made up of essentially two things，one is going to be the value at specific。

index okay so at index 0 it has the，value 1 right because it's the first。

element in the list and the second thing，that represents a list is going to be。

this second part which is a pointer and，internally this pointer is going to tell。

Python where is the memory location in，the computer where you can access the。

element and index 1 so that's it's just。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_39.png)

essentially going to be a chain going，from one index to the other and at the。

next memory location you have the value，at index 1 and then you have another。

pointer that takes you to the location，memory where the index 2 is located and。

then index 2 you have the value and then，the next pointer and so on and so on。

so this is how Python internally。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_41.png)

internally represents a list ok how you，manipulate lists we've done this a lot。

right you can get you can index into a，list you can add two lists together you。

can get the length you can append to the，end of a list you can sort a list。

reverse' lists and so many other things，right so these are all ways that you can。

interact with the list object as soon as，you've created it so notice both of。

these the internal representation and，how you manipulate lists you don't。

actually know internally how these are。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_43.png)

represented right how did how did how，did whoever wrote the list class decide。

to implement a sort we don't know ok you，also weren't aware，of how these lists were represented。

internally and you didn't need to know，that that's the beauty of。

object-oriented programming and having，these data abstractions the。

representations are private of these，objects and they're only known by what。

you can find out how it's done but they，only should be known by whoever。

implemented them you as someone who uses，this class doesn't really need to know。

how a list is represented internally in，order to be able to use it and to write。

cool programs with them okay so so just，final motivation here before we start。

writing our own types of objects is the，advantages of object-oriented。

programming is really that you're able，to bundle this data bundle some internal。

representation and some ways to interact，with a program into these packages these。

packages with these packages you can，create objects and all of these objects。

are going to behave the exact same way，they're going to have the same internal。

representation and the same way that you，can interact with them okay and。

ultimately this is going to contribute，to the decomposition and abstraction。

ideas that we that we talked about when，we talked about functions and that means。

that you're going to be able to write，code that's a lot more reusable and a。

lot easier to read in the future okay so，just like when we talked about functions。

we're going to sort of separate the code，that we talked about today into code。

where you implement you implement a data，type and code where you use use an。

object that you create okay so remember，when we talked about functions you had。

you had you were thinking about it in，terms of writing a function so you had。

to worry about the details of how you，implement a function and then you had to。

worry about just how to use a function，right so it's sort of the same idea。

today so when you're thinking about，implementing your own datatype you do。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_45.png)

that with this thing called a class okay，and when you create a class you're。

basically going to figure out what name，you want to give your class and you're。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_47.png)

going to define some attributes and，attributes are going to be the data。

representation and ways that you can，interact with your object so you as the。

programmer of this class are going to，decide how you want people to interact。

with your object and what this object，what what data this object is going to。

take have so for example someone wrote，code that implements a list class and we。

don't actually know how that was done，but we can find out so creating the。

class is is is implementing implementing，the class and figuring out data。

representation and ways to interact with，the class once that's done you can then。

use your class and you use the class by，creating new instances of of the class。

so when you create a new instance you。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_49.png)

essentially create a new object that has，the type the name of your class and you。

can create as many objects as you'd like，you can do all the operations that。

you've defined on the class so for，example someone wrote the code to。

implement list class and then you can，just use the list class like this so you。

can create a new list you can get the。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_51.png)

length of the list you can append to the，okay so let's start defining our own。

types okay so now you're going to define，classes you're going to write classes。

which are going to define your own types，of objects so for today's lecture we're。

going to define we're going to look at，code that's going to be in the context。

of a coordinate object okay and a，coordinate object is essentially going。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_53.png)

to be an object that's going to define a，point in an XY plane okay so X comma Y。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_55.png)

is going to be a coordinate in a 2d，plane so we're going to write code。

that's going to allow us to define that，kind of object so the way we do that is。

we have to define a class so we have to，tell Python hey I'm defining my own。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_57.png)

object type so you do that with this，class keyword so you say class then you。

say the name of your type in this case，we're creating a type called coordinate。

just like we had type list type string，and so on this is going to be a type。

called coordinate and then in，parentheses here you put what the，parents of the class are for today's。

lecture the parent of the classes are，going to be this thing called object an。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_59.png)

object is the very basic type in Python，it is the most basic type in Python and。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_61.png)

it it implements things like being able，to assign variables so really really。

basic operations that you can do with，objects okay so your coordinate is。

therefore going to be an object in。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_63.png)

Python all right so we've told python we，want to define an object so inside the。

class definition we're going to put。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_65.png)

attributes so what are attributes，attributes are going to be data and。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_67.png)

procedures that belong to the class okay，data are going to be the data。

representations and procedures are going，to be ways that we can interact with the。

object okay the fact that they belong to，the class means that the data and the。

procedures that we write are only going。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_69.png)

to work with an object of this type okay，if you try to use any of the data or the。

procedures with an object of a different，type you're going to get an error。

because these objects these this data，and these these attributes sorry will。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_71.png)

will belong to this particular class，okay so the data attributes is what is。

the object right what is the data that，makes up the object so for our。

coordinate example it's going to be the。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_73.png)

X and y values for a coordinate we can，decide that can be in so we can decide。

that we can let them be floats but it's，going to have one one value for an for。

the x coordinate and one value for the y，coordinate so those are data attributes。

and procedure attributes are better，known as methods and you can think of a。

method as a function except that it's a，function that only were。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_75.png)

with this particular type of object so，with a coordinate object in this case。

okay so the methods are going to define，how you can interact with the object so。

in a list for example we've said that，you can append an item to the end of the。

list we can sort of list things like，that so when you when you're defining。

methods you're defining ways that people，can interact with your object so for。

example for a coordinated object we can，say that we can take the distance。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_77.png)

between two coordinate points okay and，that's going to be a way that you can。

interact with two coordinate points and，we and just just to be clear these are。

going to belong to this class which，means that if you try to use this。

distance method on two lists for example，you're going to get an error because。

this distance method was only defined to，work with to coordinate type objects all。

right so let's carry on and continue，implementing our class so we've written。

this first line so far class coordinate，object so now let's define attributes。

first thing we're going to define our。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_79.png)

data attributes generally you define，data attributes inside this in it and。

this is underscore underscore init，underscore underscore and it's a special。

method or function in a class and the，special method tells Python when you。

when you implement the special method it，tells Python when you first create an。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_81.png)

object of this type call this method or。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_83.png)

call this function so how do we do that，so let's implement it so you say def。

because d f because it's just a function，the name is the special name in it and。

we give it some parameters right just，like any other function，these last two parameters are x and y。

which are going to represent the x it's，going to represent how you create a。

coordinate object so you give it a value，for the exponent and you give it a value。

for the y-coordinate this self however，is a little bit trickier so the self is。

going to be a parameter when you define，this class that represents a particular，instance of。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_85.png)

of the class okay so we're defining this，coordinate object in sort of a general。

way right we don't have a specific，instance yet because we haven't created。

an object yet but this self is going to，be sort of a placeholder for any sort of。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_87.png)

instance when you create the object so，in the definition of the class whenever。

you want to refer to attributes that，belong to an instance you have to use。

self dot so this dot notation and the，dot is going to say look for a value X。

sorry look for a data attribute X that。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_89.png)

belongs to this class so for methods，that belong to the class the first。

parameter is always going to be self it，could be named anything you want but。

really by convention it's always named，self so try to stick to that and then。

any other parameters beyond it are going，to be just parameters as you would put。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_91.png)

in a normal function okay in this，particular case we're going to choose to。

initialize a data a coordinate object by，two values one for the X and 1 for the Y。

and inside this init method we're groups，we're going to have two assignments the。

first one says the X data attribute of a，coordinate object I'm going to I'm going。

to assign it to whatever was passed in，and the Y data attribute for a。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_93.png)

particular object is going to be，questions so far about how to write this。

in it yeah question how do you make sure，that x and y are intz or floats so this。

is something that you could write in the，specification so the doc string with the。

triple quotes so whoever uses the，function uses the class would then know。

that if they do something outside the，specification the code might not work as。

expected or you could put in a search，statement inside the the definition of。

the in it just to sort of force that，force that to to be true great question。

yeah question does the X does this self，X and this X have to be the same name。

the answer is no and we're going to see，in the class exercise that you can have。

it to be different okay great so this，defines our the way that we create an。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_95.png)

object so now let's now we have sort of，a nice nice class it's very simple but。

we can start actually creating，coordinate objects okay so when you。

create a coordinate objects you're，creating instances of the class so this。

line here si is equal to coordinate 3 4。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_97.png)

is going to call the init method it's，going to call the init method with X is。

equal to 3 and Y is equal to 4 I'm just，going to go over here and I wrote this。

previously because notice when we're，calling this method when we're creating。

an object here we're only giving it two。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_99.png)

parameters but in the init method we，have actually three parameters right we。

have these three parameters here but，when we're creating an object we only。

give it two parameters and that's okay，because implicitly python is going to。

say self is going to be this object see，so just by default okay so when you're。

creating a coordinate object you're，you're passing it the very all the。

so this line here is going to call the，init and it's going to do every line。

inside the unit so it's going to create，an X data attribute for see a Y data。

attribute for C and it's going to assign，three and four to those respectively。

this next line here is origin equals，coordinate zero zero creates another，object okay。

it's another coordinate object whose，value of 4x is zero and whose value for。

y is zero okay so now we have to。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_101.png)

coordinate objects we can access the，data attributes using this dot notation。

and we've seen that before right when，we've worked with lists we'd say。

something like L dot append right when，we create a list so the same dot。

notation can be used with your own。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_103.png)

objects in order to access data，attributes so here this is going to。

print three because the x value for for，object C is three and the next line。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_105.png)

print Origin X is going to print zero，because the x value for the object。

origin is zero okay so we've created，we've created a coordinate object we've。

defined the init method so we have a way，to create objects when we use the class。

and then we can access the data，attributes but that's kind of lame right。

because there isn't anything cool we can，do with it there isn't ways to interact。

with this object so let's add some，methods okay remember methods are going。

to be are going to be procedural，attributes that allow us to interact。

with our object okay methods are like，functions except that there's a couple。

differences which you'll see in a moment，and when you're when you're calling。

methods you're using the dot the dot，operator like L dot append for example。

for lists so let's define now let's go。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_107.png)

back to defining our coordinate class，and let's define a method for it so so。

far we've defined that part their class，coordinate and an init so we have that。

so in this slide we're going to add，this method here so this method here is。

going to say I'm going to define a，method called distance and I'm going to，pass in two parameters。

remember self the first parameter is，always going to be the the instance of。

an object that you're going to perform，the operation on so alway pretty much by。

convention it's always named self and，this KNN for this particular method I'm。

going to give it another parameter and I，can name this whatever I want I'm naming。

it other and this is going to represent，the other coordinate object for which I。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_109.png)

want to find the distance from myself，okay so here I'm going to just implement。

the Euclidean distance formula which is，X you know x1 minus x2 squared plus y1。

minus y2 squared and square root of all，that so that's what I'm doing inside。

here okay self and other are coordinate，objects inside this method I have to。

refer to the X data attributes of each，object if I want to find the difference。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_111.png)

between the two x values from them so，that's why I'm doing self dot X here。

right if I just did X I would be，accessing just some variable named X in。

in a program which actually isn't even，defined right so you always have to。

refer when you're talking about when，when you're when you're as we're。

thinking about classes you always have，to refer to whose data attribute do you。

want to access okay in this case I want，to access the X data attribute of myself。

and I want to subtract the X data，attribute of this other coordinate。

square that same for Y square that and，then add those and take the square root。

of that so notice this method is pretty，much like a function right you have DF。

some name it takes in parameters it does，some stuff and then it returns a value。

the only difference is the fact that you，have a self here as the first thing and。

the fact that you always have to be，conscious about whose data attributes。

okay so you have to use the dot notation。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_113.png)

in order to decide whose data attributes，you want access so we've defined the。

method here distance okay so this is in，the class definition now how do we use。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_115.png)

it so let's assume that the the，definition of distance is up here I。

didn't include the code but really all，you need to know is what it takes it。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_117.png)

takes itself and another so when you，want to use this method to figure out a。

distance between two coordinate objects，this is how you do it so the first line。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_119.png)

I create one coordinate object second，line I create another coordinate object。

right first one is named C the second，one is named zero these are two separate。

objects and I'm going to find the，distance and I want to first call it on。

one object so I'm going to say C dot so，I'm using the dot notation to call the。

method distance on object C so Python，says this object C is of type coordinate。

it's going to look up at the class，coordinate that you defined it's going。

to find this method called distance and，then it's going to say what parameters。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_121.png)

does it take so it takes another，parameter right for the other and then。

in the parenthesis I just have to give，it this other parameter an easier way to。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_123.png)

see what happens is by looking at what，this line here is equivalent to okay so。

this let the third line here print C，distance 0 is equivalent to this one on。

the right and this one on the right，essentially says what's the name of the。

class dot dot notation what's the method，you want to call and then in parenthesis。

you give it all of the variables，including self okay so in this case。

you're explicitly telling Python that，self is C and other is 0 right so this。

is a little bit easier to understand。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_125.png)

like that，but it's a little cumbersome because you，always have to write coordinate dot。

coordinate dot coordinate for every data，attribute you might want to access for。

every procedural attribute you want，might want to access so it's really so。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_127.png)

by convention it's a lot easier to do，the one on the left and as I mentioned。

Python implicitly says if you're doing，the one on the left you can call this。

method on a particular object and it's，going to look up the type of the object。

and it's going to essentially convert，this on the left to the one on the right。

ok and this is what you've been using so，far so when you create a list you say L。

is equal to one two and then you say L，dot append you know three or whatever so。

we've been using this notation on the。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_129.png)

left pretty much from from the beginning，class so we have a coordinate class we。

can create a coordinate object we can，get the distance between two objects as。

you're using the class if you wanted to，use this coordinate class and you were。

maybe debugging at some point you know a。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_131.png)

lot of you probably use print as a debug，statement right and maybe you want to。

print the value of of a coordinate，object so if you create a coordinate。

object C is equal to coordinate 3/4，right that's what we've done so far if。

you print C you get this sorry you get，this funny message very uninformative。

right it basically says well C is an，object of type coordinate at this memory。

location in in in the computer which is，not what you wanted at all right maybe。

you wanted to know what the values for x，and y were that would be a lot more。

informative okay so so by default when，you create an on your own type when you。

print the type when you print the object，of that type Python tells you this sort。

of information which is not what you，want so what you need to do is you need。

to define your own method that tells。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_133.png)

Python what to do when you call print on，an object of this type so this is going。

to be a special method，just like in it is because it starts and。

ends with double underscores and the the，name of the method is underscore。

underscore STR underscore underscore and，if you define this method in your class。

that tells Python hey when you see a，print statement that's on an object of。

type coordinate call this method look，what it does and do everything that's。

inside it okay and you can choose，whatever you you can choose to make it。

do whatever you want inside your your。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_135.png)

definition of STR in this case let's say，when we print a coordinate object we're。

going to print it's x and y values，surrounded by angle brackets that seems。

reasonable right so then from now on，when you when you print coordinate。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_137.png)

objects you're going to see things like，this which is a lot more informative all。

right so how do we define this so so far。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_139.png)

we've defined all that and the last part。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_141.png)

is going to be new okay so we define the，anit and the distance and let's define。

this STR so underscore underscore STR，underscore underscore is a method it's。

only going to taste take self because，you're just calling print on the object。

itself okay there's no other are there's，no other parameters to it STR has to。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_143.png)

return a string and in this particular，case we're going to return the string。

that's the angle brackets concatenated，with the x-value of the object self x。

concatenated with a comma concatenated，with the y value of this particular。

instance of an object self dot y and。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_145.png)

then concatenated with the angle，brackets so now anytime you have print。

on an object of type coordinate you're，going to call this special method STR if。

it's implemented in your in your code。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_147.png)

okay so let's try to wrap our hand，around types and classes because we've，seen a lot today okay。

let's create a coordinate object assign，it three four as we have been and assign。

it to variable C we've implemented the，STR method so when we print C it's going。

to print out this nice three comma four，in angle brackets if we print the type。

of C this is actually going to give us，class Maine coordinate which tells us。

that C is going to be an object that's，of that that's that is sorry C is going。

to be an object that is of type class。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_149.png)

![](img/c047e8807cc5ce0daca4ea1054f34ab3_150.png)

coordinate if we look at coordinate as a，class if we print what coordinate is。

coordinate is a class right so this is，what python tells us if we print。

coordinate it's a class named coordinate，and if we print the type of a coordinate。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_152.png)

well that's just going to be a type so，class is going to be a type so you're。

defining the type of an object okay if，you'd like to figure out the type the if。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_154.png)

you'd like to figure out whether a，particular object is an instance of a。

particular class you use this special，function called is instance so if you。

print is instance C comma coordinate，this is going to print true because C is。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_156.png)

couple more words on these special。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_158.png)

operators so these special operators，allow you to customize your classes。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_160.png)

which can add some cool functionality to。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_162.png)

them so these special operators are，going to be things like addition。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_164.png)

subtraction using the equal equal sign，greater than less than length and so on，and so on。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_166.png)

so just like STR if you implement any of，these in your classes this is going to。

tell Python so for example if we've，implemented this underscore underscore。

add underscore underscore in our in our，class this is going to tell Python when。

you use this plus operator between two。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_168.png)

objects of type coordinate to call this，method if you have not implemented this。

method and you try to add two objects of，type coordinate you're going to get an。

error because python doesn't actually，know right off the bat how to add to。

coordinate objects right you have to，tell it how to do that and you tell it。

how to do that by implementing this，special special method，same with subtract same with equal so if。

you want to figure out whether two，objects are equal and when you implement。

these methods in your in your own class。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_170.png)

you can decide exactly what you want to，do so what happens when you add to。

coordinate objects you just add the X，values you just add the Y values do you。

add them both together do you do，whatever you'd like to do and then you。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_172.png)

document what you've decided so let's，create a fraction object okay so we've。

looked at a coordinate we've saw sort of，a higher level car object let's look at。

a fraction object fraction object is，going to be is going to represent a。

number that's going to be a numerator。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_174.png)

/ a denominator okay，so that's going to be a fraction object，so the way I've decided to internally。

represent a fraction object is with two，numbers and I've decided that I will not，integers。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_176.png)

so inside the anit I've decided I'm，going to represent the two numbers with。

sorry I'm going to represent my fraction，with two numbers one for the numerator。

and one for the denominator so when I，create a fraction object I'm going to。

pass in a numerator and a denominator，and a particular instance is going to。

have self numerator and self denominator，as its data attributes and I'm assigning。

those to be whatever's passed into my in，it since I plan on debugging this this。

code maybe possibly sometime in the，future I'm also including an STR method。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_178.png)

and the STR method is going to print a，nice you know a nice-looking a string。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_180.png)

that's going to represent the numerator，and then a slash and then the，denominator and then I've also。

implemented some other special methods，how do I add two fractions how do I。

subtract two FLAC fractions and how do I，convert a fraction to a float okay the。

add and subtract are almost the same so，let's look at the add for the moment how。

do we add two fractions right we're，going to take self which is the which is。

the instance of an object that I want to，do the add operation on and we're going。

to take other which is the other，instance of an object that I want to do。

the operation on so the addition and I'm，going to figure out the new top so the。

new top of the of the resulting fraction，so it's the it's my numerator multiplied。

by the other denominator plus my，denominator multiplied by the other。

numerator and then divided by the，multiplication of the two denominators。

so the top is going to be that the，bottom is going to be that notice that。

we're using self dot right once again，we're trying to access the data。

attributes of each different instance，right of myself and the other object，that I'm working with。

so that's why I have to do self dot here，once I figure out the top and the bottom。

of the Edition I'm going to return and，here notice I'm returning a fraction。

object okay it's not a number it's not a，float it's not an integer it's a new。

object that is of the exact same type as，the class that I'm implementing okay so。

as as it's the same type of object then，on the return value I can do all of the。

exact same operations that I can do on a，regular fraction object okay sub is。

going to be the same I'm returning a，fraction object float is just going to。

do the division for me so it's going to，take the numerator and then divide it by。

the denominator just just divide the，numbers and then I'm divide defining。

here my own function my own method，called inverse and this is just going to。

take the inverse of the instance I'm，calling this method on and so it's going。

to also return a new fraction object，that just has the denominator as the top。

part and the numerator as the bottom，part so then we have some code here so。

that's how that's how I implement my，fraction object so now let's use it and。

see what it gives us a is equal to，this is going to be one over for for a。

when I do C notice I'm using the plus，operator between two fraction objects。

right and B are fraction objects so，Python is going to say okay is there an。

underscore underscore ad underscore，underscore method implemented it is and。

it's just going to do whatever is inside，here so it's going to say self done。

numerator plus other denominator it's，going to calculate the top and the。

bottom it's going to turn a new fraction，object so this is going to be 4 plus 4。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_182.png)

four plus 12 divided by 16 okay and 16，over 16 so see as a fraction object is。

going to be 16 for the numerator and 16。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_184.png)

for the denominator right because it's a，fraction object if I print C it should。

print 16 over 16 so we can even run it，so it prints 16 over 16 if I print float。

C so this special method float here is，going to say is there a method that。

converts a fraction to a float and there，is it's this one implemented right here。

so it's just going to divide the two，numbers top and bottom which gives me 1。

so it's this one here and here notice，I'm calling I'm doing the exact same。

method call except I'm doing it the，other way where you type in the name of。

the method the name of the class name of，the method and then what you're calling。

it on and this gives the exact same，value here 1。0 and then here i'm calling。

the method inverse on object b which is，going to invert 3 over 4 to be 4 over 3。

and then i'm converting it to a float。

![](img/c047e8807cc5ce0daca4ea1054f34ab3_186.png)

and then i'm printing the value so it，gives me 1 point 3 3 so take a look at。

this take a look at this code in more，detail and and see if you can trace。

through all of those different things，and see if you can also write your own。

new fraction objects ok so last slide，power of object-oriented programming is。

that you can bundle together objects，that have the exact same type and all of。

these objects you know are going to have，the same data representation and the。

same methods that you can do on them and，ultimately you're going to be building。

these layers of abstractions you're，going to be building on a basic object。

type in Python you're going to be you're，going to have integer objects float。

objects on top of those you can create，lists dictionaries and on top of those。

you can even create your own object，types as we saw in your。



![](img/c047e8807cc5ce0daca4ea1054f34ab3_188.png)

![](img/c047e8807cc5ce0daca4ea1054f34ab3_189.png)