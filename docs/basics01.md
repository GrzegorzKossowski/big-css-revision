<a href='../README.md' id='top' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>

# Introduction

-   css - język używany do stylowania dokumentów html

Przykładowy kod css

```css
body {
    background-color: lightblue;
}

h1 {
    color: white;
    text-align: center;
}

p {
    font-family: verdana;
    font-size: 20px;
}
```

# Syntax

Składnia obejmuje selektory odwołujące się do konkretnych tagów, zawierające w nawiasach właściwości i ich wartości

selector { property: value }

`p { color: red; text-align: center; }`

# Selectors

Rozróżniamy następujące rodzaje selektorów

## Simple (select elements based on name, id, class)

-   odwołujący się wprost do elementu `p { text-align: center; color: red; }`
-   odwołujący się do atrybutu id tagu `#para1 { text-align: center; color: red; }`
-   odwołujący się do całej klasy obiektów `.center { text-align: center; color: red;}`

Element zawierający konretną klasę

`p.center { text-align: center; color: red; }`

zastosowanie obu klas

```
p.center {  text-align: center;	}
p.large {  font-size: 300%;	}
<p class="center large">This paragraph will be red, center-aligned, and in a large font-size.</p>
```

Grupowanie. Łączenie elementów mających wspólne style

`h1, h2, p { text-align: center; color: red; }`

Selektor uniwersalny (\*)

`* { text-align: center; color: blue; }`

## Combinator selectors (select elements based on a specific relationship between them)

**Descendant** - opisujący potomków rodzica (wszystkich) ( )

```
// wybiera wszystkie paragrafy w divie
div p {   background-color: yellow; }
```

Child - wybierający bezpośrednie dzieci rodzica (>)

```
// wybiera wszystkie paragrafy dzieci diva
div > p {   background-color: yellow; }
```

**Adjacent Sibling** (+) - wybiera bezpośrednie rodzeństwo następujące po elemencie (jedno)

```
// wybiera pierwszy paragraf po divie
div + p {   background-color: yellow; }
```

**General sibling** - wybiera całe rodzeństwo następujące PO elemencie (~)

```
// wybiera wszystkie paragrafy następujące PO elemencie divie
div ~ p {  background-color: yellow; }
```

## Pseudo-class selectors (select elements based on a certain state)

Pseudoklasy są używane celem nadania jakiegoś stanu elementowi (hover, visited, focus).

_selector:pseudo-class { property: value; }_

<div style="background-color:gold; color: red; padding: 5px;">UWAGA: a:hover MUSI być po a:link oraz po a:visited żeby zadziałało.
a:active MUSI być po a:hover żeby zadziałało.</div>

```html
/* 1) unvisited link */ a:link { color: #FF0000; } /* 2) visited link */
a:visited { color: #00FF00; } /* 3) mouse over link */ a:hover { color: #FF00FF;
} /* 4) selected link */ a:active { color: #0000FF; }
```

Pseudoklasy mogą być kombinowane z normalnymi klasami
`a.highlight:hover { color: #ff0000; }`

Przykładowe pseudoklasy

:first-child

-   zaznacza pierwsze dziecko obiektu, bez względu na atrybut `p:first-child { color: blue; }`
-   w każdym p zaznacz pierwszy i element `p i:first-child { color: blue; }`

:lang

-   pozwala na wybranie zasad dla wybranych języków `<span lang="pl">` będzie niebieski a `<span lang="no">` czerwony

```css
span:lang(pl) {
    color: blue;
}
span:lang(no) {
    color: red;
}
```

### wykaz pseudoklas

-   :active `a:active` Selects the active link
-   :checked `input:checked` Selects every checked `<input>` element
-   :disabled `input:disabled` Selects every disabled `<input>` element
-   :empty `p:empty` Selects every `<p>` element that has no children
-   :enabled `input:enabled` Selects every enabled `<input>` element
-   :first-child `p:first-child` Selects every `<p>` elements that is the first child of its parent
-   :first-of-type `p:first-of-type` Selects every `<p>` element that is the first `<p>` element of its parent
-   :focus `input:focus` Selects the `<input>` element that has focus
-   :hover `a:hover` Selects links on mouse over
-   :in-range `input:in-range` Selects `<input>` elements with a value within a specified range
-   :invalid `input:invalid` Selects all `<input>` elements with an invalid value
-   :lang(language) `p:lang(it)` Selects every `<p>` element with a lang attribute value starting with "it"
-   :last-child `p:last-child` Selects every `<p>` elements that is the last child of its parent
-   :last-of-type `p:last-of-type` Selects every `<p>` element that is the last `<p>` element of its parent
-   :link `a:link` Selects all unvisited links
-   :not(selector) `:not(p)` Selects every element that is not a `<p>` element
-   :nth-child(n) `p:nth-child(2)` Selects every `<p>` element that is the second child of its parent
-   :nth-last-child(n) `p:nth-last-child(2)` Selects every `<p>` element that is the second child of its parent, counting from the last child
-   :nth-last-of-type(n) `p:nth-last-of-type(2)` Selects every `<p>` element that is the second `<p>` element of its parent, counting from the last child
-   :nth-of-type(n) `p:nth-of-type(2)` Selects every `<p>` element that is the second `<p>` element of its parent
-   :only-of-type `p:only-of-type` Selects every `<p>` element that is the only `<p>` element of its parent
-   :only-child `p:only-child` Selects every `<p>` element that is the only child of its parent
-   :optional `input:optional` Selects `<input>` elements with no "required" attribute
-   :out-of-range `input:out-of-range` Selects `<input>` elements with a value outside a specified range
-   :read-only `input:read-only` Selects `<input>` elements with a "readonly" attribute specified
-   :read-write `input:read-write` Selects `<input>` elements with no "readonly" attribute
-   :required `input:required` Selects `<input>` elements with a "required" attribute specified
-   :root `root` Selects the document's root element
-   :target `#news:target` Selects the current active #news element (clicked on a URL containing that anchor name)
-   :valid `input:valid` Selects all `<input>` elements with a valid value
-   :visited `a:visited` Selects all visited links

## Pseudo-elements selectors (select and style a part of an element)

Pseudoelementy używane są do ostylowania fragmentów elementów, np. `::before`, `::after`, `::first-line`, `::first-letter`

Mogą być kombinowane z klasami

```
p.intro::first-letter {   color: #ff0000;   font-size: 200%; }
```

::before

```
// styluje dodany content przodu elementu. Wymaga propertki content, która może być pusta ‘’
h1::before {   content: url(smiley.gif); }
```

::after

```
// styluje dodany content z tyłu elementu. Wymaga propertki content, która może być pusta ‘’
h1::after {   content: url(smiley.gif); }
```

::marker

```
// wybiera markery listy (kulki, numery, kwadraty)
::marker {   color: red;   font-size: 23px; }
```

::selection

```
// styluje wygląd tekstu zaznaczonego
::selection {   color: red;   background: yellow; }
```

### wykaz pseudoelementów

-   ::after `p::after` Insert something after the content of each `<p>` element
-   ::before `p::before` Insert something before the content of each `<p>` element
-   ::first-letter `p::first-letter` Selects the first letter of each `<p>` element
-   ::first-line `p::first-line` Selects the first line of each `<p>` element
-   ::marker `::marker` Selects the markers of list items
-   ::selection `p::selection` Selects the portion of an element that is <span style='background-color: gold; color: red;'>selected</span> by a user

## Attribute selectors (select elements based on an attribute or attribute value)

Jest możliwe oznaczanie elementów z określonym atrybutem, jego wartością, np. ‘text’
`selector[atrybut] { … }`

[atrybut]

```
// oznaczenie każdego linku z atrybutem target
a[target] {   background-color: yellow; }
```

[atrybut=”wartość”]

```
// oznaczenie każdego inputa, pola textowego
input[target="text"] {  background-color: yellow; }
```

[atrybut~=”wartość”]

```
// oznacza element z atrybutem width zawierający wartość 150
[width~="150"] {   border: 5px solid yellow; }
```

[atrybut|=wartość]

```
// oznaczenie elementu, którego atrybut zawiera w sobie dokładnie tę wartość lub tą wartąść z minusem, czyli “value” lub “value-...”
// oznaczy każy element z wartością ‘top’ lub ‘top-’,np. np. <p class="top-text">Hello world!</p>
[class|="top"] { background: yellow; }
```

[atrybut^=’wartość’]

```
// oznaczenie elementu, którego atrybut zaczyna się na wartość “value…”
// oznaczy <p class="top">Hello world!</p> lub <p class="top-text">Hello world!</p> lub <p class="topaz">Hello world!</p>
[class^="top"] { background: yellow; }
```

[atrybut$=’wartość’]

```
// oznaczenie elementu, którego atrybut konczy się na wartość “...value”
// oznaczy <p class="top">Hello world!</p> lub <p class="test-top">Hello world!</p> lub <p class="modeltop">Hello world!</p>
[class$="top"] { background: yellow; }
```

[atrybut*=’wartość’]

```
// oznaczenie elementu, którego atrybut zawiera “…value…”
[class*="ell"] { background: yellow; }
```

-   [attribute] `[target]` Selects all elements with a _target_ attribute
-   [attribute=value] `[target=_blank]` Selects all elements with _target="\_blank"_
-   [attribute~=value] `[title~=flower]` Selects all elements with a title attribute containing the word _"flower"_
-   [attribute|=value] `[lang|=en]` Selects all elements with a _lang_ attribute value starting with _"en"_
-   [attribute^=value] `a[href^="https"]` Selects every `<a>` element whose _href_ attribute value begins with _"https"_
-   [attribute$=value] `a[href$=".pdf"]` Selects every `<a>` element whose _href_ attribute value ends with _".pdf"_
-   [attribute*=value] `a[href*="w3schools"]` Selects every `<a>` element whose _href_ attribute value contains the substring _"w3schools"_

# How To

Sposób zamieszczania styli wewnętrznych (inline)

```html
<h2 style="color: red;">Title</h2>
```

Sposób zamieszczania styli wewnętrznych (internal)

```html
<style>
    h1 {
        color: red;
    }
</style>
```

Sposób zamieszczania styli zewnętrznych

```html
<link rel="stylesheet" type="text/css" href="mystyle.css" />
```

Kolejność ważności styli:

1. Inline (wewnątrz elementu)
2. External i internal (w sekcji head) - decyduje kolejność umieszczenia
3. Browser default

# Colors

Kolory można kodować w nas. formatach: `RGB`, `HEX`, `HSL`, `RGBA`, `HSLA`

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>
```

## RGB, RGBA

`rgb(red, green, blue, alpha)`

wartości zawierają się między 0 (czarny) a 255 (biały) - 32 bitowy kanał na każdy kolor, ~16+ milionów możliwości. Alpha od 0 (przezroczyste) do 1 (nieprzezroczyste)

## HEX

`#rrggbb`

Zapis szesnastkowy tych samych wartości.

## HSL, HSLA

`hsl(hue, saturation, lightness)`

`hsla(hue, saturation, lightness, alpha)`

Wartości procentowe, gdzie hue to kąt na kole kolorów, saturation to nasycenie barwą, intensywność, a lightness to jasność koloru (białe-czarne).

## inne

Ponadto html wspiera ~140 nazw własnych predefiniowanych kolorów.

## color props

Właściwości ustawiające kolor:

`backgroun-color` - kolor tła

`color` - kolor tekstu

`border-color` - kolor linii

# Backgrounds

`background-color` - color tła

`background-image: url("paper.gif");` - obrazek jako tło

`background-repeat` - czy ma być powtarzany

```
repeat	- powtarzany pionowo i poziomo

repeat-x - powtarzany poziomo

repeat-y - powtarzany pionowo

no-repeat - nie jest powtarzany, pojawia się raz

space - obrazek jest rozciągany (space-beetwen)

round - obrazek jest rozciągany, by wypełnić przestrzeń (no gaps)
```

`background-attachment` - w jaki sposób obrazek ma być przypięty

```
scroll - obrazek przesuwa się ze stroną (default)

fixed - obrazek nie przesuwa się ze stroną. Tło jest statyczne.

local - przesuwa się z zawartością elementu


initial - ustawia defaultową wartość.

inherit - przejmuje właściwość od rodzica.
```

`background-position` - zakotwiczenie obrazu na dwóch współrzędnych.

```
left top, center, right, bottom - jeśli zostanie podana jedna, obrazek wycentruje.

x% y% - procentowe określenie pozycji

x y - określenie pozycji w jednostkach
```

`background: color image repeat attachment position` - skrót zawierający wszystkie wartości

# Borders

Pozwalają na ustawienie linii elementu.

Linie mogą być różnego typu: `dotted`, `dashed`, `solid`, `inset`, `none`, `hidden`...

# Margins

# Padding

# Height/Width

# Box Model

# Outline

# Text

# Fonts

# Icons

# Links

# Lists

# Tables

# Display

<a href='../README.md' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>
<a href='#top' style='border: 1px solid gold; padding: 5px; color: gold'>↑ back to top</a>
