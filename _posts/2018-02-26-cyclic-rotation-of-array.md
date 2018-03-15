---
layout: post
title: Cyclic Rotation of Array 
tags: [array, java, algorithms]
---
This post is my exercise for codility test. The problem will be solved by using Java, since I am good at it ;)
Here is the case, we are given an array A which is zero indexed with N-length. Here is the example. Array has length of 5, and to be rotated 3 times. 
> A = [3,6,4,7,8], R = 3

After three times of rotation, we will get

>A<sub>3</sub> = [7,8,3,6,4]

The solution can be either plucking out last three elements and put them in the front(lower index sequentially) or rotating the array three times.

Let's solve on the first method.<br>
#1. Create a temporary array to hold the size of A.length-nRotation times. Meaning that we want to have [3,6,4]

```ruby    
    int[] firstArray = new int[A.length-nRotation];	
    System.arraycopy(A, 0, firstArray, 0, firstArray.length);//will give [3,6,4]
```

#2. Hold the rest array from index of n<sub>Rotation</sub>.

```ruby
    int[] secondArray = new int[nRotation];
    System.arraycopy(A, firstArray.length, secondArray, 0, secondArray.length);	//will give [7,8]
    
```

#3. Then join secondArray to firstArray.

```ruby
    int[] wholeArray = ArrayUtils.addAll(secondArray, firstArray);
```
The whole lines of code is
```ruby

	package com.afikri.learning;

	import java.util.Arrays;
	import org.apache.commons.lang3.ArrayUtils;

	public class CyclicRotation {
	    public static int[] rotateArray(int[] A, int nRotation){    
		int[] firstArray = new int[A.length-nRotation];	
		int[] secondArray = new int[nRotation];
		
		System.arraycopy(A, 0, firstArray, 0, firstArray.length);
		System.arraycopy(A, firstArray.length, secondArray, 0, secondArray.length);	
		
		int[] wholeArray = ArrayUtils.addAll(secondArray, firstArray);
		return wholeArray;
	}

	     public static void main(String[] args) {
		int[] A = {3, 8, 9, 7, 6};		
		int nRotate = 3;
		System.out.println(Arrays.toString(rotateArray(A, nRotate)));
		//will produce [9, 7, 6, 3, 8]
	     }
	}
```
The time complexity is O(n) and the auxillary space is O(d)

References<br>
1. [Geeksforgeeks](https://www.geeksforgeeks.org/array-rotation/)
