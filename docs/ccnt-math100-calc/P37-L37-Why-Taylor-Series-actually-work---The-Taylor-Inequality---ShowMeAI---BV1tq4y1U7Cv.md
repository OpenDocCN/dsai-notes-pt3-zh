# P37：L37-Why Taylor Series actually work - The Taylor Inequality - ShowMeAI - BV1tq4y1U7Cv

If I have a power series or a Taylor series in specific。

 the power series is only as good as its remainders are small that if you want to approximate something with the first end terms of a series。

 well， how bad is the remainder Now well in the past we've seen the alternating series remainder and the integral test remainder in this video。

 we're going to focus on the Taylor series and talk about an inequality that bounds the remainder for a Taylor series。

😡，And indeed， the fact that we're going to be able to take the remainder for our Taylor series and control it in a really nice way is really what makes the Taylor series so powerful。

 Otherwise， it would just be some random expression。 But why was it useful。 Well。

 it's going to be useful because remainder is going to be small in an appropriate sense。 So。

 for instance， this is the infinite sum， But I can sort of divide the infinite sum into two different sub portions。

 There's an initial finite portion。 So the sum from I equal to1 up to n， some fixed number N。😊。

And then the infinite tail， which is the N all the way to infinity。 So two different regions。

 And the first of them， I'm going to call my Tayloror polynomial now polynomial。

 because that's finite。 And the second is my tailor's remainder。

 And then what the goal of this video is to take that remainder and argue that in an appropriate sense。

 this can be considered small， at least small when your X values are near a。

 the center of your series。😊，So let's try to graph a few things and get a sense of what's going on here。

 The first point that I want to illustrate is that the remainder really is a function of x。

 So here I've given a generic F of x。 And I'm going to put its first tater approximation on this。

 This is T1。 And it's just a linear approximation， as we could have done back in cculus 1。

Then the remainder is going to be， well， the difference between these two things iss this little strip here where I take the F of x and I subtract off the first Tayloror polynomial。

 and that height that difference is my remainder。Now， if I vary my X。

 where I'm asking my remainders at， like， if I move this along。Then by remainder gets bigger。

 it's a function of x。 And as we can sort of see here。

 it's a function of x where close to the center， the value of x equal to a in this case。

 x equal to 0。 The remainder is pretty small。 But the further that you go away。

 the remainder appears to be getting bigger and bigger and bigger And ge。

 this is generally the case that as you go away from the center。

 your remainder has the possibility of getting bigger and bigger and bigger。

 So whatever my formula for the remainder is， it better depend on the difference between x and a。

 it better depend on the magnitude of x minus a。But what else does my remainder depend on。

 I've put up a new F of x and a new linear approximation， a new T1 and a new remainder。 Now。

 we already know that as I change the x values， my remainder is going to change。

 But what if I changed the curvature of the function itself。As in my F of is a concave up function。

 but a fairly shallow one right now。 Watch what happens if I make my F ofex a sort of more aggressively concave 1。

 is in I take this and I transform it。 Now， watch the remainder as this moves。

 The remainder gets bigger and bigger and bigger， when my function gets sort of more and more curvy and and shallow in a sense。

 Now， Concavity is what the second derivative tells us about。😊，That is。

 I've done my first approximation here。 my linear approximation happens to be a horizontal line in this example。

 but the second derivative of the concavity of the function is going to make very large differences in terms of how bad the remainder is。

Now I had to program this so I know that my actual function is one plus kx squared。

 when I animated it， I sent my K to be a bunch of different values。

The first taner polynomial is just always one。 The derivative of one plus x squared is just going be 0 at x equal to 0。

 So it's the function value plus 0 So just one。And then the remainder is the difference between the function and the first Taylorlor polynomial is。

 and it's this K x squared。 Okay， so in some sort of loose sense。

 we're thinking that the remainder depends on x。 And if I'm doing a linear approximation。

 it depends on the concavity or in other words， the second derivative。All right。

 so let's actually see the full formula。 This is Taylor's inequality。

 Imagine that that n plus one derivative is bounded。 It's all less than some fixed number M。

 or at least it's all less than that M in some region， and x minus a less than D。

 some number that's as close as you might need it to be。 So in this narrow region。

 the second derivative is constrained to be some particular value or in general。

 the n plus one derivative is constrained to be less than M。 Then if you have that。 What do you get。

 Well， the remainder is less than that M that you computed that bound divided by M plus one factorial times the x minus a to the power of M plus1。

 And indeed， that's a remainder。 So it depends on this distance， the x minus a。

 It depends on that bound on the n plus one derivative。

 And it depends on n is because of the n plus one on the bottom here is N gets larger。

 This remainder is getting smaller and smaller and smaller。 So that's the general case。

 in our specific case here where we are doing the first。😊，Taylor polynomial。

 that meant that our M was equal to one。 So we were considering one plus one。

 which was the second derivative。 And the second derivative in this example is just going to be。

 well， twice K。 You do one derivative takes the x squared down to a2 k X and then goes away to 2 K。

 So M would be 2 k in this particular example。 Indeed。

 it generally looks like that bound times in our case。

 the remainder we compute exactly was x squared。 But in general。

 the distance between x minus a to the power of n plus1， if n was one。

 that would be x minus a squared。 So this general formula does seem to align with this lower dimensional when we have here。

 And indeed it's true in general， although I won't prove it more than this in this particular video。

 So now that we have the statement for Taylor's inequality， what can we actually do with it。 Well。

 let's return to the study of the Taylor series for E to the X。 Now。

 when I first introduced Taylor series。 we talked about the Taylor series for E to the X。

 But there was a little detail you may have missed。 What I said was that。😊。

If there is a power series that converges on some interval。

 then that power series better have the coefficients given by the Taylor series。

 In the case of E to the X， the coefficients are one over and factoria。

So the whole thing was conditional on the fact that if you had a representation。

 then it tells you what the representation was， but does E to X even have a power series to begin with？

So let's go out and compute the remainder and see whether the remainder is good or whether the remainder is bad。

 Now， I'm going to restrict myself to the situation where the x is less than D in terms of magnitude。

 So I'm considering some region as the Taylor's inequality ask us to do。

 We look at it for some particular region。 Okay， now。

 if I take n plus one derivativeros of E to the X。 I just get right back to E to the X and take as many as you wish。

 Always E to the X。So then if your x is less than D， your E to the x is less than E to the D。

 In other words， this e to the x is some smaller number than E to the D。 That's your M。

 That is your bound that you can put on the n plus one derivative in this particular region。Okay。

 put that into my formula。 So what do I get， My n remainder is less than e to the D that bound。

 And then I multiply it by the x minus a。 So just x in this case。

 absolute value to power impulse plus 1 divided out by m plus 1。Now。

 what happens to this remainder is my n gets large。 if I take more and more terms。 Well。

 either the D is just sum number doesn't matter in the numerator。

 you have a polynomial X to the power of n plus  one。 That would be a bigger polynomial。

 but it's polynomial。 And in the denominator， you have effect factorial。

One of the things we know of our sort of hierarchy of functions is factorials are going to dominate polynomials and certainly dominate a constant like E to the D。

 So as n gets large， this entire remainder is going to 0 as n goes to infinity。

We should just say my remainder is actually really， really good。 That's what you want。

 That's your best case scenario。 It says， if I take enough terms。

 My remainder can be as small as you wish， no matter how small you need it to be for your specific application。

 I just need to take enough values of N。 And that my remainder is good enough for you。

 This is incredibly powerful。 It's， it's so powerful that I will say that E to the x is now equal to its Taylor series。

 It's equal to the sum of the x to the n over the n factorial。

 The Taylor series that we computed up before。😊，The first video we just computed it and we said，Hey。

 look at this series， isn't that lovely， but now we know that it's a series where the difference between the series and the function。

 the remainder goes to zero if you take enough terms and that's compelling enough that we will now say the function E to the X is not just similar to。

 but in fact is actually equal to this particular Taylor series。

This inequality is what makes all the magic worse。 Now， I can use E0 D X。

 And if you do the same thing for sine and cosine and all the other sort of traditional tailor series。

 you can get all the functions that you want。 The remainders are going to be going to0。

 And then no matter what level of uncertainty you need， you could always use a tailor approximation。

 just by taking n to be sufficiently large。 So that is incredibly powerful。😊。

