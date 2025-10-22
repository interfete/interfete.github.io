# CIW Științele Comunicării

## Laborator 03: Tag-uri semantice HTML 5

### HTML 5

HTML (HyperText Markup Language) este limbajul care definește structura unei pagini web. El folosește etichete (tag-uri) pentru a indica rolul fiecărui element dintr-o pagină — de exemplu, ce este un titlu, un paragraf sau o imagine.

În versiunile mai vechi de HTML, multe pagini erau construite doar cu elemente de tip `<div>` și `<span>`, fără să indice semnificația conținutului.

Odată cu **HTML5**, au fost introduse **tag-urile semantice**, care ajută browser-ele, motoarele de căutare și tehnologiile asistive (ex. cititoare de ecran pentru persoanele cu dizabilități) să înțeleagă mai bine structura și sensul conținutului unei pagini.

### Ce sunt tag-urile semantice?

Un **tag semantic** este o etichetă HTML care descrie clar **rolul** și **conținutul** său.

Exemple de tag-uri semantice:
```
<header> conține partea de început a unei pagini sau secțiuni (ex: logo, titlu, meniu)</header>
<nav> conține link-uri de navigare</nav>
<article> conține un articol independent de restul conținutului</article>
<footer> conține informațiile de final (ex: contact, copyright)</footer>
```

Prin comparație, folosirea doar a `<div>`-urilor nu oferă aceste informații semantice (adică doar structurează informația).

### Tag-uri semantice importante în HTML5

#### `<header>`
Cuprinde antetul paginii sau antetul unei secțiuni.
```
<header><h1>Site Title</h1></header>
```

#### `<nav>`
Conține link-uri de navigare (de exemplu, meniul site-ului)
```
<nav>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
```

#### `<main>`
Marchează conținutul principal al paginii.
```
<main><p>Conținut principal</p></main>
```

#### `<section>`
Delimitează o secțiune logică a conținutului din cadrul unei pagini.
```
<section>
    <h2>Despre noi</h2>
    <p>Compania noastră activează în domeniul IT din anul 2000.</p>
</section>
```

#### `<article>`
Marchează un conținut independent, de exemplu un articol individual, o postare, un comentariu sau o recenzie.
```
<article>
    <h2>Iarna vine mai devreme în 2025</h2>
    <p>Sunt semne că vom avea o iarnă cu ger și multă zăpadă, spun meteorologii și climatologii. Frigul a venit deja de la sfârșitul lui septembrie, iar marți, la Miercurea Ciuc, s-a înregistrat un nou record de temperaturi negative: minus 9,7 grade.</p>
</article>
```

#### `<aside>`
Delimitează conținutul secundar (ex: bară laterală, reclame).
```
<aside>
    <h2>Articole similare</h2>
    ...
</aside>
```

#### `<footer>`
Marchează conținutul de final (ex: copyright, link-uri utile).
```
<footer>&copy; 2025 Companie SRL</footer>
```

#### `<figure>` și `<figcaption>`
Delimitează imagini, inclusiv cu descrierea lor.
```
<figure>
    <img src="img.jpg">
    <figcaption>Descriere imagine</figcaption>
</figure>
```

### Verificarea interpretării semantice
Validatorul oficial W3C (denumit Nu Html Checker) verifică nu doar dacă un document HTML este corect din punct de vedere sintactic, ci și dacă respectă anumite reguli semantice definite de standardele HTML5.

De exemplu, poate semnala situații în care un element semantic este folosit într-un context nepotrivit (cum ar fi un `<header>` plasat în interiorul unui `<p>`, sau un `<main>` folosit de mai multe ori într-o pagină).

De asemenea, validatorul avertizează când se utilizează tag-uri "depășite" (*deprecated*) sau când structura ierarhică a documentului (titluri, secțiuni, articole) nu respectă logica semantică a limbajului HTML5.

Astfel, validarea W3C ajută nu doar la depistarea erorilor tehnice, ci și la îmbunătățirea calității semantice a codului HTML, ceea ce contribuie la o interpretare mai corectă de către browsere, motoare de căutare și tehnologii asistive.

Validatorul W3C este disponibil aici: [https://validator.w3.org](https://validator.w3.org)

### Exerciții
1. Următorul cod produce o eroare în validator:

```
<!DOCTYPE html>
<html lang="ro">
<head>
  <meta charset="UTF-8">
  <title>Pagină test</title>
</head>
<body>
  <p>
    <header>
      <h1>Bine ați venit!</h1>
    </header>
    Acesta este un paragraf.
  </p>
</body>
</html>
```

Verificați care este eroarea și reparați-o. Este o eroare semantică sau de structură?

2. Și următorul cod produce o eroare în validator:

```
<!DOCTYPE html>
<html lang="ro">
<head>
  <meta charset="UTF-8">
  <title>Exemplu semantic greșit</title>
</head>
<body>
  <main>
    <article>
      <h1>Primul articol</h1>
      <p>Conținutul articolului...</p>
    </article>
    <main>
      <article>
        <h1>Al doilea articol</h1>
        <p>Mai mult conținut...</p>
      </article>
    </main>
  </main>
</body>
</html>
```

Care este eroarea de data aceasta și cum se repară? Este o eroare semantică sau de sintaxă?

3. Pornește de la următorul cod "nesemantic" și îmbunătățește-l folosind tag-uri semantice.

Transformă codul într-o versiune corectă semantic, cu `<header>`, `<nav>`, `<article>`, și `<footer>`.

<mark>Atenție! Codul de mai jos nu conține tag-urile `<html>`, `<head>` și `<body>`, pe care trebuie să le adăugați voi.</mark>

```
<div>
  <div>
    <h1>Blogul meu</h1>
  </div>
  <div>
    <a href="#">Acasă</a> | <a href="#">Despre</a> | <a href="#">Contact</a>
  </div>
  <div>
    <h2>Primul articol</h2>
    <p>Bun venit pe blog!</p>
  </div>
  <div>
    &copy; 2025 Blogul meu
  </div>
</div>
```

4. Descarcă fișierul <a href="lab03/example.xml" download>example.html</a> în calculator. Verifică conținutul său. Îmbunătățește codul astfel încât să cuprindă următoarele tag-uri semantice:
- `<header>` - să cuprindă zona de antet a site-ului
- `<main>` - să cuprindă conținutul principal și un link către imaginea <a href="lab03/zapada.jpg" download>zapada.jpg</a>
- `<nav>` - să cuprindă link-ul din cod și încă două link-uri
- `<footer>` - să cuprindă meniul de navigare creat anterior