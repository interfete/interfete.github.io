# CIW Științele Comunicării

## Laborator 08: Selectori avansați în CSS

### Introducere

În CSS, selectorii reprezintă mecanismul prin care alegem elementele HTML pe care vrem să le stilizăm. Pe lângă selectorii de bază (de tag, de clasă, de id), CSS oferă o gamă largă de **selectori avansați** care permit target-area precisă a unor elemente în funcție de structură, poziție, atribute sau stare. Aceștia cresc controlul asupra stilurilor și reduc nevoia de a adăuga clase suplimentare în HTML.

În acest laborator vom explora patru categorii importante: **selectorii combinatori**, **selectorii de atribute**, **pseudo-clasele** și **pseudo-elementele**.

### Selectori combinatori

#### Descendent (A B)

Selectează orice element B aflat în interiorul lui A (la orice nivel).

```
div p {
    color: blue;
}
```

#### Copil (A > B)

Selectează doar copiii direcți.

```
ul > li {
    font-weight: bold;
}
```

#### Frate adiacent (A + B)

Selectează elementul B care apare imediat după A.

```
h2 + p {
    margin-top: 0;
}
```

#### Frate general (A ~ B)

Selectează toate elementele B care apar pe același nivel după A.

```
h2 ~ p {
    color: gray;
}
```

### Selectori de atribute

Permite selectarea elementelor în funcție de prezența sau valoarea unui atribut.

#### Prezența atributului

```
input[required] {
    border: 2px solid red;
}
```

#### Egalitate exactă

```
a[target="_blank"] {
    color: green;
}
```

#### Valoare care începe cu... (^=)

```
a[href$=".pdf"] {
    color: red;
}
```

#### Valoare care se termină cu... ($=)

```
a[href$=".pdf"] {
    color: red;
}
```

#### Valoare care conține... (*=)

```
div[class*="error"] {
    background: pink;
}
```

### Pseudo-clase

Pseudo-clasele descriu *stări dinamice* ale elementelor.

#### Stări ale linkurilor

```
a:hover { color: red; }
a:active { color: orange; }
a:visited { color: purple; }
```

#### Elementul primul sau ultimul copil

```
li:first-child { font-weight: bold; }
li:last-child { font-style: italic; }
```

#### Selectare pe poziție

```
li:nth-child(odd) { background: #eee; }
li:nth-child(3) { color: blue; }
```

### Pseudo-elemente

Pseudo-elementele creează *părți virtuale* ale elementelor.

#### `::before` și `::after`

```
p::before {
    content: "-> ";
}
p::after {
    content: " <-";
}
```

#### Selectarea primei litere

```
p::first-letter {
    font-size: 2em;
    color: red;
}
```

#### Selectarea primei linii

```
p::first-line {
    font-weight: bold;
}
```

### Exerciții

#### 1. Selectori combinatori

Creează următoarea structură HTML:
```
<div class="container">
    <h2>Titlu</h2>
    <p>Paragraf 1</p>
    <p>Paragraf 2</p>
    <section>
        <p>Paragraf în secțiune</p>
    </section>
</div>
```

**Cerințe:**
- Selectează doar paragrafele **copii direcți** ai div-ului.
- Colorează orice paragraf descendent al div-ului într-o culoare diferită.
- Fă ca paragraf 2 să aibă alt stil folosind `p + p`.

#### 2. Selectori de atribute

Creează un formular cu:
```
<input type="text" required>
<input type="email">
<input type="password" placeholder="Parola">
<a href="manual.pdf">Manual</a>
<a href="https://site.com">Site</a>
```

**Cerințe:**
- Pune border roșu câmpurilor required (`border: 1px solid red;`).
- Evidențiază linkurile către PDF.
- Evidențiază imaginile (poți adăuga una) care au sursa externă (începe cu `http`).

#### 3. Pseudo-clase

Listează 6 elemente `<li>` cu posturile tale TV preferate.

**Cerințe:**
- Marchează elementele impare cu un background.
- Marchează al treilea element cu o culoare specială.
- Fă ca la *hover* pe un element să se mărească ușor fontul.

#### 4. Pseudo-elemente

Scrie un paragraf de 3–4 rânduri. Îl poți genera folosim *Lorem ipsum* în Visual Studio Code.

**Cerințe:**
- Adaugă un simbol înainte și după paragraf.
- Mărește prima literă.
- Îngroașă prima linie.

#### 5. Exercțiu integrator (Opțional)

Creează un card HTML cu:
- titlu - numele tău
- imagine (de pe <a href="https://unsplash.com/" target="_blank">Unsplash</a>)
- descriere - semigrupa ta
- buton - *Contactează-mă*

**Cerințe:**
- Folosește un pseudo-element pentru a adăuga o banderolă ("NEW") în colț.
- Schimbă culoarea cardului la hover (pseudo-clasă).
- Stilizează doar butonul cu un selector de atribut (`button[type="button"]`).
- Folosește un selector combinator pentru a stiliza textul aflat imediat după imagine.
