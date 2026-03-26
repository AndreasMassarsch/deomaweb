# Deoma — Webbplats-brief för Claude Code

## Design-filosofi

**Inspirerat av Mondaine.com — Swiss functional minimalism.**

- Vitt är bakgrunden. Alltid.
- Svart är texten. Alltid.
- Rött är accenten. Sparsamt.
- Ingenting finns på sidan utan ett syfte.
- Luft är ett designelement i sig.
- Inga gradienter. Inga skuggor. Inga animationer utöver enkel fade.
- Gridbaserat. Strikt. Precist.

Österrikiska flaggan (röd · vit · röd) är kulturell referens, inte dekoration.
Den syns bara som ett litet vertikalt sigill i logotypen.

---

## Färgpalett

```css
--red:       #CC0000;   /* Österrikisk röd — flaggfärgen, också Swiss design-klassikern */
--black:     #111111;   /* Rubrik- och logotypfärg */
--text:      #1A1A1A;   /* Brödtext */
--muted:     #888888;   /* Labels, metadata */
--border:    #E0E0E0;   /* Linjer och kortborders */
--bg:        #FFFFFF;   /* Alltid vit bakgrund */
--bg-alt:    #F5F5F5;   /* Alternerande sektioner — inte mer än detta */
```

**Färgregel:** Röd används på max 2–3 ställen per sida:
1. CTA-knapp (fylld röd)
2. Hover-state på textlänkar
3. En liten detalj i logotypen

---

## Typografi

```
Enda font: "Neue Haas Grotesk" finns ej gratis — använd "DM Sans" som närmaste match.
```

```html
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,300&display=swap" rel="stylesheet">
```

**Hierarki:**
```
Display/H1:    DM Sans 300 (light!), 5–8rem, letter-spacing: -0.02em, #111111
H2:            DM Sans 300, 2.5–3.5rem, letter-spacing: -0.01em
H3/korttitel:  DM Sans 500, 1rem, letter-spacing: 0.01em
Labels/eyebrow: DM Sans 400, 0.7rem, letter-spacing: 0.2em, VERSALER, #888888
Brödtext:      DM Sans 300, 1rem, line-height: 1.75, #1A1A1A
Nav:           DM Sans 400, 0.85rem, #111111
```

**Viktig detalj:** Stora rubriker ska vara LÄTT (weight 300) — det är det som ger Mondaine-känslan. Inte bold. Inte medium. Light och stor.

---

## Logotyp

```
[▌] DEOMA
```

- `[▌]` = Litet vertikalt sigill: 4px bred × 22px hög, tre lika bands: röd / vit / röd
  (Österrikiska flaggan roterad 90°)
- `DEOMA` = DM Sans 500, 1.5rem, letter-spacing: 0.12em, #111111
- Under: `Delin & Massarsch AB` — DM Sans 300, 0.5rem, letter-spacing: 0.2em, versaler, #888888

Sigillet är den enda "grafiken" i hela logotypen. Ingen ikon, ingen cirkel, inget badge.

---

## Layout-principer (Mondaine-regler)

1. **Max-width: 1200px**, centrerad, padding: 0 2.5rem
2. **Sektionshöjd:** Generöst — minst 120px padding top/bottom. Sektioner ska andas.
3. **Grid:** Antingen 2-kolumns eller 3-kolumns. Aldrig mixat inom samma sektion.
4. **Linjer:** En enkel `1px solid #E0E0E0` är den enda visuella separatorn som behövs.
5. **Knappar:** Kantigt (border-radius: 0 eller max 2px). Mondaine använder aldrig rundade knappar.
6. **Inga box-shadows** utom `0 1px 3px rgba(0,0,0,0.08)` på kort om det behövs.

---

## Sidstruktur

---

### 1. Navigation (sticky, vit)

```
[▌] DEOMA                          Vad vi gör    Portfolio    Om oss    Kontakt
    delin & massarsch ab
```

- Bakgrund: `#FFFFFF`, `border-bottom: 1px solid #E0E0E0`
- Höjd: 64px
- Nav-hover: text blir `#CC0000`
- Ingen hamburger-meny nödvändig för MVP

---

### 2. Hero

Bakgrund: `#FFFFFF`  
Höjd: `calc(100vh - 64px)`  
Innehållet är centrerat vertikalt och börjar en tredjedel ner från toppen.

```
INNOVATION · INVESTERING · RÅDGIVNING
(DM Sans 400, 0.7rem, versaler, letter-spacing: 0.2em, #888888)


Vi bygger idéer
som blir bolag.
(DM Sans 300, clamp(3.5rem, 7vw, 7rem), letter-spacing: -0.02em, #111111)
Max 2 rader.


En enkel röd linje: width 40px, height 2px, background #CC0000
(Enda "grafiken" i hero)


Deoma är ett boutique-innovationsbolag med lång erfarenhet av att ta
digitala tjänster från idé till marknad — med eget kapital, egna
händer och ett genuint engagemang.
(DM Sans 300, 1.05rem, line-height: 1.75, #1A1A1A, max-width: 50ch)


[  Se vår portfolio  ]    Läs om oss →
(Röd fylld knapp, 0 border-radius)   (Textlänk, röd hover)
```

Ingen bakgrundsbild. Ingen gradient. Ingenting mer.

---

### 3. Vad vi gör

Bakgrund: `#F5F5F5`  
Full padding: `140px 0`

```
VAD VI GÖR
(label-stil)

Tre sätt vi
skapar värde.
(H2, DM Sans 300, stor)
```

**3-kolumns grid, max-width 1200px:**

```
01                    02                    03
─────────────────     ─────────────────     ─────────────────
Egna tjänster         Tidig investering     Rådgivning

Vi identifierar       Vi investerar         Ibland är den
problem som           kapital och           bästa insatsen
förtjänar eleganta    kompetens mot         en klok röst i
lösningar. Från       ägarandel — men       rummet. Vi är
koncept till          bara med en aktiv     erfarna bollplank
lansering.            roll.                 och konsulter.
```

- Siffran: DM Sans 300, 3.5rem, `#E0E0E0` — stor, diskret, övre vänster
- Titel: DM Sans 500, 1rem, `#111111`, versaler, letter-spacing: 0.05em
- Tunn `1px solid #E0E0E0` linje längs toppen av varje kolumn
- Hover: linjen längst upp tonar till `#CC0000`
- Brödtext: DM Sans 300, `#1A1A1A`

---

### 4. Portfolio

Bakgrund: `#FFFFFF`  
Full padding: `140px 0`

```
TRACKRECORD

Bolag vi byggt.
```

**2×2 grid (eller 4-kolumns beroende på skärmbredd):**

```
┌─────────────────────────┐  ┌─────────────────────────┐
│                         │  │                         │
│  Avima                  │  │  Assently               │
│  Förvärvad              │  │  Förvärvad              │
│                         │  │                         │
│  Startade som           │  │  Pionjär inom           │
│  webforum.com. Ett av   │  │  e-signering på den     │
│  Sveriges tidiga        │  │  svenska marknaden.     │
│  communities.           │  │                         │
│                         │  │                         │
│  Exit → IB Finder       │  │  Exit → Verified        │
└─────────────────────────┘  └─────────────────────────┘

┌─────────────────────────┐  ┌─────────────────────────┐
│  ● Aktiv                │  │  ● Aktiv                │
│                         │  │                         │
│  Tagd.ai                │  │  Tolkster.ai            │
│                         │  │                         │
│  Modern avtals-         │  │  AI-driven tolknings-   │
│  hantering med AI i     │  │  tjänst. Vi är          │
│  kärnan. Vi är          │  │  grundare.              │
│  grundare.              │  │                         │
│                         │  │                         │
│  tagd.ai →              │  │  tolkster.ai →          │
└─────────────────────────┘  └─────────────────────────┘
```

**Kortstil:**
- Bakgrund: `#F5F5F5`
- Border: ingen (bara bakgrundsfärg för avgränsning, alternativt `1px solid #E0E0E0`)
- Padding: `40px`
- Företagsnamn: DM Sans 500, 1.4rem, `#111111`
- "Förvärvad": DM Sans 400, 0.7rem, versaler, `#888888`
- "● Aktiv": röd punkt + DM Sans 400, 0.7rem, `#CC0000`
- "Exit →" / länk: DM Sans 400, 0.8rem, `#888888`, hover: `#CC0000`

---

### 5. Om oss

Bakgrund: `#F5F5F5`  
Full padding: `140px 0`

**2-kolumns layout, 1:1:**

**Vänster:**
```
OM OSS

Deoma i korthet.
```

**Höger (brödtext, DM Sans 300, 1.05rem, line-height 1.75):**
```
Deoma grundades av Delin och Massarsch med en enkel
övertygelse: de bästa digitala produkterna föds när
erfarna byggare är med från dag ett.

Vi har vunnit, vi har lärt oss, och vi bär med oss
ett starkt nätverk, en känsla för timing och ett
genuint intresse för problemlösning.

Letar du efter en partner som förstår tekniken,
marknaden och vad det kostar att bygga något
verkligt? Hör av dig.
```

**Under texten — 4 siffror i en rad:**
```
25+               2                 4+                3
─────────         ─────────         ─────────         ─────────
Års               Lyckade           Aktiva            Sätt vi
erfarenhet        exits             bolag             hjälper
```
Siffrorna: DM Sans 300, 2.5rem, `#111111`
Label: DM Sans 400, 0.7rem, versaler, `#888888`

---

### 6. Kontakt

Bakgrund: `#111111` (svart)  
Full padding: `120px 0`

```
KONTAKT

Har du ett projekt?
(DM Sans 300, stor, #FFFFFF)


Hör av dig — vi svarar alltid.
(DM Sans 300, 1rem, #888888)


[  hej@deoma.se  ]
(Röd fylld knapp, border-radius: 0, padding: 1rem 2.5rem)
```

Ingenting mer. Ingen adress, inga sociala ikoner, inga formulär.

---

### 7. Footer

Bakgrund: `#111111`  
`border-top: 1px solid #333333`  
Padding: `2rem 2.5rem`

```
© 2025 Delin och Massarsch AB                           DEOMA
```

Footer-text: DM Sans 300, 0.75rem, `#555555`  
DEOMA: DM Sans 500, 0.85rem, letter-spacing: 0.15em, `#333333`

---

## Tekniska krav

- Ren **`index.html`** med `<style>` och `<script>` inline — noll beroenden utom Google Fonts
- Smooth scroll (`scroll-behavior: smooth`)
- **Responsiv:** På mobil staplas alla kolumner, nav-länkarna döljs
- Enkel fade-in animation: `opacity 0 → 1, translateY 16px → 0` på `.hero-content`, 0.5s, ingen stagger nödvändig
- Inga JS-ramverk, inga build-steg

---

## Kommando till Claude Code

```
Bygg en komplett ensidig hemsida för Deoma (Delin och Massarsch AB) 
baserat på denna specifikation. Skapa en enda index.html-fil med 
inbäddad CSS. Följ Mondaine-inspirerad Swiss minimalism: vitt, svart, 
röd (#CC0000) som enda accent. Font: DM Sans via Google Fonts, 
weight 300 på alla rubriker. Inga gradienter, inga skuggor, inga 
dekorativa element. Border-radius: 0 på alla knappar. Generösa 
whitespace-marginaler (minst 120px padding per sektion). Alla 
sektioner och allt innehåll från specen ska finnas med.
```
