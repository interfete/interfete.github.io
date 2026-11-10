---
layout: default
title: Laborator 06
nav_order: 7
nav_exclude: false
search_exclude: false
---

# CIW Științele Comunicării

## Laborator 06: Introducere în CSS

### Despre CSS

**CSS** (**C**ascading **S**tyle **S**heets) este limbajul folosit pentru a controla aspectul vizual al paginilor web create în **HTML**. În timp ce HTML definește structura și conținutul unei pagini, CSS stabilește cum arată acea pagină — culori, fonturi, dimensiuni de text, aliniere, distanțe, fundaluri sau poziționarea elementelor.

Prin separarea conținutului de stil, CSS permite crearea de site-uri ușor de întreținut, coerente și estetice. Acest laborator prezintă conceptele de bază despre stilizare, cum se aplică regulile CSS și cum se poate transforma o pagină web HTML simplă într-una atractivă și bine structurată vizual.

### Integrarea regulilor CSS într-o pagină web

Există **trei modalități** prin care putem aplica stiluri CSS unui document HTML. Toate folosesc aceeași sintaxă CSS, dar diferă prin locul unde sunt scrise și prin scopul lor:

#### 1. CSS inline

Stilurile sunt adăugate **direct unui element HTML**, folosind atributul `style`. Acest atribut se poate aplica pe toate tag-urile HTML prezente în `<body>`.

Adăugarea stilurilor CSS inline se folosește pentru stilizare rapidă, izolată, însă nu este recomandată pentru proiecte mari, deoarece neceită întreținere dificilă și încarcă vizual codul.

##### Exemplul 1: Reguli CSS aplicate folosind atributul `style`
```
<p style="color: blue; font-size: 18px;">Text colorat albastru și de mărime 18px.</p>
```

#### 2. CSS intern (în cadrul aceleiași paginii HTML)

Regulile CSS sunt scrise în interiorul unui tag `<style>` (*Atenție!* Este vorba de tag-ul `<style>`, nu de atributul `style` ca în varianta inline anterioară!).

Tag-ul `<style>` se adaugă în tag-ul `<head>` al paginii web.

Varianta aceasta este utilă atunci când dorim ca stilurile să se aplice doar acelei pagini și când numărul stilurilor aplicate este relativ mic. Spre deosebire de varianta inline, această variantă permite vizualizarea și manevrarea tuturor stilurilor din același punct.

##### Exemplul 2: Reguli CSS adăugate în zona de `<head>` a unei pagini web
```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Reguli CSS în zona de head</title>
    <style>
    p {
        color: green;
        font-size: 16px;
    }
    </style>
</head>
<body>
    <p>Text colorat verde și de mărime 16px.</p>
</body>
</html>
```

#### 3. CSS extern (într-un fișier separat CSS)

Varianta aceasta este **metoda recomandată** și cea mai folosită. Ea permite separarea scopurilor fiecărei pagini. Stilurile sunt adăugate într-un fișier separat, cu extensia `.css`, care este apoi conectat la pagina HTML folosind tag-ul `<link>` în cadrul tag-ului `<head>`. Astfel, browser-ul web va știi că are nevoie de un fișier CSS pentru a randa pagina.

##### Exemplul 3: Reguli de CSS adăugate într-un fișier extern CSS

**Fișierul styles.css:**
Acesta conține strict codul de CSS:
```
p {
  color: red;
  font-size: 14px;
}
```

**Fișierul HTML:**
Acesta conține doar tag-ul `<link>` cu adresa fișierului  CSS de încărcat: 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Reguli CSS din fișier extern</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <p>Text colorat roșu și de mărime 14px.</p>
</body>
</html>
```

#### Recomandare

Pentru site-uri reale (publice) este de preferat CSS-ul extern, deoarece:
- permite reutilizarea acelorași reguli în mai multe pagini HTML;
- face codul mai curat și mai ușor de întreținut (prin faptul că paginile HTML conțin strict cod HTML, iar paginile CSS conțin strict cod CSS).

### Sintaxa CSS

O regulă CSS descrie cum trebuie **stilizat un element HTML** și este formată din **două părți**:
- **selectorul CSS**, care indică ce *element* dorim să stilizăm;
- **blocul de declarații**, care conține una sau mai multe perechi formate din *proprietate* și *valoare* ce definesc stilul.

**Template de general CSS**
Exemplu de template de sintaxă CSS cu doi selectori și una-două proprietăți la fiecare:
```
selector1 {
    nume_proprietate1: valoare_proprietate1;
    nume_proprietate2: valoare_proprietate2;
}

selector2 {
    nume_proprietate1: valoare_proprietate3;
}
```

<mark>Atenție! Template-ul de mai sus prezintă doar structura generală. Numele proprietăților CSS sunt alese dintr-un set predefinit. Valorile proprietăților sunt specifice în funcție de fiecare proprietate.</mark>

**Exemplu de selector cu două reguli de CSS:**
```
p {
    color: blue;
    font-size: 18px;
}
```

Explicație template:
- `p` — este selectorul (indică elementul HTML vizat);
- `color` și `font-size` — sunt **proprietăți CSS**;
- `blue` și `18px` — sunt **valorile atribuite** acelor proprietăți;
- fiecare declarație se termină cu **punct și virgulă** `;`, iar toate declarațiile sunt încadrate între **accolade** `{ ... }`.

Astfel, această regulă:
- folosește selectorul `<p>`, astfel că se aplică tuturor elementelor de tip `<p>` (tuturor paragrafelor);
- aplică proprietatea `color` cu valoarea `blue`, care îi spune browser-ului să coloreze textul albastru;
- aplică proprietatea `font-size` cu valoarea `18px`, care îi spune browser-ului să seteze dimensiunea textului la 18px.

### Selectorii CSS

**Selectorii** sunt elementul de bază al CSS — ei indică *ce elemente HTML* vor fi afectate de regulile de stil.
Fiecare regulă CSS începe cu un selector, urmat de blocul de declarații. Prin selectori putem stiliza un singur element, un grup de elemente sau doar pe acelea care îndeplinesc anumite condiții.

#### 1. Selectori simpli

Aceștia se referă direct la numele elementului, la o clasă sau la un identificator:
```
p { color: blue; }          /* selectează toate paragrafele */
.intro { font-size: 18px; } /* selectează toate elementele cu clasa "intro" */
#header { background: gray; } /* selectează elementul cu id-ul "header" */
```

În codul de mai sus sunt folosiți următorii selectori:
- **Selector de element (tag):** vizează toate elementele HTML ce folosesc un anumit tag (`p`, `h1`, `table` etc.);
- **Selector de clasă (.):** aplică stilul tuturor elementelor care au atributul `class` cu valoarea respectivă;
- **Selector de id (#):** aplică stilul unui singur element cu acel `id` (unic în pagină).

Codul HTML care reflectă setările (după legarea regulilor CSS):
```
<p>Acest text este scris cu albastru.</p>
<div class="intro">Acest text este de dimensiune 18px.</div>
<div id="header">Această divizune are fundal gri.</div>
```

#### 2. Selectori de grupare

Permit aplicarea acelorași reguli mai multor elemente.

Fișier CSS:
```
h1, h2, h3 {
    color: darkblue;
}
```

Fișier HTML:
```
<h1>Antet de dimensiune 1 de culoare albastru închis.</h1>
<h2>Antet de dimensiune 2 de culoare albastru închis.</h2>
<h3>Antet de dimensiune 3 de culoare albastru închis.</h3>
```

#### 3. Selectori descendenți

Aplică stilul doar elementelor aflate *în interiorul* altor elemente.

Fișier CSS:
```
article p {
    color: gray;
}
```

Fișier HTML:
```
<article>
    <p>Textul acesta are culoarea gri.</p>
</article>
```

### Exerciții

1) Stilizare prin **selector de element**

Creează un fișier HTML simplu cu 3 paragrafe. Adaugă un text fictiv. Leagă la pagina HTML un fișier CSS care:
- colorează textul paragrafelor în albastru;
- schimbă fontul în Arial (folosind proprietatea `font-family`);
- centrează textul în pagină (folosind proprietatea `text-align`).

2) Folosirea **claselor CSS** și a selectorului cu punct (`.`)

Adaugă clase diferite pentru fiecare paragraf din pagina creată la exercițiul anterior.
```
<p class="intro">...</p>
<p class="info">...</p>
<p class="warning">...</p>
```

Adaugă în fișierul CSS reguli pentru clase (folosind selectorul cu punct - `.`), astfel încât:
- textul din `.intro` să fie de culoare verde;
- textul din `.info` să fie gri și italic (folosind propriertatea `font-style`);
- textul din `.warning` să fie roșu și îngroșat (folosind proprietatea `font-weight`).

3) Folosirea **ID-urilor** și a selectorului cu diez (`#`)

În pagina creată anterior adaugă un antet `<h1>` cu atributului `id="title"`.

În CSS adaugă reguli pentru ca strict acel antet:
- să fie aliniat centrat (folosind proprietatea `text-align`);
- să fie colorat în mov;
- să aibă un fundal deschis (culoarea este la alegere).

4) Selecție descendentă

În pagina HTML creată anterior adaugă următorul conținut:
```
<article>
  <h2>Titlu articol</h2>
  <p>Paragraf 1</p>
  <p>Paragraf 2</p>
</article>
<p>Paragraf 3</p>
```

În CSS schimbă culoarea textului doar pentru paragrafele din interiorul articolului (nu pentru toate `<p>` din pagină).

<mark>Paragraful 3 trebuie să rămână cu culoarea implicită (negru)!</mark>

5) Carte de vizită

Creează-ți propria „carte de vizită” cu următoarea structură în HTMML. Modifică datele cu datele tale.
```
<div class="card">
  <h2>Nume Student</h2>
  <p>Facultatea de Informatică</p>
  <p>Email: student@example.com</p>
</div>
```

În CSS:
- adaugă o margine subțire (folosind proprietatea `border: 1px solid black;`);
- setează un fundal deschis (folosind proprietatea `background-color`)
- centrează numele tău înăuntrul cărții de vizită.
