---
layout: default
title: Laborator 04
nav_order: 5
nav_exclude: false
search_exclude: false
---

# CIW Științele Comunicării

## Laborator 04: Formulare în HTML

### Formulare

Formularele HTML permit interacțiunea dintre utilizator și site-ul web. Ele colectează date (de exemplu nume, prenume, e-mail, mesaje text) și le trimit către un server web pentru procesare.

Scopul acestui laborator este de a înțelege structura unui formular, tipurile de câmpuri disponibile și modul de trimitere a datelor.

### Elemente de bază

Un formular HTML se definește cu tag-ul `<form>`: 

```
<form action="procesare.php" method="post">
  <!-- campuri de completat date -->
</form>
```

Atribute importante:
- `action` - adresa unde sunt trimise datele (spre un fișier sau server).
- `method` – modul de trimitere a datelor
    - **GET** - vizibil în URL (pentru căutări, filtrări, etc.);
	- **POST** - ascuns în corpul cererii (pentru date sensibile).

Exemplu de formular:
```
<form action="procesare.php" method="post">
    <label for="name">Nume:</label>
    <input type="text" id="name" name="name">
    <button type="submit">Trimite</button>
</form>
```

### Câmpuri de tip `input`

Folosesc tag-ul `<input>` și permit 

#### Text simplu

Scop: Introducere text scurt (de ex.: nume, prenume, oraș).

```
<input type="text">
```

#### Câmp de parolă

Scop: Ascunde caracterele introduse.

```
<input type="password">
```

#### Câmp de e-mail

Scop: Verifică formatul e-mail-ului atunci când se trimite formularul.

```
<input type="email">
```

#### Câmp numeric

Scop: Acceptă doar valori numerice. Permite setarea valorile minimă și maximă, precum și setarea pasului.

```
<input type="number" min="0" max="100">
```

#### Câmp tip dată

Scop: Selector de dată - afișează un calendar și permite selecția datei.

```
<input type="date">
```

#### Câmp de selecție tip checkbox

Scop: Alegere multiplă a unor opțiuni disponibile (ex.: tipuri de sosri la comanda de kebab).

```
<input type="checkbox">
```

#### Câmp de selecție tip radio buttons

Scop: Alegere unică între mai multe opțiuni. Atenție! Valoarea atributului `name` trebuie să fie aceeași ca să poată exista alegerea exclusivă!

```
<input type="radio" name="opt">
```

#### Câmp de text extins

Scop: Completarea unui text lung (ex.: comentarii). Atenție! Acest câmp NU este *self-closing*.

```
<textarea></textarea>
```

#### Buton

Scop: Trimiterea datelor din formular.

```
<button type="submit">
```

#### Reset

Scop: Resetează câmpurile la valoarea lor inițială (care în general este goală).

```
<button type="reset">
```

### Webhook.site

<a href="https://webhook.site/" target="_blank">Webhook.site</a> permite folosirea unei adrese "fake" pentru simularea trimiterii datelor către un server. De exemplu, scopul ar putea fi testarea funcționării unui formular.

Fiecare adresă Webhook acceptă un număr limită de request-uri (de exemplu 100), din considerente de a nu spama server-ului respectiv.

Codul următor trimite datele din formular către o adresă unică generată la momentul scrii acestui cod:
```
<form action="https://webhook.site/2841caa4-682e-4a49-9cdc-19b57602fd12" method="post">
    <p>
        <label for="camp_nume">Nume:</label>
        <input type="text" name="nume" id="camp_nume">
    </p>
    <p>
        <button>Trimite</button>
    </p>
</form>
```

Dacă completez date în acest formular și acționez butonul "Trimite", datele (valoarea din câmpul de nume) va fi trimisă către adresa web specificată.

Dacă vizitez în browser-ul web adresa din câmpul de `action`, voi vedea toate cererile trimise către acel URL.

### Exerciții - Formular simplu de contact

Veți crea un formular simplu de contact care va trimite date către un server "fake". Vom testa faptul că datele ajung la acest server, însă NU vor ajunge direct într-o căsuță de e-mail.

1) **Structură de bază**

Veți crea un formular simplu de contact cu 3 câmpuri (nume, e-mail, mesaj) și buton de trimitere.

- Creează o pagină nouă HTML în Visual Studio Code - `contact.html`
- Folosește scurtătura de generare template HTML (*Shift* + *!*) pentru a obține scheletul HTML de pornire.
- Modifică titlul din bara browser-ului în *Contact Vasile Popescu*, unde *Vasile Popescu* îl vei înlocui cu numele tău.
- În `body`, creează un formular de contact cu următoarele câmpuri:
    - Nume
    - Adresă de e-mail
    - Mesaj (câmp de tip `textarea`)
    - Buton de trimitere date

<mark>
    <b>Atenție!</b> Toate cele 3 câmpuri + butonul de trimitere trebuie cuprinse înăuntrul tag-ului <code>form</code>. Browser-ul va trimite către server doar datele cuprinse între tag-ul <code>form</code> de început și cel de sfârșit.
</mark>


2) **Atributul `name`**

Pentru fiecare dintre cele 3 câmpuri create anterior, adaugă atributul `name` și setează câte un nume unic fiecărui câmp. De exemplu, câmpul ce va conține e-mail-ul ar putea să aibă valoarea "email" pentru atributul `name`.

<mark>
    <b>Atenție!</b> Browser-ul va trimite dintr-un formular doar acele câmpuri care au atributul <code>name</code> setat. Explicația constă în faptul că se va trimite o asociere de tip pereche <i>cheie-valoare</i>, unde cheile vor fi extrase din atributul <code>name</code>, iar valorile sunt ceea ce scrie efectiv utilizatorul. 
</mark>


3) **Obținere URL Webhook**

Veți obține un URL unic, pe care îl veți folosi pentru testarea trimiterii datelor către un server web "fake".

- În orice browser web, accesați link-ul <a href="https://webhook.site/" target="_blank">https://webhook.site/</a>
- Verificați acum adresa URL din browser. Aceasta este modificată și conține un URL mai lung, unic fiecărui utilizator. Acesta reprezintă URL-ul pe care îl veți folosi pentru formularul vostru.


4) **Configurare atribut `action`**

Veți configura acel URL ca fiind URL-ul destinație al formularului vostru.

- Copiați URL-ul unic obținut anterior.
- Adăugați tag-ului `form` atributul `action` și atributul `method="post"`.
- Lipiți URL-ul unic ca valoare a atributului `action`.

Codul va arăta de forma:
```
<form action="URL_UNIC_AICI" method="post">
```
Unde în loc de `URL_UNIC_AICI` veți avea URL-ul unic copiat din browser-ul vostru.


5) **Testare formular**

Dacă ați făcut configurarea corectă, trimiterea unor date din formular va declanșa pe URL-ul unic (în browser) interpretarea răspunsului.

- După ce ați integrat URL-ul unic ca destinație a formularului, completați date și apăsați butonul de trimitere.
- În browser, la URL-ul unic obținut dați *Refresh* și verificați dacă apar cererile (*request*) cu datele trimise.
- După selectarea unei cereri din listă, în partea de subsol a paginii veți vedea datele trimise din formularul vostru.
- Repetați ciclul de trimitere date și verificare în browser de câteva ori - fiecare apăsare pe butonul de trimitere va declanșa o nouă cerere.
