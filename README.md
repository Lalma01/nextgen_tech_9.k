# Nagy Árpi Kft. – Webshop

Statikus, sötét témájú e-kereskedelmi webshop. Tiszta HTML + CSS + Bootstrap 5, kliensoldali JS kosárral. Nincs build-lépés, szerver vagy adatbázis – a fájlok közvetlenül megnyithatók.

URL: lalma01.github.io/nextgen_tech_9.k

## Technológiák (CDN-ről)

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
```

Egyéni stílusok: `style.css` (minden oldal betölti).

## Fájlstruktúra

```
index.html                főoldal (carousel + feature kártyák)
leheltermekek.html        kategória: Személyes technológia
matetermekek.html         kategória: Konyhai és háztartás
kazaitermekek.html        kategória: Fejlett technológia
mate.html / kazai.html    Rólunk / Kapcsolat
kosar.html                kosár (JS)
aszf.html / adatvedelem.html
products/*.html           egyedi termékoldalak
img/                       képek
style.css                 közös stíluslap
```

**Képútvonalak:** root oldalak `img/...`, a `products/` oldalak `../img/...` formát használnak.

## Felépítés

A navbar és footer minden oldalon azonos. A kategóriaoldalak `.card-grid`-be tett `<a class="card">` elemeket tartalmaznak; a teljes kártya egy link a termékoldalra.

```css
.card-grid { display: grid; gap: 1.5rem; }
@media (min-width: 992px) { .card-grid { grid-template-columns: repeat(3, 1fr); } }
@media (min-width: 576px) and (max-width: 991px) { .card-grid { grid-template-columns: repeat(2, 1fr); } }
@media (max-width: 575px) { .card-grid { grid-template-columns: 1fr; } }
```

Kiemelt CSS-technikák a `style.css`-ben: glassmorphism fejléc (`backdrop-filter: blur()`), gradiens szöveg (`background-clip: text`), kártya hover (`transform` + `box-shadow`), hover-dropdown asztali nézetben (`@media (hover: hover)`).

## Kosár (kosar.html)

A termékoldal `Kosárba` gombja URL-paraméterrel ad át azonosítót: `kosar.html?product=<id>`. A kosár ezt olvassa ki betöltéskor:

```javascript
const products = {
    'book-pro': { name: 'ÁrpiBook Pro', price: 699967, image: '...' },
    // ... minden termék itt szerepel
};

window.onload = () => {
    const id = new URLSearchParams(location.search).get('product');
    if (id) addToCart(id);
    updateCartDisplay();
};
```

A `cart` tömb azonos termékből többet is tárolhat; `updateCartDisplay()` darabszámra csoportosít, ÁFA-t számol (`Math.round(total * 0.27)`), és `toLocaleString('hu-HU')`-val formáz. Üres kosárnál az összegző oszlop elrejtődik, a tartalom középre kerül.

## Új termék hozzáadása

1. Kép az `img/` mappába.
2. Kártya a kategóriaoldal `.card-grid`-jébe (`<a href="products/uj.html" class="card">`).
3. Termékoldal: másolj le egy `products/*.html`-t, cseréld a `<title>`, `<img src>`, `<h1>`, ár, leírás és `?product=<id>` értékeket.
4. Vedd fel a terméket a `kosar.html` `products` objektumába **ugyanazzal az id-vel és árral** (a kártya, a termékoldal és a kosár ára egyezzen).
