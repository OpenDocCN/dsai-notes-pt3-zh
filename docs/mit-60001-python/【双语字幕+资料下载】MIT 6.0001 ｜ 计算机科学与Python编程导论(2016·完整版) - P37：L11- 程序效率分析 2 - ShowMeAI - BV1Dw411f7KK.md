# 【双语字幕+资料下载】MIT 6.0001 ｜ 计算机科学与Python编程导论(2016·完整版) - P37：L11- 程序效率分析 2 - ShowMeAI - BV1Dw411f7KK

![](img/6b3f7f52a93a387f5aea7f58c9646547_0.png)

the following content is provided under，a Creative Commons license your support。

will help MIT OpenCourseWare continue to，offer high quality educational resources，for free。

to make a donation or view additional，materials from hundreds of MIT courses。



![](img/6b3f7f52a93a387f5aea7f58c9646547_2.png)

![](img/6b3f7f52a93a387f5aea7f58c9646547_3.png)

last time we started talking about，complexity and I want to quickly remind。



![](img/6b3f7f52a93a387f5aea7f58c9646547_5.png)

you of what we're doing because we're，going to talk some more about that today。

and when I say complexity it was the，question of can we estimate the amount。

of resources typically time that we're，going to need to get an algorithm to。

solve a problem of a particular size and，we talked about that both in terms of。

estimating how much time is it going to，take and using it to go the other。

direction and think about how design，choices in an algorithm have。

implications for the cost it's going to。

![](img/6b3f7f52a93a387f5aea7f58c9646547_7.png)

be associated with that so we introduced，the idea of what we call Big O notation。



![](img/6b3f7f52a93a387f5aea7f58c9646547_9.png)

orders of growth a way of measuring，complexity and we started talking about。

different classes of algorithms so today，I'm going to quickly recap those basic。

ideas and what we're going to do is，we're going to see examples of standard。

classes of algorithms with the idea that，you're going to want to begin to。

recognize when an algorithm is in that，class so very quick recap I've already。

said part of this we want to have a，mechanism a method for being able to。

estimate or reason about how much time，do we think an algorithm is going to。

take to solve a problem of a particular，size and especially as we increase the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_11.png)

size of the input to the algorithm what，does that do in terms of the increase in。



![](img/6b3f7f52a93a387f5aea7f58c9646547_13.png)

the amount of time that we need some，ways we don't care about exact versions。

in a second we're going to see the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_15.png)

definition of this but what we care，about is that notion of how does it grow。



![](img/6b3f7f52a93a387f5aea7f58c9646547_17.png)

as we increase the problem size and what，we're going to focus in going if you。

like in the forward direction as I said，a lot of the interest is actually。

thinking about what you might think of，as the backwards or reverse direction。

how does a choice in algorithm design，impact efficiency of the algorithm and。

really what we want you to do is to，begin to recognize standard patterns。

that if you make a particular choice，this fits in a class of algorithms。

you've seen before and I know in essence。

![](img/6b3f7f52a93a387f5aea7f58c9646547_19.png)

how much time what the cost is going to，be as I do that all right so just to。



![](img/6b3f7f52a93a387f5aea7f58c9646547_21.png)

recap as I said，on the top we talked about orders of，growth the idea is we want to be able to。

evaluate programs efficiency when the，input is very big we talked about timing。

things just with a timer we suggested，that unfortunately conflates the。

algorithm with the implementation with，the particular machine we want to get。

rid of those latter two and just focus，on the algorithm so we're going to talk。

about counting operations but in a very，general sense so we're going to express。

what we call the growth of the program's，runtime as the input size grows very。

large and because we're only interested，not an exact number but in if you like。

the growth of that we're going to focus，on putting an upper bound on the growth。

an expression that grows at least as，fast as what the cost of the algorithm。

is now you could just cheat and pick a，really big upper bound that doesn't help。

us very much so in general we're going，to try and use as tight an upper bound。

as we can what's the class of algorithm，it falls in but as we've seen before we。

care about the order of growth not being，exact so something grows as two to the N。

+ 5 n I don't care about the 5 n because，when n gets big that 2 to the N is the。

really big factor and therefore we're，going to look at the largest factors。

when we think about that seen some，examples we're going to do a bunch more。



![](img/6b3f7f52a93a387f5aea7f58c9646547_23.png)

examples today to fill those in and one，of the things that we want to now do is。



![](img/6b3f7f52a93a387f5aea7f58c9646547_25.png)

say with that idea in mind there are，classes of complexity of algorithms so。



![](img/6b3f7f52a93a387f5aea7f58c9646547_27.png)

some sense the best ones are way up here，o of one order one constant it says cost。

doesn't change as I change the size of，the input it's great it's always going。

to be the same cost order log n says the，cost grows logarithmically with the size。

of the input it's a slow growth I'm，going to remind you that in a second we。

saw lots of examples of linear running，time we're going to see a few more today。

what we call log linear polynomial and，exponential and the thing I want to。

remind you is that ideally oops sorry，we'd like our algorithms to be as close。

to the top of this categorization as we，can this is actually described in，increasing。



![](img/6b3f7f52a93a387f5aea7f58c9646547_29.png)

of complexity something that takes the，same amount of time no matter how big。

the input is unless that amount of time，is a couple of centuries seems like a。

really good algorithm to have something。

![](img/6b3f7f52a93a387f5aea7f58c9646547_31.png)

that grows linearly is not bad something，that grows as we've seen down here。



![](img/6b3f7f52a93a387f5aea7f58c9646547_33.png)

exponentially tends to say this is going，to be painful and in fact you can see。



![](img/6b3f7f52a93a387f5aea7f58c9646547_35.png)

that graphically just remind you here，something this constant says if I draw。

out the amount of time it takes as a，function of the size of the input。

it doesn't change logarithmic glows，grass or it grows very slowly linear。



![](img/6b3f7f52a93a387f5aea7f58c9646547_37.png)

will grow obviously in a linear way，and I actually misspoke last time I know。

it's rare for a professor to ever admit，they misspeak but I did because I said。

linear is if you double the size of the，input it's going to double the amount of。

time it takes actually that's an，incorrect statement really what I should。

have said was the increment if I go from，say ten to a hundred the increase in。

time is going to be the same as the，increment if I go from a hundred to a。

thousand might be more than double，depending on what the constant is but。

that growth is linear if you want to，think of it take the derivative of time。

with respect to input size it's just，going to be a constant it's not going to。

change within and of course when we get，down to hear things like exponentially。

grows really fast and just as a last，recap gain I want to be towards the top。



![](img/6b3f7f52a93a387f5aea7f58c9646547_39.png)

of that there was my little chart just，showing you things that grow constant。

log linear log linear quadratic and。

![](img/6b3f7f52a93a387f5aea7f58c9646547_41.png)

exponential if I go from n of ten to a，hundred to a thousand to a million you。

see why I want to be at the top of that，chart something up here that grows。



![](img/6b3f7f52a93a387f5aea7f58c9646547_43.png)

logarithmically the amount of time grows，very slowly as I increase the input down。

here well like it says good luck it's，going to grow up really quickly as I'm。



![](img/6b3f7f52a93a387f5aea7f58c9646547_45.png)

as I move up in that scale I want to be，at the top of this chart if I can okay。

with that in mind what I'm going to do，today is show you examples filling in。

most of this chart we've already seen，some examples we've seen examples of。

linear we've seen examples of quadratic，I'm going to streamlined you that's what。

I want to do is show you how you can，begin to recognize that，of an algorithm in terms of where it。

lies so algorithms that are constant，complexity the kind of boring they tend。

to be pretty simple because this says，this code is going to run in the brief。



![](img/6b3f7f52a93a387f5aea7f58c9646547_47.png)

basically the same amount of time，independent of the size of the input now。

notice the bottom thing here it doesn't，say you can't you there try again it。

doesn't say you couldn't have a loop or，a recursive call you could it's just。



![](img/6b3f7f52a93a387f5aea7f58c9646547_49.png)

that that loop cannot depend on the size。

![](img/6b3f7f52a93a387f5aea7f58c9646547_51.png)

the input so there aren't many，interesting algorithms here we're going。

to see pieces of code that fit into this，when we do our analysis but something。

that's constantly complexity says。

![](img/6b3f7f52a93a387f5aea7f58c9646547_53.png)

independent of the size of the input，right a little more interesting not a。

little a lot more interesting or，algorithms that are logarithmic in their。

complexity since they're going to grow。

![](img/6b3f7f52a93a387f5aea7f58c9646547_55.png)

with the logarithm of the size of the，input you saw an example much earlier in。

the term when Anna showed you bisection，search was searching for a number with a。

particular property I want to show you，another example both the let you。

recognize the form of the algorithm but，especially to show you how we can reason。

about the growth and that's another。

![](img/6b3f7f52a93a387f5aea7f58c9646547_57.png)

trick called binary search or a game，it's a version of bisection search。



![](img/6b3f7f52a93a387f5aea7f58c9646547_59.png)

suppose I give you a list list of，numbers integers and I want to know if a。



![](img/6b3f7f52a93a387f5aea7f58c9646547_61.png)

particular element is in that list we，saw last time you could just walk down。



![](img/6b3f7f52a93a387f5aea7f58c9646547_63.png)

the list just iterate through the entire，list looking to see if it's there in the。

worst case which is what we worried，about it's going to be linear you only。

have to look at every element to the lid，in the list till you get to the end so。

complexity was linear in that case and，then we said suppose we know that the。

list is sorted it's ordered from，smallest to largest and we saw simple。

algorithm says again walk down the list，checking to see if it's there but when。

you get to an element that's bigger than，the thing you're looking at you can just。

stop it's no reason to look at the rest，of the list they've all got to be bigger。

than the thing you're searching for，practically in the average case that's。

going to be faster than just looking at，an unsorted list but the complexity is。

still linear because in the worst case，I've got to go all the way through the。

list before I do some thing is，there okay so even sequential search and。

an ordered list is still linear can we。

![](img/6b3f7f52a93a387f5aea7f58c9646547_65.png)

do better and the answer is short so，here's how we do better I'm going to。

take that list I'm going to assume it's。

![](img/6b3f7f52a93a387f5aea7f58c9646547_67.png)

sorted and I'm going to pick an index，that divides the list in half just pick。



![](img/6b3f7f52a93a387f5aea7f58c9646547_69.png)

the midpoint in the list and I'm going，to check that value when I ask is the。

element in the list at that point the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_71.png)

thing I'm looking for if it is great I'm，done，if I'm not that lucky I'm then going to。



![](img/6b3f7f52a93a387f5aea7f58c9646547_73.png)

ask is it larger or smaller than the，thing I'm looking for and based on that。

I'm either going to search the front。

![](img/6b3f7f52a93a387f5aea7f58c9646547_75.png)

half or the back half of the list ooh，that's nice okay because if you think。



![](img/6b3f7f52a93a387f5aea7f58c9646547_77.png)

about it in something that was just a，linear algorithm that each step are。



![](img/6b3f7f52a93a387f5aea7f58c9646547_79.png)

reduced the size of the problem by one I，went from a problem of size n to a。

problem of size n minus 1 to a problem，of size n minus 2 here I'm taking a。



![](img/6b3f7f52a93a387f5aea7f58c9646547_81.png)

problem of size n I'm reducing it to n，over 2 in one step because I can throw。

half the list away so this is a version，of divide and conquer things we've seen。

before I'm breaking it down into smaller，versions of the problem so let's look at。

that and then we'll let's write some。

![](img/6b3f7f52a93a387f5aea7f58c9646547_83.png)

code and then let's analyze it so，suppose I have a list of size n right。



![](img/6b3f7f52a93a387f5aea7f58c9646547_85.png)

there n elements in there I'm going to，look at the middle one say is it the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_87.png)

thing I'm looking for if it's not is it，bigger than or less than the thing I'm。

looking for and in this case let's，assume that in fact the thing I'm。

looking for is smaller than that element，great I'm going to throw away half the。

list now I only have to look at the，lower half of the list I'll do the same。

thing a look at the element in the，middle here and I'll say is it the thing。

I'm looking for if not is it bigger than，or smaller than the thing I'm looking。

for getting them down to n over two，elements after I do that I throw away。

half the list again in this case I'm。

![](img/6b3f7f52a93a387f5aea7f58c9646547_89.png)

assuming that the thing I'm looking for，is bigger than that middle point until I。

find that at each step I'm looking at，the middle element and I'm either。

throwing away the left half or the right。

![](img/6b3f7f52a93a387f5aea7f58c9646547_91.png)

half of that list so after I steps。

![](img/6b3f7f52a93a387f5aea7f58c9646547_93.png)

I'm down to a list of size and over 2 to，the eye now what's the worst case the。

worst case is the elements not in the，list I'm going to have to keep doing。



![](img/6b3f7f52a93a387f5aea7f58c9646547_95.png)

this until I get down to just a list of，1 element and at that point if I it's。



![](img/6b3f7f52a93a387f5aea7f58c9646547_97.png)

not the thing I'm looking for I know I'm，done and I can stop different pattern。

notice how I'm cutting down the size of，the problem by two so I can ask before。

we look at the code what's the，complexity of this how many steps do I。



![](img/6b3f7f52a93a387f5aea7f58c9646547_99.png)

have to go through in the worst case and，I know I'm going to be done looking at。

the list when n over 2 to the I is equal，to 1 meaning there's only one element。

left that I'm still looking at and I can，solve that it says I'm going to have to。



![](img/6b3f7f52a93a387f5aea7f58c9646547_101.png)

take up most I equal to log n steps，all right so logarithmic Li I'm cutting。



![](img/6b3f7f52a93a387f5aea7f58c9646547_103.png)

this down and so there we complexity of，the recursion we haven't talked about。



![](img/6b3f7f52a93a387f5aea7f58c9646547_105.png)

the code yet but in terms of the number，of steps I have to do in the worst case。

is just logarithmic in the length of the，list that's nice a lot better than。

looking at everything inside the list，and in fact you can see it right I don't。



![](img/6b3f7f52a93a387f5aea7f58c9646547_107.png)

look at everything inside the list here，I'm throwing half of the things away at。



![](img/6b3f7f52a93a387f5aea7f58c9646547_109.png)

a time ok so let's look at some code to，do that bisection search I'm going to。

give it a list of numbers I'm going to，give it something I'm looking for we can。

walk through this code hopefully it's，something you're going to be able to。

recognize pretty clearly says if the，list is empty there's nothing there。

thing I'm looking for can't be there I，return false if there's exactly one。

element in the list then I just check it，if that thinks the thing I'm looking for。

returned true otherwise return false I'm，just going to return the value there。

otherwise find the midpoint notice the，integer division here find the midpoint。

in that list and check it in particular，say if the thing at the midpoint is。

bigger than the thing I'm looking for，then I'm going to return a recursive。

call to this function only looking at，the first half of the list I'm just。

slicing into it otherwise I'll do the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_111.png)

same thing on the second half of the，list，nice this is implementing exactly what I。



![](img/6b3f7f52a93a387f5aea7f58c9646547_113.png)

said we could actually try it I'll do，that in a second if I remember but let's。



![](img/6b3f7f52a93a387f5aea7f58c9646547_115.png)

think about complexity here that's，constant alright doesn't depend on the。

size of the list that's constant doesn't，depend on the size of the list that's。



![](img/6b3f7f52a93a387f5aea7f58c9646547_117.png)

constant sounds good and what about that。

![](img/6b3f7f52a93a387f5aea7f58c9646547_119.png)

well it looks like it should be constant，right other than the number of times I。



![](img/6b3f7f52a93a387f5aea7f58c9646547_121.png)

have to go through here remember I know，I'm going to have order log in recursive。

calls I'm looking at what's the cost to，set it up it looks like it should be。

constant so does that but I'm going to，claim it's not anybody see why it's not。



![](img/6b3f7f52a93a387f5aea7f58c9646547_123.png)

you can look at the slides you've，already printed out right there I'm。

actually copying the list right when I，slice into the list like that it makes a。



![](img/6b3f7f52a93a387f5aea7f58c9646547_125.png)

copy of the list Oh crud supposed to say，something different but I won't because。



![](img/6b3f7f52a93a387f5aea7f58c9646547_127.png)

this is going to cost me a little bit as，I think about the work so let's look at。

that a little more carefully。

![](img/6b3f7f52a93a387f5aea7f58c9646547_129.png)

![](img/6b3f7f52a93a387f5aea7f58c9646547_130.png)

I've got order log in search calls we，just deduced that I've just repeated it。

here right on each call I'm reducing the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_132.png)

size of the list in half so it goes from，n to n over 2 to n over 4 to n over 8。

and over 16 I'll be done in the worst，case when I get down to having only a。



![](img/6b3f7f52a93a387f5aea7f58c9646547_134.png)

list of size one that takes log n steps，because n over 2 to the log n sent over。



![](img/6b3f7f52a93a387f5aea7f58c9646547_136.png)

N which is 1 but to set up the search，for each cell I've got to copy the list。

and the list starts out and long so in，principle I've got order and work to do。

to set up the recursive call and so by。

![](img/6b3f7f52a93a387f5aea7f58c9646547_138.png)

the things we saw last time I've got，order log in for the number of recursive。



![](img/6b3f7f52a93a387f5aea7f58c9646547_140.png)

calls times order and work inside of。

![](img/6b3f7f52a93a387f5aea7f58c9646547_142.png)

each call and that's order n log n so，it's not what I wanted，now if you're thinking about this。



![](img/6b3f7f52a93a387f5aea7f58c9646547_144.png)

carefully you'll realize on each step，I'm not actually copying the whole list。



![](img/6b3f7f52a93a387f5aea7f58c9646547_146.png)

I'm copying half the list and then 1/4，of the list and then 1/8 of the list so，going。

do the math here in fact what we'll see，and if you like you in your copious。



![](img/6b3f7f52a93a387f5aea7f58c9646547_148.png)

spare time you can go off and work this，through what you'll discover is that。

you're actually doing order and work to，do the copying but that's still the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_150.png)

problem because then I got something，that's order n plus log in and the N is。

going to dominate so this is still，linear sounds like I led you down a。

primrose path here can we fix this sure。

![](img/6b3f7f52a93a387f5aea7f58c9646547_152.png)

because we could do the following we，could say when I want to look at that。



![](img/6b3f7f52a93a387f5aea7f58c9646547_154.png)

list do I need to copy everything what，about if instead I said here's the。

beginning and the end of the list when I，test the middle I'll move one of the。

pointers to the middle of the list when，I test the middle again I'll move。

another pointer in so in other words I，can test the middle and based on that I。

could say I only need to search this，part of the list just keep track of that。

point and that point in the list and，when I test the middle again same idea。

now I'm not actually copying the list，I am simply keeping track of where the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_156.png)

pieces of the list that bound my search，ha all right I'm still reducing the size。

of the problem by a factor of two at，each step that's great all I need to do。

now though is just keep track of which。

![](img/6b3f7f52a93a387f5aea7f58c9646547_158.png)

portion of the list I'm searching I'm，going to avoid copying the list so the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_160.png)

number of recursive calls a game will be，logarithmic let's see if that actually。



![](img/6b3f7f52a93a387f5aea7f58c9646547_162.png)

fixes my problem a little bit of code，not as bad as it looks I've got an。



![](img/6b3f7f52a93a387f5aea7f58c9646547_164.png)

internal function here then I'm going to，come back to but let's look at what。

happens in this case I'm going to say，game if there's nothing in the list just。

return false element can't possibly be，there otherwise call this function with。

the list the element for whom I'm，searching in the beginning and end of。

the list so zero at one inch length，around L minus one at the other and it's。

just that idea of I'm keeping track of，the two pieces okay now let's look at。

what this does says here's the low part，of the list the high part of the list。

initially it's zero and length of list，minus one it says if they are the same。



![](img/6b3f7f52a93a387f5aea7f58c9646547_166.png)

cool then I've got a list of length one，just test to see if it's the thing I'm。

looking for if they're not find the，midpoint and the midpoints just the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_168.png)

average of lo plus high integer division，by to think about if it's zero and n。

midpoint is in over two but if it's for，example n over 2 and n midpoint is 3/4。

in so that mid picks the middle point if，it's the thing I'm looking for great I'm。

done otherwise check to see is the thing，at the middle bigger than or less than。

the thing I'm looking for and based on，that I'm going to skip this one for a。

second I'm either going to search，everything from the low point up to the。

middle point or from the middle point up。

![](img/6b3f7f52a93a387f5aea7f58c9646547_170.png)

to the high point and the last piece，here is if in fact the low point in the。

middle point are the same I got a list，of size 1 there's nothing left to do I'm，done okay。

I know it's a lot of code it would，invite you just to walk through it but I。

want to take you back again to simply。

![](img/6b3f7f52a93a387f5aea7f58c9646547_172.png)

this point and say here's what we're，doing we're starting off with pointers。

at the beginning and end of the list，we're testing the middle point on based。

on that we're giving a call we're now，the pointer is to the beginning in the。

middle of the list simply passing it，down and same as I go through all of。

these pieces so that code now gives me，what I'd like because here in the。

previous case I had a cost the cost was。

![](img/6b3f7f52a93a387f5aea7f58c9646547_174.png)

to copy the list in this case it's，constant because what am i doing I'm。

passing in 3 values and what does it。

![](img/6b3f7f52a93a387f5aea7f58c9646547_176.png)

take to compute those values is a，constant amount of work because I'm。

simply computing mid right there just，with an arithmetic operation and that。



![](img/6b3f7f52a93a387f5aea7f58c9646547_178.png)

means order log n steps because they，keep reducing the problem in half and。

the cost at each point is constant and，this is as a consequence a really nice。

example of a logarithmic complexity，function now if you think about it I'm。



![](img/6b3f7f52a93a387f5aea7f58c9646547_180.png)

cheating slightly second time today，because we said we really，don't care about the implementation we。

want to get a sense of the complexity，the algorithm and that's generally true。

but here is a place in which the，implementation actually has an impact on。

that complexity and I want to be，conscious of that as I make these。

decisions but again logarithmic in terms，of number of steps constant work for。

each step because I'm just passing in。

![](img/6b3f7f52a93a387f5aea7f58c9646547_182.png)

values and as a consequence the over，algorithm is log notice one other thing。

I said I want you to see characteristics。

![](img/6b3f7f52a93a387f5aea7f58c9646547_184.png)

of algorithms that tell you something，about the complexity of that algorithm。



![](img/6b3f7f52a93a387f5aea7f58c9646547_186.png)

something that's iterative and reduces，the problem by size 1 each time from n。

to n minus 1 to n minus 2 linear，something that reduces the size of the。

problem in half or in thirds or in。

![](img/6b3f7f52a93a387f5aea7f58c9646547_188.png)

quarters each time logarithmic generally，unless I've got a hidden cost somewhere。



![](img/6b3f7f52a93a387f5aea7f58c9646547_190.png)

here's another little example just to，give you a sense of log I want to。

convert an integer to a string I know I，can just call STR on it but how might we。

do that inside of the machine well，here's a nice little algorithm for it。

I'm going to set up something I call，digits it's just a string of all the。

digits if the thing I'm trying to，convert is 0 I just return the string 0。

otherwise let's run through a little。

![](img/6b3f7f52a93a387f5aea7f58c9646547_192.png)

loop where I take that integer divided。

![](img/6b3f7f52a93a387f5aea7f58c9646547_194.png)

by 10 the remainder of that what is that，oh that's the zeroth or the 1 order of。

the first order bit and I'm going to，index into digits to find that and I'm。



![](img/6b3f7f52a93a387f5aea7f58c9646547_196.png)

going to add it on to a string that I'm。

![](img/6b3f7f52a93a387f5aea7f58c9646547_198.png)

dealing and it'll divide I by 10 so this，has given an integer I want to convert。

it to a string I divide the integer by，10 take the remainder that gives me the。

zeroth or the if you like the ones，element I index into the string and I。

record it and then I add it to what I。

![](img/6b3f7f52a93a387f5aea7f58c9646547_200.png)

get by dividing I by 10 and doing the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_202.png)

same thing so I'll just walk down each，of the digits converting it into a。



![](img/6b3f7f52a93a387f5aea7f58c9646547_204.png)

string what I care about is the order，growth here this is all constant all。

to worry about here is how many times do，I go through the loop and inside of the。

loop this is just constant it doesn't。

![](img/6b3f7f52a93a387f5aea7f58c9646547_206.png)

depend on the size of the integer so how，many times do I go through the loop well。

how many times can I divide I by 10 and，that's log of I right so it's not I。

itself it's not the size of the integer，it's the number of digits in the integer。

and here's another nice example of log。

![](img/6b3f7f52a93a387f5aea7f58c9646547_208.png)

I'll point you again right here and，reduce think the size of the problem by。

constant factor in this case by 10 each。

![](img/6b3f7f52a93a387f5aea7f58c9646547_210.png)

time nice characteristic of a，logarithmic algorithm okay we've got。

constant we've got log about linear we，saw it last time right something like。

searching a list in sequence was an，example of something that was linear in。

fact most of the examples we saw last。

![](img/6b3f7f52a93a387f5aea7f58c9646547_212.png)

time were things with iterative loops so，for example fact written it iteratively。

factorial write n times n minus 1 times，n minus 2 all the way down to 1 I set。

product to 1 I go for a loop where I，goes from 1 update n minus 1 or just。

below n minus 1 incrementally，multiplying product by I and restoring。

that back away again we know that this，loop here how many times do I go through。

it go through it n times the cost inside，the loop there are three steps changing。

I am multiplying product times I am，storing that value back and product and。



![](img/6b3f7f52a93a387f5aea7f58c9646547_214.png)

as we saw that constant doesn't matter，this is linear so n times around the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_216.png)

loop constant costs each time order n，what about recursive I could write fact。



![](img/6b3f7f52a93a387f5aea7f58c9646547_218.png)

recursively I actually prefer it this，way right fans less than or equal to 1。

return 1 otherwise multiply and by，whatever I get by calling this on n。



![](img/6b3f7f52a93a387f5aea7f58c9646547_220.png)

minus 1 the cost inside the loop is just，constant I'm doing one subtraction one a。

multiplication how many times do I go，through it again n times because I got。

to go from n to n minus 1 to n minus 2，so again this is linear。



![](img/6b3f7f52a93a387f5aea7f58c9646547_222.png)

now if you were to time it you'd，probably see a difference，my guess is I'm sure professor good。



![](img/6b3f7f52a93a387f5aea7f58c9646547_224.png)

tackle correct me if I get it wrong is，that the factorial one probably takes a。

little more time because you've got to，set up the frame for the recursive call。

but in terms of what we care about，they're the same they're both linear。

they're order N and so interestingly，both iterative or recursive factorial。



![](img/6b3f7f52a93a387f5aea7f58c9646547_226.png)

have same order of growth gain I want。

![](img/6b3f7f52a93a387f5aea7f58c9646547_228.png)

you to notice what's the key here。

![](img/6b3f7f52a93a387f5aea7f58c9646547_230.png)

reducing the size of the problem by 1 is，indicative generally of something that's。



![](img/6b3f7f52a93a387f5aea7f58c9646547_232.png)

going to have linear growth I say in，general if it's a loop inside of a loop。

as we saw it might be a little bigger。

![](img/6b3f7f52a93a387f5aea7f58c9646547_234.png)

but this is generally linear constant，log linear log linear that is n log n。



![](img/6b3f7f52a93a387f5aea7f58c9646547_236.png)

we're going to see this next time I'm，simply going to push it ahead which。

invites you to come back on Wednesday。

![](img/6b3f7f52a93a387f5aea7f58c9646547_238.png)

and see this it's actually something，that's a really powerful algorithm it's。

going to be really useful we're going to，look at something called merge sort。

which is a very common sorting algorithm，and has that property being log linear。



![](img/6b3f7f52a93a387f5aea7f58c9646547_240.png)

so we'll come back to this next time，about polynomial well we saw this last。

time as well this commonly occurs when，we have nested loops or where we have。

nested recursive function calls nested，loop meaning I'm looping over some。

variable and inside of there I got，another loop and what we saw is the。

outer loop if it's a standard lid，iterative thing will be linear but。

inside of the loop I'm doing a linear，amount of work each time so it becomes n。



![](img/6b3f7f52a93a387f5aea7f58c9646547_242.png)

times n so order N squared ok。

![](img/6b3f7f52a93a387f5aea7f58c9646547_244.png)

exponential these are things sorry yes I，did that right I'm going to go back to。

the exponential these are things that。

![](img/6b3f7f52a93a387f5aea7f58c9646547_246.png)

we'd like to stay away from but，sometimes we can and the common。

characteristic here is when we brought a，recursive function where there's more。



![](img/6b3f7f52a93a387f5aea7f58c9646547_248.png)

than one recursive call inside the，problem。

![](img/6b3f7f52a93a387f5aea7f58c9646547_250.png)

remember towers of Hanoi that wonderful，demonstration I did I was tempted to。

bring it back because it's always fun to，get a little bit of applause when I do。

it but I won't do it this time but I，remember we，look at that problem-solving the towers。

of Hanoi how do I move a stack of size n，of different sized disks from one peg to。

another where I can only move the top，disk onto another one I can't cover up a。

smaller disk I want to remind you we saw，there was a wonderful recursive solution。

to that it said move a stack of size n，minus 1 under the spare peg move the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_252.png)

bottom one and then move that stack over，onto the thing you were headed towards。

okay what's the complexity of them while，I'm going to show you a trick for。

figuring that out it's called a，recurrence relation for a very，deliberate reason but it'll give us a。

little handy way to think about what's，the order of growth here so I'm going to。



![](img/6b3f7f52a93a387f5aea7f58c9646547_254.png)

let T sub n denote the time it takes to，move a tower of size n and I want to get。

an expression for how much time is that。

![](img/6b3f7f52a93a387f5aea7f58c9646547_256.png)

going to take what do I know I know，that's 2 times T to the N minus 1 right。

I got to move a stack of size 1 less，onto the spare peg and then one to move。

that bottom thing over and then whatever，it takes me to move a stack of size n。

minus 1 over to that peg okay so how，does that help me，well let's play the same game what's T。



![](img/6b3f7f52a93a387f5aea7f58c9646547_258.png)

of n minus 1 oh that's 2 T of n minus 2，plus 1 just substituting and I'm using。

exactly the same relationship here all，right let's just do a little math on。

that that's 4 T to the n minus 2 plus 2，plus 1 and you're still going ok who。

cares well let's do the same thing one，more time T of n minus 2 that's 2 T of M。

minus 3 plus 1 Oh see the pattern you，can start to see you two merge here。

right each time I reduce this I'm adding，another power of 2 and I'm increasing。

the coefficient up front and so in fact，after K steps I'll have 1 plus 2 plus 4。

all the way up to 2 to the K minus 1。

![](img/6b3f7f52a93a387f5aea7f58c9646547_260.png)

plus 2 to the K times T sub n minus K，hopefully you can see it if you just。

look at this expression is，all of those up there I'm just pulling。

it out each time when am i done when，this is size zero when K is equal to M。



![](img/6b3f7f52a93a387f5aea7f58c9646547_262.png)

and so that's when I get that expression，if this is going by too fast just walk。

it through yourself later on but I'm，literally just using this expression to。

do the reduction until I see the pattern。

![](img/6b3f7f52a93a387f5aea7f58c9646547_264.png)

all right what's that well if you're a，course 18 major you've seen it before if。



![](img/6b3f7f52a93a387f5aea7f58c9646547_266.png)

you haven't here's a nice little trick，let me let a equal that sum 2 to the N。

minus 1 plus 2 to the n minus 2 all the，way down to 1 let me multiply both the。

left and the right side by 2 that gives，me 2 a is equal to 2 to the n plus 2 to。

the n minus 1 all the way down to 2 I'm，just taking each of the terms。

multiplying them by 2 now subtract this，from that and on the left side you get a。

and on the right side you get that term。

![](img/6b3f7f52a93a387f5aea7f58c9646547_268.png)

these all cancel out minus 1 geometric，series cool。



![](img/6b3f7f52a93a387f5aea7f58c9646547_270.png)

so that sum is just 2 to the n minus 1，and if I plug that back in there ah I've。



![](img/6b3f7f52a93a387f5aea7f58c9646547_272.png)

got my order growth exponential 2 to the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_274.png)

N okay I was a math physics undergrad，I'd like these kinds of things but I。

wanted you to see how we can reason。

![](img/6b3f7f52a93a387f5aea7f58c9646547_276.png)

through it because this is letting us，see the growth what I want you to pull。

away from this is notice the，characteristic and towers of Hanoi want。

to do another example in a second the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_278.png)

characteristic was at the recursive step，I had not one but two recursive calls。

and that is characteristic of something，with exponential growth which I just saw。



![](img/6b3f7f52a93a387f5aea7f58c9646547_280.png)

here two to the N that by the way I，remind you the story of towers have on。



![](img/6b3f7f52a93a387f5aea7f58c9646547_282.png)

our towers of Hanoi right when the，priests in that temple moved the entire。



![](img/6b3f7f52a93a387f5aea7f58c9646547_284.png)

stack from one peg to another we all，reached Nirvana and the world ends n is。

equal to 64 here go figure out what 2 to。

![](img/6b3f7f52a93a387f5aea7f58c9646547_286.png)

the 64 is and if you're doing one move，per second which they will I think we're。

certainly going to be here awhile before。

![](img/6b3f7f52a93a387f5aea7f58c9646547_288.png)

the universe ends and we reached Nirvana，probably，several times over we are new vonner。

word MIT you're right John but we're，worrying about the rest of the world so。

okay we'll keep moving on Nirvana will，be next week when they do the quiz John。

so we'll keep moving quickly all right I，want to show you one more example it's a。

cool problem for math but mostly to see，that characteristic of exponential。

growth and then we're going to pull all，of this together this is something。

called the power set so if I have a set，of things well let's assume I have a set。



![](img/6b3f7f52a93a387f5aea7f58c9646547_290.png)

of integers with no repeats so 1 through，n 1 2 3 4 for example I want to generate。



![](img/6b3f7f52a93a387f5aea7f58c9646547_292.png)

the collection of all possible subsets。

![](img/6b3f7f52a93a387f5aea7f58c9646547_294.png)

so subsets with no elements with one，element with two elements with three。



![](img/6b3f7f52a93a387f5aea7f58c9646547_296.png)

months all the way up to n elements so，for example if my set is 1 through 4。

then the power set would be the empty，set with no elements in it all of the。

instances with 1 element all of them。

![](img/6b3f7f52a93a387f5aea7f58c9646547_298.png)

with 2 all over 3 and all of them with 4，I'd like to write code to generate this。

it's actually a handy problem in number，theory or in set theory by the way the。

order doesn't matter I could do it this，way but this would be a perfectly。

reasonable way of generating it as well，and I'm going to come back to that in a。

second as we think about solving this，the question is how would I go about。



![](img/6b3f7f52a93a387f5aea7f58c9646547_300.png)

finding all of these I'm going to use。

![](img/6b3f7f52a93a387f5aea7f58c9646547_302.png)

well could stop and say you can imagine，writing a big iterative loop you start。



![](img/6b3f7f52a93a387f5aea7f58c9646547_304.png)

with N and you decide do I include it or，not and then you still go to n minus 1。

do I include it or not you could think。

![](img/6b3f7f52a93a387f5aea7f58c9646547_306.png)

about writing a big loop that would，generate all of these actually a bunch。

of nested loops but there's a nice。

![](img/6b3f7f52a93a387f5aea7f58c9646547_308.png)

recursive solution and I want you，encourage you to think that ways so。

here's the way I'm going to do it what。

![](img/6b3f7f52a93a387f5aea7f58c9646547_310.png)

do we do when we said we want to think，recursively we say let's assume we can。

solve a smaller size problem if I want，to generate the power set of all the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_312.png)

integers from one day and I'm going to，assume that I can generate the power set。



![](img/6b3f7f52a93a387f5aea7f58c9646547_314.png)

of integers from 1 to n minus 1 if I，have that solution then I can construct。

the solution to the bigger problem，really easily Wow well all of the things，that were in。

that solution to the smaller problem，have to be part of the solution to the。

bigger problem there are all subsets of。

![](img/6b3f7f52a93a387f5aea7f58c9646547_316.png)

1 to n because they're all subsets of 1，to n minus 1 so I'm going to add all。

those in and then I'm going to say let's，take each one of those and add em to。

each of those subsets because that gives，me all the rest of the solutions I've。



![](img/6b3f7f52a93a387f5aea7f58c9646547_318.png)

got all the ways to find solutions，without n I get all the ways to find。



![](img/6b3f7f52a93a387f5aea7f58c9646547_320.png)

solutions with him that may sound like a，lot of gobbledygook let me show you the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_322.png)

example there is the power set of the，empty set it's just the empty set to get。

the power set of 1 I include that and I，include a version of everything there，with 1 added to it。

there's the power set of 1 now given，that how do I get the power set of 2。

well both of those are certainly things，I want and for each one of them let me。

just add 2 if you look at that right，that's the set of all ways of getting。

nothing one two or both of them and you，get the idea now having that solution I。

can get the solution for three because，all of those have to belong and I simply。



![](img/6b3f7f52a93a387f5aea7f58c9646547_324.png)

add 3 to each one of those oh that's，cool right all right you don't have to。

be a math geek to admit it's cool it is，kind of cool because it says G got a。

solution to the salt smaller problem，generating the next piece is a natural。

step you can also see the size of that，sets doubling each time because to get。

to 4 I'm going to add everything into。

![](img/6b3f7f52a93a387f5aea7f58c9646547_326.png)

all of those pieces really nice。

![](img/6b3f7f52a93a387f5aea7f58c9646547_328.png)

recursive description let's write some，code so I'll hand that out to you but。

here's the code and I'm going to walk，through it carefully and then we're。

going to analyze it but it's actually，for me a beautiful piece of code I did。

not write it by the way John did but，it's a beautiful piece of code I want to。

generate all the subsets or the power，set of some list of elements here's how。

I'm going to do it I'm going to set up，some internal variable called res ok and。

then what am I going to do，actually I don't know why put residen，back。

- that if the list is empty length of，the list is zero I'm going to just。

return that solution and this is not a，typo what is that funky thing there it。

is a list of one element which is the，empty list which I need because the。

solution in this case is a set with，nothing in it so there is the thing I。

returned in the base case otherwise what，do I do I take all the elements of the。

list except the last one and I call it，recursively I generate all of the。

subsets of that perfect I'm going to，call that smaller I then take the last。

element and I make a list of just the，last element and what did I say I need。

to do I need all of these guys plus I，need all of them where I add that。

element in oh nice I'll set up new as a，variable here and I'll loop over all of。

the elements from the smaller problem，where I basically add that list to that。



![](img/6b3f7f52a93a387f5aea7f58c9646547_330.png)

list and I put it into new that's simply，taking all of the solutions of subsets。

of up to M minus 1 and creating a new，set of subsets where N is included in。

every one of them and now I take this，and I take that I penned them or。



![](img/6b3f7f52a93a387f5aea7f58c9646547_332.png)

concatenate them rather shouldn't say，append them concatenate them together。



![](img/6b3f7f52a93a387f5aea7f58c9646547_334.png)

and return it that's a crisp piece of，code and I'm sorry John I have no idea。

where I put res up there I don't think I，need that anywhere in this code and I。

won't blame it on John it was my recopy，of the code sorry maybe right look I。

know I'm flaming at you I get to do it，I'm tenured as I've said multiple times。

in this course that's a cool piece of。

![](img/6b3f7f52a93a387f5aea7f58c9646547_336.png)

code imagine trying to write it with a，bunch of loops iterating over indices。



![](img/6b3f7f52a93a387f5aea7f58c9646547_338.png)

good luck you can do it maybe be on the，quiz actually note one that's way too。



![](img/6b3f7f52a93a387f5aea7f58c9646547_340.png)

hard to ask but it's a cool piece of，code because I can look at it and say。



![](img/6b3f7f52a93a387f5aea7f58c9646547_342.png)

what's the solution solve the smaller，problem and then given that take every。

one of the things in that smaller。

![](img/6b3f7f52a93a387f5aea7f58c9646547_344.png)

problem add that，element into that and put the two pieces。



![](img/6b3f7f52a93a387f5aea7f58c9646547_346.png)

together wonderful okay with that in，mind let's see if we can figure out the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_348.png)

complexity of this up here that's，constant that's okay right there I've。

got the recursive call so I know first，of all that this is going to call itself。

n times right because each stage reduces，the size of the problem by one so if I'm。

trying to get the power set of n I'm，going to have to do it to get n minus 1。

and then n minus 2 so I know the，recursion of GN subsets to Gen subsets。

this is going to go around n times，that's not so bad but right down here。

I've got to figure out what's the cost，of this right this is constant that's。

setting up is constant that's constant。

![](img/6b3f7f52a93a387f5aea7f58c9646547_350.png)

but there I've got another loop and the，loop depends on how big smaller is and。



![](img/6b3f7f52a93a387f5aea7f58c9646547_352.png)

smaller is a bad choice of term here，because it's going to grow on me but。

let's think about it by the way I'm。

![](img/6b3f7f52a93a387f5aea7f58c9646547_354.png)

assuming a pendous constant time which，generally it is the time I need to solve。

this problem includes the time to solve，the smaller problem that recursive call。

I know that's going to be linear but I，also need the time it takes to make the。

copy of all the things in that smaller。

![](img/6b3f7f52a93a387f5aea7f58c9646547_356.png)

version so how big is that Oh crud，number two number of things in the。

powerset grows as a factor of two right，if I got something you know one through。

three I've got all the things with，nothing in it all the things with one is。

it all the things with two things in it，all the things with three things in it。

that's eight and each time around I'm。

![](img/6b3f7f52a93a387f5aea7f58c9646547_358.png)

doubling the size of it so for a set of，size K there are 2 to the K cases and。

that says that this loop right here is，going to be growing exponentially。

because I got to go down that entire。

![](img/6b3f7f52a93a387f5aea7f58c9646547_360.png)

list to find all of the pieces so what's，the overall complexity I'm going to play。

the same game let's let T sub n capture，the time it takes to solve a problem of，size n。



![](img/6b3f7f52a93a387f5aea7f58c9646547_362.png)

just temporarily I'm going to let S sub，n denote the size of the solution for a。



![](img/6b3f7f52a93a387f5aea7f58c9646547_364.png)

problem of size n how big is that things，smaller and what do I know。



![](img/6b3f7f52a93a387f5aea7f58c9646547_366.png)

the amount of time it takes me to solve，the problem of size n it's the amount of。



![](img/6b3f7f52a93a387f5aea7f58c9646547_368.png)

time it takes me to solve the slightly，smaller problem that's the recursive。

call to Gen sub sets plus the amount of，time it takes me to run over that loop。

looking at everything and smaller and，adding in a new version plus some。

constant C which is just the number of，constant operations the constant steps。

inside that loop okay and if I go back，to it T sub n is cost here T sub n minus。

1 is the cost there a sub n is the size，of this and then I got one two three。

four five constant steps so C is，probably five in this case so what can I。

say there's the relationship because I，know s then minus one is two to the N。

minus one there are two to the n minus。

![](img/6b3f7f52a93a387f5aea7f58c9646547_370.png)

one elements inside of that how do I，deal with this let's play the same game。



![](img/6b3f7f52a93a387f5aea7f58c9646547_372.png)

what's T sub n minus one that's T of n，minus two plus two to the N minus two。

plus C and I could keep doing this you，can see what the pattern is going to。

look like I'm going to have K times C，constant steps for each reduction I'm。

going to get another power of two and，I'm going to reduce this overall term。



![](img/6b3f7f52a93a387f5aea7f58c9646547_374.png)

after K steps to T to the N minus K when。

![](img/6b3f7f52a93a387f5aea7f58c9646547_376.png)

am I done when that's down to something，of size zero and there's the expression。

and what you can see is what I wanted，you to see order in our sorry order two。



![](img/6b3f7f52a93a387f5aea7f58c9646547_378.png)

to the N is exponential in the size of，the problem what's the characteristic。

something that has a recursive call so I，multiple recursive calls that each step。

is likely to lead to exponential but。

![](img/6b3f7f52a93a387f5aea7f58c9646547_380.png)

that can also be buried inside of how I，grow the size of the problem and that。



![](img/6b3f7f52a93a387f5aea7f58c9646547_382.png)

was the case here there's only one，recursive call，but that loop grows in size each time。



![](img/6b3f7f52a93a387f5aea7f58c9646547_384.png)

around so the complexity is exponential。

![](img/6b3f7f52a93a387f5aea7f58c9646547_386.png)

I'm going to pull this together I said，one of the things I'd like you to start。

to recognize is what are the，characteristics of a choice and，algorithm that leads to a particular。



![](img/6b3f7f52a93a387f5aea7f58c9646547_388.png)

complexity class and you now have some，of them the code doesn't depend on the。

size of the problem that's constant and，in fact we've been using that as we look。

at pieces of the code if we can reduce，the problem set in this case by half。



![](img/6b3f7f52a93a387f5aea7f58c9646547_390.png)

each time by some constant factor from n，to n over 2 to n over 4 to n over 8 that。

tends to be characteristic unless，there's a hidden cost somewhere else。

of a logarithmic algorithm these are。

![](img/6b3f7f52a93a387f5aea7f58c9646547_392.png)

really nice simple things that reduce，the size of the problem by one at each。

step an iterative call that goes from n，to n minus 1 and then to n minus 2 and。

then to n minus 3 characteristic of，linear algorithms log linear we're going。

to see next time polynomial typically。

![](img/6b3f7f52a93a387f5aea7f58c9646547_394.png)

quadratic and squared when we have，nested loops or nested recursive calls。



![](img/6b3f7f52a93a387f5aea7f58c9646547_396.png)

looping over something inside of there，and looping over something else on a。

size that depends on the size of the。

![](img/6b3f7f52a93a387f5aea7f58c9646547_398.png)

problem and then we just saw this last，when multiple recursive calls at each。



![](img/6b3f7f52a93a387f5aea7f58c9646547_400.png)

level tends to be characteristic of，exponential and as I said we'd like to。



![](img/6b3f7f52a93a387f5aea7f58c9646547_402.png)

be as high up in this list as we can，because those are really nice algorithms。



![](img/6b3f7f52a93a387f5aea7f58c9646547_404.png)

to have let me give you one more example，I'm looking at this and then we'll be。



![](img/6b3f7f52a93a387f5aea7f58c9646547_406.png)

done fibonacci standard problem right，the nth Fibonacci number is the sum of。

the previous two Fibonacci numbers this，was the example we saw of multiplying。

rabbits if you like here's an iterative，version of Fibonacci just as if n is。

zero it's just zero if it's 1 it's just，1 otherwise I'm going to set up。

initially the two previous Fibonacci，numbers and then I'm just going to run。

through a loop where I temporarily keep，track of that number I move the second。

previous one into the last previous one。

![](img/6b3f7f52a93a387f5aea7f58c9646547_408.png)

I add those two that becomes the second，previous number and I just keep running。



![](img/6b3f7f52a93a387f5aea7f58c9646547_410.png)

through that loop you can go run it you，see it does the right thing what I want。

to look at is the complexity so that's。

![](img/6b3f7f52a93a387f5aea7f58c9646547_412.png)

constant，constant that's linear because the work，inside the loop is constant but I'm。

doing it n times so this is nice water，so I should say the bottom thing is。

constant the overall algorithm the worst。

![](img/6b3f7f52a93a387f5aea7f58c9646547_414.png)

case is just order n great what about。

![](img/6b3f7f52a93a387f5aea7f58c9646547_416.png)

the recursive version for me this is，much nicer code it's nice and clean it。

says of n is equal to zero fib of 0 0 if，that is equal to 1 fib of 1 or the first。

and second Fibonacci numbers of 0 1，otherwise just return what I get by。



![](img/6b3f7f52a93a387f5aea7f58c9646547_418.png)

summing both of those pieces and you can，probably already guess what the。

complexity is going to be here right，because I've now got two recursive calls。



![](img/6b3f7f52a93a387f5aea7f58c9646547_420.png)

inside of this call so one way to think。

![](img/6b3f7f52a93a387f5aea7f58c9646547_422.png)

about it is if I'm going to solve the，problem up here I've got to solve two。

versions of the problem below which has，got to solve two versions of the problem。

below and in general this is going to be。

![](img/6b3f7f52a93a387f5aea7f58c9646547_424.png)

exponential 2 to the n now you say wait。

![](img/6b3f7f52a93a387f5aea7f58c9646547_426.png)

a minute I was paying attention with，this guy was yeah Turing on a couple of。

weeks ago honest I was and in fact what，we saw was that fib isn't balanced in。



![](img/6b3f7f52a93a387f5aea7f58c9646547_428.png)

terms of how it goes right it's not that，on the right-hand side of the tree I。

have to solve all of those portions。

![](img/6b3f7f52a93a387f5aea7f58c9646547_430.png)

because the problem gets smaller does，that change the complexity well the。

answer is it changes the base but it's，actually still exponential and if you。

want to go look this up I'm sure you can，find you know Wikipedia very quickly。

this actually has a very cool，exponential growth it's the golden ratio。



![](img/6b3f7f52a93a387f5aea7f58c9646547_432.png)

to the nth power and in fact I encourage，you to go look at it and even more。

copious spare time you have it's a very，cool proof to see it but the bottom line。

is while we can do a little bit better，than 2 to the N it still grows。



![](img/6b3f7f52a93a387f5aea7f58c9646547_434.png)

exponentially within so what do we have，we got Big O notation as a way of。

talking about comparing efficiency of，algorithms what I want you to see here。

is that you ought to be able to，begin to reason about what's the cost of。

an algorithm by recognizing those common，patterns I keep saying it but it's going。

to be really valuable to you and you，should be able to therefore work the。

other direction when you're given a new，problem how do I get this into a linear。

algorithm if I can log linear if I can，we'd be really great but if you know I。

can't how do I stay away from，exponential algorithms and finally what。

we're going to show later on is that in，fact there are some problems that as far。

as we know are fundamentally exponential，and they're expensive to compute the。



![](img/6b3f7f52a93a387f5aea7f58c9646547_436.png)

very last thing is you might have，decided I was cheating in a different。

way so I'm using a set of built-in，Python functions I'm not going to go。

through all of these but this is just a，list for example for lists of what the。

complexity of those built-in functions，are and if you look through the list。

they kind of make sense you know，indexing you can go straight to that。

point computing the length you compute，it once you've stored it comparison。

order n because I got to compare all the，elements of the list similarly to remove。

something from the list I got to find，where it is in the list and remove it。

worst case that's going to be order in，so you can see that these operations are。

typically linear in the size of this，these are constant for dictionaries。

remember dictionaries were this nice，thing they weren't ordered it gave me a。

power in terms of storing them but as a，consequence some of the costs then go up。

for a list indexing going to a，particular point I just go to that spot。

and retrieve it indexing into a。

![](img/6b3f7f52a93a387f5aea7f58c9646547_438.png)

dictionary I have to find that point in，the dictionary that has the key and get。

the value back so that's going to be。

![](img/6b3f7f52a93a387f5aea7f58c9646547_440.png)

linear because I have to in principle，walk all the way down it it's a slight。



![](img/6b3f7f52a93a387f5aea7f58c9646547_442.png)

misstatement as we'll see later on a，dictionary actually uses a clever。

indexing scheme called a hash but in the，worst case this is going to be linear so。

you see a trade-off for dictionaries I，get more power I get more flexibility。



![](img/6b3f7f52a93a387f5aea7f58c9646547_444.png)

but it comes as a cost and so these，basically are what let me reason on top。

of the things I've been doing to figure，out complexity and next time we'll do。



![](img/6b3f7f52a93a387f5aea7f58c9646547_446.png)