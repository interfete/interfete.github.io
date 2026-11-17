---
layout: default
title: Recap parțial
nav_order: 8
nav_exclude: false
search_exclude: false
---

# CIW Științele Comunicării

## Recapitulare parțial

### Concepte cheie

- Taguri semantice vs. generice: când folosim `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>` vs. clasicul `<div>`
- Ierarhia heading-urilor: Un singur `<h1>` pe pagină, urmat corect de `<h2>`, `<h3>` fără să sară trepte (ex: `<h1>` sare direct la `<h4>`)
- Liste în HTML
- Link-uri și imagini
- Atribute globale
- Formulare
- Tabele

### Structura și semantica paginii (*Document Outline*)

Fără CSS, aspectul vizual dispare, așa că browser-ul și cititoarele de ecran se bazează exclusiv pe tag-urile semantice pentru a înțelege structura.

Scheletul de bază: `<!DOCTYPE html>`, `<html>`, `<head>`, `<title>`, `<body>`.

Tag-uri de structură:
- `<header>` – antetul paginii sau al unei secțiuni;
- `<nav>` – meniul de navigare;
- `<main>` – conținutul principal (unul singur pe pagină);
- `<section>` – o secțiune tematică a conținutului;
- `<article>` – un articol sau o știre de sine stătătoare;
- `<aside>` – conținut lateral (sidebar, reclame, link-uri conexe);
- `<footer>` – subsolul paginii.

### Liste

Principalele tipuri de liste în HTML:
- Listă ordonată: `<ol>` cu elemente `<li>`;
- Listă neordonată: `<ul>` cu elemente `<li>`.

### Legături (link-uri) și imagini

Linkuri (`<a>`) - atributul `href="..."` stabilește destinația.

Imagini (`<img>`) - atributul `src="..."` stabilește adresa (sursa) imaginii, iar `alt="..."` cuprinde un text alternativ, folosit în cazul în care imaginea nu este disponibilă.

### Atribute globale

Atribute care pot fi puse pe majoritatea tag-urilor/elementelor HTML:
- `id` – identificator unic în toată pagina HTML;
- `class` – gruparea elementelor după un nume comun.

### Formulare

Tag-ul principal: `<form action="..." method="POST">`.

Asocierea etichetelor: tag-ul `<label for="nume_id">` trebuie să aibă atributul `for` egal cu `id`-ul input-ului corespunzător (esențial pentru accesibilitate).

<mark>Este foarte importantă corectitudinea legăturilor dintre etichete și câmpuri!</mark>

Tipuri de inputuri (`<input type="...">`): text, password, email, number, checkbox, radio (opțiuni grupate prin același name), buton de tip *submit*.

Alte elemente: `<select>` împreună cu `<option>`, `<textarea>`

### Tabele 

Tag-ul principal: `<table>`.

Tag-uri de structă: `<tr>` (rând), `<th>` (celulă antet) și `<td>` (celulă de date).

Tag-uri semantice: `<thead>`, `<tbody>`, `<tfoot>`.

Atribute de *merge*:
- `colspan="n"` – unește `n` coloane pe orizontală;
- `rowspan="n"` – unește `n` rânduri pe verticală.

### Greșeli frecvente

Mai jos aveți o listă de greșeli frecvente când vine vorba de structura de bază HTML, tag-uri semantice, formulare și tabele:
- taguri/elemente neînchise - majoritatea tag-urilor au nevoie de un tag de închidre (exemplu: tag-ul `<p>` are nevoie de `</p>`);
- nediferențierea elementelor *self-closing* (precum `<img>`, `<br>`, `<input>`) - acestea nu au nevoie de tag de închidere deoarece ele nu mai conțin altceva "înăuntrul" lor;
- imagini fără atributul `alt` setat - atributul este obligatoriu, dar omis des;
- alegerea unei liste - folosirea greșită a listelor ordonate (`<ol>`) în loc de cele neordonate (`<ul>`) și invers;
- ierarhia unei liste - includerea elementelor de tip *list item* (`<li>`) în mod corect înăuntrul unei liste;
- lipsa asocierii unui label cu for pentru inputuri (foarte important pentru accesibilitate).

### Quiz demo

La adresa următoare găsiți un quiz demo care prezintă exemple de întrebări ce pot apărea în partea de grilă a examenului parțial: <a href="https://curs.upb.ro/2026/mod/quiz/view.php?id=74394" target="_blank">Quiz demo</a>.

<mark>Quiz-ul acesta este opțional, dar vă ajută să vă familiarizați cu modelele de întrebări ce pot apărea la parțial!</mark>

### Exerciții

1) Structura unei pagini semantice de știri

Dezvoltați o pagină HTML cu știri, care să conțină:
- O zonă de antet (`<header>`) care să conțină titlul site-ului (`<h1>`) și un meniu de navigare (`<nav>`).
- Un articol principal (`<article>`) care conține un titlu, un paragraf introductiv și o imagine cu text alternativ.
- Un subsol (`<footer>`) cu un text de copyright. Includeți simbolul de copyright (`&copy;`).

2) Formular de înregistrare

Dezvoltați o pagină HTML care să cuprindă un formular de înregistrare. Acesta trebuie să conțină:
- un câmp (`<input>`) pentru Nume (input de tip `text`, obligatoriu - `required`);
- un câmp (`<input>`) pentru E-mail (input de tip `email`);
- o listă derulantă (`<select>`) pentru alegerea orașului;
- un grup de butoane radio (`type="radio"`) pentru alegerea genului (*masculin* / *feminin*).
- un buton (`<button>`) de submit.

<mark>Atenție! Toate câmpurile trebuie să aibă un  `<label>` și legătura corectă între label și id-ul inputului!)</mark>

3) Orarul facultății

Fișierul <a href="recap/orar.pdf" target="_blank">orar.pdf</a> conține orarul vostru.

Creeați un tabel care să afișeze orarul pentru două zile, folosind tag-uri: `<thead>`, `<tbody>`, `<tr>`, `<th>` și `<td>`.

Folosiți atributele `rowspan` sau `colspan` acolo unde este nevoie (de exemplu pentru un seminar care este ținut atât pe impar, cât și pe par).
