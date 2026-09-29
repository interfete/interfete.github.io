# CIW Științele Comunicării

## Laborator 01

### Introducere în programarea web și structura Internetului:

### Adrese URL

O **adresă URL** (**U**niform **R**esource **L**ocator) indică adresa exactă a unei **resurse** pe internet. O resursă poate fi o pagină web, o imagine, un fișier PDF, un videoclip, etc.

Structura unei adrese URL este următoarea:
```
protocol://nume_domeniu/cale_catre_resursa
```

Unde:
- `protocol` – stabilește protocolul (modul) de acces al resursei (exemple de protocoale web: `https`, `http`, `ftp`)
- `nume_domeniu` – identifică serverul unde se află resursa (e.g.: `google.ro`)
- `cale_catre_resursa` – arată locația exactă a fișierului pe acel server

Un exemplu de adresă URL validă este chiar adresa web a paginii curente (vizibilă și în bara de adresă):
```
https://interfete.github.io/lab01
```

O adresă URL poate fi văzută ca „adresa poștală” a unei resurse de pe internet, care permite browser-ului web (clientului) să o găsească, să o acceseze și să o afișeze.

Exemple de browser-e web populare sunt: Google Chrome, Apple Safari, Mozilla Firefox, Microsoft Edge.

### Adrese IP

O **adresă IP** (**I**nternet **P**rotocol) este un număr unic atribuit fiecărui dispozitiv conectat la o rețea care folosește protocolul Internet.

Adresa IP funcționează ca un identificator digital, similar cu o adresă poștală, permițând dispozitivelor să se recunoască și să comunice între ele în rețea.

#### Tipuri de adrese IP
- *IPv4* – format din 4 numere între 0 și 255, separate prin puncte; ex.: `142.250.109.94`
- *IPv6* – format din 8 grupuri de numere hexazecimale, separate prin „:”; au fost create pentru a acoperi nevoia de mai multe adrese IP; ex.: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

O adresă IP este „numărul de identificare” al unui dispozitiv în rețea, esențial pentru trimiterea și primirea datelor între calculatoare.

### Translatarea unui nume de domeniu

Translatarea dintre un nume de domeniu (ex: `google.ro`) și o adresă IP (ex: `142.250.109.94`) se face printr-un sistem numit **DNS** (**D**omain **N**ame **S**ystem).

DNS funcționează ca o „agendă telefonică” a Internetului: el convertește numele ușor de reținut de către oameni în adrese IP folosite de calculatoare pentru comunicare.

#### Pașii procesului DNS
1.	Utilizatorul introduce un nume de domeniu în browser-ul web.
Ex.: scrii în bara de adrese a browser-ului web `google.ro`
2.	Browser-ul verifică memoria cache locală.
– Dacă a mai accesat recent acel site, adresa IP poate fi deja salvată și folosită imediat;
– Dacă nu, trece la pasul următor.
3.	Solicitarea este trimisă către un server DNS.
– Acest server poate fi furnizat de rețeaua locală (ex: router-ul din apartament) sau de un serviciu public (ex: Google DNS – 8.8.8.8).
4.	Serverul DNS caută adresa IP corespunzătoare domeniului.
– Dacă nu o are în cache, interoghează alte servere DNS mai mari, începând cu serverele rădăcină (*root*), apoi serverele de domeniu de nivel superior (.com, .ro, etc.), până la serverul autoritativ pentru acel domeniu.
5.	Răspunsul este trimis browserului.
– Browserul primește adresa IP și o folosește pentru a se conecta la serverul web corespunzător.

<mark>În concluzie, DNS traduce automat numele de domeniu în adresa IP a serverului pe care se află site-ul, permițând accesul la pagini web fără ca utilizatorul să fie nevoit să rețină numere IP!</mark>

#### Aflarea adresei IP dintr-un nume de domeniu

Există mai multe modalități prin care poți afla adresa IP asociată unui nume de domeniu — de la comenzi simple în consolă, până la instrumente online.

##### Utilitarul `ping` (disponibil în `Command Prompt` / `Terminal`)

Pe un sistem de operare *Windows*, deschideți o fereastră de `Command Prompt`.

Pe un sistem de operare *Linux* sau *Mac OS*, deschideți o fereastră de `Terminal`.

În `Command Prompt` sau `Terminal`, scrieți comanda:
```
ping google.ro
```

Rezultatul va arăta asemănător următorului output:
```
PING google.ro (172.217.18.3): 56 data bytes
64 bytes from 172.217.18.3: icmp_seq=0 ttl=116 time=30.065 ms
64 bytes from 172.217.18.3: icmp_seq=1 ttl=116 time=30.808 ms
64 bytes from 172.217.18.3: icmp_seq=2 ttl=116 time=30.524 ms
...
```

Se observă adresa IP a website-ului `google.ro` ca fiind `172.217.18.3`.

##### Website-ul NsLookup.io

Pe website-ul [http://nslookup.io](http://nslookup.io), introduceți numele de domeniul `google.ro`. Verificați ce adresă IP primiți.

##### Observație

Un nume de domeniu poate fi asociat cu mai multe adrese IP în același timp.

Acest lucru se întâmplă din mai multe motive, printre care:
- Echilibrarea traficului (**Load Balancing**) – un site foarte vizitat (ex: google.com, facebook.com) este găzduit pe mai multe servere;
- Disponibilitate ridicată (**High Availability**) - dacă un server cade, cererile pot fi direcționate automat către alt IP;
- Servere **localizate geografic** diferit (GeoDNS / CDN) - Serviciile moderne (ex: YouTube, Netflix) trimit utilizatorii către cel mai apropiat server geografic.

### Comunicarea client-server

Comunicarea client–server este un model fundamental al funcționării rețelelor și a internetului.

În acest model:
- Clientul este dispozitivul sau aplicația care face o cerere (ex.: browser-ul web);
- Serverul este calculatorul sau aplicația care primește cererea, o procesează și trimite un răspuns.

Exemplu:
Când scrii **emag.ro** în browser:
1.	Browser-ul (clientul) trimite o cerere **HTTP** (**H**yper**t**ext **T**ransfer **P**srotocol) către serverul site-ului.
2.	Serverul primește cererea, găsește fișierul cerut (ex: `index.html`) și îl trimite înapoi.
3.	Browser-ul afișează resurse (pagina web, imaginea, etc.) pentru utilizator.

Astfel, comunicarea client–server este un schimb de mesaje în care clientul solicită servicii sau date, iar serverul răspunde cu informațiile cerute.

#### Descoperirea resurselor cerute de o pagină web

Resursele cerute de un site web (fișiere HTML, CSS, imagini, script-uri etc.) pot fi vizualizate foarte ușor folosind consola de dezvoltare (*Developer Tools*) disponibilă în majoritatea browser-elor web.

Pașii principali pentru accesarea consolei:
1.	Accesați site-ul în browser-ul web (ex: Google Chrome, Edge, Firefox).
2.	Apăsați tasta `F12` sau combinația `Ctrl + Shift + I` (*Windows*) / `Cmd + Option + I` (*macOS*) pentru a deschide `DevTools`. Sau dați click-dreapta oriunde în pagină și alegeți ceva similar *Inspect* sau *Inspect Element*.
3.	Selectați tab-ul *Network*.
4.	Reîncărcați pagina (`F5` sau `Ctrl + R`).

Puteți observa în tab-ul *Network*:
- Lista completă a resurselor cerute de browser (HTML, CSS, JS, imagini, fonturi etc.).
- Tipul fiecărei resurse (document, script, stylesheet, image, xhr etc.).
- Statusul HTTP (ex: 200 OK, 404 Not Found).
- Dimensiunea fișierelor și timpul de încărcare.
- URL-ul complet al fiecărei resurse.

### Codul HTML

O pagină web este construită din **HTML** (*H*yper*T*ext *M*arkup *L*anguage), care reprezintă scheletul sau structura de bază a paginii.

HTML folosește etichete (tags) pentru a descrie elementele dintr-o pagină, cum ar fi titluri, paragrafe, imagini, linkuri sau liste.

HTML definește structura și conținutul unei pagini web, iar alte tehnologii, precum CSS și JavaScript, se ocupă de aspectul vizual și de comportamentul acesteia.

Exemplu de cod HTML:
```
<!DOCTYPE html>
<html>
    <head>
        <title>Exemplu</title>
    </head>
    <body>
        <h1>Bun venit!</h1>
        <p>Aceasta este o pagină web construită în HTML.</p>
    </body>
</html>
```

În browser, metoda rapidă de a obține codul HTML original:
- Taste: `Ctrl+U` (*Windows*/*Linux*) sau `Cmd+U` (*macOS*).
- Sau: bara de adresă → view-source:https://exemplu.com.
- Afișează HTML-ul așa cum l-a trimis serverul înainte ca JavaScript-ul să-l modifice.
- Acum puteți copia codul HTML și îl puteți salva într-un fișier cu extensia `.html`.

### Exerciții

1. Folosind utilitarul `ping`, descoperiți adresa IP a site-ului **emag.ro**.
2. Folosind website-ul [http://nslookup.io](http://nslookup.io), decscperiți adresa IP a site-ului **emag.ro**.
3. Comparați cele două adrese IP. Sunt identice sau diferite? De ce?
4. Folosind browser-ul *Google Chrome*, accesați website-ul [https://www.w3.org/](https://www.w3.org/)
Din consola browser-ului (Inspect), găsiți în lista de resurse (*Network*):
- minim un fișier *CSS*
- minim un fișier *JavaScript*
- minim două imagini
5. Folosind browser-ul *Google Chrome*, accesați website-ul [https://example.com/](https://example.com/)
Copiați sursa paginii web (*View Page Source*) într-un fișier cu extensia `.html`. Modificați conținutul astfel încât:
- în loc de `Example Domain` să scrie numele dvs.;
- în loc de textul de dedesubt să scrieți două propoziții despre hobby-urile proprii;
- link-ul `More information...` să trimită la profilul dvs. personal (Facebook, Instagram, etc.)
