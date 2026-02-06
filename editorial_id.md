## B. Belajar Bit

Gunakan identitas:

$$
N + X = (N \oplus X) + 2(N \& X)
$$

Sehingga target:

$$
(N \oplus X) + (N \& X) = (N + X) - (N \& X)
$$

Artinya, kita ingin memilih `X` **sebesar mungkin** sambil **meminimalkan overlap bit `1`** antara `N` dan `X`.

Strategi optimalnya adalah mengatur bit `1` pada `X` **hanya pada posisi di mana bit `N` bernilai `0`**, hingga bit paling signifikan (MSB) dari `N`.

Secara matematis, kandidat terbaik adalah:

$$
X = (\sim N) \,\&\, \text{mask}
$$

dengan:

$$
\text{mask} = (1 \ll (\text{MSB}(N) + 1)) - 1
$$

Jika hasilnya `X = 0` (kasus `N` terdiri dari semua bit `1`, yaitu `N = 2^k - 1`), maka jawaban yang valid adalah:


Kompleksitas waktu: `O(1)`
