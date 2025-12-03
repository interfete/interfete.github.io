# CIW Științele Comunicării

## Laborator 09: Recapitulare

### Introducere

În acest laborator veți lucra la aplicațiile practice de la parțial, menite să furnizeze exerciții recapitulative din cursurile și laboratoarele anterioare.

### Exerciții

#### 1. Care element va avea textul aliniat la dreapta?

**html**
```
<div class="container">
    <div class="item">A</div>
    <div class="item special">B</div>
    <div class="item">C</div>
</div>
```

**css**
```
.container {
    display: flex;
    justify-content: space-between;
}
.item.special {
    text-align: right;
}
```

#### 2. Ce elemente vor fi colorate în roșu? 

**html**
```
<div class="container">
    <p>Paragraf 1</p>
    <span>
        <p>Paragraf 2</p>
    </span>
    <p class="highlight">Paragraf 3</p>
</div>
<p>Paragraf 4</p>
```

**css**
```
.container > p {
    color: red;
}
```

#### 3. Ce elemente vor primi border verde?

**html**
```
<form>
    <input type="text" name="nume">
    <input type="password" name="pass">
    <input type="email" name="email">
    <input type="text" name="altceva">
</form>
```

**css**
```
input[type="text"] {
    border: 2px solid green;
}
```

#### 4. Ce culoare va avea textul butonului "Trimite"?

**html**
```
<form>
    <button type="submit" class="btn send">Trimite</button>
    <button type="button" class="btn cancel">Anulează</button>
</form>
```

**css**
```
button.btn {
    color: blue;
}

button[type="button"].send {
    color: orange;
}
```

#### 5. Formular înscriere eveniment

Creează un formular HTML pentru înscriere la un eveniment. Formularul trebuie să conțină:
- un câmp de tip text pentru nume;
- un câmp email;
- un câmp select cu 3 opțiuni (ex: "Student", "Cadru Didactic", "Vizitator");
- un buton de trimitere.

Aplică prin CSS următoarea cerință: toate elementele `<input>` să aibă font-size de `8px` și o bordură gri.

#### 6. Formular de autentificare

Scrie codul HTML pentru un formular de autentificare care include câmpurile *username* și *password*. Adaugă un checkbox *Remember me*. Folosește CSS astfel încât checkbox-ul și label-ul aferent să fie afișate pe același rând, iar butonul de *Login* să fie centrat în pagină.

#### 7. Tabel cu angajați

Creează un tabel HTML cu 3 coloane: *Nume*, *Rol*, *E-mail* și cu minim 3 rânduri de date. Aplică CSS astfel încât primul rând (header-ul) să aibă fundal închis la culoare și textul alb. În plus, alternează culoarea de fundal a rândurilor (striped table) folosind pseudo-clasa `:nth-child()`.

#### 8. Tabel cu programul zilei

Realizează un tabel cu programul pe o zi (ex: orele 8–16). Tabelul trebuie să includă orele pe rânduri și activitățile corespunzătoare. Aplică CSS pentru a alinia textul din coloana de ore la dreapta și textul din coloana de activități la stânga (proprietatea `text-align`). În plus, aplică o bordură subțire fiecărei celule.
