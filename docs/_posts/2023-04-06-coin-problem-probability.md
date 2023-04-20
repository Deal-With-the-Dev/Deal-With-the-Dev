---
layout: post
title:  "Probability of Solving the Coin Problem"
date:   2023-04-06
categories: math
---

Update: it appears this problem is [rather more complicated](https://math.stackexchange.com/questions/4674752/probability-that-2-random-numbers-can-express-another-random-number-as-positive)

If you choose 3 numbers at random, A, B, and C, what is the chance that C can be expressed as a positive integer combination of the other two? That is there is some m and n where `m*A + n*B = C`.

## The Inspiration

Trying to come up with a simple example of the sort of word problem that we inflict on students first learning algebra, I thought up

> Sam is buying fruit. Apples cost 7 dollars and oranges cost 5 dollars. He buys 42 dollars worth of fruit, how many of each did he buy?

But two things occurred to me about this
- the problem is potentially under-determined, since I didn't name the total number of fruit
- it might be the case that the total is impossible given the prices named

Largely both of these were a result of the expediency of coming up with a basic example, but this implies some interesting questions. What are the chances that I named a valid problem offhand? How does this change as the named prices change? So specifically the new problem is.

> If you choose 3 numbers at random, A, B, and C, what is the chance that C can be expressed as a positive integer combination of the other two? That is there is some m and n where `m*A + n*B = C`.

## The Infinite Case

Which is also an indeterminate sort of question, almost all questions of probability are. You cannot really select a natural number uniformly from all natural numbers. The chance of picking any particular number cannot be higher than 0, meaning that it is [almost surely](https://en.wikipedia.org/wiki/Almost_surely) not going to be chosen. 

However I still think we can meaningfully understand the spirit of the question by looking at some extreme cases. This problem is almost exactly the same as the [Coin Problem](https://en.wikipedia.org/wiki/Coin_problem), which states that given two coprime numbers, you can use them to sum up to any number greater than `AB - A - B`. Meaning that there are an infinite number of valid values for C, so we conclude.

> If A and B have a gcd of 1, then it is almost surely a valid problem

However, if A and B aren't coprime then there will be numbers which they can't make. An obvious case is that if A and B are both even, then any odd number for C will produce an invalid problem. In general if A and B have gcd x, then only multiples of x can be made. This means that only `1/x` of all numbers will possibly be valid. Considering that if you divide A, B, and C by x you end up with the coin problem, this means that of the C which are multiples of x, an infinite number of them will be solvable. 

> If A and B have a gcd of x, then there is only a `1/x` chance

We can make these approximations since we're looking at the asymptotic case, where the finite number (measure 0 that is) amount of exceptions don't add up to anything. Using this the answer becomes that the probability of choosing a valid fruit price, `P_f(A,B)` is based on the sum of the chances of getting a particular gcd from two numbers.

$$ P_f(A,B) = \sum_{k=1}^\infty P(gcd(A,B) = k) / k $$

Initially I suspected this would tend towards 100% as well, however the chance that two random numbers are coprime is [only about 61%](https://en.wikipedia.org/wiki/Coprime_integers#Probability_of_coprimality). Which gets us the first term of our sum. But what is the probability the the gcd of A and B is 2?

Stack exchange has an [answer on this](https://math.stackexchange.com/questions/39665/given-2-randomly-chosen-integers-x-y-what-is-pk-gcdx-y), which, perhaps ironically, turns out to be 

$$ \frac{6}{k^2 \pi^2} $$

This means that for our purposes

$$ P_f(A,B) = \sum_{k=1}^\infty \frac{6}{k^2 \pi^2} \frac{1}{k} = \frac{6}{\pi^2} \sum_{k=1}^\infty \frac{1}{k^3} $$

$$ \frac{\zeta(3)}{\zeta(2)} \approx 0.73 $$

