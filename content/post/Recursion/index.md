---
title: "Recursion"
subtitle: Implementing recursion and comparing it with iterative approaches
summary:  Implementing recursion and comparing it with iterative approaches
showDate: false
featured: True
draft: false
tags: ["python","code", "recursion"]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ""
  focal_point: ""
---
<sub>25 10 2020</sub>

Three simple iterative functions gcd(a,b), reverse(lst) and is_pal(string) converted into recursive functions using an auxilary function.


```python
def gcd(a, b):
    """ Determines greatest common divisor of two integers.
    
    Input : two integers a and b such that not a==b==0
    Output: greatest common divisor of a and b
    
    For example:
    >>> gcd(0, 4)
    4
    >>> gcd(10, 0)
    10
    >>> gcd(18, 27)
    9
    >>> gcd(21, 13)
    1
    """
    # implementation
    # x = max(a,b)
    # if a == 0:
    #     return b
    # elif b == 0:
    #     return a

    # while x >= 0:
    #     if a % x == 0 and b % x == 0:
    #         return x
    #     x -= 1

    # implement recursion solution

    return gcd_recursion(a, b, max(a,b))

# auxilary function
def gcd_recursion(a, b, divisor):
    if a == 0:
        return b
    elif b == 0:
        return a

    # base case (stopping point for the recursion)
    if a % divisor == 0 and b % divisor == 0:
        return divisor

    return gcd_recursion(a, b, divisor - 1) # calls itself and divisor gets closer to the base case

    
def reverse(lst):
    """ Computes reverse of input sequence.
    
    Input : any list (lst)
    Output: reverse of lst
    
    For example:
    >>> reverse([1, 2, 3, 4])
    [4, 3, 2, 1]
    >>> reverse([10, 11, 12, 13, 14])
    [14, 13, 12, 11, 10]
    >>> reverse([1])
    [1]
    >>> reverse([])
    []
    """
    
    # iterative solution
    # reversedLst = []
    # for _ in range(len(lst)):
    #     reversedLst.append(lst.pop())
    # return reversedLst

    reversedLst = []
    return recursive_reverse(lst, reversedLst)

def recursive_reverse(lst, reversedLst):
    # base case
    if lst == []:
        return reversedLst

    reversedLst.append(lst.pop())

    return recursive_reverse(lst, reversedLst)


def is_pal(string):
    """Checks whether string is palindrome.
    
    Input : any string
    Output: True if string==string[::-1]
    
    For example:
    >>> is_pal('aa')
    True
    >>> is_pal('aabb')
    False
    >>> is_pal('aba')
    True
    """
    
    ### slicing
    # if string[::-1] == string:
    #     return True
    # return False

    ### iterative solution
    # reversedString = ""
    # for _ in range(len(string)):
    #     reversedString += string[-1]
    
    # if string == reversedString:
    #     return True

    # return False

    ### recursive solution
    reversedString = ""
    reducedString = string # last element on this string is going to be reduced in the auxilary function
    return recursive_is_pal(string, reversedString, reducedString)


def recursive_is_pal(string, reversedString, reducedString):
    if reducedString == "" and reversedString == string:
        return True
    elif reducedString == "" and reversedString != string:
        return False

    reversedString += reducedString[-1]
    reducedString = reducedString[:-1] # everything except last element

    return recursive_is_pal(string, reversedString, reducedString)
```

