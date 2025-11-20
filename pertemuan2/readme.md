implementasi **Linked List** sederhana menggunakan bahasa **Python**.  
Fitur yang tersedia meliputi:

* Menambahkan data di awal list
* Menambahkan data di akhir list
* Menambahkan data di posisi tertentu
* Menghapus data di awal list
* Menghapus data di akhir list
* Menghapus data di posisi tertentu
* Menampilkan isi list
* Menghitung panjang list

# Penjelasan Class di Python

##  Apa itu Class?
**Class** adalah blueprint atau kerangka untuk membuat objek.
Class mendefinisikan **atribut (variabel)** dan **method (fungsi)** yang dimiliki oleh objek.
Dengan class, kita bisa membuat banyak objek dengan struktur dan perilaku yang sama.

## Kelas `Node`
```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```
- `Node` adalah struktur dasar dari **linked list**.  
- `data` menyimpan nilai (misalnya `"apel"`, `"jeruk"`).  
- `next` (atau `pointer`) menunjuk ke node berikutnya.  
- Jadi setiap node punya **isi data** dan **alamat node selanjutnya**.

---

##  Kelas `LinkedList`
```python
class LinkedList:
    def __init__(self):
        self.head = None
```
- `LinkedList` adalah wadah utama.  
- `self.head` menunjuk ke node pertama. Jika kosong, nilainya `None`.

### Fungsi `insert_at_first`
```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```
- Menambahkan `data` di awal list.  
- `next` dari node baru menunjuk ke `head` lama.  
- `head` diganti dengan node baru → data masuk di **depan list**.

###  Fungsi `insert_at_last`
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
- Menambahkan `data` di akhir list.
- Jika list kosong → langsung isi `head`.  
- Jika tidak kosong → telusuri sampai node terakhir (`while node_sekarang.next`).  
- Tambahkan node baru di ujung list.


### Fungsi `insert_at`
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
- Menyisipkan data di posisi tertentu.  
- Jika `index == 0` → sama seperti `insert_at_first`.  
- Jika index valid → telusuri sampai node sebelum posisi yang diinginkan.  
- Buat node baru, lalu sambungkan ke list.

### 📌 Fungsi `remove_first`
```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```
- Menghapus node pertama.  
- `head` digeser ke node berikutnya.

### Fungsi `remove_last`
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
- Jika kosong → tampilkan pesan.  
- Jika hanya 1 node → hapus dengan `self.head = None`.  
- Jika lebih dari 1 → telusuri sampai node terakhir, lalu putuskan link dari node sebelumnya.

### Fungsi `remove_at`
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
- Menghapus node di posisi tertentu.  
- Jika index = 0 → sama seperti `remove_first`.  
- Jika index valid → telusuri sampai node sebelum posisi yang dihapus, lalu sambungkan ke node setelahnya.

###  Fungsi `print`
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
- Menampilkan isi linked list dalam format `"data -> data -> ..."`.  
- Jika kosong → tampilkan `"data kosong"`.

### Fungsi `length`
```python
def length(self):
    urutan = 0
    data_sekarang = self.head
    while data_sekarang:
        urutan += 1
        data_sekarang = data_sekarang.next
    return urutan
```
- Menghitung jumlah node dalam linked list.  


##  Eksekusi Program
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

### Step by step:
1. Insert `"jeruk"` → list: `jeruk`  
2. Insert `"mangga"` di depan → `mangga -> jeruk`  
3. Insert `"apel"` di depan → `apel -> mangga -> jeruk`  
4. Insert `"nanas"` di belakang → `apel -> mangga -> jeruk -> nanas`  
5. Insert `"anggur"` di index 2 → `apel -> mangga -> anggur -> jeruk -> nanas`  

**Remove:**
1. Remove first → `mangga -> anggur -> jeruk -> nanas`  
2. Remove last → `mangga -> anggur -> jeruk`  
3. Remove at index 2 → `mangga -> anggur`  

**Output:**
```
mangga -> anggur -> 
2
```


Jadi, program ini membuat **linked list sederhana** dengan operasi **insert, remove, print, dan length**.  
