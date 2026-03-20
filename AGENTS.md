# Weart HU – WP Astro projekt – Agent útmutató

Ez a dokumentum a Cursor/AI agent számára készült: a projekt kontextusát, konvencióit és folyamatosan frissülő állapotát írja le. **A projekt során érdemes ezt az AGENTS.md-t naprakészen tartani** (új komponensek, döntések, környezetváltozások rögzítése).

---

## Projekt áttekintés

- **Név:** weart-hu-wp-astro  
- **Típus:** Astro alapú webprojekt (WordPress kapcsolattal a név alapján)  
- **Cél:** Weart magyar webes felület (részletek a fejlesztés során bővülnek)

---

## Tech stack (aktuális)

| Technológia | Verzió / megjegyzés |
|-------------|----------------------|
| Astro      | ^5.17.1              |
| Tailwind   | ^4.x (@tailwindcss/vite) |
| Heroicons  | astro-heroicons (outline / solid) |
| Nyelv      | TypeScript (tsconfig.json) |
| Stílusok   | `src/styles/global.css` – `@import "tailwindcss"` |

---

## Projektstruktúra

```
weart-hu-wp-astro/
├── astro.config.mjs    # Astro + Tailwind Vite plugin
├── src/
│   ├── layouts/
│   │   └── Layout.astro   # Közös layout, Tailwind import, html/head/body
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Hero.astro
│   │   └── Testimonials.astro   # Ajánlóblokk (vélemények) karuszel, Hero alatt
│   ├── pages/
│   │   └── index.astro    # Főoldal
│   └── styles/
│       └── global.css     # Tailwind entry
├── public/               # Statikus fájlok (pl. favicon.svg)
└── AGENTS.md             # Ez a fájl
```

---

## Konvenciók és döntések

- **Nyelv:** Oldal alapértelmezett nyelve `hu` (Layout.astro: `lang="hu"`).
- **Stílus:** Tailwind CSS v4; globális stílusok a `src/styles/global.css`-ben, layoutban importálva.
- **Layout:** Egy közös `Layout.astro` biztosítja a dokumentum szerkezetét és a Tailwind betöltését; az oldalak ezt használják.
- **Ikonok:** [Heroicons](https://heroicons.com/) az `astro-heroicons` csomaggal; import pl. `import Bars3 from 'astro-heroicons/outline/Bars3.astro'` vagy `import Star from 'astro-heroicons/solid/Star.astro'`.

---

## Következő lépések / TODO (sablon)

- [ ] WordPress integráció (ha szükséges) – részletek később
- [ ] További oldalak / komponensek hozzáadása
- [ ] Környezetváltozók és build/ deploy beállítások dokumentálása

---

## Frissítési napló (AGENTS.md)

| Dátum       | Változás |
|------------|----------|
| 2025-03-08 | Projekt létrehozva; Tailwind v4 telepítve (@astrojs add tailwind). Layout.astro + global.css, alap index oldal. AGENTS.md létrehozva. |
| 2025-03-08 | astro-heroicons telepítve; Header (Bars3), Hero (Star) átállítva Heroiconsra. |
| 2025-03-08 | Testimonials.astro: „Vélemények” ajánlóblokk a Hero alá (cím, bevezető, kártyák karuszel, teal nyilak + pontok). |

---

*Az agentnek javasolt: minden jelentősebb változásnál (új függőség, új mappa, konvenció, környezet) rövid bejegyzés kerüljön a „Konvenciók és döntések” vagy a „Frissítési napló” szekcióba.*
