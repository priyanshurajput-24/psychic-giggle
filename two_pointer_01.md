## Q1: Given a sorted array, find two numbers that add up to a target.

```python
nums = [1, 2, 3, 4, 6]
target = 6
Output = [1, 3]
def pair_with_target(nums, target):
    left, right = 0, len(nums) - 1

    while left < right:
        current_sum = nums[left] + nums[right]

        if current_sum == target:
            return [left, right]   # or return values: [nums[left], nums[right]]

        elif current_sum < target:
            left += 1

        else:
            right -= 1

    return [-1, -1]  # no pair found

print(pair_with_target(nums, target))
```


## Q2 : Remove duplicates in-place and return new length.

```python
nums = [1, 1, 2, 2, 3]
Output = 3 
def remove_duplicate(l):
    if not l:
        return 0
    i = 0
    for j in range(1, len(l)):
        if l[j] != l[i]:
            i += 1
            l[i] = l[j]
    return i + 1
print(remove_duplicate(nums))
```



## Q3: Reverse a list of characters using two pointers.

```python
input = ['h','e','l','l','o']
output = ['o','l','l','e','h']
def reverse_list_of_char(l):
    left, right = 0, len(l)-1
    while left < right:
        l[left], l[right] = l[right], l[left]
        left += 1
        right -= 1
    return l
results = reverse_list_of_char(input)
print(results)
```


## Q4: Check if a string is a palindrome.

```python
input = "madam"
def check_palindrome(s):
    left, right = 0, len(s)-1
    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1
    return True
results = check_palindrome(input)
print(results)
```

## Q5: Move all zeros to end while maintaining order.

```python
input = [0,1,0,3,12]
def move_all_zero(l):
    i = 0
    for j in range(len(l)):
        if l[j] != 0:
            l[i] = l[j]
            i += 1
    return l
results = move_all_zero(input)
print(results)
```



## Q6 : Return sorted squares of a sorted array.

```python
nums = [-4,-1,0,3,10]
def sorted_array(l):
    left, right = 0, len(l)-1
    pos = len(l)-1
    res = [0] * (len(l))

    while left < right:
        if abs(l[left]) < abs(l[right]):
            res[pos] = l[right] ** 2
            right -= 1
        else:
            res[pos] = l[left] ** 2
            left += 1
        pos -= 1
    return res
print(sorted_array(nums))  
```



## Q7: Find pair whose sum is closest to target.

```python
```

## Q8: Remove all instances of a value in-place.

```python
nums = [3,2,2,3]
val = 3
def remove_element_inplace(l, e):
    i = 0
    for j in range(len(l)):
        if l[j] != e:
            l[i] = l[j]
            i += 1
    return l
print(remove_element_inplace(nums, val))
```


## Q9: Check if s is subsequence of t.

```python
s = "abc"
t = "ahbgdc"
def isSubsequence(s: str, t: str) -> bool:
    i, j = 0, 0  # i for s, j for t

    while i < len(s) and j < len(t):
        if s[i] == t[j]:
            i += 1  # move in s only when chars match
        j += 1      # always move in t

    return i == len(s)
print(isSubsequence(s,t))
```  




## Q10: Find max water between two lines.

```python
input = [1,8,6,2,5,4,8,3,7]
output = 49
def max_area(height):
     left, right = 0, len(height) - 1
     max_area = 0

     while left < right:
         h = min(height[left], height[right])
         w = right - left
         max_area = max(max_area, h * w)
 
         if height[left] < height[right]:
             left += 1
         else:
             right -= 1
         print(f"left:{left}, right:{right}, h:{h}, w:{w}, h*w: {h*w}, max_area:{max_area}")
 
     return max_area
print(max_area(input))
```  




## Q11: After rain calculate total water stored.

```python
input = [0,1,0,2,1,0,1,3,2,1,2,1]
output = 6
def trap(height):
    left, right = 0, len(height) - 1
    left_max = right_max = 0
    water = 0

    while left < right:
        if height[left] < height[right]:
            if height[left] >= left_max:
                left_max = height[left]
            else:
                water += left_max - height[left]
            left += 1
        else:
            if height[right] >= right_max:
                right_max = height[right]
            else:
                water += right_max - height[right]
            right -= 1

    return water
print(trap(input))
```  

