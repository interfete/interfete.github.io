# CIW Științele Comunicării

## Laborator 06: Introducere în CSS

### Despre CSS

**CSS (Cascading Style Sheets)** este limbajul folosit pentru a controla aspectul vizual al paginilor web create în HTML. Dacă HTML definește structura și conținutul unei pagini, CSS stabilește cum arată acea pagină — culori, fonturi, dimensiuni, aliniere, distanțe, fundaluri sau poziționarea elementelor. Prin separarea conținutului de stil, CSS permite crearea de site-uri mai ușor de întreținut, mai coerente și mai estetice. În acest laborator, studenții vor învăța conceptele de bază despre stilizare, cum se aplică regulile CSS și cum pot transforma o pagină HTML simplă într-una atractivă și bine structurată vizual.

### Modurile de a adăuga reguli CSS într-o pagină web

Există **trei modalități principale** prin care putem aplica stiluri CSS unui document HTML. Toate folosesc aceeași sintaxă CSS, dar diferă prin locul unde sunt scrise și prin scopul lor:

#### 1. CSS inline

Stilurile sunt adăugate **direct în interiorul unui element HTML**, prin atributul `style`.
Se folosește pentru modificări rapide sau izolate, dar nu este recomandat pentru proiecte mari.


##### Exemplul 1 - Regulă CSS adăugată folosind atributul `style`
```
<p style="color: blue; font-size: 18px;">Text colorat albastru și de mărime 18px.</p>
```

#### 2. CSS intern (în cadrul paginii HTML)

Regulile CSS sunt scrise în interiorul tag-ului `<style>` (*Atenție!* Este vorba de tag-ul `<style>`, nu de atributul `style` ca în varianta anterioară!), adăugat în zona de `<head>` a paginii web.
Este util atunci când vrei ca stilurile să se aplice doar acelei pagini.

##### Exemplul 2 - Reguli CSS adăugate în zona de `<head>` a unei pagini web
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

#### 3. CSS extern (într-un fișier separat)

Este metoda **cea mai recomandată**. Stilurile sunt salvate într-un fișier separat, cu extensia `.css`, care este apoi conectat la pagina HTML prin tag-ul `<link>` din `<head>`.

##### Exemplul 3 - Reguli de CSS adăugate într-un fișier extern

**Fișierul styles.css:**
```
p {
  color: red;
  font-size: 14px;
}
```

**Fișierul HTML:**
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

Pentru site-uri reale, este preferat CSS-ul extern, deoarece permite reutilizarea acelorași reguli în mai multe pagini și face codul mai curat și mai ușor de întreținut.

### Sintaxa CSS

O regulă CSS descrie cum **trebuie stilizat un element HTML** și este formată din **două părți principale**:
- **selectorul**, care indică ce *element* dorim să stilizăm;
- **blocul de declarații**, care conține una sau mai multe *proprietăți* și *valori* ce definesc stilul.

**Structură generală CSS:**
```
selector {
    proprietate1: valoare1;
    proprietate2: valoare2;
}
```

**Exemplu:**
```
p {
    color: blue;
    font-size: 18px;
}
```
Această regulă se aplică tuturor elementelor `<p>` (paragrafe), colorând textul în albastru și mărind dimensiunea fontului la 18px.

**Explicație:**
- `p` — este selectorul (indică elementul HTML vizat).
- `color` și `font-size` — sunt **proprietăți CSS**.
- `blue` și `18px` — sunt valorile atribuite acelor proprietăți.
- fiecare declarație se termină cu **punct și virgulă (;)**, iar toate declarațiile sunt încadrate între **accolade { }**.

### Selectorii CSS

**Selectorii** sunt elementul de bază al CSS — ei indică *ce elemente HTML* vor fi afectate de regulile de stil.
Fiecare regulă CSS începe cu un selector, urmat de blocul de declarații. Prin selectori putem stiliza un singur element, un grup de elemente sau doar acelea care îndeplinesc anumite condiții.

#### 1. Selectori simpli

Aceștia se referă direct la numele elementului, la o clasă sau la un identificator:
```
p { color: blue; }          /* toate paragrafele */
.intro { font-size: 18px; } /* toate elementele cu clasa "intro" */
#header { background: gray; } /* elementul cu id-ul "header" */
```

- **Selector de element (tip):** vizează toate elementele HTML de un anumit tip (`p`, `h1`, `table` etc.).
- **Selector de clasă (.):** aplică stilul tuturor elementelor care au atributul `class` cu valoarea respectivă.
- **Selector de id (#):** aplică stilul unui singur element cu acel `id` (unic în pagină).

Codul HTML care reflectă setările (după legarea regulilor CSS):
```
<p>Acest text este scris cu albastru.</p>
<div class="intro">Acest text este de dimensiune 18px.</div>
<div id="header">Această divizune are fundal gri.</div>
```

#### 2. Selectori de grupare

Permit aplicarea acelorași reguli mai multor elemente:
```
h1, h2, h3 {
    color: darkblue;
}
```

Codul HTML care reflectă setările (după legarea regulilor CSS):
```
<h1>Antet de dimensiune 1 de culoare albastru închis.</h1>
<h2>Antet de dimensiune 1 de culoare albastru închis.</h2>
<h3>Antet de dimensiune 1 de culoare albastru închis.</h3>
```


#### 3. Selectori descendenți

Aplică stilul doar elementelor aflate *în interiorul* altor elemente:
```
article p {
    color: gray;
}
```

Codul HTML care reflectă setările (după legarea regulilor CSS):
```
<article>
    <p>Textul acesta are culoarea gri.</p>
</article>
```

### Exerciții

1) Stilizare prin selector de element

Creează un fișier HTML simplu cu 3 paragrafe. Adaugă un fișier CSS care:
- colorează textul paragrafelor în albastru;
- schimbă fontul în Arial (folosind proprietatea `font-family`);
- centrează textul în pagină (folosind proprietatea `text-align`).

2) Folosirea claselor

Adaugă clase diferite pentru fiecare paragraf:
```
<p class="intro">...</p>
<p class="info">...</p>
<p class="warning">...</p>
```

În fișierul CSS:
- fă textul din `.intro` de culoare verde;
- fă textul din `.info` gri și italic;
- fă textul din `.warning` roșu și îngroșat.

3) Folosirea ID-urilor
Creează un titlu `<h1>` cu `id="title"`.
În CSS, fă-l:
- aliniat centrat;
- colorat în mov;
- cu un fundal deschis.

4) Selecție descendentă
În HTML adaugă:
```
<article>
  <h2>Titlu articol</h2>
  <p>Paragraf 1</p>
  <p>Paragraf 2</p>
</article>
<p>Paragraf 3</p>
```

În CSS schimbă culoarea textului doar pentru paragrafele din interiorul articolului (nu pentru toate `<p>` din pagină). <mark>Paragraful 3 trebuie să rămână cu culoarea implicită (negru)!</mark>

5) Carte de vizită
Creează-ți propria „carte de vizită” cu următoarea structură. Modifică datele cu datele tale.
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
