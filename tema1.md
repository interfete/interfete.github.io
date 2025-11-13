# CIW Științele Comunicării

## Tema 1: Pagină de rezervare pentru ziua voastră

### Obiectiv

Realizarea unei pagini web simple pentru rezervarea unui loc la petrecerea de ziua voastră, care conține:
- informații generale prezentate într-un tabel;
- un formular pentru rezervare;
- un fișier CSS care oferă o prezentare plăcută.

Datele din formular trebuie trimise către un link unic generat de pe [https://webhook.site](https://webhook.site).

### Cerințe specifice

#### Structura HTML

##### Descriere generală

Pagina trebuie să aibă titlul `Zi de naștere *Vasile Popescu*`, unde *Vasile Popescu* este numele vostru. Acest titlu trebuie să apară în două locuri:
- în bara de browser (tag-ul `<title>`);
- în `<body>`-ul paginii într-un tag `<h1>` aflat într-un tag `<header>`.

##### Programul evenimentului

Informațiile despre programul evenimentului să fie prezentate într-un tabel HTML. Cuprindeți în tabel următoarele informații: sărbătorit, ora evenimentului, locația evenimentului, orașul evenimentului, durata.

Condiții:
- Tabelul trebuie să aibă un antet (un rând ce conține celule de tipul `<th>`);
- Tavelul trebuie să includă cel puțin o celulă cu `colspan` și una cu `rowspan`.

##### Formular rezervare

Vizitați [https://webhook.site](https://webhook.site) și obțineți link-ul vostru unic (generat aleator) - sub textul *Your unique URL*. Copiați și păstrați acest link. Pagina trebuie să includă un formular de rezervare care să trimită date către link-ul vostru unic.

Condiții:
- adăugați un formular (`<form>`) pentru rezervare, cu atributele `method="POST"` și `action="https://webhook.site/..."`, unde veți adăuga link-ul vostru unic;
- formularul trebuie să aibă câmpurile pentru: *nume participant*, *email*, *număr de persoane*, *comentarii* (hint: tag de tip `<textarea>`);
- câmpurile *nume participant*, *email* și *număr de persoane* trebuie să fie obligatorii (hint: atributul `required`);
- câmpul *email* trebuie să permită doar formate de tip e-mail;
- câmpul *număr de persoane* trebuie să permită doar numere între 1 și 4;
- formularul trebuie să aibă un buton *Trimite* care declanșează trimiterea datelor către link-ul unic al studentului de pe Webhook.site.

##### Stilizarea paginii

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

##### Trimiterea temei

Tema se va arhiva într-o arhivă ZIP cu nume de forma `IDMoodle_Grupa.zip`, de exemplu `874761_411H.zip`. Arhiva și va conține:
- fișierul `index.html`
- fișierul `style.css`
- un fișier `webhook.txt` ce va conține doar link-ul vostru unic

##### Punctaj

- Structura generală a paginii HTML (existență `DOCTYPE`, `<head>`, `<title>`, `<body>`, `<header>`) (**1p**)
- Tabel HTML (existență celul antet `<th>`, existență atribute `colspan` și `rowspan`) (**1p**)
- Formular HTML funcțional (datele ajung pe link-ul unic) (**3p** - vor fi testate 3 scenarii)
- Formularul verifică regulile de validare (nume obligatoriu, e-mail corect, număr de persoane între 1 și 3) (**1p**)
- Fișierul CSS este legat corect la fișierul HTML (**1p**)
- Selectori CSS (minim un selector de tag, unul de clasă și unul de id) (**1p**)
- Aspect vizual plăcut (**1p**)

##### Depunctări (din 100p)
- pagina nu este validă pe [Validator](https://validator.w3.org/) **-30p**
- link-ul Webhook.site nu este unic (apare la minim 2 studenți) **-100p**
- temă copiată **-100p**
