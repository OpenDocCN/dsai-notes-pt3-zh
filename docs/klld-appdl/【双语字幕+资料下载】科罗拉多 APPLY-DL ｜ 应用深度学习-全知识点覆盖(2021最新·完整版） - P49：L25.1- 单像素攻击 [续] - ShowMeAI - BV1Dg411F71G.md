# P49：L25.1- 单像素攻击 [续] - ShowMeAI - BV1Dg411F71G

spent，quite some time on that table and that，was a good exercise for us to understand。

what is the difference between a white，box attack，a black box attack and you have two。

different black box attacks，one is that you have access to the。

network or at least a copy of a network，and the other one is that you have a。

totally different architecture，and using them you have to generate your。

adversarial examples and then you can，attack as an adversary。

the next paper is interesting because it，says that you can take the text to the，extreme。

you can actually change one pixel in an，image。

![](img/8bbb491565a79c7c0c72716d969a2087_1.png)

and manage to fool a deep neural network，these are some examples。



![](img/8bbb491565a79c7c0c72716d969a2087_3.png)

you have a ship you change one pixel and，then it's gonna turn into a car。



![](img/8bbb491565a79c7c0c72716d969a2087_5.png)

that's a horse it's gonna turn into a，frog etc，so you can change a cat to a dog by。



![](img/8bbb491565a79c7c0c72716d969a2087_7.png)

changing only one pixel，so these are impressive results but what，is the math behind it。



![](img/8bbb491565a79c7c0c72716d969a2087_9.png)

we said we have a target classifier we，have our original image。



![](img/8bbb491565a79c7c0c72716d969a2087_11.png)

which is being correctly classified as，class t we denote f of t of。



![](img/8bbb491565a79c7c0c72716d969a2087_13.png)

x to be the probability of x belonging，to class d，we are looking for additive adversarial。



![](img/8bbb491565a79c7c0c72716d969a2087_15.png)

perturbations，we have a target class which we are，calling it。



![](img/8bbb491565a79c7c0c72716d969a2087_17.png)

adv and we want to increase the。

![](img/8bbb491565a79c7c0c72716d969a2087_19.png)

probability of that target class，by adding a small perturbation to our，original image。



![](img/8bbb491565a79c7c0c72716d969a2087_21.png)

we are interested in black box so we，don't have access to f，we can only evaluate it and we are。



![](img/8bbb491565a79c7c0c72716d969a2087_23.png)

interested in，zoom l0 norm which is basically counting。



![](img/8bbb491565a79c7c0c72716d969a2087_25.png)

the number of pixels，that are different and in our case，because we want to take it to the，extreme。



![](img/8bbb491565a79c7c0c72716d969a2087_27.png)

we set d to be one it means that you are，only allowed to change one pixel。



![](img/8bbb491565a79c7c0c72716d969a2087_29.png)

and then because you want it to be a，black box attack and because。



![](img/8bbb491565a79c7c0c72716d969a2087_31.png)

that maximization problem is a very hard，one，we don't have access to gradients and。



![](img/8bbb491565a79c7c0c72716d969a2087_33.png)

even if we have access to gradients，this is not a nice objective function to。



![](img/8bbb491565a79c7c0c72716d969a2087_35.png)

maximize because of the constraint so，it's basically a count constraint you're。



![](img/8bbb491565a79c7c0c72716d969a2087_37.png)

counting the number of pixels so we're，going to use。



![](img/8bbb491565a79c7c0c72716d969a2087_39.png)

differential evolution and what is a，differential，evolution i'm going to tell you next but，for now。



![](img/8bbb491565a79c7c0c72716d969a2087_41.png)

it's an optimization algorithm for，solving complex。



![](img/8bbb491565a79c7c0c72716d969a2087_43.png)

optimization problems and in general it，belongs to the class of。



![](img/8bbb491565a79c7c0c72716d969a2087_45.png)

evolutionary algorithms and we saw an，example of an evolutionary algorithm in。



![](img/8bbb491565a79c7c0c72716d969a2087_47.png)

when we were doing automl that one was a。

![](img/8bbb491565a79c7c0c72716d969a2087_49.png)

was an aging evolutionary algorithm this，one is，differential evolution so what is the。



![](img/8bbb491565a79c7c0c72716d969a2087_51.png)

space，where are we trying to search for a，solution so。



![](img/8bbb491565a79c7c0c72716d969a2087_53.png)

x1，and y1 is going to give you the location，of your pixel，for instance the 10th location in the x。

direction。

![](img/8bbb491565a79c7c0c72716d969a2087_55.png)

and the 2nes location in the y direction，is going to give you。



![](img/8bbb491565a79c7c0c72716d969a2087_57.png)

this pixel and then we want to set the，color we want to set。



![](img/8bbb491565a79c7c0c72716d969a2087_59.png)

with a。

![](img/8bbb491565a79c7c0c72716d969a2087_61.png)

population initially maybe you have 400，initial configuration or initial。



![](img/8bbb491565a79c7c0c72716d969a2087_63.png)

candidate solutions，in this case we have d of them d could，be 400。



![](img/8bbb491565a79c7c0c72716d969a2087_65.png)

and each one is going to be identified，by the location of the pixel and red，green blue。



![](img/8bbb491565a79c7c0c72716d969a2087_67.png)

and initially we are going to sort，things random so we are going。

we are going to do a random search we。

![](img/8bbb491565a79c7c0c72716d969a2087_69.png)

are going to sample，number。

![](img/8bbb491565a79c7c0c72716d969a2087_71.png)

from 1 to 32 and we select that at，random。

![](img/8bbb491565a79c7c0c72716d969a2087_73.png)

according to the uniform distribution if，your data set is。



![](img/8bbb491565a79c7c0c72716d969a2087_75.png)

c410 and if it is imagenet，you're gonna select those numbers from 1，to。



![](img/8bbb491565a79c7c0c72716d969a2087_77.png)

227。 so you pick two numbers，at random from that range according to。



![](img/8bbb491565a79c7c0c72716d969a2087_79.png)

the normal distribution，and for red green blue we are going to，use sorry。



![](img/8bbb491565a79c7c0c72716d969a2087_81.png)

according to uniform distribution for，red green blue we are going to choose。



![](img/8bbb491565a79c7c0c72716d969a2087_83.png)

the normal distribution it's going to，have a mean and it's going to have a。

variance that's going to give us the，initial。

![](img/8bbb491565a79c7c0c72716d969a2087_85.png)

population and initially these are going，to be。

![](img/8bbb491565a79c7c0c72716d969a2087_87.png)

our parents we have 400 of them and，we're going to create，children that are the candidate。



![](img/8bbb491565a79c7c0c72716d969a2087_89.png)

solutions so we're going to，pick the best of them and then do some，mutation。



![](img/8bbb491565a79c7c0c72716d969a2087_91.png)

to come up with the children so how are，we going to come up with the children。



![](img/8bbb491565a79c7c0c72716d969a2087_93.png)

that's where the differential evolution，comes in，you pick j k and l。



![](img/8bbb491565a79c7c0c72716d969a2087_95.png)

so you pick three members of your，parents。

![](img/8bbb491565a79c7c0c72716d969a2087_97.png)

from the previous generation so g is，denoting the generation from the。



![](img/8bbb491565a79c7c0c72716d969a2087_99.png)

previous generation，you select three points i j and k。



![](img/8bbb491565a79c7c0c72716d969a2087_101.png)

and to go to the next point in the next，generation。



![](img/8bbb491565a79c7c0c72716d969a2087_103.png)

and basically do your mutation you take，xj，and you add the difference of k minus l。



![](img/8bbb491565a79c7c0c72716d969a2087_105.png)

and that's going to give you a new point，x i that's going to be a member of your。



![](img/8bbb491565a79c7c0c72716d969a2087_107.png)

candidate solution that's going to be a，child so x i，is an element of the candidate solution。



![](img/8bbb491565a79c7c0c72716d969a2087_109.png)

now so from your，parents that's how you obtain your，children。



![](img/8bbb491565a79c7c0c72716d969a2087_111.png)

and as i said g is denoting the current，index。

![](img/8bbb491565a79c7c0c72716d969a2087_113.png)

of the generation and we are going to do，100，100 iterations so g is going to be your，iteration。



![](img/8bbb491565a79c7c0c72716d969a2087_115.png)

you're going to have a for loop on g and，then you keep selecting。



![](img/8bbb491565a79c7c0c72716d969a2087_117.png)

three random numbers or three random，elements of your parents。



![](img/8bbb491565a79c7c0c72716d969a2087_119.png)

to obtain the next candidate solution，in the next generation and that's why。



![](img/8bbb491565a79c7c0c72716d969a2087_121.png)

it's called differential，because there's a difference here and。

lambda this paper is choosing it to be。

![](img/8bbb491565a79c7c0c72716d969a2087_123.png)

0。5，that's just this k parameter and how are，you going to。



![](img/8bbb491565a79c7c0c72716d969a2087_125.png)

find the best ones because remember，evolutionary algorithms。



![](img/8bbb491565a79c7c0c72716d969a2087_127.png)

is a combination of random，search and selection so we have to，select among them。



![](img/8bbb491565a79c7c0c72716d969a2087_129.png)

what is the criteria to select the best，candidates。



![](img/8bbb491565a79c7c0c72716d969a2087_131.png)

you look at the fitness function and the，fitness function is coming from。



![](img/8bbb491565a79c7c0c72716d969a2087_133.png)

the probability that the label，f of。

![](img/8bbb491565a79c7c0c72716d969a2087_135.png)

adv and we want to maximize that if，that's a targeted attack。



![](img/8bbb491565a79c7c0c72716d969a2087_137.png)

if it's untargeted you just want to，minimize。

![](img/8bbb491565a79c7c0c72716d969a2087_139.png)

f of t f of the true class so for，c part 10 we are gonna have a targeted，attack。



![](img/8bbb491565a79c7c0c72716d969a2087_141.png)

and then we are going to increase the，probability of the target，for imagenet we are going to do an。



![](img/8bbb491565a79c7c0c72716d969a2087_143.png)

untargeted attack，so we are going to minimize the，probability of the true class。



![](img/8bbb491565a79c7c0c72716d969a2087_145.png)

so that's exactly what i mentioned there，for c part。



![](img/8bbb491565a79c7c0c72716d969a2087_147.png)

10 if your fitness function takes a，value of，bigger than 90 you're gonna stop。



![](img/8bbb491565a79c7c0c72716d969a2087_149.png)

and that's going to be a targeted attack，because you're maximizing the，probability of the target。

and for fitness function you're，minimizing so whenever，you're minimizing you want to have a。

threshold if you're below that threshold，you're going to stop the optimization。

and that's a non-targeted，attack and we are going to do it for 100，iterations。

any questions i have sort of a little，question uh，just about this this normal distribution。

they're using for the red green and blue，um i don't know if they're，parameterizing by a。

standard deviation or variants but that，seems like a just a very。



![](img/8bbb491565a79c7c0c72716d969a2087_151.png)

very strange gaussian um，because it's so flat with such a high，variance。

then why not just do like another，uniform distribution or something，i guess you could but that's why。

taking a look at the data matters if you，do some exploratory data analysis。

then you might come up with the correct，distribution，or at least a good approximation to the。

true distribution，okay because yeah i guess，then you can take a look at the mean and，the variance。

of the pixels in your data set and you，can use that to better inform。

your initial prior but this is already，going，it's already doing good enough any other，questions。

so there is a question from kevin isn't，that calcium，also take on values outside。

of the domain of a red green blue pixel，yes so there is a chance that it might，take a value，below 1。

and above 256 so that would happen，so you can have it truncated normal so，you can try and take it。

does it answer your question kevin no，it's not，truly normal and it doesn't really，matter because。

all you need to have is some random，initial guess，and then things are going to change。

according to our mutation here，and there is also a chance that when you。

difference there is a chance that your，values are not going to end up being，integers。

especially x and y but then you can also，truncate them，you can make them an integer take either。

the floor or the ceiling and，turn that into an integer so does that，answer all your questions。

are there any more questions the idea is，that that's a complicated。

optimization problem and there was no，other choice，other than evolutionary algorithms you。

don't have access to the function you，don't have access to the，gradients etc and that's a black box。

attack and you're only allowed to change，one pixel or a couple of。

pixels one two or three or more so let's，see some results，you can change your pixel and turn the。

cop to a super，you can have a basket make it a paper，towel etc，by changing one pixel here and there。

and on c part 10 your original accuracy，for four types of networks all。

convolution networking network vgg，bvlc i don't know what that is these are，your original accuracy。

gonna，reduce the accuracy you can have，non-targeted attack，it's gonna reduce the accuracy also and。

this is how confident，your attack is and your confidence are，gonna come from here。

and then say how confident are you that，is the super，and the more the higher these values the。

better is your，attack and just to clarify that，non-targeted attack is the black box，attack correct。

no so there is a difference between，targeted non-targeted，white box and black bucket black box。

attack for，targeted you say that yes i know，that the classifier is classifying this，image。

as a ship but i have a target i want the，classifier，to classify this as a car so that's your。

target the car is your target，for instance here frog is your target，you specify your target，image。

as a frog and how do you do that you，increase the probability。

of that image being classified as a frac，so that's what this adb means okay yeah，thank you。

non-targeted means you don't have any，target you just want the classifier to。

classify this something other than the，horse，so any class other than the course if，you manage to。

fool your network in that way then，you're gonna be happy，it doesn't have to be a frog what does。

it mean then you have to minimize，horse，once you minimize that then it's going。

to make a mistake by black box，i mean you don't have access to the，network structure yeah。

and i understand now thank you yeah any，other question，and the other observation is definitely。

if you increase the number of pixels，that you're allowed to change you're。

going to have a more effective，attack these are the success rate for，targeted and non-targeted。

and that's a dog and you can，have targets to be all the other nine。

cases and you're gonna be successful by，changing only one pixel。

you're gonna take a dog to be classified，as an airplane a cat or a horse。

etc any questions about robustness in，general，because i'm going to change topics for。

this particular slide，i was wondering how increasing the，resolution of。

the or the image to be classified，could decrease the effectiveness of this，attack。

that's a very good question and the，paper actually studies that。

there is a difference between c part and，an image now an image that，changing one pixel is probably。

not as effective as changing one pixel，in c part 10。that makes sense because you have more。

pixels this one is，32 times 32 this one is 227 times，227 oh yeah that's a great question and。

you're right，and in the paper they actually show that，it's less effective。

but still it's impressive that by，changing one pixel you can fool a。

