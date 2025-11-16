1. Stack (LIFO — Last In, First Out)

Stack adalah struktur data yang elemen terakhir masuk akan menjadi elemen pertama yang keluar.

Membuat Stack
stack = []

Push (Menambah Elemen ke Stack)
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack:", stack)


Output:

Stack: ['A', 'B', 'C']

Pop (Menghapus Elemen Teratas)
element = stack.pop()
print("Pop:", element)
print("Stack:", stack)


Output:

Pop: C
Stack: ['A', 'B']

Peek (Melihat Elemen Teratas)
topElement = stack[-1]
print("Peek:", topElement)


Output:

Peek: B

Mengecek Apakah Stack Kosong
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)


Output:

isEmpty: False

Ukuran Stack
print("Size:", len(stack))


Output:

Size: 2

2. Queue (FIFO — First In, First Out)

Queue adalah struktur data yang elemen pertama masuk akan menjadi elemen pertama yang keluar.

Membuat Queue
queue = []

Enqueue (Menambah Elemen ke Queue)
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue:", queue)


Output:

Queue: ['A', 'B', 'C']

Dequeue (Menghapus Elemen Pertama)
element = queue.pop(0)
print("Dequeue:", element)
print("Queue:", queue)


Output:

Dequeue: A
Queue: ['B', 'C']

Peek (Melihat Elemen Terdepan)
frontElement = queue[0]
print("Peek:", frontElement)


Output:

Peek: B

Mengecek Apakah Queue Kosong
isEmpty = not bool(queue)
print("isEmpty:", isEmpty)


Output:

isEmpty: False

Ukuran Queue
print("Size:", len(queue))


Output:

Size: 2
