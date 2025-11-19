# CIW Științele Comunicării

## Laborator 07: Proprietatea `display` din CSS

### Despre proprietatea `display`

Proprietatea `display` este una dintre cele mai importante în CSS, deoarece controlează *cum este afișat* un element pe pagină și *cum se comportă* el în raport cu celelalte elemente. Practic, display definește **tipul "cutiei"** pe care un element o ocupă în fluxul documentului.

În HTML, fiecare element are un *tip de afișare implicit* (display implicit), dar acesta poate fi schimbat folosind CSS.

### Tipuri principale de `display`

#### `display: block;`

Elementele cu `display` de tip `block`:
- încep întotdeauna pe un rând nou;
- ocupă toată lățimea disponibilă;
- pot avea setate proprietăți precum `width`, `height`, `margin` și `padding`;
- exemple `block`: `<div>`, `<p>`, `<h1>`–`<h6>`, `<section>`, `<article>`.

#### Exemplul 1: transformă un `<span>` într-un bloc

Fișierul CSS:
```
span {
    display: block;
    background: yellow;
}
```

Fișierul HTML:
```
<p>Lorem ipsum dolor <span>sit</span> amet consectetur adipisicing <span>elit</span>. Amet quisquam quibusdam <span>voluptatibus</span> beatae esse quia <span>itaque</span> non quidem, commodi <span>doloremque</span>.</p>
```

#### `display: inline;`

Elementele cu `display` de tip `inline`:
- nu încep pe rând nou; se aliniază pe același rând cu restul textului;
- ignoră proprietățile `width` și `height`;
- exemple `inline`: `<span>`, `<a>`, `<strong>`, `<em>`.

#### Exemplul 2: pune 3 `div`-uri pe același rând

Fișierul CSS:
```
div {
  display: inline-block;
  width: 100px;
  height: 100px;
  background: lightblue;
  margin: 10px;
}
```

Fișierul HTML:
```
<div>Div-ul numărul 1</div>
<div>Div-ul numărul 2</div>
<div>Div-ul numărul 3</div>
```

#### `display: inline-block;`

Un hibrid între `inline` și `block`:
- elementele se aliniază pe același rând (ca `inline`);
- dar pot avea `width`, `height`, `margin`, `padding` (ca `bloc`k`);
- foarte folosit pentru **crearea meniurilor orizontale sau butoanelor**.

<mark>Atenție! La unul dintre exerciții trebuie să creați un meniu orizontal dintr-o listă!</mark>

### Tipuri suplimentare de `display`

#### `display: none;`

Elementul:
- dispare complet din pagină (nu ocupă spațiu);
- este diferit de `visibility: hidden`, care ascunde elementul dar păstrează spațiul.

#### Exemplul 3: ascunde un element

Fișierul CSS:
```
p.secret {
  display: none;
}
```

Fișierul HTML:
```
<p>Bună ziua!</p>
<p>Acesta este un paragraf secret. El nu apare în pagină, dar se vede în codul sursă.</p>
```

###  De ce este `display` important în web design?

Pentru că stabilește:
- modul în care elementele se aliniază;
- cât spațiu ocupă elementele;
- dacă încep pe un rând nou sau stau pe același rând;
- cum reacționează atunci când adăugăm dimensiuni, margini sau padding.

Schimbarea tipului de `display` poate transforma complet structura unei pagini, fără a modifica HTML-ul.

### Exerciții

#### 1. Transformarea elementelor `inline` în `bloc`

Creează un fișier HTML ce conține trei link-uri `<a>` unul după altul, care trimit către profilurile tale sociale (IG, TikTok, etc.)

Exemplu:
```
<a href="https://www.instagram.com/notmasterpo/">TopG</a>
```

Transformă link-urile astfel încât fiecare să apară **pe linie separată**, ocupând toată lățimea containerului. Hint: `display: block;`.

#### 2. Meniu orizontal simplu

Creează o listă neordonată `<ul>` cu cinci elemente `<li>`, în care să scrii ce ai mâncat astăzi.

Transformă lista într-un meniu orizontal, folosind doar proprietatea `display` (`inline` sau `inline-block`).

Aplică o clasă `special` pe unul dintre elementele de tip `<li>` și aplică-i o culoare diferită de background față de celelalte (folosește selectorul de clasă `.special` în CSS).

Opțional: Stilează fiecare element cu `padding` și `margin` (`3px`, de exemplu) astfel încât să fie distanțat de celelalte.

#### 3. Comparație între `inline`, `inline-block` și `block`

Creează un text scurt în care inserezi trei elemente `<span>`.

Aplică o culoare diferită de background pentru fiecare. De asemenea, aplică un `display` diferit pentru fiecare:
- `display: inline;` pentru primul;
- `display: inline-block;` (cu width & height) pentru al doilea;
- `display: block;` pentru al treilea.

Observă care este comportamentul fiecăruia.

#### 4. Crearea unui card cu elemente `inline` vs `block` vs `inline-block`

Creează un card ce va cuprinde:
1. numele tău într-un tag de tip `<span>`
1. o imagine (`<img>`) cu ceea ce îți dorești (casă, mașină, vacanță, etc.) - poți folosi <a href="https://unsplash.com/" target="_blank">https://unsplash.com/</a>
1. numele grupei într-un `<div>`
1. un buton "Contactează-mă" (butonul va fi doar afișat, însă nu va fi funcțional - nu va face nimic)

Aplică următoarele modificări:
- schimbă `display`-ul numelui tău în `block;`
- schimbă `display`-ul grupei și al butonului în `inline-block;`, astfel încât să fie pe aceeași linie; setează-le și o lățime dorită (ex.: `width: 200px;`)

Opțional:
- fă în așa fel încât imaginea să fie centrată (hint: pune imaginea într-un `div` și aplică proprietatea `text-align` pe `div`)
