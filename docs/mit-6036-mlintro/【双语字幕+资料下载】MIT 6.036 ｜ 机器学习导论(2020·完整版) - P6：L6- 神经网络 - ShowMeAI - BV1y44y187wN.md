# 【双语字幕+资料下载】MIT 6.036 ｜ 机器学习导论(2020·完整版) - P6：L6- 神经网络 - ShowMeAI - BV1y44y187wN

![](img/e3bbdee916775b6931caeacad960048d_0.png)

good morning let's get started on，today's lecture。

![](img/e3bbdee916775b6931caeacad960048d_2.png)

um so in our previous，lectures uh we've been talking about all，of these different hypothesis classes。

and how to learn in them，in particular we talked about linear。

classification and linear regression and，we also talked about how you can get。

um these really interesting boundaries，and classification and really，interesting。

regression um curves by choosing，different features，um by choosing not just sort of our。



![](img/e3bbdee916775b6931caeacad960048d_4.png)

default x1 and x2 and x3 but actually，having，different features and we're going to。

sort of explore more of that today we're。

![](img/e3bbdee916775b6931caeacad960048d_6.png)

going to look at，a potential set of features that we，could use based on step functions。

and that'll lead us to discussing neural，nets as a hypothesis class。



![](img/e3bbdee916775b6931caeacad960048d_8.png)

and learning in neural nets analogous to，what we did for both，linear classification and linear。



![](img/e3bbdee916775b6931caeacad960048d_10.png)

regression，okay so let's just review briefly what，we did，with linear classification with the。

default feature so when i say default，features i mean just，x1 x2 we haven't applied any additional。

transformations here，okay so we have a bunch of data and what，we saw。

in a previous lecture is that a way that，we could approach，uh classifying this data is we could。

look at a certain set of functions，in a slightly higher dimensional space，so here we have x1。

x x1 on the sort of east-west axis，we have x2 on the north-south axis and，this additional z。

on sort of an up down axis and so we，could make。

![](img/e3bbdee916775b6931caeacad960048d_12.png)

this curve this theta transpose x plus，theta naught which is，linear in the thetas and also in this。

case happens to be linear in the x's，and we could ask ourselves um for any。

particular theta and theta naught。

![](img/e3bbdee916775b6931caeacad960048d_14.png)

where is this curve below zero and that，will give us，one of our labels you know maybe it's。

minus one and where is this curve，above zero and that's where we'll apply。

a different label maybe it's plus one，and so in general any particular theta。

and theta naught defines such a curve，which happens to be a hyperplane and。

therefore defines a set of predictions，where we apply，and predict uh plus one and where we。

predict minus one，and then what we'll do is we'll say okay，well that's a huge class。

um with all kinds of different thetas，and theta knots um but we'll try to get。

as low as possible loss。

![](img/e3bbdee916775b6931caeacad960048d_16.png)

to figure out which one will apply to，our particular data。



![](img/e3bbdee916775b6931caeacad960048d_18.png)

okay so we saw this picture before and，now，um we've also seen another picture we。



![](img/e3bbdee916775b6931caeacad960048d_20.png)

saw in in the features case that we，could do this and we can get these。

these more um complex non-linear，boundaries，here as well um so in particular one way。

that we could do that，that we saw um oh and and of course uh，again just just uh。

reiterating we predict uh one one，particular label on the side where this。

is greater than zero and a label，on the side where this is less than zero。



![](img/e3bbdee916775b6931caeacad960048d_22.png)

okay so now we can get these more，instance。

![](img/e3bbdee916775b6931caeacad960048d_24.png)

different types of features like one，example we saw was polynomial features。

so with polynomial features we said hey，phi，1 is now x1 phi 2 is x2，by 3 is x1 squared etc。

and so maybe i have a bunch of data and，maybe i don't think that there's a，really good。

single linear boundary here，so i might use my polynomial features。

and so we saw we could do the same thing，we can make this curve。



![](img/e3bbdee916775b6931caeacad960048d_26.png)

that is still linear in theta，so we might still call this linear。

classification it's just non-linear in。

![](img/e3bbdee916775b6931caeacad960048d_28.png)

the x so we have this still theta，transpose but now times phi of x。



![](img/e3bbdee916775b6931caeacad960048d_30.png)

instead of x plus theta naught and we're，going to predict，a label say minus one where this curve。

is below zero，and a different label say plus one where，the curve is above zero so it's the same。

thing it's just now a sort of more，interesting more complex curve。

okay so again we get a curve like that，for every possible theta and theta。

naught but then what we do is learning，we say，hey let's try to get as low of possible，loss。



![](img/e3bbdee916775b6931caeacad960048d_32.png)

so we'll use that to choose our theta，and theta naught，and that's what we'll apply to our data。

and then in particular used to predict，um at new points okay and so basically。

what we're going to be doing today is，we're going to be thinking about other。

possible features we could use，um there's nothing that says we have to，use polynomial features。

and in fact maybe something that we，have，a fixed set of features maybe we could，actually learn。

good features maybe the features，themselves could have，parameters that we learn and so that's。

essentially what we're going to be。

![](img/e3bbdee916775b6931caeacad960048d_34.png)

going into a lot of depth on today，now before we do that let me just um go，back。

to this picture here and let's just，notice that what's happening here is。

we're essentially applying a function，to apply this hypothesis to apply this，prediction。

for a particular theta and theta naught，we're predicting one label。

above a line and another label below the，line and so we could actually。

plot that function so here's that，function where we have one value。



![](img/e3bbdee916775b6931caeacad960048d_36.png)

on one side of the x1 x2 line and，another value on the other side so for，instance。



![](img/e3bbdee916775b6931caeacad960048d_38.png)

if we were predicting one and zero，the upper value here in in sort of the。



![](img/e3bbdee916775b6931caeacad960048d_40.png)

up down axis would be one and the lower，value，would be zero okay and so in particular。

another way that we could represent that，which we saw in a previous class is that，we could use。

um this indicator function remember the，idea here is that whatever's inside the，parentheses。

we're gonna return one if it's true and，zero if it's not，and so what we're doing here is we're。

actually plotting this indicator，function applied，to this to this linear boundary。



![](img/e3bbdee916775b6931caeacad960048d_42.png)

so we see that it's one on one side，where this is true。



![](img/e3bbdee916775b6931caeacad960048d_44.png)

and it's zero on the other side，okay so this is called the step function。

where we have sort of you know one on，one side and zero on the other side。

we're used to using step functions to，classify we've been doing this for。



![](img/e3bbdee916775b6931caeacad960048d_46.png)

essentially many uh classes now，and the really big difference about what。

we're gonna do today is we're going to，start using，step functions as features。

so we're still going to use them to。

![](img/e3bbdee916775b6931caeacad960048d_48.png)

classify but we're going to use them as，features。

![](img/e3bbdee916775b6931caeacad960048d_50.png)

okay so let's go ahead and check that，okay so we have some new features，there's step functions。

so because these are going to be，features let's give them，their own parameter names like let's say。

maybe w，transpose and w naught instead of theta，transpose and theta naught which is what。

we were using for，our classifier and，so this is a feature so i'm going to，call it phi 1。

 it's going to be our，first feature，and it's going to be some function of x。

because we've seen that that's what，features are they're just functions。

of x the original sort of default，features that we got in the beginning of，the data。

okay so let's draw this well depending，on my choice of w，and w naught i'm going to get something。

that looks like this and it's just that，breaking point that line。



![](img/e3bbdee916775b6931caeacad960048d_52.png)

that's going to be different depending，on how i choose w and w not。

but this is a feature it's a function of。

![](img/e3bbdee916775b6931caeacad960048d_54.png)

x it's something that we can use，as a feature and it's got this step。

um we can make another one of these and，we need to give it its own new，parameters。

so maybe let's call them w tilde and w，not tilde for the moment。

and again that's going to define sort of，where we break and on what side we get。

one and on what side we get zero，so this is just another feature it's。

just another function of x any function，of x could be our features。

um we happen to be choosing these at the，moment，and so now we have two features we have。

two functions of x that we can use as，features and so let's ask ourselves what。



![](img/e3bbdee916775b6931caeacad960048d_56.png)

would classification look like，with these features if i were to use。

these features for classification，okay well we've been doing linear，classification let's。

do linear classification again and what，i mean by that again is that we're doing。

something that's linear in the，parameters and the theta and theta，naught。

but now we have these interesting，features the phi's，in this case we have phi 1 and phi 2 and。

so this this function that i've just，written down the，z equals theta transpose phi of x plus。

theta naught this is nothing new this is，what we've been doing with，classification this whole time。

we've considered polynomial features，that's，new is one our new step function。

features we haven't considered step，function features before，and two our features themselves have。

parameters that's a little bit new we we，have not，done that before okay so let's see what。

what is this going to look like，well in our particular case we're，looking at two features。

and so if we write out what does this，dot product look like，there's going to be two components。

there's going to be our theta 1，times phi 1 or theta 2 times pi 2 plus，theta naught。

and then just so i can plot this i'm，going to choose some particular values。

of the thetas that'll be a particular，hypothesis whenever i choose all of my。

parameters to have a value that's one，hypothesis，later on i'm going to try to learn those。

parameters but here i'm just trying to，plot what do the hypotheses even look，like。

and so here's just an example set of，values，that i could use to plot my hypothesis。

okay and so once i have those values i，can go ahead and plot a hypothesis and，here we go。

so this is my hypothesis based on these，two features and this particular linear。

combination of these features，and again just as before what's，happening is。



![](img/e3bbdee916775b6931caeacad960048d_58.png)

we're having these labels so we're，applying a label of one。



![](img/e3bbdee916775b6931caeacad960048d_60.png)

somewhere and a label of zero somewhere，and we can find out what those are by。

sort of looking down from above so if we，z，axis we're gonna see where we apply the。

different labels so in one region of the，space in fact on，two different sides but wherever。

wherever you're seeing um that that，check pattern we're getting。



![](img/e3bbdee916775b6931caeacad960048d_62.png)

that we're gonna get a label of one in，this case，and in that in between part we're going。

to get a label of 0。so it's just like before where we say，hey we have this function。

we're going to ask where is that，function above 0 and where is it below 0。

that's where we're going to get our，label of 1 and our label of 0，respectively。

and what's different now is just we get，a different type of function this isn't。

a function that we saw when we did，vanilla linear classification。

this wasn't a function that we saw when，we did polynomial，linear classification with the。

polynomial features this is a new，function for a new set of features and。

it actually might be pretty useful so，just as an example of where you might。

want this kind of classifier，let's think about exoplanets so。



![](img/e3bbdee916775b6931caeacad960048d_64.png)

exoplanets again are these stars that，are outside of our solar system or sorry。

there are these planets that are around，stars that are not in our solar system。

and so one thing that we might want to，ask is which exoplanets are habitable。

you know which ones could could life，actually exist on，and if you look at this well there are a。

lot of different sizes of stars，that exist out in the world or out in，the。

universe and for each of those stars，if as the star gets bigger the habitable。

zone is going to be sort of farther out，because if you get too close to the star。

everything's going to be too hot if you，get too far away from the star。

everything's going to be too cold you，want to be in that like perfect little，goldilocks area。

and so this kind of hypothesis can，express that，that as the size of the star increases。

there's this nice little band of，distance，where things aren't too hot and aren't。

too cold and you know maybe。

![](img/e3bbdee916775b6931caeacad960048d_66.png)

life could exist on this star，and so from that perspective this is a，useful hypothesis to have。

you know we wouldn't want to just use a。

![](img/e3bbdee916775b6931caeacad960048d_68.png)

linear classifier for this because we，wouldn't be able to say that there's，that nice little band。

that's separate from everything else now，we have a little bit more。

um flexibility that we didn't have，before with，just a linear classifier now we have the。

ability to have sort of，you know two different divisions and to。

say something's happening on either side。

![](img/e3bbdee916775b6931caeacad960048d_70.png)

of them，okay so this is one，particular setting of these。



![](img/e3bbdee916775b6931caeacad960048d_72.png)

weights in the features，and one particular setting of，these theta and theta naught in the。

classifier but let's see what would，happen if we changed，those settings just a little bit。

remember the idea of hypothesis classes，different，shapes that we can get by changing our，parameters。

and so let's just change our parameters，a little bit and see what else might，happen。

so in particular let's look at this，first feature，what would happen if i change say the w。

and w naught well i'm gonna move around，the line，that defines where i'm labeling zero and。

where i'm labeling one in this feature，well if i do that then that's gonna，change。

my plot down here because it's still，this linear combination of future one，and feature two。

instead it's going to look like this。

![](img/e3bbdee916775b6931caeacad960048d_74.png)

so i've just changed one of my features，and that therefore changes my prediction。



![](img/e3bbdee916775b6931caeacad960048d_76.png)

here，and now when i look at it from above and，see what gets labeled one and what。



![](img/e3bbdee916775b6931caeacad960048d_78.png)

gets labeled zero it's going to look，different，i'm going to get a different kind of。



![](img/e3bbdee916775b6931caeacad960048d_80.png)

now we can do this with the other，feature too，so here's another feature here's our，second feature。



![](img/e3bbdee916775b6931caeacad960048d_82.png)

we could change the weights in the，second feature remember，you know we've seen this sort of thing。

before that these，the sort of normal and the offset，defines a line and so if we change。

those values we're going to change where，that line is and so we can do that。

too so here i just happen to have，changed it to a different set of values。

and now if we keep the same weights in，our final classifier，we're going to get something different。

now what happened here，in this case you'll notice there was，some overlap。



![](img/e3bbdee916775b6931caeacad960048d_84.png)

of the two features and because we're，just adding them up，we're going to get a value of 2 instead。



![](img/e3bbdee916775b6931caeacad960048d_86.png)

of just a value of one or zero，and that's fine i mean in general we，here。

for this linear combination but in the，end of the day，if we if we take this step function，down。

on this and we're going to ask where is。

![](img/e3bbdee916775b6931caeacad960048d_88.png)

this function above 0 and where is it。

![](img/e3bbdee916775b6931caeacad960048d_90.png)

below 0 to make our classification，and so this is what our final classifier，is going to look like。

our final hypothesis is going to look，like it's going to predict 1。

in the sort of upper corner it's going，to predict zero in this lower corner。

and again this is sort of a potentially，useful classifier to have。

just as an example maybe i'm trying to。

![](img/e3bbdee916775b6931caeacad960048d_92.png)

decide you know when do i go for a run，i want to look at the temperature maybe。



![](img/e3bbdee916775b6931caeacad960048d_94.png)

in the precipitation and decide，and from here you can sort of see you，know maybe x1 is precipitation。

on this horizontal axis and i might say，to myself if it's，you know snowing or raining too much i'm。

just not going to go for a run and i，don't go for a run then，um conversely if it's way way way too。

hot outside，i'm not gonna go for a run and so we're，seeing that as well here。

and so this is again something that i，couldn't get necessarily from a。

straight linear classifier with just the，default features as we saw before。

that i need something a little bit。

![](img/e3bbdee916775b6931caeacad960048d_96.png)

different and here i'm able to express，this now what if，i also don't go for a run if it's too，cold。

i don't go for a run if it's raining or，snowing too much，but i also don't go for a run if it's。

either too hot or too cold，i'd like to be able to express that i'd。

like to be able to express that in my，hypothesis，so how could i do that well i might add。

in add in a third feature so here so far，we have two features five one and phi，two。

they're both step functions but there's，nothing that stops us，from going further and making yet。

another feature，so we have the two so far let's let's go，for a third。

so here i'm just adding yet another step，function i'm running out of notation so，i'm calling it w。

tilde tilde and w not tilde tilde，this is clearly a problem that we're。

going to have to resolve and we're going，to resolve it on the next slide but bear。



![](img/e3bbdee916775b6931caeacad960048d_98.png)

with me for the moment，it's just another step function it's，just another line。

with one value on one side and one value，on the other side。



![](img/e3bbdee916775b6931caeacad960048d_100.png)

and now i want to ask myself how does，this change，you know once i have this new feature。

how does this change the function，and then，my final classifier that i can make from，that function。

okay well let's start with this function，i make with linear combinations in order。

to look at this function i'm going to，need to change what i was doing over，here because i。

so far i only have two features over，here，so let's look at this first line the。

first line is generic this is for any，number of features，um it's it's going to work out because。

it's just the features as a vector，the second line is the problem it's only。

got two features in it so far we're，going to need to add a third feature and。

so this is really what that，first line is going to look like when we，have three features。

so all i did was i added in that theta 3，phi 3 term that wasn't there before。

so this is really just writing out that，dot product from the line above but now。

with three features instead of two，okay so now let's choose some particular，values。

just so we can plot this because we're，going to need some particular values in，order to have a。

a particular hypothesis so，here i had some values for two features。

i'm going to add in another weight for a，third feature，it's pretty arbitrary i'm just choosing。

some weights here so we can see what do，these hypotheses even look like。

so if i do these weights now i can plot，what does my function look like the，function defined。

right there on the left it's just a，function of x，and here we go so now we see that，there's。

multiple values that we can get，but again some of them are above one and，some of them are below one。

and that's what we were doing with our，classification for polynomials that's。

what we were doing with our，classification for，just vanilla features and that's what。

we're gonna do now we're gonna ask，what's above one and what's below one。

and so we're gonna get the following，hypothesis for classification。

i'm not going to go for a run if it's，raining or snowing too much i'm not。

going to go for a run if it's too hot or，it's too cold but if it's in that。

nice little middle place where it's not，running or snowing too much。

and the temperature is just right，i'll go for a run and so again this is，the kind of hypothesis。

that we couldn't have expressed if we，just had our traditional you know。

no nonsense not changing anything，features we just had our x1 and our x2。

but now that we've created these more，complex step function features we're，able to say。

this sort of complex statement about，going for a run，okay yes there's a question um please。

could you say that it's more it's more，confidently predicting a one if the，graph is higher。

above one or oh yeah that's a great，intuition so this idea that we kind of。

feel like it should be more confidently，predicting a one if the graph is very，much above one。

versus if not it's sort of saying like，oh here are all the reasons i wouldn't，go for a run。

you know it's raining too much and it's，too cold and so it's like wow。

if all of those things are true i'm，super not gonna go for a run。

and that's such a great intuition and，that's the kind of thing that we can，express。

if instead of a straight stem function，we had a sigmoid because a sigmoid is。

basically telling us exactly that kind，of thing remember like。

when are we most likely to go for a run，and when are we least likely and so。

we're going to see that later basically，so right now we're just saying hey am i。

going for a run or not um but absolutely，that's great intuition um and uh and。

we're definitely gonna go there later in，the lecture，great okay cool，so right now we have。

this set of hypotheses um but we were，running into an issue was。

which was namely that i was running out，of tildes you know like the notation was。

just getting way out of hand，at some point i can't just keep adding。

tildes to my weights i'm gonna need to，you know what if i want four features。

what's going to happen then，what if i want four of these step。

functions and so let's just take a step，back now and try to develop a much。

more general set of notation for the，idea that we've just been talking about。

basically the idea again being that we，create a whole bunch of step functions。

we're going to use them as features and，then we're going to put them。

into a classification problem okay，so now we're just going to spend time on，that notation。

so let's get some new notation again，just for exactly the thing that we just。

okay so the first layer was constructing，the features there were kind of two。

layers that were going on here we first，them all，into a linear classifier okay so。

let's talk about constructing the，features and let's develop some。

notation for that same thing we did just，with some new notation，okay our input is going to be a data。

point so just as before we said we have。

![](img/e3bbdee916775b6931caeacad960048d_102.png)

these phi of x they take a data point，and they output our features。

we're going to have our data point and。

![](img/e3bbdee916775b6931caeacad960048d_104.png)

we're going to output some features so，just as an example maybe our data exists，in two dimensions。

and this could be our data point that we，would use an input this little star。

okay now something that we're going to，do is we're going to have this sort of。

general notation for each layer so the，superscripts on this page are going to。

represent the layers so，in this first layer we're constructing。

the features we're in the first layer so，we're layer one and we're going to say。

that the number of inputs，to layer one is m super one so that's。

just going to be a notation that we use，um but in this particular example in。

this drawing that i have of x right here，can somebody tell me what is m1 as a。

number what would what would the，size of the data point b so this is uh。

okay so the the answer here in in this，particular，drawing that i have on the right this is。

a two-dimensional data point，so we're seeing that it has size you。

know we've been thinking about these，things as column vectors so it has size，two by one。

and so m one here is two and the size of，the data point is two by one。

okay great now we've called this，something different in the past and so。

i'm just going to point that out we've，called this d，in the past so m1 is just equal to d the。

d the dimension of the data that we，talked about before，okay now our output in this layer。

is going to be the feature values so，let's just go back to what we had on the，previous slide only。

in miniature so these were our three。

![](img/e3bbdee916775b6931caeacad960048d_106.png)

features on the previous slide，they're each a function of x1 and x2。

although i've only labeled those axes in，the third feature，but each one is a function of x1 and x2。

and so what a1 is going to be。

![](img/e3bbdee916775b6931caeacad960048d_108.png)

is it's going to be those features，evaluated，at x so if i，take my particular x so this is just the。

same x that i have above here，it's got a pretty low value of x1 and，sort of a mid value of x2。

and i ask what's phi 1 of x at that，x well it looks like it's 0 in this case。

in this particular case phi 2 of x also，looks like it's 0 and phi 3 of x looks，like it's zero。

but it's basically what we're going to，do is we're going to evaluate our，features。

at this particular x and that's how，okay so we get these particular values，we line them all up。

and so that's going to have size we're，going to say that the output size。

is a column vector of size n1 and so in，this particular，illustration where we have exactly these。



![](img/e3bbdee916775b6931caeacad960048d_110.png)

features，this is another question for the chat，what's the size of n1 or what exactly is。

n1 can you tell me what n1 is again just，for this illustration。



![](img/e3bbdee916775b6931caeacad960048d_112.png)

![](img/e3bbdee916775b6931caeacad960048d_113.png)

okay great we're getting a lot of threes，just for this illustration。

and one is three so basically the idea，is we're going to take in。

data of whatever data dimension we have，in this particular illustration the data。

dimension was 2 and then we're going to，output a set of feature values in this。

particular illustration the number of。

![](img/e3bbdee916775b6931caeacad960048d_115.png)

feature values is 3。just has，size and one by one it's a column vector。

okay so how do we get these feature，values well we apply our feature and so，a。

step function we had some function，f1 that's basically the step function，and then we applied it。

to some linear function，of the x and so，here i've gotten around this issue of。

okay well i was running out of tildes，with my ws by just saying hey i'm gonna，give。

a different w to each one of these，problems，ah i i see that there is a small typo，here the w。

naught should also be indexed by i um i，will fix that for the，later。

but basically we're going to have a set，of w。

![](img/e3bbdee916775b6931caeacad960048d_117.png)

so that's both the offsets and the，normals here that we're used to。

and we're going to have one of those for，each of the features so we're going to，have a w not。

i and a wi as well and then the，superscript again，everywhere here the superscript just。

means we're in the first layer we're。

![](img/e3bbdee916775b6931caeacad960048d_119.png)

constructing the features，so that's what that superscript one，means。

okay so in particular if we were looking，at i equals three，we're constructing the third feature so。

here i'm focusing it on the third，feature，that's i equals three um and the way。

that we would do that is exactly we，would construct our function of x in the，following way。

so this is phi 3。 this is the phi 3，function of x，for this particular step function，feature。

and then we would say hey let's evaluate，at this particular x，so in this particular case in this。

particular case if we're looking at i，equals 3，and we evaluate our feature and we get。

out our ai1 what is the value of ai1，again remembering that this phi 3 has。

two values it's either zero or one，so what is a i1 here this is a question，for the。

okay great so the answer is zero in this，know that，is we look at that particular x that's。

that little star，we evaluate it at phi three of x and we，see that at that particular x here。

the value is zero there were two choices，sort of zero one and this one happened。

to be zero great so lots of，okay so now though we actually want to。

do this multiple times we don't just，want to do this for one particular i。

we want to do this over all the features，i and so，we're going to do all the features at。

once and put them into this vector，and that's going to look like this now。

let's talk carefully through this，equation because there's some weird，stuff going on here，so first w。

one capital w one here is collecting，the w i's the w i super ones the little。

wi super ones so it's going to be an m1，by n1 matrix，and it's just collecting all of the w i。

ones that we had from those i，features similarly w，naught is collecting all the w knots so。

i made this typo it should be w not i，in that i feature area um and so this。



![](img/e3bbdee916775b6931caeacad960048d_121.png)

would be collecting，for each of those eyes the w not ones，okay now here's where the weirdness。

comes in，so you should check using the kind of，tools that we used in previous lectures。

what is the dimension of that vector，you can get it from the w1s the size of，one。

i'll tell you i mean you can kind of see，just by looking at w not one if i'm。

going to add w not one to it this has，got to have the same size as w not one。

and so this whole thing is going to be n，one by one。



![](img/e3bbdee916775b6931caeacad960048d_123.png)

and what's weird about that is we've，never really applied a function to a，vector before。

that's not something that we've been，doing in this class we've always applied，it to a scalar。

and when you apply a function to a，vector that could mean a lot of。

different things and so i want to be，really clear what does，this particular usage mean it means。

we're going to apply it。

![](img/e3bbdee916775b6931caeacad960048d_125.png)

element-wise that doesn't always have to，mean that there are different ways to。

apply functions to vectors，but here that's what we mean by this so。



![](img/e3bbdee916775b6931caeacad960048d_127.png)

f1 is applied to each element，in that vector to get a1 out，so this is really you know this this a1。

equation with all the features at once，is just a shorthand of writing what we，did for the i。

feature i times or n1 times，and that's really the story of this，slide and the notation of。

neural nets in some sense is that it's，all this sort of，shorthand that seems laborious at the。

time and is like kind of a headache but，ultimately will make our lives easier。

because we're going to have too many，things floating around to have the。

okay so that's the first layer where we，constructed the features。

now let's go to the second layer where，we take those features and we assign a，label。



![](img/e3bbdee916775b6931caeacad960048d_129.png)

or potentially multiple labels，so this is really kind of like what we。



![](img/e3bbdee916775b6931caeacad960048d_131.png)

were doing before，you know in previous classes like just，doing linear classification with。

different features。

![](img/e3bbdee916775b6931caeacad960048d_133.png)

um and so we're just going to do that，again，only with like slightly different。

notation okay so let's do this so first，in this layer the input is going to be。



![](img/e3bbdee916775b6931caeacad960048d_135.png)

the features，just like if you were doing linear，classification with polynomial features。

you would take in those polynomial，features，so now we're going to call the size of，any layer。

m super that layers index by one，so in the first layer we call the m1x1。

in this layer we're going to call it，m2x1，um is m two equal to anything else。

on this slide could you could you say in，the private chat，is there something that m2 would be。

great yes it's the number of features，which we just said was the output of the。



![](img/e3bbdee916775b6931caeacad960048d_137.png)

perfect，great great um observations here another，good one is it's the dimension of a1。

totally another great way to phrase this，um it's the number of elements in the。

vector a1 um so these are these are all，correct，um good stuff so i'm just going to write。

that explicitly here。

![](img/e3bbdee916775b6931caeacad960048d_139.png)

m2 is the number of inputs to this layer，so it's got to be the number of outputs。

in the previous layer，because we're taking the number of。



![](img/e3bbdee916775b6931caeacad960048d_141.png)

features and in this particular，illustration that we have on the side，again that's going to be。



![](img/e3bbdee916775b6931caeacad960048d_143.png)

okay so now here our output，is going to be the labels now in。

everything else we've done in this class，so far，we've had a single label we've said okay。

are we classifying this，you know as uh an exoplanet in the，habitable zone or not。

are we classifying this as i'm gonna go，for a run or not you know are we，classifying this as。

um you know one thing or the other and，so，this is a little bit different，potentially than that。

and that we could have multiple outputs，so in what we just saw。

in the illustration that we saw in the，previous slide we were just having one，output。



![](img/e3bbdee916775b6931caeacad960048d_145.png)

we were doing this classification of am，i going to go for a run or not。



![](img/e3bbdee916775b6931caeacad960048d_147.png)

so that's either one or zero and so in，this particular case our vector of，labels。

is actually just a one by one vector，there's there's nothing to it but you。

can imagine that maybe i want to，you know say multiple things i want to。

say am i going to go for a run，based on the precipitation and the，temperature。

and is my best friend gonna go for a run，based on the precipitation and the，temperature。

and you know is our neighbor gonna go，for a run based on the precipitation and。

the temperature and if i asked all of，those questions using the same。

set of features then i would have a，vector of labels here，incidentally i'm going to call this。

whole function，that starts from the data goes through，the first layer and。

through the second layer n for neural，net because we're basically building up，a neural net。

which hopefully um is something that you，today，um and and did your exercises uh and。



![](img/e3bbdee916775b6931caeacad960048d_149.png)

we'll we'll talk much more about，you know this this wording of neural。

nets but basically we're just building，up a complex function here and so。

and it depends on these parameters w。

![](img/e3bbdee916775b6931caeacad960048d_151.png)

label，and what that label is is we're just，evaluating that complex function that，we're building up。

at a particular point so we put in that，point to get our feature values the a1s。

now we put in the a1s to get，our final value a2 maybe final values。

but in this particular example it's just，one，and so this is gonna have a size we'll。

call it n two by two by one。

![](img/e3bbdee916775b6931caeacad960048d_153.png)

that's the number of outputs but again，typically n2 is just going to be one。

because you're going to be doing。

![](img/e3bbdee916775b6931caeacad960048d_155.png)

one classification or later we'll see，okay and so again we have the same idea，that we're going to。

apply our in this case classifier，to get the ith label so for instance if，we have a single label。

we apply the classifier in the following，way and this is our typical，classification。

this is the kind of thing that you know，we've been doing for a while now and the。

only thing that's changed essentially is。

![](img/e3bbdee916775b6931caeacad960048d_157.png)

how we express it in notation，so previously we had theta and theta，naught。



![](img/e3bbdee916775b6931caeacad960048d_159.png)

now we have w i super two because this，is the second layer，and again unfortunately i made a typo。

this is w not i it depends on which，output you have。



![](img/e3bbdee916775b6931caeacad960048d_161.png)

um and so you're going to have a w not i，again super two because this is the。

second layer so that's why we have that，two superscript，and then again we might do this fancy。

thing where we collect all of them，together at once by applying this，component-wise。

f you know which in in the case that，we've been looking at so far it's been，the step function。

but we're going to see some alternatives，so we apply this component y is f。

um and we you know collect everything in，these w2，and w not two matrices very much。

analogous to what we did in the first，layer，okay so the whole idea here。

and i think the important thing to take，home from this is that all we've done。

is constructed a really complex，hypothesis，so remember what is a hypothesis it's。

it's just a way to go from data，to a label and it depends on some，parameters。

and that's exactly what we have here we，have。

![](img/e3bbdee916775b6931caeacad960048d_163.png)

a function that goes from our original，data，through to some features and then，finally to a label。

and so what i'm plotting here is that，whole function，that function just takes in data and。

outputs a label，and here we're sort of not seeing the，hidden calculations along the way we're。

just seeing here's the final output we，can see that as a result this is a。

pretty complex interesting function，and the other important thing to note is。

it depends on the choices of the，parameters，the w and w not so just like in the past。

our hypotheses for，say just linear classification with，default parameters depended。

on the choice of our parameters here we，get the same thing if i choose different。

parameters if i move the parameters，around i get a different hypothesis。

and that's what's let us do learning you，know ultimately what we want to do is we。

want to say hey there's a lot of，different hypotheses for a lot of，different parameters。

and when we get a particular set of data，we're going to ask well which of these。

hypotheses has a particularly low loss。

![](img/e3bbdee916775b6931caeacad960048d_165.png)

can we minimize that loss，and so what we're doing here is really。

just building up what even are these。

![](img/e3bbdee916775b6931caeacad960048d_167.png)

hypotheses，what do these look like and in，okay so this is a big old slide of，notation。

which i think is the kind of thing you，know all notation looks weird when you，first see it and you。

you get used to it by working with it by，working with a lot and so that's what。

you're going to be doing，in your labs your exercises you know，everything that you're doing you're。

going to be getting really familiar with，this notation and。



![](img/e3bbdee916775b6931caeacad960048d_169.png)

it'll hopefully become you know second，nature it'll become something that。

you're more used to but certainly，it does feel like a lot in the beginning。

okay so now what we're going to do is，we're going to find，another way to express the same idea。

which can also be a very useful way to，express the same idea and that's with a。

okay so again let's just reiterate so。

![](img/e3bbdee916775b6931caeacad960048d_171.png)

there's there's sort of a couple of key，things going on in this slide and i'm。

just going to extract them，this is basically the whole slide we had。

the first layer where we constructed the，features，and we output the feature values and we。

had the second layer，where we took those feature values and，we turned them into labels。

and then we said this whole thing we'll，call this a neural net，where nn and it's just a big function。

that takes in our data，and outputs some labels a2，okay and now what we're going to do is，idea。



![](img/e3bbdee916775b6931caeacad960048d_173.png)

this way to express our function。

![](img/e3bbdee916775b6931caeacad960048d_175.png)

as a function graph，again we're just sort of describing our，hypotheses at this point we're saying。

what do they look like，um and here's just another way to，describe them and i think it's。

it's useful to have these multiple，descriptions because we're getting into，these pretty complex。

hypotheses and so we want to be able to，understand all the little components，that go into them。

um and to understand you know how does，this work so let's let's look at this，idea of a function。

graph okay so the first thing we're，going to do to build up our function，graph。

is we're going to look at what does a，function graph look like。

if we're constructing one feature let's，say the i，okay it's going to look like the。

following so we have，our inputs x1，x2 up to xm1，because we said that that's our cool new。

way to describe the number of inputs but，m1 is just d it's just the d。

that we saw from before now we see this，circle what does a circle mean in a。

function graph a circle means that a，function evaluation is happening so this。

first circle where all the x1s are going，x1 x2 x3 etc are going into there's this。

little summation symbol and that，essentially represents，this dot product plus adding w naught。

because the dot product's just a sum，you know if you think about it you're。

really just summing over the elements of，that vector and then we're adding in the，w naught。

and so we're doing that whole dot，product and we're getting out an output。

and we can call that z we could call，that output z this is basically the，thing that's going to go。

now why doesn't z have a circle around，it because there's no function，evaluation going on there。

so we have a circle around the sum，because we're taking all those x ones。

and doing something to them and out，making an output with z，we just that is a value and now we're。

going to take that，and put it into a new function f1 and。



![](img/e3bbdee916775b6931caeacad960048d_177.png)

because with f1 we're doing a function，evaluation getting an output that's。

going to have a circle on it again，and so now we do that function。

evaluation we take this z and we put it，into f1。

![](img/e3bbdee916775b6931caeacad960048d_179.png)

so again z is just this w1 transpose x，plus w naught，for the i component and then we get out。

this a i 1 by applying f 1 and this is，representing that component wise。

evaluation that we talked about from，before so for particular for the i。

value for the i feature we have a，particular value a scalar zi1 that goes，into f1。



![](img/e3bbdee916775b6931caeacad960048d_181.png)

![](img/e3bbdee916775b6931caeacad960048d_182.png)

okay and now if we want to look at the，whole first layer，it's just doing this a bunch of times。

so this is exactly what i drew for one，particular，i and now we have。

the same thing for i equals 1 i equals 2，i equals 3 up to i equals m1 because，again there were n1。

different features now something that's，kind of interesting about this though is。

i didn't just repeat the same graph，over and over you'll see that the inputs，are shared。

and so that's something that this graph，is expressing is that it's not just a，again。

we have the x1 x2 up to xm1 going to，every single one，of these summations because the inputs。

um there's a question uh in the chat，shouldn't there be a w not going into，the sum。

that's a good point um so here i，actually haven't really represented the。

w's so something that you'll be familiar，with um from seeing some of your。

representations in the course um and in，the reading。



![](img/e3bbdee916775b6931caeacad960048d_184.png)

haven't even，shown them um and so if i were showing，the ws i would definitely want to make。

sure that like both i have the w's and，the w knots，i guess i'm kind of just avoiding even。

showing them on this so they're implicit，in this particular sum but that's a good。

point it's worth noting，that really you are using the x's and，the w's going into this and it's。

it's sort of you know here i'm kind of，using it the same way that um you know。

x's are the inputs and w's are the，parameters like they're still inputs but。

we kind of treat them as like different，inputs um and so uh but yeah but they，definitely are。

still inputs and they're definitely，going into every one of these sums and。

it's a different w set of w's going into，okay great so now，we have these features a1 a2。



![](img/e3bbdee916775b6931caeacad960048d_186.png)

up to a n and what i want to do now is i，want to look at the second layer how。

we're going to represent the second。

![](img/e3bbdee916775b6931caeacad960048d_188.png)

layer，on this function graph representation。

![](img/e3bbdee916775b6931caeacad960048d_190.png)

well it's going to be a similar deal now，our inputs into the second layer are。

going to be the features from the first，layer，i'm going to write a second layer where。

there's only one output，but there could be more outputs and if，there were more outputs。

then we would have the same features for，each one。

![](img/e3bbdee916775b6931caeacad960048d_192.png)

okay so we have our first layer we have，our second layer。



![](img/e3bbdee916775b6931caeacad960048d_194.png)

and then the whole thing you know each，one of these individually was a set of。

functions the whole thing is one giant。

![](img/e3bbdee916775b6931caeacad960048d_196.png)

function it takes in a bunch of x's and，it spits out，in this particular case one label at the，end。

it could do more labels one label is，pretty standard，okay so now we're just going to make a。



![](img/e3bbdee916775b6931caeacad960048d_198.png)

few notes about this function graph，representation，the first note is that it has。

directionality there is a notion，of going forward and a notion of going，backward in it。

something you'll notice is that there's，a direction defined by going from the。

inputs to the outputs and all the arrows，accord with that direction。

and that direction is what we're going，to call forward so forward means going。

to the inputs from the inputs to the，outputs，there is also accordingly a notion of，going backward。

once we have a notion of forward，backward is the other direction。

so we can also draw backward so backward，we'll be going from the outputs。

to the inputs and this is something，that's going to come up when you're，actually doing inference。

when you're actually doing learning in，these models，um it turns out you're going to do a lot。

of chain rule，and the easiest way to do that chain，rule is often by going backwards and so。

that's why we have something called back，propagation because you're going。

now this particular network that we've，shown here is what's known as a feed。

forward neural network because，all of the lines go forwards，it is possible to have a network that is。

not a fee-forward network where some of，the lines go backwards so for instance。

here is such a network this is just an，example。

![](img/e3bbdee916775b6931caeacad960048d_200.png)

of a network that would not be a fee，forward network because。



![](img/e3bbdee916775b6931caeacad960048d_202.png)

one of the further along outputs then，becomes an input，it has a it has a line that goes。

backwards an arrow that goes backwards，and this is actually something that。

we're going to see later in this course，with recurrent neural nets。

but it's not something we're doing right。

![](img/e3bbdee916775b6931caeacad960048d_204.png)

now the networks that we're looking at，right now，like this network before i added this。



![](img/e3bbdee916775b6931caeacad960048d_206.png)

extra bit are feed forward neural，networks so now we're back to a，i've。



![](img/e3bbdee916775b6931caeacad960048d_208.png)

gotten rid of that that weird backwards。

![](img/e3bbdee916775b6931caeacad960048d_210.png)

okay let's also label some of the things，that are going on here。

so we have inputs you can actually have，case，in in this first layer our inputs are。

going to be the data，we have essentially this dot product，that's going on where we're adding in。



![](img/e3bbdee916775b6931caeacad960048d_212.png)

the the w knots too but you can think of，that as part of a dot product um。

perhaps with a feature that is equal to，one you know we've seen seen that。

interpretation before we have this。

![](img/e3bbdee916775b6931caeacad960048d_214.png)

thing which is the output of doing the，dot product and adding w。



![](img/e3bbdee916775b6931caeacad960048d_216.png)

naught but before we apply，this function f1 and so we're going to，call that the pre-activation。

it's what goes into the function f1，and a reason for that name，pre-activation。

is in some sense because the function f1，will be called the activation function。

and so it's before you apply the，activation function so it's the。



![](img/e3bbdee916775b6931caeacad960048d_218.png)

pre-activation，and then finally what we get when we，apply the activation function is perhaps。

not surprisingly at this point the，activation，now why might this be called the。

activation well if you think about these，step functions that we've been talking。

about that have a zero and a one you can，think of them as being sort of activated。

when you hit a one and not active when，you hit a zero，so this is sort of telling us you know。

did we did we activate，uh this particular what we're going to，find out is a node but did we activate。

this particular。

![](img/e3bbdee916775b6931caeacad960048d_220.png)

okay so now a neuron，or sometimes a unit or a node is，basically the sequence of inputs through。



![](img/e3bbdee916775b6931caeacad960048d_222.png)

the dot product and the activation，function，so not going through any other。

activations just getting to that nearest，activation，um and taking all the inputs that go。

into that node that's going to be。

![](img/e3bbdee916775b6931caeacad960048d_224.png)

a neuron or a node，then a layer oh here's just another，neuron or node。

you know we can have them in any layer，and now implicitly we've been saying the。

word layer a lot let's let's just say a，layer is this collection。

of neurons here at a certain distance，relative to the inputs or the outputs。

so for instance this is a particular，layer this is sort of the first one。

um it's it's out of all of these，neurons or a particular distance，relative to the inputs。

and then we have we'll see we have，another layer，as well，okay and then finally we go through all。

of this stuff and we eventually get，a set of final predictions。

and which is which is what we get from，we do，whenever we put in a particular data。

point we get a final，prediction or guess out of that，hypothesis for each possible data point，value。

and so this is no different one the one，thing that is a little bit different。

is that we could have more than one，that's not something that we've talked，about too much before。

um i mean implicitly i guess we could，have done it but here we're sort of。

explicitly including it in our notation，as a possibility，again in this particular function graph。

i've only shown one output but i could，okay this also happens to be what's。

known as a fully connected，network so in particular we say that a，layer，to。

every neuron in the layer are the same。

![](img/e3bbdee916775b6931caeacad960048d_226.png)

and in this particular case that's true，of all of the layers，so the whole network is fully connected。

now one more note we can actually name，some of these layers，you could say we have this output layer。

so that's the layer that eventually we，gets，out of the thing that we actually report。

at the end of the day，and the stuff before it we don't see，you know we don't get a final prediction。

or a final output out of and so we might，call those the hidden。

well in this case it's one hidden layer，spoiler alert we can have more than one，layer。

that is hidden and in that case we will，but it's basically it's the stuff that's。

not the output layer it's the stuff that，okay so now we have multiple ways to。

think about neural networks，um with our original step function idea。

um with all of the notation that we，developed with this function graph。

representation and so let's think about，how we would slot that into the way that，we think。

about hypotheses and the way that we do，okay so our typical problem setup this。

is just what we would do for any，any learning problem so far is we choose，a hypothesis class。

we've done that every time that，hypothesis class could have been the，linear classifiers。

this time we might choose instead the，neural networks，they're defined by the layers。

by the number of units in each layer the，number of nodes in each layer。

and by these weights the w's and w knots，and so，to really nail down a hypothesis class。

we'll have to say，you know we're going to have this many，hidden layers and this many outputs and。

we're going to have this many nodes in，each layer，okay in this particular case we chose，two layers。

with let's say you know one output，and then the next thing we have to do。

always is choose a loss and so for，instance if we are interested in。

classification there's a number of，losses that we've talked about we've。

talked about zero one loss we've talked，about asymmetric loss we've talked about。

negative log likelihood loss，there's a lot of choices we just choose。

then we learn the parameters we have，now，like gradient descent and stochastic。

gradient descent so we could，we could hope to apply those although。

we're going to see there's a rub in just。

![](img/e3bbdee916775b6931caeacad960048d_228.png)

and then once we have learned some set，of parameters that is to say we've we've。

found some set of parameters that seems，to get the loss pretty low。

and we try to minimize the loss then we，can use those parameters。

to choose our particular hypothesis we，don't just have a whole class anymore we。

have a particular one and we can use，that to predict，unknown data okay so this is our general。

setup i mean this is how we approach，these problems in this class this is not。

specific to neural nets it's just you，know if we choose this hypothesis class。

and we're using neural nets um but there，are some problems with applying this。



![](img/e3bbdee916775b6931caeacad960048d_230.png)

general setup right now，to what we're doing and so let's go into。

that before we can actually apply it，because we're going to have to resolve，those problems。

okay so here's here's the first issue，the first problem that arises。

if we want to use gradient descent or，stochastic gradient，descent we can't really use these step。

function activation functions that we，were talking about before，the reason for that is that their。

derivatives are zero basically。

![](img/e3bbdee916775b6931caeacad960048d_232.png)

everywhere，and so if i apply gradient to center，stochastic radiated descent。

whatever gradient i calculate it's just，gonna move，and that's it that's done i'm done with。



![](img/e3bbdee916775b6931caeacad960048d_234.png)

stochastic gradient descent i'm done，with gradient descent and that's boring。

and that's not telling me anything and，it's not useful right。

i really want to use stochastic gradient，descent and gradient descent to get to。

some good set of parameters，and so that's not going to happen if i，have。

these step function activations and so，i'm really going to have to do something。

else if i want to apply gradient descent。

![](img/e3bbdee916775b6931caeacad960048d_236.png)

or stochastic gradient doesn't。

![](img/e3bbdee916775b6931caeacad960048d_238.png)

another issue with our current setup，is what if i want to do regression you。

know here so far we've talked，we've been talking about f2 as a step，function。

it returns one or it returns zero that's，not very helpful for regression we，really want。

some value that could be continuous that，could take a range of values。

certainly not something that is only 0，or 1。and so we're going to have to resolve。

that and another one is that actually，even if i wanted to use negative log，likelihood loss。

you know this loss that we've talked，about that can be really useful for。

classification that's also a problem，because the step function returns 0。

one and as many people have been having，a really nice，set of discussions in discourse about i。

i just can't put in a straight zero or，one into that loss i really want，something that's between。

zero and one something that i can，interpret as a probability。

and so i'm going to need to do something，else if i want to use。

okay so let's think about what can we do，to solve，all of these issues that i want to use。

some kind of gradient descent or，stochastic gradient descent，i want to do regression i want to use。

negative log likelihood loss，luckily it turns out there is basically。

a single solution to all of these issues，and that's to use a different activation，function。

that we are not beholden to step，functions we don't have to use step。

functions they provide some nice，intuition，um they're they're useful for plotting。

things and understanding what a neural，network does，but we can use things that are like step。

functions，and still have the properties that we，want，and so that's why we're now going to。

turn to choosing a different activation，function，than just a step function。

okay let's look at different activation，functions so，so our hypotheses look like this right。

now we're looking at neural networks，with two layers，in the first layer we create the。

features and in the second layer，we get the labels from the features so。



![](img/e3bbdee916775b6931caeacad960048d_240.png)

our sort of typical，linear classification or linear，regression is going on in the second。

okay so let's ask first what if i want，to do regression，so the problem that we said was that if。

f2 was a step function if it only，returned，zero or one then i'm，i'm not doing anything really。



![](img/e3bbdee916775b6931caeacad960048d_242.png)

interesting for regression like i really，want something that could be。

generally real valued that i could get，all kinds of different values for。

um i mean that's sort of the point of，regression is to be able to have a range，you know。

what is my um air conditioning bill。

![](img/e3bbdee916775b6931caeacad960048d_244.png)

going to be i don't think it's just，going to be zero or one i think it's。

going to take on all kinds of values and，i want to predict that，so instead of。

a particular step function activation，for f2，here i could have the identity。

so if the inputs to f2 can take on a，range of values，then now my outputs will be able to take。

on a range of values，so i'll be able to get an interesting，okay what if i want to use negative log。

likelihood loss i want，my output of f2 to be between 0 and 1。well if i use f2 equal to the identity。

if i use f2 equal to a step function，get 0，1。 but luckily we have a great。

you know function that we know returns，values between，and that's our sigma function so we can。

use the sigmoid。

![](img/e3bbdee916775b6931caeacad960048d_246.png)

okay our third question was what if i，what if i want to use gradient descent。



![](img/e3bbdee916775b6931caeacad960048d_248.png)

or stochastic gradient descent i have，this sort of nice，general way of optimizing losses now if。

i want to use those well i need to be，able to take，derivatives and i need them to be useful。



![](img/e3bbdee916775b6931caeacad960048d_250.png)

so you can take derivatives of the step，function it's just not super useful it。

just gives you 0 everywhere。

![](img/e3bbdee916775b6931caeacad960048d_252.png)

so what do i want to do here i want to，get something that is that is actually。

non-zero that sort of tells me，where to go and so let's think about how。

well first of all we need the f2s to be，differentiable，luckily each of the f2 values that we。

just said，is fine for that z the identity is，differentiable，the sigmoid is differentiable so we're。

all set on the f2s，on the sort of output activations，okay but we need the f1s to be。

differentiable too，so we have to think about what f1s would，we choose now f2 and f1 are sort of。

accomplishing different things in this，network when you look at the output。

layer you're getting the labels，you're making the labels and so with f2。

we're thinking about hey what are the，choices that we've made before to do。

regression or classification or get，these output labels with f1 we're。

thinking about creating the features，or thinking about what features would be，useful to have。

and so with f1 we want to think well，what kind of features would be useful，but also。

have useful derivatives and so there are，actually multiple choices here because i。

mean in some sense features aren't，as immediately obvious like what do you，have to have in a feature。

we sort of know with regression and with，classification what we're looking for in。

our output but what do you have to have，in a feature，so there's a few different options so。

one option，is to just choose the sigmoid again you，know we know the sigmoid we're familiar。

with the sigmoid，it has derivatives everywhere and you，know they're。

generally useful they tell us you know。

![](img/e3bbdee916775b6931caeacad960048d_254.png)

where to go um，and they can tell us things about the，sigmoid another option so you can think。



![](img/e3bbdee916775b6931caeacad960048d_256.png)

of the sigmoid as sort of a relaxed，zero one function there's something，called a hyperbolic tangent。

tangent which is a relaxed negative 1，1 step function so if for any reason you。

want something that's sort of a，relaxation of negative 1，1 then that might be more convenient so。

you might use the tange，instead another option，is what's known as a rectified linear，unit or relu，z。

or zero it does have an，interesting non-zero derivative on one，side when you're on that side。

it's extremely easy to take that，derivative，because it's just the derivative of z so。

that's super easy it's one，it's great um and what's kind of nice。

about this too is that if you're doing，something like regression you can't。

really get like a really big，range of values out you can get，something that's like a linear function。



![](img/e3bbdee916775b6931caeacad960048d_258.png)

and so you might find that useful for，what you're doing，but ultimately at least from our。



![](img/e3bbdee916775b6931caeacad960048d_260.png)

perspective right now these are all，perfectly fine functions that we could。



![](img/e3bbdee916775b6931caeacad960048d_262.png)

use to create，features and that's what we're trying to，do with them we're just trying to create。

some features。

![](img/e3bbdee916775b6931caeacad960048d_264.png)

that we could use okay so let's just do，a quick little look at how this。

changes our setup that we saw before，when we use these different functions。

like what's what's going to be different，so before we said we were going to use a。

step function activation in our first，layer，so we make our features by using the。

step function activation，and this is what our features look like。



![](img/e3bbdee916775b6931caeacad960048d_266.png)

boundary，and then there was this just sharp cut。

![](img/e3bbdee916775b6931caeacad960048d_268.png)

okay and then in our second layer we，into，a final prediction and so here we're。

going to show is the full，function that we get out from x all the，way to that final。

prediction i mean this is just what we，saw before and again it's going to have。

these very sharp boundaries，but it's only going to have values of 0。

1 because we're using a step function，activation and now let's just ask how，would this change。

okay well let's go up here and change，our activation function to for instance。

the sigmoid let's use the sigmoid，instead，and you can think to yourself how do you。

think that these step functions，are going to change you might just take，a moment and think。

you know what what do you think that，these are going to look like when we。

change to the step function，activation and in general like the idea，that we've seen before。

about the sigmoid is that it's much like，a step function，but sort of smoother and so here i'm。

just showing the exact same linear，boundaries that we had before。

and you can just see when we apply the，sigmoid activation function。

instead of this strict step function，activation that things kind of smooth，out。

you know it's it's a little bit gentler，we see that you know usually they're in。

life there isn't a clear dividing line，you know things are just more or less。

likely and that's what this is。

![](img/e3bbdee916775b6931caeacad960048d_270.png)

now we can go to our second layer down，here and think about our outputs。

you know how does this all translate，into taking input x，and so one option is we might care about。

regression so if we care about，regression，our output activation will just be the。

identity or you know it's certainly a，very reasonable choice，that we might make and in that case。

we're going to get a very different，looking function so one thing that's，happening here。

is that we're actually seeing you know，multiple，sort of plateaus that are happening。

because we can actually see what's，happening，when we're adding in these different you，know almost。

step function features and so we're，seeing that here and then of course，everything's smoother。

because not only you know are we，choosing z as our output now but we had，those smoother。

um inputs to go in we had those smoother，features to go in，now something you can see here is that。

when we're doing regression but we，have these sigmoid um features that you。

still kind of get like these different。

![](img/e3bbdee916775b6931caeacad960048d_272.png)

layers，you know there's there's different，there's sort of a，uh different levels that you can get if。

you don't want that you can get away，from that with a relu if you were using。

a relu for your features you wouldn't，necessarily have to have those levels。

that could be useful it could not be，useful。

![](img/e3bbdee916775b6931caeacad960048d_274.png)

but by changing the weights you really，can't get any value here。



![](img/e3bbdee916775b6931caeacad960048d_276.png)

for your output okay now we could also，ask what happens if we use our sigmoid。



![](img/e3bbdee916775b6931caeacad960048d_278.png)

for our final output so we're just going，to basically take。



![](img/e3bbdee916775b6931caeacad960048d_280.png)

what we have on the left here and smush，it down with the sigmoid so with the，sigmoid。

we're just taking all those different，values，that we get because you know essentially。

the left is the pre-activation because，it was the identity，and we're smooshing them down to be。

between zero and one so this comes back，to the question from earlier you know。

is it that when these values are higher，when we see these higher values in our。

pre-activation does that sort of，represent that you know maybe some class。



![](img/e3bbdee916775b6931caeacad960048d_282.png)

that's，that's made sort of very concrete and，made very um precise yes。

exactly when we have that higher，pre-activation value that gets smushed。



![](img/e3bbdee916775b6931caeacad960048d_284.png)

to a higher value，when we apply the sigmoid and so we have，a higher probability of a particular。



![](img/e3bbdee916775b6931caeacad960048d_286.png)

okay so at this point，we have this ability to choose all kinds，of different features。

we have this ability to have different，types of outputs，you know regression style output or。

classification style output，and we can finally ask you know how do，we learn these parameters。

because we can apply these methods that，we know from before，okay so before we can apply stochastic。

gradient descent or gradient descent，we have to know what are we applying it。

to you know what what is the objective，that we're going to try to minimize with。

stochastic gradient to center gradient，descent，and in some sense what i'm writing here。

is just a completely generic objective，you know i'm just saying hey we said。

from the beginning that the notion，of training error is one over the number，of data points。

a sum over the data points，of the loss between our guess and our，actual for each data point。

our guess is the hypothesis applied to，that data point，and our actual is our actual label yi。

when we're doing supervised learning，now in this particular case our，hypotheses。

we're thinking of as neural networks and，so they're going to have these big w。

and w naught you know multiple matrices，that we're trying to solve for and so。

those are going to be the parameters，here，now again what's really interesting。

about this problem and very different，is that we have parameters not just for，that final。

classification or regression step but，also for all the features。

that we've built along the way and so，all of those are in here。

all of those are in our hypothesis the，parameters you know for that final。

layer which is doing the classification，of the regression but also the。

parameters for all the hidden layers，which are building up those features。

and so that's different from what we've，done before but ultimately at the end of。

the day what we have is a function，of all those parameters and it's a，differentiable function。

and those derivatives are not just zero，and so we can apply，gradient to centers to casting gradient。

descent，now the one slight thing that is untrue，about that is there is this one point in，the relu。

that is not differentiable but you，or，you essentially never go there if you're。

you know running around in stochastic，gradient to center gradient descent。

you pretty much will never be at that，point because it's just a single point。

and you can also even just define what，happens at that point like maybe。

you know define the gradient to be zero，there as well and so it's not。

as big of a concern as it might see on，the bigger concern is that when you're。

at any other point which you pretty much，always are that you have um a non-zero，derivative。

for most of those points and you do，still get that with the relu that。



![](img/e3bbdee916775b6931caeacad960048d_288.png)

there's that whole side of it that's，non-zero，and with the other ones we see that you。

really do get a non-zero value for the，derivative everywhere for the tangent，for the the sigmoid。

okay so let's just review what goes on。

![](img/e3bbdee916775b6931caeacad960048d_290.png)

with gradient descent and stochastic，gradient descent before we apply them。

for our particular problem。

![](img/e3bbdee916775b6931caeacad960048d_292.png)

so let's think about a different problem，with some different parameters let's，call them theta。



![](img/e3bbdee916775b6931caeacad960048d_294.png)

and so with gradient descent remember，the idea of gradient descent，is essentially hey i've got this。

objective function，it's over some parameters in this，particular case let's say theta one and。

theta two，and i would like to find the minimum and，so i'll start at some particular point。

i'll calculate the gradient i'll move in，the direction of the gradient。

times eta say and i'll end up at a new，point now here's the thing。

so we have previously said that the，gradient，is a vector that's equal to the size of，theta。

so in this case the gradient's a，two-dimensional vector because my theta。

is two-dimensional but it looks like i，just plotted a vector in three，dimensions。

so can anybody tell me what's the third，dimension here why is there a value。

in this sort of up down axis，so this is another one for the chat what。

do you think is the third dimension what，is what is the value of the up down axis。

okay there's some some answers that are，on point um and also，i think some um answers that are going。

the other way so this is a good，i think this is a good thing for us to。

be discussing so what we're seeing here，so what this vector that i'm plotting。

here is it's a three-dimensional vector，it's eta times the gradient in the theta，1 theta 2 plane。

and then its value in the up down，direction，is the actual objective function。

so the starting point of that vector is，the objective function at our initial，point。

and the ending point of that vector is，our objective function。

after we have moved in the direction of，the gradient and so this vector isn't。

just the gradient and that's，a really important thing to notice if we，gradient。

it would just be in the theta one theta，two plane，here we're drawing the gradient with a。

little extra information，we're also showing where it came from，and where it moved to。

okay so once we've done that we've moved，to a new point，in the theta space and also implicitly。

in the j of theta space，because we can evaluate the objective，function of that particular theta。

and that's what we've done here in this，gradient and so we can do it again we。

can say hey let's take another，gradient descent step let's calculate，the gradient let's calculate。

you know where we move to in the theta，space and then let's calculate the j of，theta at that point。

and then let's do it again and then，let's do it again，um and there's a question about the。

magnitude of this uh vector and yes so，what's happening is，plane the theta 1 theta 2 is，then。

the total magnitude of the vector in，that direction is the magnitude of the。

gradient times the step size，and then the magnitude or the difference，in the。

j direction is the difference in，okay so that's gradient descent。

and then we've also learned now about，stochastic gradient descent。

and you can think of stochastic gradient，descent as like drunk gradient descent。

it's like you're taking steps but you，don't have a lot of information。

and things are feeling pretty cloudy and，so you，start somewhere and you go somewhere off，to the side。

because you only have the information，from one data point you don't have all。



![](img/e3bbdee916775b6931caeacad960048d_296.png)

looked at，j j is defined by all of the data points，you know the the optimization。



![](img/e3bbdee916775b6931caeacad960048d_298.png)

objective when it's when it's this loss，is defined by all the data points。

and so with stochastic gradient descent，you don't have access to this beautiful。

objective function that we're plotting，here you only have access to information。

from one data point that one data point，isn't very reliable so it just sends you。

off in all kinds of crazy directions，and so who knows where you're going next，it's maybe over here。

whatever um and you just keep moving，around like that，now now again let's just make sure we。

review why would we ever do this，you know why wouldn't we just go with。

gradient descent when it has this all，this great information at every step and。

again the difference is that the cost of，one of these steps is just a。

huge difference so to make even one，go through，absolutely every single data point so if。

we have a ton of data points that's，going to take forever，whereas with stochastic radiant descent。

yeah sure it's like a，drunken meandering step but it took us，so little time。

and by the time we've taken a lot of，these steps that are just kind of in the，right direction。

we'll probably in many cases especially，with a lot of data be doing better。

than if we had waited that whole time，okay so we have these theorems from our，previous。

um you know talking about gradient，descent and stochastic gradient isn't，roughly。

and in very plain english that roughly，say okay if our objective is nice and，convex。

then gradient descent stochastic，gradient descent should perform well in。

the sense that if you run them long，enough they should get near，that。

unique global optimum exists that unique，global minimum in the case where we're。

minimizing things we're minimizing the，okay so this is the challenge of neural。

nets this is why we're spending，a few weeks on them um you know。

we're gonna have a couple of weeks with，lots of different，explorations um and if you are just。

using them in practice，this is something that you should，absolutely be aware of this is why there。

are so many different parts to this，chapter there are so many different，things to read about。



![](img/e3bbdee916775b6931caeacad960048d_300.png)

because the neural net objective is not，just，not convex it's like super not convex。

it's got so many different local optimum，um it is something that to this day。

especially in the kinds of neural nets，that people are really looking at and。

trying to use in practice，people spend tons of time trying to，understand，know。



![](img/e3bbdee916775b6931caeacad960048d_302.png)

in this particular cartoon and again，it's always worth reiterating and，reminding ourselves。

what we're doing with cartoons in this，cartoon our parameter space is，two-dimensional。

even for the simple two-dimensional，neural net or sorry two-layer neural net。

that we've talked about today，with maybe just a couple of hidden units，or three hidden units。

we're in so much higher dimensions than，two all ready for our parameter space。

our parameter space is going to be，hugely high dimensional in real life，it's going to get so big。

and so it's so hard to visualize what's，going on and to get a sense of what's。

going on especially when we as humans，can only see in。



![](img/e3bbdee916775b6931caeacad960048d_304.png)

two dimensions we can only really，understand what's going on，in two dimensions and so there's a ton。

of research that goes in，just trying to understand these，landscapes and to try and understand。

what to do with these landscapes，um and in particular，a lot of that's going to mean that we're。

things，to optimize and to regularize，so in general we just can't expect。

because this is so non-convex that we're，going to be getting to。



![](img/e3bbdee916775b6931caeacad960048d_306.png)

a global optimum when we optimize。

![](img/e3bbdee916775b6931caeacad960048d_308.png)

and so what can we do about that you're，going to see in the reading you've。

probably already seen in the reading，that there's a huge bag of tricks。

to deal with this and again i can't，emphasize enough this is a area。

of active research to think about what，are good，ways to do optimization in neural nets。

and a really tricky thing about this，problem is that it's not clear that you。

actually want the global optimum，and this relates to regularization now。

we've talked in the past about you know。

![](img/e3bbdee916775b6931caeacad960048d_310.png)

these polynomial bases with just a few，different basis functions。

these polynomial features as being super。

![](img/e3bbdee916775b6931caeacad960048d_312.png)

complex and that you might overfit，and so it's probably not going to be a。

surprise that if we have these。

![](img/e3bbdee916775b6931caeacad960048d_314.png)

super expressive you know many，different step function like features。



![](img/e3bbdee916775b6931caeacad960048d_316.png)

that it seems like，we could easily overfit you know，especially if we just keep adding more。

and more of them，and so we have these conflicting things，that we want to do we want to minimize。

the loss we want to do really well in，terms of loss but we also maybe don't，want to do it too much。

we want to regularize somehow we don't，want to necessarily over fit to all of，that data that we have。

and so this is again just a huge，that's，very different from what we have looked。

at before in this class in terms of，linear classification linear regression，where everything。

was nice and compact so you could have，all these nice guarantees about how，you're going to perform。

now there's so much more work that has，to go into，optimizing and understanding what's the。

right way to regularize，given that you know you don't，necessarily want to perfectly optimize。

this objective。

![](img/e3bbdee916775b6931caeacad960048d_318.png)

and so these are the kind of trade-offs，that you see in this bag of tricks and。

partly i also want to emphasize that you。

![](img/e3bbdee916775b6931caeacad960048d_320.png)

see all of these awesome，ideas that people have come up with，actually pretty recently in some cases。

in the reading，and that's not the end of the story，because this is such an you know。

a major area that people are working in，right now new ideas are getting。

developed pretty recently and so it，might well be the case that you know by。

the time in a few years we're，using this in some other application。

that there might be new tricks to be，using there might be even better things。

to be using and so i think，that's why you really want to take away，this very high level idea。

about what's going on with neural nets，and what's going on with their。

optimization and learning in neural nets，become，obsolete in a few years it's hard to。

know and so you want to be just aware of，the challenges，and what these are trying to address。

okay so that all being said i just want。

![](img/e3bbdee916775b6931caeacad960048d_322.png)

to spend，a few moments at the end saying we don't。

![](img/e3bbdee916775b6931caeacad960048d_324.png)

have to just have two layers，so we've talked this whole time about，having two layers。

in our neural nets the one where we，create the features and the one where we。

do sort of the regression or the。

![](img/e3bbdee916775b6931caeacad960048d_326.png)

classification，um but why stop there and we're gonna，get into this a lot more when we talk。

about convolutional，neural nets and there they definitely，don't stop at two layers。

but let's just think about why we would，want to have more than two layers。

so here this is just another，representation as a function graph so。

here i'm taking the function that takes，the x's takes all the w's。



![](img/e3bbdee916775b6931caeacad960048d_328.png)

and turns it just into the output um at，any particular layer so i've sort of。



![](img/e3bbdee916775b6931caeacad960048d_330.png)

compressed a few of the functions into，one function，from what we saw earlier but that's fine。

i mean a function graph the circle is，just a function it can be whatever，function i want。

and here there's actually three layers，to this net we first come up with a set。

of a super ones then we come up with a，a super twos and then finally some a。

and so that final layer sort of in，general is where we do the linear。

classification of regression that was，true in the two layer net。

and that's also true in our three layer。

![](img/e3bbdee916775b6931caeacad960048d_332.png)

net here and in higher layer nuts，and the rest of this is sort of where，we're making features。

now before we just made features out of，our data but something we could do is。

sort of recursively make features，we could make features and then we can。

make features out of those features，and that's what you can do when you have，multiple。

hidden layers and again we're going to。

![](img/e3bbdee916775b6931caeacad960048d_334.png)

see a really concrete example of this，when we get into convolutional。



![](img/e3bbdee916775b6931caeacad960048d_336.png)

now a corollary of this observation，is that in general when i'm adding or。

subtracting layers what i'm doing is i'm，taking it from these hidden layers。

these layers that are making the，features and so，if i subtracted enough layers that i。

only got down to one layer，all that would be left in my neural net，is that linear classification and。

regression layer at the end，and so just a single layer of a neural，net。

with just one output is linear，classification and regression again。

with the default features it's just what，we've been seeing this whole time you。

can think of it as a special case。

![](img/e3bbdee916775b6931caeacad960048d_338.png)

of this broader idea now，okay great so that's neural nets we have。

defined neural nets we've we've seen，some examples of fifor。



![](img/e3bbdee916775b6931caeacad960048d_340.png)

neural nets um fully connected neural，nets you're gonna be exploring neural。

nets and using them and getting into the，all these issues of，you know how do we actually optimize in。



![](img/e3bbdee916775b6931caeacad960048d_342.png)

them um in your labs and homeworks and，everything like that，um there is no live lecture。

next week um although there is a，pre-recorded lecture from previous years。

so you can check that out if you're，interested，um i will note however that the week。

after that we'll be back and again we'll，be talking about，more layers basically what happens with。

more layers why might we use more layers。

![](img/e3bbdee916775b6931caeacad960048d_344.png)