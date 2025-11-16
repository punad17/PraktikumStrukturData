# **1. Stack (LIFO — Last In, First Out)**

Stack adalah struktur data yang cara kerjanya: *yang terakhir dimasukin, itu yang pertama keluar*. Mirip numpuk piring.

## **Membuat Stack**

```python
stack = []
```

**Penjelasan**

Baris ini buat bikin wadah stack kosong.
Ibaratnya kita baru nyiapin tempat buat naruh data.

## **Push (Menambah Elemen ke Stack)**

```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack:", stack)
```

**Penjelasan**

`append()` itu buat menaruh elemen ke atas tumpukan.
'A', 'B', dan 'C' dimasukin satu per satu ke stack.
`print()` cuma buat nunjukkin isi stack sekarang.

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

**Penjelasan**

`pop()` ngambil elemen paling atas lalu ngapusnya dari stack.
Nilai yang di-pop disimpan ke variabel `element`.
`print()` buat lihat apa yang diambil dan sisa stack.

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

**Penjelasan**

`stack[-1]` itu cara lihat elemen paling atas tanpa ngapus.
Jadi cuma intip aja, tidak mengubah isi stack.

**Output:**

```
Peek: B
```
## **Mengecek Apakah Stack Kosong**

```python
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)
```

**Penjelasan**

`bool(stack)` bakal `True` kalau stack ada isinya.
`not bool(stack)` jadi `True` kalau stack kosong.
Ini cara simpel buat ngecek apakah datanya masih ada atau tidak.

**Output:**

```
isEmpty: False
```
## **Ukuran Stack**

```python
print("Size:", len(stack))
```

**Penjelasan**

`len(stack)` menghitung berapa banyak elemen di stack.
Intinya: nanyain “ada berapa item sih di tumpukan?”.

**Output:**

```
Size: 2
```
# **2. Queue (FIFO — First In, First Out)**

Queue bekerja seperti antrian yang duluan masuk, itu yang duluan keluar.

## **Membuat Queue**

```python
queue = []
```

**Penjelasan**

Ini bikin antrian kosong.
Baru nyiapin tempatnya, belum ada isi.

## **Enqueue (Menambah Elemen ke Queue)**

```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue:", queue)
```

**Penjelasan**

`append()` menambah elemen ke **belakang** antrian.
Elemen yang masuk dulu akan berada di depan.
`print()` untuk lihat isi antrian.

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

**Penjelasan:**

`pop(0)` ngambil elemen urutan pertama (yang paling depan).
 Cocok sama aturan FIFO.
`print()` nunjukkin hasil ambil dan sisa queue.

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

**Penjelasan**

`queue[0]` cuma ngelihat elemen paling depan, tanpa ngapus.
Jadi ini cuma buat ngecek siapa yang bakal keluar berikutnya.

**Output:**

```
Peek: B
```
## **Mengecek Apakah Queue Kosong**

```python
isEmpty = not bool(queue)
print("isEmpty:", isEmpty)
```

**Penjelasan**

Sama kayak stack: `True` kalau kosong.
Ini cara cepat buat tau apakah antrian masih ada orangnya atau nggak.

**Output:**

```
isEmpty: False
```
## **Ukuran Queue**

```python
print("Size:", len(queue))
```

**Penjelasan**

`len(queue)` hitung jumlah orang/item di antrian.
Intinya menghitung panjang queue sekarang.

**Output:**

```
Size: 2
```
