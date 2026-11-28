---
layout: default
title: Tema 1
nav_order: 14
nav_exclude: true
search_exclude: true
---

### CIW Științele Comunicării
#### Tema 1: Pagină de rezervare pentru ziua voastră

##### Obiectiv
Realizarea unei **pagini web simple pentru rezervarea unui loc la petrecerea de ziua voastră**, care conține:
* informații generale despre eveniment prezentate într-un tabel;
* un formular funcțional pentru rezervare;
* un cod personal de acces derivat din numele vostru;
* un fișier CSS de bază care oferă o prezentare clară și lizibilă.

Datele din formular trebuie trimise către un link unic generat de pe [https://webhook.site](https://webhook.site).

---

##### Date calendaristice
* **Data publicării:** 28.11.2026
* **Soft deadline:** 05.12.2026, ora 23:59:59
* **Hard deadline:** 12.12.2026, ora 23:59:59

* Se aplică o depunctare de **1p** pentru fiecare zi de întârziere față de *soft deadline* până la *hard deadline* (maxim 7 zile)!
* După *hard deadline* nu se mai poate trimite tema!

---

##### Cerințe specifice

###### 1. Descriere generală și cod personal de acces
Pagina (`index.html`) trebuie să aibă structura completă și corectă de HTML5 (`<!DOCTYPE html>`, `<html>`, `<head>`, `<title>`, `<body>`).

* **Titlul paginii:** trebuie să fie *Zi de naștere Vasile Popescu*, unde *Vasile Popescu* este numele vostru real. Acest titlu trebuie să apară în două locuri:
  * în bara de browser (tag-ul `<title>`);
  * în `<body>`-ul paginii, într-un tag `<h1>` aflat într-un tag `<header>`.
* **Cod personal de acces (obligatoriu):** în `<header>` (sub `<h1>`), adăugați un paragraf cu atributul `id="cod-acces"` care să conțină doar **inițiala primului vostru prenume urmată de inițiala primului vostru nume** (cu majuscule, fără spații sau puncte între ele).
  * *Exemplu:* Pentru studentul **Andrei Popescu**, codul este `AP`, iar tag-ul va arăta astfel:
    `<p id="cod-acces">AP</p>`
  * *Atenție:* Codul este verificat automat în raport cu numele vostru din Moodle. Nu lăsați exemplul `AP` dacă nu sunt inițialele voastre!

###### 2. Programul evenimentului
Informațiile despre programul evenimentului vor fi prezentate într-un **tabel HTML** (`<table>`). Tabelul trebuie să conțină un antet și următoarele informații: **sărbătorit**, **data și ora** și **locația**.

Condiții de structură pentru tabel:
* Tabelul trebuie să aibă un rând de antet format din celule `<th>` (de ex. 2 coloane: *Detaliu* și *Informație*);
* Tabelul trebuie să includă **cel puțin o celulă cu `colspan`** (de ex. un rând de titlu sau o notă finală pe toată lățimea tabelului) și **cel puțin o celulă cu `rowspan`** (de ex. gruparea a două rânduri precum *Locația* și *Orașul* sub aceeași categorie).

###### 3. Formular rezervare
Vizitați [https://webhook.site](https://webhook.site) și obțineți link-ul vostru unic (generat aleator) — sub textul *Your unique URL*. Copiați și păstrați acest link. Pagina trebuie să includă un formular de rezervare care să trimită date către link-ul vostru unic.

Condiții formular:
* adăugați un formular (`<form>`) pentru rezervare, cu atributele `method="POST"` și `action="https://webhook.site/..."`, unde veți adăuga link-ul vostru unic;
* fiecare câmp de intrare trebuie să aibă un atribut `name` sugestiv (fără spații/diacritice, ex. `nume`, `email`, `persoane`, `comentarii`), astfel încât datele să poată fi citite de către browser la trimiterea formularului;
* formularul trebuie să aibă câmpurile pentru: *nume participant*, *e-mail participant*, *număr de persoane*, *comentarii* (hint: tag `<textarea>`);
* câmpurile *nume participant*, *e-mail participant* și *număr de persoane* trebuie să fie obligatorii (hint: atributul `required`);
* câmpul *-email participant* trebuie să permită doar formate de tip e-mail (`type="email"`);
* câmpul *număr de persoane* trebuie să permită doar numere între 1 și 3 (`type="number"`, `min="1"`, `max="3"`);
* formularul trebuie să aibă un buton *Trimite* (`<button type="submit">` sau `<input type="submit">`) care declanșează trimiterea datelor către link-ul unic al studentului de pe Webhook.site.

###### 4. Stilizarea paginii (CSS de bază)
Creați un fișier separat `style.css` și legați-l în `<head>`-ul paginii prin `<link rel="stylesheet" href="style.css">`. Folosiți doar reguli CSS de bază (fără stiluri inline `style="..."` în fișierul HTML).

Adăugați cel puțin:
* un **selector de tag** (ex. `body`, `table`, `h1`);
* un **selector de clasă** (ex. `.formular-rezervare`);
* un **selector de id** (recomandat pentru `#cod-acces`).

Fiecare dintre cei 3 selectori obligatorii va defini **minim 2 reguli CSS**.

###### 5. Validarea codului HTML și CSS
Înainte de trimitere, verificați ambele fișiere folosind validatoarele oficiale W3C:
* **Validator HTML:** [https://validator.w3.org/](https://validator.w3.org/) (codul din `index.html` nu trebuie să aibă erori — mesajele cu roșu; *Warning*-urile nu se depunctează);
* **Validator CSS:** [https://jigsaw.w3.org/css-validator/](https://jigsaw.w3.org/css-validator/) (codul din `style.css` nu trebuie să aibă erori).

---

##### Politica privind utilizarea instrumentelor AI / LLM
Această temă evaluează capacitatea voastră de a scrie și înțelege cod HTML5 și CSS de bază.
* Puteți folosi instrumente AI/LLM strict pentru a înțelege concepte teoretice (ex. *„cum funcționează atributul rowspan”*), **nu pentru a genera rezolvarea temei**.
* Utilizarea unui LLM pentru generarea codului HTML/CSS al temei (identificabilă prin texte demonstrative generice, cod de acces necorelat cu numele studentului, structuri standardizate neadaptate sau nepotriviri între fișiere și alte elemente specifice LLMs) atrage o depunctare de **-3p**.

---

##### Trimiterea temei
Tema se va arhiva într-o arhivă **ZIP** cu nume de forma `IDTeams_Grupa.zip`, de exemplu `874761_411H.zip`, unde `IDTeams` este ID-ul vostru unic de pe Microsoft Teams, iar `411H` este grupa voastră. Arhiva va conține **exact** următoarele 4 fișiere (direct în rădăcina arhivei, fără subfoldere):
* `index.html` — cu codul HTML;
* `style.css` — cu codul CSS (legat la fișierul HTML);
* `webhook.txt` — ce va conține **doar** link-ul vostru unic `https://webhook.site/...` pe prima linie (fără alt text);
* `screenshot.png` (sau `.jpg`) — o captură de ecran cu pagina întreagă deschisă în orice browser web.

Arhiva se va trimite prin Moodle la următoarea adresă: <a href="https://bit.ly/ciw-tema1" target="_blank">https://bit.ly/ciw-tema1</a>.

---

##### Barem notare (max. 10p)
1. **Structura generală** a paginii HTML (`DOCTYPE`, `<html>`, `<head>`, `<title>`, `<body>`) (**1p**)
2. **Codul personal de acces** (`#cod-acces`) prezent în structura cerută și corect corelat cu numele studentului (**1p**)
3. **Tabel HTML** complet (existență celule antet `<th>`, existență atribute `colspan` și `rowspan` folosite logic) (**2p**)
4. **Formular HTML** funcțional (`method="POST"`, `action` identic cu `webhook.txt`, atribute `name` și buton *Trimite*) (**2p**)
5. **Reguli de validare** în formular (nume, email și număr persoane obligatorii, format email, număr persoane între 1 și 3) (**1p**)
6. **Fișierul CSS** este legat corect la fișierul HTML (`<link rel="stylesheet" href="style.css">`) (**1p**)
7. **Selectori CSS** (minim un selector de tag, unul de clasă și unul de id, fiecare cu minim 2 reguli) (**1p**)
8. **Aspect vizual** lizibil și îngrijit, fără stiluri inline (**1p**)

###### Depunctări (din 10p)
* pagina HTML nu este validă pe [W3C Markup Validator](https://validator.w3.org/) (apar erori cu roșu; *Warning*-urile nu se depunctează) (**-3p**)
* fișierul CSS nu este valid pe [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) (apar erori) (**-3p**)
* folosirea unui LLM / AI pentru generarea rezolvării (**-3p**)
* **-1p** pentru fiecare zi de întârziere față de *soft deadline* până la *hard deadline* (maxim 7 zile)
* link-ul *Webhook.site* nu este unic (apare la minim 2 studenți) (**-10p**)
* tema este copiată de la alt student (**-10p**)

###### Limitări
* Majoritatea cerințelor din baremul de notare și depunctările se vor testa folosind un script automat.
* Numirea incorectă a arhivei duce la punctaj zero pe temă.
* Lipsa cel puțin a unuia dintre cele 4 fișiere din arhivă (`index.html`, `style.css`, `webhook.txt`, `screenshot.png`/`.jpg`) sau plasarea lor într-un subfolder duce la punctaj zero pe temă.