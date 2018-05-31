---
layout: acc_layout
toc: prolog
use_math: true
use_highlight: true
---

# Programowanie w Logice - Lista 1

## Fakty

Przykład teoretyczny: \\( p(t_1, t_2, ... t_n) \\)

Przykład praktyczny:
```prolog
lubi(student, rzs). %czytany jako student lubi rzs
```
<p></p>
---

## Reguły

Przykład teoretyczny: jeśli \\(head\\) jest postaci \\(p(t_1, t_2, ... t_n) \\) a \\(body\\) jest
warunkiem z którego wynika \\(head \\) to zapisujemy \\(head :- body\\).

Przykład praktyczny:

```prolog
lubi(autor, X) :- lubi(X, rzs) %czytany jako student autor lubi X jeśli X lubi rzs
```
<p></p>
---

## Operatory logiczne

\\(\land \\) zapisujemy jako \\(,\\)

\\(\lor \\) zapisujemy jako \\(;\\) Uwaga: Krążą pogłoski braku miłości do średników. Należy stosować prawa De Morgana

\\(\neg \\) zapisujemy jako \\(not (p(...))\\) albo \\( \backslash+ (p(...)) \\)

---

## Styl

Dla części \\(body \\) po każdym z warunków należy stosować enter oraz tabulację.

Takie same reguły należy zapisywać pod sobą.

Między różnymi regułami należy zostawić co najmniej jedną linię przerwy.

---

## Stałe i zmienne

W [pierwszym](#fakty) przykładzie praktycznych mieliśmy dwie stałe. Pierwszą z nich jest student, drugą rzs.
W [drugim](#reguły) przykładzie praktycznych mamy dwie stałe: autor oraz rzs. Zmienną jest \\(X\\). Prolog poszuka takich
\\(X\\), aby spełniały fakt (lub regułę, jeśli będzie zdefiniowana) lubi. W [pierwszym](#fakty) przykładzie widzimy, iż student lubi rzs.
Zatem następuje przypisanie do \\(X\\) wartości student. Po tym zabiegu stwierdza, że autor lubi student.



---

## Zasada zamkniętego świata:

Przyjmujemy, że prawdziwe w programie jest jedynie to, co było podane.

---

## Wskazówki

* Warto uzupełniać zadania własnymi testowymi danymi i sprawdzić działanie programu. Wszakże wszyscy wiemy, iż początki bywają... różne.
* Gdy zmienna pojawia się tylko raz w regule należy użyć zmiennej anonimowej, w innym przypadku otrzymamy ostrzeżenie. Taką zmienną zapisujemy za pomocą _ (podkreślenie). Przykładem jest:
```prolog
ojciec(X) :- syn(Y , X) % X jest ojcem, gdy Y jest synem X. Powoduje ostrzeżenie, że Y jest użyty tylko raz.
ojciec(X) :- syn(_ , X) % X jest ojcem kogoś. Nie interesuje nas kogo.
```

* Należy uważać z operatorem negacji. Utrudnia on prologowi wnioskowanie, szczególnie przy dużych regułach.

---

## Zadania

[Treści zadań](/pdfs/wyb/prolog/pl_lista1.pdf)

### Zadanie 1.

Należy opisać relacje rodzinne przy pomocy innych podanych. Przykładowo:
```prolog
dziadek(X, Y) :- ... % musimy napisać, że istnieje takie Z, iż X jest ojcem Z a Z jest ojcem Y
```
Analogicznie inne przykłady.

---

### Zadanie 2.

Celem tego zadania jest nauczenie nas potęgi rekurencji w Prologu. Oczywistym stwierdzeniem jest, że dla wieży
\\(B_1 > B_2 > B_3 > B_4 > B_5 \\) gdzie \\( > \\) oznacza bycie ponad nasza relacja jest przechodnia. Tzn. \\(B_1 > B_4 \\).

Zatem above należy zdefiniować jako: \\( B_i \\) jest ponad \\( B_j \\) jeśli są bezpośrednio nad sobą albo istnieje takie \\( B_k \\), że \\( B_k \\) jest bezpośrednio nad \\( B_j \\) oraz \\( B_i \\) jest ponad \\( B_k \\). Użycie sformułowania, iż \\( B_k \\) jest bezpośrednio ponad \\( B_j \\) umożliwa nam uniknięcie podwójnej rekurencji, która zapętli się w nieskończoność.

```prolog
above(X, Y) :- (onB(X, Y);
               (onB(X, Z), above(Z, Y))).
```
<p></p>

---

### Zadanie 3.

Tutaj nie do końca należy się trzymać polecenia. Zamiast definiować rekurencyjne dla \\( leftOf \\) powinniśmy zdefiniować inną, podobnie nazwaną regułę.
W innym przypadku wpadniemy w nieskończoną rekurencję. Niech ta reguła nazywa się \\( rLeftOf \\). Należy ją zdefiniować analogicznie do zadania2.
\\( rRightOf \\) definiujemy jako zamianę argumentów w \\( rLeftOf \\). Analogicznie definiujemy rekursyjne \\( rAbove \\)

Najtrudniejszą częścią zadania jest predykat \\( higher \\) . Musimy rozważyć aż cztery przypadki. Dla \\( higher(X, Y) \\):
* \\( X \\) może być \\( rAbove \\) nad \\( Y \\)
* \\( X \\) może być \\( rAbove \\) nad \\( Z \\) a \\( Z \\) na lewo od \\( Y \\)
* \\( X \\) może być \\( rAbove \\) nad \\( Z \\) a \\( Z \\) na prawo od \\( Y \\)
* \\( X \\) może być \\( above \\) nad \\( A \\), \\( Y \\) może być \\( above \\) nad \\( B \\) oraz \\( A \\) jest \\( higher \\) \\( B \\)

```prolog

left_of(olowek, klepsydra).
left_of(klepsydra, motyl).
left_of(motyl, ryba).

above(rower, olowek).
above(aparat, motyl).

right_of(X, Y) :- left_of(Y, X).
below(X, Y) :- above(Y, X).

r_right_of(X, Y) :- right_of(X, Y).

r_right_of(X, Y) :-
	right_of(X, Z),
	r_right_of(Z, Y).

r_left_of(X, Y) :- left_of(X, Y).

r_left_of(X, Y) :-
	left_of(X, Z),
	r_left_of(Z, Y).

r_above(X, Y) :- above(X, Y).

r_below(X, Y) :- r_above(Y, X).

r_above(X, Y) :-
	above(X, Z),
	r_above(Z, Y).

higher(X, Y) :-
	r_above(X, Y).

higher(X, Y) :-
	r_above(X, Z),
	r_left_of(Z, Y).

higher(X, Y) :-
	r_above(X, Z),
	r_right_of(Z, Y).

higher(X, Y) :-
	above(X, A),
	above(Y, B),
	higher(A, B).

```
<p></p>

---

### Zadanie 4.

Tutaj następuje przymusowa powtórka LiSF.

\\( X \\) jest elementem maksymalnym częściowego porządku, jeśli \\( le(X, X) \\) (X jest w dziedzinie)
oraz nie istnieje \\( le(Y, X) \\) (tj. nie istnieje Y, który jest większy od Y).
Element jest największy, jeżeli jest on w dziedzinie oraz jest on jedynym elementem maksymalnym (tj. nie istnieje inny element maksymalny).

Analogicznie element najmniejszy oraz minimalny.

```prolog
maksymalny(X) :- le(X,X),
                 not((le(Y,X), Y \= X)).
minimalny(X)  :- le(X,X),
                 \+ (le(X,Y), Y \= X).
najwiekszy(X) :- maksymalny(X),
                 \+ (maksymalny(Y), Y \= X).
najmniejszy(Y):- minimalny(X),
                 \+ (minimalny(Y), Y \= X ).
```
<p></p>

---

### Zadanie 5.

Ciąg dalszy powtórki LiSF.

Aby sprawdzić, czy relacja jest częściowym porządkiem należy sprawdzić trzy własności. Ponieważ prolog kiepsko radzi sobie sprawdzając przypadki ogólne
należy pozamieniać kwantyfikatory.

Przechodniość:

\\( \forall X(X \in D \implies le(X, X)) \\).

Należy zamienić na:

\\( \neg (\exists X((X \in D)\land( \neg (le(X, X))))) \\).

\\(X \in D \\) zapiszemy w prologu jako:
```prolog
le( X, _) ; le(_, X)
```

Analogicznie postępujemy z innymi własnościami. Dokładniejsze przekształcenie na [stronie](http://ki.pwr.edu.pl/kobylanski/dydaktyka/page6/page2/index.html) prowadzącego.


```prolog
zwrotnosc :- \+ (
                 (le(X, _); le(_,X)),
                 \+ le(X,X)).

przechodniosc :- \+ ((le(X,_); le(_,X)),
                       (le(Y,_); le(_,Y)),
                       (le(Z,_); le(_,Z)),
                       le(X,Y), le(Y,Z),
                       \+ le(X,Z)).

slaba_antysymetrycznosc :- \+ ((le(X,_); le(_,X)),
                                 (le(Y,_ );le(_,Y)),
                                 le(X,Y), le(Y,X),
                                 X \= Y).


czesciowyporzadek :- zwrotnosc, przechodniosc, slaba_antysymetrycznosc.
```
<p></p>
---

### Zadanie 6.

Najwygodniej skorzystać z predykatu:
```prolog
between(X, Y, Z), ... %Z przyjmie wtedy wszystkie wartości pomiędzy X a Y (włącznie!)
```
następnie trzeba napisać predykat \\(prime(N)\\) zwracający \\(true \\) jeśli \\(N \\) jest liczbą pierwszą. Należy w nim zapisać, iż żadna mniejsza liczba od \\(N \\) nie dzieli \\(N \\) bez reszty.
Można tego dokonać także rekurencyjnie.

```prolog
divisible(X, Y) :- (X > 1,
                        ((X =:= Y) ;
                        (not(0 is X mod Y), divisible(X, Y + 1)))
                   ).

prime(X, Y, N) :- between(X,Y,N), divisible(N, 2).
```
