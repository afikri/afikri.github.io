---
layout: post
title: Cyclic Rotation of Array 
tags: [array, java, algorithms]
---

This post is my exercise for codility test. Here is the case, we are given an array A which is zero indexed with N-length. Here is the example. Array has length of 5, and to be rotated 3 times. 
> A = [3,6,4,7,8], R = 3

After three times of rotation, we will get

>A3 = [4,7,8,3,6]

The solution can be either plucking out first three elements or rotating the array three times.

Let's solve on the first method.
1. Create a temporary array to hold the size of N = K-1 array.
`This is a line of code
`
2. Shift the array from index of k-1 to the left.
`This is a line of code
`
3. Append the temporary array to the shifted one.
`This is a line of code
`
The steps need to be taken are

And the second method is


References<br>
1. Geeksforgeeks[1] 
[1]: https://www.geeksforgeeks.org/array-rotation/
