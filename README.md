# *Q-Learning*

## *Kelompok 7*

Ikbal Dzakwan (234311043)
Mukti Ali Mudlofar (234311046)
Rara Aliviana Gumaranti (234311050)
Rian Cahyo Anggoro (234311052)

---

## *Deskripsi Singkat*

Q-Learning adalah algoritma Reinforcement Learning yang mengajarkan agen mengambil keputusan optimal melalui proses trial-and-error. Algoritma ini menggunakan *Q-Table* untuk menyimpan nilai kualitas tiap aksi pada kondisi tertentu.
Agen belajar dengan mencoba aksi, menerima reward, lalu memperbarui nilai Q menggunakan *persamaan Bellman*, sehingga mampu mempelajari strategi terbaik tanpa mengetahui model lingkungan.

---

## *Tujuan Q-Learning*

* Menentukan tindakan terbaik pada setiap state
* Memaksimalkan reward jangka panjang
* Belajar dari pengalaman
* Menghasilkan kebijakan optimal tanpa model lingkungan

---

## *Konsep Utama*

### *State (S)*

Posisi atau kondisi agen di lingkungan.

### *Action (A)*

Tindakan yang bisa dipilih agen: kiri, kanan, atas, bawah.

### *Reward (R)*

Feedback berupa nilai positif/negatif.

### *Q-Value / Q-Table*

Tabel berisi kualitas setiap pasangan state–action.

### *Policy (π)*

Strategi pemilihan aksi, misalnya *ε-greedy*.

### *Learning Rate (α)*

Seberapa besar nilai Q diperbarui.

### *Discount Factor (γ)*

Seberapa penting reward masa depan.

---

## *Rumus Q-Learning (Bellman Update)*

[
Q(s, a) \leftarrow Q(s, a) + \alpha (r + \gamma \max Q(s', a') - Q(s, a))
]

---

## *Hipotesa Function*

Mapping dari pasangan state–action ke nilai Q-value.
Diperbarui terus dengan pendekatan *Temporal Difference Learning (TD-Learning)*.

---

## *Cost Function*

Menggunakan *TD Error*:

[
TD = r + \gamma \max Q(s',a') - Q(s,a)
]

Tujuan algoritma: meminimalkan error ini agar Q-value semakin akurat.

---

## *Contoh Kasus: Grid 4×4*

* Terdapat 16 state (0–15)
* 4 aksi (left, right, up, down)
* Reward:

  * +1 jika mencapai *goal (state 15)*
  * 0 jika belum

Setelah banyak episode, agen mempelajari jalur tercepat ke goal.

---

## *Alur Kerja Q-Learning*

1. Inisialisasi Q-table dan parameter
2. Menentukan state awal
3. Memilih aksi (ε-greedy)
4. Mendapat reward
5. Update Q-table
6. Pindah ke state berikutnya
7. Ulangi sampai goal tercapai

---

## *Implementasi Program*

Program Python mencakup:

* Q-table 16×4
* Hyperparameter:

  * learning_rate = 0.8
  * discount_factor = 0.95
  * exploration_prob = 0.2
* Fungsi get_next_state()
* Training 1000 episode
* Visualisasi heatmap Q-value

---

## *Hasil*

Setelah pelatihan, Q-value tertinggi membentuk pola jalur optimal menuju goal. Agen telah mempelajari strategi terbaik melalui pengalaman tanpa instruksi jalur.

---

## *Kesimpulan*

Q-Learning merupakan algoritma efektif dalam pengambilan keputusan berbasis pengalaman. Dengan mekanisme eksplorasi–eksploitasi dan pembaruan nilai menggunakan persamaan Bellman, agen mampu mempelajari strategi optimal meskipun tanpa model lingkungan. Implementasi pada grid 4×4 menunjukkan bahwa Q-Learning mampu menemukan jalur terbaik menuju goal secara konsisten.
