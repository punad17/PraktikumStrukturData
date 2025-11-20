implementasi **Linked List** sederhana menggunakan bahasa **Python**.  
Fitur yang tersedia meliputi:

## Fitur
* Menambahkan data di awal list (`insert_at_first`)  
* Menambahkan data di akhir list (`insert_at_last`)  
* Menambahkan data di posisi tertentu (`insert_at`)  
* Menghapus data di awal list (`remove_first`)  
* Menghapus data di akhir list (`remove_last`)  
* Menghapus data di posisi tertentu (`remove_at`)  
* Menampilkan isi list (`print`)  
* Menghitung panjang list (`length`)  

# Penjelasan Class di Python

##  Apa itu Class?
**Class** adalah blueprint atau kerangka untuk membuat objek.
Class mendefinisikan **atribut (variabel)** dan **method (fungsi)** yang dimiliki oleh objek.
Dengan class, kita bisa membuat banyak objek dengan struktur dan perilaku yang sama.

```markdown
# Linked List Project (Python)

##  Deskripsi
Proyek ini berisi implementasi **Linked List** sederhana menggunakan bahasa **Python**.  
Linked List adalah struktur data linear yang terdiri dari node-node, di mana setiap node menyimpan data dan pointer ke node berikutnya.  


## Penjelasan Persintaks

### Class `Node`
```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```
`Node` adalah struktur dasar dari linked list.  
`data` → menyimpan nilai.  
`next` → menunjuk ke node berikutnya.  

### Class `LinkedList`
```python
class LinkedList:
    def __init__(self):
        self.head = None
```
`LinkedList` adalah wadah utama.  
`self.head` menunjuk ke node pertama.  

### Fungsi `insert_at_first`
```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```
Menambahkan data di awal list.  
Node baru menunjuk ke head lama, lalu head diganti.  

---

### Fungsi `insert_at_last`
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
Menambahkan data di akhir list.  
Jika kosong → langsung isi head.  
jika tidak → telusuri sampai node terakhir, lalu tambahkan node baru.  

### Fungsi `insert_at`
```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid!")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head
        
        while urutan < (index - 1):
            urutan += 1
            node_sekarang = node_sekarang.next

        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```
* Menyisipkan data di posisi tertentu.  
* Jika index = 0 → sama dengan `insert_at_first`.  
* Jika valid → telusuri sampai node sebelum posisi yang diinginkan, lalu sisipkan node baru.  

---

### Fungsi `remove_first`
```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```
* Menghapus node pertama.  
* Head digeser ke node berikutnya.  

---

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
* Menghapus node terakhir.  
* Jika hanya 1 node → head jadi `None`.  
* Jika lebih dari 1 → telusuri sampai node terakhir, lalu putuskan link dari node sebelumnya.  

---

### Fungsi `remove_at`
```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index invalid!")
    elif index == 0:
        self.remove_first()
    else:
        urutan = 0
        node_sekarang = self.head

        while urutan < index - 1:
            node_sekarang = node_sekarang.next
            urutan += 1

        node_sekarang.next = node_sekarang.next.next
```
* Menghapus node di posisi tertentu.  
* Jika index = 0 → sama dengan `remove_first`.  
* Jika valid → telusuri sampai node sebelum posisi yang dihapus, lalu sambungkan ke node setelahnya.  

---

### Fungsi `print`
```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head

        while node_sekarang:
            text_print += str(node_sekarang.data) + " -> "
            node_sekarang = node_sekarang.next

        print(text_print)
```
* Menampilkan isi linked list dalam format `"data -> data -> ..."`.  
* Jika kosong → tampilkan `"data kosong"`.  

---

### Fungsi `length`
```python
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1
    return urutan
```
* Menghitung jumlah node dalam linked list.  

---

## 🧪 Eksekusi Program
```python
LL = LinkedList()

# insert
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

# remove
LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)

LL.print()
print(LL.length())
```


## 🔎 Step by Step Proses

1. Insert `"jeruk"` → list: `jeruk`  
2. Insert `"mangga"` di depan → `mangga -> jeruk`  
3. Insert `"manggis"` di depan → `manggis -> mangga -> jeruk`  
4. Insert `"apel"` di belakang → `manggis -> mangga -> jeruk -> apel`  
5. Insert `"anggur"` di index 2 → `manggis -> mangga -> anggur -> jeruk -> apel`  

**Remove:**
1. Remove first → `mangga -> anggur -> jeruk -> apel`  
2. Remove last → `mangga -> anggur -> jeruk`  
3. Remove at index 1 → `mangga -> jeruk`  
4. Remove at index 1 → `mangga`  

**Output:**
```text
mangga -> 
1
```

```markdown
# 🧪 Penjelasan Eksekusi Program Linked List

## 📌 Kode Program
```python
LL = LinkedList()

# insert
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

# remove
LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)

LL.print()
print(LL.length())
```

---

## 🔎 Step by Step Proses

### 1. Membuat Linked List kosong
```python
LL = LinkedList()
```
* Membuat objek `LL` dari class `LinkedList`.  
* `head = None` → list masih kosong.  

---

### 2. Insert "jeruk" di depan
```python
LL.insert_at_first("jeruk")
```
* Node `"jeruk"` dibuat dan dijadikan `head`.  
* List:  
```
jeruk
```

---

### 3. Insert "mangga" di depan
```python
LL.insert_at_first("mangga")
```
* Node `"mangga"` dibuat.  
* `next` dari `"mangga"` menunjuk ke `"jeruk"`.  
* `head` diganti ke `"mangga"`.  
* List:  
```
mangga -> jeruk
```

---

### 4. Insert "manggis" di depan
```python
LL.insert_at_first("manggis")
```
* Node `"manggis"` dibuat.  
* `next` dari `"manggis"` menunjuk ke `"mangga"`.  
* `head` diganti ke `"manggis"`.  
* List:  
```
manggis -> mangga -> jeruk
```

---

### 5. Insert "apel" di belakang
```python
LL.insert_at_last("apel")
```
* Telusuri sampai node terakhir (`jeruk`).  
* Tambahkan node `"apel"` setelah `"jeruk"`.  
* List:  
```
manggis -> mangga -> jeruk -> apel
```

---

### 6. Insert "anggur" di index 2
```python
LL.insert_at(2, "anggur")
```
* Telusuri sampai node index 1 (`mangga`).  
* Sisipkan `"anggur"` setelah `"mangga"`.  
* List:  
```
manggis -> mangga -> anggur -> jeruk -> apel
```

---

## 🔥 Operasi Remove

### 7. Remove first
```python
LL.remove_first()
```
* `head` digeser ke node berikutnya (`mangga`).  
* List:  
```
mangga -> anggur -> jeruk -> apel
```

---

### 8. Remove last
```python
LL.remove_last()
```
* Telusuri sampai node terakhir (`apel`).  
* Putuskan link dari node sebelumnya (`jeruk`).  
* List:  
```
mangga -> anggur -> jeruk
```

---

### 9. Remove at index 1
```python
LL.remove_at(1)
```
* Telusuri sampai node index 0 (`mangga`).  
* Putuskan link ke node index 1 (`anggur`).  
* List:  
```
mangga -> jeruk
```

---

### 10. Remove at index 1 lagi
```python
LL.remove_at(1)
```
* Telusuri sampai node index 0 (`mangga`).  
* Putuskan link ke node index 1 (`jeruk`).  
* List:  
```
mangga
```

---

## 📌 Output Akhir
```text
mangga -> 
1
```

`LL.print()` → menampilkan isi list (`mangga ->`).  
`LL.length()` → menghitung jumlah node (hasilnya `1`).  


## Kesimpulan
Program ini menunjukkan bagaimana operasi **insert** dan **remove** bekerja pada **Linked List**.  
Setiap operasi mengubah arah pointer antar node sehingga list bisa bertambah atau berkurang sesuai instruksi.
```

