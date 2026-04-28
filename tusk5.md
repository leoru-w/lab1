# Задание 5 
Провести замеры алг. и пространственной сожности сортировки
Сортировка вставками

```python
import time
import random
import tracemalloc

def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

def generate_array(n):
    arr = []
    for i in range(n):
        arr.append(random.randint(0, 10000))
    return arr

def measure_time(func, data):
    start = time.perf_counter()
    func(data)
    end = time.perf_counter()
    return end - start

def measure_memory(func, data):
    tracemalloc.start()
    func(data)
    current, maxi = tracemalloc.get_traced_memory()
    tracemalloc.stop()
    return maxi

sizes = [100, 1000, 5000, 10000]


for n in sizes:
    arr =generate_array(n)
    t = measure_time(insertion_sort,arr)
    m = measure_memory(insertion_sort,arr)
    print(n, f"{t:.7f}", m)
```
| n      | t       | m      |
|--------|---------|--------|
| 100    | 0.0001231 | 80   |
| 1000   | 0.0112300 | 140   |
| 5000   | 0.3472799 | 140   |
| 10000  | 1.2331686 | 140  |
