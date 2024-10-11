# 【双语字幕+资料下载】MIT 6.0001 ｜ 计算机科学与Python编程导论(2016·完整版) - P38：L12- 搜索与排序 - ShowMeAI - BV1Dw411f7KK

![](img/155d22819dc0cdb343122828e099e8ea_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/155d22819dc0cdb343122828e099e8ea_2.png)

![](img/155d22819dc0cdb343122828e099e8ea_3.png)

so for the last two lectures we've been，talking about analyzing algorithms。

complexity orders of growth how do we。

![](img/155d22819dc0cdb343122828e099e8ea_5.png)

estimate the cost of an algorithm as the，size of the input grows and as I've said。

several times I'll say at least once，more how do we also turn at the other。

direction how do we use thoughts about，choices of pieces of algorithm in terms。

of implications on the cost it's going，to take us to compute we saw last time a。

set of examples constant algorithms，linear algorithms，sorry constant algorithms logarithmic。

algorithms linear algorithms quadratic，algorithms exponential algorithms today。

what I'm going to do is fill in one more，piece a log linear algorithm something。

that's really a nice kind of algorithm，to have and use it to talk about one。

last class of algorithms that are really，valuable and those are searching and。

sorting algorithms so a search algorithm，kind of an obvious statement you use。

them all the time when you go to Google，or Bing or whatever your favorite search。

mechanism on the web is it's just a way，to find an item or a group of items from。

a collection if you think about it that，collection could be either implicit or。

explicit so way back at the beginning of，the term we saw an example of a search。

algorithm when you were looking for，square roots and we saw simple things。

like a new or exhaustive enumeration，we'd go through all the possibilities we。

saw our first version of bisection，search there where you would do。

approximations newton raphson these are，all examples of a search algorithm where。

the collection is implicit it's all the，numbers between some point at some other。

point more comment is a search algorithm，where the collection is explicit I don't。

know for example I've got all the data，records of students and I want to know。

how do I find a particular student so I，can record that a plus that everybody in。

this room is going to get next Tuesday，on that exam that's not a promise sorry，but we'll work on it。

so could do it in place it could do it，explicit doing search explicitly and it。

could be on different kinds of，collections but I'm going to focus just。

as an example on search over lists and，to，make it a little easier let's just do。

search over lists of numbers but it，could obviously the other kinds of。



![](img/155d22819dc0cdb343122828e099e8ea_7.png)

elements now you've already seen some of，this right we did search where we said。

we could do linear search brute force，just walk down the list looking at。

everything until we either find the。

![](img/155d22819dc0cdb343122828e099e8ea_9.png)

thing we're looking for or we get to the，end of the list sometimes also called。

British Museum algorithm or exhaustive，enumeration I go through everything in。

the list nice news is the list doesn't，have to be sorted it could be just an。

arbitrary order what we saw is that the，expected sorry not expected the worst。

case behavior is linear in the worst，case the elements not in the list I got。

a look at everything so it's going to be。

![](img/155d22819dc0cdb343122828e099e8ea_11.png)

linear in terms of complexity and then，we looked at bisection search where we。

said the list needs to be sorted but if，it is we can actually be much more。

efficient because we can take advantage。

![](img/155d22819dc0cdb343122828e099e8ea_13.png)

of the sorting to cut down the size of，the problem and I'll remind you about。



![](img/155d22819dc0cdb343122828e099e8ea_15.png)

both of those there was our simple，little linear search right set a flag。

that says I haven't yet found it and，then just loop over the indices into the。

list I could have also just looped，directly over the list itself checking。

to see if the ithe member of the list is，the thing I'm looking for if it is。

changed the flag to true so that when I，come out of all of this I'll return the。



![](img/155d22819dc0cdb343122828e099e8ea_17.png)

flag either false because it was set，that way initially or true because I。

found it and of course what we knew is，we have to look at everything to see if。

it's there or not I could speed this up，by just returning true at this point。

well that would improve the average case，doesn't improve the worst case and。

that's the thing we usually are，concerned about because in the worst。



![](img/155d22819dc0cdb343122828e099e8ea_19.png)

case I got to go through everything and，just to remind you we said this is order。

length of the list to go around this，part the loop right here and inside the。

loop it's constant work I'm doing the，same number of things each time that's。



![](img/155d22819dc0cdb343122828e099e8ea_21.png)

order n times order 1 and Beyer rules，that's just order M so it's linear in。

the size of the problem ok we said we。

![](img/155d22819dc0cdb343122828e099e8ea_23.png)

could do it on sorted lists but just，again walk down the list again here I。

could loop over everything in the list，checking to see if it's the thing I want。

returned true and if I ever get to a，big，than the thing I'm looking for I know it。

can't be in the rest of the list because，all the things to the right are bigger。



![](img/155d22819dc0cdb343122828e099e8ea_25.png)

yet I could just return false and drop，out in terms of average behavior this is。

better because it's going to stop as，soon as it gets to a point where it can。

rule everything else out but in terms of，complexity it's still order am because。

are still on average half - not average，in the worst case I'm still going to be。

looking n times through the loop before，I get to a point where I can decide to。

bail out of it so order an and then，finally last piece of recap bisection。

search repeat again the idea here is，take the midpoint of the list look at。

that element if it's the thing I'm，looking for great I just won the lottery。

if it isn't decide is the thing I'm，looking for bigger or less than that。

middle point if it's bigger than that I，only use the upper half of the list if。

it's less than that I only use the lower，half of the list and the characteristic。

here was at each step I'm reducing the，size of the problem in half I'm throwing。



![](img/155d22819dc0cdb343122828e099e8ea_27.png)

away half of the remaining list at each，step it'll just remind you of that code。

I know it's a lot here but just to，remind you it said down here if I've got。

an empty list can't be there I'm going，to return false otherwise call this。

little helper function with the list the，thing for which I'm searching and the。

beginning and end point indices into the，list initially start in the very end and。

this code up here basically says if，those two numbers are the same I'm down。

to a list of one just check to see if，it's the thing I'm looking for otherwise。

pick something halfway in between and，ignore this case for the moment。

basically then check to see is the thing，at that point bigger than II in which。

case I'm in general going to call this。

![](img/155d22819dc0cdb343122828e099e8ea_29.png)

only with from the low point to the mid，point otherwise I'm going to call this。

with the mid point too high and that was，just this idea of keep cutting down in。



![](img/155d22819dc0cdb343122828e099e8ea_31.png)

half the size of the list last piece of，the recap the thing we wanted you to see。

here is there are the two recursive，calls I'm going to do only going to do。

one because I'm making a decision at，each step I'm cutting down the problem。

by half and that says the number of。

![](img/155d22819dc0cdb343122828e099e8ea_33.png)

steps the number of times I'm going to，iterate through here will be log in the。

length of the list and if that still，doesn't make sense to you it says I need。

to know when one over two to the K where，K is the number of steps is equal to one。

because on each step I'm reducing by，half and that's when K is log base two。

of n so that's why it's log linear and，so this just reminds you again that。

recap number of calls reduce it outside，the call it gets reduced by factor two。

each time I'm going to have log n work，going around it and inside its constant。

amount of work because I'm just passing，the pointers not actually copying the。

list and that's a nice state to be okay，so sounds good could just use linear。

search it's going to be linear when you，use binary search or bisection search we。

can do it in log time that's great we，assumed the list was sorted but all。

right so that less basically says okay，so when does it make sense to sort the。

list and then do the search right，because if I can sort the list cheaply。

then the search is going to be，logarithmic that's really what I would。



![](img/155d22819dc0cdb343122828e099e8ea_35.png)

like this little expression basically，says let's let sort be the cost of。

sorting the list I want to know when，that cost plus something that's order。

log n which is what it's going to cost，me to do the search when is that less。

than something that's order M because，then it's going to be better to do the。

sort first and do the search and so I，can just rearrange it it needs to be。

when does the cost of sorting when is it，less than this expression which。

basically says when is sorting going to。

![](img/155d22819dc0cdb343122828e099e8ea_37.png)

crud actually good news for you right，this is a really short lecture because。

it says it's never true ouch don't worry，if we got more to go in the lecture the。

reason it can't be true if you think，about it just informally is if I've got。

a collection of n elements and I want to，sort it I've got to look at each one of。

those elements at least once right I，have to look at them to decide where，they go oh that's n。

elements so the sorting must be at least，order n because I got to look at。

everything and in fact as it says there，I'm going to have to use at least linear。

time to do the sort sounds like we're，stuck but we're not and the reason is。

often when I want to search something，I'm going to do multiple searches but I。

may only want to sort the list once in，fact I probably only want to sort the。

list once so in that case I'm spreading。

![](img/155d22819dc0cdb343122828e099e8ea_39.png)

out the cost i'm amortizing the expense，of the sort and now what I want to know。

is if I'm going to do K searches the，cost of those K searches I know is going。

to be K log n because it's log to do the，search and I simply need to know is the。

cost of sorting plus this can I have，something where it's less than K search。



![](img/155d22819dc0cdb343122828e099e8ea_41.png)

is just using linear search and the，answer is yes there are going to be four。

large k's ways in which we can do this，sort where the sort time becomes。

irrelevant that the cost is really，dominated by the search and so what I。

want to do now is look at all right how，could we do this sort reasonably。

efficiently it's going to have to be at，least linear we're going to see it's。

going to be a little more than linear，but if I could do it reasonably I'm。

going to be in good shape here so what I，want to do is show you a number of ways。

in which we can do sorting take a list，of elements and sort them from in this。

case smaller to higher are in increasing，order so here's my goal I want to。

efficiently sort a list I want to see if，we can do this as efficiently as。

possible I'm going to start I'm going to，say with a humorous version of sort。

you've all convinced that my humor is，non-existent you're right but it sets。



![](img/155d22819dc0cdb343122828e099e8ea_43.png)

the stage for this is I saw you can look，it up it's called monkey sort BOGO sort。



![](img/155d22819dc0cdb343122828e099e8ea_45.png)

stupid sort slow store permutation store，shotgun store and here's how it works。

anna has nicely given me a set of。

![](img/155d22819dc0cdb343122828e099e8ea_47.png)

numbers on cards here here's how you do，BOGO sort now I got to do that better。

I've got to spread them out randomly，look this oh good I'm going to have to。

sorry Tom I'm now walking and now I pick，them up saying is that less than this。



![](img/155d22819dc0cdb343122828e099e8ea_49.png)

which is less than Oh crud they're not，sorted，all right I pick them all up and I do it。

again a little brain damage right now，it's intended to get your attention I。

did I heard a couple of chuckles those，are a students by the way I heard a。

couple of chuckles here we could，actually do this exhaustively basically。

it's called permutation sort because you，could search through all possible。

permutations to see if you find，something that's sorted that by the way。

the complexity of that is something like，n factorial which for large n is n to。

the nth power and that fends anything，bigger than about two don't do it all。

right but it would be a way to think，about doing this all right now having。

caught in the humorous version of this，how could we do this a little bit better。

sorry I should say what's the complexity。

![](img/155d22819dc0cdb343122828e099e8ea_51.png)

there's a nice crisp definition of bogo，sort it's best-case is order n because I。

just need to check it sorted it's，average case is n factorial and it's。

worst case if I'm just doing it randomly，as God knows because I could be doing it。

here forever so we're going to move on。

![](img/155d22819dc0cdb343122828e099e8ea_53.png)

here's the second way to do it call，bubble sort I'm going to do this with a。

small version of this I'm going to put，out a settle it turn these up so you can。

see them in a second the idea of bubble，sort is I'm going to start up I'm going。

to call this the front end of the list，and I'm going to walk down comparing。

elements one it pairwise and I'm always，going to move the larger one over so I。

start here and I say ones less than 11，I'm okay，11 is bigger than 5 I'm going to bubble。

that up 11 is bigger than 6 I'm going to，bubble that up 11 is bigger than 2 I've。

basically bubbled 11 to the end now I go，back here I say 1 is less than 5 that's。

good 5 is less than 6 that's good，6 is bigger than 2 bubble that 6 is less。

than 11 you get the idea comparison，comparison and swapped comparison。

comparison and now if I go back to this，part and do it you'll notice that's in。

the right order that's in the right，order that's in the right order that's。

in the right order I'm done，small round of applause please I was。



![](img/155d22819dc0cdb343122828e099e8ea_55.png)

able to sort five elements thank you the，little video is sort of showing in the。

same thing you can see the idea here，it's called bubble sort because you're。

literally bubbling things up out to the，end of the list it's pretty simple to do。

you're just swapping pairs and as you，saw when I get to the end of the list I。



![](img/155d22819dc0cdb343122828e099e8ea_57.png)

go back and do it until I have a pass，where I go all the way through the list。

and I don't do any swaps and in that，case I know I'm done because。

everything's in order and I can stop one，of the properties of it is that the。

largest unsorted element is always at，the end after the pass in other words。

after the first one I know that the，largest elements at the end after the。

second one the largest thing left is，going to be in the next place and that。

tells me among other things that this is，going to take no more than n times。

through the list to succeed might，actually take fewer than that okay。



![](img/155d22819dc0cdb343122828e099e8ea_59.png)

gain let's look at some code for it，let's look at its complexity and let's。

actually run this so here is a little，simple version of bubble sort I'm going。

to set a flag up here I'm going to call，it swap initially to false that's going。

to let me tell when I'm done when I'm，gone through everything in the list。

without doing a swap and then I'm going，to loop as long as swap is false so the。

first time through it's going to do that，loop I set swap initially to true and。

notice what I then do I let J range from，1 up to the length of the list and I。

look at the J element in the previous，element if the previous element is。

bigger I'm going to flip them right，there and that's just doing that swap。

what I just did down here and if that's，the case I'm going to set the flag to。

false which says I've done at least one，bubble as part of this which means when。

I come out of here and go back around to，the loop it's going to do it again and。

it will do it until all of this succeeds，without this ever being true in which。

case that's true which makes that false。

![](img/155d22819dc0cdb343122828e099e8ea_61.png)

![](img/155d22819dc0cdb343122828e099e8ea_62.png)

and it will drop out ok let's look at an，example of this running it's just to。



![](img/155d22819dc0cdb343122828e099e8ea_64.png)

give you a sense of that assuming I can，find the right place here so there's a。

gain aversion a bubble sort on the side，and I'm going to bring this down to the。

bottom I've got a little，list there and I'm just I've put a print。

statement in it so you can see each time，through the loop what's the form of the。

list as it starts and assuming I've done，this right here you go。

there's the list the first time through，notice after one pass twenty fives at。

the end of the list the biggest element，exactly what I like but you can also see。

a few other things have flipped right，right in there there have been some。

other swaps as it bubbled through and in，fact you can see it's well you can see。

that idea you can see 25 moving through。

![](img/155d22819dc0cdb343122828e099e8ea_66.png)

notice on the next step a whole bunch of，the list is actually in the right order。

it's just because I got lucky，all I can guarantee is that the second。

largest element is at the second and or。

![](img/155d22819dc0cdb343122828e099e8ea_68.png)

the second from the end at the list but，you can see here even though the list is。



![](img/155d22819dc0cdb343122828e099e8ea_70.png)

I think 9 long it only took us 4 passes，through so this is nice it says at most。

n times through the list and at the end，we actually get out something that's in。

the right form okay so let's go back to。

![](img/155d22819dc0cdb343122828e099e8ea_72.png)

this and basically say what's the，complexity，well that's length n right has to be I'm。

going through the entire list and inside，of there is just constant work for。

operations I'm doing a test that's right，5 I'm doing a test and in depending。

whether that test is true or not I'm，setting a flag and doing some movement。

of things around but it's just cost I，don't care about the 5 and there how。

many times do I go around the loop in。

![](img/155d22819dc0cdb343122828e099e8ea_74.png)

the worst case in all I can guarantee is，after the first pass bigger thing is。

here to the second pass the second，biggest thing is there after the third。

pass you get the idea so I've got order。

![](img/155d22819dc0cdb343122828e099e8ea_76.png)

and things inside the loop and I'm doing，that loop n times and I hope that looks。

familiar we've talked about this right，this is nested loops。



![](img/155d22819dc0cdb343122828e099e8ea_78.png)

what's this quadratic so it's order N，squared where n is the length of the。

list now as you also saw on average it，could be less than that but it's going。

to be order N squared ok，that's one possibility here's the second。



![](img/155d22819dc0cdb343122828e099e8ea_80.png)

nice simple sort algorithm it's called，selection sort and kind of think of this。

as going the other way not completely，but going the other way when I say going。

the other way the idea here is that I'm，going to find the smallest element in。

the list and I'm going to stick it at，the front of the list when I'm done and。

simply swap that place with whatever was。

![](img/155d22819dc0cdb343122828e099e8ea_82.png)

there flip them I might do a few other，flips along the way depending how I。

implement this next pass I'm just going，to look at everything but the first。

element because I know that one's done，I'm going to do the same thing find the。

smallest element remaining in the list，put it in the second spot and keep doing。

that what I know is if I implement this，correctly after I steps the first il。

immense of the list will be sorted and，everything in the rest of the list has。

to be bigger than the largest thing in，the first part of the list okay so we。

could build that before we do it I'm，going to show you a little video。

starring professor Guttag this is his。

![](img/155d22819dc0cdb343122828e099e8ea_84.png)

cameo perfect performance here but I，want to just show you an example of this。



![](img/155d22819dc0cdb343122828e099e8ea_86.png)

using not numbers but people all right，so now we're going to do selection sort。

the idea here is that each step we're，going to select the shortest person and。

put them next in line of the sorted，group so we'll bring the leftmost person。

forward and we will compare her to，everybody else so one at a time step。

forward you're still the winner you go，back please step forward，and while your different comparisons。

that go on by the way we're going to，still the winner next ah a new winner。

all right so you can take her place so，here we're choosing to actually insert。

into the spot in the line we could have，put her back at the front but this is。

not one where same old winner same，winner no change，let's keep getting kind of boring don't。

fall over same winner please this is a，tough one oh close but I think you're，still shorter all right。

next no change which means you are the，first in line congratulations。



![](img/155d22819dc0cdb343122828e099e8ea_88.png)

so smallest element now round down the，and I would invite you to watch the left。



![](img/155d22819dc0cdb343122828e099e8ea_90.png)

hand of the list notice how it is slowly，building up at each stage to have that。

portion sorted and we deliberately admit。

![](img/155d22819dc0cdb343122828e099e8ea_92.png)

students to be of different heights so，gong-gong can do this demo you are the。

winner take your place in line next，and once again we have a lovely group of。

students sorted in height order and。

![](img/155d22819dc0cdb343122828e099e8ea_94.png)

check out I want you to remember number，of comparisons 55 not that the video but。

I want you to see comparison as we go on，in a second so gain selection sort this。

is this idea of find the smallest。

![](img/155d22819dc0cdb343122828e099e8ea_96.png)

element put it at the front and I might，do a little a number of flips as you can。



![](img/155d22819dc0cdb343122828e099e8ea_98.png)

see here along the way but this is the，same sort of animation of that so let's。

first of all convince ourselves it will，do the right thing and then look at some。

code and then run the code so to，convince ourselves that this is going to。

do the right thing we could talk about，something that we often refer to as a。

loop invariant we're going to write a，loop what we're going to walk through。

this and the invariant here we want to，just demonstrate if it's true at the。

beginning and it's true at each step。

![](img/155d22819dc0cdb343122828e099e8ea_100.png)

therefore by induction as we did earlier，I can conclude it's true always is that。

if I'm given the prefix or the first，part of a list from 0 up to I and a。

suffix or a second part of the list from，I plus 1 up to the end of the overall。

list given that then I want to assert，that the invariant is that the prefix is。



![](img/155d22819dc0cdb343122828e099e8ea_102.png)

sorted and no element of the prefix is，larger than the smallest element of the。

suffix just what I said early says at，any stage here if this is the amount of。

sort I've done so far I can guarantee，I'm going to claim this will be sorted。



![](img/155d22819dc0cdb343122828e099e8ea_104.png)

and everything here is bigger than that，thing there how do I prove it well the。

base case is really easy in the base，case the prefix is empty I don't have。

anything so it's obviously sorted and，everything in the suffix is bigger than。

anything in the prefix so I'm fine and，then I just want to say as long as I。

write my code so that this step is true，that I'm going to move the smallest。

element from the suffix the second part，of the list to the end of the prefix。

since the prefix was sorted this is now，sorted and everything in the suffix is。

still going to be bigger than everything，in the prefix and as a consequence by。

induction this is going to give me，something that says it's always going to，be correct。



![](img/155d22819dc0cdb343122828e099e8ea_106.png)

so here's code that would do that，here I'm just going to set a little。

thing called the start of suffix or，suffix start initially it's going to。

point to the beginning of the list and，then I'm going to run a loop and as long。

as I still have things to search in the，list that that pointer doesn't point to。

the end of the list what am I going to，do I'm going to loop over everything。

from that point to the end of the list，comparing it to the thing at that point。

if it's less than I'm going to do a swap，because I wanted to move it up and you。

can see by the time I get through this，loop I will have found the smallest。

element in the remainder of the list and，I would have put it at that spot。



![](img/155d22819dc0cdb343122828e099e8ea_108.png)

whatever suffix start points to and when，I'm done all of that I just changed this。

by one having found the smallest element，I've stuck at at spot zero I'll do the。

same thing having found the next，smallest element I know it's at point。

one and I'll just continue around one of，these you can see here is as opposed to。

bubble sort this one is going to take n，times around the loop because I'm only。

moving this pointer by one so it starts，at 0 and then 1 and then 2 all the way。

up to n minus 1 you can also see in this。

![](img/155d22819dc0cdb343122828e099e8ea_110.png)

particular implementation well I'm，certainly ensuring that the smallest。



![](img/155d22819dc0cdb343122828e099e8ea_112.png)

element goes into that spot I may do a。

![](img/155d22819dc0cdb343122828e099e8ea_114.png)

few other flips along the way I'm going，to find something I think is a smallest。

element put it there and put that，element here and then when I find。

another smaller element I may do that，flip I could have implemented this where。

I literally searched for the smallest，element and only move that doesn't make。

any difference in terms of the。

![](img/155d22819dc0cdb343122828e099e8ea_116.png)

complexity alright what's the complexity，here already said this part I will loop。

n times because I start at 0 and then 1，you get the idea inside of the loop I'm。

going to walk down the remainder of the，list which is initially N and then n。



![](img/155d22819dc0cdb343122828e099e8ea_118.png)

minus 1 and then n minus 2 times but，we've seen that before as well while。



![](img/155d22819dc0cdb343122828e099e8ea_120.png)

they get shorter that complexity is，still quadratic，order n times going through this process。



![](img/155d22819dc0cdb343122828e099e8ea_122.png)

within the process order and things that，I have to compare and yes n gets smaller。

but we know that that that that n term，if you like dominates so again this is。

quadratic okay before you believe that，all sorting algorithms are quadratic I。

want to show you the last one the one，that actually is one of the I think the。

prettiest algorithms around in a great，example of a more efficient algorithm。

it's called merge sort merge sort takes，an approach we've seen before talked。

about dividing conquer break the problem，down into smaller versions of the same。

problem and once you've got those，solutions bring the answer back together。

for merge sort that's pretty easy it，says if I've got a list of 0 or 1。

elements it's sorted da okay if I got a，list of more than one element here's my。

trick I'm going to split it into two，lists I'm going to sort them and when。

I'm done I'm just going to merge those，two lists into one list and the merge is。

easy because if I've got two lists that，are sorted I just need to look at the。

first element of each take the one，that's smaller add it to my result and。

keep doing that until one of the lists，is empty and then just copy the。

remainder of the other list you can，probably already get a sense of what the。

cost is going to be here because this is，cutting the problem in half now I've got。

two pieces so I need to think about both。

![](img/155d22819dc0cdb343122828e099e8ea_124.png)

of them I want to give you a couple of，visualizations of this here's the first。

one it says basically I've got a big，unsorted list I'm going to split it and。

I'm going to split it and I'm going to，split it until I get down to just lists。

that are either 0 or 1 which by，definition are sorted and once I'm at。

that level then I just have to merge，them into a sorted list and then merge。



![](img/155d22819dc0cdb343122828e099e8ea_126.png)

them pairwise into a sorted list and you，get the idea，so it's dividing conquer the divide is。

dividing it up into smaller pieces the。

![](img/155d22819dc0cdb343122828e099e8ea_128.png)

conquer is merging them back together，and we have professor Guttag back for an。



![](img/155d22819dc0cdb343122828e099e8ea_130.png)

encore together with his students so，let's show you an example of merge sort。

so we're about to demonstrate mergesort，and we're going to sort this rather。

motley collection of MIT students by，height so the first thing we need to do。

is we're going to ask everyone to split，into a group of two so you split a。

little bit you two were together you two，are together you two are together you，yourself。

I'm sorry are guarana so now let's take，the first group take a step down and。

what we do is we sort this group by，height with the shortest on the left and。

look at this we don't have to do，anything thank you，feel free to go back up we then sort the。

next pair please and it looks to me like，we need to switch all right take a step。

and again okay notice each side knee，you're now short order which is great。

now what we do is we take these groups，and merge the groups so let's have these。

two going to sort these groups have them，step forward and now what we're doing is。

we're doing a merge of the two sorted，groups so we start by merging them we'll。

take the leftmost person in this group，and compare her to the first person in。

this group and decide she's still the，shortest take a step back now we're。

going to look at you and say you're，actually taller than this fellow so you。

now step up there and we're good here，both of you take a step back now we'll。

take these two groups and follow the，same procedure we'll merge them let's。

see we'll compare you the first person，in this group to the first person in。

this group now it's a little tricky so，let's see the two of you compare let's。

see back-to-back we have a winner，set back and now you need to compare the。

shortest person in this group to the，shortest person in this group we have a。

winner it's you I'm sorry，and now we just we're okay please step。

now we'll have these two groups come，forward will compare the shortest person。

in this group to the shortest person in，that group I actually need you guys to。

get back to back here you are the winner，and it's pretty clear that the shortest。

person in this group is shorter than the，shortest person in that group so you go。

there and you step back，notice the groups and they all sort it，we repeat the same process and notice。

how the whole subgroup now goes up once。

![](img/155d22819dc0cdb343122828e099e8ea_132.png)

we know that one group is empty and you，can see that we have a group of students。

sorted in order by height remember the。

![](img/155d22819dc0cdb343122828e099e8ea_134.png)

first number right 55 28 now this is，just numbers but you can see the。

expectation is this is going to take，less time and it certainly did there so。



![](img/155d22819dc0cdb343122828e099e8ea_136.png)

gain just the demo in another way，visually I'm sorting sorry I'm splitting。

down until they got small things and，then just merging them up I may have to。

do multiple passes through here but it's。

![](img/155d22819dc0cdb343122828e099e8ea_138.png)

going to be hopefully faster than the，other methods we looked at I'm going to。

show you code in a second and then we're，going to run it just to see it but let。

me stress one more time just the idea of，merging you can see the idea I keep。

splitting down till I got something，small enough I want to merge them back。

the idea of merging you've seen it from，Professor Guttag but I just want to。

highlight why this is going to be。

![](img/155d22819dc0cdb343122828e099e8ea_140.png)

efficient if I've got two lists list one，and list two the things left their。

process is very simple I pull out the，smallest element of each I compare them。

and I simply put the smallest one into，the result move on in that first list so。

the one disappears from that left list，and now again I pull out just the。

smallest element of each one do the，comparison smallest one goes to the end。

of my result and I drop that element，from its list so I've now taken one from。

list one excuse me one from list two，and you get the idea the reason I want。

to give you this visualization so let me，do the last step once I get to a place。

where one of the lists is empty just。

![](img/155d22819dc0cdb343122828e099e8ea_142.png)

copy the rest of the list onto the end，you can see already a hint of the code。

and that is that I'm only going to ever，look at each element of each sub list。

once as I do the merge and that's a nice，property having had them sorted I don't。

need to do lots of interior comparisons，I'm only comparing the ends of the list。

I only therefore look at each element，the number of comparisons rather I。

should say I do leave I may look at each，element more than what's the number of。

comparisons is going to be at most the，number of elements in both lists and。

that's going to be a nice queue as we。

![](img/155d22819dc0cdb343122828e099e8ea_144.png)

think about how to solve it so here's，the code to merge and then we'll write。

merge sort and I know there's a lot of，code here but we can walk through it and。

get a good sense of it I'm going to set，up variable called result that's going。

to hold my answer and I'm going to set，up two indices I and J that are。

initially 0 they're pointing to the，beginning and remember the input here is。

two lists that we know are sorted or，should be sorted or we screwed up in。

some way so initially I and J are both，pointing to the beginning of the left。

and right lists and look at what we do，we say as long as there's still。

something in the left list and still，something in the right list I is less。

than the length of left J is less than，the length of right do the comparison if。

the left one's smaller add it to the end，of result to the end of result right I'm。

appending it because I want it to be in，that sorted order and increase I if it's。

not add the right one to the end of，result and increase J and I'll just keep。

doing that until I exhaust one of the，lists and when I do I can basically say。

if the right list is empty I know if I，get out of here they can't both be true。

in other words if there's still，something in the left list just put it。



![](img/155d22819dc0cdb343122828e099e8ea_146.png)

on the end otherwise if the only things，left on the right list just put them on。

the end so I'm just walking down the，list doing the comparison adding the。

smallest element to my result and when，complexity we can already begin to see。



![](img/155d22819dc0cdb343122828e099e8ea_148.png)

here right this says the left and right，sub lists are order so I'm just moving。



![](img/155d22819dc0cdb343122828e099e8ea_150.png)

the indices depending on which one holds，the smaller element and when I get done。

I'm just returning the rest of the list，so what's the complexity here I'm going。

to do this a little more informally you，could actually do that kind of。

relationship I did last time but what am，i doing I'm going through the two lists。

but only one time through each of those，two lists，I'm only comparing the smallest elements。

so as I already said this says that the，number of elements I copy will be。

everything in the left list and，everything in the right list so that。



![](img/155d22819dc0cdb343122828e099e8ea_152.png)

order is just the length of left plus，the length of right and how many。

comparisons do I do the most I have to，do is however many are in the longer。

list right that's the maximum number I，need to have oh that's nice that says if。

the lists are of order n I'm doing order，n copies because order n plus order n is。

just 2 n which is order N and I'm doing。

![](img/155d22819dc0cdb343122828e099e8ea_154.png)

order and comparisons so it's linear in，the length of the list okay sounds good。

that just does the merge how do I do，merge sort well we set it break the。

problem in half keep doing it until I，get sorted lists and then grow them back。



![](img/155d22819dc0cdb343122828e099e8ea_156.png)

up so there's merge sort it says if the，list is either empty or of length one。

just return a copy of the list it's，sorted otherwise find the middle point。

there's that integer division and split，split the list everything up to the。

middle point and do merge sort on that，split everything in the list from the。

middle point on do more merge sort on，that and when I get back those two。



![](img/155d22819dc0cdb343122828e099e8ea_158.png)

sorted lists just merge them again I，hope you can see what the order of，growth should be here。

cutting the problem down in half at each，step so the number of times I should。

have to go through this should be log in。

![](img/155d22819dc0cdb343122828e099e8ea_160.png)

the size of the original list and you，can see why we call it divide and。

conquer on dividing it down into small，pieces until I have a simple solution。

and then I'm growing that solution back，up so there's the base case there's the。



![](img/155d22819dc0cdb343122828e099e8ea_162.png)

divide and there's the nice conquer，piece of this okay I'm going to show you。

an example of that but let's actually，look at some code sorry about that let's。

look at some code to do this and in fact，I meant to do this earlier and didn't I。



![](img/155d22819dc0cdb343122828e099e8ea_164.png)

also have a version of bubble sort here，sorry selection sort I've already done。

bubble sort there selection sort let's，uncomment this and let's run both of。

those and just see the comparison，between them and sorry just to make that。

a little easier to read there we go so，we saw a bubble sort it only went。

through four times so less than n times，their selection sort and as I said to。

you it has to do and passes because it，can only ever guarantee that it gets one。

element at the beginning so you can fact，see in this case from the first or after。

the initial input until the end of the，first step it looks like it didn't do。

anything because it determined，eventually that one was in the right。

spot and similarly I think there's，another one right there where it doesn't。

do any are peers not to do anything all，it's guaranteeing is that the next。

smallest element is in the right spot as，we get to the end of it and in fact ends。

up in the right place and then let's，look at merge sort and the one more。

visualization of this so again let me，remove that and if we run it gene I've。

just put some print statements in there，here you can see a nice behavior I start。

off calling merge sort with that which，splits down into doing merge sort of。

this portion eventually it's going to，come back down there and do the second。

one it keeps doing it until it gets down，to simple this that it knows are sorted。

and then it merges it does the smaller。

![](img/155d22819dc0cdb343122828e099e8ea_166.png)

pieces and then merges it and having now，to merge things it can do the next level。

of merge so you can see that it gets，this nice reduction of problems until it。



![](img/155d22819dc0cdb343122828e099e8ea_168.png)

gets down to the smallest size so let's，just look at one more visualization of。

that and then get the complexity so if I，start out with this list sorry about。

that what I need to do is split it take，the first one，split it keep doing that until I get，those are。

and I simply merge them pass it back up，take the second piece split it until I。

get down to base cases do the merge，which is nice and linear pass that back。

up having done those two pieces I do one，more merge and I do the same thing I。

want you to see this because again you，can notice how many levels in this tree。

log log in the sides because at each，stage here I went from a problem of。

eight to two problems of for each of，those went to two problems of two and。

each of those went to two problems of。

![](img/155d22819dc0cdb343122828e099e8ea_170.png)

size one all right so the last piece is，what's the complexity here's a simple。

way to think about it at the top level，I've got I start off with n elements。

I've got two sorted lists of size n over，two and to merge them together I need to。

do order and work because as I said I've，got to do at least n comparisons where n。

is the length of the list and then I got，to do n plus n copies which is just。

order in so I'm doing order n work at，the second level it gets a little more。

complicated now I've got problems of，size n over four but how many of them do。

I have four oh that's nice because what，do I know about this I know that I have。

to copy each element at least once so，not at least once I would copy each。

element exactly once and I'll do，comparisons that are equal to the length。

of the longer list so I've got four sub，lists of length n over four that says n。

elements oh that's nice order n at each，step sub problems get smaller but I have。

more of them but the total size of the，problem is n so the cost at each step is。

order n how many times do I do it log in，so this is log in iterations with order。



![](img/155d22819dc0cdb343122828e099e8ea_172.png)

and work at each step and this is a，wonderful example of a log linear。



![](img/155d22819dc0cdb343122828e099e8ea_174.png)

algorithm it's n log n where n is the，length of the lift，so what you end up with then is I'll。

write a joke version some reasonable，ways of doing sort that are quick and。

easy to implement but are quadratic and，then an elegant way of doing the search。

this end login and I'll remind you I，started by saying as long as I can make。

the cost of sorting small enough I can，amortize that cost and if you go back。

and look at last lectures notes you'll，see n log n grows pretty slowly and it's。

actually a nice thing to do it makes it，reasonable to do this sort and then I。

can do the search in order n time and，here's the last punchline it's the。

fastest we can do I'm going to look at，John again I don't think anybody has。

found a faster sort algorithm right this，is the best one can do unless you do。

sorry the best worst case I've said John，is absolutely right there are better。

average cases again our concern is worst，case so this is as good as we're going。

to do in terms of a worst case algorithm，so there you now have sorting algorithms。

and searching algorithms and you've now，seen excuse me sorry constant log linear。

log linear quadratic and exponential，algorithms I remind you we want things。

as high up in that hierarchy as possible，all right I have six minutes left some。

of you are going to leave us we're going，to miss you but that's okay I'm sure。

we'll see you later on for those of you，hanging around this isn't a bad time。

just to step back and say so what have，we seen and I want to do this just very。

quickly I'm sorry I remind you we，started by in some sense giving you a。

little bit of a contract of things we，were going to show you and I would。

simply suggest to you what have we done，we given you a sense of how to represent。

knowledge with data structures tuples，lists dictionaries more complicated。

structures we've shown you some good，computational metaphors iteration and。

loops recursion as a great way of，breaking problems down into simpler。

versions of the same problem and they，really are metaphors there are ways of。

thinking about problems we've given you，abstraction the idea of capture。

computation buried in a procedure you，now have a contract you don't need to。

know what happens inside the procedure，as long as，delivers the answer it says it would or。

another way of saying it you can，delegate it to somebody and trust that。

you're going to get what you like out of，it we've seen classes and methods is a。

wonderful way to modularize systems to，capture combinations of data and things。

that operate on them in a nice elegant，way and we just spent a week and a half。

talking about classes of algorithms and，their complexity if you step up a level。

what we hope you've gotten out of this，are a couple of things you've begun to。

learn computational modes of thinking，how do i tackle a problem divide and。

conquer how do I think about recursion，is a tool in dealing with something。

you've begun to begun I will use that，word deliberately to master the art of。

computational problem solving how can，you take a problem and turn it into an。

algorithm and especially you've begun to，have the ability to make the computer do。

what you want it to to say if I've got a，problem from biology or chemistry or。

math or physics or chemical engineering，or mechanical engineering how do I take。

that problem and say here's how I would，design an algorithm to give me a。

simulation and a way of evaluating what，it does and so what we hope we've done。

is we started you down the path to being，able to think and act like a computer。

scientist all right don't panic，that doesn't mean you stare at people's。

shoes when you talk to them not all。

![](img/155d22819dc0cdb343122828e099e8ea_176.png)

computer scientists do that just faculty，sorry John so what a computer scientists。

do and this is actually meant to be，serious and I put up two of my famous。

historical figures of computer，scientists they do think computationally。

they think about abstractions but，algorithms but automated execution so。

the three A's of computational thinking，in the same way but traditionally you。

had the 3 R's of reading writing，arithmetic，computational thinking we hope is。

becoming a fundamental that every，well-educated person is going to need。

and that says you think about the right，abstraction when you have a problem in。

your Europe what's the right abstraction。

![](img/155d22819dc0cdb343122828e099e8ea_178.png)

how do I pull apart the pieces how do I，think about that in terms of the。

decomposing things into a relationship。

![](img/155d22819dc0cdb343122828e099e8ea_180.png)

that I can use to solve problems how do，I automate how do i mechanize that。

traction how do I use what I know，happens inside of the machine to write a。



![](img/155d22819dc0cdb343122828e099e8ea_182.png)

sequence of steps in a language I'm，using to capture that process and then。

finally how do I turn that into an，algorithm and that not only means I need。



![](img/155d22819dc0cdb343122828e099e8ea_184.png)

a language for describing those，automated processes and a bill and if。



![](img/155d22819dc0cdb343122828e099e8ea_186.png)

you like allowing the abstraction of，details but frankly also a way to。

communicate if you have to think crisply，about how do I describe an algorithm。

it's actually giving you a way to，crystallize or clarify your thinking。

about a problem this is not to say you，should talk to your friends in Python I。

don't recommend it but it does say you，should use that thinking as a way of。

capturing your ideas of what you're，going to do and that leads them to this。

idea of how difficult is a problem how，best can I solve it we've shown you。

these complexity classes and we've，hinted at the idea that in fact some。

problems are inherently more difficult，than others that's something I hope you。

come back to as you go along and，especially we want you to start thinking。

recursively we want you to think about，how do I take a hard problem break it up。

into simpler versions of the same，problem and then construct the solution。

and that shows up lots of places right，recursion is in all sorts of wonderful。

places so just to give you an example I，could say to you recursively this。

lecture will end when I'm done talking，about this lecture which will end when。

I'm done talking about this lecture，which will end when I'm done all right。



![](img/155d22819dc0cdb343122828e099e8ea_188.png)

you don't like infinite recursion good。

![](img/155d22819dc0cdb343122828e099e8ea_190.png)