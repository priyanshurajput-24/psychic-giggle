## 1. Problem: Given two lists, create a dictionary where one list contains keys and the other contains values.

```python
keys = ["name", "age", "city"]
values = ["Saniya", 25, "Chennai"]
result = dict((zip(keys,values)))
print(result)
```

## 2. Problem: Count the frequency of each character in the given string.

```python
from collections import Counter
s = "banana"
freq = dict(Counter(s))
print(freq)
```

## 3. Problem: Find the key that has the maximum value in the dictionary.

```python
scores = {"math": 85, "science": 92, "english": 88}
key = max(scores, key = scores.get)
value = scores[key]
print(f"{key}:{value}")
```

## 4. Problem: Merge two dictionaries into one.

```python
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}

df = dict1|dict2
print(df)
```

## 5. Problem: Create a new dictionary containing only items with values greater than 50.

```python
marks = {"A": 45, "B": 78, "C": 60, "D": 32}
m = {k:v for k,v in marks.items() if v>=60}
print(m)
```

## 6. Problem: Check whether the key "age" exists in the dictionary.

```python
person = {"name": "Saniya", "city": "Chennai"}
print("Age" in person)
```

## 7. Problem: Find the sum of all values in the dictionary.

```python
data = {"a": 10, "b": 20, "c": 30}
s = sum(data.values())
print(s)
```

## 8. Problem: Create a new dictionary with squared values.

```python
nums = {"a": 2, "b": 3, "c": 4}
s = {k:v**2 for k,v in nums.items()}
print(s)
```

## 9. Problem: Convert the dictionary into a list of (key, value) tuples.

```python
info = {"x": 1, "y": 2}
info = {"x": 1, "y": 2}
s = list(info.items())
print(s)
```

## 10. Problem: Swap keys and values of the dictionary.

```python
data = {"a": 1, "b": 2, "c": 3}
s = {v:k for k,v in data.items()}
print(s)
```

## 11. Problem: Count character frequency without using Counter.

### 1st Sol:

```python
s = "mississippi"
result = {i:s.count(i) for i in set(s)}
print(result)
```

### 2nd Sol:

```python
s = "mississippi"
freq = {}
for ch in s:
    freq[ch] = freq.get(ch, 0) + 1
print(freq)
```

## 12. Problem: Find keys that have duplicate values.

```python
data = {"a": 1, "b": 2, "c": 1, "d": 3}
r = {key for key,values in data.items() if list(data.values()).count(values) > 1}
print(r)
```

## 13. Problem: Sort the dictionary by values in ascending order.

```python
scores = {"math": 90, "english": 70, "science": 85}
r = dict(sorted(scores.items(), key=lambda x: x[1]))
print(r)
```


## 14. Problem: Group words based on their length.

```python
words = ["hi", "hello", "bye", "python"]
r = {word:len(word) for word in words}
print(r)
```

## 15. Problem:  Extract the value 92.

```python
data = {
    "student": {
        "name": "Saniya",
        "marks": {"math": 85, "science": 92}
    }
}
r = data["student"]["name"]
print(r)
```

## Problem: Print the value which is >0

```python
products = [
    {"id": 1, "name": "Laptop"},
    {"id": 2, "name": "Mouse"},
    {"id": 3, "name": "Keyboard"},
]

orders = [
    {"product_id": 1, "quantity": 2},
    {"product_id": 2, "quantity": 0},
    {"product_id": 3, "quantity": 5},
]

s = {p["name"] for p in products for o in orders if p["id"] == o["product_id"] and o["quantity"]>0}
print(s)
```
