---
layout:     post
title:      Party Schedule(Spoj)
date:       2018-12-02 1:21:18
summary:    A dynamic programming problem on spoj
categories: Dynamic-Programming
thumbnail: cogs
tags:
 - DP 
 - Spoj
---

This is a famous spoj problem [PARTY](https://www.spoj.com/problems/PARTY/).
Basically, we are given with a number of parties each with their cost and fun values respectively.
We are given with our budget ,say B. We need to select a set of parties such that the total cost doesn't exceed B 
and total fun value is maximized.


Say number of parties, we are given with is P. And our budget is B.We denote cost  of ith party by cost[i]
and fun value by fun[i].

Let  $$DP(i,j)$$  denotes the maximum total fun value with budget i and till party j (0 based indexing).
So our answer will be DP(B,P-1)

Base cases: $$DP(0,j) = 0 , \forall \ j = 0 \ to \ P-1$$

$$DP(i,0) = \begin{cases} 0 &\text{if }cost[0] > i \\ fun[0] &\text{if }cost[0] \leq i \end{cases}$$

Now for  all i=1 to B and j = 1 to p-1 :

\$$DP(i,j) = max(\,DP(i,j-1)\, ,\,fun[j] + DP(i-cost[j], j-1)\,)$$


Hence, our required answer is $$DP(\,B,P-1\,)$$

In order to find the total amount required to obtain the maximum fun , we need to make a similary
function AMT(i,j) and updating it for all i,j. Hence AMT(B,P-1) will give the total amount required.

Link to [code](https://ideone.com/ycs7vH)


