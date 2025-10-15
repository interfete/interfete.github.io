# CIW Științele Comunicării

## Laborator 02: XML și HTML

### XML

XML (e**X**tensible **M**arkup **L**anguage) este un limbaj de **marcare** utilizat pentru a stoca și a transporta date într-o manieră structurată și ușor de înțeles atât de oameni, cât și de calculatoare. XML descrie ce reprezintă datele. Structura sa se bazează pe **tag-uri** definite de utilizator, ceea ce oferă o mare flexibilitate în organizarea informației.

Un fișier XML este format dintr-un set de elemente ierarhice, delimitate de etichete de deschidere (`<nume>`) și închidere (`</nume>`). Aceste elemente pot conține text sau alte elemente imbricate (elemente "copii").

```
<persoana>
    <nume>Popescu</nume>
    <prenume>Vasile</prenume>
</persoana>
```

Tag-urile pot avea atribute care descriu proprietăți suplimentare:

```
    ...
    <prenume limba="ro">Vasile</prenume>
    <prenume limba="ru">Vasily</prenume>
    ...
```

XML este utilizat în aplicații web și în schimbul de date între sisteme diferite, deoarece permite definirea de **formate personalizate** care pot fi validate și interpretate automat (prin intermediul altor script-uri/programe). Este frecvent folosit împreună cu alte tehnologii precum DTD (Document Type Definition) sau XML Schema pentru validarea structurii documentului.

### HTML
HTML (**H**yper**T**ext **M**arkup **L**anguage) este folosit pentru afișarea informațiilor în paginile web. El definește structura vizuală a conținutului — cum ar fi paragrafe, titluri, tabele sau imagini — și este interpretat de browser-ele web pentru a reda pagina către utilizator într-un format accesibil vizual (user-friendly).

XML, în schimb, este proiectat pentru stocarea și schimbul de date, nu pentru prezentare. Cu toate acestea, HTML este derivat din XML, HTML fiind de fapt XML cu niște reguli clare (doar anumite nume de tag-uri pot fi folosite, doar anumite atribute pot fi folosite pe un anume tag, etc.).

#### HTML 5

HTML 5 este cea mai recentă versiune a limbajului HTML și reprezintă standardul actual pentru construirea paginilor web moderne. A fost creat pentru a îmbunătăți structura și funcționalitatea web-ului, oferind suport nativ pentru conținut multimedia (fișiere audio, video), grafică (prin tag-ul `<canvas>`), aplicații interactive și formulare avansate, fără a fi nevoie de plugin-uri externe precum Adobe Flash, așa cum era necesar anterior (în HTML 4).

Un exemplu simplu de pagină de tip "Hello, world!" în HTML5 este următorul:

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hello World</title>
</head>
<body>
  <h1>Hello, World!</h1>
  <p>Welcome to my first HTML5 page.</p>
</body>
</html>
```

În acest exemplu:
- `<!DOCTYPE html>` specifică faptul că documentul folosește standardul HTML5.
- Etichetele `<html>`, `<head>` și `<body>` definesc structura de bază a unei pagini web.
- Textul "Hello, world!" este afișat ca titlu principal pe pagină.

### Validarea unui document HTML 5

Validarea unui document HTML5 reprezintă procesul prin care se verifică dacă pagina web respectă regulile și standardele definite de **W3C** (**W**orld **W**ide **W**eb Consortium). Scopul validării este de a identifica erori de sintaxă, etichete neînchise sau atribute incorecte, pentru a asigura o afișare corectă și uniformă în toate browser-ele.

Pentru a valida un document HTML5, se poate folosi validatorul oficial W3C, disponibil online la adresa:
[https://validator.w3.org/](https://validator.w3.org/)

Există trei moduri principale de validare:
1. Prin URL – introduci adresa unei pagini web deja publicate.
2. Prin încărcarea unui fișier local – utile când lucrezi la o pagină pe calculatorul propriu.
3. Prin introducerea directă a codului sursă – poți lipi (Paste) conținutul HTML în formularul de validare.

Dacă documentul respectă specificațiile HTML5, validatorul va afișa mesajul:
<cite>Document checking completed. No errors or warnings to show.</cite>

În caz contrar, vor fi afișate erorile și avertismentele, împreună cu numărul liniei unde apar, pentru a putea fi corectate ușor.

<mark>Validarea este o bună practică recomandată pentru toate proiectele web, mai ales în contextul educațional, deoarece contribuie la crearea de pagini conforme, compatibile și ușor de întreținut.</mark>

#### Erori comune in HTML 5

În realizarea paginilor web cu HTML5, apar frecvent anumite erori care pot afecta afișarea, funcționalitatea sau validarea documentului. Iată câteva dintre cele mai comune:

1. Etichete neînchise sau scrise incorect (ex.: lipsește `</p>`)
2. Atribute incorecte sau lipsă de ghilimele (ex.: `<img src=imagine.jpg alt=Imagine>`)
3. Lipsesc atribute obligatorii (ex.: `<img src=imagine.jpg>`)
4. Lipsa declarației DOCTYPE
5. Etichete HTML vechi (deprecated) - de obicei din HTML 4
6. Structură incorectă a documentului

### Exerciții
1. Deschideți fișierul <a href="lab02/recipe.xml" download>recipe.xml</a> în browser. Observați modul interactiv în care este afișat conținutul.
2. Creați un fișier numit `student.xml` care să descrie informațiile de bază despre un student: nume, specializare, an de studiu și notă finală.
3. Deschideți pagina <a href="lab02/hello.html" download>hello.html</a> în browser. Găsiți zona în care apare titlul paginii (pe bara de titlu a browser-ului). Modificați titlul de pe bară în "Goodbye World" în loc de "Hello Wolrd".
4. Modificați paragraful din pagină (tag-ul `<p>`) astfel încât cuvântul **first** să fie scris cu bold - folosiți tag-ul `<b>`.
5. Copiați conținutul fișierului <a href="lab02/wrong.html" download>wrong.html</a> în Validator-ul W3C. Găsiți cele 3 erori și remediați-le.
6. Verificați folosind validatorul:
- site-ul [eMAG](https://emag.ro)
- site-ul [Știrile ProTV](https://stirileprotv.ro)
Sunt valide? Studiați erorile identificate.

<mark>Dacă o pagină nu poate fi verificată direct prin intermediul URL-ului, copiați codul sursă (click-dreapta => View Page Source) și lipiți-l (Paste) în Validator. Unele pagini au politici restrictive în privința script-urilor care le accesează!</mark>

