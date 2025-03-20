**1. Kelas Graph**
Kelas ini merepresentasikan graf berbobot dengan metode:

__init__() → Inisialisasi edges (sisi graf) dan heuristic (nilai heuristik tiap node).
add_edge(node1, node2, cost) → Menambahkan jalur dua arah antar node dengan bobot cost.
set_heuristic(heuristics) → Menetapkan nilai heuristik setiap node.
reconstruct_path(came_from, current) → Menyusun kembali jalur dari node tujuan ke awal.

**2. Algoritma Pencarian**
**a. Greedy Best-First Search**
Menggunakan heuristik saja untuk memilih node berikutnya.
Gunakan Priority Queue (heapq.heappush) untuk memilih node dengan heuristik terkecil.
Jalurnya tidak selalu optimal, karena tidak mempertimbangkan bobot jalur.

**b. Search***
Gunakan f(n) = g(n) + h(n) untuk menentukan jalur terpendek.
g(n): Jarak dari awal ke node saat ini.
h(n): Heuristik (perkiraan jarak ke tujuan).
Priority Queue dipakai untuk memilih node dengan biaya total terendah.

Kode ini menerapkan Greedy Best-First Search dan A Search* untuk mencari jalur dalam graf berbobot menggunakan heuristik.

Graf dan Heuristik
Node: **S → A(2), S → B(3), A → D(4), A → B(1), B → C(3), D → G(1), C → G(4)**
Heuristik ke G:** {S:6, A:4, B:3, C:2, D:1, G:0}**
Algoritma dan Hasil
Greedy Best-First Search → Pilih node dengan heuristik terkecil.
Jalur: **S → B → C → G** (Cepat, tapi bisa kurang optimal).
A Search* → Gunakan g(n) + h(n) untuk jalur optimal.
Jalur: **S → A → D → G **(Optimal).

**Kesimpulan**
Greedy: Cepat, tapi tidak selalu optimal.
A*: Akurat, jalur optimal.
