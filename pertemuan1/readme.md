# **1. Stack (LIFO — Last In, First Out)**

*Stack adalah struktur data yang elemen terakhir masuk akan menjadi elemen pertama yang keluar.*

## **Membuat Stack**

```python
stack = []
```

## **Push (Menambah Elemen ke Stack)**

```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack:", stack)
```

**Output:**

```
Stack: ['A', 'B', 'C']
```

## **Pop (Menghapus Elemen Teratas)**

```python
element = stack.pop()
print("Pop:", element)
print("Stack:", stack)
```

**Output:**

```
Pop: C
Stack: ['A', 'B']
```

## **Peek (Melihat Elemen Teratas)**

```python
topElement = stack[-1]
print("Peek:", topElement)
```

**Output:**

```
Peek: B
```


## **Mengecek Apakah Stack Kosong**

```python
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)
```

**Output:**

```
isEmpty: False
```

---

## **Ukuran Stack**

```python
print("Size:", len(stack))
```

**Output:**

```
Size: 2
```

# **2. Queue (FIFO — First In, First Out)**

*Queue adalah struktur data yang elemen pertama masuk akan menjadi elemen pertama yang keluar.*

## **Membuat Queue**

```python
queue = []
```
## **Enqueue (Menambah Elemen ke Queue)**

```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue:", queue)
```

**Output:**

```
Queue: ['A', 'B', 'C']
```
## **Dequeue (Menghapus Elemen Pertama)**

```python
element = queue.pop(0)
print("Dequeue:", element)
print("Queue:", queue)
```

**Output:**

```
Dequeue: A
Queue: ['B', 'C']
```

## **Peek (Melihat Elemen Terdepan)**

```python
frontElement = queue[0]
print("Peek:", frontElement)
```

**Output:**

```
Peek: B
```
## **Mengecek Apakah Queue Kosong**

```python
isEmpty = not bool(queue)
print("isEmpty:", isEmpty)
```

**Output:**

```
isEmpty: False
```

## **Ukuran Queue**

```python
print("Size:", len(queue))
```

**Output:**

```
Size: 2
```

