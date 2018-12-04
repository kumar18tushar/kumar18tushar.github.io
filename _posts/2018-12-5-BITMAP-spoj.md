---
layout:     post
title:      Bitmap(Spoj)
date:       2018-12-02 1:21:18
summary:    A bfs problem on spoj
categories: BFS
thumbnail: cogs
tags:
 - multisource BFS 
 - Spoj
---

This is a famous spoj problem [BITMAP](https://www.spoj.com/problems/BITMAP/).
Basically, we are given with an n x m matrix of 0 and 1.
We need to find the distance of each cell from the nearest cell containing 1.

Say number of row is n  and number of column id m. And our matrix is mat . 

$$1 <= n <= 182 \\ 1 <= m <= 182$$

The naive approach to solve this problem is to apply a breadth-first search from each node and stop whenever the 1st '1' is found.
For each node, we'll get its distance from nearest '1'.
This is approach is correct but not fast enough to pass the time constraint.

A better approach to solve this problem is to use multisource-bfs technique.
Let us say the cells which have 1's in them are source and rest as vertices.

Explanation: 
The C++ implementation uses a set of pairs (distance from the source, (row,col) ) sorted according to the distance from the source.
Initially, we push all the sources into the set with distance = 0, and the rest of the vertices with distance = infinity. 
On each step, we will go to the vertex with minimum distance(d) from source, i.e, the first element of the set 
(the source itself in the first step with distance = 0). 
We go through all it’s adjacent reachable vertices and if the distance of any vertex is > d + 1 we replace its entry in the set with the new distance. 
Then we remove the current vertex from the set. We continue this until the set is empty.
The idea is there cannot be a shorter path to the vertex at the front of the set than the current one since any other path will be a sum of a longer path (>= it’s length) and a non-negative path length (unless we are considering negative edges).

Since all the sources have a distance = 0, in the beginning, the adjacent non-source vertices will get a distance = 1. All vertices will get distance = distance from their nearest source.

Implementation : [code](https://ideone.com/VsBLYx)
