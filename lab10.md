# CIW Științele Comunicării

## Laborator 10: Introducere în Bootstrap

### Introducere

Bootstrap este un framework CSS popular folosit pentru a construi site-uri moderne, responsive și consistente, fără a scrie tot stilul de la zero. Oferă un set de componente predefinite (grid, butoane, carduri, formulare, navigație) care pot fi folosite rapid doar prin aplicarea unor clase de CSS.

Beneficii:
- ajută dezvoltatorii software să lucreze cu un design modern fără efort;
- reduce timpul de dezvoltare;
- asigură compatibilitate între dispozitive (*responsiveness*);
- este foarte folosit în industrie.

### Cum integrăm Bootstrap?

Pentru a integra Bootstrap într-un site web există mai multe variante:
- integrare direct din link-ul extern (de obicei găzduit pe un CDN - *Content Delivery Network*) - link-ul e furnizat pe site-ul oficial sau este căutat manual pe site-uri CDN dedicate;
- descărcare locală a bibliotecii, integrare fișier CSS în proiect și "legare" a fișierului local în site;
- instalare bibliotecă folosind un *Package Manager* - variantă folosită de dezvoltatorii software avansați.

În ambele variante, legarea fișierului CSS (extern sau local proiectului) se face în zona de `<head>` folosind tag-ul `<link>`.

#### Fișier extern (modalitatea recomandată)

Se introduce următorul cod în zona de `<head>`:

```
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
```

#### Fișier local

1. Se descarcă ultima versiune a Bibliotecii de pe site-ul oficial [https://getbootstrap.com](https://getbootstrap.com) (folosind butonul de *Download*).
2. Se copiază fișierul `bootstrap.min.css` în proiect.
3. Se introduce următorul cod în zona de `<head>`:

```
<link href=bootstrap.min.css" rel="stylesheet">
```

### Clase utile și componente


#### Alerte

Alertele în Bootstrap sunt componente *UI* folosite pentru a afișa mesaje importante către utilizator — notificări, confirmări, atenționări sau erori. Ele sunt stilizate automat și pot fi colorate în funcție de semnificație. Bootstrap oferă clase predefinite astfel încât dezvoltatorul trebuie doar să adauge textul.

Toate alertele folosesc clasa de bază `alert`. Acesteia i se adaugă una dintre următoarele clase contextuale specifice:
- `alert-primary` - mesaj informativ general (accent de marcaj);
- `alert-secondary` - mesaj auxiliar, mai puțin important;
- `alert-success` - confirmări sau mesaje pozitive (ex.: "Formular trimis cu succes");
- `alert-danger` - erori, probleme critice;
- `alert-warning` - atenționări non-critice, avertizări;
- `alert-info` - mesaje informative;
- `alert-light` / `alert-dark` - variante pentru mesaje neutre sau pentru varianta *dark*.

**Exemplu alertă de succes:**
```
<div class="alert alert-success" role="alert">
    Contul tău a fost creat cu succes!
</div>
```

**Exemplu alertă de eroare:**
```
<div class="alert alert-danger" role="alert">
    Câmpul nume de utilizator trebuie completat!
</div>
```

**Exemplu alertă de avertizare:**
```
<div class="alert alert-warning" role="alert">
    Atenție! Urmează să ștergi acest câmp!
</div>
```

#### Butoane

Butoanele în Bootstrap sunt elemente interactive predefinite, stilizate uniform, care permit utilizatorilor să declanșeze acțiuni (de ex. trimitere de formulare, navigare în pagină, deschidere de componente suplimentare). Bootstrap oferă un set larg de clase pentru butoane, astfel încât poți crea rapid elemente vizuale coerente și *responsive* fără CSS suplimentar. Folosind clasa de bază `btn` împreună cu una dintre clasele contextuale (ex.: `btn-primary`, `btn-success`, `btn-danger`), poți controla culoarea, stilul, dimensiunea și comportamentul butoanelor. Clasele pentru butoane pot fi aplicate atât pe tag-ul `<button>`, cât și pe tag-uri precum `<a>` sau `<input>`, menținând aceeași estetică indiferent de elementul HTML folosit.

**Exemplu de buton de bază:**
```
<button class="btn btn-primary">Trimite</button>
```

**Alte butoane de contextuale:**
```
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-light">Light</button>
<button class="btn btn-dark">Dark</button>
```

**Butoane de tip link:**
```
<a href="https://google.ro" class="btn btn-primary">Mergi la Google</a>
```

**Butoane cu contur:**
```
<button class="btn btn-outline-primary">Outline Primary</button>
<button class="btn btn-outline-success">Outline Success</button>
<button class="btn btn-outline-danger">Outline Danger</button>
```

**Butoane de mărimi diferite:**
```
<button class="btn btn-primary btn-lg">Large Button</button>
<button class="btn btn-primary btn-sm">Small Button</button>
```

**Buton dezactivat:**
```
<button class="btn btn-secondary" disabled>Disabled</button>
```

#### Carduri

Acestea sunt componente util pentru orice site. Pot fi folosite în diverse contexte precum prezentarea profilului unui utilizator, un produs individual de pe o pagină ce cuprindă o categorie de produse, un articol de pe o pagină de știri, o imagine dintr-o galerie de imagini, etc.

**Card cu detaliile unui curs:**
```
<div class="card">
    <img src="https://picsum.photos/200" class="card-img-top">
    <div class="card-body">
        <h5 class="card-title">Construcția Interfețelor Web</h5>
        <p class="card-text">Cursul prezintă conceptele fundamentale pentru crearea unui site web HTML de la zero.</p>
        <a href="#" class="btn btn-primary">Vezi mai mult</a>
    </div>
</div>
```


### Sistemul de tip Grid

Grid-ul din Bootstrap folosește un sistem pe 12 coloane. El permite ca elementele să se aranjeze pe rânduri (*rows*) și coloane (*cols*), adaptându-se la dimensiunea ecranului (indiferent că este un desktop, laptop sau dispozitiv mobil). Pentru ca acest lucru să se poată aplica, rândurile trebuie cuprinse într-un *container*.

În exemplul următor se definește un singur rând, care conține 3 coloane. Fiecare coloană va avea o dimensiune proporțională din spațiul disponibil în container. Fiind 3 coloane în total, fiecare coloană va ocupa 33.33%.

**Exemplu cu 3 coloane de dimensiune identică:**
```
<div class="container">
  <div class="row">
    <div class="col">Coloana 1</div>
    <div class="col">Coloana 2</div>
    <div class="col">Coloana 3</div>
  </div>
</div>
```

### Breakpoint-uri importante

Bootstrap este un framework de tipul *mobile first*. Acest lucru înseamnă că ne ajută să definim design-ul unui site web mai întâi pentru dispozitivele mobile (mai mici), apoi către dimensiuni din ce în ce mai mari. Astfel, el cuprinde 6 breakpoint-uri inspirate de dimensiunile dispozitivelor Apple:
- `col-`: Pentru dispozitive de dimensiuni foarte mici (*extra small*).
- `col-sm-`: Pentru dispozitive de dimensiuni mici (*small*).
- `col-md-`: Pentru dispozitive de dimensiuni medii (*medium*).
- `col-lg-`: Pentru dispozitive de dimensiuni mari (*large*).
- `col-xl-`: Pentru dispozitive de dimensiuni foarte mari (*extra large*).
- `col-xxl-`: Pentru dispozitive de dimensiuni extrem de mari (*extra extra large*).

Folosind aceste breakpoint-uri se poate seta ca un layout de site să apară altfel pe dispozitivele mici față de dispozitivele mari. Mai jost sunt unele exemple, în care dimensionare pornește de jos în sus (de la dimensiuni mici, la dimensiuni mari).

**Exemplu cu o singură coloană pe mobil, dar 3 coloane pe desktop:**
```
<div class="container">
  <div class="row">
    <div class="col-sm-12 col-md-4">
      <div class="p-3 bg-light border">Coloana 1</div>
    </div>
    <div class="col-sm-12 col-md-4">
      <div class="p-3 bg-light border">Coloana 2</div>
    </div>
    <div class="col-sm-12 col-md-4">
      <div class="p-3 bg-light border">Coloana 3</div>
    </div>
  </div>
</div>
```

*Explicație:*
- `col-sm-12` - pe dispozitive mici și forate mici (mobile, maxim 767px) elementul ocupă toată lățimea;
- `col-md-4` - pe dispozitive medii (tabletă, desktop, minim 768px) se împarte în 3 coloane egale.

**Exemplu cu 2 zone în pagină: sidebar + content pe desktop, însă pe mobil sidebar-ul trece dedesubt:**
```
<div class="container">
    <div class="row">
        <!-- Content (pe mobil apare primul) -->
        <div class="col-12 col-lg-8">
            <h2>Content</h2>
            <p>Aici este conținutul principal.</p>
        </div>

        <!-- Sidebar (pe mobil trece dedesubt) -->
        <div class="col-12 col-lg-4">
            <h3>Sidebar</h3>
            <p>Aici este zona de sidebar.</p>
        </div>
    </div>
</div>
```

*Explicație:*
- `col-12` - pe dispozitivele mobile și până la primul breakpoint care schimbă asta, ocupă toată lățimea (fiecare secțiune pe un rând nou);
- `col-lg-8` și `col-lg-4` - pe desktop devin două coloane.

### Exerciții

#### 1. Alerte

Creează o secțiune cu 4 alerte diferite:
1. `alert-success` – confirmare ("Formularul a fost trimis cu succes!")
2. `alert-danger` – eroare ("A apărut o problemă!")
3. `alert-warning` – avertizare ("Atenție! Câmp obligatoriu.")
4. `alert-info` – informație generală ("Creând cont la noi, acceptați termenii și condițiile site-ului.")

#### 2. Butoane

Creează o secțiune cu următoarele butoane:
1. 3 butoane de tip principal: `btn-primary`, `btn-success`, `btn-danger`.
2. 2 butoane cu contur: `btn-outline-primary`, `btn-outline-warning`.
3. 1 buton mare `btn-lg` și 1 buton mic `btn-sm`.

#### 3. Carduri

Creează un card care să conțină:
- o imagine cu o persoană de pe [Unspalsh](https://unsplash.com/) (`img`);
- un titlu cu numele vostru (folosiți clasa `card-title` înăuntrul cardului);
- un text descriptiv cu hobby-ul vostru preferat (folosiți clasa `card-text` înăuntru cardului);
- un buton de contact de tip `btn-primary`.

#### 4. Grid

Creează o secțiune cu layout responsive:
- Mobil: fiecare coloană ocupă 12 unități (`col-12`) → apare una sub alta
- Desktop (≥992px): 3 coloane egale (`col-lg-4`)

Fiecare coloană va conține cardul de la exercițiul 3 (copiați-l de 3 ori).
