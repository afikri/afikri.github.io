---
layout: post
title: (Time Complexity) Frog Jump
tags: [time complexity, java, algorithms]
---

```ruby
public class FrogJmp{
	public static int solution(int x, int y, int distance){
		int diffDistance = y - x;
		if(diffDistance%distance == 0) 
			return diffDistance/distance;
		else
			return diffDistance/distance + 1;
	}
	
	public static void main(String[] args){
		System.out.println("#Jump must made:"+solution(10,110,30));
	}	
}
```
