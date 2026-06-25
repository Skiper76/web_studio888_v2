# Studio 888 — Kevin Hermand

Portfolio photographique, vidéographique et drone. Site vitrine multi-pages en HTML/CSS/JS pur, déployé sur Vercel.

## Aperçu

Site personnel de Kevin Hermand (Studio 888), photographe · vidéaste · pilote de drone certifié DGAC, basé à Fécamp (Normandie). Le site présente ses travaux et permet aux clients de le contacter ou de réserver directement.

---

## Pages

| Page | URL | Description |
|---|---|---|
| **Accueil** | `/` | Portfolio principal one-page |
| **Mariage** | `/wedding/` | Sous-site dédié mariage (thème crème/or/noir) |
| **Sites web** | `/web.html` | Offres de création de sites web |
| **Tarifs** | `/tarifs.html` | Grille tarifaire complète (onglets par catégorie) |

---

## Sections — Accueil (`index.html`)

| Section | Description |
|---|---|
| **Hero** | Vidéo plein écran autoplay, typewriter animé 16 spécialités, mode focus cinéma |
| **À propos** | Photo de profil (`photo-kev.jpg`), présentation, stats (5+ ans, 100+ projets, DGAC) |
| **Services** | Photographie · Vidéographie · Drone — 3 cartes cliquables |
| **Photos** | Grille 13 photos, lightbox clavier/swipe, lien portfolio Lightroom Adobe |
| **Vidéos caméra** | Onglets : Cinématique / Ralenti / Stabilisé — bloc info caméra + description + lien portfolio Adobe |
| **Drone** | YouTube facade + texte pilote DGAC, onglets drone |
| **Contact** | Téléphone, email, localisation, Cal.com popup (namespace `discuter-de-mon-projet`) |

---

## Sous-site Mariage (`wedding/index.html`)

Thème élégant : Cormorant Garamond · Great Vibes · Jost — palette crème/or/encre.

| Section | Contenu |
|---|---|
| Hero | Photo plein écran (DSCF9060.jpg), ornements décoratifs |
| Intro | Grille 3 photos d'accroche |
| Galerie | 18 photos mariage en colonnes masonry, lightbox |
| Tarifs | Onglets Photo / Vidéo / Complet — 4 forfaits chacun |
| Contact | Cal.com popup, lien retour accueil |

**Forfaits Photo** : Essentiel 690 € (3h · 80 photos) · Sérénité 1 090 € (6h · 200 photos) · Prestige 1 790 € (10h · 350 photos) · Luxe 2 490 € (14h · 450 photos)

---

## Stack technique

- **HTML5 / CSS3 / Vanilla JS** — zéro dépendance, zéro framework
- **Google Fonts** — Oswald, Inter, Cormorant Garamond, Great Vibes, Jost
- **Vercel** — déploiement statique (`vercel.json` avec `outputDirectory: "."`)
- **Cloudflare R2** — hébergement vidéos et assets lourds (bucket public)
- **Cal.com** — prise de rendez-vous via popup element-click (`data-cal-link`)

---

## Structure du projet

```
web_studio888_v2/
├── index.html              # Accueil principal
├── web.html                # Page services web
├── tarifs.html             # Page tarifs (onglets par catégorie)
├── vercel.json             # Config déploiement Vercel
├── wedding/
│   └── index.html          # Sous-site mariage
├── assets/
│   ├── logo-white-rmbg.png
│   ├── logo/
│   │   └── logo_noir_rmbg.png      # Logo noir (fond clair)
│   ├── images/
│   │   ├── photo-kev.jpg           # Photo profil À propos
│   │   ├── wedding/                # 18 photos mariage
│   │   └── Select-Compress/        # 13 photos portfolio (DSCF*.jpg)
│   ├── trailer/
│   │   └── Portfolio_trailer.mp4   # Vidéo hero
│   └── videos/                     # Vidéos locales (non versionnées, sur R2)
```

**Vidéos sur Cloudflare R2** (`pub-397fb824d7fa411cb520f9f716dec06b.r2.dev`) :
- `camera_cinematique.mp4` · `camera_ralenti.mp4` · `camera_stabilise.mp4`
- `drone_ballon.mp4` · `drone_hauteur.mp4`

---

## Lancer en local

```bash
python3 -m http.server 8888
```

Ouvrir [http://localhost:8888](http://localhost:8888).

> Les vidéos et la lightbox requièrent un serveur HTTP — `file://` bloque le chargement des assets.

---

## Déploiement

Déploiement automatique sur Vercel à chaque `git push` sur `main` (branch = production).

```bash
git add .
git commit -m "message"
git push
```

DNS : OVH → Vercel nameservers (`ns1/ns2.vercel-dns.com`). Domaine : `studio888.fr`.

---

## Fonctionnalités notables

- **Curseur custom** — point + anneau avec lag, blend-mode `difference`
- **Loader** — animation logo + barre de progression
- **Mode focus hero** — clic masque l'UI pour regarder la vidéo plein écran
- **Typewriter** — 16 spécialités animées dans le hero
- **Lightbox** — navigation clavier (←/→/Esc) et swipe tactile, caméra + description par photo
- **YouTube facade** — thumbnail + bouton play custom, iframe chargé au clic
- **Cal.com popup** — prise de RDV sans quitter la page
- **Reveal on scroll** — `IntersectionObserver` pour animations d'entrée
- **Logo swap mariage** — `.logo-white` / `.logo-black` via `nav.scrolled`
- **Responsive** — breakpoints 900px (tablet) et 600px (mobile), menu hamburger

---

## Liens utiles

- **Portfolio photos** : [adobe.ly/4g62LNX](https://adobe.ly/4g62LNX)
- **Portfolio vidéos** : [adobe.ly/4vvsN23](https://adobe.ly/4vvsN23)
- **Instagram** : [@kev.pics8](https://www.instagram.com/kev.pics8/)
- **LinkedIn** : [kevin-hermand](https://www.linkedin.com/in/kevin-hermand/)
- **Email** : ke.hermand76@gmail.com
