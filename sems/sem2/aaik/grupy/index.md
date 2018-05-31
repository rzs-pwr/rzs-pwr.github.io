---
layout: acc_layout
toc: aaik
use_math: true
---

### Grupy i podgrupy

1.  Def. Zbiór \\( H \\subseteq G \\) jest podgrupą grupy \\( 
    (G,\\cdot) \\) jeśli \\( H\\neq \\emptyset \\) oraz
    1.   \\( (\\forall x,y\\in H)(x\\cdot y \\in H) \\) 
    2.   \\( (\\forall x\\in H)(x^{-1} \\in H) \\) 
2.  Tw. Niepusty podzbiór \\( H \\) grupy \\( (G,\\cdot) \\) 
    jest podgrupą wtedy i tylko wtedy, gdy \\[ (\\forall x,y\\in
    H)(x\\cdot y^{-1} \\in H) \\] 
3.  Tw. Jeśli \\( \\mathcal{H} \\) jest rodziną podgrup grupy \\( 
    (G,\\cdot) \\) to \\( \\bigcap\\mathcal{H} \\) jest podgrupą
    grupy \\( (G,\\cdot) \\).
4.  Def. Podgrupą grupy \\( (G,\\cdot) \\) generowaną przez zbiór
    \\( X\\subseteq X \\) nazywamy najmniejszą podgrupę \\( 
    \\langle X \\rangle \\) grupy \\( G \\) zawierającą zbiór X. Mamy \\[ 
    \\langle X \\rangle = \\bigcap\\{H: \\text{ jest podgrupą } G \\land X\\subseteq
    H\\} \\] 
5.  Jeśli \\( \\mathrm{rank} (a) = k \\) to \\( \\langle a \\rangle =
    \\{e,a,a^2,\\ldots,a^{k-1}\\} \\sim C\_k \\).
6.  Jeśli \\( \\mathrm{rank} (a)=\\infty \\) to \\( \\langle a \\rangle =
    \\{\\ldots,a^{-2},a^{-1},e,a,a^2,\\ldots\\} \\sim (\\mathbb{Z},+) \\) . Izomorfizm: \\( \\phi:\\mathbb{Z}\\to G: k \\to a^k \\) 
7.  Graf Cayley\'a grupy \\( C\_5\\times C\_2 \\)
    
    ![](https://cs.pwr.edu.pl/cichon/2016_17_b/Algebra/C5C2.png)
    
8.  Grupa symetrii \\( n \\) -kąta równobocznego \\( D\_{2n} \\) 
    : obrót \\( \\alpha \\), odbicie \\( \\beta \\) ; równania:
    \\( \\alpha^n=e \\), \\( \\beta^2=e \\), \\( 
    \\alpha\\beta\\alpha\\beta=e \\) ; graf Cayley\'a grupy \\( 
    D\_{8} \\) 
    
    ![](https://cs.pwr.edu.pl/cichon/2016_17_b/Algebra/D8.png)
    
9.  **Twierdzenie \[Lagrange\]** Jeśli \\( H \\) jest podgrupą
    skończonej grupy \\( G \\), to \\[ \\mathrm{card}(H) \\big\|
    \\mathrm{card}(G)\~.  \\] Dowód (szkic). Określamy relację \\( 
    x\\sim y \\leftrightarrow xy^{-1}\\in H \\). Pokazujemy, że jest to relacja
    równoważności na \\( G \\). Pokazujemy, że \\( \[a\]\_\\sim =
    H \\cdot a \\) (= \\( \\{ha:h\\in H\\} \\) ). Następnie
    pokazujemy, że \\( \|Ha\| = \|H\| \\).\
    **UWAGA: musicie znać ten dowód !!!**
10. Wniosek. Jeśli \\( G \\) jest grupą skończoną oraz \\( a\\in G
    \\) to \\( \\mathrm{rank} (a) \| \\mathrm{card}(G) \\) \
    Dowód (szkic): \\( \|\\langle a \\rangle\| = \\mathrm{rank} (a) \\). Następnie
    stosujemy twierdzenie Lagrange\'a.
11. **Wniosek** (Małe Twierdzenie Fermata) Niech \\( p \\) będzie
    liczbą pierwszą oraz \\( 1\\leq a\\lt p \\). Wtedy \\[ 
    a^{p-1} = 1 \\mod p \\] Dowód (szkic): Stosujemy poprzedni
    wniosek do grupy \\( \\mathbb{Z}\_p^\*
    =(\\{1,2,\\ldots,p-1\\},\\cdot\_p) \\).

