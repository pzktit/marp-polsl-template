---
marp: true
math: mathjax
theme: polsl
size: 16:9
paginate: true
backgroundImage: url("img/normal-page-background.png") 
transition: fade
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


<div class="columns">
<div>

- Visual Studio Code,
- rozszerzenie wspierające Marp,
- rozszerzenie LTeX może być użyteczne,
- i już.
- **nie musisz instalować VS Code. Skorzystaj z [vscode.dev](https://vscode.dev)!**

#### Poradniki

1. [https://www.youtube.com/watch?v=DG7FmbSojeY](https://www.youtube.com/watch?v=DG7FmbSojeY),
1. [Chris Ayers, Marp - Create Presentations with Markdown](https://dev.to/chris_ayers/marp-create-presentations-with-markdown-5e6k),
1. [Seven Tips For Getting The Most Out Of Marp](https://www.hashbangcode.com/article/seven-tips-getting-most-out-marp)
1. [Marpit Markdown](https://marpit.marp.app/markdown)

##### Kontent przygotowuje się w języku Markdown (plus małe wstawki HTML).

</div><div align="center" >

![w:400](img/marp-for-vscode.png)

</div>
</div>

###

###


---

## Szablon

Przedstawiony szablon stara się być zgodny z zaleceniami ["Systemu Identyfikacji Wizualnej Politechniki Śląskiej"](https://www.polsl.pl/siwps/).

##### Najlepszym sposobem zapoznania się z procesm składu jest eksperyment z szablonem

#### Kroki niezbędne do instalacji

<div class="columns">
<div>

- Wykonaj fork tego repozytorium ([https://github.com/pzktit/marp-polsl-template](https://github.com/pzktit/marp-polsl-template)) na swoje konto GitHub. 
- Otwórz [https://vscode.dev](https://vscode.dev) lub ...
- Sklonuj repozytorium do lokalnego folderu i uruchom w nim VS Code. Jeżeli nie chcesz instalować zalecanego rozszerzenia otwórz DevContainer.


</div><div>

- Wyedytuj plik `slides/Slides.md`. **Nie zmieniaj jego nazwy**
- Rozszerzenie oferuje opcję podglądu wyników oraz eksportu do HTML i PDF.
-  Po wypchnięciu aktualnej treści prezentacji do GH, automatycznie uruchamia się budowanie `GitHub Pages` (budowanie musi być skonfigurowane na `GitHub Actions`). Jeżeli nie chcesz publikować wyników swojej pracy to zmień repo na prywatne albo usuń katalog `.git`.

</div>
</div>

###


###

---

## Plik wejściowy

Plik wejściowy to niemal "zwykły" Markdown. Jedyna różnica polega na wprowadzeniu znaku podziału slajdów w postaci trzech znaków minus (dash): `---`. 

<div class="columns">
<div>

```
---
marp: true
theme: polsl
size: 16:9
---

## Slajd 1

blah blah blah

---

## Slajd 2

blah blah blah

```

</div><div>

- Pierwszy slajd jest specjalny i zawiera preambułę. Dostępne parametry preambuły można sprawdzić w VS Code skótem `Ctrl+Spacja`.
- Wokół sekwencji `---` oddzielającej slajdy należy umieścić puste linie.
- W pliku VS Code należy poprawnie ustawić opcję umożliwiającą stosowanie wstawek HTML oarz ścieżkę do stylu (`.vscode/settings.json`)
```json
"markdown.marp.enableHtml": true,
"markdown.marp.themes": [
    "./slides/themes/polsl.css"
    ],
"markdown.marp.exportType": "html",
```

</div>
</div>

---

## Struktura dokumentu

##### Sposób składu znaczników podziału na sekcje definiuje styl.


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

Skład slajdu może jedno i dwukolumnowy. Więcej kolumn łatwo uzyskać, wprowadzając nowe klasy. Jednak celem tego szablonu jest zapewnienie maksymalnej prostoty edycji.

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
</div>

---

## Zawartość slajdu

###

### Wyrażenia matematyczne

W tekście można umieszczać wyrażenia matematyczne zgodnie ze składnią _TeX_ (a dokładniej _MathJax_). Wrażenia mogą być wstawione $2\pi r = \sqrt{3 x^3}$ oraz wystawione 
$$  y=\int\limits_{0}^{\infty} e^{-x^2} dx $$
Jak widać efekt jest całkiem zadowalający. Pionowe wyrównanie tekstu najłatwiej osiągnąć wstawiając puste nagłówki w pożądanych miejscach.

###

###

###

---

## Zawartość slajdu

### Kod komputerowy

Obowiązują reguły dokładnie takie same jak dla języka Markdown. Dla większości języków programowania wspierane jest kolorowanie składni. Kolory przypisane do elementów logicznych są kontrolowane w pliku CSS stylu. Aby umieścić kod języka `Python` należy zastosować następującą konstrukcję


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

###

### Slajd może również zawierać grafikę


<div class="columns">
<div>

- Szczegółowy opis składni umożliwiającej włączenie grafiki opisano w dokumentacji [https://marpit.marp.app/image-syntax](https://marpit.marp.app/image-syntax).
- należy zwrócić uwagę, że proponowany styl zawiera już obraz tła, zatem korzystanie z opcji `bg` może prowadzić do niepożądanych skutków.
- Pliki zawierające grafikę nie muszą być zapisane na lokalnym dysku - można się do nich odwoływać poprzez `url`.

```md
![w:300](https://picsum.photos/720?image=29)
```

</div>
<div style="justify-self: center; align-self: center">

![w:300](https://picsum.photos/720?image=29)

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
<figcaption style="font-size: 80%; text-align: center">
Tabela 1. Przykład podpisu pod rysunkiem lub tabelą.
</figcaption>

####
---

## Skład w wielu kolumnach

###
###
###

Możliwość podziału slajdu na dwie kolumny umożliwia kontener `columns`. Jego użycie zilustrowano we wzorcu, więc można go zacząć stosować bez zrozumienia "na wzór i podobieństwo". Kontener ten jest zrealizowany jest jako wstawka HTML elementu `grid`. Szczegółowy opis opcji jakie można stosować do wyrównania elementów w poziomie i pionie (przykłady użycia we wzorcu) przedstawiono w dokumencie [Chris House "A Complete Guide to CSS Grid"](https://css-tricks.com/snippets/css/complete-guide-grid/). Na podstawie zamieszczonego tam opisu bardzo łatwo stworzyć wzorce podziału obszaru slajdu na więcej logicznych elementów. Ale to już bardziej złożone zagadnienie.

###
###
###
###
---

##### Podczas eksportu do pliku HTML lokalne pliki graficzne nie są kopiowane. Należy je przenieść osobno i umieścić w odpowiednim podkatalogu względem pliku prezentacji. Podobny problem ma miejsce podczas prezentacji na systemie bez dostępu do sieci!

# Powodzenia!

