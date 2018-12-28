---
layout:     post
title:      Gargari And Bishop
date:       2018-12-26 15:06
summary:    Greedy and DP
categories: Greedy
thumbnail: cogs
tags:
 - Greedy
 - intuition
 - Codeoforces
 - DP
---

Today , I solved [this](https://codeforces.com/contest/463/problem/C) problem from Codeforces round 264 (div2).
It took me quite a while to figure out the logic.

The key idea behind this was that two Bishops placed on a chess board will not attack a common cell (I repeat , a common cell) 
if and only if <ins>the sum of the row number and column number of one Bishop is odd and that of the other is even, respectively</ins>. If both will be odd or even together , there will be a common cell attacked by both.
In simple words, one Bishop should be at white cell and other should be at black cell or vice-versa. <ins>Two cells with sums odd and even respectively, ensures that two cells are different ie. one is black and other white</ins>.

That is, if Bishop 1 is at cell (r1,c1) and Bishop 2 is at cell (r2, c2)  , then one of the [ (r1+c1) , (r2+c2) ] should be odd 
and the other should be even.


Implementation was simple.

1. Use dynamic programming to fill the matrix that will give us the total number of points collected by a Bishop if placed at any cell    (r,c). That is , for any cell (i , j) , dp[ i ][ j ] equals total points earned by bishop kept at cell (i , j).

2. Find two cells such that the sum of indexes of one is odd and other even and the total points collected by placing the two Bishops at those  two indexes is maximised.


**Implementation :** [here](https://ideone.com/RtyF3o)
