# RZS-site

Do lokalnego generowania strony wymagane są: Ruby 2.5+ oraz bundler (`gem install bundler`).
Po pobraniu kopii repozutorum należy na jej roocie uruchomić `bundle exec jekyll serve`.
Strona pojawi sie wtedy na localhost:4000

## Dodawanie przedmiotu (jednostronowy)

Aby dodać do strony nowy przedmiot jednostronowy należy utworzyć plik index.md w odpowiedniej lokalizaji (np jeśli skrót nazwy naszego przemiotu to xyz i jest to przedmiot z piątego semestru, ścieżka będzie wyglądać tak: `sems/sem5/xyz/index.md`). W pliku tym dodajemy nagłówek:

```yml
---
layout: default
---
Tytuł strony
---
Treść
```

Następnie musimy jeszcze dodać przedmiot do głównej nawigacji. W tym celu dodajemy do odpowiedniego semsetru:

```yml
- page: Pełna nazwa przedmiotu
  url: ścieżka_do_pliku/index.md
```

Jeśli nie ma na liście potrzebnego semstru dodajemy go dodajęc w odpowiednim miejscu (kolejność wpisów jest taka sama jak kolejność w menu) oraz późnej dodajemy do niego nasz przedmiot:

```yml
- title: Semestr NUMER_SEMESTRU
  subfolderitems:
    - page: Pełna nazwa przedmiotu
    url: ścieżka_do_pliku/index.md
```

## Szybka konwersja
pandoc

## Dodawanie przedmiotu (wielostronowy)

Opis pojawi się wkrótce...

## TODO:

## TODO (aktualne przedmioty):
* Algorytmy i Sturtukry Danych (skrypt!!!)
* Wprowadzenie Do Teorii Grafów (skrypt!)
* Grafkika Komputerowa i Wizualizacja  (skrypt!)
* Technologie Sieciowe (skrypt)
* Wprowadzenie Do Funkcji Zespolonych (skrypt)
* Programowanie w logice
* Nowoczesne Technologie WWW (w zasadzie sam nie wiem, co tu trzeba...)
* Teoretyczne Podstawy Informatyki (Dla Wybrańców)

## TODO (archiwum):
* Analiza matematyczna 1 (przepisać notatki Kuby na webdev)
* Matematyka dyskretna (uporządkować zagadnienia dr-a Żeberskiego)
* Fizyka (podlinkować katedrę fizyki, na nic więcej się nie wysilamy)
* Problemy Prawne Informatyki (Alek?)
* Kurs Programowania (bez żartów, uratujmy tych nieszczęśników od AWT - choćby krótka wzmianka o wyższości FXa)
* Architektura komputerów i systemy operacyjne (uzupełnić dwa brakujące rozdziały, następnie przepisać na webdev)

## TODO (Damian):
* grafy z MD (podkradnę parę z Wprowadzenia do grafów!)
* rozbudować wyprowadzenie funkcji tworzącej F_n
* Zapisy



## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
