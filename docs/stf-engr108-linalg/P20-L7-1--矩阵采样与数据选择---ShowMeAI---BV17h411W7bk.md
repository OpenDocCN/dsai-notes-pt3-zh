# P20：L7.1- 矩阵采样与数据选择 - ShowMeAI - BV17h411W7bk

![](img/19619b77769012253dd3461cc9004784_0.png)

We now turn to chapter7 which is matrix examples and we'll look at a bunch of matrices that come up in applications。

 it's just to give you an idea of what matrices what matrices arise in practice， what they look like。

 and also in many cases we'll look at things like what does a row mean or a column or what does matrix vector your multiplication mean because that'll always be interesting depending on the application。



![](img/19619b77769012253dd3461cc9004784_2.png)

So we'll start with geometric transformations。So a lot of geometric transformations in 2D or 3D can be represented via matrix multiplication。

 so that looks something like this just y equals AX a is you think of a as a matrix that carries out the geometric transformation so here's an example consider the mapping or transformation that rotates a vector by theta radiance so here's a vector X and it gets rotated over to theta radance got the same same norm。

 but it's been rotated。And it's been rotated by theta radiance， and of course。

 in the mathematically positive direction， that means counterclockwise。

Okay so's that's a rotation mapping and it turns out it has the form y equals ax Now to get to get the entries of a there are lots and lots of ways to do it。

 but a very simple one is to do things like this when you have y equals a X if x is equal to E1 the first unit vector then y is going to be the first it's going to be the first column of a so for example。

 if I took e1 that's this vector here and I rotate it by theta radians。

 I get to this vector and sure enough this distance is the cosine of theta。

 that's our first entry here and this height here is sine theta and that's here and to get the second column we look at a E2 so remember that when you have a matrix a and you multiply by E2。

 the second unit vector what you get is the second column so let's take E2 E2 is this vector and we rotate it。

Theta radance， whoops， my mistake， that's a little bit too long， but there we go。

So we take that and then we say， what are the coordinates of that vector？

The X coordinate or x1 coordinate here is going to be minus the sine theta and so there you go that's that one and then the height here of this thing here over here is going to be cosine theta and so that gives you this thing and by the way。

 a matrix like this is called a rotation matrix for obvious reasons because it rotates vectors by theta radiance this is just one example。

 there are a couple of others if you take a look in the book you'll see more for example。

 reflection through a plane things like that and rotation matrices are used in lots and lots of applications in mechanics in lots and lots of areas in graphics for example。

 when you're working out know what does something look like from a certain angle okay。

The next big group of examples we're going to look at is pretty generic it's called selectors and i'll tell you what a selector is so a matrix is a selector if each of its rows has exactly one one and all other entries are zero now another way to say that is that each row is a unit vector transposed so here's a selector i'll just make one for you like this。

Right， so there you go。Okay， so there's there's a three by three selector matrix and if I multiply this by x1。

 x2， x3， that's a vector， what I what comes out is that's x3 because I'm just going cross here and down here。

Then I get x1 and I get x3 and what it says is if you think of this as y and y equals ax then what ax gives you is each entry of that if that's y each entry is one of the x's so each what it is is that selecting and it's selecting from the entries of x right they can be repeated so for example here x3 shows up there and it also shows up there so that's how that works and so multiplying by a a vector basically selects different entries Okay so here's here's a practical example from if you like signal processing or time series here's the matrix a and it's an M by2 m matrix and it looks like this。

Lots of ways to interpret it， so the first row is E1 transpose。The second row is E3 transpose。

 The third is going to be E5 transpose and so on。 So if you imagine what happens when you multiply this by a vector x。

 here's what you get。 it will take the first entry in the first component of AX then it will take x3 that's the third entry of X then x5 and so on。

 And so for example， if x was a time series then this would be referred the slang would is you would say that the time series has been downsampled to x meaning I'm taking the first。

 the third， the fifth， the seventh and so on。 And so' that's what that so you would be able to look at that matrix and say a that represents if you multiply by a vector that's downsampling for example but this comes up all over the place in a lot of image processing you'd get the same thing like image cropping would be a selector right so if I have an image represented by a big long vector and I want to do things like crop to some smaller portion of it。

I'm just selecting various pixels and again it would a would be a selector matrix okay so this will come up we'll see this in a lot of applications。



![](img/19619b77769012253dd3461cc9004784_4.png)

![](img/19619b77769012253dd3461cc9004784_5.png)