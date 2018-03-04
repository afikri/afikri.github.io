---
layout: post
title: Cyclic Rotation of Array 
tags: [array, java, algorithms]
---

This post is my exercise for codility test. Here is the case, we are given an array A which is zero indexed with N-length. Here is the example. Array has length of 5, and to be rotated 3 times. 
> A = [3,6,4,7,8], R = 3

After three times of rotation, we will get

>A<sub>3</sub> = [4,7,8,3,6]

The solution can be either plucking out first three elements or rotating the array three times.

Let's solve on the first method.
1. Create a temporary array to hold the size of nRotation times where nRotation = N<sub>rotation</sub>-1.
```php 
    int[] firstArray = new int[nRotation];
    System.arraycopy(A, 0, firstArray, 0, firstArray.length);//will give [3,6]
```

2. Hold the rest array from index of n<sub>Rotation</sub> .
```php
    int[] secondArray = new int[A.length-firstArray.length];
    System.arraycopy(A, firstArray.length, secondArray, 0, secondArray.length);	//will give [4,7,8]
```

3. Then join secondArray to firstArray.
```php
    int[] wholeArray = ArrayUtils.addAll(secondArray, firstArray);
```
The whole lines of code is
```php
package com.afikri.learning;

import java.util.Arrays;
import org.apache.commons.lang3.ArrayUtils;

public class CyclicRotation {
    public static int[] rotateArray(int[] A, int nRotation){    
        int[] firstArray = new int[nRotation];
        int[] secondArray = new int[A.length-firstArray.length];

		System.arraycopy(A, 0, firstArray, 0, firstArray.length);
		System.arraycopy(A, firstArray.length, secondArray, 0, secondArray.length);	

		int[] wholeArray = ArrayUtils.addAll(secondArray, firstArray);
		return wholeArray;	
		
   	}

	public static void main(String[] args) {
		int[] A = { 3,6,4,7,8 };			
		int nRotate = 3;
		System.out.println(Arrays.toString(rotateArray(A, nRotate)));
	}
}
```

References<br>
1. [Geeksforgeeks][1].
[1]: https://www.geeksforgeeks.org/array-rotation/
