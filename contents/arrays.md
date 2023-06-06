<frontmatter>
  title: Arrays
  layout: default.md
  pageNav: 4
  pageNavTitle: "Topics"
</frontmatter>

<br>

# Arrays

Arrays are one of the most fundemental and basic structures in programming, a simple indexed structure of elements, usually integers or strings. It is the most common topic for Leetcode questions, involving around 40% of 

Most Leetcode problems deal with 1 dimensional arrays, and involve some form of manipulation including sorting, searching or indexing of the array.


## Common Array Manipulation Tricks

### Filtering
Returns all elements in a array that return true based on a function

```
python
filter(lambda x: x < 3, arr)
#Returns only numbers that are 3 or greater
```

### Mapping
Manipulates all elements in the array based on a function
```
python

```

### Sorting
Sorting any array can be done with O(nlogn) time with Python's built in sort() function

```


```

Quicksort is a very common type of 


### Binary Search
Binary search is used to search through a monotonic (increasing or decreasing) array for an element in O(logn) time. It is one of the most common types of search and used for many Leetcode array problems.

Implementation of Binary Search can be tricky, need to be wary of the bounds during recursion:

```
python
def binary_search(arr, low, high, x):
 
    # Check base case
    if high >= low:
 
        mid = (high + low) // 2
 
        # If element is present at the middle itself
        if arr[mid] == x:
            return mid
 
        # If element smaller than mid, then it can only be present in left subarray
        elif arr[mid] > x:
            return binary_search(arr, low, mid - 1, x)
 
        # Else the element can only be present in right subarray
        else:
            return binary_search(arr, mid + 1, high, x)
 
    else:
        # Element is not present in the array
        return -1
```


### Sliding Window

A subarray is constantly indexed and shifted through the array. This is usually done with 2 pivots or indexes. 

left, right = 0,0

### Prefix Sum

This is a common technique done in th e