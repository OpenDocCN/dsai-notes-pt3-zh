# P5：L2.1- 分支与循环 - ShowMeAI - BV1Dw411f7KK

![](img/4964a17e81ae8c50118bdf883d5d6985_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/4964a17e81ae8c50118bdf883d5d6985_2.png)

![](img/4964a17e81ae8c50118bdf883d5d6985_3.png)

alright let's get started everyone so，good afternoon welcome to the second。



![](img/4964a17e81ae8c50118bdf883d5d6985_5.png)

lecture of six triple zero one and also，of 600 so as always if you'd like to。

follow along with the lecture with the，lectures please go ahead and download。

the slides and the code that that I'll。

![](img/4964a17e81ae8c50118bdf883d5d6985_7.png)

provide at least an hour before class，every day alright so quick recap of what。

we did last time so last time we talked，a little bit about what a computer is。



![](img/4964a17e81ae8c50118bdf883d5d6985_9.png)

and I think the main takeaway from the，last lecture is really that a computer。

only does what it is told right so it's，not going to spontaneously spontaneously。

make decisions on its own you as the，programmer have to tell it what you want。

it to do by writing programs okay so we，talked about simple objects and these。

objects were of different types so we，saw integers floats and boolean's and。

then we did a couple of simple，operations with them today we're going。

to look at a different a new a new type，of object called a string and then we're。

things in our programming toolbox so，we're going to look at how to how to。

branch within a program and how to make，things how to make the computer repeat。

certain tasks within our program all，right so let's begin by looking at。

strings so strings are a new object type，we've seen so far integers which were。

whole numbers floats which were decimal，numbers and we have seen we've see。



![](img/4964a17e81ae8c50118bdf883d5d6985_11.png)

billions which were true and false，so strings are going to be sequences of。

characters and these characters can be，anything they could be letters digits。

special characters and also spaces and，you tell Python that you're you're。

talking about a string object by，enclosing it in quotation marks so in。

this case I'm creating an object whose，value is h-e-l-l-o space th er E and。

Python knows it's a string object，because we're enclosing it in quotations。

they could be either double quotes or，single quotes but as long as you're。



![](img/4964a17e81ae8c50118bdf883d5d6985_13.png)

consistent it doesn't matter，and this object worse where we're。

binding it to this variable named hi and，we're using that using the equal sign。

which is the assignment operator okay so，from now on whenever we refer to this。

variable hi python is going to say oh i，know what the value is and it's that。

string of characters so we're going to，learn about two things that you can do。



![](img/4964a17e81ae8c50118bdf883d5d6985_15.png)

on strings today two operations one is，to concatenate them and concatenation is。

really just a fancy word for using this，plus operator which means put the。

strings together so I have this original，variable named hi and I create a new。

variable called name and in it I'm going，to assign I'm going to assign the string。

a na to the variable name and when I use。

![](img/4964a17e81ae8c50118bdf883d5d6985_17.png)

the plus operator in between high and，named those two variables Python is。

going to look at the values of those two，and it's going to just put them together。



![](img/4964a17e81ae8c50118bdf883d5d6985_19.png)

okay I'm going to switch to Sky to，spider and this is just that example。

from the from the slides so let's see，what happens so I have the variable hi。

the variable name and I'm just，concatenate again and then I'm going to。

print that out so if I run the code，notice it prints out hello there Anna。

right there's no space and there's no，space because the concatenation up。

operator the plus doesn't add any spaces，implicitly so again another example of。

just computer just doing what it's told，if we want to add a space we'd have to。

actually insert the space manually so，that's this line here line 8 and in this。

line we're concatenating the very value，of the variable high with a space notice。

we're putting it in quotation marks just，the space and then with name so if we go。

ahead and print that value notice this。

![](img/4964a17e81ae8c50118bdf883d5d6985_21.png)

was that garbage greeting there and now，another so that's the concatenation。

between strings and then the other thing，we're going to look at related to。



![](img/4964a17e81ae8c50118bdf883d5d6985_23.png)

strings is the star operator so that's，this one here on line 10 so python。

allows you to use the star operator。

![](img/4964a17e81ae8c50118bdf883d5d6985_25.png)

which is stands for multiplication。

![](img/4964a17e81ae8c50118bdf883d5d6985_27.png)

between a string and a number and when，you do that python interpreter。

interprets it as repeat that string that，many number of times so in this case I'm。

creating a silly greeting and I'm，concatenated the value of hi which is。

hello there with the space plus the name，so notice here I'm using parentheses to。

tell Python do this operation first and，then multiply whatever the result of。

this is by 3 okay so if I print that out，it's going to multiply the space with my。

name three times and it's going to，concatenate that with hello there so。



![](img/4964a17e81ae8c50118bdf883d5d6985_29.png)

that's exactly what it printed out there，last lecture we talked a little bit。

about about print today I'm going to，talk about about some nuances related to。

print so you use print to interact with，the user it's cool to write programs。

that print things out to the user so the，keyword here being print and then you。



![](img/4964a17e81ae8c50118bdf883d5d6985_31.png)

put parentheses after print and in the，parentheses you put in whatever you want。

to show the user so in this little，program I have I create a variable named。

X I assign it the value 1 and then I，print one here I'm casting so I'm taking。



![](img/4964a17e81ae8c50118bdf883d5d6985_33.png)

the number one the integer one and I'm，casting it to a string and you'll see。

why in a moment so I want to bring to，your attention a couple things here so。



![](img/4964a17e81ae8c50118bdf883d5d6985_35.png)

in the first print I'm using commas，everywhere here and then the second。

so by definition if you can use print，you can use commas inside a print inside。

the parentheses of print and if you use，a comma Python is going to automatically。

add a space in between the two things，that the commas in in between the values。

so my fav num is is the first thing and，the second thing is whatever is after，the comma。



![](img/4964a17e81ae8c50118bdf883d5d6985_37.png)

let's take X so if you use a comma，Python is going to automatically insert。



![](img/4964a17e81ae8c50118bdf883d5d6985_39.png)

a space for you okay sometimes you might，want that sometimes you might not if you。

don't want that you can use the，concatenation operation the plus and you。

can add all of your little bits together。

![](img/4964a17e81ae8c50118bdf883d5d6985_41.png)

to create one big string if you're using，commas the items the objects in between。

the commas do not all have to be strings，that's the plus side of using commas but。

the downside is you get spaces，everywhere if you use plus operator the。

plus side is Python does exactly what，you tell it to do but everything has to。

be a string object so my fav num is is a，string object you have to convert all of。



![](img/4964a17e81ae8c50118bdf883d5d6985_43.png)

your numbers to string objects and so on，this is the same almost the same code so。

here I don't have spaces anywhere so you，can see that the first line here has。

commas everywhere so I'm going to have，spaces in between every one of the。

things that I'm that I'm printing out，this line here is sort of a combination。

between commas and concatenation so，depending on where I use the comma I'm。

going to have an extra space and this，everywhere，okay so if I run this notice this very。

first line added spaces everywhere in，between all my objects the second one。

added spaces somewhere and you can sort，of trace through and see exactly where。

the spaces were added and the last line。

![](img/4964a17e81ae8c50118bdf883d5d6985_45.png)

okay，so printing things out to the console is，nice but the second part of sort of。

writing an interactive program is，getting input from the user and that's。

that's a more interesting part so if，you've done problem set 0 you might have。

sort of already tried to understand this。

![](img/4964a17e81ae8c50118bdf883d5d6985_47.png)

on your own but here we are so the way，you get input from the user is using。

this command function called input and，inside the parentheses you type in。

whatever you'd like to prompt the user，with so in this case in my example here。

I have input and then here I said type，anything so the user is going to see。

this text here and then the program is，just going to stop and it's going to。

wait for the user to type in something，and hit enter as soon as the user types。

in enter whatever the user types in，becomes a string okay if the user types。

in a number for example that becomes the，string that number okay so everything。

that user types in is going to be made，as a string in this line right here。

whatever the user types in becomes a，string and we're going to bind that。

string object to this variable named，called text okay so now further in my。

program I could do whatever I want with，this variable text in this case I'm。

going to print 5 start text okay，so if the user for example gave me ha。

I'm going to print ha 5 times if the，user gave me 5 what do you think the。

users what do you think's going to be，printed out 25 or 5 5 times great。

often times you don't want to work with，numbers as strings right you want to。

work with numbers as numbers right so，you have to cast and we learn that last。

lecture you cast by just putting in this，little bit right in front of the input。

and you can cast it to whatever type you，want here I cast it to an int but you。

can also cast to a float if you want to，work with floats and that converts。

whatever the user typed in as long as，it's some number that Python knows how。

to how to convert into the number itself。

![](img/4964a17e81ae8c50118bdf883d5d6985_49.png)

so in this case if the user gives me，five I'm going to print out five times。



![](img/4964a17e81ae8c50118bdf883d5d6985_51.png)

![](img/4964a17e81ae8c50118bdf883d5d6985_52.png)

that's the code here so the first bit is，I'm going to get the user to type in。

anything and I'm going to put five five，five and then when I type in the number。

since I'm casting it I'm going to do。

![](img/4964a17e81ae8c50118bdf883d5d6985_54.png)

why do you want to cast - oh the，question is why do you want to cast - a。

string what why do you want to cast a，string to a number Oh so Python always。

whatever you whatever you type in just，by default by definition of the input。

command Python always makes it a string，so if you want to work with numbers you。

have to explicitly tell it I'm going to，work with a number so even if you give。

it the number five it's going to think，it's the string five yeah that's just。



![](img/4964a17e81ae8c50118bdf883d5d6985_56.png)

the next thing we're going to look at is，ways that you can start adding tests in。



![](img/4964a17e81ae8c50118bdf883d5d6985_58.png)

your code and before you can start，adding tests before you can start adding。

tests in your code you need to be able，to do the actual tests，so this is where comparison operators。

come in okay，so here let's assume that I and J are，variables okay the following comparisons。

are going to give you a boolean so it's，either going to say this is true or this。

is false so that's going to be your test，so if I and J are variables you're。

allowed to compare in swith int floats，with floats strings with strings and。

you're allowed to compare instant floats。

![](img/4964a17e81ae8c50118bdf883d5d6985_60.png)

between themselves but you're not，allowed to compare a string with a。



![](img/4964a17e81ae8c50118bdf883d5d6985_62.png)

number in fact if you even try to do，that in Python in spider here if I try。

to say is the letter A greater than 5 I。

![](img/4964a17e81ae8c50118bdf883d5d6985_64.png)

get some angry text right right here and，this just tells me Python doesn't。

understand the meaning of what how do I，okay so just like in math we can do。



![](img/4964a17e81ae8c50118bdf883d5d6985_66.png)

these usual comparisons we can say if，something is greater than something。

greater or equal to less than less than，or equal to I'd like to bring to your。

attention the Equality so the single，equal sign is an assignment so you're。

taking a value and you're signing it to，a variable but when you're doing the。

double equal sign this is the test for，equality is the value of variable I the。

same as the value of the variable J okay，and that's again also going to give you。

a boolean either true or false and you，can also test for inequality with the。



![](img/4964a17e81ae8c50118bdf883d5d6985_68.png)

exclamation equal so that means is the，value of the variable I not equal to the。

value of the variable J true if yes，false if no okay so those are comparison。



![](img/4964a17e81ae8c50118bdf883d5d6985_70.png)

operators on integer floats and strings，on bullying's you can do some logic，operators。

and the simplest is just inverting so if，a is a vet is a variable that can that。

has a boolean value not a is just going，to invert it so if it is true then not a。

is false and vice versa this is a table，that sort of represents what I've said。

here so you can do you can use and and，or these are keywords in Python you can。

use those two keywords on variables on，boolean variables and you get the result。

and B is only true if both a and B are，true and a or B is only false if a and B。

are false and this is the complete table。

![](img/4964a17e81ae8c50118bdf883d5d6985_72.png)

alright so now that we have ways to do，yeah great question so what does it mean。

to compare a string with a string with。

![](img/4964a17e81ae8c50118bdf883d5d6985_74.png)

the greater than so that's just going to，compare them like psychographically。

so it does it come first in the alphabet，so we can even test that out we can say。



![](img/4964a17e81ae8c50118bdf883d5d6985_76.png)

is a greater than B and it's false so B，so now we have ways to do the tests so。



![](img/4964a17e81ae8c50118bdf883d5d6985_78.png)

we can add some branching to our，programming toolbox now that we have。

ways to do tests okay this is a map of，MIT I'm going to go through sort of a。



![](img/4964a17e81ae8c50118bdf883d5d6985_80.png)

little example to motivate why we would，want to do branching in our in our in。

our code and I think after this lecture，you'll be able to sort of code up this。

algorithm that I'm going to explain so，most of us see MIT as a maze I first did。

when I came here when I first came here，obviously I signed up for the free food。

mailing list and MIT being amazed I had，no idea where to go right what the。

shortest path was to free food so one，way to think about it is all I wanted to。

do was get to the free food a very，simple algorithm to get there would be。

to say okay I'm going to take my right，hand and I'm going to make sure that my。

right hand is always on a wall okay and，I'm going to go around campus with my。



![](img/4964a17e81ae8c50118bdf883d5d6985_82.png)

right hand always being at a wall and，eventually I'll get to the where the。

free food is I might not there might not，be any left right but I'll be there okay。



![](img/4964a17e81ae8c50118bdf883d5d6985_84.png)

so the algorithm is as follows okay if，my right hand always has to be on a wall。

then I'm going to say if there's no wall，to my right side then I'm going to go。



![](img/4964a17e81ae8c50118bdf883d5d6985_86.png)

right until I get to a wall okay then if，there's a wall to my right and I can go。

forward I'm just going to keep going。

![](img/4964a17e81ae8c50118bdf883d5d6985_88.png)

forward okay if I keep going forward and，there's a wall to my right and in front。

of me I'm going to turn around and go，left okay and then if there's a wall to。

my right in front of me and to the left，back，so with this fairly simple algorithm I。

just follow the the path always keeping。

![](img/4964a17e81ae8c50118bdf883d5d6985_90.png)

the wall to my right and eventually I，wind up where I need to be okay so。

notice I used just in plain English a，like that，so in programming we have those same。

constructs and those same sort of，intuitive words can be used to tell，Python to do。

thing or to do something else or to，choose from a different set of。



![](img/4964a17e81ae8c50118bdf883d5d6985_92.png)

possibilities okay and this way we can，get the computer to make decisions for。

us now you might be thinking well you，said that computers can't make decisions。

on their own it's not us programmers are，going to build these decisions into the。

program and all the computer is going to，do is going to say is going to reach the。

decision point and say okay this is a，decision point should I go left or。

should I go right or which one do I pick，and these sort of decisions are created。

by you as the programmer and the，computer just has to make make the。

decision and choose a path okay so in，programming there's three sort of simple。

ways that you can add control flow to，your programs and that's making one。

decision and choosing whether to execute，something or execute something else the。

first is a simple if okay and given a，program that just linearly has。

statements that get executed whenever I，reach an if statement you're going to。

check the condition the condition is，going to be something that's going to。

get evaluated to either true or false，okay so I've reached the condition here。

and if the condition is true then I'm，going to additionally execute this extra。

set of expressions but if the condition，is false then I'm just going to keep。

going through the program and not，execute that extra set of instructions。

okay how does Python know which，instructions to execute they're going to。

be inside this what we call code block。

![](img/4964a17e81ae8c50118bdf883d5d6985_94.png)

and the code block is denoted by，indentation so it's going to be。

everything that's indented is part of，that if code block typically four spaces。

indentation okay so that's，that's how you'd write code that decides。

whether to execute this extra thing or，not now let's say I don't just want to。



![](img/4964a17e81ae8c50118bdf883d5d6985_96.png)

execute an extra thing I want to reach a，condition I want to reach a point where。

I say I'll either go down this path or，I'll do something else okay。

that's this right here so this if/else，construct says this is my code I've。

reached my decision point here if the，condition inside this if is true then。

I'm going to execute maybe this set of，statements here okay but if the。

condition is not true then I'm not going，to execute that set of statements and。

instead I'm going to execute under，whatever else is so using this construct。

I'm either going to do one set of，expressions or the other but never both，okay。

and after I've executed one or the other。

![](img/4964a17e81ae8c50118bdf883d5d6985_98.png)

I'm going to continue on with just the，regular execution of the program all，right。

okay so we're able to either choose one，thing choose one thing or another but。

what if we want to have more than one，choice so if some number is equal to。

zero I want to do this if it's equal to，one I want to do this otherwise if it's。



![](img/4964a17e81ae8c50118bdf883d5d6985_100.png)

equal to two I want to do this and so on，that's where this last one comes in and。

we introduced this other keyword here，called Elif so that stands for short。

form for else--if so first we check if，this condition is true so we're going。

through our program we've reached our，decision point if the condition is true。

we're going to execute maybe this set of，instructions if the conditions not true。

maybe we'll check what if the condition，is not true we will check this next。

condition that's part of the L if right，here and if that one's true we're going。

to execute a different set of，instruction，you can have more than one L if and。

depending on which one's true you're，going to execute a different instead of。

instructions and then this last else is，sort of a catch-all where if none of the。

previous conditions were true then just，do this this last set of expressions so。

in this case you're going to choose，between one of these three one of these。

four routes or however many you have and，then when you're done making your choice。



![](img/4964a17e81ae8c50118bdf883d5d6985_102.png)

you're going to execute the remaining，set of instructions so the way this。

works is if more than one condition is，true you're actually just going to enter。

one of them and you're going to enter，the very first one that's true so you're。

never going to enter more than one of，these code blocks you're always enter。

one and you enter the very the first one，that's that evaluates to true so notice。

that we denoted code blocks using，indentation and that's actually one of。

the things that I really like about，Python it sort of forces you to write。



![](img/4964a17e81ae8c50118bdf883d5d6985_104.png)

pretty code and nice-looking code and，just code that's very readable and that。

it forces you to indent everything，that's a code block okay so you can。

easily see sort of where the flow of，control is and where decision-making。

points are and and things like that okay，so in this particular example we have。

one if statement here and it checks if，two variables are equal and we have an，if L if else。

and in this example we're going to enter，either this code block or this one or。

this one depending on the variables of X，and Y and we're only going to enter one。

code block and we'll enter the first one，that that's true，notice you can have nested conditionals。

so inside this first if we have another，if here and this inner if is only going。

to be checked when we enter the first，this outer if，okay I do want to make one point though。

so sometimes you might forget to do the，double equals sign when you do when you。

check Warren you're checking for，equality and that's okay if you just use。

one equal sign pythons going to give you，an error and it's going to say syntax。

error and it's going to highlight this，line and then you're going to know that。

there's there's a there's a mistake，there you should be using equality。

because it doesn't make sense to be，using to assign to be making an。



![](img/4964a17e81ae8c50118bdf883d5d6985_106.png)

assignment inside the if okay all right，so we've learned about branching and we。

know about conditionals let's try to，apply this to to a little game and。



![](img/4964a17e81ae8c50118bdf883d5d6985_108.png)

spoiler we won't be able to we'll have，to learn about a new thing but back in。

1980s there was the Legend of Zelda cool，graphics where there was a scene with。

the Lost Woods okay oversimplification，if anyone's a Zelda know die-hard fan。

but the basic idea was if you entered，the woods you know you entered from the。

left to the right and then as long as，you kept going right it would show you。

the same screen over and over again okay，and the trick was you just had to go。

backward and then you'd exit exit the，woods okay so very simple using what we。

know so far we could sort of code this，up and we'd say something like this if。

the user exits right then set the，background to the woods background。

otherwise set the background to the exit，background okay now let's say the user。

and then and then in the else we're done，let's say the user went right well you'd。

show them the woods background and now，ask them again where do they want to go。

if they exit right set the background to，the woods background otherwise set the。



![](img/4964a17e81ae8c50118bdf883d5d6985_110.png)

background to the exit background and so，on so you notice that there's sort of no。

end to this right how many times do you，know do you know how many times the user。

might keep going right they might be，really persistent right and they'll be，times。

get out of the woods you know maybe a，thousand one maybe so this this would。

probably be who knows how deep this，nested does these nested ifs okay so we。



![](img/4964a17e81ae8c50118bdf883d5d6985_112.png)

don't know so with what we know so far，we can't really code this this cute。

little game but enter loops and，specifically a while loop so this code。

here that could be you know infinitely，number of nested if statements deep can。

be rewritten using these three lines so，we say while the user exits right set。

the background to the woods background，and with a while loop it's going to do。

what we tell it to do inside the loop，and then it's going to check the。

condition again and then it's going to，do what we what we say it should do。

inside the code block and then it's，going to set the check the condition。

again and then when the condition as，long as the condition is true it's going。

to keep doing that little loop there and，as soon as the condition becomes false。

it's going to stop doing the loop and do，whatever is right after the while okay。

so that's basically how a while loop，works we have while that's the keyword。

the condition is something that gets，evaluated to true or false and once。

again we have a code block that's，indented and it tells Python these are。

the expressions I want to do as long as，the condition is true so the condition。

is true you evaluate every expression in，the code block when you reach the end of。

the expression end of the code block you，check the condition again if it's true。

still you keep doing the expressions，so here's a little game and with these。

lines of code we were able you know we，can code up the the lost losses of of。

Zelda even worse graphics by the way，than the original Zelda is this one that。

I coded up here so I print out the，following things you're in the last。

forest go left or right and my program，is going to say you know you're in the。

last forest go left or right it's going，to get user input it's going to say。

while the user keeps typing in right，show them this text and ask them again。

right so I'm asking them again by just。

![](img/4964a17e81ae8c50118bdf883d5d6985_114.png)

saying input here again and that's it，that's going to just keep getting input。

from the user and if the user doesn't，type in right and maybe types in left。

you're going to exit out of this loop，and print out you got out of the loss。

force so I have to show you this because，I spent too much time on it but I。

decided to improve on the code that's in，the slides and I've written here ways。

that you guys can also improve it so if，I run my code you'll know you're in the。

last force go left or right so if I say，left then yay I got out of the last。

forest but if I go right then I'm stuck，right I took down some trees you can see。

there's no more trees here I made a。

![](img/4964a17e81ae8c50118bdf883d5d6985_116.png)

table and then I flipped it over okay so，the expansion to this if you want to try。

it out I put this in the comments here，is try to use a counter okay if the user。

types and write the first two times just，make that a sad face but if the user。

types in more than two times make them，cut down some trees and build a table。

and flip it okay that's a cute little，expansion if you want to test yourself。

to make sure you you're getting loops。

![](img/4964a17e81ae8c50118bdf883d5d6985_118.png)

okay so so far we've used while loops to，ask for user input and that's actually。

somewhere where it makes sense to use，while loops because you don't actually。

know how many times the user is going to，type in something you can use while，loops。

to keep sort of a counter and to write，code that counts something if you do。

that though there's two there's two，things you need to take care of the。

first is this first line here which is，sort of an initialization of this loop。

counter and the second is this line here，the reason why the second one is。

important is because let's look at our。

![](img/4964a17e81ae8c50118bdf883d5d6985_120.png)

condition here so while n is less than，five if you didn't have this line here。

you'd never increment n so every time，through the loop you just keep printing。

zeros okay and you'd have an infinite。

![](img/4964a17e81ae8c50118bdf883d5d6985_122.png)

loop I do want to show though what if，you do have an infinite loop it's not。

the end of the world so I can say，something like so while true print zero。

okay so this is going to give me an，okay so notice it's just printing the。

letter P over and over again and if I，let it go any longer it's going to slow。

down the computer so I'm going to hit，control-c or command-c maybe and it's。



![](img/4964a17e81ae8c50118bdf883d5d6985_124.png)

going to stop the program from printing，okay，so just in case you ever enter enter。

infinite loops in your programs just go，to the console and hit control-c and。

that's going to stop it from sort of，slowing down the computer okay so going。

back to this example I was saying that，if you're using counters or variables in。

order to sort of count up inside the，while loop you have to take care to。

initialize a counter variable first and，then to increment it otherwise you'll。

enter an infinite loop that feels a，little bit tedious and so there's a。

shortcut for doing that exact same thing，so these four lines you can rewrite。

those into these two lines right here，using this new type of loop called a for。

loop so the for loop says for some loop，variable in this case I named it n you。

can name it whatever you want in range 5，we're going to come back to what range。

means in a little bit print n okay so，every time through the loop you're going。

to print out what the value of n is，range 5 actually creates internally a。

sequence of numbers starting from 0 and，going to that number 5 minus 1 so the。

sequence is going to be 0 1 2 3 and for，the first time through the loop you're。



![](img/4964a17e81ae8c50118bdf883d5d6985_126.png)

going to say n is equal to 0 or，internally this is what happens and gets。

the value 0 you're going to print n then，you're going to back go back to the to。

the top and gets the value 1 then you're，going to go execute whatever is inside。

so you're going to print 1 then you're，going to increment that to the next。

value in the sequence you're going to。

![](img/4964a17e81ae8c50118bdf883d5d6985_128.png)

print out 2 and so on so this is the，general look of a for loop so we have。

for some loop variable again can be，named whatever you want in rain。

change some number do a bunch of stuff，and again these are part of this four。

loop code block so you should indent，them to tell Python that these are the。

things that you should do okay so when，you're using range some number you start。

out with variable getting the values，zero okay with with variable having。

value zero you're going to execute all，of these expressions after all the。

expressions in the code block are done，you're going to go on to the next value。

so one you're going to execute all these，expressions with variable being value。



![](img/4964a17e81ae8c50118bdf883d5d6985_130.png)

one and then so on and so on until you，go to some num minus one that it's so so。

using range in that way is a little bit，constraining because you're always going。

to get values starting from zero and，ending at some numb - 1 ok whatever is。

in the parentheses in range sometimes，you might want to write programs that。

maybe start at a custom value don't，start at 0 maybe they start at 5。

maybe start at minus 10 and sometimes，you might want to write programs that。

don't go with don't increment the，numbers by 1 but maybe skip every other。



![](img/4964a17e81ae8c50118bdf883d5d6985_132.png)

number go every two numbers every three，numbers and so on so you can customize。

range to your needs the one thing you do，need to give it is this stop so if you。

give it only one value in the，parentheses that stands for stop and by。

default start is going to have the value，0 and step is going to have the value 1。

if you give it two things in the，parenthesis you're giving it start and。

stop so the first thing start the second，being stop and step gets this value of 1。

by default and if you give it 3 things，in the parenthesis you're giving it。

and you're always going to start at the，start value and stop at or so you're。

going to start at the start value and，you're going to go until stop minus one。

so those are the the sequences of，numbers so in this first code right here。

my sum is going to get the value zero，and you're going to have a for loop。

we're going to start from seven right，because we're giving it two numbers and。

when you give it two numbers it，represents start and stop with step。



![](img/4964a17e81ae8c50118bdf883d5d6985_134.png)

being one so you're starting at seven if，step is one the next value is eight。



![](img/4964a17e81ae8c50118bdf883d5d6985_136.png)

what's the value after that if we're，incrementing by one nine and since we're。

going until stop minus one we're not，actually going to pick up on ten okay so。

this loop variable I the very first time，through the loop is going to have the。

value seven so my sum is going to be，zero plus seven that's everything that's。

inside the code block the next time，through the loop I gets the value eight。

so inside inside the for loop my sum，gets whatever the previous value was。

which was seven plus eight okay the next，time through the loop my sum gets the。

value seven plus eight plus nine，obviously replacing that with the。



![](img/4964a17e81ae8c50118bdf883d5d6985_138.png)

previous value so fifteen okay since，we're not going through ten that's where。

we stop and we're going to print out my，sum which is going to be the value of，okay。

that's a great question we can try that。

![](img/4964a17e81ae8c50118bdf883d5d6985_140.png)

out I'm not actually sure right off just，off the top of my head so you can go in。

Spyder and say let's say in this example，here in this example here so we can say。

seven point one ten point three yeah so。

![](img/4964a17e81ae8c50118bdf883d5d6985_142.png)

![](img/4964a17e81ae8c50118bdf883d5d6985_143.png)

okay so that's that's that example and，let's erase that in this particular。

example we have start/stop and step and，here we're going going every other value。

so we're starting at five tell me what，the next value is supposed to be if。

we're taking every other one seven and，then nine and then are we doing 11 or。



![](img/4964a17e81ae8c50118bdf883d5d6985_145.png)

not excellent nice yeah so we're going，to the end minus one okay so it's。

possible that sometimes you write code。

![](img/4964a17e81ae8c50118bdf883d5d6985_147.png)

where you might want to exit out of the，loop early okay you don't want to go。

through all of the sequences of your，numbers maybe there's a condition inside。

there where you just want to exit the，loop early inside the while loop maybe。

you want to exit the loop before the，condition becomes false so that's where。

the break statement comes in so the，break works like this it's going to as。

soon as Python sees this break statement，it's going to say okay I'm going to look。

at whatever loop I'm currently in I'm，not evaluating any expression after it。

that comes within my loop and I'm going，to immediately exit the loop so I'm。

going inside this while this while I'm，evaluating this one expression and I。

suddenly see a break expression B does，not get evaluated and break is going to。

immediately exit out of the innermost，loop that it's in so this while loop。

that has condition - that's the，innermost loop that the break is found。

its found in so we're going to exit out，of this innermost loop here and we're。

evaluating expression C and notice we're，evaluating expressions C because its。

expression C is part of the outer while，loop it's at the same level as this one。



![](img/4964a17e81ae8c50118bdf883d5d6985_149.png)

and these ones are part of the inner，while loop okay okay。



![](img/4964a17e81ae8c50118bdf883d5d6985_151.png)

last thing I want to say is just a，little bit of a comparison between for。

and while loops so when would you use，you，problem sets so for loops you usually。

use when you know the number of，iterations okay while loops are very。

useful when for example you're getting，user input and user input is。

unpredictable right you don't know how，many times they're going to do a certain。

task for both for and while loops you，can end out of the loop early using the。

break the for loop uses this counter its。

![](img/4964a17e81ae8c50118bdf883d5d6985_153.png)

inherent inside the for loop a while，loop you can use a counter in order you。

can use a while loop to count things but，you must initialize the counter before。

the while loop and you have to remember。

![](img/4964a17e81ae8c50118bdf883d5d6985_155.png)

to increment it within the loop，otherwise you may be lead to an infinite。

loop we've seen in as the very first，example of a for loop that the while。

loop the for loop could be rewritten as，a while loop but the vice-versa is not。



![](img/4964a17e81ae8c50118bdf883d5d6985_157.png)

necessarily true and the counter example，to that is just user input so you might。

not know how many times you might do a，certain task all right great that's。



![](img/4964a17e81ae8c50118bdf883d5d6985_159.png)