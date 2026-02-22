## Q1: If a number is even, double it, else keep it as it is.

```python
nums = [1, 2, 3, 4, 5]
result = [i**2 if i%2==0 else i for i in nums]
print(result)
```

## Q2: Square the number if it's on even place else return as it is.

```python
nums = [1, 2, 3, 4, 5]
result = [nums[i]**2 if i%2==0 else nums[i] for i in range(len(nums))]
print(result)
```

## Q3: Label temperatures as "Hot" if > 30 else "Normal".

```python
temps = [25, 32, 28, 40]
result = ["Hot" if i>30 else "Normal" for i in temps]
print(result)
```

## Q4: Replace empty strings with "NA".

```python
data = ["apple", "", "banana", ""]
result = ["NA" if i=="" else i for i in data]
print(result)
```

## Q6:Pass / Fail / Distinction

```python
marks = [35, 78, 92, 40, 55]
result = ["Merit" if i>90 else "Distinction" if i>75 else "pass" if i>40 else "fail" for i in marks]
print(result)
```

## Q7: Replace numbers < 0 with "Invalid".

```python
values = [10, -5, 30, -1]
result = ["Invalid" if i<0 else i for i in values]
print(result)
```

## Q8: Print the extension of the file name

```python
files = ["drawing.dwg", "plan.dxf", "report.pdf", "image.png", "main.py"]
results = [i.split(".")[1] for i in files ]
print(results)
```
## Q9: Print Vowel or Consonant

```python
letters = ["a", "b", "e", "k", "i"]
result = ["Vowels" if i in ["a","e","i","o","u"] else "Consonants" for i in letters]
print(result)
```

## Q10: Add "High-" prefix if value > 50 else "Low-".

```python
scores = [45, 80, 30, 90]
result = [("High-" if i > 50 else "Low-") + str(i) for i in scores]
print(result)
```


## Q11: From a list of numbers, Keep only positive numbers, Square even numbers, Cube odd numbers

```python
nums = [-3, 2, 5, -1, 4]
result = [i**2 if i%2==0 else i**3 for i in nums if i>0]
print(result)
```


## Q12: Multiple looping + flatten 

```python
matrix = [[
    [1, 2, 3],
    [4, 5, 6]
],
[
    [1, 2, 3],
    [4, 5, 6]
]
]

result = [k for i in matrix for j in i for k in j]
result = ["E" if k%2==0 else "O" for i in matrix for j in i for k in j]
print(result)
```


## Q13: Write a program using list comprehension to filter a dictionary and return only those key–value pairs where the value is greater than 50.

```python
scores = {
    "Math": 80,
    "Science": 45,
    "English": 70
}
results = [{key:value} for key,value in scores.items() if value>50]
print(results)
```


## Q14: Write a program using list comprehension to classify each number in a list as Zero, Negative, Positive-Odd, or Positive-Even.

```python
nums = [3, -2, 0, 4, -5, 6,8,0,-8,11,-13,-16]
result = [
    "Zero" if i == 0
    else "Negative" if i < 0
    else "Positive-Odd" if i % 2 != 0
    else "Positive-Even"
    for i in nums
]
result = ["Positive-Odd" if i%2!=0 else "Negative" if i<0 else "Zero" if i==0 else "Positive-Even" if i>0 and i%2==0 else i for i in nums]
print(result)
```


## Q15: Write a program to create a dictionary from two lists using `zip()` and return only those entries where the score is greater than 60 using list comprehension.

```python
names  = ["A", "B", "C", "D"]
scores = [55, 75, 40, 90]

d = {}
for n,s in zip(names,scores):
    # print(n,s)
    d[n]=s
# print (d)

results = [{key:value} for key,value in d.items() if value>60]
print(results)
```



## Q16: Write a program using list comprehension to replace elements at odd indices in a list with `X` while keeping even-indexed elements unchanged.

```python
data = [10, 20, 30, 40, 50]
results = ["X" if i%2!=0 else data[i] for i in range(len(data))]
print(results)
```



## Q17: Write a program using list comprehension to strip spaces, convert to lowercase, and remove empty strings from a list of raw strings.

```python
raw = ["  Data ", "", " PYTHON", "  ", "AI "]
result = [i.strip().lower() for i in raw if i.strip()!='']
print(result)
```

## Q18: Write a program using list comprehension to extract all digits from a string and convert them into integers.

```python
s = "a1b2c3"
results = [int(i) for i in s if i.isdigit()]
print(results)
```

## Q19: Normalize values: None or < 0 → 0, Else divide by 100

```python
values = [100, None, -20, 250]
result = ["0" if i is None or i < 0 else i/100 for i in values]
print(result)
```


## Q20: Create all pairs (x, y) such that x != y.

```python
nums = [1, 2, 3]
results = [(x,y) for x in nums for y in nums if x!=y]
print(results)
```


## Q21: What is a Python one-line solution using list comprehension to generate all possible color-size combinations.

```python
colors = ["red", "blue"]
sizes = ["S", "M", "L"]
# ['red-S', 'red-M', 'red-L', 'blue-S', 'blue-M', 'blue-L']
results = [f"{c}-{s}" for c in colors for s in sizes]
print(results)
```
 
