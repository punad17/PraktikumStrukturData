🧃 Implementasi Queue di Python
Program ini menunjukkan contoh sederhana struktur data Queue (antrian) menggunakan list di Python.
Queue bekerja dengan prinsip FIFO (First In, First Out) — elemen yang pertama masuk akan menjadi yang pertama keluar.

📘 Kode Program
queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontElement = queue[0]
print("Peek: ", frontElement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
📖 Penjelasan
Inisialisasi Queue Membuat list kosong sebagai antrian:

queue = []
Enqueue (Menambah Data) Menambahkan elemen ke dalam antrian menggunakan append():

queue.append('A')
queue.append('B')
queue.append('C')
Setelah bagian ini, isi antrian: ['A', 'B', 'C'].

Dequeue (Menghapus Data Terdepan) Menghapus elemen pertama dengan pop(0):

element = queue.pop(0)
Elemen 'A' keluar dari antrian.

Peek (Melihat Elemen Terdepan) Melihat isi paling depan tanpa menghapus:

frontElement = queue[0]
isEmpty (Cek Kosong atau Tidak) Mengecek apakah antrian kosong:

isEmpty = not bool(queue)
Size (Jumlah Elemen) Menghitung banyaknya elemen yang tersisa:

len(queue)
🧩 Hasil Eksekusi
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
💡 Kesimpulan
Queue di Python bisa dibuat dengan list.

Prinsip kerjanya adalah FIFO (First In, First Out).

Operasi dasar:

append() → menambah data (enqueue)
pop(0) → menghapus data paling depan (dequeue)
queue[0] → melihat data paling depan (peek)
Struktur ini berguna untuk simulasi antrian pelanggan, sistem printer, atau proses data berurutan.
