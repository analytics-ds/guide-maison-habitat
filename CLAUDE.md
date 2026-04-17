# Hugo Site Factory

Ce repo est un template pour créer des sites blogs statiques avec Hugo, optimises SEO/GEO, heberges gratuitement sur GitHub Pages.

## Comment ca marche

Ce repo ne contient pas de site. Il contient les **instructions et templates** pour que Claude Code genere un site complet automatiquement.

### Premier lancement

1. L'utilisateur connecte Claude Code a ce repo
2. L'utilisateur tape `/create-site`
3. Claude pose les questions nécessaires (nom du site, couleurs, catégories, etc.)
4. Claude genere tout le site Hugo, les fichiers SEO, et configure le deploiement
5. L'utilisateur push sur GitHub, active GitHub Pages, le site est en ligne

### Utilisation courante

- `/create-article` : créer un nouvel article de blog (choix parmi plusieurs types : article standard, comparatif). Push automatiquement sur GitHub si le repo est configure
- `/seo-setup` : generer ou mettre a jour les fichiers SEO techniques de base (robots.txt, llms.txt, sitemap, structured data)
- `/seo` : mode interactif pour modifier/ajouter des éléments SEO (meta tags, JSON-LD, audit on-page, etc.)
- `/serve` : lancer le serveur Hugo en local (previsualisation sur `http://localhost:1313/`)
- `/share` : lancer Hugo + ngrok pour partager le site via un lien public (accessible par n'importe qui)
- `/github-setup` : créer un repo GitHub, push le code et activer GitHub Pages (mise en ligne du site)
- `/github-deploy` : push les modifications vers GitHub et declencher le deploiement

## Structure du repo

```
.claude/
├── scripts/
│   └── fetch-image.sh           ← Recuperation auto d'image libre de droit (Openverse API)
├── skills/
│   ├── create-site.md           ← Workflow création de site complet
│   ├── create-article.md        ← Workflow création d'article (multi-types)
│   ├── seo-setup.md             ← Workflow fichiers SEO techniques (baseline)
│   ├── seo.md                   ← Mode interactif SEO (modifications ponctuelles)
│   ├── serve.md                 ← Lancer le serveur Hugo en local
│   ├── share.md                 ← Lancer Hugo + ngrok (partage public)
│   ├── github-setup.md          ← Créer un repo GitHub + activer GitHub Pages
│   └── github-deploy.md         ← Push et deployer sur GitHub Pages
└── templates/
    ├── data/
    │   ├── authors.yaml          ← 6 auteurs partages avec bios FR/EN, expertise, topics
    │   └── avatar-prompts.md     ← Prompts de generation des 6 avatars (Midjourney/DALL-E)
    ├── hugo-workflow.yml         ← GitHub Actions CI/CD
    ├── main.css                  ← Design system CSS complet (variables, composants, responsive, a11y)
    ├── articles/                 ← Templates d'articles par type
    │   ├── article-standard.md   ← Article informatif SEO + GEO (type par defaut)
    │   └── geo-comparatif.md     ← Article comparatif avec mise en avant
    ├── seo/                      ← Fichiers SEO techniques (editables)
    │   ├── robots.txt            ← Modèle robots.txt
    │   ├── llms.txt              ← Modèle llms.txt
    │   └── structured-data/      ← Schemas JSON-LD
    │       ├── article.json      ← Article (avec image et @id croise)
    │       ├── organization.json ← Organization (avec @id, logo, expertise)
    │       ├── author.json       ← Person (auteur)
    │       ├── breadcrumb.json   ← BreadcrumbList
    │       ├── website.json      ← WebSite (avec publisher @id)
    │       └── faq.json          ← FAQPage (genere auto depuis frontmatter)
    ├── layouts/
    │   ├── baseof.html           ← Layout de base (skip-to-content, fonts non-bloquantes, favicon)
    │   ├── home.html             ← Page d'accueil
    │   ├── list.html             ← Pages de liste
    │   ├── single.html           ← Page article (breadcrumb, TOC sticky, image hero, auteur, articles similaires)
    │   ├── sitemap-html.html     ← Page plan du site (liste toutes les pages)
    │   └── 404.html              ← Page 404 custom
    └── partials/
        ├── header.html           ← Header sticky (backdrop-filter, aria-labels, mobile menu)
        ├── footer.html           ← Footer (aria-label, lien plan du site)
        └── seo-head.html         ← Meta tags SEO complets + JSON-LD auto (OG avec image, Twitter, canonical, hreflang, author, article:section, FAQPage auto, Organization @id)
```

## Contexte du site

> Cette section est remplie automatiquement par le skill `/create-site`.
> Elle permet a Claude de connaitre le contexte du site pour les futures actions.

- **Nom du site** : Guide Maison & Habitat
- **Description (FR)** : Guide Maison & Habitat : immobilier, investissement, aménagement, travaux, deco et jardin. Conseils d'experts, comparatifs et guides pratiques.
- **Description (EN)** : Guide Maison & Habitat: real estate, investment, interior design, rénovation, decor and garden. Expert advice, comparisons and practical guides.
- **URL** : https://guide-maison-habitat.fr/
- **Charte graphique** : style éditorial vert olive + creme chaud (inspiration Armonia Excursions : typo serif italic impactante, cards arrondies, CTA pill sombres, fleches ↗)
- **Couleurs** :
  - primary : `#3D4A2A` (vert olive fonce)
  - primary-light : `#5A6B45`
  - background : `#F4EFE3` (creme chaud)
  - background-alt : `#E8E2D0` (creme fonce pour sections alternees)
  - accent : `#3D4A2A` (même que primary)
  - cta : `#3D4A2A`
  - cta-hover : `#2A3419`
  - text : `#1A1A14`
  - text-light : `#5A5A52`
  - border : `#D6CFBA`
- **Polices** : Fraunces (titres, italic pour hero et logos), Inter (corps + UI)
- **Langue principale** : français (version EN active en sous-dossier `/en/`)
- **Architecture SEO** : 2 silos thematiques clairs pour positionnement expert immobilier + maison
  - **Univers Immobilier** (3 cats) : Immobilier, Investissement immobilier, Ou vivre
  - **Univers Maison** (4 cats) : Aménagement intérieur, Travaux et rénovation, Décoration, Jardin
- **Catégories (FR ↔ EN)** :
  - Immobilier / Real estate
  - Investissement immobilier / Real estate investment
  - Ou vivre / Where to live
  - Aménagement intérieur / Interior design
  - Travaux et rénovation / Rénovation and works
  - Décoration / Décoration
  - Jardin / Garden
- **Règle d'affectation auteur** :
  - `claire-beaumont` : aménagement, travaux, décoration, jardin (auteur principal par defaut)
  - `sophie-martin` : immobilier, investissement immobilier, ou vivre (finance/patrimoine)
- **Maillage interne** : chaque article des cats Immobilier / Investissement / Ou vivre doit contenir au moins 3 liens internes vers d'autres articles de ces 3 cats pour renforcer le cocon semantique immobilier.
- **Avatars** : non generes. Prompts dans `.claude/templates/data/avatar-prompts.md`. Les placeholders (1ere lettre du nom sur fond colore) s'affichent en attendant.
- **Image OG par defaut** : `/images/og-default.jpg` a créer (1200x630). Non présente pour l'instant.

## Suivi des publications (MEMORY.md)

Le fichier `MEMORY.md` à la racine tracé tous les articles publies, classes par semaine. Il est mis a jour automatiquement par `/create-article`.

**Limite de publication : 4 articles par semaine maximum.** Avant chaque création d'article, le système vérifié le quota. Si 4 articles sont déjà publies dans la semaine en cours, l'utilisateur est averti.

Cette limité sert a éviter la publication en masse et a maintenir un rythme de publication régulier, ce qui est meilleur pour le SEO.

## Règles générales

- **Bilinguisme obligatoire (langue principale + EN)** : tous les blogs generes par ce template sont bilingues. La langue principale est servie à la racine (`/`), la version anglaise en sous-dossier `/en/`. Hugo gere le multilingue via la convention de dossiers `content/` (principale) et `content/en/` (anglais). Chaque article et page à une paire de fichiers avec un `translationKey` identique dans le frontmatter. Le header contient un language switcher automatique. Les balises hreflang sont generees automatiquement par le partial `seo-head.html`. **Ne JAMAIS generer un site ou un article dans une seule langue** — c'est systematiquement FR + EN (ou la langue principale + EN)
- Toujours utiliser `relURL` dans les templates Hugo pour les liens (compatibilite GitHub Pages)
- Les articles vont dans `content/blog/` (langue principale) et `content/en/blog/` (anglais)
- Les slugs sont en minuscules, sans accents, mots separes par des tirets
- Ne JAMAIS utiliser `&` dans les noms de catégories ou de tags — toujours remplacer par "et" (Hugo genere un double tiret `--` dans le slug, ce qui casse les URLs)
- Le ton des articles est impersonnel (pas de je/tu/nous/vous) sauf instruction contraire
- Les specs d'article (mots minimum, H2, blocs obligatoires) dependent du type choisi — lire les `<!-- NOTES POUR CLAUDE -->` dans chaque template d'article
- Chaque article doit contenir au minimum 3 liens internes contextuels vers d'autres articles du blog. L'ancre de chaque lien doit contenir le mot-cle principal de l'article cible. **Maillage intra-langue uniquement** : un article FR ne mail que des articles FR, un article EN ne mail que des articles EN (le lien vers la traduction est gere par le language switcher du header)
- **Système d'auteurs partage** : 6 auteurs fictifs definis dans `data/authors.yaml` (copie depuis `.claude/templates/data/authors.yaml` à la création du site). Chaque auteur a un id-slug, un nom, un type (person/organization), un avatar, des `jobTitle`/`role`/`bio` bilingues FR/EN, une liste d'`expertise` et une liste de `topics` (mots-cles pour la sélection automatique). Les auteurs disponibles : `thomas-durand` (tech), `magalie-ergoz` (mode/beaute), `claire-beaumont` (maison/habitat), `laura-verdier` (santé/bien-etre), `kevin-moreau` (transport/mobilité), `sophie-martin` (finance/patrimoine)
- **Selection automatique de l'auteur** : dans le frontmatter d'un article, le champ `author` contient l'**ID slug** de l'auteur (ex: `author: thomas-durand`), pas son nom complet. La skill `/create-article` sélectionné automatiquement l'auteur le plus pertinent selon les `topics` et `expertise` qui matchent avec le sujet de l'article. Si aucun match clair, l'auteur principal du site (defini dans la section "Contexte du site" de ce CLAUDE.md) est utilisé
- **Avatars des auteurs** : fichiers WebP 512x512 dans `static/images/authors/[id].webp`. Style unifie "flat illustration portrait". Prompts de generation documentes dans `.claude/templates/data/avatar-prompts.md`. Si l'avatar est manquant, un placeholder coloree avec la 1ere lettre du nom s'affiche
- **JSON-LD Author** : le partial `seo-head.html` genere automatiquement un schema.org/Person (ou Organization) complet depuis les données de `data/authors.yaml` (name, jobTitle, description, knowsAbout, image, sameAs, worksFor)
- **Bloc auteur en bas d'article** : le layout `single.html` affiche automatiquement un encart avec avatar, nom, role, bio complète et expertise de l'auteur, traduit dans la langue de l'article (FR ou EN)
- Les templates SEO dans `.claude/templates/seo/` sont editables par l'utilisateur — toujours lire la version en place avant de generer
- Pour ajouter un nouveau type d'article, créer un `.md` dans `.claude/templates/articles/` — il sera automatiquement propose par `/create-article`
- Pour ajouter un schema JSON-LD, créer un `.json` dans `.claude/templates/seo/structured-data/` et utiliser `/seo` pour l'intégrer
- Chaque article doit avoir un champ `lastmod` dans le frontmatter (= date de dernière modification). Il est utilisé par le sitemap XML, le sitemap HTML et le schema JSON-LD
- Quand un article est modifié, toujours mettre a jour le champ `lastmod` avec la date du jour
- Le sitemap HTML (`/plan-du-site/`) se regenere automatiquement à chaque build Hugo
- Toujours build et vérifier (`hugo`) avant de commit
- Chaque article doit avoir un champ `faq` dans le frontmatter (liste de questions/réponses) pour generer automatiquement le schema FAQPage JSON-LD. Minimum 3 questions
- Chaque article à une image hero OBLIGATOIRE, recuperee automatiquement par `.claude/scripts/fetch-image.sh` au moment de `/create-article`. L'image provient de l'API publique Openverse (federe Wikimedia, Flickr, etc.), filtree sur les licences autorisant l'usage commercial et la modification (CC BY, CC BY-SA, CC0, PDM). Convertie en WebP automatiquement si `cwebp` est installé. Stockee dans `static/images/blog/[slug].webp`
- Le frontmatter contient 3 champs liés a l'image : `image` (chemin Hugo), `imageAlt` (texte alternatif FR, max 125 car), `imageCredit` (attribution du photographe). Ces 3 champs sont remplis automatiquement par le script
- L'image est affichee : (1) dans les cards de la homepage et des pages de liste, (2) en bannière côté a côté avec le titre sur la page article, (3) dans og:image pour les partages sociaux, (4) dans le schema Article JSON-LD
- Le credit photo est affiche sous l'image de l'article (petite mention en italique alignee a droite). Obligatoire pour respecter les licences CC BY et CC BY-SA
- Les Google Fonts sont chargees en non-bloquant (média="print" + swap JS) pour de meilleures performances
- Le layout inclut un lien "Skip to content" pour l'accessibilite
- Les navigations ont des `aria-label` pour les lecteurs d'ecran
- Le CSS respecte `prefers-reduced-motion` pour desactiver les animations si l'utilisateur le demandé
- Les articles affichent une table des matières (TOC) sticky en sidebar, generee automatiquement par Hugo
- Les articles similaires sont affiches en bas de page, calcules par Hugo via la config `[related]` dans hugo.toml

## Comment répondre a l'utilisateur

- Tutoiement, ton decontracte
- Pas de jargon technique sans explication
- Reponses structurees avec listes a puces
- Pas d'emoji sauf demandé explicite




## Règle IMPERATIVE : toute nouvelle URL doit apparaitre dans le sitemap + plan de site

**Chaque fois qu une URL est ajoutée au site (article, page, catégorie, auteur...), elle DOIT être présente dans :**

### 1. Le sitemap XML (robots + bots)

Hugo genere automatiquement les sitemaps via :
- `layouts/sitemapindex.xml` -> `/sitemap.xml` (l index qui référence les sitemaps par langue)
- `layouts/sitemap.xml` -> `/fr/sitemap.xml` + `/en/sitemap.xml` (urlsets par langue)

Vérifier après build :
```bash
hugo
grep "<nouveau-slug>" public/fr/sitemap.xml public/en/sitemap.xml
```

### 2. Le plan de site HTML (utilisateurs + bots)

Page `/plan-du-site/` (FR) et `/en/site-map/` (EN) rendues via `layouts/_default/sitemap-html.html`. Elles listent toutes les pages groupees par section (Pages principales, Blog, Catégories, Auteurs, Pages légales). Mise a jour automatique au build Hugo.

**LE LIEN VERS `/plan-du-site/` DOIT ETRE PRESENT DANS LE FOOTER DE TOUTES LES PAGES** (via `layouts/partials/footer.html`).

### 3. La page auteur

Page `/authors/<slug-auteur>/` qui liste automatiquement tous les articles dont le frontmatter contient `author: <slug>`. Vérifier que le slug de l auteur dans le frontmatter correspond a un auteur defini dans `data/authors.yaml`.

### 4. La liste du blog

Page `/blog/` qui liste les articles par date decroissante. Hugo l inclut automatiquement si le fichier est dans `content/blog/` (FR) ou `content/en/blog/` (EN).

### 5. Le JSON-LD Article (SEO / schema.org)

L article genere automatiquement son schema.org/Article via `seo-head.html` (date, auteur, headline, image).

### 6. Le fichier llms.txt (referencement IA)

Le fichier `static/llms.txt` à la racine du site liste toutes les URLs stratégiques destinees aux LLMs (ChatGPT, Claude, Perplexity, etc.).

**À chaque publication ou modification de contenu, ajouter la nouvelle URL dans la section appropriee du fichier `static/llms.txt`.**

Structure attendue :

```markdown
# Nom du Site

> Description courte et factuelle du site

## A propos

Description éditoriale (methodologie, independance, auteurs experts, etc.)

## Articles de référence (FR)

- Titre de l'article 1 : https://domaine.com/blog/slug-1/
- Titre de l'article 2 : https://domaine.com/blog/slug-2/
- [a compléter à chaque nouvel article]

## Version anglaise (EN) — si multilingue

- Homepage EN : https://domaine.com/en/
- Blog EN : https://domaine.com/en/blog/
- Title of article 1 : https://domaine.com/en/blog/slug-1/

## Informations techniques

- Generateur : Hugo (site statique)
- Multilingue : français (defaut) + anglais (si applicable)
- Sitemap : https://domaine.com/sitemap.xml
- RSS : https://domaine.com/index.xml
- Schema.org : Organization, Article, BreadcrumbList, FAQPage, WebSite, CollectionPage, Person

## Contact

- URL : https://domaine.com/
```

Après chaque nouvel article :
1. Ouvrir `static/llms.txt`
2. Ajouter la ligne `- Titre complet : URL absolue` dans la bonne section (FR ou EN)
3. Commit + push

### Workflow post-publication

```bash
# 1. Build
hugo

# 2. Vérifier sitemap
grep "<nouveau-slug>" public/fr/sitemap.xml
grep "<nouveau-slug>" public/en/sitemap.xml  # si multilingue

# 3. Vérifier plan de site HTML
grep "<nouveau-slug>" public/plan-du-site/index.html

# 4. Vérifier page auteur
grep "<titre>" public/authors/<slug>/index.html

# 5. Vérifier le footer (plan-du-site doit être présent)
grep "plan-du-site" public/index.html

# 6. Vérifier llms.txt (mise a jour manuelle)
grep "<titre>" static/llms.txt

# 7. Commit + push
git add -A && git commit -m "Article : <titre>" && git push origin main
```

**Si l une des 5 vérifications echoue, NE PAS COMMIT et debugger.**

