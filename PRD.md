# THAO — Product Requirements Document

> One-pager e-commerce · Grip socks pilates · Marché France
> Version 2.0 · Mars 2026

---

## 1. Vision produit

THAO vend des grip socks premium pour femmes pratiquant le pilates, la barre et le yoga en France. Le site est un one-pager conçu comme une page de vente unique : le trafic payant (Meta Ads) atterrit dessus, scroll, achète.

**Ce qu'on est :** Une marque premium, féminine, minimaliste. L'équivalent français d'Elliosa avec l'exigence esthétique d'une maison de luxe.

**Ce qu'on n'est pas :** Technique, sportif, agressif, discount, coloré. Pas de majuscules hurlantes, pas de rouge promo, pas de compte à rebours.

**Référence esthétique :** TALA × Aesop × Byredo. Beaucoup d'espace, peu de mots, chaque élément respire.

**Le visuel est le produit.** Ratio 70% image / 30% copy. Sur cette niche, personne n'achète parce qu'elle a lu un argumentaire — elle achète parce qu'elle a vu un truc cute au studio. Le site est un container pour du contenu visuel aspirationnel.

**Naming : français uniquement.** Noms de collections et de produits en FR (ex: "Latte", "Pivoine", "Nuage").

---

## 2. Design System

### 2.1 Palette

| Rôle | Hex | Usage |
|---|---|---|
| Background principal | `#EFEAE4` | Body, sections alternées |
| Background secondaire | `#FFFFFF` | Cards, cart drawer, modals |
| Accent doux | `#FFD9D9` | Badges, bundle highlight, hover states |
| CTA / Headings | `#4D0011` | Boutons, titres, liens actifs |
| Texte body | `#1A1A1A` | Paragraphes (pas noir pur — plus doux) |
| Texte secondaire | `#6B6560` | Captions, labels, meta |
| Borders | `#E0DBD5` | Séparateurs, inputs, accordéons |

**Règle :** Pas d'autres couleurs. Jamais de rouge promo, jamais de vert succès flashy, jamais de bleu. Le site est monochrome chaud.

### 2.2 Typographies (self-hosted .woff2)

| Usage | Font | Weight | Taille desktop | Taille mobile |
|---|---|---|---|---|
| H1 (hero) | Plus Jakarta Sans | 800 | 56px | 36px |
| H2 (sections) | Plus Jakarta Sans | 700 | 40px | 28px |
| H3 (sous-titres) | Plus Jakarta Sans | 700 | 24px | 20px |
| Body | Fustat | 400 | 16px | 15px |
| Body medium | Fustat | 500 | 16px | 15px |
| UI (boutons, labels) | Fustat | 600 | 14px | 14px |
| Captions | Fustat | 400 | 13px | 12px |

**Line-height :** Headings 1.1 · Body 1.6 · UI 1.4
**Letter-spacing :** Headings -0.02em · Body 0 · UI/Captions 0.04em (légèrement aéré)

### 2.3 Composants

**Bouton primaire (CTA)**
- Background : `#4D0011`
- Texte : `#FFFFFF`
- Padding : 16px 32px
- Border-radius : 8px
- Font : Fustat 600, 14px, letter-spacing 0.04em, uppercase
- Hover : opacity 0.9, transition 200ms ease
- Min-height : 52px (touch target)

**Bouton secondaire**
- Background : transparent
- Border : 1.5px solid `#4D0011`
- Texte : `#4D0011`
- Même padding/radius/font que primaire
- Hover : background `#4D0011`, texte blanc

**Badge**
- Background : `#FFD9D9`
- Texte : `#4D0011`
- Padding : 6px 12px
- Border-radius : 20px (pill)
- Font : Fustat 600, 12px, uppercase

**Accordéon**
- Border-bottom : 1px solid `#E0DBD5`
- Padding : 20px 0
- Icône : + / − en Fustat 400, 20px
- Animation : max-height transition 300ms ease

**Input / Sélecteur**
- Border : 1.5px solid `#E0DBD5`
- Border-radius : 8px
- Padding : 14px 16px
- Focus : border-color `#4D0011`
- Font : Fustat 400, 15px

**Swatch couleur**
- Cercle 36px × 36px
- Border : 2px solid transparent
- Sélectionné : border `#4D0011`
- Hover : scale(1.08), transition 150ms

**Swatch taille**
- Pill : padding 10px 20px
- Border : 1.5px solid `#E0DBD5`
- Sélectionné : background `#4D0011`, texte blanc
- Font : Fustat 500, 14px

### 2.4 Layout

| Propriété | Desktop | Mobile |
|---|---|---|
| Container max-width | 1200px | 100% |
| Padding horizontal | 48px | 20px |
| Section padding vertical | 100px | 64px |
| Grid gap | 24px | 16px |
| Card border-radius | 12px | 12px |

### 2.5 Spacing scale

Basé sur un système de 8px :
`4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 80 · 100 · 120`

### 2.6 Animations

Tout est subtil. Rien ne bounce, rien ne flash.

- **Fade-in au scroll** : opacity 0→1, translateY 20px→0, duration 600ms, ease-out
- **Hover boutons** : opacity transition 200ms
- **Hover images** : scale(1.02), transition 400ms ease
- **Accordéons** : max-height + opacity, 300ms ease
- **Cart drawer** : translateX(100%→0), 300ms ease
- **Marquee ticker** : scroll horizontal continu, 30s linear infinite

---

## 3. Structure One-Pager

### 3.0 Header (sticky)

- Logo THAO™ centré (SVG, hauteur 24px)
- Icône panier à droite (badge count si items)
- Background : transparent → `#EFEAE4` au scroll (transition 200ms)
- Hauteur : 64px
- Z-index : 100
- Pas de : menu hamburger, barre de recherche, compte utilisateur (one-pager)

### 3.1 Hero

**Layout :** Image plein écran (100vh desktop, 85vh mobile)

- Image lifestyle : femme en position pilates, studio lumineux, grip socks visibles
- Overlay gradient subtil (bas → transparent)
- Headline H1 : une ligne, centrée, bas de l'image
- Sous-titre : une ligne, Fustat 400
- CTA primaire : "Découvrir"
- Image : object-fit cover, pas de lazy-load (LCP)
- Scroll indicator : chevron discret animé
- Mobile : image recadrée verticale (crop différent)

### 3.2 Produit

**Layout :** 2 colonnes desktop (55% galerie / 45% infos) · Stack mobile

**Galerie (gauche) :**
- 1 image principale + 5 thumbnails
- Lightbox zoom au clic
- Swipe mobile
- Format carré 1:1, WebP, max 200ko
- Desktop : galerie sticky pendant scroll infos

**Infos (droite) :**
1. Nom produit — H2 Santral Bold
2. ★★★★★ 4.9 (X avis) — ancre vers reviews
3. Prix 19,90 € — Fustat 600, 24px
4. Swatches couleur (cercles)
5. Sélecteur taille S/M · M/L + "Guide des tailles" (modal)
6. Quantité +/−
7. **"Ajouter au panier"** — bouton primaire full-width → ouvre cart drawer
8. Apple Pay · Google Pay · Shop Pay (icônes 32px)
9. 4 icônes bénéfices (grille 2×2) :
   - Grip silicone antidérapant
   - Coton premium respirant
   - Design français exclusif
   - Taille universelle
10. "Livraison offerte dès 40€ · Retours sous 30 jours"

### 3.3 Bundle

**Layout :** Fond `#FFD9D9` · centré · padding généreux

1. Badge pill : "Économisez jusqu'à 45%"
2. H2 : "Composez votre pack"
3. Sous-titre explicatif (une ligne)
4. **Sélecteur palier** — 4 options visuelles :
   - 2 paires → −20% (31,84 €)
   - 4 paires → −27% (58,11 €)
   - 6 paires → −33% (79,99 €)
   - 8 paires → −45% (87,56 €)
5. Économie en € sous chaque palier
6. Progress bar fine + "Plus que X paire(s) pour débloquer −Y%"
7. CTA primaire

### 3.4 Social Proof (Marquee)

**Layout :** Bande horizontale, fond `#4D0011`, texte blanc

- Scroll continu : "★★★★★ 4.9/5" · "Livraison offerte dès 40€" · "Retours 30 jours" · "Coton premium" · "Made for pilates"
- Au lancement : USP en boucle. Post-lancement : ajouter "X+ pratiquantes" + extraits avis
- Hauteur : 48px
- Font : Fustat 600, 13px, uppercase, letter-spacing 0.08em
- Animation : translateX 30s linear infinite, pause au hover

### 3.5 Lifestyle / UGC

**Layout :** Grille 3 colonnes, fond `#EFEAE4`

- 6-9 photos UGC (contenu gifting influenceuses)
- Mix : studio pilates, reformer, lifestyle, flat lay
- Pas de texte sur les images
- "@thao" en caption discrète
- Au lancement : photos lifestyle placeholder, remplacées par UGC dès les gifting
- Images : border-radius 12px, gap 8px
- Hover : scale(1.02) + overlay semi-transparent

### 3.6 Réassurance

**Layout :** 4 colonnes desktop · 2×2 mobile · centré

1. Livraison offerte · Dès 40€ d'achat
2. Retours gratuits · Sous 30 jours
3. Coton premium · Doux et respirant
4. Design exclusif · Créé en France

- Icônes SVG custom, stroke, 32px, `#4D0011`
- Titre : Fustat 600, 14px
- Sous-titre : Fustat 400, 13px, `#6B6560`
- Pas de background card

### 3.7 FAQ

**Layout :** Container max-width 720px, centré

- H2 : "Questions fréquentes"
- 5 accordéons :
  1. Quelle taille choisir ?
  2. Combien coûte la livraison ?
  3. Comment entretenir mes grip socks ?
  4. Quel est le délai de livraison ?
  5. Puis-je retourner ma commande ?
- Premier accordéon ouvert par défaut
- Icône +/− animée (rotation 45deg)

### 3.8 CTA Final

- Image de fond + overlay `#4D0011` à 60%
- H2 court, aspirationnel, texte blanc
- CTA primaire blanc : "Trouver ma paire" → scroll smooth vers #produit
- Hauteur : 50vh desktop, 60vh mobile

### 3.9 Footer

**Fond `#4D0011` · texte blanc · minimaliste**

- Logo THAO™ version blanche
- 2 colonnes : (Notre histoire · FAQ · Contact) + (CGV · Confidentialité · Mentions légales)
- Instagram · TikTok (24px, blanc)
- Visa · Mastercard · Apple Pay · Shop Pay (icônes grises)
- "© 2026 THAO™ — Tous droits réservés"
- Padding 64px vertical
- Liens : Fustat 400, 14px, opacity 0.7 → 1 au hover

---

## 4. Overlays

### 4.1 Cart Drawer

**Trigger :** Icône panier OU "Ajouter au panier"
**Layout :** Panel droit 420px desktop / 100% mobile

1. "Votre panier" + fermer (×)
2. Progress bar livraison : "Plus que X,XX € pour la livraison offerte"
3. Liste produits (thumbnail 80px + nom + couleur + taille + quantité + prix + supprimer)
4. **Upsell slider** : "Complétez votre sélection" — 3-4 autres coloris
5. Sous-total
6. **"Commander"** — bouton primaire full-width
7. Paiements express
8. Fond blanc, overlay `#000` 40%, slide-in 300ms

### 4.2 Newsletter Popup

**Trigger :** Exit-intent desktop · 30s mobile · Max 1×/session

- "Accédez aux avant-premières et nouveautés"
- Input email + CTA "Rejoindre"
- "Non merci" discret
- Pas de discount en popup — protège le positionnement premium (pattern Skims/Alo)
- Modal centré 480px, border-radius 16px
- Intégration Klaviyo

### 4.3 Guide des tailles

- Tableau : Taille · Pointure EU · UK · US
- "En cas de doute, prenez S/M"
- Modal 560px

---

## 5. Catalogue

### 5.1 Produit principal
- **Type :** Grip socks pilates femme
- **Prix :** 19,90 €
- **Tailles :** S/M (35-39) · M/L (39-43)
- **Matière :** 85% coton, 12% polyester, 3% élasthanne
- **Grip :** Silicone antidérapant (semelle complète)

### 5.2 Coloris (3-5 au lancement)
Nommage FR lifestyle : "Latte", "Pivoine", "Nuage", etc.

### 5.3 Bundle pricing

| Paires | Remise | Prix total | Prix/paire | Économie |
|---|---|---|---|---|
| 1 | — | 19,90 € | 19,90 € | — |
| 2 | −20% | 31,84 € | 15,92 € | 7,96 € |
| 4 | −27% | 58,11 € | 14,53 € | 21,49 € |
| 6 | −33% | 79,99 € | 13,33 € | 39,41 € |
| 8 | −45% | 87,56 € | 10,95 € | 71,64 € |

### 5.4 Livraison
- Offerte dès 40€
- Standard : 3,90 € (< 40€)
- Délai : 3-5 jours ouvrés France

---

## 6. Tracking (AVANT le premier euro d'ads)

- **Meta Pixel** — Purchase, AddToCart, ViewContent, InitiateCheckout
- **GA4** — événements e-commerce
- **Shopify Analytics** — natif
- **Klaviyo** — email capture + flows

### Flows email :
1. Welcome : bienvenue + code −10%
2. Abandoned cart : 3 emails (1h / 24h / 72h)
3. Post-purchase : remerciement + demande avis (J+7)

---

## 7. Performance

| Métrique | Cible |
|---|---|
| LCP | < 2,5s |
| CLS | < 0,1 |
| FID | < 100ms |
| Images | WebP, lazy-load (sauf hero), max 200ko |
| Fonts | Self-hosted .woff2, font-display: swap |
| JS | Vanilla uniquement, defer, pas de jQuery |
| CSS | Custom properties, pas de framework |

---

## 8. Conventions

- Fichiers Liquid : snake_case (`section-hero.liquid`)
- CSS : custom properties dans `base.css`
- JS : vanilla ES6+, defer
- Images : WebP, `thao-[section]-[description].webp`
- Commits : anglais, concis (feat:, fix:, style:)
- Mobile-first : media queries min-width

---

## 9. Pages secondaires (liens footer)

Templates Liquid standards, pas sections du one-pager.

- **Notre histoire** — hero + 2-3 paragraphes fondateur + valeurs
- **Contact** — formulaire simple
- **CGV / Confidentialité / Mentions légales** — templates texte

---

## 10. Hors scope (MVP)

- Compte client / login
- Wishlist
- Blog
- Multi-langue
- Programme de fidélité
- Wholesale / B2B
- Bundle builder interactif (v1 = paliers simples)
- Page collection séparée (one-pager)
- Reviews au lancement (Judge.me prêt, pas de contenu)

---

## 11. Inputs requis avant build

- [ ] Photos produit (6 min par coloris, ou placeholders)
- [ ] Fichiers fonts Santral + Fustat (.woff2)
- [ ] Domaine final
- [ ] Logo SVG versions : noir, blanc, burgundy
