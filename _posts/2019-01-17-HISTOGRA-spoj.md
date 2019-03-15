---
layout:     post
title:      Largest Rectangle in a Histogram
date:       2019-01-17 19:58:18
summary:    A Divide and Conquer problem
categories: Divide_And_Conquer
thumbnail: cogs
tags:
 - Divide and Conquer
 - Range Querry
 - Spoj
---

Today, I solved this problem [link](https://www.spoj.com/problems/HISTOGRA/) from Spoj.
We are given with a histogram and we need to find the area of the largest rectangle formed

![Thumper](https://i.imgur.com/u3BjujO.jpg)



# Approach:

The idea is to find the minimum value in the given array. 
Once we have index of the minimum value, the max area is maximum of following three values:
  * Maximum area in left side of minimum value (Not including the min value)
  * Maximum area in right side of minimum value (Not including the min value)
  * Number of bars multiplied by minimum value.<br/><br/><br/>

  
  
# Implementation:

* The main requirement is to find the index of the minimum element in the subinterval for each subproblem.
  To find this efficiently , we build a range-minimum segment tree and querry.
* Next , we build a divide and conquer recursive function which returns the answer for each subproblem.<br/><br/>



**Link to code:** [here](https://ideone.com/FWCNWt)


