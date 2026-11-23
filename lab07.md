---
layout: default
title: Laborator 07
nav_order: 8
nav_exclude: false
search_exclude: false
---

# CIW Științele Comunicării

## Laborator 07: Proprietatea `display` din CSS

### Despre proprietatea `display`

Proprietatea `display` este una dintre cele mai importante în CSS, deoarece controlează *cum este afișat* un element pe pagină și *cum se comportă* el în raport cu celelalte elemente. Practic, display definește **tipul "cutiei"** pe care un element o ocupă în fluxul documentului.

În HTML, fiecare element are un *tip de afișare implicit* (display implicit), dar acesta poate fi schimbat folosind CSS.

### Tipuri principale de `display`

#### `display: block;`

Elementele cu `display` de tip `block`:
- încep întotdeauna pe un rând nou;
- ocupă toată lățimea disponibilă (relativ la părintele lor);
- pot avea setate proprietăți precum `width`, `height`, `margin` și `padding`;
- exemple de elemente de tip `block`: `<div>`, `<p>`, `<h1>`–`<h6>`, `<main>`, `<nav>`, `<section>`, `<article>`, `<aside>`.

**Exemplul 1: transformă un element `<span>` într-un bloc**

În HTML, tag-ul `<span>` este folosit pentru a delimita o selecție *inline* dintr-un block. De exemplu, pentru a marca câteva cuvinte dintr-o propoziție. Dacă setăm explicit `display`-ul să fie de tip `block` pe aceste elemente, toate cuvintele ce folosesc `<span>` vor fi forțate să treacă pe linie nouă:

Codul CSS:
```css
span {
  display: block;
  background: yellow;
}
```

Codul HTML:
```html
<p>Lorem ipsum dolor <span>sit</span> amet consectetur adipisicing <span>elit</span>. Amet quisquam quibusdam <span>voluptatibus</span> beatae esse quia <span>itaque</span> non quidem.</p>
```

#### `display: inline;`

Elementele cu `display` de tip `inline`:
- NU încep pe rând nou; se aliniază pe același rând cu restul textului;
- ignoră proprietățile `width` și `height` (dacă sunt setate din CSS, nu au efect);
- exemple de elemente de tip `inline`: `<b>`, `<i>`, `<u>`, `<span>`, `<a>`, `<strong>`, `<em>`.

**Exemplul 2: așează 3 element de tip `div` pe același rând**

Elementele de tip `<div>` sunt, implicit, elemente de tip block. Asta înseamnă că fiecare va forța trecere pe linie nou (vor sta singure pe linie atâta timp cât nu le setăm alte proprietăți). Dacă setăm explicit `display`-ul să fie de tip `inline` pe aceste elemente, toate elementele de tip `<div>` vor putea sta împreună în aceeași linie (cât timp mai este loc în linia respectivă):

Codul CSS:
```css
div {
  display: inline-block;
  width: 100px;
  height: 100px;
  background: lightblue;
  margin: 10px;
}
```

Codul HTML:
```html
<div>Primul div</div>
<div>Al doilea div</div>
<div>Al treilea div</div>
```

#### `display: inline-block;`

Acest tip de `display` este un hibrid între `inline` și `block`:
- elementele se aliniază pe același rând (ca la `inline`);
- dar pot avea `width`, `height`, `margin`, `padding` (ca `block`);
- este foarte folosit pentru **crearea meniurilor orizontale sau a butoanelor așezate în linie**.

<mark>Atenție! În cadrul unuia dintre exercițiile din acest laborator trebuie să creați un meniu orizontal dintr-o listă!</mark>

### Alte tipuri de `display`

#### `display: none;`

Elementele care au `display` setat pe valoarea `none`:

- vor dispărea complet din pagină (nu sunt afișate și nici nu ocupă spațiu);
- sunt folosite uneori abuziv de către anumite site-uri care vor să ascundă conținut în pagină;
- mai pot fi folosite pentru *Easter Eggs*, ce reprezintă mici "surprize" ascunde de dezvoltatori pentru cei care explorează codurile sursă;
- efectul este diferit față de folosirea proprietății `visibility: hidden`, care ascunde elementul dar păstrează spațiul (rămâne o zonă "goală" în pagină).

**Exemplul 3: ascunde un element**

Exemplul următor include un paragraf care nu va fi afișat în browser-ul web, dar codul apare în sursa paginii:

Codul CSS:
```css
p.secret {
  display: none;
}
```

Codul HTML:
```html
<p>Bună ziua!</p>
<p class="secret">Acesta este un paragraf secret. El nu apare în pagină, dar se vede în codul sursă.</p>
```

###  De ce este proprietatea `display` importantă în Web Design?

Pentru că stabilește:

- modul în care elementele se aliniază (în bloc, în linie sau mixt - blocuri așezate în linie);
- cât spațiu ocupă elementele;
- dacă încep pe un rând nou sau stau pe același rând cu elementul anterior;
- cum reacționează atunci când adăugăm dimensiuni (`width` și `height`), margini sau padding.

Schimbarea tipului de `display` al elementelor poate transforma complet structura unei pagini web, fără a modifica HTML-ul!

### Exerciții

#### 1. Transformarea link-urilor `inline` în `block`

Creează un fișier HTML ce conține trei link-uri create cu elementul de tip ancoră `<a>`, așezate unul după celălalt, cu link-uri către profilurile tale sociale (Instagram, TikTok, etc.).

Transformă link-urile astfel încât fiecare să apară **pe linie separată**, ocupând toată lățimea containerului. Hint: folosește `display: block;`

Exemplu:
```html
<a href="https://www.instagram.com/notmasterpo/">TopG</a>
<a href="https://www.tiktok.com/@georgebecaliofficiel">Gigi Becali</a>
<a href="https://www.facebook.com/SellyOficial">Selly</a>
```

#### 2. Listă orizontală

Creează o listă neordonată (folosind `<ul>`) cu cinci elemente de tip `<li>`, în care să scrii ce ai mâncat astăzi.

Transformă lista într-una orizontală folosind doar proprietatea `display` (setează-i valoarea la `inline` sau `inline-block`).

Setează o clasă `special` pe unul dintre elementele de tip `<li>` și adaugă-i o culoare de background (folosește selectorul de clasă `.special` în CSS).

Stilează fiecare element cu `padding` și `margin` (`3px`, de exemplu) astfel încât să fie distanțat de celelalte. Verifică dacă are efect atunci când ai setat `display: inline`, respectiv `display: inline-block`.

#### 3. Comparație `inline`, `inline-block` și `block`

Creează un text scurt în care să nserezi trei elemente `<span>`. Poți porni de la codul de mai jos sau poți crea propriul cod:

```html
<p>De ce nu se ceartă <span>programatorii</span> niciodată?</p>
<p>Pentru că preferă să rezolve <span>conflictele</span> înainte să devină <span>erori</span>.</p>
```

Aplică o culoare diferită de background pentru fiecare dintre cele 3 tag-uri de tip `<span>` (hint: folosește ID-uri sau clase de CSS).

De asemenea, aplică un `display` diferit pentru fiecare:
- `display: inline;` pentru primul tag de tip `<span>`;
- `display: inline-block;` (cu width & height) pentru al doilea tag de tip `<span>`;
- `display: block;` pentru al treilea tag de tip `<span>`.

Observă care este comportamentul fiecărui tag de tip `<span>` în funcție de proprietatea `display`.

#### 4. Crearea unui card cu elemente `inline` vs `block` vs `inline-block`

Creează un card ce va cuprinde:

1. numele tău într-un tag de tip `<span>`;
2. o imagine (`<img>`) cu ceea ce îți dorești (o casă, o mașină, o vacanță, etc.) - poți prelua imaginea de pe site-ul <a href="https://unsplash.com/" target="_blank">https://unsplash.com/</a>
3. numele grupei într-un `<div>`;
4. un buton *Contactează-mă* (butonul va fi doar afișat, însă nu va fi funcțional - nu va face nimic când este apăsat).

Aplică următoarele modificări din CSS:

- schimbă `display`-ul numelui tău (tag-ul `<span>`) în `block;`
- schimbă `display`-ul grupei și al butonului în `inline-block;`, astfel încât să fie pe aceeași linie; setează-le și o lățime dorită (ex.: `width: 200px;`)

Opțional:

- fă în așa fel încât imaginea să fie centrată (hint: pune imaginea într-un `div` și aplică proprietatea `text-align` pe `div`)
