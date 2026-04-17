# Design System — Handicap International Belgique

> Source : brandbook fédéral HI/Humanité & Inclusion (2017), page logo hi.org, charte graphique HI Belgique (2009).
> À utiliser comme référence pour tout développement de landing page, email ou composant web pour ce client.

---

## Couleurs

### Palette principale

```css
:root {
  /* Couleur signature */
  --hi-blue:       #0077c8;  /* Pantone 3005 — CMJN 100/31/0/0 — RGB 0/119/200 */
  --hi-blue-dark:  #005a9e;  /* Variante sombre, hover, liens */
  --hi-blue-light: #e6f3fb;  /* Fonds, encadrés, zones info */

  /* Neutres */
  --hi-white:      #ffffff;
  --hi-gray-light: #f5f5f5;  /* Arrière-plans secondaires */
  --hi-gray-text:  #333333;  /* Corps de texte */
  --hi-black:      #1a1a1a;  /* Logo N&B, texte fort */
}
```

### Règles d'usage couleurs

- Le bleu `#0077c8` est la seule couleur de marque officielle
- Pas de palette secondaire étendue dans les chartes publiées
- Blanc + bleu + noir constituent l'essentiel du système visuel
- Si des couleurs complémentaires sont utilisées sur le site BE (orange, vert...), les confirmer directement avec l'équipe com HI Belgique

---

## Logo

| Contexte | Version à utiliser |
|---|---|
| Fond blanc | Logo bleu `#0077c8` |
| Fond bleu | Logo blanc en réserve |
| Fond sombre (N&B) | Logo blanc (ou 60% noir autorisé) |
| Fond clair (N&B) | Logo noir 100% |

- Format web : PNG (fond transparent)
- Format print : EPS vectorisé
- Taille minimale web : 40px de large (version optimisée), 85px (version principale)
- Taille minimale print : 25mm
- Aucune déformation, rotation, contour, ombre ou modification de couleur autorisée

---

## Typographie

### Police principale : Nunito

Google Fonts (libre) — import :

```html
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&display=swap" rel="stylesheet">
```

Ou via CSS :

```css
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&display=swap');
```

### Hiérarchie typographique

```css
/* H1 — Titre principal */
h1 {
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: clamp(24px, 4vw, 32px);
  line-height: 1.2;
  color: var(--hi-black);
}

/* H2 — Sous-titre de section */
h2 {
  font-family: 'Nunito', sans-serif;
  font-weight: 600;
  font-size: clamp(18px, 2.5vw, 22px);
  line-height: 1.3;
  color: var(--hi-black);
}

/* H3 — Titre de bloc */
h3 {
  font-family: 'Nunito', sans-serif;
  font-weight: 600;
  font-size: 17px;
  line-height: 1.4;
  color: var(--hi-black);
}

/* Corps de texte */
p, li {
  font-family: 'Nunito', sans-serif;
  font-weight: 400;
  font-size: 15px;
  line-height: 1.65;
  color: var(--hi-gray-text);
}

/* Légende, mention, note */
.caption, small {
  font-family: 'Nunito', sans-serif;
  font-weight: 400;
  font-size: 12px;
  line-height: 1.5;
  color: #666666;
}
```

### Grammages disponibles

| Grammage | Usage |
|---|---|
| 400 Regular | Corps de texte, légendes |
| 600 SemiBold | Sous-titres, labels, nav |
| 700 Bold | Titres, CTAs, chiffres clés |

---

## Composants de base (CSS)

### Bouton principal

```css
.btn-hi-primary {
  background-color: var(--hi-blue);
  color: #ffffff;
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: 15px;
  padding: 12px 24px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  transition: background-color 0.2s ease;
}

.btn-hi-primary:hover {
  background-color: var(--hi-blue-dark);
}
```

### Bouton secondaire (outline)

```css
.btn-hi-secondary {
  background-color: transparent;
  color: var(--hi-blue);
  font-family: 'Nunito', sans-serif;
  font-weight: 700;
  font-size: 15px;
  padding: 12px 24px;
  border: 2px solid var(--hi-blue);
  border-radius: 4px;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  transition: all 0.2s ease;
}

.btn-hi-secondary:hover {
  background-color: var(--hi-blue);
  color: #ffffff;
}
```

### Lien texte

```css
a {
  color: var(--hi-blue);
  text-decoration: underline;
}

a:hover {
  color: var(--hi-blue-dark);
}
```

---

## Notes pour Claude Code

- Nunito est la police unique sur tous les supports (pas de police secondaire documentée)
- Le bleu `#0077c8` est non négociable pour les éléments de marque (logo, CTAs, liens)
- Système sobre : éviter d'introduire des couleurs non validées par HI Belgique
- Pour les emails HTML : utiliser des couleurs en valeurs hexadécimales directes (pas de variables CSS), Nunito en fallback `sans-serif`
- Si des couleurs complémentaires sont visibles sur le site live (ex. orange sur certains blocs), les prélever via l'inspecteur et les ajouter ici
