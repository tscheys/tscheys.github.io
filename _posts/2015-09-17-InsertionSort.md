---
layout: post
title: A verbose walkthrough of the insertion sort algorithm
---
##Introduction

[**InsertionSort**](https://en.wikipedia.org/wiki/Insertion_sort) is a simple sorting algorithm that builds a sorted list of numbers one value at a time. It iterates through the list of values, while growing the sorted portion of the array behind the current value. For every value it looks at the sorted portion of the array, and swaps values until the current value is correctly placed in the sorted portion. 

**Important notes**:

1.  There is only one focal object: the input list.
2.  We do not copy over to a new, sorted array.
3.  It does not alter the position of equal values (this principle is referred to as a *stable sort*)
4.  We will sort in *ascending* order. So in our example [3,2,1,3,8] the first three will always be put before the second three after the insertion sort happened.

##Step by step explanation of the algorithm

-  [3,2,1,3,8] Our input
-  [1,2,3,3,8] Desired Output
-  [**3**,2,1,3,8] Iteration one
-  [*3*,**2**,1,3,8] Iteration two 
  -  [3,**2**] Inside iteration 2
  -  [**2**,3] Swap the values
  -  Stop
-  [*2*,*3*,**1**,3,8] Iteration three
  -  [*3*,**1**] Inside iteration three
  -  [**1**,3] Swap the values
  -  [*2*,**1**,3,3,8] Inside iteration
  -  [*2*,**1**] Inside iteration three
  -  [**1**,2] Swap the values
-  [*1*,*2*,*3*,**3**,8] Iteration 4
-  [*1*,*2*,*3*,*3*,**8**] Iteration 5
  

##Walkthrough

The basic idea here is to look behind us, to the previous values, which are already sorted and see where our current iterator value belongs. 

###[3,2,1,3,8] Iteration one

First value is 3, we look behind us: Since this is the first element of the array we can not compare it to previous values. Therefore this iteration stops here and we move one value to the right. 

###[3,2,1,3,8]
So we move on to the next value which is 2
We look backwards and we ask ourselves the focal question: is this value (2) larger than the one just in front of it (3)? Remember that we are sorting in ascending order. Okay what should we do now? The simplest way to do this is to a swap. we swap 3 and 2. [3,2] therefore becomes [2,3] in the list and now we get. The array is now [2,3,1,3,8] (blue is the sorted part of the array). Great, our two first elements in the array are now sorted!

###[2,3,1,3,8] 
Let’s iterate to the value 1. let’s look backwards and ask ourselves the question one previous value at a time: is our current value (1) smaller than the previous one? In this case 1 is indeed smaller than 3, so let’s swap thos 2 values:
[3,1] becomes [1,3] 

###[2,1,3,3,8]
As you can see our array is not sorted yet. To make our insertion sort really work we must keep on comparing and swapping our current value (1) until it is in the right place of the sorted partition of the array. 

>The essantial operation can be summarized as follows: Keep swapping our current value with the previous value while it is not larger than that previous value.

This means we have to compare it to the value in front of it, which is 2. Sure enough 1 is not larger than 2, so we can swp these two.[2,1] becomes [1,2].

###[1,2,3,3,8] 
The following steps keep on iterating until the end of the array, but we can clearly see the last two values in the list will not change. 

###[1,2,3,3,8]
Therefore our work is done! 

Important to note here is that the *stable sort* principle applies here. This principle says that two 3’s in our example will not be swapped since 3 > 3 will evaluate to false.

I will repeat the essential part of this algorithm: 
>The essantial operation can be summarized as follows: Keep swapping our current value with the previous value while it is not larger than that previous value.

For those of you that want to turn this algorithm into code, **while** is the word you want to remember here.

##Pseudocode 

###Swap every time 
for each value in the list at a certain index i, starting at index 1
  while(list[i - 1] > list[i])
    var current = list[i]
    list[i] = list[i - 1]
    list[i - 1] = current


###Swap only once 
for each value in the list at a certain index i, starting at index 1
  while(list[i - 1] > value)
    list[i] = list[i - 1]
    i--
  array[i] = value (*)

(*)This while loop will stop when our current value is not smaller than the previous value, thus is in the right place.

If you are curious about a code example, I have also included a javascript version of the above pseudocode snippets: [gist](https://gist.github.com/tscheys/54e5fca6dd92f5dd8c57)

##Conclusion

When to use this algorithm: if you want to sort small data sets. When the list is small, it is even more efficient than quicksort!
Space complexity: O(1)
Time complexity: O(n2)
