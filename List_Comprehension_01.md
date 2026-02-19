## Q1: If a number is even, double it, else keep it as it is.

```python
nums = [1, 2, 3, 4, 5]
result = [i**2 if i%2==0 else i for i in nums]
print(result)
```

## Q2: 

```python
nums = [1, 2, 3, 4, 5]
result = [nums[i] if i%2==0 else nums[i] for i in range(len(nums))]
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



