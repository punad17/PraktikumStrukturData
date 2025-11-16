
# **1. Stack (LIFO — Last In, First Out)**

*Stack adalah struktur data yang elemen terakhir masuk akan menjadi elemen pertama yang keluar.*

## **Membuat Stack**

```python
stack = []
```

**Penjelasan Sintaks:**

* `stack = []` → Membuat struktur stack kosong menggunakan list.

## **Push (Menambah Elemen ke Stack)**

```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack:", stack)
```

**Penjelasan Sintaks:**

* `stack.append('A')` → Menambahkan elemen `'A'` ke dalam stack.
* `stack.append('B')` → Menambahkan elemen `'B'` ke atas stack.
* `stack.append('C')` → Menambah elemen `'C'` di posisi paling atas.
* `print("Stack:", stack)` → Menampilkan seluruh isi stack.

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

**Penjelasan Sintaks:**

* `stack.pop()` → Menghapus dan mengembalikan elemen paling atas.
* `element = ...` → Menyimpan elemen yang di-pop ke variabel `element`.
* `print("Pop:", element)` → Menampilkan elemen yang dihapus.
* `print("Stack:", stack)` → Menunjukkan kondisi stack setelah pop.

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

**Penjelasan Sintaks:**

* `stack[-1]` → Mengambil elemen paling atas tanpa menghapusnya.
* `topElement = ...` → Menyimpan elemen tersebut.
* `print("Peek:", topElement)` → Menampilkan elemen teratas.

**Output:**

```
Peek: B
```

## **Mengecek Apakah Stack Kosong**

```python
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)
```

**Penjelasan Sintaks:**

* `bool(stack)` → Menghasilkan *True* jika stack ada isinya, *False* jika kosong.
* `not bool(stack)` → Membalik nilai, sehingga *True* menandakan stack kosong.
* `isEmpty = ...` → Menyimpan hasil pengecekan.
* `print("isEmpty:", isEmpty)` → Menampilkan status kosong/tidak.

**Output:**

```
isEmpty: False
```

## **Ukuran Stack**

```python
print("Size:", len(stack))
```

**Penjelasan Sintaks:**

* `len(stack)` → Menghitung jumlah elemen di dalam stack.
* `print("Size:", ...)` → Menampilkan jumlah elemen.

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

**Penjelasan Sintaks:**

* `queue = []` → Membuat struktur queue kosong.
## **Enqueue (Menambah Elemen ke Queue)**

```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue:", queue)
```

**Penjelasan Sintaks:**

* `queue.append('A')` → Menambah `'A'` ke belakang antrian.
* `queue.append('B')` → Menambah `'B'` ke urutan berikutnya.
* `queue.append('C')` → Menambah `'C'` sebagai elemen paling baru.
* `print("Queue:", queue)` → Menampilkan isi queue.

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

**Penjelasan Sintaks:**

* `queue.pop(0)` → Menghapus dan mengembalikan elemen paling depan (indeks 0).
* `element = ...` → Menyimpan elemen yang dihapus.
* `print("Dequeue:", element)` → Menampilkan elemen yang keluar.
* `print("Queue:", queue)` → Menampilkan kondisi queue setelah dequeue.

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

**Penjelasan Sintaks:**

* `queue[0]` → Mengambil elemen paling depan tanpa menghapusnya.
* `frontElement = ...` → Menyimpan elemen tersebut.
* `print("Peek:", frontElement)` → Menampilkan elemen terdepan.

**Output:**

```
Peek: B
```
## **Mengecek Apakah Queue Kosong**

```python
isEmpty = not bool(queue)
print("isEmpty:", isEmpty)
```

**Penjelasan Sintaks:**

* `bool(queue)` → Mengecek isi queue.
* `not bool(queue)` → True jika queue kosong.
* `print("isEmpty:", isEmpty)` → Menampilkan hasil pengecekan.

**Output:**

```
isEmpty: False
```
## **Ukuran Queue**

```python
print("Size:", len(queue))
```

**Penjelasan Sintaks:**

* `len(queue)` → Menghitung jumlah elemen queue.
* `print("Size:", ...)` → Menampilkan jumlah elemen.

**Output:**

```
Size: 2
```



