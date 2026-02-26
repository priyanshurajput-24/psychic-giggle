## Q1: Flatten a 2D List

```python
matrix = [[1, 2, 3], [4, 5], [6, 7, 8]]
result = [j for i in matrix for j in i]
print(result)
```

## Q2: Extract only job names where `status == success`.

```python
jobs = [
    {"name": "job1", "status": "success"},
    {"name": "job2", "status": "failed"},
    {"name": "job3", "status": "success"},
]

result = [i["name"] for i in jobs if i['status']=="success"]
result = [k[1] for k,v in [i.items() for i in jobs] if v[1]=="success"]
print(result)
```



## Q3: Create a list of filenames where, extension is “dwg” or “dxf”, size > 500

```python
data = [
    {"file": "a.dwg", "size": 1200},
    {"file": "b.dxf", "size": 300},
    {"file": "c.pdf", "size": 2000},
]
results = [k[1] for k,v in [i.items() for i in data] if k[1].split('.')[1] in ['dwg', 'dxf'] and v[1] > 500]
print(results)
```


## Q4: Create a list of unique lowercase names using list comprehension (order preserved).

```python
names = ["alice", "bob", "Alice", "BOB", "charlie"]
result = list(dict.fromkeys(name.strip().lower() for name in names))
print(result)
```
* We can't use set here as we have to preserve the order.
* Python 3.7+, `dictionaries` preserve insertion order.
* `Set` does not preserve the order.



## Q5: Write a program to Return numbers that are greater than the next element.

```python
nums = [10, 5, 8, 20, 3]
results = [nums[i] for i in range(len(nums)-1) if nums[i] > nums[i+1]]
results = [a for a,b in zip(nums, nums[1:]) if a > b]
print(results) # [10, 20]
```



## Q6: Sliding Window Logic: Create list of pairwise sums.

```python
nums = [10, 20, 30, 40, 50]
results = [k+v for k,v in zip(nums, nums[1:])] 
results = [a+b+c for a,b,c in zip(nums, nums[1:], nums[2:])]
print(results)  # [30, 50, 70, 90].  # [60, 90, 120]
```



## Q7: Write a program to return product names where `quantity > 0`.

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
```

### 1st Solution

```python 
part_1 = [k[1] for k,v in [i.items() for i in orders] if v[1]>0] # Get the id first. 
result = [i['name'] for i in products if i['id'] in [k[1] for k,v in [i.items() for i in orders] if v[1]>0]]
print(result) # ["Laptop", "Keyboard"]
```

### 2st Solution

```python
from collections import defaultdict

qty = defaultdict(int)
for o in orders:
    qty[o["product_id"]] += o["quantity"]

result = [p["name"] for p in products if qty[p["id"]] > 0]

print(result)
```

## Q8: Write a program to extract the main and anti-diagonal.

```python
matrix = [
    [5, 1, 9],
    [2, 8, 3],
    [4, 6, 7]
]
n = 3 # n is the dimension of matrix
r = [matrix[i][i] for i in range(len(matrix))]
s = [matrix[i][n-1-i] for i in range(len(matrix))]
print(r)
print(s)
```

* `(i, i) `        - The main diagonal
* `(i, n - 1 - i)` - The anti-diagonal
* For anti-diagonal in an `n × n` matrix:
    - `Row index + Column index = n - 1`



## Q9: Return unique filenames that, end with `.dwg` and preserve order.

```python
data = [
    {"batch": 1, "files": ["a.dwg", "b.dxf", "c.pdf"]},
    {"batch": 2, "files": ["d.dwg", "e.pdf"]},
    {"batch": 3, "files": ["f.dxf", "g.dwg"]},
]
```  
### 1st solution

```python 
result = [c for p in [v[1] for k,v in [i.items() for i in data]] for c in p if c.split('.')[1] == 'dwg']  # This solution does not preserve order.
```

### 2st solution

```python 
result = list(dict.fromkeys(
    f
    for batch in data
    for f in batch["files"]
    if f.endswith(".dwg")
))
```

### 3st solution

```python
seen = set()
result = []

for batch in data:
    for filename in batch["files"]:
        if filename.endswith(".dwg") and filename not in seen:
            seen.add(filename)
            result.append(filename)

print(result)
```

