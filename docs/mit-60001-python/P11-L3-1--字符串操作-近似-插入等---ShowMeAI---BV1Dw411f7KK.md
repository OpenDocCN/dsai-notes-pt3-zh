# P11：L3.1- 字符串操作、近似、插入等 - ShowMeAI - BV1Dw411f7KK

![](img/812bfd386a67e73a21a9154de4c0b38c_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/812bfd386a67e73a21a9154de4c0b38c_2.png)

![](img/812bfd386a67e73a21a9154de4c0b38c_3.png)

all right everyone let's get started，so all right good afternoon so this is。

the third lecture of six triple one and。

![](img/812bfd386a67e73a21a9154de4c0b38c_5.png)

600 as always please download slides and，code to follow along so quick recap of。

what we did last time last time we，talked about strings as a new object。

type as sequences of characters and then，we introduced two new concepts that。

allowed us to write slightly more，complicated programs so we introduced。

branching with these keywords，if/elif/else and branching allowed us to。

write programs that us as programmers，could could introduce decisions into our。

programs and then we introduced two，different kinds of loops while loops and。

for loops and those also added a little，bit of complexity to our programs today。

we're going to talk a little bit more，about strings so we're going to see a。

couple more operations that you can do。

![](img/812bfd386a67e73a21a9154de4c0b38c_7.png)

on strings and string objects and then，we're going to talk about three。

different algorithms I guess and check，algorithm an approximate solution。



![](img/812bfd386a67e73a21a9154de4c0b38c_9.png)

algorithm and a bisection method，algorithm okay so let's dive right in。

we'll talk a little bit about strings，first so strings we thought of them as。

sequences of characters right，case-sensitive as we saw in in in。



![](img/812bfd386a67e73a21a9154de4c0b38c_11.png)

programs we wrote last lecture and，strings are objects and we can do all of。

these operations on string objects like，tests if they're equal less than greater。

than and so on turns out we can do more，than just concatenate two strings。

together or do these little tests on，them so we're going to start introducing。

the the idea of of a function or，procedure and we're going to see more。



![](img/812bfd386a67e73a21a9154de4c0b38c_13.png)

about functions and how you can write，your own functions next lecture but for。



![](img/812bfd386a67e73a21a9154de4c0b38c_15.png)

today you can think of a function as，sort of a procedure that does something。

for you okay someone already wrote this，so the first one we're going to look at。



![](img/812bfd386a67e73a21a9154de4c0b38c_17.png)

is a pretty popular function and when，applied on a string this function called。

Len will tell you the length of a string，so that's going to tell you how many。

characters are in the string，and characters are going to be letters。

digits special characters spaces and so，on so it's just going to count how many。

letters how many how many characters in，their string so if I of the string s is。

equal to ABC remember string is in，quotation marks then if I do this this。



![](img/812bfd386a67e73a21a9154de4c0b38c_19.png)

if I write this expression Len s here，since it's an expression it has a value。

so it evaluates to a certain value and，by definition it's going to tell me what。

the length of the string is which is，three characters long okay another thing。

that we can do on strings is since their，sequence of characters I might want to。

get what character is at a certain。

![](img/812bfd386a67e73a21a9154de4c0b38c_21.png)

position so we do this using this fancy，word called indexing but pretty much。

what indexing into a string means is，you're going to tell Python I want to。

know the character at this certain，position or at this certain index inside。

my string okay so once again let's use，this string s is equal to ABC and let's。

index into it so in computer science we，start from 0 counting by convention，class。



![](img/812bfd386a67e73a21a9154de4c0b38c_23.png)

Python is no different so python and，python you start indexing at position 0。

or you start indexing at 0 so the first，character in your string we say is at。

position 0 so right or at index 0 the，next character in the string is at index。

1 and the next character in the string，is at index 2 in Python it turns out you。



![](img/812bfd386a67e73a21a9154de4c0b38c_25.png)

can also use negative numbers to index，and if you use if you index into the。

string with negative 1 for example that，means that you want the last character。

in the string so the last character in，your string is always going to be at。

position negative 1 second the last。

![](img/812bfd386a67e73a21a9154de4c0b38c_27.png)

character is at negative 2 third to last，characters at negative 3 and so on and。

so on ok so the way you index into a，here，and this is the notation so if I want。

the character at position 0 or at index，0 I say s which is the string I want to。

index into and then inside the square，brackets I say what index I want so s at。

index 0 is going to be the value a s at，index 1 is going to be the value B and。

so on and so on and we can also do，negative negative indexing as well if。

you do try I added this in here if you，do try to index into a string beyond the。



![](img/812bfd386a67e73a21a9154de4c0b38c_29.png)

limits of the string and we can even try，this out just to show you that it's not。

the end of the world if we do that if we，have s is equal to ABC and we have s at。

position 20 for example obviously my，string is only length 3 so what's at。

position 20 I get an error right I call，this angry text here in Python but。

really the most relevant thing to note，is these last couple of lines here this。

tells you what line is problematic so s，at position 20 has an issue and this。

last line here tells me what actual，error I have so it's an index error。



![](img/812bfd386a67e73a21a9154de4c0b38c_31.png)

which means I'm trying to index too far，into the string because it only has。

three characters okay so it's nice to be，able to get a single character out of my。

string but sometimes I might want to get，a substring so I want to start at you。

know the first character and go halfway。

![](img/812bfd386a67e73a21a9154de4c0b38c_33.png)

into the string or I want to take the，few few characters in between or I want。



![](img/812bfd386a67e73a21a9154de4c0b38c_35.png)

to skip every other letter or something，like that in my string so if I want to。



![](img/812bfd386a67e73a21a9154de4c0b38c_37.png)

do this slightly more complicated，interaction with strings we call that。

slicing slicing into a string okay and，this notation here should seem a little。

bit familiar because we saw it last，lecture when we did it with a range okay。



![](img/812bfd386a67e73a21a9154de4c0b38c_39.png)

we had a start stop and a step the，notation was a little bit different，parenthesis。

seas and commas in between but except，for that this sort of works the same the。

start is the index starting from zero，from where you want to slice into the。

string the stop is the stop index you're，going to go up until stop minus one and。

take that index and then the step is。

![](img/812bfd386a67e73a21a9154de4c0b38c_41.png)

so this is the full notation here but，sometimes you can not give it a third a。

third sort of number in here so if you，only give it two numbers then that to。

Python that represents just the start。

![](img/812bfd386a67e73a21a9154de4c0b38c_43.png)

and the stop and by default step is，going to be one and there's a lot of。

other things you can do with with，strings you can just you can omit。

numbers and just leave colons and Python，just by the way that by by definition。

the way that whoever wrote slicing had。

![](img/812bfd386a67e73a21a9154de4c0b38c_45.png)

decided if you omit numbers then it's，going to be equivalent to these things。

here so we slice using square brackets，just like indexing except now that we。

can get now we can give it two numbers。

![](img/812bfd386a67e73a21a9154de4c0b38c_47.png)

okay so with this string s if we slice，into the if we slice into the string s。

we start from index 3 and go up and up。

![](img/812bfd386a67e73a21a9154de4c0b38c_49.png)

until index 6 so if we have a b c d e f。

![](img/812bfd386a67e73a21a9154de4c0b38c_51.png)

g h right this is position 0 1 2 3 4 5 6，7 and you just you just count so s。



![](img/812bfd386a67e73a21a9154de4c0b38c_53.png)

starting from 3 and going till 6 is，going to start here 3 right so it's。

going to come up with sorry d and then，we're going to take e and then we're。

going to take f and since we're going，until stop minus 1 we're not going to。



![](img/812bfd386a67e73a21a9154de4c0b38c_55.png)

take g right because this is position 6，and we're going until 6 minus 1。

okay the next one here three six two is。

![](img/812bfd386a67e73a21a9154de4c0b38c_57.png)

going every other one right so we start，at 3 and then we skip every other one so。

we go D but not E and then F and then。

![](img/812bfd386a67e73a21a9154de4c0b38c_59.png)

![](img/812bfd386a67e73a21a9154de4c0b38c_60.png)

stop if you do s and then nothing，nothing inside except colons notice that。

you're going to have s and then nothing，and then ：nothing ： nothing so nothing for start。

nothing for stop nothing for step and，that's just going to evaluate to the。



![](img/812bfd386a67e73a21a9154de4c0b38c_62.png)

string itself it's the same as 0 to the。

![](img/812bfd386a67e73a21a9154de4c0b38c_64.png)

length s going every step this one might，actually be useful it reverses the。

string automatically for you so with，this one little line here you can get。

the inverse of your string and that's，equivalent to that so the minus 1。

represents starting from the end and，going back every letter and then this。

one's a little bit more more complicated。

![](img/812bfd386a67e73a21a9154de4c0b38c_66.png)

but also not too bad okay okay so as，we're doing with the as word as we're。

doing these string slices again if，you're unsure what something does just。

type it into spider and you know you，might be surprised you might not be but。

it's a good way to check yourself to，make sure you know you're understanding。

what's happening okay one thing I want，to mention and it's good to keep this in。



![](img/812bfd386a67e73a21a9154de4c0b38c_68.png)

the back of your mind we're going to，come back to this as we as we start。

talking about slightly more complicated。

![](img/812bfd386a67e73a21a9154de4c0b38c_70.png)

object types but strings are immutable，so just keep this word in the back of。

your mind as we go through this class，and what I mean by this is that an。



![](img/812bfd386a67e73a21a9154de4c0b38c_72.png)

actual string object once it's created，cannot be modified okay this might not。

mean anything right now but let me just。

![](img/812bfd386a67e73a21a9154de4c0b38c_74.png)

draw a little something let's say I have，this string s is equal to hello remember。

in the first lecture we drew a diagram，sort of like this this is my memory I。

have this object hello and this object，hello is bound to this variable s right。

so now I can access the object hello，using this variable s now you might。

think well since I could index into a，string I might be able to you know just。

say something like s at position zero is，equal to Y right and that'll just change。

the little H into a Y and I'll have an，object，well strings are immutable which means。

in Python you're not actually allowed to，do this and it gives you an error if you。



![](img/812bfd386a67e73a21a9154de4c0b38c_76.png)

do try to do that if you want the，variable s to point to the string ye ll。

oh you could just say s is equal to Y ll，o or you could do string operations like。



![](img/812bfd386a67e73a21a9154de4c0b38c_78.png)

this and this takes the Y and it，concatenates it to the string s all of。

the elements starting from position 1，which is e ll o so this makes ye ll o。

now internally what happens when I when，I write this line is Python says ok I'm。

going to break my bond with this，original object hello I'm going to bind。

my string variable s to the new object，yellow and this other old object still。

is in memory somewhere but it's an，entirely different object that I've。



![](img/812bfd386a67e73a21a9154de4c0b38c_80.png)

created here again might not mean，anything right now but just keep this in。

the back of your mind strings are，immutable ok all right so the next thing。

I want to talk about is a little bit of，recap of on for loops and we're going to。

see how we can apply for loops very。

![](img/812bfd386a67e73a21a9154de4c0b38c_82.png)

easily too right very nice readable code，when dealing with strings ok so remember。

that for loops had a loop variable right，my loop variable being this var here in。

this particular case it could be，anything you want and it's variable in。

this particular case iterates iterates，over this sequence of numbers 0 1 2 3 4。

so the very first time through the loop。

![](img/812bfd386a67e73a21a9154de4c0b38c_84.png)

var has a value of 0 it does the，expressions in the loop as soon as。

they're done var takes the value 1 it，does all the expressions in the loop and。

then var takes the value 2 and it does，all the way up until 0 1 2 and the last。



![](img/812bfd386a67e73a21a9154de4c0b38c_86.png)

time it goes around is with var is equal，to 3 and remember we said that we can。

customize our range in order to start，from a custom value to end at a。



![](img/812bfd386a67e73a21a9154de4c0b38c_88.png)

different value and to skip certain，numbers so so far we've only been using。

for loops over a sequence of numbers but，actually for loops are a lot more。

powerful than that you can use them to，iterate over any sequence of values not。

just numbers but also strings ok so here。

![](img/812bfd386a67e73a21a9154de4c0b38c_90.png)

are two pieces of code this one and this，one here ok these two pieces of code。

both do the exact same thing okay to me，possibly to you this one looks a lot。

more readable than this one right just，at a first glance a farmer to read this。

one just using the keywords and and and，variables here it's out it would sound。

like broken English right but you you，could decipher what I'm trying to say。

for a char in a string s if the char is，equal to I or a char is equal to you。



![](img/812bfd386a67e73a21a9154de4c0b38c_92.png)

print there is an i or you okay，sounds weird but you could probably tell。

what I was trying to do here whereas up，here it's it's a little more complicated。



![](img/812bfd386a67e73a21a9154de4c0b38c_94.png)

to tell what I'm doing right you have to，sort of think about it a little bit for。

some index in this range of numbers 0，through the length of the of the string。

s if s at position index is an i or s at。

![](img/812bfd386a67e73a21a9154de4c0b38c_96.png)

position index is a you print there's an，ir you okay，both of these codes just go through the。

string s and if it encounters a letter，that's an i or you it's just going to。

print out this string here but this，bottom one is a lot more pythonic it's。

an actual word created by the Python，community and it just looks pretty right。

like you can you can tell what it what，this codes supposed to do whereas this。

so that's sort of an illustration of a，for loop over a sequence of characters。

right so char is going to be a loop，variable still and the loop variable。

instead of getting instead of iterating，over a set of numbers it's going to。

iterate over every character in s，directly and char is going to be a。

specific character right it's going to，be a letter okay so here's a more。



![](img/812bfd386a67e73a21a9154de4c0b38c_98.png)

complicated example I wrote this code Oh，a couple years ago and it was my attempt。

at creating robot cheerleaders because I，needed some motivation and and then yeah。

I googled last night robot cheerleaders，and was not disappointed created this。

jiff looks pretty cool and it looks like。

![](img/812bfd386a67e73a21a9154de4c0b38c_100.png)

they kind of stole my idea but that's，fine so let's look at what this codes。



![](img/812bfd386a67e73a21a9154de4c0b38c_102.png)

supposed to do I'm gonna run it okay I'm，gonna run it and then we'll go through。

it okay so all right it prints out I，will cheer for you enter a word you know。

what I like robots so I'll put in robots，how enthusiastic and my about robots。

let's say six okay so what this is going，to print is it's a cheerleader right。

give me an R R give me an O o give me a，B B and so on and so on what does that。

spell robots and it's going to print it，six times because I'm six out of ten。



![](img/812bfd386a67e73a21a9154de4c0b38c_104.png)

enthusiastic about robots okay so that's，pretty much what that codes supposed to。

do and you can write it using what we've，learned so far now let's go through it a。

little bit and I'm going to show you，just how how easy it is to convert this。



![](img/812bfd386a67e73a21a9154de4c0b38c_106.png)

code using a for loop over characters，right right now what it does is it asks。

the user for input so a word and a，number and then it does this thing here。

right first it uses a while loop，and second it uses indexing okay and the。

tip here that what tips you off that，it's using indexing is right it's using，okay。

and obviously it's using a while loop，and it has to first create a counter。

initialize it and then down here it's，going to increment it inside the while。

loop if you remember that's sort of what，we need to do for a while loops so it's。

going to start at zero and it's just，basically going to go through index I is。

equal to 0 1 2 3 4 which is going to go，all the way to the end of the word。

whatever the user typed in in this case，robots it's going to get the character。

at that position right word at position，I is going to be a character this line。



![](img/812bfd386a67e73a21a9154de4c0b38c_108.png)

here is just sort of for pretty for for，the cheerleading to make sense it's just。

to take care of letters that make sense，to use on right so give me a B give me。

unbe so give me unbe does not make sense。

![](img/812bfd386a67e73a21a9154de4c0b38c_110.png)

right so that's just taking care of that，and I'm using this in keyword to check。

whether the character so the character，are for example in robots is inside on。

letters and unlettered I've defined up，here which is these are all the letters。

and so if it makes sense to use on，before the letter use that and otherwise。

use just an a and after I'm done I say，what is that spell and then it's just a。

for loop that goes times many times and。

![](img/812bfd386a67e73a21a9154de4c0b38c_112.png)

prints out the word and the exclamation，mark so okay so this code might have。

been a little bit more intuitive if I，rewrote it or if I'd originally wrote。



![](img/812bfd386a67e73a21a9154de4c0b38c_114.png)

written it with a for loop okay so this，part here right the while loop and。

indexing and creating my original，counter we can get rid of that and we。

can replace it with this for char in，word okay，I'm originally using char so I can use。



![](img/812bfd386a67e73a21a9154de4c0b38c_116.png)

char as my loop variable again and，simply I'm just going to iterate over。

the word itself so now instead of having，this mess here I have one liner that。

says for every character in my word do，all this stuff here so that remains the。

same and then I don't even need to，increment a counter variable because I'm。

not using wild loops anymore I'm just，using a for loop okay so the code。



![](img/812bfd386a67e73a21a9154de4c0b38c_118.png)

becomes delete that for char in word and，then delete that and that does the exact。



![](img/812bfd386a67e73a21a9154de4c0b38c_120.png)

same thing okay and it's a lot more，readable right all right so this was our。

toolbox at the beginning of this course。

![](img/812bfd386a67e73a21a9154de4c0b38c_122.png)

we are two and a half，I guess lectures in these are the things，we've added to it。

we know integers float floats boolean's，we know a bit of string manipulation。

math operations we added recently these，conditionals and branching right to。

write slightly more interesting programs，and now we have loops for and while。

loops to add interesting and more，complicated programs okay so with these。

the second part of this lecture is going。

![](img/812bfd386a67e73a21a9154de4c0b38c_124.png)

to be looking at three different，algorithms okay that's the sort of。

computer science part of this of this，class introduction to computer science。

and programming using Python，don't let the word algorithms scare you。

right there they're not that complicated，you just have to sort of think a little。



![](img/812bfd386a67e73a21a9154de4c0b38c_126.png)

bit about them and and and you'll be，able to get them okay so we're going to。

look at three algorithms all in the，context of solving one problem which is。



![](img/812bfd386a67e73a21a9154de4c0b38c_128.png)

finding the cube root first algorithm is，guess and check then we're going to look。

at an approximation algorithm and then a，bisection search so the first is the。

guess and check method okay you might，have done this，in math in high school the guess and。

check method is is also sometimes called，exhaustive enumeration and you'll see。

why so given a problem let's say find，the cube root of a number let's say you。

can guess a starting value for a，solution the guess and check method。

works if you're able to check if your，solution is correct，so if your guess is originally zero you。

can say is zero cubed equal to the cube，the cube of whatever I'm trying to find。

the cube root of so if I'm trying to，find the cube root of eight is zero，cubed equal to eight No。

right so the solution is not correct if，it's not correct yes another value do it。

systematically until you find a solution，or you've guessed all of the values。

possible you know all the possible，values you've exhausted all of your。



![](img/812bfd386a67e73a21a9154de4c0b38c_130.png)

search space，so here's very simple guess and check，code that finds the cube root of a。

number so I'm trying to find the cube，root of eight so my cube is eight I'm。

going to have a for loop that says I'm，going to start from zero and I'm going。

to go all the way up to so I'm going to，start from zero and go all the way up to。

eight for every one of these numbers I'm，going to say is my guess to the power of。

three equal to the cube eight and if it，is I'm going to print out this this。



![](img/812bfd386a67e73a21a9154de4c0b38c_132.png)

message okay pretty simple however this，code is not very user-friendly。

right if if the user wants to find the，cube root of nine they're not going to，get any output。

okay because we never print anything in，the case of of the the guest not being a。

perfect cube or the cube not being a，perfect cube okay so we can modify the。



![](img/812bfd386a67e73a21a9154de4c0b38c_134.png)

code a little bit to add to extra，features okay the first is we're going。

to be able to deal with negative cubes，which is kind of cool and the second is。

we're going to tell the user if the cube，is not a perfect cube。



![](img/812bfd386a67e73a21a9154de4c0b38c_136.png)

hey this cube is not a perfect cube so，we're not going to silently just fail。

because then the user has some sort of，feedback on their on their input so。



![](img/812bfd386a67e73a21a9154de4c0b38c_138.png)

let's step through this code we have，first of all a for loop just like before。

and we're going to go through zero to，eight in this case we're using the。

absolute value because we might want to，find the cube root of negative numbers。

first thing we're doing is doing this。

![](img/812bfd386a67e73a21a9154de4c0b38c_140.png)

check here instead of guessing if the，instead of guessing whether the guess to。

the power of three is equal to the cube。

![](img/812bfd386a67e73a21a9154de4c0b38c_142.png)

we're going to check if it's greater or，equal to and we're going to do that for。

the following reason so if we're if，we're trying to find the cube root of。

eight for example like versus a cube，root of nine this is eight and this is。

nine okay what does this code going to，do it's going to first guess zero zero。

cubed is not greater equal to eight 1，cubed is not greater equal to eight two。

cubed is greater equal to eight so here，once we've guessed two we're going to。



![](img/812bfd386a67e73a21a9154de4c0b38c_144.png)

break because we found a number that，works and there's no need to keep。

looking right once we found the perfect，the cubed root of this number eight。

there's no need to keep searching write，the remainder three four five six seven。

eight okay sort of the same idea when，we're trying to find the cube root of。

nine we're going to start with zero zero，to power three。



![](img/812bfd386a67e73a21a9154de4c0b38c_146.png)

is less than 9 1 ^ 3 is less than 9 2 ^，3 is less and 9 when we get to 3 ^ 3。



![](img/812bfd386a67e73a21a9154de4c0b38c_148.png)

that's going to be greater than 9 so，this code tells us once we've picked a。

number that's beyond the logical sort of，cubes of the what's sorry once we've。

picked a number that's beyond the，reasonable number of our cubed root of。

our cube the cube root of our cube then。

![](img/812bfd386a67e73a21a9154de4c0b38c_150.png)

we can we should stop because again it，doesn't make sense to keep searching。

because if 3 to the power of 3 is。

![](img/812bfd386a67e73a21a9154de4c0b38c_152.png)

already greater than 9 4 to the power of，3 is also going to be greater than 9 and。

so on okay so once we break here we，either have guess being 2 or guess being。



![](img/812bfd386a67e73a21a9154de4c0b38c_154.png)

3 depending on what cube we're trying to，find and if the guess to the power of 3。



![](img/812bfd386a67e73a21a9154de4c0b38c_156.png)

is not equal to the cube then obviously，a cube was not a perfect cube so that's。

this case here if we were looking at 3，at the cube root of 9 and otherwise this。

part here just looks at whether we，should make it a positive or or a。

negative cube okay so if our original，cube was less than 0 then obviously the。

cube root of a negative number is going，to be a negative number and otherwise。



![](img/812bfd386a67e73a21a9154de4c0b38c_158.png)

it's just our word guests okay so that's，the guess and check method slightly more。

feature-rich program for guessing the，cube root but that only tells us the。

cube root of perfect cubes and doesn't，really give us any anything else any。

more information so sometimes you might，want to say well I don't care that 9 is。

not a perfect cube just give me a close，enough answer okay，so that's where approximate solutions。



![](img/812bfd386a67e73a21a9154de4c0b38c_160.png)

come in so this is where we're good，we're okay with having a good enough。

solution okay so in order to do that，we're going to start with a guess and。

then increment that guess by some small。

![](img/812bfd386a67e73a21a9154de4c0b38c_162.png)

value okay start from 0 and start，incrementing by point zero zero one and。

just go upwards from there and at some。

![](img/812bfd386a67e73a21a9154de4c0b38c_164.png)

point you might find a good enough，solution，in this program we're going to keep。

guessing as long as we're not close。

![](img/812bfd386a67e73a21a9154de4c0b38c_166.png)

enough and close enough is going to be，given by this epsilon value in the。

program okay so as long as the guest，cubed minus the cube so how far away are。

we from the actual answer is greater，than some epsilon keep guessing right。

because the solutions not good enough，but once this is less than epsilon then。

we've reached a good enough solution so，two things to note with approximate。

solutions right so you can get more，accurate answers if your step size is。

really really small if you're，incrementing by point zero zero zero one。

you're going to get a really good，approximate solution but your program。

will be a lot slower okay same sort of，idea with epsilon you can change epsilon。

if you change epsilon to be a bigger，epsilon right you're sacrificing。

accuracy but you're going to reach a，solution a lot faster so here's the code。



![](img/812bfd386a67e73a21a9154de4c0b38c_168.png)

for the approximate solution of a cube，root might look intimidating but look。

almost half this code is just，initializing variables，okay so we're initializing this is a。

cube we want to find the cube root of we，pick an epsilon of this we start with a。

guess of zero we start with an increment，of point zero zero zero one and just for。

fun let's keep track of the number of，guesses that it takes us to get to the。

answer this is similar to the guess and。

![](img/812bfd386a67e73a21a9154de4c0b38c_170.png)

check from before if or it's not so what，this part is similar to I guess and。

check from before so if so we're going，to take the guess to the power of three。

minus the cube right so that's how far，away are we from the actual answer and。

we're going to say if that's not good，enough so if we're still greater than or。

equal to the epsilon then keep guessing，so we're going to be stuck in this loop。

where we keep guessing values until，we've reached a guess that's good enough。

so until we're small we're less than。

![](img/812bfd386a67e73a21a9154de4c0b38c_172.png)

Epsilon，and the way we keep guessing is just，with this line right here which says。

increment by guests by increment my。

![](img/812bfd386a67e73a21a9154de4c0b38c_174.png)

guests by increment and increment being，this really small value that makes sense。

okay so I'm going to keep incrementing，my guests by that small value before I。

go on I'm going to run the code and。

![](img/812bfd386a67e73a21a9154de4c0b38c_176.png)

we're going to discover a small issue，so with 27 we're going to run it perfect。

it took me 300 guesses but two point，nine nine nine nine nine nine is close。

to the cube root of 27 okay we can find，the cube root of this guy here and it。

took me twenty thousand guesses but I，figured out that two hundred point nine。

nine and a nine so two hundred and one，is close to the cube root of that large。

number and then I should have done this，this is going to be a giveaway you guys。

sorry then we're going to have let's say，I want to try cube of ten thousand so。

ten thousand is not a perfect cube so we，can run the code and with eight one two。

oh 601 I had already gotten an answer，but with ten thousand I'm not getting an。



![](img/812bfd386a67e73a21a9154de4c0b38c_178.png)

answer yet right so I'm I'm thinking，that there might be something wrong so。

I'm going to stop my code so I just hit，control C because I feel like I've。

entered an infinite loop and in fact I，have so what ended up happening is this。

problem here so I'm going to draw。

![](img/812bfd386a67e73a21a9154de4c0b38c_180.png)

I'm going to start from zero and I'm，going to increment right my guesses like。

that with every with every little，increment I'm going to make a new guess。

I'm going to take that guess to the，power of three I'm going to subtract the。

cube and I'm going to figure out if I'm，less than Epsilon okay this is the。

epsilon that I want to be in okay this，little bit here so with every new guess。

I might be maybe so this is where I want，to be right within this little boundary。

here with every new guess I might be，here with the next guess over here I。

might be here when I make another guess，I might be here so I'm getting close to。

being with an Epsilon but maybe with my，next guess I'm going to hop over my。



![](img/812bfd386a67e73a21a9154de4c0b38c_182.png)

epsilon and have made too big of a guess，okay so just because of the way the。

numbers right the numbers were chosen in，this example just to illustrate this。

using an increment of 0。01 with finding，the cube of 10，000 and epsilon of 0。1 it。

turns out that as I'm doing all these，calculations I'm going to skip over this。

perfect bound this perfect sort of，epsilon difference so first I'm going to。



![](img/812bfd386a67e73a21a9154de4c0b38c_184.png)

be too too small and then I'm going to，be too large and once I've become too。

large or too far away from Epsilon the，guess is I continue to make are just。

going to be even even farther away from。

![](img/812bfd386a67e73a21a9154de4c0b38c_186.png)

Epsilon and I'm not going to get to my，answer and that's why I've reached an。



![](img/812bfd386a67e73a21a9154de4c0b38c_188.png)

infinite loop in this code okay all I'm，doing in this code is guessing whether。

it is checking whether my guest cube，minus cube is less than Epsilon the only。

thing I need to do here is sort of add，this little clause here that says oh by。



![](img/812bfd386a67e73a21a9154de4c0b38c_190.png)

the way also check that I'm less than。

![](img/812bfd386a67e73a21a9154de4c0b38c_192.png)

cube because this is just like we did in，the very first program when I'm taking。

I'm checking your 0 1 2 3 4 5 6 7 8，right when I'm trying to find the cube，root of 8。



![](img/812bfd386a67e73a21a9154de4c0b38c_194.png)

ah cube root of eight right，once I've reached eight I'm going to。



![](img/812bfd386a67e73a21a9154de4c0b38c_196.png)

stop and it's the same thing here so I，just added this lo clause that says well。

while I'm greater than equal to the，epsilon and I'm still less than the。

actual cube just keep searching but once，I've reached the cube then stop。

searching and with ten thousand you can，see that I failed to actually find so。

that's what I that's what this part here，does it tells me that I've failed to。



![](img/812bfd386a67e73a21a9154de4c0b38c_198.png)

find the cube root with those particular，parameters okay last thing we're going。

to look at is bisection search and to。

![](img/812bfd386a67e73a21a9154de4c0b38c_200.png)

illustrate this I'm going to need one，volunteer and you're going to play a。

game with me in front of the whole class。

![](img/812bfd386a67e73a21a9154de4c0b38c_202.png)

and there will be a prize，ah there go the hands in the blue shirt。

right there all right cool so the prize。

![](img/812bfd386a67e73a21a9154de4c0b38c_204.png)

is going to be once again this I promise。

![](img/812bfd386a67e73a21a9154de4c0b38c_206.png)

I don't have I don't have millions of，these Google glasses I also don't work。



![](img/812bfd386a67e73a21a9154de4c0b38c_208.png)

okay，so the game is this I'm going to ask，I'm going to ask you to pick a number a。

whole number between 0 and 100 okay，and I'm going to try to guess it and you。

need to make it hard for me and you make，it so hard for me that I cannot guess it。

within 10 guesses okay and if you can do，that if I cannot guess it within 10。



![](img/812bfd386a67e73a21a9154de4c0b38c_210.png)

guesses you get this okay so and I'm，along，okay so do you have your number yes okay，perfect。

let me erase that actually I should，probably kept that because I'll still。



![](img/812bfd386a67e73a21a9154de4c0b38c_212.png)

use it okay there's the numbers zero to，100 okay is your number 50 okay 50 was。



![](img/812bfd386a67e73a21a9154de4c0b38c_214.png)

my guess so I've made one guess is is，your number higher lower than 50 higher。



![](img/812bfd386a67e73a21a9154de4c0b38c_216.png)

okay is your number。

![](img/812bfd386a67e73a21a9154de4c0b38c_218.png)

my next guest is going to be 75 and the，guest and the reason I'm guessing 75 is。

because what's your name。

![](img/812bfd386a67e73a21a9154de4c0b38c_220.png)

what's that Sophie Sophie said 50 was，too low so I immediately know that it。

cannot be any less than 50 so I've，already eliminated half of the numbers。



![](img/812bfd386a67e73a21a9154de4c0b38c_222.png)

right so my next guest is 75 is your。

![](img/812bfd386a67e73a21a9154de4c0b38c_224.png)

number 75 okay lower is your number，lower higher higher is your neck okay so。



![](img/812bfd386a67e73a21a9154de4c0b38c_226.png)

I'm since it's higher I'm eliminating，this half here is your number between 75。

and 100 oh boy you're putting me on the，spot what's that 87 thank you 87 higher。



![](img/812bfd386a67e73a21a9154de4c0b38c_228.png)

or lower lower okay so since it's lower。

![](img/812bfd386a67e73a21a9154de4c0b38c_230.png)

I'm gonna let me eliminating that half。

![](img/812bfd386a67e73a21a9154de4c0b38c_232.png)

![](img/812bfd386a67e73a21a9154de4c0b38c_233.png)

is your number 81 higher or lower okay，so she said lower so I'm eliminating。



![](img/812bfd386a67e73a21a9154de4c0b38c_235.png)

that half is your number 78 boy that's。

![](img/812bfd386a67e73a21a9154de4c0b38c_237.png)

![](img/812bfd386a67e73a21a9154de4c0b38c_238.png)

really hard 78 okay higher lower is your，number 76 yay all right perfect。

76 was the number so how many guesses，have I made one two three four five six。



![](img/812bfd386a67e73a21a9154de4c0b38c_240.png)

I made six guesses so I did get it under，under ten but you know what the game was。

rigged so you get so you get the prize，anyway just because I pick the game here。

you go thank you all right。

![](img/812bfd386a67e73a21a9154de4c0b38c_242.png)

so notice in bisection search what I did，was I eliminated half the search space。

right with every guess I said well she，said it's higher or lower so I。

definitely cannot be in the other search，space right if I was doing approximate。

solution or in this case guess in check。

![](img/812bfd386a67e73a21a9154de4c0b38c_244.png)

I would be I would be asking Sophie is，your number zero one two three four and，so on。

right so with guess and check it would，have taken me 76 guesses to get to the。

number whereas with this bisection。

![](img/812bfd386a67e73a21a9154de4c0b38c_246.png)

search that I just did it only took me，six right is that cool so that means。

that the larger the space actually is，that I need to search the better it is。

to use bisection search this bisection，search method okay so that's basically。



![](img/812bfd386a67e73a21a9154de4c0b38c_248.png)

what I'm illustrating here so we have，our original search space we're going to。

choose a guess halfway and eliminate，half of the guesses then we're going to。



![](img/812bfd386a67e73a21a9154de4c0b38c_250.png)

choose an look in the remaining interval，eliminate half the guesses and so on and。

okay so then this is the code for。

![](img/812bfd386a67e73a21a9154de4c0b38c_252.png)

bisection search also looks intimidating，but it's not so bad，so we're initializing a bunch of stuff。

up here most important a couple things，we're initializing our first of all this。



![](img/812bfd386a67e73a21a9154de4c0b38c_254.png)

high and this low boundaries okay so，with a guessing game the low boundary。

was zero and the high boundary was a，hundred right when we're looking at the。

cube root the low boundary is going to，be zero right and the high boundary is。



![](img/812bfd386a67e73a21a9154de4c0b38c_256.png)

going to be just my cube right because，the cubed because I guess to the power。

of three cannot be any greater than cube，and then just going to do the same。

procedure that I did the guessing game，which is I'm going to make my guess be。



![](img/812bfd386a67e73a21a9154de4c0b38c_258.png)

halfway in between，so with this guessing game I had to sort，of choose if if there were three numbers。

if there are four numbers in between you，know should I go higher or lower but。



![](img/812bfd386a67e73a21a9154de4c0b38c_260.png)

when we're doing by section by section，search here we don't care about that。

we're just going to do floating point，division because we want a we want。

decimal numbers okay so I have a lot，lower boundary and a high boundary and。



![](img/812bfd386a67e73a21a9154de4c0b38c_262.png)

I've figured out my halfway point then I，have this while loop here while loop is。

similar to the approximation method，where as long as I'm not as long as I。

don't have a guess that's good enough，so this depicted by this greater equal。

to Epsilon as long as my guess is not，good enough I'm going to keep guessing。



![](img/812bfd386a67e73a21a9154de4c0b38c_264.png)

saying，so if the guests the power of three -，cube is not good enough keep guessing。



![](img/812bfd386a67e73a21a9154de4c0b38c_266.png)

and the way I keep guessing is this part。

![](img/812bfd386a67e73a21a9154de4c0b38c_268.png)

here says my guess was too low so if my，guess was too low set the low boundary。

to be the guess right because I don't，care about all of the other numbers that。



![](img/812bfd386a67e73a21a9154de4c0b38c_270.png)

are much lower than me so set the low to，be the guess that's what that line is。

doing and otherwise my guess was too，high that's what this else is doing so。

set the high to be the guess because I，don't care about numbers any higher than。

my guess okay once I have these new。

![](img/812bfd386a67e73a21a9154de4c0b38c_272.png)

boundaries I make another guess again，halfway in between the new boundary。

points okay so essentially I'm just，having my interval with every single。

guess okay and that's what the while。

![](img/812bfd386a67e73a21a9154de4c0b38c_274.png)

loop is doing and then I print out the，remaining part so notice the search。

space right originally being n we're，having it with each guess so the first。

guest divides it by two the second gets，divided by four and so on so by the time。

we get to the kaif guess and / - k right，the kaif guess let's say that's the。

actual answer we're interested in，there's only one value in that little。

interval and that's the answer we want，so 2 to the K is equal to n and then how。



![](img/812bfd386a67e73a21a9154de4c0b38c_276.png)

many guests did we make k is equal to，log base 2 of n so when we were playing。

the guessing game of 100 right my n was，100 log base 2 of 100 is 6 point。

something I think so in fact I could，have said if I don't guess it within 7。

guesses you would have won as well so，that's why the game was rigged right so。

the guest notice it converges on the，order of log base n instead of just。

linearly in terms of n so that's why，it's so powerful one last thing I want。

to mention is the code I showed only，works for positive cubes and that's。



![](img/812bfd386a67e73a21a9154de4c0b38c_278.png)

because of the following so I have the，zero and one let's say I'm trying to，find the cube root of 0。

5 when I first，set my initial boundaries my low is this，one and my high is this one right but。

what's the cube root of 0。5 is it within，boundary，I heard outside it's like 0。7 something。

so it's out here so with this particular，code I'm going to be having my interval。



![](img/812bfd386a67e73a21a9154de4c0b38c_280.png)

in between those numbers but I'll never，get to an answer because the actual cube，root of 0。

5 or numbers less than 1 is，going to be outside that boundary so。

there's a small change you can make to，the program which will fix that and。

that's in the code I didn't put it in，but it's a very small change a small if。



![](img/812bfd386a67e73a21a9154de4c0b38c_282.png)

statement so that's it all right thank。

![](img/812bfd386a67e73a21a9154de4c0b38c_284.png)