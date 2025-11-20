
# ✅ **README.md – Penjelasan Linked List**
````markdown
# Struktur Data — Linked List (Python)

Di file ini kita bahas cara kerja Linked List sederhana yang dibuat pakai Python.  
Setiap fungsi dijelasin satu per satu biar gampang paham alurnya.

## ## 📌 1. Class Node

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
````

**Penjelasan:**

`Node` itu semacam kotak yang nyimpen **data** dan **petunjuk** (pointer) ke node berikutnya.
`data` → isi yang disimpan.
`next` → penunjuk ke node selanjutnya (default-nya `None` kalau belum ada).

## ##  2. Class LinkedList

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

`head` adalah node paling depan.
 Kalau `head = None`, berarti list masih kosong.

# ## 3. Fungsi Insert (Menambah Data)

---

## ### insert_at_first() — Tambah data di depan

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

Bikin node baru yang diarahkan ke `head`.
Terus `head` diganti jadi node baru itu.

## ###  insert_at_last() — Tambah data di belakang

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next

        node = Node(data)
        node_sekarang.next = node
```

Kalau list kosong → langsung jadi head.
Kalau nggak kosong → jalan sampai node terakhir.
Pas nemu ujungnya → tambah node baru.

## ### insert_at() — Tambah data di posisi tertentu

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index invalid!")
    elif index == 0:
        self.insert_at_first(data)
    else:
        node_sekarang = self.head
        urutan = 0
        while urutan < (index - 1):
            node_sekarang = node_sekarang.next
            urutan += 1

        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

Cek dulu index valid atau tidak.
Kalau index 0 → pakai insert depan.
Kalau index lain → cari posisi sebelumnya, lalu sisipkan node baru.

---

# ## 4. Fungsi Remove (Menghapus Data)

## ### remove_first() — Hapus data paling depan

```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```

Nggak ada data → tampilkan pesan.
Ada data → geser `head` ke node berikutnya.

## ### remove_last() — Hapus data paling belakang

```python
def remove_last(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    elif self.head.next is None:
        self.head = None
    else:
        node_sebelumnya = None
        node_sekarang = self.head

        while node_sekarang.next:
            node_sebelumnya = node_sekarang
            node_sekarang = node_sekarang.next

        node_sebelumnya.next = None
```

Kalau list kosong → nggak bisa hapus.
Kalau cuma satu node → hapus langsung.
Kalau lebih dari satu → cari node terakhir dan putuskan koneksinya.

## ### remove_at() — Hapus data berdasarkan index

```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index invalid!")
    elif self.head is None:
        print("list kosong")
    elif index == 0:
        self.head = self.head.next
    else:
        urutan = 0
        node_sekarang = self.head

        while urutan < (index - 1):
            node_sekarang = node_sekarang.next
            urutan += 1

        node_sekarang.next = node_sekarang.next.next
```

Cek dulu index valid atau tidak.
Kalau index 0 → hapus depan.
Kalau bukan → cari posisi sebelum index, lalu lewati node yang mau dihapus.

# ## 5. print() — Tampilkan isi Linked List

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ""
        node_sekarang = self.head

        while node_sekarang:
            text_print += str(node_sekarang.data) + " -> "
            node_sekarang = node_sekarang.next

        print(text_print)
```

Loop dari depan sampai habis.
Gabung tiap data pakai panah (“->”).

---

# ##  6. length() — Menghitung jumlah node

```python
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        urutan += 1
        data_sekarang = data_sekarang.next

    return urutan
```

Hitung jumlah node dengan cara jalan dari head ke akhir.

# ##  7. Contoh Penggunaan

```python
LL = LinkedList()

# insert
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("apel")
LL.insert_at_last("nanas")
LL.insert_at(2, "anggur")

# remove
LL.remove_first()
LL.remove_last()
LL.remove_at(2)

LL.print()
print(LL.length())
```


# Selesai


```

