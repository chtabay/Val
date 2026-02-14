# Landing V6 — Spécification de structure et contraintes de design

## Philosophie

La V6 suit le modèle **StoryBrand** : le prospect est le héros, Valérie est le guide.
La page ne se présente pas — elle **parle au prospect de son problème** et l'accompagne
vers une prise de conscience progressive.

Séquence psychologique :

```
Douleur → Preuve → Valeur concrète → Déclic → Action
```

Pas de dashboard, pas de choix, pas de grille. Un **récit vertical unique** que le
prospect parcourt naturellement en scrollant, comme une conversation.

---

## Principes de design

### Ton et voix

- Valérie parle en **"je"** et s'adresse au prospect en **"vous"**
- Le ton est **direct, empathique, sans jargon** — comme un premier café
- Pas de formulations corporate ("DRH externalisée", "accompagnement structuré")
- Préférer les formulations concrètes et vivantes :
  - ❌ "Accompagnement en recrutement"
  - ✅ "Votre meilleur élément vient de démissionner. Et vous ne savez pas pourquoi."

### Densité et rythme

- **Maximum 2 écrans de scroll** avant la première preuve sociale
- **Maximum 3 écrans** avant le calculateur (premier geste interactif)
- Chaque section fait **1 écran maximum** en hauteur (desktop)
- Alternance stricte : texte → visuel → texte → interactif → texte
- **Aucun contenu caché** (pas de panels dépliables, pas de tabs, pas de modals)
- Tout est visible dans le flux naturel du scroll

### Hiérarchie visuelle

- Ratio texte/espace blanc : **40/60** — la page respire
- Un seul niveau de titre par section (pas de sous-sections imbriquées)
- Couleur d'accent utilisée avec **parcimonie** (1 élément par section max)
- Les images et avatars sont des **ancres visuelles** qui rythment le scroll

### Responsive

- Mobile-first : la structure doit fonctionner **parfaitement en 375px**
- Desktop : max-width `780px` (colonne étroite = lecture confortable, comme un article)
- Pas de grille multi-colonnes sauf pour les offres (qui passent en stack sur mobile)

### Performance

- Aucune dépendance JS externe
- Fonts : Inter (corps) + Playfair Display (titres) uniquement
- Animations CSS minimales (opacity + translateY au scroll, rien de plus)

---

## Structure section par section

### Section 1 — ACCROCHE (hero)

**Objectif :** En 3 secondes, le prospect se dit "c'est exactement mon problème".

| Élément | Détail |
|---|---|
| Surtitre | Petite phrase contextuelle, ex: "Pour les dirigeants de PME qui n'ont pas de DRH" |
| Titre principal | **Question ou situation douloureuse**, pas une proposition de valeur. Ex: "Votre entreprise grandit. Vos problèmes RH aussi." |
| Sous-titre | 2 lignes max. Nommer 3-4 douleurs concrètes en une phrase. Ex: "Un départ imprévu, un conflit qui s'envenime, une embauche ratée — et personne pour vous aider à décider." |
| CTA | **Aucun.** Pas de bouton d'action dans le hero. Le seul "call to action" est une flèche ou un texte qui invite à scroller. |
| Photo | Valérie, petite, ronde, en bas à droite — présence humaine discrète, pas centrale |

**Contrainte :** Le hero ne mentionne ni "Twiga", ni "20 ans d'expérience", ni "DRH externalisée". On parle du prospect, pas de nous.

**Hauteur :** `70vh` max desktop, `60vh` mobile. Pas de plein écran.

---

### Section 2 — BARRE DE PREUVE SOCIALE

**Objectif :** Crédibiliser instantanément, avant que le prospect ne lise quoi que ce soit d'autre.

| Élément | Détail |
|---|---|
| Format | Bande horizontale discrète, fond légèrement contrasté |
| Contenu | 3-4 chiffres clés en ligne : "20 ans d'expérience · +400 recrutements · PME de 10 à 500 salariés · Toulouse & remote" |
| Style | Petite typo, gris moyen, sobre — ce n'est pas une section, c'est une **ligne de confiance** |

**Contrainte :** Pas de logos (Valérie est indépendante, pas une agence). Des chiffres humains.

**Hauteur :** `60px` fixe. Ne doit pas ressembler à une section.

---

### Section 3 — SITUATIONS (nommer la douleur)

**Objectif :** Le prospect se reconnaît dans au moins une situation. Effet miroir.

| Élément | Détail |
|---|---|
| Intro | "Vous vous reconnaissez ?" ou similaire — une ligne, directe |
| Cartes | 4 cartes de situation, chacune = une phrase de douleur concrète |
| Exemples | "Votre meilleur élément vient de partir — et vous ne savez pas pourquoi." / "Un manager toxique plombe l'équipe mais c'est votre meilleur commercial." / "Vous avez reçu une lettre des prud'hommes." / "Vous devez recruter 5 personnes et vous ne savez pas par où commencer." |
| Style | Icône minimaliste + texte court + fond blanc, bordure subtile |

**Contrainte :** Pas de solution ici. Seulement la douleur. Chaque carte = une phrase, pas un paragraphe.

**Hauteur :** 1 écran max. Les cartes sont en grille 2×2 desktop, stack mobile.

---

### Section 4 — LE GUIDE (Valérie, brièvement)

**Objectif :** Transition entre "j'ai un problème" et "quelqu'un peut m'aider". Valérie se présente en 3 lignes, pas plus.

| Élément | Détail |
|---|---|
| Photo | Portrait Valérie, plus grand que dans le hero (~120px rond) |
| Citation | En "je", directe. Ex: "Je suis Valérie. Depuis 20 ans, j'aide les dirigeants de PME à reprendre le contrôle de leurs RH. Pas de jargon, pas de slides de 80 pages. Des solutions concrètes, à votre rythme." |
| Signature | "Valérie Gaudel — Fondatrice de Twiga RH" en petit sous la citation |

**Contrainte :** C'est la **première et seule fois** que la page parle de Valérie. Maximum 4 lignes. Pas de liste de compétences, pas de CV.

**Hauteur :** Demi-écran max. Section aérée, centrée.

---

### Section 5 — CALCULATEUR (valeur concrète)

**Objectif :** Premier geste interactif. Le prospect obtient un chiffre *qui le concerne personnellement*. C'est le "moment de vérité".

| Élément | Détail |
|---|---|
| Intro | Une phrase d'accroche. Ex: "Combien vous coûtent réellement vos départs ?" |
| Sliders | 3 curseurs : effectif, taux de turnover, salaire moyen |
| Résultat | Encart sombre avec montant en gros, coût par départ en petit |
| Insight | Phrase contextuelle sous le résultat. Ex: "C'est l'équivalent de X mois de salaire d'un DRH à temps partagé." |

**Contrainte :** Pas de CTA commercial après le calculateur. Juste l'insight. Le choc du chiffre suffit.

**Hauteur :** 1 écran. Le résultat doit être visible sans scroller après avoir bougé les curseurs.

---

### Section 6 — PONT VERS L'APPROFONDISSEMENT

**Objectif :** Pour les prospects engagés, proposer d'aller plus loin avec les outils de diagnostic. C'est un **embranchement optionnel**, pas un passage obligé.

| Élément | Détail |
|---|---|
| Format | Bandeau discret avec fond légèrement contrasté |
| Texte | "Envie d'aller plus loin ? Deux outils gratuits pour affiner votre diagnostic." |
| 2 liens | Carte compacte quiz dirigeant (4 min) + Carte compacte diagnostic entreprise (6 min) |
| Style | Cartes petites, inline, horizontales. Pas de cartes géantes. |

**Contrainte :** Cette section est **optionnelle visuellement** — elle ne casse pas le flux de lecture. Un prospect qui ne clique pas continue naturellement vers les témoignages.

**Hauteur :** Demi-écran max.

---

### Section 7 — TÉMOIGNAGES (preuve sociale détaillée)

**Objectif :** Le prospect lit des gens comme lui qui racontent leur expérience. La confiance se construit.

| Élément | Détail |
|---|---|
| Format | 3 témoignages **visibles en entier**, en stack vertical |
| Chaque témoignage | Contexte (secteur, taille) + citation longue (3-4 phrases) + avatar + nom + titre |
| Style | Guillemets stylisés, texte en italique, fond alternant blanc/gris très léger |

**Contrainte :** Les témoignages sont **dans le flux principal**. Pas de carrousel, pas de slider, pas de panel. On les lit en scrollant, naturellement.

**Hauteur :** ~1.5 écran (on accepte que cette section soit longue — c'est voulu).

---

### Section 8 — L'OFFRE (3 formules)

**Objectif :** Maintenant que le prospect a confiance, il découvre comment travailler avec Valérie.

| Élément | Détail |
|---|---|
| Intro | "Comment on travaille ensemble" — ton simple |
| 3 cartes | DRH à temps partagé / Conseil ponctuel / Coaching |
| Chaque carte | Titre + 2-3 lignes de description + "Pour qui c'est fait" en une ligne |
| Style | Grille 3 colonnes desktop, stack mobile. Bordure colorée en haut de chaque carte. |

**Contrainte :** Pas de prix (c'est du sur-mesure). Pas de bouton "acheter". Juste de l'information.

**Hauteur :** 1 écran max.

---

### Section 9 — CTA FINAL (contact)

**Objectif :** Le prospect est prêt. On lui facilite le passage à l'action.

| Élément | Détail |
|---|---|
| Titre | Direct et humain. Ex: "On en parle ?" ou "Un premier échange, sans engagement" |
| Sous-texte | "15 minutes en visio ou par téléphone. Je vous écoute, vous décidez." |
| Boutons | 2 boutons : "M'écrire" (mailto) + "Appeler" (tel) |
| Téléphone | Numéro visible en clair, pas juste dans un bouton |
| Localisation | "Près de Toulouse · Partout en visio" |

**Contrainte :** Fond contrasté (sombre) pour marquer la rupture visuelle. C'est le **seul moment** de la page qui demande quelque chose au prospect.

**Hauteur :** Demi-écran. Centré. Respire.

---

### Section 10 — FOOTER

Minimaliste. © 2025 Twiga RH — Valérie Gaudel. Rien d'autre.

---

## Récapitulatif du flux

```
┌─────────────────────────────────────┐
│  1. ACCROCHE                        │  ← "C'est mon problème"
│     Question douloureuse, pas de CTA│
├─────────────────────────────────────┤
│  2. BARRE DE PREUVE                 │  ← "C'est crédible"
│     20 ans · +400 recrutements      │
├─────────────────────────────────────┤
│  3. SITUATIONS                      │  ← "Je me reconnais"
│     4 cartes de douleur concrète    │
├─────────────────────────────────────┤
│  4. LE GUIDE                        │  ← "Quelqu'un comprend"
│     Valérie, 3 lignes, en "je"      │
├─────────────────────────────────────┤
│  5. CALCULATEUR                     │  ← "Ça me concerne"
│     Chiffre personnel, insight      │
├─────────────────────────────────────┤
│  6. PONT (optionnel)                │  ← "Je peux approfondir"
│     Quiz dirigeant + Diagnostic     │
├─────────────────────────────────────┤
│  7. TÉMOIGNAGES                     │  ← "D'autres l'ont fait"
│     3 récits complets, visibles     │
├─────────────────────────────────────┤
│  8. OFFRE                           │  ← "Je comprends comment"
│     3 formules, pas de prix         │
├─────────────────────────────────────┤
│  9. CTA FINAL                       │  ← "J'agis"
│     "On en parle ?" + tel + mail    │
├─────────────────────────────────────┤
│ 10. FOOTER                          │
└─────────────────────────────────────┘
```

---

## Éléments interdits sur la V6

- ❌ Panels dépliables / accordéons
- ❌ Grille de choix type "dashboard"
- ❌ CTA dans le hero
- ❌ Carrousel ou slider
- ❌ Jargon RH ("externalisation", "structuration", "leviers de performance")
- ❌ Liste de compétences ou CV
- ❌ Plus de 2 polices
- ❌ Animations complexes ou scroll-jacking
- ❌ Contenu caché derrière une interaction

## Éléments obligatoires sur la V6

- ✅ La douleur nommée avant toute solution
- ✅ Preuve sociale visible sans aucun clic
- ✅ Calculateur interactif dans le flux
- ✅ Témoignages complets dans le scroll
- ✅ Un seul CTA, en fin de page
- ✅ Ton "je/vous", conversationnel
- ✅ Max-width 780px (lecture article)
- ✅ Fonctionne parfaitement en 375px
- ✅ DA skin switcher (DA1/DA2/DA3)
- ✅ Lien retour Hub
