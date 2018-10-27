---
layout:     post
title:      Tripple Fat Ladies(Spoj)
date:       2018-10-03 12:32:18
summary:    A number theory problem on spoj
categories: Number theory, Observation
thumbnail: Number theory
tags:
 - Number theory 
 - Spoj
 - Maths
---

This is a famous spoj problem [EIGHTS](https://www.spoj.com/problems/EIGHTS/)
Basically, we need to find Kth number whose cube ends in "888".

Let’s start by assuming the number to be (10∗n+2) .
2 at the end because it will give us an 8 when cubed. We need to find minimum n that satisfy the given condition.
On cubing , we get :
(10∗n+2)3=1000∗n3+600∗n2+120∗n+8
Unit’s digit is already an 8, so we’ll not think upon that . Discard it and divide the remaining number by 10.
We’re left with 100∗n3+60∗n2+12∗n. Now this has to end in 88.Actually, 60∗n2+12∗n has to end in 88 because 100∗n3 will always end with at least two zeroes.
For 12∗n to end with an 8 , n should be ending with 4 or 9. n can be 4,9,14,19......
We need to select n from above in such a way that 60∗n2+12∗n ends with 88.

60∗(4)2+12∗(4)=1008
60∗(9)2+12∗(9)=4968
60∗(14)2+12∗(14)=11928
60∗(19)2+12∗(19)=21888

So the desired value of n is 19. And the first number whose cube ends with “888” is (10∗19+2) which is 192.
To find next number , let it be (192+m).
(192+m)3=(192)3+k(m)
k will be some expression in m. Since 1923 ends in “888”, so we need to figure out the least value of m, so thatk(m) ends with “000”. On imposing this condition and some pen paper work gives,m=250.

Hence the next number is(192+250)and the whole sequence is an AP with common difference 250. So, the kth number of the series is 
192+(k−1)250.

Further reading [link](http://qr.ae/TUGHty)

Jekyll is a tool for transforming your plain text into static websites and
blogs. It is simple, static, and blog-aware. Jekyll uses the
[Liquid](http://docs.shopify.com/themes/liquid-basics) templating
language and has builtin [Markdown](http://daringfireball.net/projects/markdown/)
and [Textile](http://en.wikipedia.org/wiki/Textile_(markup_language)) support.

It also ties in nicely to [Github Pages](https://pages.github.com/).

Learn more about Jekyll on their [website](http://jekyllrb.com/).
