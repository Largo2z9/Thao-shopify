# THAO — Shopify Store

## Projet
One-pager e-commerce grip socks premium femmes (pilates/barre/yoga). Marché France.
Store : `thao-237199.myshopify.com`

## Stack
- Shopify (Dawn theme fork)
- Liquid + HTML/CSS/JS vanilla
- GitHub sync vers Shopify

## Design System

### Couleurs
- Background principal : `#EFEAE4` (beige)
- Background secondaire : `#FFFFFF` (cards, modals)
- Accent doux : `#FFD9D9` (rose — badges, bundle, hover)
- CTA / headings : `#4D0011` (burgundy)
- Texte body : `#1A1A1A` (pas noir pur)
- Texte secondaire : `#6B6560` (captions, labels)
- Borders : `#E0DBD5` (séparateurs, inputs)
- **Règle : monochrome chaud uniquement. Jamais de rouge promo, vert, bleu.**

### Typographies (self-hosted .woff2)
- Headings : **Plus Jakarta Sans Bold** (700) + ExtraBold (800) pour H1
- Body/UI : **Fustat** (400, 500, 600)
- Line-height : Headings 1.1 · Body 1.6 · UI 1.4
- Letter-spacing : Headings -0.02em · UI/Captions 0.04em

### Composants
- Border radius boutons : 8px
- Border radius cards : 12px
- CTA principal : bg `#4D0011`, texte blanc, padding 16px 32px, uppercase, Fustat 600
- CTA secondaire : border 1.5px `#4D0011`, texte `#4D0011`, bg transparent
- Badge : bg `#FFD9D9`, texte `#4D0011`, pill 20px radius
- Accordéon : border-bottom `#E0DBD5`, icône +/−, 300ms ease
- Swatch couleur : 36px cercle, border `#4D0011` si sélectionné
- Swatch taille : pill, border `#E0DBD5`, bg `#4D0011` + texte blanc si sélectionné

### Layout
- Container : max-width 1200px
- Padding horizontal : 48px desktop / 20px mobile
- Section padding vertical : 100px desktop / 64px mobile
- Grid gap : 24px (desktop) / 16px (mobile)
- Spacing scale (8px) : 4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 80 · 100 · 120
- Mobile-first : media queries min-width

### Animations
- Fade-in scroll : opacity 0→1, translateY 20px→0, 600ms ease-out
- Hover boutons : opacity 200ms
- Hover images : scale(1.02), 400ms ease
- Cart drawer : translateX 300ms ease
- Marquee : scroll horizontal 30s linear infinite

## Ton de voix
- Premium, chaleureux, féminin sans infantiliser
- Français uniquement (naming produits et collections en FR)
- Phrases courtes et directes
- Pas de majuscules agressives
- Le visuel fait le travail (70% image / 30% copy)

## Structure One-Pager
1. Header sticky (logo centré + panier)
2. Hero (image lifestyle plein écran + headline + CTA)
3. Produit (galerie sticky + sélecteurs + ATC)
4. Bundle (fond rose + paliers visuels + progress bar)
5. Social proof marquee (fond burgundy)
6. Lifestyle / UGC (grille photos)
7. Réassurance (4 icônes)
8. FAQ (5 accordéons)
9. CTA final (image + bouton)
10. Footer (fond burgundy)

## Overlays
- Cart drawer (slide-in droite + progress livraison + upsell)
- Newsletter popup (exit-intent, "avant-premières", pas de discount)
- Guide des tailles (modal)

## Prix
- Unitaire : 19,90 €
- Bundles : 2+ → 20% / 4+ → 27% / 6+ → 33% / 8+ → 45%
- Livraison offerte ≥ 40€

## Conventions
- Fichiers Liquid : snake_case (`section-hero.liquid`)
- CSS : custom properties dans `base.css`
- JS : vanilla ES6+, defer, pas de jQuery
- Images : WebP, lazy load (sauf hero), max 200ko
- Commits : anglais, concis (feat:, fix:, style:)

## Référence
- PRD complet : `PRD.md`
- Logo SVG : `assets/logo-thao-black.svg` (+ white, burgundy variants)
- Fonts : `assets/plus-jakarta-sans-*.woff2` + `assets/fustat-*.woff2`
