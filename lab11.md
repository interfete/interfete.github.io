# CIW Științele Comunicării

## Laborator 11: Formulare în Bootstrap. Spațiere.

### Introducere

Formularele sunt principalul mod prin care utilizatorii interacționează cu un site web: trimit mesaje, se autentifică în contul personal, oferă feedback sau se înscriu la un serviciu. Bootstrap oferă clase CSS predefinite care permit crearea rapidă a unor formulare clare, consistente și responsive, fără a scrie mult CSS personalizat.

Spațierea controlează distanța dintre elementele din pagină și spațiul din interiorul lor, astfel încât conținutul să fie ușor de citit, aerisit și bine organizat.

În acest laborator vom învăța:
- cum să structurăm un formular folosind Bootstrap;
- care sunt cele mai folosite câmpuri de formular;
- cum arată un formular bine organizat;
- cum să aplicăm spațiere (*margin* și *padding*) elementelor din pagină.

### Structura de bază a unui formular de Bootstrap

Un formular Bootstrap pornește de la elementul de formular HTML `<form>`, iar fiecare câmp este grupat într-un container logic (de exemplu, un `<div>`).

```
<form>
    <div>
        <label class="form-label">Email</label>
        <input type="email" class="form-control">
    </div>

    <button type="submit" class="btn btn-primary">Trimite</button>
</form>
```

Clase importante:
- `form-control` – stilizează câmpurile text
- `form-label` – stilizează etichetele

### Tipuri de câmpuri uzuale

#### Câmp de text scurt (de ex. pentru nume sau username)

```
<input type="text" class="form-control" placeholder="Numele dvs.">
```

#### Câmp de e-mail

```
<input type="email" class="form-control" placeholder="email@exemplu.ro">
```

#### Câmp de parolă

```
<input type="password" class="form-control">
```

#### Câmp pentru text lung

```
<textarea class="form-control" rows="4"></textarea>
```

#### Checkbox-uri

```
<div class="form-check">
    <input class="form-check-input" type="checkbox">
    <label class="form-check-label">Sunt de acord cu termenii și condițiile site-ului</label>
</div>
```

#### Butoane radio

```
<div>
    <p>Gen:</p>
    <div class="form-check">
        <input class="form-check-input" type="radio" name="gen" value="masculin">
        <label class="form-check-label">Masculin</label>
    </div>
    <div class="form-check">
        <input class="form-check-input" type="radio" name="gen" value="feminin">
        <label class="form-check-label">Feminin</label>
    </div>
    <div class="form-check">
        <input class="form-check-input" type="radio" name="gen" value="altul">
        <label class="form-check-label">Altul</label>
    </div>
</div>
```

#### Meniu de selecție de tip dropdown

```
<select class="form-select" name="tara">
    <option selected>Alege țara</option>
    <option value="ro">România</option>
    <option value="ua">Ucraina</option>
    <option value="bg">Bulgaria</option>
</select>
```

### Spațiere în Bootstrap

Bootstrap oferă un set de clase utilitare pentru controlul rapid al spațiilor dintre elemente (**margin**) și al spațiului din interiorul elementelor (**padding**), fără a scrie CSS personalizat.

#### Diferența dintre **margin** și **padding**
- **margin** - spațiul din exteriorul unui element
- **padding** - spațiul din interiorul elementului, între conținut și margine

#### Structura claselor de spacing

Clasele Bootstrap pentru spacing au forma generală:

```
{property}{side}-{size}
```

{property} poate lua valorile:
- `m` - margin
- `p` - padding

{side} poate lua valorile:
- `t` - top
- `b` - bottom
- `s` - start (început/stânga)
- `e` - end (sfârșit/dreapta)
- `x` - orizontal (stânga și dreapta)
- `y` - vertical (sus și jos)
- (fără) - toate laturile

{size} poate lua valorile:
- `0` - fără spațiu
- `1` - foarte mic
- `2` - mic
- `3` - mediu
- `4` - mare
- `5` - foarte mare

**Exemplu de margini aplicate:**
```
<div class="mb-3">Margin mediu dedesubt</div>
<div class="mt-5">Margin mare sus</div>
<div class="mx-2">Margin mic pe orizontală (stânga și dreapta)</div>
```

**Exemplu de padding-uri aplicate:**
```
<div class="p-3">Padding mediu pe toate laturile (sus, dreapta, jos, stânga)</div>
<div class="pt-4">Padding mare sus</div>
<div class="px-5">Padding foarte mare pe orizontală (stânga și dreapta)</div>
```

### Exerciții

#### 1. Formular de contact

Creează un formular de înregistrare ce folosește clase de Bootstrap. Acesta trebuie să conțină:
- Nume
- Email
- Parolă
- Buton de trimitere a datelor

#### 2. Câmp de selecție

Adaugă formularului anterior o secțiune de selecție a genului cu butoane de tip radio. Include minim 3 genuri (de ex. *Masculin*, *Feminin*, *Altul*). Secțiunea va fi inclusă înaintea butonului de trimitere a datelor. Adaugă și o opțiune goală astfel încât genul să NU vină preselectat pe o anumită opțiune.

#### 3. Stilizare formular

Stilizează formularul în așa fel încât:
- butonul de folosească clase din Bootstrap pentru a fi de culoare portocalie (Hint: *btn-warn*)
- fiecare câmp din formular să fie distanțat față de celelalte (Hint: aplică o margine deasupra sau dedesubt)

#### 4. Formular responsive

Aplică clase de responsivitate pe formular (folosind sistemul de tip Grid din Bootstrap) astfel încât:
- Pe mobil fiecare câmp (nume, email, parolă) va sta pe câte un rând separat;
- Pe tabletă câmpurile nume și email vor sta pe un rând, iar parolă pe al doilea rând (Hint: folosește breakpoint-ul *md*);
- Pe desktop toate cele 3 câmpuri (nume, email, parolă) vor sta pe același rând (Hint: folosește breakpoint-ul *lg*);
- Câmpurile de tip nume, email și parolă să stea pe același rând pe Desktop 

- Secțiunea de selecție a genului va fi afișată mereu pe un rând separat, indiferent de dispozitiv
- Butonul de trimitere a datelor va fi afișat mereu pe un rând separat, indiferent de dispozitiv
