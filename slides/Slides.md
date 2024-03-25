---
marp: true
math: mathjax
theme: polsl
size: 16:9
paginate: true
backgroundImage: url("img/normal-page-background.png") 
transition: fade 1s
---
<!-- _class: titlepage -->
<!-- _backgroundImage: url("img/title-page-background.png") -->

##

##

##

##

##

# Jak szybko tworzyć prezentacje

# korzystając z VS Code i Marp

### Piotr Zawadzki

### 24.03.2024 

---
## Niezbędne oprogramowanie

###

###


<div class="columns">
<div>

- Visual Studio Code,
- rozszerzenie wspierające Marp,
- rozszerzenie LTeX może być użyteczne,
- i już.

#### Poradniki

1. [https://www.youtube.com/watch?v=DG7FmbSojeY](https://www.youtube.com/watch?v=DG7FmbSojeY),
1. [Chris Ayers, Marp - Create Presentations with Markdown](https://dev.to/chris_ayers/marp-create-presentations-with-markdown-5e6k),
1. [Seven Tips For Getting The Most Out Of Marp](https://www.hashbangcode.com/article/seven-tips-getting-most-out-marp)
1. [Marpit Markdown](https://marpit.marp.app/markdown)

##### Kontent przygotowuje się w języku Markdown.

</div><div>

![w:400](img/marp-for-vscode.png)

</div>
</div>

###

###


---

## Szablon

###

###

Przedstawiony szablon stara się być zgodny z zaleceniami ["Systemu Identyfikacji Wizualnej Politechniki Śląskiej"](https://www.polsl.pl/siwps/).

#### Kroki niezbędne do instalacji

<div class="columns">
<div>

- Wykonaj fork tego repozytorium ([https://github.com/pzktit/marp-polsl-template](https://github.com/pzktit/marp-polsl-template)) na swoje konto GitHub. 
- Sklonuj repozytorium do lokalnego folderu.
- Uruchom VS Code. Jeżeli nie chcesz instalować zalecanego rozszerzenia otwórz DevContainer.


</div><div>

- Wyedytuj plik `slides/Slides.md`. **Nie zmieniaj jego nazwy**
- Rozszerzenie oferuje opcję podglądu wyników oraz eksportu do HTML i PDF.
-  Po wypchnięciu aktualnej treści prezentacji do GH, automatycznie uruchamne jest budowanie `GitHub Pages`. Jeżeli nie chcesz publikować wyników swojej pracy to zmień repo na prywatne albo usuń katalog `.git`.

</div>
</div>

###


###


---

## Struktura dokumentu

###


### Podział na sekcje
<div class="columns">
<div>

Strona tytułowa:
```
# Tytuł
## Podtytuł
### Autor
#### Data
##### Organizacja
```

</div><div>

Ciało dokumentu:
```
# Część
## Tytuł slajdu
### Nagłówek
#### Blok
##### Alert
```

</div>
</div>

### Szablon można łatwo dostosować


Skład prezentacji jest kontrolowany przez plik `slides/themes/polsl.css`.

###

###


---
## Zawartość slajdu

### Tekst

Skład slajdu może jedno i dwukolumnowy. Więcej kolumn łatwo uzyskać, wprowadząjąc nowe klasy. Jednak celem tego szablonu jest zapewnienie maksymalnej prostoty edycji. 

<div class="columns">
<div>

#### Wyliczanka 
To jest zwykły tekst po prostu wystarczy pisać $2\pi r = \sqrt{3 x^3}$ i pisać i pisać.
- jeden
- dwa
- trzy

</div><div>

#### Lista numerowana
To jest zwykły tekst po prostu wystarczy pisać.
1. jeden
2. dwa
3. **trzy**

</div>

---

## Zawartość slajdu

###

### Wyrażenia matematyczne

W tekście można umieszczać wyrażenia matematyczne zgodne ze składną _TeX_ (a dokładniej _MathJax_). Wrażenia mogą być wstawione $2\pi r = \sqrt{3 x^3}$ oraz wystawione 
$$  y=\int\limits_{0}^{\infty} e^{-x^2} dx $$
Jak widać efekt jest całkiem zadowalający. Pionowe wyrównanie tekstu najłatwiej osiągnąć wstawiając puste nagłówki w pożądanych miejscach.

###

###

###

---

## Zawartość slajdu

### Kod komputerowy

Obowiązują reguły dokładnie takie same dla języka Markdown. Dla większości języków programowania wspierane jest kolorowanie składni. Kolory przypisane do elementów logicznych są kontrolowane w pliku CSS stylu. Aby umieścić kod języka `Python` należy zastosować następującą konstrukcję


<div class="columns">
<div>

Fragment pliku `Slides.md`

```
```py
num1 = 1.5
num2 = 6.3

# Add two numbers
sum = num1 + num2

# Display the sum
print('The sum of {0} and {1} is {2}'.format(num1, num2, sum))
#``` usuń znak komentarza
```

</div>
<div>

Uzyskany wynik składu
```py
num1 = 1.5
num2 = 6.3

# Add two numbers
sum = num1 + num2

# Display the sum
print('The sum of {0} and {1} is {2}'.format(num1, num2, sum))
```

</div>
</div>

###

###


---

## Zawartość slajdu

### Slajd może również zawierać grafikę



<div class="columns-centered">
<div>

- Szczegółowy opis składni umożliwiającej włączenie grafiki opisano w dokumentacji [https://marpit.marp.app/image-syntax](https://marpit.marp.app/image-syntax).
- należy zwrócić uwagę, że proponowany styl zawiera już obraz tła, zatem korzystanie z opcji `bg` może prowadzić do niepożądanych skutków.
- Pliki zawierające grafikę nie muszą być zapisane na lokalnym dysku~-- można się do nich odwołuwać poprzez `url`.

```md
![w:400](https://picsum.photos/720?image=29)
```

</div>
<div>

![w:400](https://picsum.photos/720?image=29)

</div>
</div>


---

## Zawartość slajdu

### Tabele

- Tabele są zawsze wycentrowane i mogą zawierać wyrażenia matematyczne
- Do umieszczania podpisów można wykorzystać makro `figcaption`

| Column A | Column B | Column C | Column D |
| -------- | -------- | -------- | :------: |
| A1       | B1       | C1       |    D1    |
| A2       | B2       | C2       |    D2    |
| A3       | B3       | C3       |    D3    |
| A3       | B3       | C3       |    $y=\frac{2}{\pi}$    |
<figcaption align="center" style="font-size: 80%">
Tabela 1. Przykład podpisu pod rysunkiem lub tabelą.
</figcaption>


---

##### Podczas eksportu do pliku HTML grafika z podkatalogu `img` nie jest eksportowana. Musisz ją przenieść razem z plikiem HTML. Podobny problem ma miejsce podczas prezentacji na systemie bez dostępu do sieci!

# Powodzenia!

