---
layout: default
title: Laborator 05
nav_order: 6
nav_exclude: false
search_exclude: false
---

# CIW Științele Comunicării

## Laborator 05: Tabele în HTML

### Tabele

Tabelele în HTML sunt folosite pentru a organiza informațiile în rânduri și coloane, similar cu un tabel dintr-un fișier *Microsoft Excel*. Tabelele sunt utile pentru afișarea datelor structurate — cum ar fi orare, liste de prețuri, meniuri, rezultate de chestionare, etc.

### Tag-uri folosite

Un tabel este definit cu ajutorul tag-ului `<table>`, iar structura sa de bază include:
- `<tr>` – definește un rând întreg (**table row**);
- `<th>` – definește o celulă de antet/cap de tabel (**table header**);
- `<td>` – definește o celulă de date (**table data**).

#### Exemplul 1 - Tabel simplu

Exemplul următor definește un tabel cu două coloane (*Nume* și *Vârstă*), un rând ce conține capul de tabel și două rânduri de conținut:
```
<table border="1">
  <tr>
    <th>Nume</th>
    <th>Vârstă</th>
  </tr>
  <tr>
    <td>Maria</td>
    <td>22</td>
  </tr>
  <tr>
    <td>Andrei</td>
    <td>24</td>
  </tr>
</table>
```

### Tag-urile `<thead>`, `<tbody>` și `<tfoot>`

Tag-urile `<thead>`, `<tbody>` și `<tfoot>` sunt tag-uri semantice care ajută motorul de căutare să înțeleagă cum este structurat conținutul. De asemenea, aceste trei elemente ajută la organizarea logică a conținutului unui tabel HTML, separând clar părțile componente:
- **`<thead>`** – cuprinde rândurile de antet ale tabelului (ale căror celule sunt de obicei definite cu tag-uri `<th>`).
Este util pentru a specifica numele coloanelor și pentru ca browserele sau cititoarele de ecran să le recunoască drept capete de tabel. Atenție! Tabelele pot avea mai multe rânduri de antet, dar toate vor fi cuprinse într-un singur tag `<thead>`!
- **`<tbody>`** – include conținutul principal al tabelului, adică toate rândurile de date efective (de obicei rânduri de tip `<tr>` ce cuprind date definite cu tag-uri de tip `<td>`).
Poți avea un singur `<tbody>` într-un tabel!.
- **`<tfoot>`** – conține rândul de subsol, folosit adesea pentru totaluri, subtotaluri, note de subsol ale tabelului sau concluzii ale datelor.

#### Exemplul 2 - Tabel cu structură semantică
Exemplul următor definește un tabel cu două coloane (*Produs* și *Preț*), un rând de cap de tabel și trei rânduri de celule cu conținut. Capul de tabel este cuprins in tag-ul `<thead>`, iar rândurile de conținut în tag-ul `<tbody>`:
```
<table border="1">
  <thead>
    <tr>
      <th>Produs</th>
      <th>Preț</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Mere</td>
      <td>5 lei</td>
    </tr>
    <tr>
      <td>Pere</td>
      <td>6 lei</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>11 lei</td>
    </tr>
  </tfoot>
</table>
```

Astfel, aceste elemente nu schimbă aspectul vizual al tabelului în mod direct, dar adaugă claritate semantică și structură logică, lucru important pentru accesibilitate și validarea HTML.

### Atributele `colspan` și `rowspan`

Într-un tabel HTML, uneori este nevoie ca o celulă să ocupe mai multe coloane sau mai multe rânduri.

Pentru aceste situații se folosesc atributele `colspan` și `rowspan`, aplicate pe elementele `<th>` sau `<td>`.

#### `colspan` – unirea coloanelor

Atributul `colspan` specifică numărul de coloane pe care o celulă trebuie să le ocupe.

##### Exemplul 3 - Tabel cu `colspan`
Tabelul următor definește două coloane: *Nume* și *Note*, dar coloana *Note* se întinde pe două coloane. Din această cauză, rândul de conținut are, de fapt, 3 celule:
```
<table border="1">
  <tr>
    <th>Nume</th>
    <th colspan="2">Note</th>
  </tr>
  <tr>
    <td>Maria</td>
    <td>9</td>
    <td>10</td>
  </tr>
</table>
```

#### `rowspan` – unirea rândurilor

Atributul `rowspan` specifică numărul de rânduri pe care o celulă trebuie să le acopere.

##### Exemplul 4 - Tabel cu `rowspan`
Tabelul următor definește un tabel cu două coloane, *Categorie* și *Produs*, iar coloana *Categorie* se întinde pe două rânduri:
```
<table border="1">
  <tr>
    <th rowspan="2">Categorie</th>
    <th>Produs</th>
  </tr>
  <tr>
    <td>Mere</td>
  </tr>
</table>
```

#### Observații

Folosirea acestor atribute ajută la crearea unor tabele mai complexe și mai clare vizual.

Totuși, trebuie folosite cu grijă, pentru ca structura tabelului să rămână logică și ușor de citit (atât pentru oameni, cât și pentru programele care suportă tehnologii asistive).

### Exerciții

1) Salvați într-un fișier HTML codul din *Exemplu 1 - Tabel simplu*, de mai sus. Nu uitați de structura de bază HTML! Adăugați acestui tabel o nouă coloană *Notă* și completați date pentru ea.

2) Salvați într-un fișier HTML codul din *Exemplul 3 - Tabel cu `colspan`*, de mai sus. Adăugați încă o notă, astfel încât Maria să aibă 3 note. Ce atribut trebuie să mai modificați?

3) Fișierul PDF <a href="intretinere.pdf" target="_blank">intretinere.pdf</a> conține o listă simplificată de întreținere. Realizați un document HTML care să creeze un tabel cât mai asemănător cu acesta. Valorile numerice nu sunt relevante (le puteți completa aleator).
Condiții minime:
- minim 4 coloane
- minim 2 secțiuni (ex.: SCARA A, SCARA B) - folosiți atributul `colspan`
- folosiți tag-uri semantice pentru structurarea antetului, corpului și subsolului tabelului
