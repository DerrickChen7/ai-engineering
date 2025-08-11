# Python Data Structures Cheat Sheet

## Main Built-in Data Types

- **int**: Integer numbers (e.g., `5`, `-3`)
- **float**: Floating-point numbers (e.g., `3.14`, `-0.5`)
- **str**: String/text (e.g., `"hello"`)
- **bool**: Boolean (`True` or `False`)
- **list**: Ordered, mutable sequence (e.g., `[1, 2, 3]`)
- **tuple**: Ordered, immutable sequence (e.g., `(1, 2, 3)`)
- **dict**: Dictionary, key-value pairs (e.g., `{"a": 1, "b": 2}`)
- **set**: Unordered collection of unique elements (e.g., `{1, 2, 3}`)
- **NoneType**: Special type for `None`

---

## List

```python
# Create a 2D array with m rows and n columns
m = 3
n = 4
two_d_array = [[5] * n for _ in range(m)]

# Append
my_list = [1, 2, 3]
my_list.append(4)

# Loop
numbers = [1, 2, 3, 4]
for number in numbers:
    print(number)

# Loop with index
for index, number in enumerate(numbers):
    print(index, number)

# Reverse options
for number in reversed(numbers):
    print(number)

for number in numbers[::-1]:
    print(number)

for i in range(len(numbers)-1, -1, -1):
    print(numbers[i])

# Insert at position
numbers.insert(0, 12)  # [12, 1, 2, 3, 4]

# Sort
numbers.sort()  # Ascending
numbers.sort(reverse=True)  # Descending
numbers = sorted(numbers)  # Returns new sorted list

# Extend
original_list = [1, 2, 3]
additional_elements = [4, 5, 6]
original_list.extend(additional_elements)
print(original_list)  # [1, 2, 3, 4, 5, 6]
```

---

## Stack Example

```python
# Stack: Last In First Out (LIFO)
stack = []
stack.append("hello")
stack.append("world")
stack.pop()  # Removes and returns the top item
len(stack)   # Size
stack[-1]    # Last element
```

---

## Queue Example

```python
# Queue: First In First Out (FIFO)
# Option 1: Using a list
queue = []
queue.append("hello")
queue.append("world")
queue.pop(0)  # Remove from the front
len(queue)
queue[-1]

# Option 2: Using collections.deque
from collections import deque
queue = deque()
queue.append("hello")
queue.append("world")
queue.popleft()
len(queue)
queue[-1]
```

---

## Map/Dictionary

```python
# Default map
example_map = {}
example_map["test"] = "helloworld"
example_map["test"]  # Error if key not exists
example_map.get("test")  # None if key not exists

# Get with default
default_value = "default"
example_map.get("test2", default_value)

# Check key
if "test" in example_map:
    print("exists!")

# Loop
for key in example_map:
    print(example_map[key])

# Keys, values, items
example_map.keys()
example_map.values()
example_map.items()

# Delete
del example_map["test"]
example_map.pop("test")

# Compare dicts
example_map1 = {"a": 1, "b": 2}
example_map2 = {"b": 2, "a": 1}
example_map1 == example_map2  # True

# defaultdict for automatic default values
from collections import defaultdict
words = ["apple", "banana", "apricot", "blueberry", "cherry"]
grouped = defaultdict(list)
for word in words:
    first_letter = word[0]
    grouped[first_letter].append(word)
print(grouped)
```

---

## Set

```python
test_set = set()
test_set2 = {"apple", "banana", "cherry"}
test_set.add("helloworld")

if "test" in test_set:
    print("exists!")

len(test_set)

# Remove (raises error if not exists)
test_set.remove("test")

# Intersection
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
z = x.intersection(y)
```

---

## Heap / PriorityQueue

```python
import heapq

heap = [5, 3, 8, 1]
heapq.heapify(heap)
heapq.heappush(heap, 2)
smallest = heapq.heappop(heap)  # returns 1
min_element = heap[0]  # returns 2
print(heap)  # Heap structure is maintained
```

- For tuples, heapify arranges by the first element of each tuple.

---

## String

```python
# Split
txt = "welcome to the jungle"
x = txt.split()
print(x)

# Search
sentence = 'hello'
result = sentence.index('hel')
print(result)  # 0

# Check letters or numbers
a.isalpha() or a.isdigit()
```

---

## Tuple

```python
my_tuple = (1, 2, 3)
print(my_tuple[0])

# Single element tuple
single_element_tuple = (1,)

# Packing and unpacking
my_tuple = (1, 2, 3)
a, b, c = my_tuple
print(a, b, c)

# Index and count
my_tuple = (1, 2, 3, 2)
print(my_tuple.index(2))  # 1
print(my_tuple.count(2))  # 2
```

---

## Character <-> Integer

```python
chr(97)   # 'a'
ord('a')  # 97
```

---

## Max and Min Number

```python
float('inf')    # positive infinity
float('-inf')   # negative infinity
```

---

## Random Integer

```python
import random
print(random.randint(3, 9))  # 3 to 9 inclusive
```

---

## String Case

```python