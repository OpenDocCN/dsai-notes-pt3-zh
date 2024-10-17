# P1：L1- 计算机视觉中的深度学习介绍 - ShowMeAI - BV13P4y1t7gM

welcome I hope y'all in the right place，welcome I hope y'all in the right place。

welcome to ECS four nine eight zero zero，seven slash five five eight zero zero。

five this special topics class talk with，a first-time here at Michigan departing，for computer vision。

I wish we had a snappier easier more，easy to remember course type course。

number but when you teach a special，topics class they give you numbers like。

this so I'm sorry about that but，hopefully you're all in the right place。

so the title of this class is deep，learning for computer vision so I think。

we need to unpack a little bit what this，what these terms mean before we get。

started so computer vision is the study，of building artificial systems that can。

process perceive and otherwise reason，about visual data and this couldn't this。

kind of quite a broad definition on what，does process we'll just perceive what。

does reason mean it's kind of up for，interpretation or what this visual data。

that could be images that could be，videos that could be medical scans that。

could be just about any type of，continuously valued signal you can think。

about can sometimes be found in computer，vision conferences or publication。

somewhere so these terms are really，defined quite broadly so why is computer。

vision important well I think computer，vision is particularly particularly。

important and exciting topic to study，because it's everywhere I think many of。

us in this room right now are carrying，around one or more some several cameras。

and who were just taking millions of，photos every day there's cameras all。

around us all the time people are always，creating visual data sharing digital。

data talking about visual data and this，is very important that we build。

algorithms that can perceive reason and，process for a couple country statistics。

if you look at YouTube actually，anomalous looking instagramers so。

Instagram is very popular many of you，are familiar with it and they some。

there's something like 100 million，photos and videos uploaded on Instagram。

every single day if we go on YouTube，it's even worse so on YouTube as of 2015。

so I'm sure it's grown since then people，are uploading roughly 300 hours of video。

on YouTube every minute so that means if，you do the math and you think if I。

wanted to as a single individual human，being look at all the visual data just，being uploaded。

Instagram in YouTube in one day if you，do the math say I'm going to look at。

images for maybe you call one second，each I'm going to look at my YouTube。

videos at double speed it's gonna take，me about 25 years to look at the visual。

data that's going to be uploaded on just，these two sites in a single day so when。

you think about this these massive，statistics and think about the massive。

amount of visual data being processed，and shared across the Internet these。

days it becomes clear that we need to be，able to build automated systems that。

kind of deal with it because we just，don't have the human manpower to look。

anything process and perceive all of the，data that were created so that's why I。

think computer vision is such an，important topic to be to be studying。

these days and it's only going to get，more important as the number of visual。

sensors out in the world keep increasing，with new with new emerging technologies。

like autonomous vehicles augmented and，virtual reality drones you can imagine。

that the role of computer vision in our，modern society will just continue。

getting more and more and more important，so clearly I'm is because this is my。

research area but I think this is the，most important and exciting research。

topic that we can be studying right now，to your science，so that's computer vision computer。

vision is a is the problem that we're，trying to solve its X force this problem。

of understanding digital data but it，doesn't but computer vision doesn't。

really care how we solve that problem，our goal is just to stop just to crunch。

through all of those images and videos，however we have but the way it that。

means the the technique that we happen，to be using in computer vision in across。

the field these days is deep learning so，deep learn so before get to the report。

we get to deep learning what is learning，learning is the process of building。

artificial systems that can learn from，data and experiences notice that this is。

someone worth bogging all to the goals，of computer vision computer vision just。

says we want to understand visual data，we don't care how you do it。

learning is this separate problem of，trying to build systems that can adapt。

to the data that they see and the，experiences that they have in the world。

and from the outside it's not，immediately clear why these two go。

together but it turns out that in the，last 10 to 20 years，we found that building learning based。

systems is very important for building，many kinds of generalizable computer。

systems both in computer vision and，across many areas artificial。

intelligence and computer science more，broadly so now when we think about deep。

learning deep learning is then yet，another subset of machine learning where。

deep learning is sort of maybe a bit of，a bit of a baby name a bit of a buzzword。

a name but my definition is that it's a，type of type the deep learning consists。

of hierarchical learning algorithms with，many layers whatever that means in the。

context of Han that are very very，loosely inspired by it by the out by the。

architecture of the mammalian brain and，some types of a million visual system。

now I know could I say loosely this is a，thing that you'll often see people talk。

about in deep learning that it's how the，brain learns or how the brain works I。

think you should take any of these，comparisons with a massive grain of salt。

there's some very coarse comparisons，between brains and neural networks that。

we use today but I think you should not，keep them too seriously so that I'm kind。

of stepping back a little bit from these，two topics computer vision and machine。

learning both fall within the purview of，the larger research field of artificial。

intelligence so artificial intelligence，is very general very broad it's broadly。

speaking how can we build computer，systems that can do things that normally。

people do so that's kind of my，definition I think people will argue。

about what is and is not artificial，intelligence but I think we just want to。

build smart machines whatever that means，to any of us and I think there's clearly。

many different sub disciplines of，artificial intelligence but two of the。

most important clearly again in my，biased opinion our computer vision。

teaching machines to see and machine，learning teaching machines to learn and。

these are the topics that we'll study in，this class so then kind of where is deep。

learning fall in this regime ether me，would be a subset of machine learning。

and it intersects both computer vision，and falls within the larger AI ground I。

think it's important at the outset to，end so then this class is going to focus，at kind of this。

section right in the middle the，intersection of computer vision machine。

learning and deep learning to start out，with this slide is because it's really。

easy to get caught up in the hype these，days and think that computer vision is。

the only type of AI deep learning is the，only type of AI deep learning is the。

only type of computer vision but I think，none of these are true there are many。

there are types of AI which have nothing，to do with learning nothing to do with，deep learning。

there's classical results about symbolic，systems and other approaches to AI that。

are very different technically there's，areas of computer vision that do not use。

any very much machine learning over much，deep learning so I love it even though。

the focus of this class will be the，intersection of these different research。

areas I just want to keep I just want，you to keep in mind as a whole that。

there is a much broader realm of AI，research being done tonight around the。

world by different groups that falls，into different pieces of this pipe heart。

and of course there's many other areas，within AI that we won't talk about too。

much so there's natural language，processing things like speech。

recognition things like robotics and I，kind of ran out of space on the chart。

with many more sub areas but suffice to，say artificial intelligence is a，massively。

is a massively successful a massively，popular area of research an area of。

study these days that again with the，broad goal of making machines do things。

that people normally do you can imagine，that there's a whole lot of things that。

we might do out in the world that fall，under this umbrella of our different。

intelligence so that's kind of the big，picture roadmap and now for the route。

for the rest of the semester we're gonna，focus on this little red area in here。

but again don't forget that there's a，lot more to the world than what we're。

talking about in this class so today's，agenda is a little bit different from。

most of the lectures in this class，because again it is the first week so。

before we can really dive into that red，piece of the pie chart and talk about。

machine learning and deep learning and，computer vision all that really good。

stuff I think it's important to get a，little bit of historical context about。

how we got here as a field this has been，a hugely successful research area in the。

last five to ten years but deep learning，machine learning in computer vision。

these are areas with decades and decades，of research built upon them and all of，years。

have been a result of building upon，decades of prior research in these areas。

so today I want to give a bit a bit of a，brief history and overview of someone。

who puts historical context that let up，with the successes of today and then。

following that we need to talk about，some of the boring stuff of course。

overview logistics all that other stuff，that you expect to see in the first。

election class so let's start with so，we're going to do this in two ways right。

we're going to do a parent we're going，to do a parallel stream first we're。

going to talk about the history of，computer vision and we're going to sort。

of switch switch a little bit and we'll，cover the history of deep learning so。

before we dive into the material as any，sort of questions before we launch into。

this historical s-capepod know ok，perfectly clear，so if we go I think whenever you talk。

about a research area it's always，difficult to pinpoint the start right，else。

there's always prior work everyone was，inspired by something else that came。

before but with a finite amount of time，to talk about a finite number of things。

you got to cut the line somewhere so one，place where I like to draw the line and。

point to as maybe the start of computer，vision is actually not with computer。

scientists at all and happen it's from，this this seminal study of Hubel and。

Wiesel back in 1959 who were not，interested in computers at all they。

wanted to understand how the malian，brains work so what they did is they got。

a cat they got an electrode they put the，electrode into the brain of the cat into。

the visual cortex of the cat just the，part in the back of your head that。

processes visual data and with this，electrode they're able to record the。

neuronal activity of some of the，individual neurons in the cat's visual。

cortex so then with this somewhat，grotesque experimental setup they were。

able to have the cat watch TV and then，not really TV because it was 1950 time。

but they were able to show different，sorts of slides to the cat they cash in。

and with they had this general，hypothesis that maybe there's certain。

neurons in the brain that responds，different types of visual stimuli and by。

showing the cap different types of，visual stimuli and recording the neural。

activity from individual neurons maybe，we can start to puzzle out how this。

thing called vision works at all so，that's exactly，they did they got these cats they stuck。

neurons in their brains and they started，showing a bunch of different images on a。

slideshow to try to see what kinds of，images would activate the neurons and。

cats brains so they tried different，things you can show them make mice and。

fish and other kinds of things that cats，like to eat or play with but it was。

really hard to get any any solid signal，about what these neurons were responding。

to so what what one really interesting，discovery happened is you know today。

we're using PowerPoint back in the day，we've natural slide projectors and when。

you change the slide like there's kind，of a vertical bar that would move up and。

down the screen and what they，surprisingly found is that some of the。

neurons in the cat's brain which，consistently responds to the time when。

they change the slides and they even，though they couldn't recognize any。

patterns of what was how it was the cat，responding to things on the slides and。

they eventually discovered that it was，in fact this this moving vertical bar。

that was indeed causing some of the，neuronal activity in the cat's brain so。

with this hint they were able to puzzle，out that there are certain that there。

are different types of cells in the，brain that are responding to different。

types of visual stimuli many of them are，very hard to interpret but some of these。

easiest are these so-called simple cells，that they that they discovered so the。

simple cells would respond to an edge，that's maybe light on one side dark on。

another side at a particular orientation，at a particular position in the cat's。

visual field and if there happened to be，an edge at the right position on the。

right angle in the right place then that，particular neuron might fire that was。

very exciting because men may have some，concrete evidence of what it is that。

cats are actually responding to in their，brains then with a bit more exploration。

they remember to find other types of，cells in the brain that responded to。

even more complex patterns like the，complex cells that would respond to bits。

of motion or could respond to orienting，edges but anywhere in the visual appeal。

to give a sense of some sense of，translation and Berryman's in the visual。

representations that they perceive so I，think that this is really one of the。

bounding oh and by the way of course I，have to mention that these guys this was。

very seminal research and these guys won，the Nobel Prize for it in 1981 so this。

was a very important research in history，of science and psychology and vision。

overall but I like to point to this as，the beginning of computer，for a couple reasons one is this。

emphasis on oriented edges will see this，come up over and over again on the。

different architectures that we study，throughout the semester on the other is。

this hierarchical representation of the，visual system of building from simple。

cells that represent one thing combining，with complex cells and more and more。

complex cells that respond to more and，more complex types of visual stimuli。

this broad idea was hugely influential，on the way that people thought about。

visual processing and even on neural，representations more generally so then。

if we move forward a couple years in，1963 Larry Roberts then his that's when。

Larry Roberts graduated from MIT PhD and，did perhaps what was the first PhD。

thesis on computer vision here of course，it was 1963 doing anything with。

computers was very cumbersome doing，anything with digital cameras was very。

cumbersome so large portions of his，thesis just to talk about how do you。

actually get photographic information，into the computer because this was not。

something you could take for granted at，that time but even working through those。

constraints he built some system that，was able to take this this raw visual。

picture detect some of the edges in the，picture sort of inspire inspired by。

useful and weasels discovery that edges，were fundamental to visual processing。

then from there detect feature points，and then from there start to understand。

the 3d geometry of objects and images，now what's really interesting is that if。

you go and look at your Larry Roberts，for Wikipedia page it actually doesn't。

mention any of this at all，because after he finished his PhD he。

went on to become the founding father of，the internet and did went on to be a。

hugely a major player in the World Wide，Web and all of the networking。

technologies that were developed around，that time so doing the first PhD thesis。

in computer vision was kind of a low，point in his career，I think all of us can aspire to that。

successful so then moving forward a，couple of a couple more years people are。

getting really excitement so there was，this very famous study in 1966 from MIT。

a similar pack word proposed the the，summer computer vision project the。

summer computer vision project basically，what he wanted to do is like oK we've。

got digital cameras now they can detect，edges we know how all those cubed Wiesel。

told us how the brain works what we're，gonna do is hang a couple undergrads put。

them to work over the summer and after，the summer we show it we should be able。

to construct a significant portion of，the visual system man these guys are。

really ambitious back in the day because，now it's a clearly computer vision is。

not solved they did not achieve this，this a lot people and nearly 50 years。

later we're still plugging away trying，to achieve this what they thought they。

so moving forward into the 1970s one，so moving forward into the 1970s one。

hugely influential figure in this era，was was being Tamar who proposed this。

idea of stages of visual representation，then again kind of harkens back to。

Google and reasonable so here you can，see that maybe we want the input image。

then we have another prop another stage，of visual pops and we extract edges then。

from the edges we extract some kind of，depth information that maybe beacon。

segment objects and say which which，which parts of image belong to which two。

different types of objects and then，think about the relative depths of those。

objects and then eventually start to，reason about whole 3d models of the。

world and of the scene and then we'll be，bored of the seventies people were。

started to become interested in，recognizing objects and thinking about。

ways to build computer systems that，could not just detect edges and simple。

geometric shapes but more complex，objects like people bombs it was work。

about some things like generalized，cylinders and pictorial structures that。

built that try to recognize people as，easy formal configurations of rigid。

parts with some kind of known topology，and you can see ideas and this was this。

was out this was very influential work，at a time but the problem is that in the。

nineteen seventies processing power was，was very limited visual cameras were。

very limited so a lot of this stuff was，sort of，toy in a sense and as we move into the。

80s people's people have much more，access to better digital cameras more a。

more computational power and people，began to work on slightly more realistic。

images so one one kind of theme in the，80s was trying to recognize objects and。

images via edge detection I told you，that edges were going to be super。

influential throughout the history of，computer vision so there was a very。

famous paper from John Candy in 1986，that proposed the very robots algorithm。

for detecting edges and images and then，David Lowe the next year in 1987。

proposed the mechanism for recognizing，objects images by matching their edges。

so in this example you can imagine we've，got this this cluster razors and then we。

detect the edges then maybe we have some，template rate picture of a razor that we。

know about then we can detect the edges，of our template razor and try to match。

it into this image this cluttered image，there's a menu of all the razors and。

then by kind of matching edges in this，way you might be able to recognize that。

there are many ten razors in this image，and what are their relative。

configurations just based on matching，with our tumbler image and now I'm。

moving at moving on into the 1990s，people again wanted to build to more and。

more complex images more and more，complex scenes so here a big theme was。

trying to recognize objects via grouping，so here rather than maybe just matching。

the edges what we want to do is take the，input image and segment and segmented。

into semantically meaningful chunks，maybe like maybe we know that the person。

is composed of one meaningful chunk the，the different umbrellas would be。

composed of a different meaningful chunk，with the idea that if we can first do。

some sort of grouping then later Dallas，tree and recognizing or giving a label。

to those groups might be an easier，problem then in the 2000s a big theme。

was was recognition via matching and，this is a there was a hugely famous。

paper called sift by David loved by，David Lowe again in 1999 that proposed a。

different a different way of recognition，via matching so here the idea is that we。

would take our input image detect little，recognizable key points and different。

position 2d positions in the image and，have each of those key points we're。

going to represent its appearance using，some kind of feature vector and that。

feature vector is going to be a real，valued vector this somehow encodes the。

of image at that little point in space，and the end by very careful design of。

exactly how that feature vector is，computed you can encode different types。

of invariances into that feature vector，such that if we were to take the same。

image and rotate it a little bit or，brighten or darken the lighting。

conditions in the scene a little bit，that hopefully we would compute the same。

value for that feature vector even if，the underlying image were to change a。

little bit and there was a lot of work，in the it's been once we can extract。

these sets of robust and invariant，feature vectors then you can improve。

again perform some kind of recognition，via matching so that on the left if we。

have some template image of a stop sign，we can detect all these all these。

distinctive invariant feature key points，then on the right if we have another。

another image of at a stop sign this may，be taken from a different angle with。

different lighting conditions then by a，careful clever design of these invariant。

robust features then we can match and，then correspond points in the one image。

into points in the other image and，thereby be able to recognize that the。

right image is indeed a stop sign so，then another hugely influential work in。

the 2000s was the viola Jones algorithm，published in 2001 and this was really。

and they developed a very very powerful，algorithm for recognizing faces in。

images so here they would you know you，have an image then you want to draw a。

box where all the people's faces are and，this was notable for this this piece of。

work was notable for a couple reasons，one it was the first major use of。

machine learning and computer vision so，viola and Jones used some algorithm。

called the boosted decision trees that，were able to learn somehow the right。

combination of features to use in order，to recognize images they were to。

recognize faces and to what was，particularly notable was the very fast。

commercialization of this algorithm that，this this piece of research went very。

quickly from a sort of academic piece of，research publishing 2001 and within a。

few years this was actually being，shipped in digital cameras at the time。

so if you remember maybe they had like，an autofocus feature or you would kind。

of hold the shutter half down and it，would like beep a little bit and draw。

boxes are on the faces and then focus on，the people in the scene well that was。

most likely using this viola Jones，algorithm so this is a particularly，notable piece of work。

for those two reasons so now after they，kind of unlocked the box of using data。

and using machine learning to augment，our visual representations then moving。

on into the 2000s we began to see more，and more uses of machine learning more。

and more uses of data in order to，improve our visual recognition systems。

so one hugely influential piece of work，here was the Pascal visual object。

challenge so here they download a bunch，of them because now it's 2，000 layered。

Roberts had excellent computer vision，and invented the internet so we could。

then download images from the internet，to help build these datasets images and。

then we could get graduate students to，go and label those images and then then。

we could use your machine learning，algorithms to mimic the labels that the。

graduate students have written down the，images and then if you do that then you。

can see this nice crack on the right，performance increasing on this of this。

recognition challenge increased steadily，over time from about 2005 to 2011 so。

then this this brings us to the image，net learners feel visual recognition。

challenge so here this was a very very，large scale data set in computer vision。

that has become hugely influential and，has become one of the main benchmarks in。

computer vision even leading up to this，day so the image in that classification。

challenge was this fairly large data set，of more than about 1。4 million images，and each of those 1。

4 million images，were labeled with one with one of a，thousand different category labels and。

the big the big new piece of innovation，here was that if you kind of do the math。

here you gonna be a lot of graduate，students label all this stuff so the big。

piece of innovation here was to not，label data using graduate students，instead this this made use of。

crowdsourcing so here you could go on，services like Amazon Mechanical Turk and。

then person up little pieces of work and，then blast mode on over there over there。

over the Internet and then people，anywhere in the world could label。

McConnel images get paid a couple of，cents for each image they label and that。

was able to massively increase those，amano I mean this this is beneficial in。

two ways right because one researcher，get people to label their data without。

being constrained by the number of，graduate students that they have and to。

it become a nice source of income for，some people who were bored at worked and。

just like this or or in classes that，gets maybe or not it's still weird it's。

the running by the lady that grew up，introducing tasks but anyway this became。

a hugely influential data set and，computer vision and more than a data set。

it became a benchmark challenge so they，had every year they ran a competition。

when they were different researchers，would compete and try to build their own。

algorithms that would try to recognize，objects in this limit in this in his。

classification challenge and this became，somewhat jokingly known sometimes as the。

Olympics of computer vision that there，was a period of time from maybe in the。

the mid 20 2010 the late 2000s early 20，times when people would just really。

excitedly want to look at the results of，imagenet competition every year and see。

what kind of advances the field had made，last year then then given that I told。

you is this competition you can look at，what was the error rate on this on this。

competition moving over time so the，first time the competition was ran in。

2010 in 2011 we were sitting in error，rates of around 28 around 25 and then。

something big happened in 2012 so at the，2012 imagenet competition suddenly the。

error rates dropped in a single year，from 25% all the way down to 16% and。

when it and this and after 2012 errors，just kept on diminishing diminishing。

very very fast such that once we got to，about 2017 we were building systems that。

could compete on this imagenet challenge，and to perform even better than humans。

when they try to recognize images in，this data set so then the question is is。

what happened in 2012 so what happened，in 2012 is that deep learning came onto。

the scene and this was really the，breakthrough moment for deep learning。

and computer vision researchers suddenly，woke up and saw that there's this this。

crazy new thing that is suddenly，sweeping our field so in 2012 there was。

this absolutely seminal paper from Alex，pachowski，Ilya Salisbury and Geoff Hinton where。

they proposed that deep convolutional，not work Alex not that just crushed。

everyone else at the imagenet，competition five years and four people。

working in computer vision at that time，this was shocking this felt like there。

was this Brandon thing that just came，out of nowhere and just suddenly crushed。

all these algorithms that we've been，working on you know as we kind of watch。

this history of computer vision walking，from the 1950s all the way up into the。

bat'leth till the 2000s，you'll notice that neural networks were。

not a mainstream part of that history，throughout much of computer visions。

history so when this suddenly appeared，it felt a lot of computer vision。

researchers like this was this brand-new，thing suddenly appearing all at once。

that this brand-new exciting technology，and that was a little bit flawed because。

this was not a brand new technology，there had been a parallel stream of。

researchers going back similar similarly，similar amounts of time that had been。

developing and holding these techniques，for decades and 2012 was the sudden。

breakthrough moment where all of that，hard work paid off and became mainstream。

so then let's talk a little bit about，the history of deep learning kind of。

going back in time yet again so then，about the same time that Hubel and。

Wiesel were doing some of their seminal，work on the visual recognition and Katz。

there was another very influential，algorithm called though actually wasn't。

even algorithm Oh called the perceptron，so the perceptron was one of the。

earliest systems that could learn as a，computer system but what's interesting。

is that this was what 1958 so the idea，of an algorithm the idea of programming。

the computer these were already quite，these were quite novel research topics。

on their own at that Friedan style so，the perceptron was actually implemented。

as a piece of hardware they there's a，picture of it on the right that is the。

perceptron it was this giant like，cabinet size thing with like wires going。

all over the place it had weights that，rep that were stored in these。

potentiometers which I don't even know，what that is because I'm a computer，scientist。

and and these these these weights were，just mechanically up the values of these。

weights were changed mechanically dear，during learning by a set of electric。

motors which again I'm not a mechanical，engineer so I definitely could not build。

this thing but what was but even though，this was this mechanical device that was。

bigger than a person it actually could，learn from from data somehow and it was。

able to learn to recognize letters of，the alphabet on these tiny 20 20 by 20。

images that were super state-of-the-art，in 1958 but so if I don't want to talk。

about any of the math with us for the，perceptron but if you were to look at it。

with modern eyes we would probably call，it a linear classifier and we'll talk。

about next week on Wednesdays lecture so，this perceptron got a lot of people。

really excited it caught people thinking，like wow here's a mechanism that allows。

machines to learn novel stuff from data，without people having to explicitly。

program how it's going to work and all，of that kind of came to a crashing halt。

in 1969 when Marvin Minsky and Seymour，Packard who published this this infamous。

book called perceptrons in 1969 and what，mitts in Peppard pointed out in their。

book basically was that perceptrons are，not magical devices right the perceptron。

is a particular learning algorithm and，there are certain types of functions。

that it can learn for our present and，other types of functions that it cannot。

to learn to represent in particularly，they pointed out that the act of the the。

actual function is not something that is，learn about my eyelid by the linear。

perceptron learning algorithm that we'll，talk about again a little bit more next。

week and this is this sudden realization，well okay so the normal story that gets。

told is that the sudden realization of，this book was that oh these these。

learning algorithms are not magical，there's things they can't learn and。

people just lost interest in the field，and work in learning work in perceptrons。

kind of dried up for a period of time，following the release of this bugger but。

what's interesting is that I think，nobody actually read the book because um。

if you actually read it there are，sections where they say yes，the original perceptron learning。

algorithm is quite limited and it can，only represent certain functions but。

there's something else there's another，potential version of the algorithm。

called a multi-layer perceptron that，actually can learn，many many many many different types of。

functions and is very flexible in its，representations but that Penna got lost。

in the headlines at the time and nobody，realized that and people just heard that。

for sub Tron's didn't work and we're，dead，so you should definitely read the。

assigned reading but then going forward，because then going forward quite some。

amount of time we skip ahead to 1980 and，there was this very influential paper。

called system proposed called the neocon，neutron that was developed by Fukushima。

with a Japanese computer scientist and，he wanted he was directly inspired by。

Hubel and Wiesel idea of this，hierarchical processing of neurons。

remember people and Wiesel talk about，these business simple cells these，complex cells。

he's hierarchies of neurons that could，gradually learn more learn to and see。

more and more complex visual stimuli in，the image so Fukushima proposes this。

computational realization people and，weasels formulation if you call the new。

economy economy so the neocon Neutron，interleaved two types of operations one。

were these computational simple cells，that if we were to look at them with。

modern terminology would they would they，look very much like convolution and the。

latter was these computational，realizations of complex cells that again。

under modern terminology look very much，like the pulling operations that we use。

in modern evolution or networks so，what's striking is that even back in。

this neo cognate Ron from 1980 had an，overall architecture and overall method。

of processing that looked very similar，to this famous Alex net system that。

swept in 2012 um even the figures that，they have in the papers look pretty。

similar so they gotta be the same thing，right but what was striking but the Neo。

cognate Ron is that they defined this，computational model they had the right。

idea of convolution and pooling and，hierarchy but they did not have any。

practical method to train the algorithm，because remember this there's a lot of。

learning awaits in this system a lot of，connections between all the neurons。

inside they need to be set somehow and，even then Fukushima did not have an。

efficient algorithm for learning to，properly set all those although。

free-weight parameters in the system，based on the based on data。

so then a couple years later there was，this again massively influential paper，by rumelhart。

and Ted Williams in 1986 the interview，introduced the backpropagation algorithm。

for training these multi-layer，perceptrons so remember that in the。

perceptrons book there was this thing，called a multi-layer perceptron that was。

thought to be very powerful in its，ability to represent and learn to。

protects functions well in the back，propagation in in this paper that。

introduced the back propagation，algorithm was one of the first times。

that people were able to successfully，and efficiently training these deeper。

models with multiple layers of，computations and this looks very much。

like a modern neural network that we're，using today that if you look at one you。

kind of look at this paper and over to，knock them through it you'll see they。

talk about gradients and they talk about，jacobians impressionnant all this kind。

of mathematical terminology that we，think about today when we're when we're。

building and training neural networks so，these look very much like the modern。

fully connected networks that we still，use today there are sometimes called。

multi-layer perceptrons in homage to，this of this long history so now that。

does not let a lot of people that let's，do a lot of small people sort of get。

really excited about them there are，networks together and try to figure out。

different types and structures of neural，networks that could be built and trained。

powered by this new back propagation，algorithm and one of the most。

influential works are on that time was a，young McCune at almost paper in 1998。

that introduced the idea of a，convolutional neural network so this。

looks again very much like the Fukushima，algorithm that we split this what they。

do here is they took Fukushima this kind，of idea of convolution and pooling and。

multi-layer multiple layers inspired by，the visual system and combine that with。

the back propagation algorithm from，rumelhart，paper in 1986 and with that combination。

they were able to train this，convolutional these very large at the。

time convolutional neural networks that，could learn to recognize different types。

of things and images and this was a，hugely successful system it didn't I。

think it actually was very successful，commercially so in addition to being a。

piece of very influential academic，research it was also deployed in a，commercial system by NEC。

labs and，for a period of time this convolutional，neural net system developed by that。

group was actually being used to process，the handwriting get a lot of checks that。

were written in the United States at，that time um one thing that I found。

stated that up to 10% of all cheques in，the United States we're actually being。

having their the numbers on the cheque，being read automatically by these。

convolutional neural net systems in the，late 90s and early 2000s and again if。

you look at exactly what this this，algorithm is doing Lynette was kind of，like this。

so the algorithm here was called，Lynette's after Don McCune ironies。

pressure and then that if you look at，the structure of an algorithm it looks。

very similar almost identical to the，types to the to the algorithm that was。

used in Aleks that near nearly nearly 30，years later，so then emboldened by the success they。

were again a small group of people，throughout the late 90s and early 2000s。

whom were really interested in trying to，move them in in push neural net systems。

and figure out ways to train neural net，systems that were ever bigger ever。

deeper ever wider and could be used on，an increasing variety of tasks and。

around this period of time in the 2000s，was wearing the term deep learning first。

emerged where it records were it where，the term deep was meant to refer to。

multiple layers in these neural network，type algorithms there's a and so this。

was really not a super mainstream，research area at this time there was a。

relatively small number of research，groups and relatively small number of。

people studying these ideas are on this，time but I think a lot of the。

fundamentals that were reaping the，rewards of now were really developed。

during this period of time in the 2000s，when people started figuring out all the。

new modern trips to train different，types of neural network systems so that。

finally brings us back to Alex fat and，then in 2012 we had this great。

confluence of this great this this，computer vision task called image net。

that people in computer vision were，super excited about we had the second。

new techniques convolutional neural，networks and efficient ways to train。

them that have been developed by this，parallel research community and。

everything just seemed to come together，just，time in 2012 so then from 2012 to。

present day we've seen an absolute，explosion in the in the usage of。

convolutional and other types of neural，networks across both across computer。

vision and across other types of related，areas in AI and across computer science。

so here on the Left we have the Google，Trends for deep learning that shows you。

this massive sort of exponential growth，that really took off starting in 2012。

and on the right this is a photo I took，at the computer vision of pattern。

recognition conference on this summer in，2019 so this is one of the premier。

venues for academic publications in，computer vision and here is a graph that。

they were showing at the keynote for，that for that conference where they。

showed on the x-axis the year of the，conference and on the y-axis of the。

number of submitted and accepted papers，in this and this conference so you can。

see that even though the last five to，ten years have resulted in this massive。

explosion both of machine learning，systems both maybe in popular perception。

especially from Google Trends as well as，the massive increase in academic。

interest into both machine learning，systems and computer vision systems as。

evidenced by this fine spot on the right，and if you look around the field today。

we see the convolutional networks other，types of deep neural network you see are。

being used for just about every possible，application of computer vision that you，can imagine。

so from 2012 these convolutional，networks are really everywhere they're。

getting use from such a wide diversity，of tasks like image classification we。

want to put labels on images or image，retrieval or want to retrieve images。

from collections things like object，detection we want to recognize the。

positions of objects and images while，simultaneously label like that the。

record should be image segmentation I'm，threatening to fix the slide where we。

want to label the what where this is，going back to this idea of semantic。

grouping you saw for computer vision in，the 90s where we want to label the pics。

of pixels as being part of a cohesive，whole comments are going to use for。

things like video classification on，activity recognition things they're。

gonna use for things like pose，estimation where you want to say how are。

the exact geometric poses of people，arranged in images even for things that。

don't really feel like classical，computer vision like playing Atari games，with a。

process the visual input of the Atari，game with a convolutional neural network。

and combine that with other sorts of，learning techniques in order to both。

jointly learn a visual representation of，the video game world as well as how to。

play in that normal um convolutional，neural networks are also getting use for。

visual tasks that are about visual data，at，so convolutional networks are getting。

used in things like medical imaging to，diagnose different types of tumors。

diagnose different types of skin lesions，other medical conditions they're going。

to use in galaxies classification，they're getting used in tons of。

scientific applications like classifying，whales or elephants or other types of。

people or because there's this problem，where scientists want to go out into the。

world and collect a lot of data and then，be able to use images and visual。

recognition as a kind of universal，sensor to make use of all this data that。

they collect and gain insights into，their their particular field of。

expertise that they're interested in and，we've seen computer vision and。

convolutional networks branch out into，all these other areas of science and。

just open up and unlock lots of new，applications just across the board。

they're big the comments are going to，use for all kinds of fun tasks like。

image captioning that we can write，systems we can build systems they can。

write natural language descriptions but，images these are using convolutional net。

words we can use convolutional networks，for generating arts so we can know we。

can make all these kind of psychedelic，portraits again using a convolutional。

neural networks so then we might ask，what was it that happened in 2012 that。

made all of this take off well I think，the jury's out and we'll have to see。

what the story ins right 50 years from，now but my personal interpretation is。

that it was a combination of three big，components that came together all at。

once one was the set of algorithms that，we saw that there was a stream of people。

working on deep learning at common，neural networks and machine learning who。

had developed these powerful set of，tools for representing learning。

functions and for learning that was the，fact propagation algorithm we saw this。

the second stream of data that with the，rise of digital cameras later Robertson。

running the internet and people to，develop a crowdsourcing we were able to，collect unprecedented。

to label data that could be used to，train these systems and the third piece。

that we haven't really talked about was，the massive rise in computational。

resources that has been continually，happening throughout the history of。

computer science so one graph that I put，together that I find particularly。

striking is looking at the gigaflops of，computation per dollar as a function of。

time so here on the blue you can see，these are different types of CPUs are in。

a CPU central processing units the thing，that's remained on your cloud with all。

of your laptops truck and they get，faster but not that much faster over。

time but starting in 2008 there was some，really interesting developments with。

GPUs graphics processing units and so，these were these special-purpose pieces。

of hardware that were originally，developed to pump up pixels in computer。

graphics applications but around 2008，people started developing techniques to。

run generalized programs on these，graphics processing units and starting。

and and then over time these techniques，became more and more easy to write。

general-purpose scientific code and，mathematical code to run on these。

massively parallel or graphics pasta，units and then if you look at the。

timeline from 2006 to 2007 teen and look，at the gigaflops per dollar on these。

graphics processing units you can see，that although this exponential moore's。

law may not have held up for CPUs it，actually has been we actually haven't。

seen exponential increases in GPU，computing power over time over the last。

10 years and if you look at maybe the，Alec and this has been striking even in。

the last couple of years so if you look，at the Alex next system in 2012 he was。

using this GTX 580 GPU that was very，very exciting at the time if you're a。

gamer and if you push it on into more，recent cards like the gtx 980ti。

or more recently a 2080 ti about update，the slides then you can see that the。

cards we have even five years later are，are literally exponentially more。

powerful than the cards that they were，going to keep it in 2000 as well so I。

think that it was really this this，confluence of algorithms of data and of，massive increase。

in computation fueled by advances in，GPUs that led to them all this magic。

happening in 2012 that led to all these，these new applications of convolutional。

networks on different types of computer，vision and in recognition of all of this。

in recognition of the impact of computer，vision and deep learning across the。

field the 2018 Turing award was awarded，to Yahoo of NGO Jack Hinton and Yama kun。

for their work on pioneering many of the，deep learning ideas that we'll learn。

throughout this class and for those of，you who don't know the Turing award is。

basically that considered the Nobel，Prize equivalent in the field of。

computer science so this just happened，last year and this was just a。

recognition that this has been a，massively influential piece of research。

that's been changing all of our lives，over the last over the last several。

years but I think it's important to stay，humble and realize that despite all of。

the successes that we've seen in，convolutional networks in deep learning。

and computer vision I think we're really，still a long way away from building。

systems that can perceive and understand，visual data to the same fidelity and and。

power and strength as humans one image，that I like to use to exemplify this is，this this example。

so what's if we were to send this to a，convolutional network he would probably。

say person or scale or locker-room maybe，but if we were to look at this you see。

quite a different story，you see a guy standing on a scale you。

know how scales were which require some，into some idea of physics you know that。

he's looking at the scale you know that，he's trying to measure his own weight。

you know that people tend to be，self-conscious about their weight you。

know that the person behind him is，stepping on the scale and pushing down。

because of your knowledge of physics you，know that that's going to make you feel。

for a bigger number because of your，knowledge of that guys psychology you'll。

know that that might make him feel，embarrassed or uncomfortable because he。

thinks he ate too much and then you also，know who that person pushing down on the。

scale is and because of your knowledge，of who he is it makes it may be。

surprising that he's acting in this way，you understand you can see the people。

behind him watching this scene and，know，how it is the people look at each other。

you understand that maybe they're，surprised that this guy is doing this。

thing that's causing this guy to be，embarrassed so there's a lot going on in。

this image that we as human as visually，intelligent humans could understand and。

perceive and I think we're a long way，away from building computer vision。

systems that can match that level of，visual fidelity but I'm hoping that as。

we move forward and continue to advance，the field maybe one day we'll get there。

but in the meantime I think that，computer vision technology really has。

massive and massive potential to improve，all of our lives，it'll make our lives more fun through。

sort of new videoman applications，applications in VR AR it'll make our。

transportation safer with advances in，autonomous vehicles it'll lead to。

improvements in medical imaging and，diagnosis and overall I think computer。

vision as a whole has a massive Trek，massive ability and potential to。

continue leading to massive improvements，in all of our day-to-day lives so that's。

why I think we should be studying，computer vision that's why I make it。

excited to be teaching this class this，year so that basically covers our brief。

history of computer vision of deep，learning except there's one little spot。

on the timeline that we didn't fill out，and that's this class so with that it's。

time to if there was any if there's any，questions about historical stuff then。

we're going to move on to course，logistics，you're out no okay great so for staff。

who are wheaton I'm Justin Johnson I'm a，new assistant professor here in the。

computer science and engineering，engineering department this is the first。

class I'm teaching here at Michigan this，is the first time I've been in this room。

so glad I found it about the laptop，identity but I'm excited to be here。

excited to be teaching you guys this，class there we have an amazing team of。

graduate student instructors that are，going to be helping us out this semester。

the standard will be docile so these，the standard will be docile so these。

guys are all experts in computer vision，they're all PhD students here moonscape。

works and video understanding and，generative models keep on course and。

robustness and generalization gluant，works a lot in visual vision plus。

language so if you have questions both，those particular research areas you，should go talk to them。

so how to contact us so this is an，important slide right taking pictures。

with this comes a good idea I probably，could feel some kindness to something。

we'll extract abuse formation out from，them automatic but we kept on a course。

website that's up in this URL the course，website has followed the information。

that you'll need for others throughout，the quarter you can find the syllabus。

this head so the schedule you'll find，links to assignments they're your。

clients links the lecture videos，assuming a set of lecture capture。

properly really important we're going to，use the Gaza or most communication with。

you guys so we really encourage you if，you have questions for the course。

material we're going to use the Gala's F，is our main mechanism to communicate。

back and forth with you guys so if you，have questions about course content。

questions about material post post on，Piazza and similarly if we when we need。

to make announcements back to the class，to announce thing is like of the。

homeworks about changes to logistics，Piazza，so it's really important that you guys。

get signed up as quickly as possible and，one piece of the note is that please。

don't post any code on P about public，questions on Piazza if you do need to。

ask particular questions about code we，ask that you make private questions that。

are visible only to you start only to，the instructor so we will have canvas I。

I think I need to suck that up still，this week but we're really use canvas。

primarily for just turning in，assignments，mostly will be using Piazza and the。

course website for this class we will，have office hours both me and the GSIS。

started next week and you'll be able to，find the times and locations of the。

office hours on the Google Calendar that，I set up here finally。

we really want most the vast majority of，communication you do with us should be。

should be through Piazza but if you have，some kind of very sensitive topic that。

you would prefer to discuss directly，with me then you can email me directly。

but for the vast majority of，circumstances you should be going，through Piazza for four course。

communication that will ensure that，everyone all will all open teaching。

staff is able to help you in a timely，manner and if you're able to make and if。

you're making public questions and lets，you all help each other and learn。

collectively and learn from each other's，mistakes，I think Piazza is really great learning。

tool for that so we're going to have an，optional test in text level there's no。

required textbook for this class，on this schedule you'll find on the。

website there will be recommended，readings for all of the lectures this。

this text this textbook is totally，optional and it's completely available。

for free online you don't have to visit，being purchased a copy if you don't。

watch it so on course content and，grading we're gonna the main bulk of the。

course is gonna be six programming，assignments oh is that a problem is。

that's I think these are gonna be really，exciting assignments we're going to use。

Python high court and Google collab and，we're gonna walk you through the。

implement eight the detailed，implementations a lot of the ideas that。

we talked about in lecture we will have，a midterm exam and we will have a final。

exam but there will not be an important，project the majority of the stuff will。

be learning us through the programming，assignments so we have a leak policy so。

don't turn it in late but more seriously，you all get three free big days of use。

on your homework assignments you don't，have to tell us beforehand just randomly。

and then I can automatically once you've，exhausted your late days I'm gonna take。

25% earth-protecting something like，that's reasonable，are there any questions about content of。

policies late days anything like that，yeah over here yeah so the question is。

will the course materials be available，for people not on the waitlist and they。

will be as really available as I can，possibly make not so even if you can't。

get an open the class you can definitely，feel free to follow along with the。

lecture slides with lecture videos what，the course，yeah question yeah it's up to you you're。

all grown up so you can use the funny，lengthiest first time as you want but we。

you take too many and we were zero so I，don't recommend that but three ladies。

you can use as many as you want and，expert ladies you somebody as you want。

for sign that but we'll just take this，tape off lines and sizes here yeah so。

let's talk about collaboration policy so，we really encourage you guys to work。

together in groups I think it's great to，discuss which course material it with。

your classmates and to learn together，but we have a couple of ground rules。

about that for a collaboration policy，one is that everything you submit should。

be your own work it's fine to talk about，ideas with other other students that's。

great and encourage but you shouldn't be，sharing or looking at each other's code。

word necessarily you can talk about，things conceptually but you shouldn't be。

turning on the same code as as people，you work with secondly on the flip side。

don't share your solution code to other，people this means don't post on Piazza。

don't give it to your to your roommates，don't throw down big puzzles because。

that will make it easier and more，tempting for other people to violate。

collaboration policy and review，charities and third when you turn in。

assignments we have to indicate who you，work with what would in turn in your。

assignment and will be more equal in，instructions on that later，and in general training in something。

late or incomplete is much better than，potentially violating collaboration。

policies and not just in this course but，more generally any questions about that。

okay so then of course philosophy what，are we here for right all right yeah。

this class is not learn pipework too，many games this class is dogs learn deep。

learning in ten lines of Python you can，find tutorials on the internet that tell。

you how to do that that's what you want，but I think that learning about deep。

learning in that way does yourself a，huge disservice I think that you want to。

focus on fundamental concepts we want us，we want you to understand not just the。

latest and raised API level API is the，raft，answer club we want you to understand。

the fundamentals of how those these guys，might have been implemented why I didn't。

let it the way they work such that when，faced with the next piece the next bit。

of technological tools you you，understand the fundamentals and you do。

them yourself what that means is that，you'll be writing a lot of backdrop code。

yourself in this course I think that，it's very important for people to learn。

how to compute gradients and how and how，the computation of gradients affects the。

overall flow of learning pressure system，so for the first several assignments。

you'll be using no autographs you'll be，using Java tensorflow still be deriving。

and in fluent in your own background，your own gradient computations and you。

will be a better computer scientist born，so given that we prefer to move afraid。

to write inventory for the purpose of，pedagogy we encourage you we're going to。

encourage you to write and stretch，rather than relying on existing open。

source implementations again this will，make you a better keep learning。

practitioners that said we're also，practical we will well we're going to。

give you lots of tools and techniques，for debugging and training big neural。

networks because it's tricky when you，can't rely on that find that ten lines。

of code wrapping around lots of stuff so，we're going to talk a lot about how you。

can practically get these things to work，what tips and tricks should you be using。

when developing and debugging and，training their networks we will use。

state of the art software tools like I，taught you tensor flow but only after。

you've earned your wings by writing a，lot of Badcock code yourself we're going。

to focus on state of the art a lot of，the material that we cover in this。

course despite the long historical，context we talked about in this lecture。

but the majority of the actual concrete，implementations and concrete results，this course。

have been discovered in the last five to，ten years so this has a couple of。

interesting applications for，implications for teaching a course that。

means that there aren't good textbooks，for this stuff that means that no you。

there might not be great resources，outside of original piece of original。

research papers for learning about this，stuff，so that's going to be maybe a bit of us。

a bit of a struggle and a bit，challenging but on the upside I think。

it's really exciting to be learning，about such deep in our material in a。

classroom setting so also in philosophy，we want you could also have a little bit，of fun。

so we'll be Petzl we'll be covering some，some sort of fun topics like image。

captioning that you've got a good laugh，when I put it up here couple slides ago。

and some B's on a deep dream and our，artistic style transfer that lets you。

use neural networks to generate new，pieces of art not just improving our。

lives so in terms of the course，structure the first the bird the take。

down the first half the course will，focus on fundamentals we'll talk about。

the details of how to implement，different types of neural networks。

we'll cover building a fully connected，commotion all recurrent net neural。

networks will talk about pug debug them，how to implement them how to train them。

and they'll be very detailed and by the，end of this module is goal basically。

implementing your own convolutional，neural network system from scratch now。

in the second half of the course we're，going to shift a little bit in flavor。

and here we're going to focus more on，applications and more emerging sort of。

research topics so around that point in，the course you'll notice the bit of。

shift in tone in the lectures so they，will become a little bit less detail。

will sometimes skip over some of the，low-level details and perhaps refer to。

put your papers if you need to know，those details and instead the lectures。

will more focus on giving you an，overview of how people are how these。

different things are used across，different applications in computer。

vision and beyond well in the second，half we'll talk about things like 100。

detection image segmentation 3d vision，videos we'll talk about attention，formers。

vision language generative models I，think it's gonna be a lot of fun but。

because there's a lot to get through，first homework assignment will be out。

over the weekend that will cover，basically an intro and a warm-up to the。

collab and height or the environment，that we'll be using for our quarter so。

this should not this is not intended to，be difficult or a long assignment this。

should be your home over the weekend and，whenever we get it out it'll be Zoo will。

be after that and everything you need to，do this first homework assignment will。

get through the con based lecture so，with that said welcome to the class。

come back on Monday when we'll talk，[Applause]。

![](img/00f7bb7b67bae4c69475f89f019f3dd6_1.png)

![](img/00f7bb7b67bae4c69475f89f019f3dd6_2.png)