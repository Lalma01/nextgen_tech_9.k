# Nagy Árpi Kft. – Weboldal dokumentáció

> IKT projektmunka – Kandó Kálmán Informatikai Technikum  
> Készítők: Lehel, Máté, András  
> URL: lalma01.github.io/nextgen_tech_9.k

---

## 1. Projekt áttekintése

A **Nagy Árpi Kft.** egy fiktív tech-vállalat weboldala, amelyet iskolai projektként készítettünk. Az oldal egy modern, sötét témájú e-kereskedelmi webshopot valósít meg Bootstrap 5 alapokon, 15 termékkel és 3 termékkategóriával.

**Főbb oldalak:**

| Fájl | Leírás |
|------|--------|
| `index.html` | Főoldal – carousel, „Miért minket?" szekció |
| `leheltermekek.html` | Személyes technológia kategória |
| `materemekek.html` | Konyhai és háztartás kategória |
| `kazaitermekek.html` | Fejlett technológia kategória |
| `mate.html` | Rólunk oldal – csapatbemutató |
| `kazai.html` | Kapcsolat oldal |
| `kosar.html` | Bevásárlókosár (JavaScript alapú) |
| `aszf.html` | Általános Szerződési Feltételek |
| `adatvedelem.html` | Adatvédelmi irányelvek |

**Termékoldal-fájlok (`products/` mappa):**

| Fájl | Termék | Kategória |
|------|--------|-----------|
| `book-pro.html` | ÁrpiBook Pro | Személyes technológia |
| `phone-pro.html` | ÁrpiPhone Pro | Személyes technológia |
| `watch-pro.html` | ÁrpiWatch Pro | Személyes technológia |
| `pad-pro.html` | ÁrpiPad Pro | Személyes technológia |
| `pod-pro.html` | ÁrpiEar Pro | Személyes technológia |
| `tv-pro.html` | ÁrpiTV Pro | Személyes technológia |
| `szivo.html` | Árpiszívó | Konyhai és háztartás |
| `moso.html` | Árpimosó | Konyhai és háztartás |
| `suto.html` | Árpisütő | Konyhai és háztartás |
| `suto-pro.html` | Árpisütő Pro | Konyhai és háztartás |
| `huto.html` | Árpihűtő | Konyhai és háztartás |
| `mikro.html` | Árpimikró | Konyhai és háztartás |
| `robot-pro.html` | ÁrpiRobot Pro | Fejlett technológia |
| `arpilab.html` | ÁrpiVac Pro | Fejlett technológia |
| `arpistream.html` | ÁrpiMiniBot | Fejlett technológia |

---

## 2. Fájlstruktúra

```
nextgen_tech_9.k/
├── index.html              ← Főoldal
├── leheltermekek.html      ← Személyes technológia kategória
├── materemekek.html        ← Konyhai és háztartás kategória
├── kazaitermekek.html      ← Fejlett technológia kategória
├── mate.html               ← Rólunk oldal
├── kazai.html              ← Kapcsolat oldal
├── kosar.html              ← Bevásárlókosár
├── aszf.html               ← ÁSZF
├── adatvedelem.html        ← Adatvédelmi irányelvek
├── style.css               ← Közös stíluslap (minden oldal használja)
├── img/                    ← Képek mappája
│   ├── LOGÓTESZT 2 good.png           ← Logó (fejléc + favicon)
│   ├── Nagy Árpi KFT. Logó 2.png      ← Alternatív logó
│   ├── Árpimosó.jpg                   ← Mosógép kép
│   ├── Árpisütő Pro.jpg               ← Sütő Pro kép
│   ├── chathuraanuradha-robot-8043126_1920.jpg  ← ÁrpiRobot Pro
│   ├── pexels-atomlaborblog-844874.jpg          ← ÁrpiVac Pro
│   ├── pexels-kindelmedia-8566424.jpg           ← ÁrpiMiniBot
│   ├── hangszóró.jpg        ← ÁrpiEar Pro
│   ├── hűtő.jpg             ← Árpihűtő
│   ├── mikró.jpg            ← Árpimikró
│   ├── porszívó.jpg         ← Árpiszívó
│   ├── sütő.jpg             ← Árpisütő
│   └── tv.jpg               ← ÁrpiTV Pro
└── products/               ← Termékoldal fájlok (15 db)
    ├── book-pro.html
    ├── phone-pro.html
    └── ...
```

> **Képhivatkozások:** A root-szintű oldalak `img/fájlnév.jpg` formátumot használnak.  
> A `products/` almappában lévő oldalak `../img/fájlnév.jpg` formátumot használnak (egy szinttel feljebb lépve).

---

## 3. Felhasznált technológiák

### Bootstrap 5.3.0
A Bootstrap egy nyílt forráskódú CSS keretrendszer, amely kész, reszponzív komponenseket biztosít: rácsrendszer, navigáció, gombok, kártyák, carousel.

```html
<!-- Bootstrap CSS – stílusok -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
<!-- Bootstrap JS – interaktív elemek (dropdown, carousel) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
```

### Google Fonts – Inter
Az egész oldalon az **Inter** betűtípust használjuk, amelyet CDN-ről töltünk be. A `wght@400;700;800` paraméter 3 betűvastagságot kér le: normál, félkövér, extra-félkövér.

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800&display=swap" rel="stylesheet">
```

### Font Awesome 6.0.0
Vektoros ikonkönyvtár. A navigációs ikonok, termékkártya-ikonok és a kosár ikon innen érkeznek.

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
```

Példa ikonhasználatra: `<i class="fas fa-robot"></i>` → robot ikon; `<i class="fas fa-shopping-cart"></i>` → kosár ikon.

### Saját CSS – `style.css`
Minden oldal betölti ezt a közös stíluslapot. A fájl tartalmazza az összes egyéni stílust, animációt és reszponzív szabályt.

---

## 4. A navigáció (style.css + minden HTML fájl)

A navigáció minden oldalon azonos Bootstrap Navbar szerkezetet követ:

```html
<header class="site-header">       <!-- fix fejléc, üveg-effektus -->
  <nav class="navbar navbar-expand-lg navbar-dark">
    <a class="navbar-brand" href="index.html">  <!-- logó + cégnév -->
      <img src="img/LOGÓTESZT 2 good.png" alt="Nagy Árpi Kft." height="30">
      Nagy Árpi Kft.
    </a>
    
    <button class="navbar-toggler" ...>  <!-- mobil hamburger gomb -->
    
    <ul class="navbar-nav gap-3">
      <li class="nav-item"><a href="index.html">Főoldal</a></li>
      
      <li class="nav-item dropdown">               <!-- legördülő menü -->
        <a class="dropdown-toggle" data-bs-toggle="dropdown">Termékek</a>
        <ul class="dropdown-menu">
          <li><a href="leheltermekek.html">Személyes technológia</a></li>
          <li><a href="materemekek.html">Konyhai és háztartás</a></li>
          <li><a href="kazaitermekek.html">Fejlett technológia</a></li>
        </ul>
      </li>
      
      <li class="nav-item"><a href="mate.html">Rólunk</a></li>
      <li class="nav-item"><a href="kazai.html">Kapcsolat</a></li>
    </ul>
    
    <a href="kosar.html" class="cart-icon">  <!-- kosár ikon számlálóval -->
      <i class="fas fa-shopping-cart"></i>
      <span class="cart-count">0</span>
    </a>
  </nav>
</header>
```

**Hover dropdown asztali nézetben:** CSS média-lekérdezéssel valósítottuk meg, hogy egér ráhúzáskor nyíljon meg (nem kattintásra). A `padding-top: 10px` egy „hidat" képez az egér pozíciója és a menü között, hogy ne záródjon be átmozgatás közben.

```css
@media (hover: hover) and (min-width: 992px) {
    .nav-item.dropdown:hover > .dropdown-menu { display: block; }
    .nav-item.dropdown > .dropdown-menu {
        margin-top: 0 !important;
        padding-top: 10px;
    }
}
```

**Mobilon** Bootstrap kattintásos viselkedés marad (`data-bs-toggle="dropdown"`).

---

## 5. A CSS stíluslap felépítése (style.css)

### Sötét háttér radial gradienssel

```css
body {
    background-color: #050508;
    /* Kék fényfolt a tetején – kozmikus hatás */
    background-image: radial-gradient(ellipse at 50% 0%,
        rgba(0,80,180,0.12) 0%, transparent 60%);
    color: #fff;
}
```

### Fix fejléc üveg-effektussal (glassmorphism)

```css
.site-header {
    background: rgba(5, 5, 8, 0.88);     /* átlátszó fekete alap */
    backdrop-filter: blur(24px);           /* mögöttes tartalom elmosása */
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 1000;
}
```

A `backdrop-filter: blur()` CSS tulajdonság elmossa a fejléc mögötti tartalmat, ezzel üvegszerű hatást kelt.

### Gradiens szöveg

```css
.section-title {
    background: linear-gradient(135deg, #fff 55%, rgba(255,255,255,0.55));
    -webkit-background-clip: text;         /* háttér csak a szöveg formájára vágva */
    -webkit-text-fill-color: transparent;  /* a szöveg maga átlátszó */
    background-clip: text;
}
```

Ez a technika a szöveget átlátszóvá teszi, és a mögötte lévő gradienst mutatja meg, így a betűk gradiens színűek lesznek.

### Reszponzív kártyarács (CSS Grid)

```css
.card-grid {
    display: grid;
    gap: 1.5rem;
}
/* Asztali: 3 oszlop */
@media (min-width: 992px) {
    .card-grid { grid-template-columns: repeat(3, 1fr); }
}
/* Tablet: 2 oszlop */
@media (min-width: 576px) and (max-width: 991px) {
    .card-grid { grid-template-columns: repeat(2, 1fr); }
}
/* Mobil: 1 oszlop */
@media (max-width: 575px) {
    .card-grid { grid-template-columns: 1fr; }
}
```

Az `1fr` egység „1 szabad rész"-t jelent – a böngésző egyenlően osztja el a rendelkezésre álló helyet az oszlopok között.

### Kártya hover animáció

```css
.card { transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1); }

.card:hover {
    transform: translateY(-7px);               /* felfelé emelés */
    box-shadow: 0 20px 56px rgba(0,80,200,0.22); /* kék árnyék */
    border-color: rgba(0,113,227,0.35);          /* kék szegély */
}

.card:hover img { transform: scale(1.05); }    /* kép kis nagyítás */
```

A `cubic-bezier` egy egyéni gyorsulási görbe, amely természetesebb mozgást ad mint az egyenletes `linear`.

---

## 6. A főoldal (index.html)

### Carousel (képváltó)
Bootstrap `carousel` komponens, 3 slide-dal, 5 másodperces automatikus váltással:

```html
<div id="heroCarousel" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-inner">
        <div class="carousel-item active" data-bs-interval="5000">
            <!-- háttérkép inline style-ban -->
            <div class="hero-slide" style="background-image: url('...')">
                <div class="hero-overlay">  <!-- sötét átlátszó réteg -->
                    <h1>ÁrpiBook Pro</h1>
                    <p class="price">699.967 Ft</p>
                    <a href="products/book-pro.html" class="btn">Megnézem</a>
                </div>
            </div>
        </div>
        <!-- ... további slide-ok -->
    </div>
    <!-- Előző/Következő gombok -->
    <button class="carousel-control-prev" data-bs-slide="prev">...</button>
    <button class="carousel-control-next" data-bs-slide="next">...</button>
</div>
```

### „Miért minket?" szekció
3 egyforma `feature-card` kártya Font Awesome ikonokkal:

```html
<section class="container py-5">
    <h2 class="section-title">Miért minket válasszon?</h2>
    <div class="card-grid mt-3">
        <article class="feature-card">
            <i class="fas fa-rocket fa-2x mb-3 d-block"></i>
            <h3 class="card-title">Innovatív megoldások</h3>
            <p class="card-text">Legújabb technológiák alkalmazása minden termékünkben.</p>
        </article>
        <!-- ... -->
    </div>
</section>
```

---

## 7. Kategóriaoldalak (leheltermekek.html, materemekek.html, kazaitermekek.html)

Mindhárom kategóriaoldal azonos HTML sablont követ:

```html
<main class="main-content">
    <!-- Fejléc sáv kategória ikon + cím + alcím -->
    <div class="page-hero">
        <div class="container">
            <span class="category-badge"><i class="fas fa-microchip"></i></span>
            <h1 class="section-title">Személyes Technológia</h1>
            <p class="section-subtitle">Csúcstechnológia a mindennapokhoz</p>
        </div>
    </div>

    <!-- Termék kártyák rácsban -->
    <div class="container">
        <div class="card-grid">
            <a href="products/book-pro.html" class="card">
                <img src="img/kep.jpg" alt="ÁrpiBook Pro">
                <div class="card-body">
                    <h2 class="card-title">ÁrpiBook Pro</h2>
                    <p class="card-text">Rövid leírás.</p>
                    <p class="price">699.967 Ft</p>
                </div>
            </a>
        </div>
    </div>
</main>
```

A kártya maga egy `<a>` link, így az egész kártya kattintható és a termékre navigál.

---

## 8. Termékoldal sablon (products/*.html)

```html
<main class="main-content">
    <div class="container py-5">
        <div class="product-hero">
            <!-- Vissza gomb a kategóriaoldalra -->
            <a href="../leheltermekek.html" class="btn-back">
                <i class="fas fa-arrow-left"></i> Személyes Technológia
            </a>

            <!-- Termék kép -->
            <img src="../img/kep.jpg" alt="ÁrpiBook Pro">

            <!-- Adatok -->
            <h1>ÁrpiBook Pro</h1>
            <p class="price">699.967 Ft</p>
            <p class="product-description">Részletes termékleírás...</p>

            <!-- Kosárba gomb – URL paraméterrel adja át a termékazonosítót -->
            <a href="../kosar.html?product=book-pro" class="btn btn-primary btn-lg">
                <i class="fas fa-cart-shopping me-2"></i> Kosárba
            </a>
        </div>
    </div>
</main>
```

A `?product=book-pro` URL paraméter a `kosar.html` JavaScript kódjának szól: ez alapján tudja melyik terméket kell hozzáadni a kosárhoz.

---

## 9. Bevásárlókosár rendszer (kosar.html)

A kosár teljes egészében böngészőoldali JavaScript-tel működik – nincs szerver vagy adatbázis.

### Termékkatalógus

```javascript
const products = {
    'book-pro':  { name: 'ÁrpiBook Pro',  price: 699967, image: '...' },
    'phone-pro': { name: 'ÁrpiPhone Pro', price: 679969, image: '...' },
    // ... összesen 15 termék
};
```

Az árak egész számok (forintban), a megjelenítéskor a `toLocaleString('hu-HU')` formázza őket magyar formátumra (szóközzel tagolva).

### Oldalbetöltéskor – URL paraméter feldolgozása

```javascript
window.onload = function() {
    // Beolvassa az URL-ből a ?product=... paramétert
    const productId = new URLSearchParams(window.location.search).get('product');
    if (productId) addToCart(productId);  // ha van, hozzáadja
    updateCartDisplay();                   // frissíti a megjelenítést
};
```

### Kosár megjelenítése

```javascript
function updateCartDisplay() {
    // Megszámolja az azonos termékeket
    const productCounts = {};
    cart.forEach(item => {
        productCounts[item.name] = (productCounts[item.name] || 0) + 1;
    });

    // Minden egyedi termékhez HTML-t generál
    Object.entries(productCounts).forEach(([name, qty]) => {
        const item = cart.find(i => i.name === name);
        const itemTotal = item.price * qty;
        total += itemTotal;
        html += `<div class="cart-item">...</div>`;
    });
}
```

### ÁFA számítás

```javascript
const vatAmount = Math.round(total * 0.27);  // 27% ÁFA kiszámítása
subtotal.textContent = formatPrice(total - vatAmount);  // nettó ár
vat.textContent = formatPrice(vatAmount);               // ÁFA összeg
cartTotal.textContent = formatPrice(total);             // bruttó összeg
```

### Mennyiség módosítása

```javascript
function changeQty(name, delta) {
    if (delta > 0) {
        // +1: másolat hozzáadása a kosár tömbhöz
        const item = cart.find(i => i.name === name);
        cart.push(item);
    } else {
        // -1: utolsó előfordulás törlése
        const idx = cart.findLastIndex(i => i.name === name);
        if (idx !== -1) cart.splice(idx, 1);
    }
    updateCartDisplay();
}
```

---

## 10. Rólunk oldal (mate.html)

Két szekcióból áll:

1. **Cégbemutató szöveg** – egy `feature-card` kártyában, `col-lg-8` szélességben (asztali nézeten nem tölti ki a teljes sort)
2. **Csapattagok kártyái** – 3 egyforma `feature-card` kártya `card-grid`-ben

| Csapattag | Ikon | Szerepkör |
|-----------|------|-----------|
| Lehel | `fa-microchip` | Vezérigazgató · Vezető fejlesztő |
| Máté | `fa-bullhorn` | PR-vezető · Igazgató |
| András | `fa-robot` | Tartalomért- és minőségért felelős igazgató |

---

## 11. Kapcsolat oldal (kazai.html)

Három egyforma magasságú kártya Bootstrap `row` + `align-items-stretch` + `h-100` kombinációval:

```html
<div class="row justify-content-center g-4 align-items-stretch">
    <div class="col-md-4">
        <div class="feature-card text-center h-100">
            ...Telefon...
        </div>
    </div>
    <div class="col-md-4">
        <div class="feature-card text-center h-100">
            ...E-mail...
        </div>
    </div>
    <div class="col-md-4">
        <div class="feature-card text-center h-100">
            <h3>Ügyfélszolgálat</h3>
            <p>Budapest, Váci utca 69.</p>
        </div>
    </div>
</div>
```

Az `align-items-stretch` a sorban lévő oszlopokat egyforma magasságra nyújtja, a `h-100` a kártyát kiterjeszti az oszlop teljes magasságára.

---

## 12. Árképzési séma

Minden termék ára **69-cel vagy 67-tel kezdődik és végződik** – ez a vállalati márkaidentitás része.

| Termék | Ár |
|--------|----|
| ÁrpiBook Pro | 699.967 Ft |
| ÁrpiPhone Pro | 679.969 Ft |
| ÁrpiWatch Pro | 69.967 Ft |
| ÁrpiPad Pro | 679.667 Ft |
| ÁrpiEar Pro | 67.967 Ft |
| ÁrpiTV Pro | 697.669 Ft |
| ÁrpiRobot Pro | 6.769.967 Ft |
| ÁrpiVac Pro | 697.767 Ft |
| ÁrpiMiniBot | 69.769 Ft |
| Árpiszívó | 69.969 Ft |
| Árpimosó | 679.769 Ft |
| Árpisütő | 697.967 Ft |
| Árpisütő Pro | 699.669 Ft |
| Árpihűtő | 697.769 Ft |
| Árpimikró | 67.969 Ft |

---

## 13. Hogyan adjunk hozzá új terméket?

### 1. lépés – Képet helyezz az `img/` mappába

Ajánlott formátum: JPEG, min. 800px széles.

### 2. lépés – Kategóriaoldalon add hozzá a kártyát

Pl. `leheltermekek.html` fájlban, a `.card-grid` div-be:

```html
<a href="products/uj-termek.html" class="card">
    <img src="img/uj-kep.jpg" alt="ÁrpiXYZ Pro">
    <div class="card-body">
        <h2 class="card-title">ÁrpiXYZ Pro</h2>
        <p class="card-text">Rövid leírás.</p>
        <p class="price">699.967 Ft</p>
    </div>
</a>
```

### 3. lépés – Hozz létre termékoldalt (`products/uj-termek.html`)

Másold le egy meglévő termékoldalt (pl. `book-pro.html`), és cseréld le:
- `<title>` → termék neve
- `<img src>` → `../img/uj-kep.jpg`
- `<h1>` → terméknév
- `<p class="price">` → ár
- `.product-description` → leírás
- `href="../kosar.html?product=uj-termek"` → egyedi azonosító (kisbetű, kötőjeles)

### 4. lépés – Add hozzá a kosár katalógushoz (`kosar.html`)

A JavaScript `products` objektumhoz:

```javascript
'uj-termek': { name: 'ÁrpiXYZ Pro', price: 699967, image: 'img/uj-kep.jpg' },
```

---

## 14. Lábléc (minden oldalon azonos)

```html
<footer class="site-footer">
    <div class="footer-content">
        <div class="footer-legal">
            <a href="aszf.html">ÁSZF</a>
            <a href="adatvedelem.html">Adatvédelmi Irányelvek</a>
        </div>
        <div class="footer-social">
            <!-- Facebook és Instagram linkek -->
        </div>
        <div class="copyright">&copy; 2026 Nagy Árpi Kft. Minden jog fenntartva.</div>
        <div class="warning-text">
            A weboldal tartalma kitaláció... Készült a Kandó Kálmán Informatikai Technikumban.
        </div>
    </div>
</footer>
```

---

## 15. Jogi nyilatkozat

Ez az oldal egy **iskolai projektmunka**. Minden termék, ár, elérhetőség és egyéb adat fiktív. A weboldal nem valódi e-kereskedelmi célokat szolgál.

Készítette: **Lehel, Máté, András** – Kandó Kálmán Informatikai Technikum, 2026.
