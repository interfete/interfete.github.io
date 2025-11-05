# CIW Științele Comunicării

## Laborator 05: Tabele în HTML

### Tabele

Tabelele în HTML sunt folosite pentru a organiza informațiile în rânduri și coloane, similar cu un tabel dintr-un fișier Excel. Ele sunt utile pentru afișarea datelor structurate — cum ar fi orare, liste de prețuri sau rezultate de sondaje.

### Tag-uri folosite

Un tabel este definit cu tag-ul `<table>`, iar structura sa de bază include:
- `<tr>` – definește un rând (table row),
- `<th>` – definește o celulă de antet (table header),
- `<td>` – definește o celulă de date (table data).

#### Exemplul 1 - Tabel simplu
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

Aceste trei elemente ajută la organizarea logică a conținutului unui tabel HTML, separând clar părțile componente:
- `<thead>` – conține rândurile de antet ale tabelului (de obicei cu tag-uri `<th>`).
Este util pentru a specifica titlurile coloanelor și pentru ca browserele sau cititoarele de ecran să le recunoască drept capete de tabel.
- `<tbody>` – include conținutul principal al tabelului, adică toate rândurile de date efective (`<tr>` cu `<td>`).
Poți avea un singur `<tbody>` într-un tabel, dar unele browsere permit mai multe pentru tabele complexe.
- `<tfoot>` – conține rândul de subsol, folosit adesea pentru totaluri, note sau concluzii ale datelor.
Interesant este că, deși apare vizual la final, poate fi plasat în cod înainte de `<tbody>`, pentru ca browserul să poată procesa mai eficient tabelele mari.

#### Exemplul 2 - Tabel cu structură semantică
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

Celula "Note" se întinde pe două coloane în exemplul de mai sus.

#### `rowspan` – unirea rândurilor

Atributul `rowspan` specifică numărul de rânduri pe care o celulă trebuie să le acopere.

##### Exemplul 4 - Tabel cu `rowspan`
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

Celula "Categorie" se întinde pe două rânduri în exemplul de mai sus.

#### Observații

Folosirea acestor atribute ajută la crearea unor tabele mai complexe și mai clare vizual.

Totuși, trebuie folosite cu grijă, pentru ca structura tabelului să rămână logică și ușor de citit (atât pentru oameni, cât și pentru tehnologii asistive).

### Exerciții

1) Salvați într-un fișier HTML codul din *Exemplu 1 - Tabel simplu*, de mai sus. Nu uitați de structura de bază HTML! Adăugați acestui tabel o nouă coloană *Notă* și completați date pentru ea.

2) Salvați într-un fișier HTML codul din *Exemplul 3 - Tabel cu `colspan`*, de mai sus. Adăugați încă o notă, astfel încât Maria să aibă 3 note. Ce atribut trebuie să mai modificați?

3) Fișierul PDF <a href="lab05/intretinere.pdf" target="_blank">intretinere.pdf</a> conține o listă simplificată de întreținere. Realizați un document HTML care să creeze un tabel cât mai asemănător cu acesta. Valorile numerice nu sunt relevante (le puteți completa aleator).
Condiții minime:
- minim 4 coloane
- minim 2 secțiuni (ex.: SCARA A, SCARA B)
- folosiți tag-uri semantice pentru structurare antet, corp și subsol tabel
