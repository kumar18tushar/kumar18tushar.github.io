---
layout:     post
title:      Chef And Math
date:       2019-03-15 18:29:19
summary:    A dynamic programming + recurssion problem on codechef
categories: Dynamic-Programming
thumbnail: cogs
tags:
 - DP 
 - Codechef
---

This is an interesting problem on codechef [CHEFMATH](https://www.codechef.com/problems/CHEFMATH).
What we need to do is , we'll be given with q queries of the forrm "X K".<br/>
We have to count total number of different ways to create X using K fibonacci numbers.<br/>
We are allowed to use any fibonacci numbers any number of times.<br/>
And order does not matter .. ie. fib[i] + fib[j] is same as fib[j] + fib[i].<br/>

Now to form dp relation:
Let $$DP(x,k,n)$$ be the number of ways to form the sum x using exactly k fibonacci numbers from fib(1),fib(2),…fib(n).<br/>

So, we have two options:
  * Either don't take the nth fib and proceed with (n-1)th one,
  * Either take nth fib and reduces k and x and call from n again.

Then DP can be calculated using the following relation:
$$DP(x,k,n) = DP(x,k,n-1) + DP(x-fib[n],k-1,n)$$

Our answer will be DP(x,k,n).<br/>
Constraint is small. Just with small prunning, the recurssion can pass.<br/>
Prunning : If $$fib(n)*k<x$$ , $$DP(x,k,n) = 0$$<br/><br/> 

**Implementation :** [code](https://ideone.com/qQpz5f)

