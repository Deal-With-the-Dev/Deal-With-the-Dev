---
layout: post
title:  "Probability of Solving the Coin Problem"
date:   2023-04-06
categories: math
---

If you choose 3 numbers at random, A, B, and C, what is the chance that C can be expressed as a positive integer combination of the other two? That is there is some m and n where `m*A + n*B = C`.

## The Inspiration

Trying to come up with a simple example of the sort of word problem that we inflict on students first learning algebra, I thought up

> Sam is buying fruit. Apples cost 7 dollars and oranges cost 5 dollars. He buys 42 dollars worth of fruit, how many of each did he buy?

But two things occured to me about this
- the problem is potentially underdetermined, since I didn't name the total number of fruit
- it might be the case that the total is impossible given the prices named

Largely both of these were a result of the expediency of coming up with a basic example, but this implies some interesting questions. What are the chances that I named a valid problem offhand? How does this change as the named prices change? So specifically the new problem is.

> If you choose 3 numbers at random, A, B, and C, what is the chance that C can be expressed as a positive integer combination of the other two? That is there is some m and n where `m*A + n*B = C`.
