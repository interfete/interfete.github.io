# CIW Științele Comunicării

## Laborator 12: Media queries. Unități CSS.

### Introducere

Paginile web sunt accesate de pe dispozitive foarte diferite: telefoane mobile, tablete, laptopuri și monitoare mari, cu precădere mai mult pe dispozitive mobile.
Pentru ca o pagină web să arate bine pe toate aceste ecrane, este necesar ca stilurile CSS să se adapteze în funcție de dimensiunea ecranului (anumite secțiune pot dispărea, anumite coloane pot fi mai late sau mai înguste, etc.)

CSS oferă două instrumente esențiale pentru acest scop:
- Media Queries – pentru a aplica stiluri diferite în funcție de dispozitiv
- Unități CSS – pentru a defini dimensiuni flexibile și scalabile

### Media Queries

Media Queries permit aplicarea unor reguli CSS doar atunci când sunt îndeplinite anumite condiții, cel mai frecvent legate de lățimea ecranului. Ele spun browserului "aplică aceste stiluri doar pe anumite ecrane".

Următorul media query (scris în CSS) aplică o culoare diferită de background pe întreaga zonă de desenare (pe `<body>`) doar pentru dispozitivele de maxim *768px*:

```
@media (max-width: 768px) {
    body {
        background-color: lightgray;
    }
}
```

Explicație:
- `@media` – definește o regulă condițională;
- `max-width: 768px` – regula se aplică doar dacă ecranul este mai mic sau egal cu 768px;
- codul din interior (care este un CSS obișnuit, cu selectori și reguli de tipul `proprietate: valoare;`) se aplică doar în aceste condiții.

### Tipuri uzuale de Media Queries

#### max-width

```
@media (max-width: 600px) {
    h1 {
        font-size: 20px;
    }
}
```

utilizat pentru telefoane mobile

#### min-width

```
@media (min-width: 992px) {
    .container {
        max-width: 1100px;
    }
}
```

utilizat pentru ecrane mari (desktop)

### Conceptul "Mobile First"

Abordarea mobile first presupune:
- stiluri de bază pentru ecrane mici;
- stiluri suplimentare pentru ecrane mai mari folosind `min-width`.

```
.card {
    font-size: 14px;
}

@media (min-width: 768px) {
    .card {
        font-size: 16px;
    }
}
```

### Ce sunt unitățile CSS?

Unitățile CSS definesc dimensiunea elementelor (lățimi, înălțimi, font-size, margini).

Există două categorii mari:
- unități absolute
- unități relative

#### Unități absolute

**px** - pixeli

- dimensiune fixă
- nu se adaptează la ecran

```
p {
    font-size: 16px;
}
```

#### Unități relative

**em** - relativ la dimensiunea fontului părintelui

```
p {
    font-size: 1.2em;
}
```

**rem** - relativ la dimensiunea elementului `root` (fontului elementului `<html>`)

```
html {
    font-size: 16px;
}

h1 {
    font-size: 2rem;
}
```

**%** - procent, relativ la dimensiunea elementului părinte

```
img {
    width: 100%;
}
```

**vw** și **vh**

- *vw* = procent din lățimea ferestrei
- *vh* = procent din înălțimea ferestrei

```
section {
    height: 100vh;
}
```

### Exemple uzuale

Text care se adaptează:

```
p {
    font-size: 1rem;
}

@media (min-width: 768px) {
    p {
        font-size: 1.2rem;
    }
}
```

Layout flexibil:

```
.container {
    width: 90%;
}

@media (min-width: 992px) {
    .container {
        width: 70%;
    }
}
```

### Greșeli comune

- folosirea exclusivă a px
- prea multe media queries inutile
- neînțelegerea diferenței dintre em și rem
- stiluri contradictorii în media queries

### Exerciții

Pentru următoarele exerciții testați soluțiile prin redimensionarea ferestrei browserului și folosind modul "Responsive" din DevTools. Rezolvați exercițiile pe ideea de *mobile first* - veți crea stiluri CSS globale, iar apoi veți crea media query-uri pentru dimensiuni mai mari.

#### 1. Text și spațiere adaptivă

Creează o secțiune (`<section>`) cu un titlu (`<h1>`) și un paragraf (`<p>`) în care:
- pe mobil:
    - titlul are `1.5rem`;
	- există o spațiere mică între titlu și paragraf (`margin-bottom`).
- pe desktop (`>= 992px`):
	- titlul are `2.5rem`;
	- există o spațiere mai mare între titlu și paragraf.
- înălțimea secțiunii să fie *minim 60vh* (proprietatea `min-width`).

#### 2. Layout cu două coloane care se reorganizează

Creează o pagină cu două zone: *sidebar* și *content*. Scrieți înăuntrul lor un text de forma *Aici este sidebar*, respectiv *Aici este content*.

Comportament:
- pe mobil: cele două zone vor sta una sub alta (folosiți comportamentul nativ al *div*-urilor).
- pe desktop (`>= 768px`): sidebar = `30%`, content = `70%` (folosiți proprietatea de CSS `width` și proprietatea `float: left;`).

Atenție!
- NU folosiți Bootstrap Grid!
- Folosiți doar CSS cu media queries;
- Lățimile celor două zone trebuie să fie definite în procente (`%`).

#### 3. Card •responsive* cu dimensiuni fluide

Creează un card simplu care:
- are lățimea 90% pe mobil
- are lățimea 60% pe desktop (`>= 992px`)
- textul din card să folosească `rem` (setați un `font-size` la alegere)
- spațierea internă să folosească `em` (setați un `margin` sau `padding` la alegere)

Pentru card puteți folosi o clasă specifică, de exemplu `.card-custom`. Cardul trebuie să fie centrat pe pagină - puteți face asta aplicând `margin: 0 auto;` pe card.
