---
name: virtual-regatta-brand-guidelines
description: "Apply Virtual Regatta's visual identity consistently across all document types (Word, PowerPoint, HTML, PDF, Excel). Use this skill before any document creation task for Virtual Regatta — emails, presentations, reports, contracts, spreadsheets, or any branded content. Triggers: any mention of 'Virtual Regatta document', 'charte VR', 'document VR', or any creation task requiring Virtual Regatta branding."
---

# Virtual Regatta Brand Guidelines Skill

## Purpose
Apply Virtual Regatta's visual identity consistently across all document types (Word, PowerPoint, HTML, PDF). Read this file before any document creation task.

---

## Color Palette

### Palette Corporate (documents, emails, contrats)

| Name | Hex | Usage |
|---|---|---|
| Bleu VR | #00425c | Titres, en-tetes de tableaux, objet, elements structurants |
| Rose VR | #dc006b | Accents, highlights, donnees cles |
| Gris VR | #58585b | Texte courant, corps de document |
| Bleu VR clair | #e6f0f4 | Lignes alternees de tableaux |
| Blanc | #ffffff | Fond de page, texte sur fond colore |

### Palette VR Dark (dashboards, artifacts HTML, presentations commerciales)

| Name | Hex | CSS var | Usage |
|---|---|---|---|
| Background | #0a0a0a | --bg | Fond de page principal |
| Card | #111111 | --card | Fond des cartes et blocs |
| Card2 | #161616 | --card2 | Fond secondaire (commentaires, thead table) |
| Border | #1c1c1c | --border | Bordures, separateurs |
| Rose | #E8197C | --rose | Accent principal, highlights, bordure commentaires, bouton actif |
| Cyan | #00b4d8 | --cyan | Accent secondaire, donnees complementaires |
| Vert | #00e676 | --vert | Positif, hausse, en cours, succes |
| Orange | #ff9100 | --orange | Attention, valeur intermediaire |
| Jaune | #ffd600 | --jaune | Alerte, warning |
| Rouge | #ff3d00 | --rouge | Negatif, baisse, critique |
| Blanc | #ffffff | --blanc | Texte principal sur fond sombre |
| Text | #dddddd | --text | Texte courant sur fond sombre |
| Text2 | #888888 | --text2 | Texte secondaire, labels, metadata |
| Gris | #666666 | --gris | Elements neutres |

**Semi-transparents pour badges** : chaque couleur a une variante `-d` a `rgba(…, .15)` pour les fonds de badges (ex: `--rose-d: rgba(232,25,124,.15)`).

### Palette VR Light (dashboards en mode clair, toggle `body.light`)

| Name | Hex | CSS var | Usage |
|---|---|---|---|
| Background | #ffffff | --bg | Fond de page blanc |
| Card | #f7f8fa | --card | Fond des cartes |
| Card2 | #eef2f5 | --card2 | Fond secondaire |
| Border | #d9d9d9 | --border | Bordures, separateurs |
| Rose | #D12E77 | --rose | Accent principal (ajuste pour contraste) |
| Cyan | #005A6F | --cyan | Accent secondaire (plus fonce) |
| Vert | #0e8a45 | --vert | Positif (assombri) |
| Orange | #c96d00 | --orange | Attention (assombri) |
| Jaune | #b89700 | --jaune | Alerte (assombri) |
| Rouge | #d32f2f | --rouge | Negatif (assombri) |
| Blanc | #00425c | --blanc | **Texte principal = Bleu VR** (inversion) |
| Text | #58585b | --text | Texte courant |
| Text2 | #6B6B6E | --text2 | Texte secondaire |

**Semi-transparents VR Light** : opacite reduite a `.08-.10` (ex: `--rose-d: rgba(209,46,119,.1)`).

---

## Typography

| Element | Police | Taille | Couleur |
|---|---|---|---|
| Principale | Montserrat (fallback Arial) | — | — |
| H1 | Montserrat Bold | 24-40pt | Bleu VR #00425c (light) / #fff (dark) |
| H2 | Montserrat SemiBold | 18-22pt | Bleu VR #00425c (light) / #fff (dark) |
| H3 | Montserrat Medium | 14-16pt | Bleu VR #00425c (light) / #fff (dark) |
| Corps | Montserrat Regular | 10pt | Gris VR #58585b (light) / #ddd (dark) |
| Accent / objet | Montserrat Bold | 10pt | Bleu VR #00425c (light) / Rose #E8197C (dark) |

**Google Fonts import (HTML)** :
```
https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,700;1,800;1,900&display=swap
```

---

## Regles visuelles validees

- **Objet du courrier** : Bleu VR (#00425c), gras
- **Pas de ligne separatrice** dans l'en-tete ni le pied de page
- **En-tete** : logo Virtual Regatta seul (haut gauche), sans bandeau colore
- **Pied de page** : sobre — texte confidentiel a gauche, numero de page a droite, Gris VR 8pt
- **Signature** : Nom en Bleu VR + titre en Gris VR — pas de mention "Virtual Regatta" en bas (le logo suffit)

---

## Tableaux

### Tableaux light (documents, emails)
- **En-tete** : fond Bleu VR (#00425c), texte blanc, gras
- **Lignes** : alternance blanc (#ffffff) / Bleu VR clair (#e6f0f4)
- **Bordures** : fines (#cccccc)
- **Texte cellules** : Gris VR (#58585b), 10pt

### Tableaux dark (dashboards HTML)
- **En-tete (thead)** : fond #161616, texte #888 uppercase 10px bold, letter-spacing .8px, sticky top
- **Lignes** : fond transparent, bordure bottom #1a1a1a, hover rgba(232,25,124,.04)
- **Texte cellules** : #ddd, 11px
- **Tri** : cursor pointer sur thead, hover -> texte blanc

---

## Reference PDF (ReportLab) — modele valide

```python
from reportlab.lib.pagesizes import A4
from reportlab.lib import colors
from reportlab.lib.units import cm
from reportlab.lib.styles import ParagraphStyle
from reportlab.platypus import SimpleDocTemplate, Paragraph, Spacer, Table, TableStyle
from reportlab.lib.enums import TA_RIGHT, TA_JUSTIFY

BLEU_VR = colors.HexColor('#00425c')
ROSE_VR = colors.HexColor('#dc006b')
GRIS_VR = colors.HexColor('#58585b')
BLEU_VR_CLAIR = colors.HexColor('#e6f0f4')
W, H = A4
LOGO_PATH = "path/to/logo_vr.png"  # Logo Virtual Regatta PNG

def header_footer(canvas, doc):
    canvas.saveState()
    # Logo seul, sans ligne separatrice
    canvas.drawImage(LOGO_PATH, 2*cm, H - 2.2*cm, width=3.5*cm, height=1.5*cm,
                     preserveAspectRatio=True, mask='auto')
    # Pied de page sobre, sans ligne
    canvas.setFillColor(GRIS_VR)
    canvas.setFont("Helvetica", 8)
    canvas.drawString(2*cm, 1.2*cm, "Virtual Regatta — Confidentiel")
    canvas.drawRightString(W - 2*cm, 1.2*cm, f"Page {doc.page}")
    canvas.restoreState()

doc = SimpleDocTemplate(
    "output.pdf", pagesize=A4,
    topMargin=3.8*cm, bottomMargin=2.5*cm,
    leftMargin=2*cm, rightMargin=2*cm,
)

# Styles
s_body  = ParagraphStyle("body",  fontName="Helvetica", fontSize=10, textColor=GRIS_VR, leading=17, alignment=TA_JUSTIFY)
s_h2    = ParagraphStyle("h2",    fontName="Helvetica-Bold", fontSize=14, textColor=BLEU_VR, spaceBefore=16, spaceAfter=6)
s_objet = ParagraphStyle("objet", fontName="Helvetica-Bold", fontSize=10, textColor=BLEU_VR, spaceAfter=4)
s_right = ParagraphStyle("right", fontName="Helvetica", fontSize=10, textColor=GRIS_VR, alignment=TA_RIGHT)
s_meta  = ParagraphStyle("meta",  fontName="Helvetica", fontSize=10, textColor=GRIS_VR, leading=15)
s_sig   = ParagraphStyle("sig",   fontName="Helvetica-Bold", fontSize=11, textColor=BLEU_VR)

# Tableau
table_data = [
    ["Colonne 1", "Colonne 2", "Colonne 3"],   # en-tete
    ["Valeur A",  "Description A", "Q1 2026"],
    ["Valeur B",  "Description B", "Q2 2026"],
]
t = Table(table_data, colWidths=[3.2*cm, 10.5*cm, 3*cm])
t.setStyle(TableStyle([
    ('BACKGROUND', (0,0), (-1,0), BLEU_VR),
    ('TEXTCOLOR',  (0,0), (-1,0), colors.white),
    ('FONTNAME',   (0,0), (-1,0), 'Helvetica-Bold'),
    ('FONTSIZE',   (0,0), (-1,-1), 10),
    ('FONTNAME',   (0,1), (-1,-1), 'Helvetica'),
    ('TEXTCOLOR',  (0,1), (-1,-1), GRIS_VR),
    ('ROWBACKGROUNDS', (0,1), (-1,-1), [colors.white, BLEU_VR_CLAIR]),
    ('VALIGN',     (0,0), (-1,-1), 'MIDDLE'),
    ('TOPPADDING', (0,0), (-1,-1), 7),
    ('BOTTOMPADDING', (0,0), (-1,-1), 7),
    ('LEFTPADDING', (0,0), (-1,-1), 8),
    ('GRID',       (0,0), (-1,-1), 0.4, colors.HexColor('#cccccc')),
]))
```

---

## Reference HTML / Artifacts

### Theme Light (pages web, artifacts simples, landing pages)

```css
font-family: 'Montserrat', Arial, sans-serif;
background: #ffffff;
/* Titres */   color: #00425c;
/* Texte */    color: #58585b;
/* Accent */   color: #dc006b;
/* thead */    background: #00425c; color: #fff;
/* tr pair */  background: #e6f0f4;
```

### Theme VR Dark (dashboards, reportings interactifs, artifacts data)

Usage : tout dashboard de pilotage, artifact HTML data-driven, reporting interactif, game reports HTML.
References : VRO Race Control Center 2026, RORC Transatlantic Game Report 2026.

**Stack technique :**
- HTML5 single-file (pas de serveur, pas de build)
- Chart.js 4.4.1 via CDN (`https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js`)
- Google Fonts Montserrat
- CSS custom properties (variables)

#### CSS Variables — VR Dark (defaut)

```css
:root {
  --bg: #0a0a0a;
  --card: #111;
  --card2: #161616;
  --border: #1c1c1c;
  --rose: #E8197C;
  --rose-d: rgba(232,25,124,.15);
  --cyan: #00b4d8;
  --cyan-d: rgba(0,180,216,.15);
  --vert: #00e676;
  --vert-d: rgba(0,230,118,.15);
  --orange: #ff9100;
  --orange-d: rgba(255,145,0,.15);
  --jaune: #ffd600;
  --rouge: #ff3d00;
  --gris: #666;
  --gris2: #999;
  --blanc: #fff;
  --text: #ddd;
  --text2: #888;
}
```

#### CSS Variables — VR Light (toggle `body.light`)

Le mode light s'active via `body.classList.toggle('light')`. Toutes les variables sont surchargees :

```css
body.light {
  --bg: #ffffff;
  --card: #f7f8fa;
  --card2: #eef2f5;
  --border: #d9d9d9;
  --rose: #D12E77;
  --rose-d: rgba(209,46,119,.1);
  --cyan: #005A6F;
  --cyan-d: rgba(0,90,111,.08);
  --vert: #0e8a45;
  --vert-d: rgba(14,138,69,.1);
  --orange: #c96d00;
  --orange-d: rgba(201,109,0,.1);
  --jaune: #b89700;
  --rouge: #d32f2f;
  --gris: #999;
  --blanc: #00425c;    /* INVERSION : texte principal = bleu fonce */
  --text: #58585b;
  --text2: #6B6B6E;
}
```

**Points cles VR Light** :
- `--blanc` devient `#00425c` (Bleu VR) — c'est la couleur de texte principale en mode clair
- `--rose` ajuste de `#E8197C` a `#D12E77` pour meilleur contraste sur fond blanc
- `--cyan` passe de `#00b4d8` a `#005A6F` (plus fonce, accessible)
- Les verts/oranges/rouges sont assombris pour accessibilite sur fond clair
- Les semi-transparents `-d` passent de `.15` a `.08-.10` (plus subtils sur fond blanc)

#### Toggle Dark / Light — Implementation

```css
.theme-toggle {
  position: fixed;
  top: 16px;
  right: 16px;
  z-index: 200;
  background: var(--card);
  border: 1px solid var(--border);
  color: var(--text2);
  padding: 6px 14px;
  border-radius: 20px;
  cursor: pointer;
  font: 600 11px/1 'Montserrat', sans-serif;
  letter-spacing: .5px;
  transition: border-color .2s, color .2s;
}
.theme-toggle:hover { border-color: var(--rose); color: var(--blanc); }
```

```js
const themeBtn = document.querySelector('.theme-toggle');
themeBtn.addEventListener('click', () => {
  document.body.classList.toggle('light');
  const isLight = document.body.classList.contains('light');
  // Mettre a jour le label du bouton (avec i18n si actif)
  themeBtn.textContent = isLight ? T('ui.theme_light') : T('ui.theme_dark');
  rebuildCharts();  // Detruire et recreer tous les charts avec nouvelles couleurs
});
```

**IMPORTANT** : les charts Chart.js ne reagissent PAS aux CSS variables — il faut `rebuildCharts()` qui detruit chaque instance et la recree avec les couleurs lues dynamiquement via `getComputedStyle`.

#### Toggle FR / EN — Systeme i18n

Le dashboard supporte un toggle langue FR ↔ EN. Architecture :

```css
.lang-toggle {
  position: fixed;
  top: 16px;
  right: 120px;  /* A gauche du bouton theme */
  z-index: 200;
  /* Meme style que .theme-toggle */
}
```

```js
let currentLang = 'en';
const i18n = {
  en: { /* ~170 cles */ },
  fr: { /* ~170 cles */ }
};

function T(key) { return i18n[currentLang]?.[key] ?? i18n['en'][key] ?? key; }

function setLang(lang) {
  currentLang = lang;
  // Texte simple
  document.querySelectorAll('[data-i18n]').forEach(el => {
    el.textContent = T(el.dataset.i18n);
  });
  // HTML riche (commentaires avec <span class="hl">)
  document.querySelectorAll('[data-i18n-html]').forEach(el => {
    el.innerHTML = T(el.dataset.i18nHtml);
  });
  // Tooltips
  document.querySelectorAll('[data-i18n-tip]').forEach(el => {
    el.setAttribute('data-tip', T(el.dataset.i18nTip));
  });
  // Recreer charts avec labels traduits
  rebuildCharts();
}
```

**Attributs HTML** :
- `data-i18n="section.key"` — remplace `textContent`
- `data-i18n-html="comment.key"` — remplace `innerHTML` (pour garder les `<span class="hl">`)
- `data-i18n-tip="tip.key"` — met a jour l'attribut `data-tip` (tooltips)

**Ce qu'on ne traduit PAS** : noms de pays, noms de marques, abreviations techniques (DAU, WAU, B2B, IAP, VAT), montants, pourcentages, dates dans les charts.

#### Fond Isobathes — Pattern bathymetrique

Un motif de lignes de sonde (isobathes) en fond de page, genere par heightmap 2D Perlin + marching squares. Les contours ne se croisent jamais (propriete mathematique des courbes de niveau).

```css
body::before {
  content: '';
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
  opacity: .09;
  background-image: url("data:image/svg+xml,...");  /* SVG isobathes blanc */
  background-size: 1200px 1200px;
  background-repeat: repeat;
}
body.light::before {
  background-image: url("data:image/svg+xml,...");  /* SVG isobathes bleu #00425c */
  opacity: .10;
}
/* Le contenu doit etre au-dessus du pattern */
main { position: relative; z-index: 1; }
```

**Generation** (Python) :
1. Heightmap 2D avec bruit de Perlin (FBM 5 octaves, lacunarite 2.0, persistence 0.5)
2. Extraction de contours via marching squares a 8 niveaux de seuil
3. Chainage des segments + simplification RDP (epsilon 3.0)
4. Canvas 1200x1200, cellules 20px
5. SVG paths avec `stroke-width: 1`, `fill: none`
6. Dark : strokes `white`, Light : strokes `#00425c`
7. Encode en data URI inline dans le CSS

**ATTENTION z-index** : ne PAS mettre `position: relative; z-index: 1` sur `.theme-toggle`, `.lang-toggle` ou `.sidebar` — cela ecraserait leur `position: fixed`. Seul `main` recoit `position: relative; z-index: 1`.

#### Couleurs JS (pour Chart.js et rendu dynamique)

```js
const C = {
  rose: '#E8197C',
  cyan: '#00b4d8',
  vert: '#00e676',
  orange: '#ff9100',
  jaune: '#ffd600',
  rouge: '#ff3d00',
  blanc: '#fff'
};
```

**ATTENTION** : `C.text` et `C.text2` n'existent PAS dans l'objet C. Si besoin de gris pour Chart.js, utiliser `'#ddd'` ou `'#888'` en dur.

#### Composants UI Dark

**Header sticky** :
- Background gradient `linear-gradient(135deg, #0d1117, #141a24)`, border-bottom #1c1c1c
- Titre uppercase 13px bold, letter-spacing 2px, accent rose dans un `<span>`
- Boutons filtres : fond card, border #1c1c1c, texte #888, hover -> border rose + texte blanc
- Bouton actif : fond rose, border rose, texte blanc (classe `.act`)

**Cartes KPI** :
- Background #111, border 1px #1c1c1c, border-radius 10px, padding 16px 18px
- Barre coloree 3px en haut (`.r`=rose, `.c`=cyan, `.v`=vert, `.o`=orange, `.j`=jaune, `.g`=rouge)
- Label : 11px uppercase bold, letter-spacing 1.5px, couleur var(--text2)
- Valeur : clamp(22px, 2.4vw, 30px) weight 800, couleur var(--blanc)
- Sous-texte : 12px, couleur var(--text2)
- Grid : 6 colonnes, gap 12px

**Cartes graphiques** :
- Background #111, border 1px #1c1c1c, border-radius 10px, padding 18px
- Titre : 13px bold var(--blanc), avec badge optionnel (fond semi-transparent + texte couleur accent)
- Grid : 2 colonnes par defaut (`.cg`), variantes `.c3` (3 col) et `.c4` (4 col)

**Badges** :
- 9px bold uppercase, padding 3px 8px, border-radius 4px, letter-spacing .8px
- `.b-r` : fond rose-d, texte rose / `.b-c` : fond cyan-d, texte cyan / `.b-v` : fond vert-d, texte vert / `.b-o` : fond orange-d, texte orange

**Indicateurs de statut** :
- Pastille 7px ronde (`.sd`) avec box-shadow pour statuts actifs
- `.term` = gris / `.enc` = vert + glow / `.acq` = cyan + glow / `.av` = orange / `.ni` = rouge

**Jauges readiness** :
- Grid responsive (min 260px), fond card2, border #1c1c1c, radius 8px
- 8 segments de 6px de haut, radius 3px, couleur vert si `.on`, #2a1a1a si `.off`
- Score colore : `.high`=vert, `.med`=orange, `.low`=rouge

**Barres de progression** :
- Container 80px x 5px, fond #222, radius 3px
- Fill avec couleur dynamique (vert >80%, orange 50-80%, rouge <50%)

**Timeline Gantt** :
- Row flex, nom 200px, barre positionnee en absolute, radius 3px, opacite .75 -> 1 au hover
- Ligne "today" : 2px de large, couleur rose, z-index 10

**Commentaires analytiques** :
- margin-top 20px, padding 18px 22px
- Background var(--card2)
- Border-left 3px solid var(--rose)
- Border-radius 0 8px 8px 0
- Font-size 14px, line-height 1.85, couleur var(--text2)
- Highlights : `.hl` = var(--blanc) bold, `.up` = var(--vert) bold, `.dn` = var(--rouge) bold, `.mid` = var(--orange) bold
- Masque automatique si vide (`:empty { display: none }`)

**Titres de sections** :
- 36px weight 800, uppercase, letter-spacing 3px, couleur var(--blanc)
- Icone section (.sec-ico) : 32px, opacity .85, filter grayscale(.15)
- Flex avec gap 16px, margin-bottom 36px, padding-top 16px

**Sections separatrices (sous-sections)** :
- 12px bold uppercase, letter-spacing 2px, couleur var(--text2)
- Ligne horizontale apres le texte (`::after` flex 1px var(--border))

#### Chart.js — Configuration VR Dark

```js
// Axes
scales: {
  x: {
    ticks: { color: '#888', font: { size: 10 } },
    grid: { color: '#1c1c1c' }
  },
  y: {
    ticks: { color: '#888', font: { size: 10 } },
    grid: { color: '#1c1c1c' }
  }
}

// Legendes
plugins: {
  legend: {
    labels: { color: '#ccc', font: { size: 11 } }
  }
}

// Doughnut
plugins: {
  legend: {
    position: 'bottom',
    labels: { color: '#ccc', font: { size: 10 }, padding: 12 }
  }
}

// Palette barres : rose pour reel/realise, cyan pour objectif/forecast
// Scatter : fond semi-transparent, border plein
```

**Regle Canvas** : ne JAMAIS utiliser `roundRect` (pas supporte partout). Toujours utiliser `quadraticCurveTo` pour les coins arrondis.

#### Animations & Micro-interactions (VR Dark)

Les animations apportent un effet premium aux dashboards et game reports HTML. Toutes sont declenchees au scroll via IntersectionObserver (une seule execution par element).

##### Scroll Reveal (sections, cartes, KPIs)

Chaque element avec `.reveal` apparait au scroll avec un glide-up fluide.

```css
.reveal {
  opacity: 0;
  transform: translateY(32px);
  transition: opacity .7s cubic-bezier(.16,1,.3,1), transform .7s cubic-bezier(.16,1,.3,1);
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
/* Stagger children — chaque enfant direct est decale de 80ms */
.reveal.visible > *:nth-child(1) { transition-delay: 0ms; }
.reveal.visible > *:nth-child(2) { transition-delay: 80ms; }
.reveal.visible > *:nth-child(3) { transition-delay: 160ms; }
.reveal.visible > *:nth-child(4) { transition-delay: 240ms; }
.reveal.visible > *:nth-child(5) { transition-delay: 320ms; }
.reveal.visible > *:nth-child(6) { transition-delay: 400ms; }
/* Enfants aussi en reveal individuel */
.reveal > * { opacity: 0; transform: translateY(18px); transition: opacity .5s cubic-bezier(.16,1,.3,1), transform .5s cubic-bezier(.16,1,.3,1); }
.reveal.visible > * { opacity: 1; transform: translateY(0); }
```

```js
const revealObs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); revealObs.unobserve(e.target); } });
}, { threshold: 0.15 });
document.querySelectorAll('.reveal').forEach(el => revealObs.observe(el));
```

##### Counter Animations (KPIs hero, chiffres cles)

Chiffres qui comptent de 0 a la valeur cible avec easeOutExpo (deceleration progressive, plus impactant).

```html
<span class="counter" data-count="13036">0</span>
<span class="counter" data-count="9596" data-prefix="€" data-suffix="">0</span>
```

```js
function easeOutExpo(t) { return t === 1 ? 1 : 1 - Math.pow(2, -10 * t); }

function animateCounter(el) {
  const target = parseInt(el.dataset.count);
  const prefix = el.dataset.prefix || '';
  const suffix = el.dataset.suffix || '';
  const duration = 1800;
  const start = performance.now();
  function tick(now) {
    const t = Math.min((now - start) / duration, 1);
    el.textContent = prefix + Math.round(easeOutExpo(t) * target).toLocaleString('fr-FR') + suffix;
    if (t < 1) requestAnimationFrame(tick);
  }
  requestAnimationFrame(tick);
}

const counterObs = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { animateCounter(e.target); counterObs.unobserve(e.target); } });
}, { threshold: 0.3 });
document.querySelectorAll('.counter').forEach(el => counterObs.observe(el));
```

##### Lazy Chart Rendering (Chart.js)

Les charts ne sont crees qu'a l'entree dans le viewport — ameliore la performance et produit un effet d'apparition.

```js
const chartDefs = {
  'myChart': () => new Chart(document.getElementById('myChart'), { /* config */ }),
};
const chartInstances = {};

const chartObs = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const id = e.target.id;
      if (chartDefs[id] && !chartInstances[id]) chartInstances[id] = chartDefs[id]();
      chartObs.unobserve(e.target);
    }
  });
}, { threshold: 0.2 });
document.querySelectorAll('canvas[id]').forEach(c => chartObs.observe(c));
```

**Animations Chart.js par type** :

```js
// Doughnut — rotation + scale
animation: { animateRotate: true, animateScale: true, duration: 1200, easing: 'easeOutQuart' }

// Bar chart — cascade (chaque barre avec delay)
animation: { duration: 900, easing: 'easeOutQuart', delay: (ctx) => ctx.dataIndex * 60 }

// Line chart — trace progressif
animation: { x: { duration: 1400, easing: 'easeOutQuart' }, y: { duration: 800, easing: 'easeOutQuart', delay: 300 } }

// Horizontal bar (geo / classements) — cascade lente
animation: { duration: 1200, easing: 'easeOutQuart', delay: (ctx) => ctx.dataIndex * 40 }
```

##### Hover KPI Cards

```css
.kpi-card {
  transition: border-color .25s ease, box-shadow .25s ease;
}
.kpi-card:hover {
  border-color: var(--rose);
  box-shadow: 0 0 20px rgba(232,25,124,.08);
}
```

#### Responsive Breakpoints

Utiliser `clamp()` pour un sizing fluide et `auto-fit + minmax` pour des grids adaptatifs.

**Principes clamp()** :
```css
font-size: clamp(1.6rem, 4vw, 2.8rem);   /* Titres hero */
font-size: clamp(22px, 2.4vw, 30px);      /* KPI values */
font-size: clamp(26px, 3.4vw, 42px);      /* Hero stat values */
font-size: clamp(13px, 1.5vw, 16px);      /* Hero sous-titre */
font-size: clamp(9px, 1.1vw, 11px);       /* Hero stat labels */
font-size: clamp(20px, 2.8vw, 28px);      /* Funnel values */
padding: clamp(24px, 4vw, 48px) clamp(16px, 3vw, 32px);  /* Sections */
```

**Takeaways** :
- Titre : 13px bold var(--blanc)
- Texte : 14px, line-height 1.85, couleur var(--text)

**Footer** :
- Gauche : 11px, var(--text2)
- Droite : 12px, var(--text2)

**Grids adaptatifs** :
```css
.kpi-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 16px; }
.chart-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 20px; }
```

| Breakpoint | Adaptations |
|---|---|
| <= 1400px | KPIs 3 col, grilles c4 -> 2 col |
| <= 1200px | Sidebar reduite (28px, texte masque, logo seul) |
| <= 1100px | Grilles -> 1 col, c3 -> 2 col, jauges min 220px |
| <= 900px | Header vertical, main padding reduit, KPIs 2 col, tables 10px. Sidebar masquee. Funnel vertical. |
| <= 600px | KPIs 2 col serrees, header logo 32px, sections 10px, jauges 1 col. Doughnuts max-width 260px centres. |
| <= 380px | KPIs 1 col, font-size base reduit, padding minimal |

**Layout main centré** :
```css
main {
  margin-left: 32px;       /* decalage sidebar */
  margin-right: auto;
  max-width: 1400px;
  padding: 0 clamp(16px, 4vw, 48px) 80px;
}
/* Centrer quand l'ecran depasse max-width + sidebar */
@media (min-width: 1480px) {
  main { margin-left: auto; margin-right: auto; padding: 0 clamp(32px, 4vw, 64px) 80px; }
}
```

**Sidebar responsive** :
```css
@media (max-width:1200px) { .sidebar { width: 28px; } .sidebar span { display: none; } }
@media (max-width:900px) { .sidebar { display: none; } .main { margin-left: 0; } }
```

**Funnel responsive** :
```css
@media (max-width:900px) {
  .funnel { flex-direction: column; align-items: stretch; }
  .funnel-step { min-width: auto; }
  .funnel-arrow { transform: rotate(90deg); margin: 8px auto; }
}
```

---

## Regles par type de document

### Word (.docx)
- H1 Bleu VR 24pt / H2 18pt / H3 14pt, corps Montserrat 10pt Gris VR
- En-tete : logo seul, pas de ligne ni bandeau
- Objet : Bleu VR gras

### PowerPoint (.pptx) — Gestion des templates

**REGLE OBLIGATOIRE** : Avant toute creation de presentation, demander :
> Quel template souhaites-tu utiliser ? VR White, VR Dark ou 52ent 2026 ?

Si game report / rapport audience / bilan evenement -> proposer VR White par defaut.

#### Template : VR White
Usage : Game reports, rapports audience, bilans evenement, presentations partenaires externes
Fichier reference : Rapport_Vendee_Globe_2025.pptx

Palette VR White :
- Blanc #FFFFFF — fond dominant
- Noir #000000 — texte principal
- Rose VR White #D12E77 — accent principal, titres, highlights
- Gris texte #6B6B6E / #53585F — texte secondaire
- Bleu-vert #005A6F — accent secondaire (graphiques, legendes)
- Gris clair #D9D9D9 — bordures, separateurs

Police : Montserrat Regular (fallback Helvetica) | Format : 16:9

Layouts disponibles :
- Header Race + Text — slide de couverture (photo race + titre)
- Laptop 2 — slide contenu standard (image + texte + KPIs)
- Numbers — slide chiffres cles (grands nombres en Rose VR White)
- Graph Leg — slide graphiques avec legendes (inclut #005A6F)
- pie chart — slide graphique circulaire
- Title and Content — slide cloture / contact
- Vierge — slide libre (resultats financiers, tableaux custom)

Structure type game report (11 slides) :
1. Couverture — Header Race + Text
2. La Communication — Laptop 2 (campagnes, RS, emailing)
3. Impact Media — Laptop 2 (portee, earned media value)
4. Le Jeu en chiffres — Numbers (KPIs joueurs, dispo, finishers)
5-6. Graphiques performance — Graph Leg
7. Repartition plateformes — pie chart (iOS/Android/Web)
8. Resultats financiers — Vierge
9. Contenu editorial — Laptop 2
10. Resultats financiers detailles — Vierge
11. Cloture — Title and Content (contact, mentions legales)

Ton : Factuel, oriente donnees, sobre. Mention CONFIDENTIEL en pied de page.

#### Template : VR Dark
Usage : Presentations commerciales partenaires, pitch partnerships, presentations generales Virtual Regatta
Fichier reference : Template_Presentation_VR_2025.pptx (base) + VR-Global_Presentation_v2.pdf (rendu final)

Palette VR Dark (VR commercial) :
- Noir #000000 — fond dominant (toutes les slides)
- Blanc #FFFFFF — texte principal, logo, titres ligne 1
- Rose accent #E8197C — titres ligne 2, CTA buttons, blocs highlight, icones check
- Bleu acier #156082 — accent secondaire structure (herite template 52ent)
- Gris fonce #333333 / #3A3A3A — cartes KPI, fond blocs stats
- Gris sidebar #1C1C1C — barre laterale gauche

Police : Arial (template de base) | Format : 16:9 widescreen

Identite visuelle specifique :
- Barre laterale gauche : fine barre verticale avec texte (c) VIRTUAL REGATTA CONFIDENTIAL en rotation -90 degres
- Logo VR : version BLANCHE uniquement, coin haut gauche
- Structure titre : Ligne 1 en blanc gras + Ligne 2 en rose (ex: The eSailing / Leading Platforms)
- CTA button : fond rose #E8197C, texte blanc gras, style pill/rectangle arrondi (ex: PLAY NOW)

Layouts / types de slides :
- Cover plein ecran : photo race full-bleed, logo VR blanc centre, tagline + sous-titre blancs
- Content + visuels : titre gauche (blanc/rose), image droite (mockups phones/laptops)
- Stats & chiffres : grands chiffres blancs, label gris clair, fond noir
- KPI cards : cartes grises foncees, grand nombre blanc, label sous-titre gris clair, icone rose optionnelle
- Partenaires logos : grille logos sur fond noir, blanc pour les logos, couleurs natives conservees
- Mosaic / collage : grille photos + blocs rose plein avec texte blanc gras
- Two-column : texte argumentaire gauche + liste a puces gris clair, visuel droite
- Closing : fond noir, logo VR blanc centre, logos produits (VRO + VRI), bouton PLAY NOW rose

Structure type presentation commerciale VR (17 slides observees) :
1. Cover — photo race + logo + We Make Sailing Easy
2. Les plateformes eSailing — produits VRI et VRO
3-4-5. Experience produit — slides Offshore / eSailing (mockup laptop)
6. Partenariats internationaux — grille logos evenements
7. Worldwide Community — carte monde + KPI stats
8. Engagement — mosaic photos + bloc rose Extreme Engagement
9. Storytelling / Adventures — grille photo + blocs rose
10. Profil joueurs — graphiques doughnut sur fond noir
11. Email / CRM — KPI cards sur fond noir
12-13. Brand integration — playground visuel + carte
14. Turn your company into a Crew — 3 colonnes
15. Case study — chiffres cles (ex: IMOCA Virtual Series)
16. Closing — logo VR + produits + PLAY NOW

Ton : Inspire, premium, impactant. Phrases courtes. Chiffres mis en avant. Anglais.
Confidentialite : Mention (c) Virtual Regatta Confidential en sidebar gauche + footer.

#### Template : 52ent 2026
Usage : Reportings internes 52 Entertainment - Direction, COMEX, Finance, board. Presentations institutionnelles groupe.
Fichier reference : 52E_2026_Template.pptx

Palette 52ent 2026 :
- Bleu nuit #0D3559 - structurant dominant (fonds, titres, encadres)
- Bleu nuit fonce #112C48 - fonds secondaires, blocs KPI
- Or sable #DABA94 - accent principal, highlights, separateurs
- Gris clair #D9E1E8 / #E8E8E8 - fonds slides contenu
- Vert menthe #92E3A9 - donnees positives, indicateurs de performance
- Ardoise #263238 - texte secondaire, labels graphiques
- Blanc #FFFFFF - texte sur fonds sombres
- Rose alerte #FF1A6A - usage ponctuel uniquement (alertes)

Police : Poppins Light (titres) + Aptos (corps) - fallback Arial | Format : 16:9

Identite visuelle :
- Fond dominant bleu nuit #0D3559 - different du VR Dark (noir pur)
- Accent or/sable #DABA94 (vs rose vif dans les deux autres templates)
- Break slides : fond #0D3559 plein, titre or centre, sobre - pas de photos
- Graphiques : palette bleu / vert menthe / or - pas de rose
- KPI cards : fond #112C48, grand chiffre blanc, label or
- Ton entierement neutre et structure - pas de CTA ni visuels lifestyle

Layouts disponibles (92 slides dans le template) :
- Cover : fond bleu nuit, titre blanc/or, periode et date
- Break slide : separateur de section, fond #0D3559, texte or centre
- Content standard : fond gris clair, titre bleu nuit, corps ardoise
- Two-column : texte argumentaire + tableau ou visuel
- KPI cards : grands chiffres blancs sur fond #112C48
- Graphiques : barres, courbes, secteurs - palette bleu/vert/or
- Tableau de donnees : en-tetes #0D3559 texte blanc, lignes alternees blanc/#D9E1E8
- Infographie : icones + chiffres sur fond blanc ou bleu nuit
- Timeline / Roadmap : elements lineaires sur fond clair
- Closing : fond bleu nuit, titre or

Structure type reporting 52E :
1. Cover - titre reporting, periode, date
2. Sommaire - break slide + liste des sections
3-N. Sections thematiques separees par break slides :
   - Financier : P&L, revenus, couts, EBITDA
   - KPIs produit : DAU, MAU, revenus par ligne metier
   - Operationnel : avancement projets, roadmap, risques
   - Conclusion / Next steps
Dernier slide : Closing sobre

Ton : Factuel, neutre, structure. Chiffres precis. Francais obligatoire.
Confidentialite : Document interne 52 Entertainment - ne pas diffuser.

### Excel (.xlsx)
- **Police** : Arial 10pt (fallback Montserrat)
- **En-tetes de colonnes (row 1)** : fond Bleu VR (#00425c), texte blanc, gras, centre
- **Lignes de donnees** : alternance blanc (#ffffff) / Bleu VR clair (#e6f0f4)
- **Texte cellules** : Gris VR (#58585b), alignement gauche par defaut
- **Donnees numeriques / KPIs cles** : Rose VR (#dc006b), gras
- **Bordures** : fines #cccccc — pas de bordures epaisses
- **Onglets** : nommer explicitement, fond Bleu VR si possible
- **Ligne de totaux** : fond Bleu VR (#00425c), texte blanc, gras
- **Quadrillage natif** : desactiver — ws.sheet_view.showGridLines = False
- **Largeur colonnes** : auto-fit au contenu

Reference openpyxl :
```python
from openpyxl import Workbook
from openpyxl.styles import PatternFill, Font, Alignment, Border, Side
from openpyxl.utils import get_column_letter

BLEU_VR    = "00425c"
ROSE_VR    = "dc006b"
GRIS_VR    = "58585b"
BLEU_CLAIR = "e6f0f4"
BLANC      = "ffffff"
BORDURE    = "cccccc"

wb = Workbook()
ws = wb.active
ws.title = "Donnees"
ws.sheet_view.showGridLines = False

header_fill  = PatternFill("solid", fgColor=BLEU_VR)
header_font  = Font(name="Arial", size=10, bold=True, color=BLANC)
header_align = Alignment(horizontal="center", vertical="center")
fill_pair    = PatternFill("solid", fgColor=BLEU_CLAIR)
fill_impair  = PatternFill("solid", fgColor=BLANC)
cell_font    = Font(name="Arial", size=10, color=GRIS_VR)
kpi_font     = Font(name="Arial", size=10, bold=True, color=ROSE_VR)
total_fill   = PatternFill("solid", fgColor=BLEU_VR)
total_font   = Font(name="Arial", size=10, bold=True, color=BLANC)

thin_border = Border(
    left=Side(style="thin", color=BORDURE),
    right=Side(style="thin", color=BORDURE),
    top=Side(style="thin", color=BORDURE),
    bottom=Side(style="thin", color=BORDURE),
)

# En-tete row 1
headers = ["Colonne 1", "Colonne 2", "Colonne 3"]
for col, h in enumerate(headers, start=1):
    cell = ws.cell(row=1, column=col, value=h)
    cell.fill = header_fill
    cell.font = header_font
    cell.alignment = header_align
    cell.border = thin_border

# Lignes de donnees
data = [["Valeur A", "Description A", 1200], ["Valeur B", "Description B", 3400]]
for row_idx, row_data in enumerate(data, start=2):
    fill = fill_pair if row_idx % 2 == 0 else fill_impair
    for col_idx, value in enumerate(row_data, start=1):
        cell = ws.cell(row=row_idx, column=col_idx, value=value)
        cell.fill = fill
        cell.font = cell_font
        cell.border = thin_border

# Auto-fit colonnes
for col in ws.columns:
    max_len = max(len(str(c.value)) for c in col if c.value)
    ws.column_dimensions[get_column_letter(col[0].column)].width = max_len + 4

wb.save("output.xlsx")
```

### PDF (ReportLab)
- Voir reference code ci-dessus
- Logo en haut gauche, pied de page sobre sans ligne

---

## A faire systematiquement

1. Lire ce fichier avant toute creation de document VR
2. Utiliser le logo Virtual Regatta PNG dans l'en-tete
3. Objet en Bleu VR (pas Rose VR)
4. Pas de ligne separatrice dans en-tete / pied de page
5. Signature : Nom (Bleu VR) + Titre (Gris VR) uniquement
6. Excel : desactiver le quadrillage natif, appliquer bordures fines manuellement
7. HTML Dark/Light : toujours utiliser les CSS variables (`var(--x)`), jamais de couleurs en dur hors du `:root` et `body.light`
8. Chart.js : axes et grid en `var(--border)`, ticks en `var(--text2)`, legendes en `var(--text)` — lire via `getComputedStyle` au moment de la creation
9. Canvas : ne JAMAIS utiliser `roundRect` — utiliser `quadraticCurveTo`
10. Objet C en JS : ne contient PAS `text` ni `text2` — utiliser '#ddd'/'#888' en dur
11. HTML : toujours utiliser les animations scroll reveal + counter sur les KPIs et sections
12. Chart.js : toujours utiliser le lazy rendering via IntersectionObserver + animations par type
13. Responsive : toujours utiliser clamp() + auto-fit grids, jamais de tailles fixes
14. Toggle theme : `rebuildCharts()` obligatoire apres changement dark/light (Chart.js ne reagit pas aux CSS variables)
15. Toggle i18n : utiliser `data-i18n`, `data-i18n-html`, `data-i18n-tip` — fonction `T(key)` pour acceder aux traductions
16. Isobathes : fond bathymetrique via `body::before` — ne JAMAIS mettre `position: relative` sur les toggles ou la sidebar (casse leur `position: fixed`)
17. Titres de sections : 36px weight 800 uppercase, letter-spacing 3px, avec icone 32px
