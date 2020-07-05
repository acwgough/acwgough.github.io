---
title: "Quantum Bird Poop"
date: 2020-07-07
mathjax: true
categories:
  - physics (informal)
tags:
  - quantum, estimation
---

(This post is based on a Twitter thread I originally wrote [here](link). I wanted to slightly formalise some of the thinking that went into my original calculation, as well as to expand on some points I didn't include in Twitter.)

There's been a viral TikTok making the rounds recently, which shows a bird pooping on a car windshield and then the bird poop showing up on the inside of the car window. The viral video explains this as the bird poop "quantum tunneling through the window" and claims that this has something like a "1 in 15 trillion chance of happening." This came to my attention when host of SciShow and generally cool person [Hank Green](link) posted a TikTok complaining about this viral video misrepresenting how quantum mechanics works (mirrored [here](link)) (Also Hank has a [new book out](link) and it is excellent and everyone should go read it). As someone who knows something about quantum mechanics, I wanted to try and calculate what the actual probability of something like this happening, because I *know* that is it much smaller than the claimed 1 in 15 trillion.

# 1. Why does this *feel* wrong

A good starting place for this discussing is why does this number "1 in 15 trillion" feel wrong to someone who has studied quantum mechanics. 1 in 15 trillion is indeed a very small chance of something happening, and the problem with very small and very big numbers is that the human brain is not at all designed to be able to think about them accurately. 


The main number that becomes relevant in quantum mechanics is Planck's constant $h$. Often physicists will use a different letter $\hbar$ (pronounced h-bar) which is simply Planck's constant divided by $2\pi$ to prevent lots of factors of $2\pi$ from floating around in equations. In a sense, the thing that makes quantum mechanics, quantum, i.e. what makes it different from classical, everyday physics, is that this Planck's constant when written in everyday units, is very very small. Writing $h$ in units of Joule seconds (it has dimenisons of energy times time) Planck's constant is
$$
h = 6.626\times 10^{-34} \rm \ J \cdot s .
$$
To see why this matters so much, let's see how $h$ tends to appear in quantum mechanics equations. 

The de-Broglie equation relates the momentum $p$ of a particle to its wavelength $\lambda$ by
$$
\lambda = \frac{h}{p}
$$
(this is the equation that people talk about when they introduce "wave-particle duality"). The momentum of a classical particle is simply its mass times its velocity. If we consider an "everyday" particle to be something that has a mass which is sensibly measured in grams or kilograms, and a velocity which is sensibly measured in metres per second, then the wavelength $\lambda$ will be very small as
$$
\lambda = \frac{6.626\times 10^{-34} \rm \ J\cdot s}{\sim 1  \text{kg} \ \times  \sim 1 \rm \ m/s} = \frac{\text{very small # of metres} }{\text{# about 1}} = \text{very small # of metres}.
$$
The quantum wavelength of an "everyday" object is very very small precisely because Planck's constant is very very small in everyday units. This is why everyday particles act only like particles, and not like waves.

A similar thing is happning in the problem we're considering. Quantum tunneling is, you guessed it, a quantum effect, and so will introduct Planck's constant somewhere. This Planck's constant will be multiplied or divided by some number that is about 1 in everyday units when we're consiering bird poop, because bird poop falling is sensibly measured in grams, kilograms, metres, and seconds. It actually gets even worse, as with tunneling, the probability typically goes *exponentially* with $1/h$, and the exponential of a very large number is very *very* large. So, without doing any actual calculations yet, I'm going to extimate that the probability of this happening is something like
$$
P_{\rm tunnel} \sim \frac{1}{e^{Q/h}} = e^{-Q/h}
$$
where $Q$ is some number that we need to estimate from the size of our poop droplet that has the same units as $h$ (because anything in an exponent cannot have units). We know that $h$ has units of energy $\times$ time so $Q$ must also have these units. A reasonable amount of kinetic energy for bird poop to have is maybe 1 Joule, and the timescale is maybe a millisecond for the poop to "splat" (really the timescale should be how long the poop would take to travel through the windshield). Putting these in:
$$
Q = 1 \rm \ J \cdot 0.001 \ s = 1 \times 10^{-3} \ J \cdot s
$$
then
$$
\frac{Q}{h} = \frac{10^{-3} \rm \ J \cdot s}{6.626\times 10^{-34} \rm \ J\cdot s} = 1.5\times 10^{30}
$$
so the final probability should be something along the lines of 
$$
P_{\rm tunnel} \sim e^{-Q/h} = e^{-1.5\times 10^{30}} \sim 10^{-10^{30}}.
$$
And wow, that is soooo much smaller than 1 in 15 trillion ($P_{\rm tunnel} \sim 6.6\times 10^{-14}$). So, even without any detailed calculations we can see that it's right to be suspicious of this number. We'll delve into thinking about quite how small this number is later in this post.


# 2. The set up of the problem

With some initial thoughts out of the way, let's set up the problem a little more formally.The way that I considered this was similar to a classic problem in undergraduate quantum mechanics: tunneling through a finite potential barrier.

The set up is as follows. We start with a quantum particle with mass $m$ and energy $E$ moving in the positive $x$ direction. This particle moves freely until it reaches $x=0$, where it encounters a *potential barrier* of height $V_0$ and width $a$. Because we're considering a quantum particle, some of the particle's wavefunction will be reflected off the barrier, and some will continue through the barrier. How much "tunnels through" is precicely what we're trying to calculate. 

***IMAGE HERE***

For a classical system with the same set up, we notice that as long as the particle has more energy than the height of the barrier, it can get to the other side, but if $E<V_0$ then the far side of the barrier is impossible to get to.

I won't derive the equation for the tunneling probability in this set up, because it's long and boring and takes us out of the realm of bird poop windows, but if you're interested it can be found in most quantum mechanics textbooks. I took it from ******chapter x of y*******. The equation is the following
$$
P_{\rm tunnel} = \frac{1}{\cosh^2(Ka) + \left(\frac{k^2-K^2}{2kK}\right)^2\sinh^2(Ka)}
$$
where the k variables $k,K$ are called the "wavenumber" in the different regions and are defined
$$
k = \frac{\sqrt{2mE}}{\hbar}, \qquad K = \frac{\sqrt{2m(V_0-E)}}{\hbar}.
$$
We can already start to see that the combination $Ka$ is like the $Q$ variable defined in section 1. 

To be able to plug numbers  into this formula we're going to need to estimate $k, K, a$ which requires knowing

* $a$, the thickness of the barrier. This is just the thickness of the glass of a car windshield.
* $m$, the mass of bird poop
* $E$, the energy of the bird poop while falling
* $V_0$, the height of the potential barrier, i.e. how hard is it to get through the glass.


# 3. Estimates
## Thickness of the glass

The thickness of the glass, which we're taking to be the width of the potential barrier, $a$, is the easiest thing in the problem to estimate. For practical purposes I simply looked up the thickness of glass used in cars, which is [approximately 2 mm](link). If I didn't have access to this webpage I probably would have guessed it to be less than a centimetre but more than a millimetre, maybe 2-5 mm, which is consistent with what our source says.

## Mass of the bird poop

The mass of the average bird dropping that hits cars is surprisingly difficult information to procure, so we'll have to rely on some reasonable guesswork. This is usually present in any sort of "real" problem, and we'll revisit how much this estimate affects the final result at the end, to see how important it is we get it right.

To start, we can take a guess at how big a splat of bird poop is. If we assume it's a circular splatter, the average one might be 3 cm wide and 1 mm thick, leaving us with $2.82 \rm \ cm^3$ of bird poop. I don't know how dense bird poop is, but it's probably not too different to that of water (physicists like to assume anything related to biological systems has the same density of water). I think bird poop might be slightly more dense than 

## Energy of the bird poop

## Height of the barrier

# 4. The final number
## Analogies for large numbers
## Properties of large numbers and *very* large numbers

# 5. Concluding thoughts

## Quantum effects (decoherence etc)
## Value of estimation
## How much does the accuracy of our estimation matter?