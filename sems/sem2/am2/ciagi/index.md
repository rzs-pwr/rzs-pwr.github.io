---
layout: acc_layout
toc: am2
use_math: true
---

Analiza Matematyczna 2
---

## Ciągi w \\( \mathbb{R^n} \\)

### Definicja granicy ciągu
\\[ \lim\_{k\to\infty} P_k = P \iff \lim\_{k\to\infty} \ \vert P\_k - P\ \vert  = 0\ \\]

### Zbieżność po współrzędnych

Niech \\( P\_k = (p\_{k\_1}, \ldots, p\_{k\_n}) \\) oraz \\( P = (p\_1, \ldots, p\_n) \\) wtedy:
\\[ \lim\_{k\to\infty} P\_k = P \iff \left(\forall i \in \[n\] \right)\left(\lim\_{k\to\infty} p\_{k\_i} = p\_i\right)\\]

### Warunek Cauchy'ego
\\[ \left(\forall \varepsilon > 0\right)\left(\exists k_0\right)\left(\forall m,l \geq k_o\right)\left(\ \vert P_m - P_l\ \vert  < \varepsilon\right)\ \\]
Czyli dla zbieżności po współrzędnych mamy:
\\[ \left(\forall i \in \[n\]\right)\left( \vert p_{m_i} - p_{l_i} \vert  \leq \sqrt{\sum_{j=1}^n\left(p_{m_j} - p_{l_j}\right)^2} < \varepsilon\right)\\]

### Własności ciągów zbieżnych

* Jest tylko jedna granica
* Podciąg ciągu zbieżnego jest zbieżny do tej samej granicy
* Każdy ciąg zbieżny jest ograniczony
* Ciąg spełniający warunek Cauchy'ego jest zbieżny
* \\( \lim\left(A_k+B_k\right) = A + B \\)
* \\( \lim\left(A_k-B_k\right) = A - B \\)
* \\( \lim\left(A_k\cdot B_k\right) = A \cdot B \\)
* \textbf{Podciąg podciągu jest podciągiem ciągu}


### Punkty skupienia

Punkt zbioru \\( \mathcal{D} \\), taki, że istnieje ciąg postaci \\( \left\\{\overrightarrow{P\_k}\right\\}\_{k=1}^\infty \subset \mathcal{D} \\) do niego zbieżny.

### Zbiory zwarte

* Zbiór \\( \mathcal{D} \subset \mathbb{R}^n \\) jest **domknięty** \\( \iff \\) każdy ciąg zbieżny postaci \\( \left\\{\overrightarrow{P_k}\right\\}\_{k=1}^\infty \subset \mathcal{D} \\) ma granicę w \\( \mathcal{D} \\).
* Zbiór jest **ograniczony** jeśli zawiera się właściwie w pewnej kuli.
* Zbiór jest **zwarty** jeśli jest domknięty oraz ograniczony.
* Suma skończonej ilości zbiorów domkniętych jest zbiorem domkniętym.
* Suma skończonej ilości zbiorów zwartych jest zbiorem zwartym.
