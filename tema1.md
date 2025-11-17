# CIW Științele Comunicării

## Tema 1: Pagină de rezervare pentru ziua voastră

### Obiectiv

Realizarea unei **pagini web simple pentru rezervarea unui loc la petrecerea de ziua voastră**, care conține:
- informații generale prezentate într-un tabel;
- un formular pentru rezervare;
- un fișier CSS care oferă o prezentare plăcută.

Datele din formular trebuie trimise către un link unic generat de pe [https://webhook.site](https://webhook.site).

### Date calendaristice

**Data publicării:** 14.11.2025

**Soft deadline:** 28.11.2025, ora 23:59:59

**Hard deadline:** 05.12.2025, ora 23:59:59

- Se aplică o depunctare de **1/10p** pentru fiecare zi de întârziere de la *soft deadline* până la *hard deadline*!
- După *hard deadline* nu se mai poate trimite tema!

### Cerințe specifice

#### 1. Descriere generală

<!-- Ziua Izabelei -->

Pagina trebuie să aibă titlul `Zi de naștere *Vasile Popescu*`, unde *Vasile Popescu* este numele vostru. Acest titlu trebuie să apară în două locuri:
- în bara de browser (tag-ul `<title>`);
- în `<body>`-ul paginii într-un tag `<h1>` aflat într-un tag `<header>`.

#### 2. Programul evenimentului

Informațiile despre programul evenimentului să fie prezentate într-un tabel HTML. Cuprindeți în tabel următoarele informații: sărbătorit, ora evenimentului, locația evenimentului, orașul evenimentului, durata.

Condiții:
- Tabelul trebuie să aibă un antet (un rând ce conține celule de tipul `<th>`);
- Tabelul trebuie să includă cel puțin o celulă cu `colspan` și una cu `rowspan`.

#### 3. Formular rezervare

Vizitați [https://webhook.site](https://webhook.site) și obțineți link-ul vostru unic (generat aleator) - sub textul *Your unique URL*. Copiați și păstrați acest link. Pagina trebuie să includă un formular de rezervare care să trimită date către link-ul vostru unic.

##### Condiții formular:
- adăugați un formular (`<form>`) pentru rezervare, cu atributele `method="POST"` și `action="https://webhook.site/..."`, unde veți adăuga link-ul vostru unic;
- formularul trebuie să aibă câmpurile pentru: *nume participant*, *email*, *număr de persoane*, *comentarii* (hint: tag de tip `<textarea>`);
- câmpurile *nume participant*, *email* și *număr de persoane* trebuie să fie obligatorii (hint: atributul `required`);
- câmpul *email* trebuie să permită doar formate de tip e-mail;
- câmpul *număr de persoane* trebuie să permită doar numere între 1 și 4;
- formularul trebuie să aibă un buton *Trimite* care declanșează trimiterea datelor către link-ul unic al studentului de pe Webhook.site.
<!-- undeva în pagină să apară Robin Hood -->

#### 4. Stilizarea paginii

Creeați un fișier separat `style.css` și legați-l în pagină prin `<link rel="stylesheet" href="style.css">`.
Adaugați cel puțin:
- un selector de tag
- un selector de clasă
- un selector de id

Fiecare selector va defini minim 2 reguli. Exemple de elemente pe care le puteți stiliza:
- tabelul (culori și spațiere);
- textul din `<h1>` și antetul paginii;
- formularul (aliniere, spațiere între câmpuri);
- butonul de trimitere (culoare, mărime font);

### Trimiterea temei

Tema se va arhiva într-o arhivă ZIP cu nume de forma `IDTeams_Grupa.zip`, de exemplu `874761_411H.zip`, unde `IDTeams` este ID-ul vostru unic de pe Microsoft Teams, iar `411H` este grupa voastră.  Arhiva va conține următoarele 3 fișiere:
- fișierul `index.html` cu codul HTML
- fișierul `style.css` cu codul CSS (legat la fișierul HTML)
- un fișier `webhook.txt` ce va conține doar link-ul vostru unic pe prima linie

Arhiva se va trimite prin Moodle la următoarea adresă: <a href="https://bit.ly/ciw-tema1" taget="_blank">https://bit.ly/ciw-tema1</a>.

### Barem notare (max. 10p)

1. **Structura generală** a paginii HTML (existență `DOCTYPE`, `<head>`, `<title>`, `<body>`, `<header>`) (**1p**)
1. **Tabel** HTML (existență celul antet `<th>`, existență atribute `colspan` și `rowspan`) (**2p**)
1. **Formular** HTML funcțional (datele ajung pe link-ul unic) (**3p** - vor fi testate 3 scenarii)
1. Formularul verifică **regulile de validare** (nume obligatoriu, e-mail corect, număr de persoane între 1 și 3) (**1p**)
1. **Fișierul CSS** este legat corect la fișierul HTML (**1p**)
1. **Selectori CSS** (minim un selector de tag, unul de clasă și unul de id) (**1p**)
1. **Aspect vizual** plăcut (**1p**)

#### Depunctări (din 10p)

- pagina nu este validă pe [Validator](https://validator.w3.org/) (apar erori - cu roșu; *Warning*-urile nu contează!) (**-3p**)
- **-1/10p** pentru fiecare zi de întârziere față de *soft deadline* până la *hard deadline*
- link-ul *Webhook.site* nu este unic (apare la minim 2 studenți) (**-10p**)
- tema este copiată (**-10p**)

#### Limitări

- Majoritatea cerințelor din baremul de notare se vor testa folosind un script automat.
- Numirea incorectă a arhivei duce la punctaj zero pe temă.
- Lipsa cel puțin a unuia dintre fișiere din arhivă (fișier HTML, fișier CSS, fișier webhook) duce la punctaj zero pe temă.
