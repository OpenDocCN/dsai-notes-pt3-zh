# P17：L17- 3D计算机视觉 - ShowMeAI - BV13P4y1t7gM

so welcome back to lecture 17 that's a，so welcome back to lecture 17 that's a。

prime number it's very exciting and，today's lecture we're gonna talk about。

3d vision so then the last two lectures，we had really done this kind of world。

world whirlwind tour of a bunch of，different tasks in computer vision where。

we wanted to not only identify objects，and images but really localize what。

parts of images correspond into the，different objects that we recognized so。

we talked about this wide array of，different types of tasks and computer。

vision including semantic segmentation，object detection instant segmentation。

and we talked about others like key，point estimation that are there also not。

on the slide but the whole the the last，two lectures basically have been a。

whirlwind tour of different ways that，you can predict the 3d the the，two-dimensional shape or the。

two-dimensional structure of objects，that appear in images and these have a。

lot of really useful real-world，applications so these are types of。

computer vision tasks that actually get，used a lot in practice out there in the。

world but it so happens that the world，we live in is actually not。

two-dimensional right the world that we，live in is actually free dimensional so。

then there's a whole separate research，area which is how can we add this third。

dimension to this third spatial，dimension to our neural network models。

and now build neural network models that，can not just operate on two-dimensional。

data but somehow push into this third，dimension and understand the 3d。

structure of the world and the 3d，structure of different types of data and。

that's going to be the topic of today's，lecture is how can we add three。

dimensional information into different，types of neural network models so we're。

gonna focus on two categories of 3d，problems today one is the task of。

predicting 3d shapes from single images，so here we're going to want to input。

some single RGB image on the left and，then output some some representation of。

the 3d shape of the objects in that，image and the second and and here for。

this task of 3d shape prediction we're，using the 3d data as the output of the。

neural network model so then the input，is still going to be our favorite two。

dimensional image representations that，we've used many many times before but。

now the output of the model will somehow，be a three dimensional representation of。

the objects and but but sometimes you，might not want to produce three。

dimensional outputs from your neural，neural network models instead it's also。

it's also a common thing that you might，want to ingest or input three。

dimensional information into your neural，network models and then perform maybe。

some classification decision or some，segmentation decision based on a 3d。

input data so that's what we're gonna，focus on today is sort of how can we。

structure our neural networks to both，predict different sorts of 3d。

information as well as ingest different，sorts of 3d information and I should and。

and and for both of these problems we'll，focus on the fully supervised task so。

for all the tasks we talked about today，we'll assume that we have access to a。

training set that has I'll maybe the，input image and the corresponding 3d。

shape or the 3d shape and the，corresponding semantic label that we。

want to predict so everything today will，make this a fully supervised assumption。

that we have access to this full，training set to supervise everything you。

want to predict but I should point out，that that this is just really scratching。

the surface of what types of topics are，possible in 3d computer vision and it's。

really sort of impossible to do proper，justice to this topic in just a single。

lecture so instead we'll have to just，point out on one slide that there's a。

lot more to 3d computer vision than just，these sort of shape prediction or shape。

classification types of problems and，what's really interesting about maybe 3d。

computer vision is that this is one area，where there's actually a lot of non deep。

learning methods that are still alive，and well and still very important to。

know about and that's because there's a，lot of there's a lot of geometry。

involved in actually the 3d structure of，objects and 3d structure of the world so。

there's a whole different there's a，whole large set of types of tasks that。

people work on in 3d computer vision，that we just don't have time to talk。

about today but to give you a sense one，thing you might want to do is maybe like。

this this this concept of structure for，motion where you maybe want to input a。

video sequence that's a sequence of 2d，image frames and now you want to predict。

or reconstruct the the trajectory of the，camera through the 3d world through the。

video sequence and there's a whole，that's just maybe one flavor of a type。

of problem that you can do in computing，computer vision that's sort of just。

beyond the scope of what we have time to，talk about in a single lecture so I just。

want to give you that context that，there's a lot more to the world of 3d。

vision then we're going to talk about，today but today we'll just focus。

these these two particular problems of，supervised sheet prediction and then。

maybe super bad shape classification so，in any kind of questions on this sort of。

preamble about 3d computer vision before，we really dive into these different。

types of models alright so then if we're，going to talk about 3d shape prediction。

and 3d shape classification then I've，been a little bit cagey here with this。

term 3d shape so here that that's kind，of a loose ill-defined term but in。

practice there's a lot of different，types of representations that people use。

to model 3d shapes and 3d information so，we're going to structure this by talking。

about these different five different，types of 3d shape representations that。

people work with often in practice that，all have their different sort of pros。

and cons and we'll see how each of these，five different types of 3d shape。

representations can be processed or，predicted with neural network models so。

and then if these are cartoon graphics，of these three shape representations or。

maybe not super clear by the out at the，outset hopefully by the end you'll。

understand that each of these five these，five little cartoon pictures that we've。

shown here are all sort of meant to，represent different representations of。

the same underlying 3d shape so the，first representation to talk about is。

that of the depth map so a depth map is，conceptually a very simple 3d shape。

representation and basically what a，depth map does is it assigns to each。

pixel in an input image it assigns the，distance from the camera to that pixel。

right because each pixel in the image，corresponds to some object out there in。

the real world and now a depth map tells，us for each pixel in the image what is。

the distance like in meters between the，camera and that that position out there。

in the real world that the pixel is，trying to represent and then this is。

some than a traditional RGB image that，we're used to working with would be。

maybe a height by width grid of pixel，values where each pixel value gives us。

the color of a pixel and now the depth，map is just a similar 2d grid where now。

the value of the pixel is not the color，it's just this depth in meters of that。

pixel and then it's very common to，actually combine together an RGB image。

and then add on this fourth channel of，information giving the depth information。

and that would be an RGB image，and sometimes these RGB images are，actually called to play 5d images。

because they're not like real full 3d，because one of the one of the cons one。

of the trade offs of these def image is，is that they can't they can't capture。

the structure of occluded objects right，because say that in this maybe this。

example here there's actually part of，the bookcase that's occluded by the。

couch in the top image but now the depth，map doesn't have any 3d representation。

for the portion of the bookcase which is，behind the couch instead this this RGB D。

or depth map representation only is able，to represent the visible portions of the。

image so for that reason we sometimes，think of it as a slightly less powerful。

powerful or less general 3d，representation which we encapsulate by。

just calling it maybe two point five D，to mean that it's not fully 3d but one。

reason why this depth map type of data，is very important is that is that we can。

actually capture depth map data with，various types of raw 3d sensors so。

something like the Microsoft Kinect that，you may have been familiar with actually。

uses a form of structured light to，estimate these these depth images。

directly using some some fancy sensor，tricks or if you look at something like。

the the face ID sensor on an iPhone then，that's also capturing some kind of depth。

image because it's projecting out these，infrared dots and then able to use that。

that information to estimate the depth，at each pixel of the image that it。

captures so these definite information，these understanding how to work with。

these depth map images is super，important because this is actually a。

type of 3d data that we can just capture，from the world using raw using actual。

sensors and then it turns out actually，trying to then one one task that you。

might want to try to do is to try to，input a vanilla RGB image and then given。

an RGB image try to predict this depth，channel that is try to predict for every。

pixel in the input image what is this，distance from the pixel to the object。

out in the world but that but that pixel，is covering and it turns out that we can。

actually that this is the architecture，that we could use to predict this is。

actually something that we saw a lot in，last lecture and that's this idea of a。

fully convolutional network so if you，recall in the last lecture when we。

talked about this this task of semantic，segmentation there we wanted to predict，for every pix。

in the input image what was the the，semantic category label of the pixel and。

there we saw that using some kind of，fully convolutional network with some。

pattern of down sampling and up sampling，inside the network was a useful neural。

network architecture that let us make，one prediction per pixel and we can。

reuse that exact same type of，architecture now for predicting these。

depth maps so then in order to maybe，predict the def map from a single image。

you would input your RGB image to some，fully convolutional network the final。

convolutional layer of that network，would have maybe one filter or one。

output channel that where then the，output of that love that one filter。

would these would be interpreted as that，depth that we're trying to predict and。

then we would train this thing using，some kind of loss function that compares。

for every pixel of the predicted depth，and we look at the corresponding pixel。

or the ground truth depth and try to，compare them and then well obviously we。

want our pretty good depth to be the，same as the the ground truth depth or do。

we it turns out that that's actually not，quite possible with with 3d vision and。

the reason is this fundamental problem，that we run into with 3d representations。

which is the problem of scale depth，ambiguity so here，what right we you if you're looking at a。

single image you can't really tell the，difference between a large object that's。

very far away and a close object that's，very close to you so in particular if we。

had this image of a cat and if you were，looking at a cat that was like right in。

front of your eye versus a cat that was，twice as large and two times as far away。

from you they would look exactly the，same they would project the exact same。

image onto the retina onto your onto，your retina and your eye or onto the the。

sensor in any kind of digital camera and，for that reason that that this the。

overall the absolute scale and the，absolute depth is actually ambiguous。

from a single 2d image so as a result of，this scaled so whenever you're working。

with any kind of 3d representation or，3ds prediction problem it's always。

important to think about this this，potential problem of scale depth and big。

Uwe T and then it's often the case that，we need to actually change something in。

the structure of our neural network，model in order to deal with this problem。

of scale depth contiguity so I don't I，don't want to walk through the math here。

in input in concrete detail but it turns，out that there's a very clever。

loss function that we can use for this，depth prediction problem that is。

actually scale invariant and what I mean，by that is that suppose that our neural。

network predicted a ground truth depth，that was correct up to some constant。

scaling factor of the true depth right，like maybe our network just predicted。

the depth all of the predicted depths，from our network were like one half of。

what they were supposed to be from the，drug from the ground truth well then。

this scale invariant loss function would，still assign zero loss to that situation。

the only thing that it cares about is，somehow that there's the way that you'll。

get zero loss with this with this loss，function is that if there exists a。

scalar that you can multiply your，predictions by and then match the ground。

treat perfectly then in that case you，get zero loss but this log function does。

not actually penalize a global global，office of a global multiplicative offset。

in scale and there's some clever math，behind this loss function and see。

exactly why that works and how that，works out I suggest you look at look。

into this 2014 NURBS paper that's，referenced on the slide and that will。

walk you through the mathematical，details of exactly how this scale，variance is achieved with this。

particular mathematical form so then，there's actually another very related 3d。

shape representation that is very，similar in spirit to this idea of RGB D。

or def images and that's the idea of a，surface normal map or surface normal。

image and here I'm just like with a，depth image what we wanted to do is。

assign to each pixel the distance in，meters between the pixel and the object。

out there in the world what a surface，normal what a surface normal。

representation will do is assign to each，pixel we want to know what is the。

orientation of the surface of that，object out there in the world so then。

for every pixel that we would as we，would have a some unit vector if for。

each pixel that tells us the orientation，of the surface for the pics for that for。

the object that that pixel is showing，and it's typical to represent or draw。

these 3d normal map of these normal map，images using RGB colors so here these。

are for this particular example this，image on the right is showing a normal。

map version of this image on the left so，here blue represents may be pointed up。

so you can see that the floor and the，top of the bed is all kind of colored。

to mean that that's but those normal，vectors are pointing up red is kind of。

pointing kind of pointing this way to，say that maybe the side of the bed is。

kind of pointing this way and then green，is pointing the other way so if you look。

at the cabinet's you can see that，they're colored green and the exact。

mixture between RGB it tells us the，exact orientation of the of the surface。

normal at every point in the image and，now we can imagine predicting these。

surface normals using a very similar，technique right we can just take our RGB。

image run it through a fully，convolutional net work and now predict。

at the output of three channel image，that tells us what is this what is this。

three dimensional vector at every，position in the input image and now the。

loss function here we want to compare，the angles between two vectors so we can。

use a dot a per pixel dot product，normalized by the by the by the norms of。

the vectors in order to have our loss，function these it be something like the。

related to the angle of between the，vectors in that our network is。

predicting and that is a present in the，ground truth so this is so it actually。

turns out that you can actually train，one joint network that does both。

semantic segmentation and surface normal，estimation and depth estimation and you。

can actually train one network that will，input a single RGB image and then。

predict for you all of those things all，in a single forward pass so that's。

that's kind of one so that's a fairly，conceptually simple or 2d representation。

but I think it's actually pretty useful，in practice for a lot of different。

applications because once you have a，depth map and once you have a surface。

normal that actually gives you quite a，lot of information about the 3d。

structure of the image that you're，looking at but of course the the。

drawback of these surface normal or a，three-point or of these def map。

representations is that they can't，represent occluded parts of the image so。

if we want to have a more complete 3d，representation of our 3d scenes we need。

to move on and consider other types of，3d shape 3d shape representations so。

then the next 3d shape representation，that we can think about is a voxel grid。

now a voxel grid is conceptually very，very simple great so what is going on in。

a box of grid is we're just going to，represent the 3d world as some 3d grid。

and within each cell of the grid we want，to have have it，turned on or off to say whether or not。

that that cell in the grid is occupied，so this is basically like a Minecraft。

representation of the world right that，because you know the whole world we're。

assuming the world is built from blocks，and then there's some so there's some。

identifiers or some some property at，each grid cell in the world and now this。

these voxel representations are，conceptually pretty easy to think about。

and pretty straightforward to think，about and it's sort of basically like。

the mass representation that we use in，NASCAR CNN for representing foreground。

or background of an object except，extended into 3d so you can imagine that。

all of the similar machinery that we use，for processing may be two-dimensional。

occupancy grids in NASCAR CNN or for，segmentation we can use similar sorts of。

machinery to represent these and 3d，voxel occupancy grids but now a big。

problem with voxel representations is，that you actually need to use a very。

high box'll resolution if you're going，to capture the very fine details of the。

objects in the scene so as an example if，you look at this chair there's actually。

a lot of sort of very fine detail over，the part of the chair where you might。

put your hand there's actually a very，subtle curvature there that looks like。

to be very comfortable to rest your hand，on but if you look at the box or。

representation on the right you can see，that it's very blocky and a lot of this。

really fine-grained geometry of the，chair has been lost as we move from sort。

of a raw like the actual input image to，some Vox live representation of the。

scene and to actually recover these very，fine details we would need to use a very。

very high box'll resolution and that，could be computationally expensive but。

it turns out that actually processing，voxel represent halo processing voxel。

grids is fairly conceptually simple，right so suppose that we were given a。

voxel grid as input like we received as，input this voxel representation of the。

chair on the right and now our task was，to classify these different voxel grids。

and say is this grid the shape of a，chair or is an airplane or is a couch or。

something else well if we wanted to do，this kind of classification of a voxel。

grid we can use a very familiar sort of，3d convolutional network neural network。

architecture the difference is that now，we need to use 3d convolution or。

three-dimensional convolution as our，basic building block so here the input。

to those two such a 3d convolutional，neural network would be on this。

raw box'll this raw voxel model this raw，voxel grid telling us for every point in。

3d space is that voxel occupy or not，occupied and now every layer of the。

model would be some 3d convolution，operation where now our convolutional。

kernel is some little three-dimensional，cube that we're going to slide over。

every point in 3d space over the，previous feature map compute inner。

products and that will give us a scalar，output at the next layer so now you can。

imagine building up three-dimensional，convolutional neural networks that are。

very similar in structure to the，familiar 2d convolutional neural。

networks that we've seen many many times，before so you can build up maybe on。

several layers of 3d convolution，followed by maybe a couple fully。

connected layers or some kind of global，global average pooling layer and then。

finally go to some classification layer，and basically all of the types of neural。

network architectures that we're，familiar with working with for。

two-dimensional images you can imagine，porting them over into three into these，way。

oh yeah so to explain the input，dimension a little bit so here the the。

one is the feature that the so we have，now at every stage of the network it's a。

four dimensional tensor so we have three，spatial dimensions and one channel or。

feature dimension so for the for the，input to the network it's a voxel grid。

so there's three spatial dimensions of，30 by 30 by 30 and then for the input to。

the network we have one feature at every，point in that voxel grid which is。

whether or not that voxel is occupied，but now as we move along the，convolutional mountain as we move。

through the 3d ComNet then we will still，have three spatial layer three spatial。

dimensions at each edge at each layer，but now we might have a whole feature。

vector at every point in that 3d grid，which gives us a 4d tensor so if you。

look at the second layer in this network，the it's a it's a 48 by 13 by 13 by 13，spatial grid。

well the 13 by 13 by 13 is the is a，spatial size and that within every point。

of that grid we have a 48 dimensional，vector which means that this this layer。

was produced using a 3d convolution，operator that had 48 filters because。

each one of our three dimensional，filters is now going to give rise to a。

full cube with one scalar value at every，point and the，and then we need to stack up those cubes。

to give us a four dimensional tensor is，that does that clarify the the。

dimensions a little bit of these，networks yeah yeah so then the input。

would be some binary tensor it just says，whether every point in space is occupied。

or not occupied although maybe if you，had some other type of information like。

maybe if you were literally trying to，work on Minecraft then you might。

actually have like the block type at，every at every position in space which。

you might represent as like an integer，or something like that or a some one hot。

representation but for the if your，fridge was representing raw 3d shapes。

then the input you would usually be some，to some binary representation just to。

say whether or not each point in space，is occupied oh yeah but the kernel does。

not need to be binary so typically on，only the input that this network would。

be binary and everything else would all，be real value it just like it has been。

in all the applications we've seen so，far so the kernels would be real valued。

and each of these intermediate eacher，layers would be real valued it's just。

the input is going to be forced to be a，binary in this case okay so then the。

next task you might want to do with，voxels is actually predict voxels from。

an input image so in this previous case，we're sort of assuming we receive voxels。

as input and then we want to classify，them or make some some prediction on。

input boxes a related task is say we，receive an input image and now we want。

to predict a voxel grid that gives the，3d shape of that input image so now the。

input on the left is our is our familiar，three dimensional tensor giving two。

spatial dimensions and one RGB Channel，dimension and now all the way out at the。

other side on the right we need to，somehow end up with a 4 dimensional。

tensor that has three spatial dimensions，and one channel dimension giving us the。

occupancy probability at every point in，the voxel grid so then we need some。

architecture that lets us sort of move，add an extra spatial dimension somewhere。

inside the model and then assuming we，had some way to convert the spatial。

dimensions in the right way then the，output we could imagine training this。

thing with some cross entropy loss，because ultimately maybe we predict a。

occupancy probability or occupancy score，for every point in the voxel grid and。

then we compare that with our binary，occupancies that we have in our graph。

truth and you could imagine training，this thing with a softmax or a logistic。

regression type of type of binary of，classification loss but now as for the。

network architecture one fairly common，way to predict voxel grids would be to。

actually bridge the gap between 2d，between 3-d and 4-d tensors using a。

fully connected layer so what we can，imagine is processing our input image。

with a familiar 2-dimensional CNN and，then at the end of a 2-dimensional CNN。

we would have a three dimensional tensor，that has two spatial dimensions by H and。

W and one channel or feature dimension C，and then you could imagine flattening。

this this this three dimensional tensor，into a into a big vector and then having。

a couple fully connected layers and then，from the output of the fully connected。

layers we could sort of reshape them，back into a four dimensional tensor so。

then this then we could sort of use，these these fully connected layers in。

the middle to sort of add an extra，spatial dimension between our。

three-dimensional input and the four，dimensional output that we want to。

predict and then once we've got this，initial three dimensional output then。

you can imagine doing some，three-dimensional convolution with sort。

of three dimensional spatial up sampling，on the right-hand side of the figure in。

order to go from this this 3d，representation with small spatial，dimensions up to a 3d representation。

with the large number of spatial，dimensions that we finally want to。

predict at the output of the network and，you can imagine that this that now this。

the second half of the network would，have sort of 3d analogs of all the。

different uncool Anor or up sampling，operations that we talked about in last。

lecture in the context of semantic，segmentation so this is a fairly，straightforward way to deal with。

predicting 3d voxel information but it，turns out that this is this this type of。

architecture is very computationally，expensive because actually these 3d。

convolutions any kind of 3d convolution，operation is going to be extremely。

extremely computationally expensive，right because um the number of receptive。

fields is now going to scale cubically，with the with the spatial size of the of。

the feature map of the feature grid，which means that the the computational。

cost of performing 3d convolutions is，very very high compared to the cost of。

doing 2d convolutions so as a result，sometimes people try to put，box of 3d voxel grids using only 2d。

convolutions and this is sometimes，called a voxel tube representation um。

and here the idea is that our input，image is going to be a three dimensional。

tensor with three channel dimensions and，two spatial dimensions and then we're。

going to go through some two dimensional，convolutional Network where at every。

point in our two-dimensional，convolutional Network we will still have。

two spatial dimensions and to end one，channel dimension but now the very last。

layer of our of our network will be very，special and say that we want to predict，a voxel。

output voxel grid of size V cross V，cross V then for the last layer in our。

2d CNN we will arrange the spatial，convolutions such that the 2d spatial。

size of the final layer of our of our 2d，CN n will be V cross V and then we the。

the number of output channels or output，filters of the final tunic of the final。

2d convolution will have will be the，filters or V channels of the last two。

deconvolution and now at the very end of，the network then we will play a bit of a。

trick where we will in where the output，of the convolution will have sort of。

literally had two spatial dimensions and，one channel dimension but when computing。

the loss we will interpret that laughs，that that channel dimension as actually。

the depth dimension of the of the output，tensor and if you by kind of using this。

this this voxel to representation it，lets us predict voxel representations。

using only 2d convolutions which is much，more computationally efficient and this。

is called a voxel to representation，because it has this interpretation that。

we're doing to deconvolution that looks，at the input image and then for the。

final layer of the convolution it's sort，of predicting a tube along the channel。

dimension that gives us a whole a whole，a whole tube of voxel probabilities or。

voxel outputs as the channel outputs of，our final 2d convolutional layer so is。

that maybe this these these two，different approaches of 3d convolution。

and voxel to representations clearer for，predicting voxel outputs yeah that's a。

good question so the question is do we，sacrifice anything when we move from。

this from this 3d convolution model to，this box will to，what representation model and what we。

lose is actually translational，invariance in the Z dimension right so。

one proper one one nice property of，convolutions is that they don't sort of。

care about the position in space where，the inputs are located right so suppose。

that we were trying to do two to，deconvolution and recognize a cat then。

recognizing a cap in the upper left hand，at a corner and lurking as a cat in the。

lower right hand corner should be，exactly the same because if we're。

sliding two-dimensional filters over the，image then when our whatever our cap。

filters can intersect the cat then，they'll fire cat features but now if。

we're 3d CNN we would also get sort of，three dimensional spatial invariants but。

if there was some particular 3d，structure in the input data that could。

occur at any point in 3d space then we，could imagine having a 3d kernel but is。

now invariant to three arbitrary 3d，translations of the input but when，you're using a box with two。

representation that's not the case，because now suppose that you wanted。

different versions we wanted to be able，to represent somehow in the model。

different shifts over in the Z dimension，then you would actually need to learn。

separate convolutional 2-d convolutional，filters to represent each possible。

offset in the Z dimension so basically I，think what you're giving up with this。

voxel to representation is um，translational invariance or，translational translational acrobatics。

in the Z direction but you still would，good translational equivariance in the。

XY plane so I think that's what you're，giving up here okay but then a big。

problem with voxel representations is，that they take a lot of memory so we。

already noted that in or if we wanted to，represent the very fine-grained details。

or fine-grained fine grain structure of，objects then we would need to use a very。

high resolution voxel grids and it turns，out very high resolution voxel grids。

take a very lot of memory and GPUs don't，actually have enough memory to work with。

very high resolution voxel grids so as，an example suppose we wanted to。

represent a voxel grid that was 1024 by，1024 by 1024 and then because this is a。

neural network within each cell of the，voxel grid we wants to have a 32-bit。

floating-point number that represents，the the the occupancy probability or the。

occupancy score for every point in this，high dimensional voxel grid well then。

I'm just restoring this this 3/2，ten sir would take almost four gigabytes。

of memory and that's not counting all of，the convolutional layers that we would。

need to use in order to actually predict，this high-resolution voxel grid so as a。

result of this very high memory，requirements of voxel grid's on people。

just don't just dismiss not possible or，not feasible to use sort of naive voxel。

grids at very high spatial resolutions，but there are some tricks that people。

sometimes play in order to scale voxel，representations up to higher spatial。

resolutions so one trick is to sort of，use a multiverse a kind of multi。

resolution voxel grid and one way to do，this is this idea called an ox tree so I。

don't really want to go into too much，detail here but the idea is that we're。

going to kind of represent a voxel grid，where some kind of multiple resolutions。

so we will be able to capture the course，through facial structure of the object。

using some low resolution voxel grid，maybe a thirty-two cubed and then we can。

represent maybe the we can fill in the，fine details by turning on a sparse。

subset of numbers of box'll cells at，higher spatial resolutions like 64 cubed。

or 128 cubed and now implementing these，things gets quite tricky because you。

need to deal with kind of mixing，multiple resolutions and now using。

sparse representations of these voxel，grids so in the implementation of these。

types of structures is a bit non-trivial，but if you can manage that。

implementation hurdle then you can，actually excuse this kind of tricks to。

scale box or representations of the，fairly high spatial resolutions another。

trick that I thought was kind of cute is，this idea of a nested shape layer which。

is kind of like these these nested，matroyshka Russia and dolls so the idea。

is that rather than representing this，like full 3d shape as a dense voxel grid。

instead we kind of are gonna represent，the shape of the object from the。

inside-out so we're going to have some，kind of like coarse outer layer and then。

some negative minus some negative voxels，that are inside might plus some more。

positive box holes minus another layer，of negative box holes and then we don't。

actually have to and we can represent，all of these things sparsely we don't。

have to represent the full voxel grid in，a dense way we just kind of represent it。

as this sum and difference of a couple，different a sparse voxel layers so this。

is another way that people are able to，scale box or representations to。

higher spatial resolutions okay but then，so that's kind of the voxel grid。

representation and that's that's，actually one that gets used quite a lot。

in practice now another kind of really，interesting 3d shape representation is。

that up an implicit surface so with the，idea with an implicit surface is that we。

want to represent our 3d shape as a，function and what we're going to do is。

learn some function that inputs the，court some coordinate in 3d space and。

what it's going to output is the，probability that that position that。

arbitrary through position in 3d space，is either occupied or not occupied by。

the object and then rat so then we，rather than kind of trying to fill so。

with a voxel grid what we're kind of，doing is sampling such a function at。

some finite set of points in 3d space，and then storing those samples to the。

function in some explicit grid，representation but now with an implicit。

function we're kind of just using some，mathematical function itself to。

represent these these 3d shapes，implicitly so then we could then sample。

from this function at arbitrary put，points in 3d space and it should be able。

to tell us whether or not arbitrary，positions in 3d space are either inside。

or outside the object and then the，actual of the exterior surface of that。

object would be represented as the level，set of points in 3d space where that。

occupancy probability is equal to 1/2，and then we can kind of represent this。

representation visually on the left here，where now this implicit function the。

color of each position in space sort of，gives on what the value of this implicit。

function would be if we were to have，evaluated it at that point in space。

where blue were corresponds to values，very close to 1 and red corresponds to。

value is very close to zero and then，this white region in the middle is where。

the we actually have this level set of，1/2 that represents the actual surface。

of the 3d shape you'll also sometimes，see this called a signed distance。

function where the idea is that we this，dysfunction is giving us Euclidean。

distance from the point in 3d space to，to the surface where that distance is。

maybe positive or negative depending on，whether the point is inside or outside。

the object but these are basically sort，of equivalent representations。

just a question of whether we whether，the output of this function is between，zero and one。

or between minus infinity and infinity，but otherwise there they're sort of。

equivalent and now of course whenever，you see a very complicated function that。

you might want to represent or learn，what we're going to do is just like。

learn this function as a neural network，so then what we're going to do is learn。

a neural network that inputs a 3d，coordinate and then outputs a，probability to say whether that 3d。

coordinate is actually inside or outside，the shape and then you can imagine。

training such a function by having some，some data some data set of samples from。

your 3d shape and then training it to，classify these coordinates as being。

either inside or outside the 3d shape，and now if we actually wanted to extract。

some explicit shape representation from，this learned function then what we can。

imagine doing is kind of sampling that，learned function at some grid of points。

in space and then the function would，tell us whether each one was inside or。

outside and then for the bount then we，could imagine going back and resampling。

the function now at new points that are，kind of on the boundary of the inside or。

outside then you can imagine sort of，going back and iteratively resampling。

new points from this learn implicit，function toward actually extract some。

explicit representation of the boundary，of the shape that the implicit function。

represents but of course um this is，actually this actually has a lot of sort。

of hairy implementation details as well，as you might imagine and the exact。

procedure of how you hook up these，architectures and how you connect image。

information into these to these SDF，neural network functions or how you。

actually what is the exact algorithm for，extracting a 3d shape from a trained SDF。

these are all sort of complicated，details that I don't really want to get。

into I just thought that this is a kind，of interesting way to represent 3d。

shapes because we're sort of，representing the shape implicitly as the。

values computed by a learned function，whereas most of the other。

representations that we use are kind of，explicitly representing the shape of the。

object using some some some primitives，in 3d space so I think this is an。

interesting 3d shape representation to，be aware of okay so then the the next 3d。

shape representation to think about is，the the point cloud representation。

so here a point cloud representation is，basically saying we're going to。

represent a 3d shape as a set of points，in 3d space where the set of points in。

3d space are going to somehow cover the，surface of that 3d shape that we want to。

represent so for example if we wanted to，represent this this airplane here as a。

plainclothes n tation then we might，represent it as the set of points in 3d。

space that all kind of were many many，points on the surface of the airplane。

representation so one sort of nice，property about point cloud。

representations is that they're somehow，more adaptive compared to voxel grid。

representations so we saw that if we，wanted to use a voxel grid to represent。

3d shapes of with very fine details and，with high fidelity then you would need。

to use a very very high boxful，resolution but now with a 3d point cloud。

representation you can imagine that we，can represent fine details of 3d shapes。

by varying the density of the point，cloud at different points in space so。

for a point cloud representation like，for the the four parts of the object。

that require very fine detail like maybe，the tips of the wings or the the the。

tail fins of this airplane you can，imagine putting more points there to。

just represent those fine details，whereas other parts of the object like。

maybe the fuselage of the plane that，don't have as much fine structure you。

can imagine having maybe allocating，fewer points on that part of the object。

to represent it with with less fidelity，so that means that even if you have a。

fixed finite number of points to，allocate or your your 3d shapes then you。

can position those those points out in，space in different ways to more flexibly。

or adaptively represent areas of high，and low detail of the shapes you want to。

represent but sort of one one downside，with 3d point cloud representations is。

that you need to do some kind of，post-processing if you actually want to。

extract out some actual 3d shape to，visualize and that's kind of clear even。

from this visualization that we're，showing on the screen because um，mathematically this point cloud。

representation each of our points are，infinitesimally small but there's no way。

that we can actually visualize these，infant pestilent infant testimony small。

points so even just to visualize a point，cloud representation we can。

I need to inflate the points to some，finite ball size and then render these。

balls so that's what we're showing on，the screen here um so that means that。

this this raw point cloud representation，is something that we can't really work。

with for a lot of applications in order，to actually represent any kind of dance。

to your application we might need to do，some post-processing on the point cloud。

to convert it into some other format or，some other representation for us to。

render or visualize or work with but，that said this point code representation。

is still a very useful thing to work，with in neural networks and this is。

actually a very common representation，that's used for example in maybe。

self-driving car applications so for a，self-driving car they actually have this。

aw this spinning lidar sensor that's uh，that's on the roof of the car and then。

it actually collects this point cloud，representation of the environment around。

it so then for any kind of self-driving，car application you need like kind of。

the raw data that the system is，ingesting is some point cloud，representation of the world around it。

and that's maybe and then what was then，it's sort of important that we are able。

to build neural network models that can，ingest these raw Planck load。

representations and then make some some，decision based on raw point cloud inputs。

so then one kind of neural network，architecture that people often use for。

ingesting point cloud inputs is this，so-called point net architecture so here。

this is kind of a simplified version but，what we want to do is input a set of。

three points so that one so then our，input is going to be a point cloud with。

P points and each of those points will，have an XYZ position in 3d space and now。

we want to input this set of points as，input to the network and then we maybe。

want to make some classification or，regression decision based on the this。

point cloud input so maybe one thing we，might want to do is classify what is the。

the category of the shape that is being，represented by this input point cloud so。

then once then we need some kind of，neural network architecture that can。

input a set of points and then output，some classification score but what's。

interesting here is that we don't want，the order of the points in the cloud to。

matter right this this point cloud is，really a set of 3d points and then the。

order that the points are represented in，memory actually should not matter so，this。

like the transformer that we talked，about several lectures ago that we want。

the operations performed by our neural，network to be invariant or equivariance。

to the order of the points that are，represented so then one way that we can。

do this is this this point net，architecture so here what we're going to。

do is train a little Eva's have a little，MLP a multi-layer perceptron a fully。

connected neural network that is going，to input the 3-dimensional coordinate。

and then go through several fully，connected layers and then finally output。

a feature of dimension D and then we can，run this of this fully connected network。

independently on each point in the cloud，and that will then give us some feature。

vector for every point in the cloud and，then and then if and then this this then。

if we had point clouds with varying，numbers of inputs and we could imagine。

just running this NLP independently on，point clouds with arbitrary numbers of。

points and then once we've used this，display connected network to extract a。

feature vector for every point in the，cloud then we can use a Mac spooling。

operation to do some max pooling over，all of the points in the cloud and that。

will collapse these these people in the，cloud down to a single feature dimension。

a feature vector of dimension D and then，this single feature vector of dimension。

D we could then imagine going back to，using it to some other fully connected。

network to eventually output our final，class scores or class probabilities and。

because this max pulling up because the，max function doesn't care what order its。

inputs were in then this architecture，doesn't care what order the points were。

represented on the input tensor so that，means that this this this architecture。

is really operating on sets of input，points um so it's quite appropriate for。

dealing with these point cloud，representations and this is actually um。

maybe a quite a simplified version of a，point out architecture so in practice。

you might imagine vert so this is kind，of doing one layer of global aggregation。

across all the points but in more，complicated versions of this，architecture what you could imagine。

doing is taking this pooled vector and，then concatenate it again to all of the。

vectors of the points in the cloud and，then doing more independent MLPs and。

then more pooling and kind of iterating，this procedure of independent operation。

on the feature vectors of the points，pooling across the points and then，concatenate。

pulled vector back back to the feature，vectors of the points and that you could。

imagine sort of more complicated，variants of this type of architecture。

but this is sort of very commonly used，for processing point cloud inputs now。

another thing we might want to do is，generate point cloud outputs so here。

what we might want to do is input an RGB，image and then output a point cloud。

representing the 3d 3d shape of the of，the point the 3d shape of the object so。

then what we could imagine doing is kind，of hooking up some three to some neural。

network architecture that is now，spitting out some 3d point clouds that。

give the 3d shape and maybe we can skip，over the exact details of this。

architecture because I think the，interesting point about generating point。

clouds is that we need some kind of loss，function that is able to compare our。

predicted the point cloud that our，network predicted and the point cloud。

that we should have predicted and now，this is kind of a new thing that we。

haven't really seen before because we，need to write down a loss function that。

operates on two sets and tells us how，similar is this point cloud does these。

two sets the one that we predicted and，the one that we should have predicted。

and then of course this loss function，needs to be differentiable so we can。

back propagate through it and use it to，train the network，well one function that we often use to。

compare point clouds is called the the，chamfer distance and it has this。

particular mathematical form but I think，it's maybe easier to understand if you。

walk through it visually so here the，idea is that we're going to input on two。

sets of points the the orange points and，the blue points and now the chamfer。

distance should tell us how different，are these two sets of points so there。

are two terms in this loss function so，the first one what we're going to do is。

for each blue point we're going to find，its nearest neighbor orange point and。

then we're going to compute the，Euclidean distance between each blue。

point and its nearest neighbor orange，point and then we're going to sum up。

those those distances across all of the，blue points and that will be this first。

term in the loss function and then the，second term will do something kind of。

equivalent so for each blue point we，will now find sorry for each orange。

point we will now find its nearest，neighbor blue point and then compute。

that distance to its nearest neighbor，and then sum of all of those distances。

and now our chamfered unmeant our final，chamfer loss will then be the sum of。

these two sort of nearest neighbor，matching loss functions and now you can，see that the only。

possible way to get this to drive this，chapter loss to zero is if the two point。

clouds coincide perfectly that is if，every orange point is exactly on top of。

some blue point and vice versa，that's the only way that we can achieve。

a zero loss but of course because of，this nearest neighbor operation the。

order of the two points in the clouds，does not matter so that's exactly so。

then this this chamfer loss function is，somehow is somehow matching the L to。

nearest neighbor distance between two，sets of points in 3d space so then we。

can imagine using this chamfer loss，function to to train our neural network。

that's predicting point clouds so then，we could have the point cloud that's。

predicted by our model and then the the，point cloud from the ground truth data。

set that we should have predicted and，then compute this chamfer distance。

between them and the back propagate，through everything to Train it the。

weights of the network so that gives us，our our point cloud 3d shape。

representation and the final one is the，the mesh representation of 3d triangle。

meshes so here a 3d triangle mesh is，actually a very commonly used。

representation in computer graphics if，you've ever taken like a graphics or a。

rendering rendering class and here what，we're going to do is represent the 3d。

shape as a set of vertices in 3d space，which is basically a point cloud。

representation but now in addition to，this set of points in 3d space we're。

also going to have a set of triangular，faces that are triangles with vertices。

on the point cloud and then this will，give this will basically let represent。

the 3d certain 3d shape of the object，not as a set of points in space but as a。

as a set of triangular faces throughout，interconnected through per distance so。

this is also sort of adaptive because we，can have sort of bigger or smaller。

triangles at different points in the，model and it's also very useful for。

computer graphics because it gives us，this explicit representation of the。

surface of the object and what this，means is that we can also sort of。

interpolate arbitrary data over the，surface of a triangle mesh using。

something like very central coordinate，interpolation but the exact details of。

that don't matter what that means is，that for example if we had maybe if we。

attached data at each vertex like a，color or a normal vector or a texture。

coordinate or some other piece of data，at each vertex then you could sort of。

interpolate those pieces of data over，the triangular faces of the triangle。

mesh so that would sort of ladder，represent this sort of extension of our。

finite samples of data over this entire，3d surface in 3d space and that's for。

example of how we often render 3d，textures in in computer graphics engines。

so for all those reasons I think this，this 3d mesh representation is really。

nice especially as for for graphics II，type applications but actually on。

processing pretty Ramesh's with neural，networks there's kind of a non-trivial。

operation you need to sort of invent a，lot of new structures to process meshes。

with they're all networks so there was a，very nice paper presented by some folks。

at EC that last year in 2018 that have I，think a lot of really cool ideas for。

processing meshes with neural networks，this was called pixel to mesh because。

what they wanted to do was input a，single RGB image on left and then output。

a triangle mesh giving the full 3d shape，of that about object in the image and。

they had maybe three four key ideas for，processing meshes with inside of a。

neural network that I thought were quite，interesting so the first is the idea of。

iterative mesh refinement so ultimately，we want to build a neural network that。

is able to output or emit a triangle，mesh representing a 3d shape but it's。

sort of difficult to invent trade 3d，meshes from scratch in in the。

differentiable way so instead what we're，going to do is sort of input some in。

some initial template mesh to the neural，network and then throughout processing。

of the neural network what it's going to，do is deform that initial template mash。

it to give our final mesh output so then，what we're going to do is sort of input。

to the network this on sphere initial，sphere or initial ellipsoid mesh that。

gives us some initial positions for all，the vertices and some set of triangular。

faces over those vertices and then we're，going to then iteratively refine the。

positions of those vertices so then in，the first stage of processing will。

process that input mesh in some way see，how much does that initial mesh match。

the image and then move the vertices，around in 3d space to give some updated。

or refined version of that triangle mesh，then given that refined triangle match。

rule again somehow compare it to the，input image see how much does it match。

the input image and then again move each，of the vertices a little bit in order to。

further refine the exact structure of，the 3d mesh to be output，and you can imagine going through。

several stages of this and hopefully by，the end you'll be able to output a 3d。

triangle mesh that matches the geometry，of the input image very nicely。

so that's the first sort of interesting，useful idea for processing triangle。

meshes with neural networks the second，is that we need some kind of neural。

network layer that can operate over mesh，structured data and the way that we do。

that is using an operator called graph，convolution so we're very familiar with。

two-dimensional and three-dimensional，convolution right the idea with normal。

2d convolution is that we have some grid，of feature vectors and that at the input。

and then the output we're going to，compute a new grid of feature vectors。

and every feature vector in the output，grid is going to depend on some local。

receptive field or a local neighborhood，of the features in the input grid and。

then we're going to slide that same，function over every point in the grid to。

compute all of our feature vectors in，the output now with graph convolution。

it's going to be very similar but sort，of extending not to two dimensional or。

three dimensional spatial grids，but instead to arbitrary graph structure。

data so what we're going to do is that，the input to a graph convolution layer。

will be a graph and a feature vector，attached to every vertex of the graph。

and now the output of the graph，convolution layer we want to compute a。

new feature vector for every vertex in，the graph and the the output feature。

vector for a vertex should depend on a，local receptive field of the feature。

vectors in the input graph to the graph，convolution layer so then we can use。

this particular mathematical formalism，up here at the top that lets us compute。

a new output feature vector F prime I，for vertex VI that's going to depend。

both on the input feature vector F I as，well as the the all of the neighboring。

feature vectors F J that are all the，neighbors in the graph to that feature。

vector F I and the way that we do this，as we all maybe this is sort of a lot of。

different low-level ways that you can，implement graph convolution there's a。

lot of different papers showing exactly，did slightly different architectures for。

this thing but they all share this，similar intuition that we want to。

compute the output feature vector in a，way that depends on sort of the local。

neighborhood of feature vectors in the，integrand and then we're going to apply。

this same function to every vertex in，the graph and sort of slide。

/ convolutional e and begin with this，and this is sort of we think of this as。

a convolution because we're sort of，sliding this function over every vertex。

in the graph to compute our output，feature vectors and then just like image。

convolution can be applied at test time，to arbitrary grids of arbitrary sizes。

well then a single graph convolution，layer can operate on graphs with。

arbitrary numbers of vertices an，arbitrary topology or connectivity。

patterns at test time then we can use，sort of 1：1 neural network layer that。

can process our graphs of arbitrary，topology so then in order to process。

triangle meshes with graph convolution，where the main body of a network is now。

going to be a graph convolutional，Network where we stack up many many of。

these graph convolution layers so then，in the inside the body of this network。

we will always attach a feature vector，at every vertex in the mesh and now at。

every layer of graph convolution it's，going to update or compute a new feature。

vector for every vertex in the mesh in a，way that sort of depends on local。

neighborhoods of the input of the，neighbors in the mesh to all of the to。

each vertex where the neighbors are sort，of along the edges as indicated by the。

faces and you can imagine stacking up，many many graph convolution layers to。

now update or to now process feature，vectors and propagate them along the。

edges of this mesh so I thought this was，again a very nice way to process mesh。

structure data with come up with with，some kind of neural network structure。

but now the problem is that I said that，our initial task here was to input an。

RGB image and then output the triangle，mesh so we need some way to actually mix。

in image information into this graph，convolutional Network so that brings us。

to I think the third really cool idea，that this pixel too much paper had and。

that's this idea of getting vertex，aligned features so here what we want to。

do is for every vertex in the mesh we，want to get some kind of feature vector。

from the image that represents the kind，of visual appearance of the image at。

that put at that spatial position of the，vertex so then what we can do is take。

our input image and then run it through，a 2-dimensional CNN and that will give。

us some 2-dimensional grid of image，features that we've seen many many times。

and now what we can do is if we，understand the in the camera intrinsic。

or the then what we can do is take our，3d triangle mesh and then project the。

vertices of the mesh onto the image，plane using kind of a 3d to 2d。

projection operator and that will take，every three that will take every 3d。

position of each vertex out in space and，now project it down onto the image plane。

and now for each of those projected，vertex locations we can use bilinear。

interpolation to sample a feature vector，from our image from our convolutional。

neural network features that now gives，us a feature vector for each vertex that。

is all perfectly aligned to the position，in the image plane where that feature。

vector projects and this idea of been，this bilinear interpolation is basically。

the same that we saw last lecture in the，ROI align operator in NASCAR CNN but。

here rather it was C so here we still，want to kind of sample on feature。

vectors and arbitrary positions in the，2d image plane but rather than sort of。

sampling them at a regularly spaced grid，like we did in the ROI align operator。

instead what we want to do now is sample，a feature vector at every point in the。

image plane for all the projected vertex，positions and that will allow us to mix。

in image information into our graph，convolutional Network okay so then the。

final thing that we need to figure out，with processing graphs is what is our。

loss function so then we're going to，have our model predicts own 3d triangle。

mesh and we have some ground truth the，3d triangle mesh and we need some loss。

function that now compares 3d triangle，meshes and tells us how similar our。

predicted mesh was to the ground truth，mesh but the problem here is that we can。

actually represent the exact same 3d，shape using different triangle meshes。

and when I and as an example here we，could represent a square using a try。

using two big triangles or using four，small triangles and both of these。

different not represent Asians and，represent the exact same shape and。

somehow we want our loss function to be，invariant to the particular way that we。

represent the shape using triangles we，just want the the loss function to。

depend on the underlying shape itself，and not the particular way that we。

decide to carve it up into triangles so，the the idea to get around that is。

actually our loss function we have we，have actually seen though we already。

seen the answer so what we're going to，them，two point clouds by sampling points。

along the interior of the of the mesh，and then use our chamfer distance to。

compare these these two point clouds and，in practice what we're going to do is。

sample points from the ground truth mesh，on the right sample points from the。

predicted mesh on the left and then，compare these two point cloud。

representations using this chamfer loss，that we've already seen but of course。

the problem here is that for the ground，truth mesh on the right you can imagine。

doing those that sampling off line and，sort of sampling all those points and。

cashing them to disk but now to in order，to two sample points on the left from。

our prediction now we need to in order，to do that we actually need to do this。

sampling operation online so that's sort，of a difficult implementation to do and。

then also we need to be able to back，propagate through this sampling。

operation on the left if we're going to，do this to do this online I'm gonna。

turns out there is a way to sort of back，propagate through the sampling operation。

in a nice way that you can check out，this ICML 20：19 paper to see the exact。

details ok so then once we've seen all，of these four key ideas that gives us。

some that gives us a Mac a way that we，can operationalize a neural network that。

can input an RGB image and then output a，triangle mesh that represents the 3d。

shape of that image right then we're，going to use iterative refinement we're。

going to use graph convolution at，several points in this graph convolution。

Network we're going to mix in image，information using vertex align features。

and we'll train the thing using a，chamfer loss function so that gives us。

our four 3d shape representations，there's actually a couple more issues。

they need to deal with when when dealing，with 3d shapes but maybe we won't go。

into full detail on these so we need，some some metrics to compare 3d shapes。

actually tell whether our models are，working well we saw in 2d we can use。

intersection over union to compare，bounding boxes we can actually use a。

similar type of intersection over Union，to compare 3d shapes but it turns out。

that I'm actually intersection over，union of 3d shapes is maybe not as。

meaningful or useful as a metric as we，might like so another metric we can use。

to compare 3d shapes is this chamfer，distance that we've already seen so one。

way to compare 3d shapes is to sample，point clouds from each of our different。

shape representations and then compare，them using a chamfer distance and but。

the problem with the chamfer distance is，that because it relies on this kind of。

l to distances and it's very sensitive，to outliers so if you look at these。

these two examples here this this this，this one example unlit on the left has。

very different chamfer distances to，these two examples on the right on。

because of this l2 nature of the loss，function so as a result I think a better。

loss function for sure come for，comparing 3d shapes is to use an f1。

score which also operates on point，clouds so this is sort of similar to the。

the chamfer loss in that we will take，our to 3d shape representations and。

sample point clouds from them and then，compare the two 3d shapes as point。

clouds so what we're going to do is，maybe we've got our predicted point。

clouds in orange here and our ground，truth point cloud point clouds in blue。

and then we can compute the precision，that is the fraction of the predicted。

points that were actually correct，and when I say correct that means that。

yeah a predicted point is counted as，correct if it is within some some。

threshold radius of a ground truth point，so then for this example we kind of。

imagine expanding out a sphere around，each of our predicted points and then if。

some growing truth point falls within，that sphere then the predicted point is。

counted as true so then the precision in，this example it would be 3 over 4。

because 3 of our 4 predicted orange，points somehow our correct and have a。

blue point fall within that within the，radius then we can go the other way and。

compute the recall which is what，fraction of the ground truth points were。

hit with a predicted point within some，radius and then here for this example。

the recall would be 2/3 because two out，of the three that doesn't seem right it。

actually looks like they're all hit no，they're not because the one the lower。

right doesn't quite hit they just sort，of barely touching right um so then of。

these three blue points on two of them，are hit with over the predicted point。

within the radius and the third one is，not so recall is 2/3 and the f1 score is。

this is this is this a geometric mean of，the of the of the precision and the。

recall so in this case would be point，seven so this is a number between zero。

and one and the only way we can get one，is if both the precision and the recall。

are 1 and this f1 score is sort of a，nicer metric for comparing 3d shapes。

because it's more robust to outliers so，I think that this is the the best roll。

like sort of the nicest metric we have，right now for comparing 3d shapes okay。

so another thing you need to deal with，worry about when you're working with 3d。

shapes is actually the camera coordinate，system that you're working with because。

now cameras and these camera systems get，kind of complicated once you're working。

in 3d so there's one so that so suppose，we're working on this task where we're。

going to input input an image and then，we want to output a pretty shape。

representing the 3d shape of that input，image now one up and then we have to。

answer the question what is the，coordinate system that we're going to。

use to represent the 3d shape out in 3d，space well one option is to use a so。

called canonical coordinate system and，what this means is that we sort of for。

the object for each object category we，kind of fix canonical directions of。

front and left and up and running and，and down so for example if we're maybe。

training a network to predict 3d shapes，of chairs then we say that the plus Z。

Direction is maybe always the front of，the chair and the plus y direction is。

always the up is always going up normal，to the to the seat of the chair and then。

plus ax is always to the right another，option is to predict in View coordinates。

so this would be to use a 3d coordinate，system for the target that is aligned to。

the input image and this would be，another option for representing the。

three the the coordinate system of the，3d shapes and we're trying to predict。

that and actually if you read a lot of，papers in detail I think a lot of people。

use view coordinates just because it's，sort of easier to implement because。

these 3d models are kind of stored on，disk and some canonical coordinate。

system you could just kind of load them，up in disk and then predict the。

coordinate system that they're stored，with natively so I think a lot of people。

use these canonical coordinates for a，lot of in practice but I think view。

provide but in but there's a problem，with canonical coordinates which is that。

it means that the features of your，outputs are no longer properly aligned。

to the features of your inputs whereas，if you use a view coordinate system that。

means that the position of your the，feature is corresponding to each thing。

that you output are going to be better，aligned to the original input that you。

process as input so for this reason I，think it's preferable to make。

predictions in View coordinates there's，actually some been some some research。

that backs this up so here it is，experiment where they see that if you。

train two networks that are identical，but one is in view coordinates and one。

is in canonical coordinates then the，network in canonical coordinates tends。

to overfit to the training shapes that，it sees during training whereas networks。

that are trained in view coordinates，tend to generalize better at test time。

to either novel 3d shapes or to novel，object categories so for those reasons I。

think it's maybe preferable in most，scenarios to make predictions in you。

coordinates so then if we're as soon as，kind of an example what that looks like。

is that if we're going to make view，centric voxel predictions then what that。

means is that this voxel 2，representation that we talked about for。

predicting voxels becomes very natural，because now we're going to maybe for。

each we for every aligned appropriate，position in the input image we need to。

predict an aligned tube of occupancy of，box occupancies，which then is sort of natural to process。

with this 2d voxel tube convolution，representation that we talked about ok。

so the way all states that maybe cover a，couple of the datasets that people often。

use for these tasks one is shape that，right because we're all very familiar。

with image net an image net was this，like you know a large-scale data set of。

images that led to keep learning，revolution and blah blah blah and。

because of the because of image that was，so successful then like everyone wanted。

to build a data set and call it，something that so then we have shape net。

which is supposed to be like the image，net of 3d shapes so then shape net is。

actually a fairly large scale it gives，about fifty thousand of 3d CAD models or。

3d mesh models spread across 50，different categories and then it's。

common to render these 3d CAD models，from a variety of different viewpoints。

to actually generate a fairly large data，set of maybe around a million images so。

it's fairly similar in it to image that，in scale in terms of images but because。

um because it's kind of synthetic right，because these objects are just like。

isolated CAD models they're not real，images they're not they don't have real。

context to them so they're kind of it's，kind of nice for playing around with。

with 3d representations but it's not，it's not a realistic data set another。

data set that I like a lot is this pix，3d data set from some people at MIT。

which actually has real-world images and，it actually has 3d mesh models of。

furniture that are aligned to pixel wise，to the input images，and the way they collected this was。

quite ingenious because it turns out，that um people loved shop at IKEA and。

when people buy IKEA furniture they love，to go online and say like hey look at my。

new IKEA bed model like whatever and it，then let you can just like Google the。

IKEA model number and then get a lot of，images that show you like this exact bed。

in a lot of different rooms and then it，turns out that IKEA actually publishes。

3d mesh models of their furniture so，then what they can do is download all。

these 3d mesh models from Ikea um go on，Google Image Search and search google。

for a bunch of images of the specific，IKEA models and then pay people to align。

the the IKEA models to the input images，so that's like pretty cool I thought。

that was very clever way to collect a，data set and because of that it means we。

actually get like real world images with，like lots of like cluttered messy。

bedrooms and stuff that show this，show-off like different types of IKEA。

furniture in sort of cluttered real，world scenarios ok so then that finally。

architecture that we teased in the last，architecture that we teased in the last。

lecture so here we're basically，combining all of the detections - all of。

the detection pipeline that we built up，in the previous lectures but now in。

addition which then we want to input a，real-world RGB image detect all the。

objects in the image and then for each，detected object emit a full 3d triangle。

mesh to give us the 3d shapes of each of，those detected objects and the way that。

this works is that it's basically as we，said last time all the detection stuff。

is basically NASCAR CNN and then the 3d，shape prediction part is sort of a blend。

of all of these 3d shape prediction，methods that we've talked about in this。

lecture so one of the things that we do，in mesh our CNN is actually use a hybrid。

3d shape representation we ultimately，want to predict a mesh so we liked this。

idea of mesh deformation from from pixel，to mash but the problem with mesh。

deformation is that it constrains the，topology of 3d shapes that you can。

output because if you recall this idea，of 3d mesh deformation is that the model。

was going to input some initial 3d mesh，and then it was going to reposition all。

the vertices in order to give our final，output mesh but this only works if the。

if the the model the the shape，the output has the same topology as that。

initial 3d mesh shape so for example it，means that there's no possible way to。

deform like if you take in a topology，class you know there's no way that you。

can continuously deform a sphere into a，doughnut so then there's there's just。

it's just fundamentally impossible to，input this like a lip side or spherical。

mesh and then deform it to predict a，doughnut output so that's kind of a。

fundamental limitation with this idea of，iterative refinement but it turns out。

that these other other things that these，other shape representations we've talked。

about today actually do not suffer from，this so basically what we're going to do。

is we want to overcome this limitation，of limited topologies of this this。

iterative refinement method by first，making coarse voxel Pradesh predictions。

converting the voxel predictions to a，mesh and then using iterative refinement。

from there so basically the pipeline is，that given an input image will do all。

the 2d object recognition stuff that，we're familiar with from NASCAR CNN this。

is going to be this these are P ends and，then for each RPN we're going to regress。

boxes and then have a second stage it's，gonna do our classification and our。

instant segmentation and that's going to，give us these these boxes for the。

detective and use images in the scene，then for each detected detected image。

we're going to use a voxel tube，representation a voxel tube network in。

the second stage of the the NASCAR scene，and pipeline to predict a course voxel。

representation of the 3d of of each of，each shape and then we'll convert each。

of those predicted voxel representations，into some blocky mesh representation and。

then use that blocky mesh representation，as the initial mesh to use to go along。

for iterative refinement but then allows，us to finally output for each detected。

in it for each detected object I'll put，this this high fidelity mesh。

representation and then our results is，like basically we could predict things。

with holes like that that's the big，thing right because because we're going。

through this intermediate box or，representation it allows us to output。

meshes that have sort of arbitrary，topology so if you look at so these are。

some example results where the top row，shows our input RGB image the middle row。

shows examples from this iterative，refinement approach that is going to。

deform from a sphere for initial sphere，or mesh and you can，because it's it just can't get rid of。

holes in objects so for this example of，like the the chair on the left it seems。

like the network kind of knows that，there should be a hole there so it kind。

of pushes the vertices all the way from，the hole but it just can't delete that。

face so it just has no way to actually，properly model the holes in these。

objects whereas on in our in our in our，results because we go through this。

initial course box or representation，then the voxel representation can be。

used to model the initial holes in the，object and then the meshes can be used。

to refine and give us this very，fine-grained outputs there's a slight。

problem though which is that if we train，only with the chamfer loss we actually。

get really ugly results so we actually，find that we need to use some。

regularization term that encourages the，result the generated meshes to be less。

degenerate and more visually pleasing um，so the way that we do that is that in。

addition to minimizing the chamfer loss，between the predicted mesh and the。

ground truth mesh then we also minimize，the l2 norm of each edge in the mesh and。

it turns out to this relatively simple，regularizer，let's the model predict now very well。

structured meshes and the results is，that now we can predict these full。

triangle meshes we can input these，real-world images on the Left we can。

detect the objects in the images and，then predict these these output 3d mesh。

mesh models that give very fine-grained，3d shapes for each of the detected。

objects and you can see that they，actually represent not only the visible。

portion of the object but also the，invisible back sides of the objects and。

from this bookshelf example on the upper，left hand here you can see that we can。

represent it we can output these 3d，meshes with very complicated topology。

with a lot of different holes so that's，a kind of nice nice result and then you。

know because this is built on top of an，object detection framework then it can。

actually detect many many objects per，scene but of course it doesn't work。

perfectly so and actually another kind，of nice feature of this architecture is。

that it actually predicts it does what，we call a modal prediction so that means。

that it predicts not only the visible，parts of objects but also the occluded。

or the invisible parts of all of all the，objects so if you for example if you。

look at the image on the left you can，see that like part of the couch is。

actually occluded by the dog's head but，our prediction on the right we actually。

predicts the full we actually predict，the 3d，of the couch even in the port even in。

the region of the image without were，though where the couch was covered up at，the dogs head。

um so that's that's called a mobile，prediction and that's actually a bit a。

little thing that's something like，Nascar Sina usually will not do and。

notice that we don't predict the dog，because IKEA doesn't sell dogs and then。

there's another it's also kind of，interesting to look at the failure modes。

here and what's an interesting failure，mode is that we see that places where。

the 2d recognition fails are also places，where 3d recognition tends to fail so。

here if you look at the predicted，segmentation mask for the bookcase you。

see that the regions of the image where，we miss the segmentation mask are also。

the regions of the image where we miss，on the predicted mesh so that makes me。

think that maybe improvements in 2d，recognition could also lead to future。

improvements in a 3d recognition so，that's then to kind of a recap where we。

got today we talked about these two，fundamental problems of understanding 3d。

shapes of neural networks which was，predicting 3d shapes from edges or maybe。

classifying 3d shapes and we had kind of，a very fast walk over of how you can。

represent all these different types of，3d record 3d shape representations using。

neural networks and that's that's kind，of where we ended off today and。

basically today was about adding a third，spatial dimension to our on their own。

networks and now next time we'll talk，about videos which is like adding a。

temporal dimension to our neural，networks so it'll be a different way。

that we can extend our neural networks。

![](img/792014a42c3725ca758e4cbeaa2df831_1.png)

to it to an extra dimension so come back。

![](img/792014a42c3725ca758e4cbeaa2df831_3.png)