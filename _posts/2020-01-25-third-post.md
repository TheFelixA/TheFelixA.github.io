---
layout: post
category: Education
tags: [Math, Statistics]
title: Intro to Probability Theory
---

This post will provide an overrview of what I learned in my first semester probability course. The purpose of this post is to improve my understanding and presentation of the material. The focus will be on the broad picture and as a result, the treatment of the subject will not be rigorous. The article will be intended for an undergraduate. I will provide intuition and refer interested readers to references. 

Along with course lecture notes, the other material that I used were from Resnick and Taboga to help get a simplified view of what proability works. Then I worked my way up to Cinlar, Durrett and Dembo. Ash's probability book is also a good book to follow for beginners in probability theory. Those books provide a much greater detailed exposure to the topic and will do more justice I can in a single post.

There will be six sections: (1) Measure Theory (1.a) Measurable Spaces (1.b) Random Variables, (1.C) Expectations; (2) Law of Large Numbers (2.a) Weak Law (2.b) Strong Law; (3) Central Limit Theorem (3.a) Characteristic/Generating Functions (3.b) Central Limit Theorem; (4) Markov Chains; (5) Martingales (6) Poisson Processes

Measure Theory:

Measure Spaces

Measure theory provides a structure to formally develop probability thoery. Suppose we run an experiment where we know all the possible outcomes. Then in order to properly define a probability of an event, we must also include probability of the event not happening (complement), and the proability of multiple events including that one in conjunction (intersection). A simpler way of stating this is by saying that the collection of all these events must be explicitly listed. Or equivalently, that the overarching set that contains any subset of events is closed. The reason that it is called closed in because we we are performing boolean algebra on these sets, and the resulting set is still in the collection. The formal name for the collection of sets is called a sigma-algebra.

Notice how general these sets are, no mention of how we enumerate the results of the experiment is of concern. That shows the beauty of math, the foundations are based on principals that lead to generality. 

A probability measure is a function that takes in an element from the outcome and maps it to a number between 0 and 1. The probability measure along with the sigma-algebra we defined earlier is called a meassure space. This framework will work in defining any experiment. The reason that we do not define a probability as simply the proportional result of an experiment is because it fails in many instances, i.e..... 

We can represent probabilities as their cdf

Side note: If we have mutually exclusive events such that the union of the events forms the whole sample space. Then we call that a partition. The nice things about partitions is that they are independent. We can treat them as a sort of basis of the sample space. This relates closely with basis in a linear algebra sense. When we compute probabilities on the partitions we no longer have to worry about inclusion exclusion formulas. Also, when we compute expectations it is easier to see.	

Random Variables

A random variable is simply a way for us to represent the outcomes. It is a mapping from the sigma-algebra to another space. The range is usually the real number line but it does not have to be limited to it. We are very concerned with being able to pull-back into our domain space from the range so this function should have an inverse (injective to be more specific). The inverse can be the empty set. Most of the time we label the random variable with a capital letter, such as X.  

We can transform these random variables too.	

Expextations

Expectations is another way to define the weighted mean through the random variable. It is written symbolically as an integral and can be used to formulate the Riemann integrals that we are familiar with. Expectation is  more general concept. With a Reimann integral, we take the function value and multiple it infitismal changes in the x axis. With expectation we take the same function value and now multiply it to the probability of the pull back from the random variable. We can find expecations of a transformed random variable too.

Law of Large Numbers:

This is the first major theorem that we discuss and it is a very central topic in probability and statsistics. Suppose we have a sequence of independent and identically dfistributed random variables. If we sum the random variables and divide by the amount (to get the average), then that will converge to a constant that we expects

Weak Law of large Numbers:
In order to discuss the weak law we need to become familiar with a convept of convergence called convergence in probability. This is defined as the lim ... Giving the epsilon-delt definition of this, it means that, for all epsilon and delta, there exists a N(e) such that for all n>N, The prob of being far away from the limit is small (or being close to it is large). To define this our random variable must lie in some metric space so that we can discuss distances. In simpler terms, when we say a random variable converges in probality to some limit (which may be a random vairable), we mean that if you give me any threshold of deviation, I go down far enough in the sequence that the probability of going past that deviation is sufficiently small. Proved using chebyshev/Markov inequality.
'
We apply this is concept to formall state the weak law: Let Sn = . and then The average converges to the expectation. We can eliminate some of these assumptions and still come up with a formal proof. I will prove with second moment bounded but there are many other variations

Strong Law of Large Numbers:

If there is a weak law then there should be a strong law. This one features a different and stronger version of convergence. This is called almost sure convergence (almost everywhere, ...). I will write it symbolically and state the epsilon delta defition. For all epsilon positive, there exists a N(e) > 0 such that for all n>N, events that make the limit far apart have 0 probability (or the ones that make them close is 1). More simply, if you give me a small positive numnber, I can find a point in the sequence where the probability of event being less than that sequence is partically small. Proved using Borel-Cantelli usually.

It may be hard to distinguish between the two but there are differences. In convergence by probability we say that the probability of events that make the difference large is small. In convergence a.s., we say that the difference has no chance of happening after a certain point. Therefore, if something converges a.s. then it must converge in probability.  

The strong law states that the partial sum converges almost surely to its expectation. We need stronger assumptions such as IID and second moment for this. It was provbed by truncation in my course but I am sure there are other ways to prove this. 

Both of these results are remarkable. It is saying that if we keep sampling and compute averages, we will get something like the weighted mean that we formulated earlier. This is for all iid samples no matter their structure. We will see how this is used in my statistics class.

Central Limit Theorem

Characteristic Functions

When the central limit theorem is proved there is usually some discussion on characteristic functions. Most of you may be familiar with moment generating functions and they are very similar. We define a characteristic function because every random variable has one as opposed to a moment generation function. The imaginary gives us more flexibility ?? E[itX]. We can use these functions to generate moments. And if moments all moments of random variable is finite, then it has a unique characteristic funciton representation. 
There are other properties

There is another type of convergence, called convergence in distribution. This is the weeakewst of the three and is the most intuitive. Let Fn be the cdf of the nth random variable Xn. The epsilon delta defintion of this is that for a fixed x and for all epsilon, there exists a N(e) such that for all n>N, fn(x) - F(x) < epsilon. This is just pointwise convergence of afunction that you would typically see in a calculus class. In order to prove this, we can simply take limits of the functions  	

Central Limit Theorem:
The reason characteristic functions was brought out was because since the normal distrution has a unique characteristic function, if we can show pointwise convergence to that function then we have shown that their convergence is in distribution. We know that the mg of the normal is e^t2 then represent the sum of random variables as X1+X2+...+Xn. Then we can show through taylor series expansion that this conges to the stadard normal. I took the mean of these random variables to be 0 and we can do that because we can transform the.

We can also show that the expectation converges by Portmanteau. The version we learned uses the linedeberg0fuller triangulization proof.

The central limit theorem can also be rewritten as root n( sample mean), This basically means that if we scale the difference between the smaple mean and true mean (which we know goes to 0 by the LLN) then we get an interesting distribution. The scale factor of root n is cruicial because other wise, it would just go to 0 by LLN	

This is a crucial result. It gives us a way to approximate large sample distributions. It doesnt say anything about a random variable being distributed normal. Its that the sum goes to a normal. As you look at stats literature, you will see how important and easy to handle the normal distribution is. 

Markov Chains

Markov chains are the first stochastic process that we discussed. The formal definiton of a stochastic process is a sequence of random vairables defined on the same measure space indexed by something like time. So an iid sample can be considered a stochastic process but tht isnt really interesting. the key defining point of a markov chain is that it possesses the markovian property. That the next step on depends on the current step. It is independent of the steps it took to get to the point its at today. 

A good example of a random chain is a random walk. We flip a coin and determine were we will go in the next period. Nothing before is factored into the probability of the next move. When we discuss markov chains we only care about what will happen in the long run. That is what proportion of time will the chain spend ina a certain state. This proportion exists when we have an irreducible and aperied markov chain. I.e. we can get to any state no matter how far along the chain has been running for.

When the state space is not finite, there are times when it is impossible for a chain to return to a state after leaving. We call this a transient markov chain and those do not have a stationary distribution. This make intuitive sense because there is an infitntie amount of time that we will no longer be in that state after we leave so the fraction of time spent there is 0

Strong Markov

We learned about coupling

Martingale

MArtingales came after we learned more about conditional propbability. It was the right transition because in order to understand martingales, one has to be familiar with conditioning. It is another king of stochastic process. The concept of a martingale originates from gambling. It's defining property is that E[], or more simply my expectation for tomorrow based on what i have today is that same as what i have today. Todays information is all I have. And I am not expected to change over time. 

An interesting problem we got is when we saw that a markov chain that is a mg then it has an absorbing state, if it is in finite state space.

We saw the optional stopping time theorem that says that a stopped process has the same expectation as the mg if we can somehow bound the mg or the stopping time. 

We also saw Doobs mg convergence theorem where we see that a if sup of expectation is bounded then we can show that teh mg converges almost surely. 

Poissoin Process:

This may tbe the most useful stochastic process because it is actually used to model things liek call centers. It is a counting process that relates the exponential distribtion and the poisson distrubiton. We can model the number of event that ecur in a time interval as a poissoin distribution; and the time until event hppen can me modelled as an exponential distribution. 

USing the supoerposiiton and __position of the process we can intuiviyl define some propoerties of the poisson and exponential distribution. Max of exponential is a benoulii. given we have n total, the total is multinomial

then this is used as the building blocks of the continuous markov chain
