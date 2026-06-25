# Studio 888 — Kevin Hermand

Portfolio photographique, vidéographique et drone. Site vitrine one-page en HTML/CSS/JS pur, déployé sur Vercel.

## Aperçu

Site personnel de Kevin Hermand (Studio 888), photographe · vidéaste · pilote de drone certifié DGAC, basé en Normandie. Le site présente ses travaux et permet aux clients de le contacter directement.

### Sections

| Section | Description |
|---|---|
| **Hero** | Vidéo plein écran en autoplay avec typewriter animé, mode focus cinéma au clic |
| **À propos** | Présentation, photo de profil, statistiques (5+ ans, 100+ projets, certifié DGAC) |
| **Services** | Photographie · Vidéographie · Drone — 3 cartes cliquables |
| **Photos** | Grille éditoriale 12 colonnes de 13 photos, lightbox avec navigation clavier/swipe |
| **Vidéos** | Onglets : Drone Ballon / Drone Altitude / Démo YouTube |
| **Drone** | Embed YouTube + texte de présentation, badge DGAC |
| **Contact** | Téléphone, email, localisation, bouton mailto + lien rendez-vous (zcal) |

## Stack technique

- **HTML5 / CSS3 / Vanilla JS** — zéro dépendance, zéro framework
- **Google Fonts** — Oswald, Inter, Cormorant Garamond
- **Vercel** — déploiement statique (`vercel.json` avec `outputDirectory: "."`)
- **Assets locaux** — photos compressées (`assets/Select-Compress/`), vidéos (`assets/videos/`, `assets/trailer/`)

## Structure du projet

```
web_studio888_v2/
├── index.html              # Source unique du site
├── vercel.json             # Config déploiement Vercel
├── assets/
│   ├── logo-white-rmbg.png
│   ├── images/
│   │   └── photo_profil.JPEG
│   ├── Select-Compress/    # 13 photos du portfolio (DSCF*.jpg)
│   ├── trailer/
│   │   └── Portfolio_trailer.mp4   # Vidéo hero
│   └── videos/
│       ├── drone_ballon.mp4
│       └── drone_hauteur.mp4
```

## Lancer en local

```bash
# Python (inclus sur macOS/Linux)
python3 -m http.server 8888

# Node.js
npx serve .

# VS Code
# Extension "Live Server" → clic droit sur index.html → Open with Live Server
```

Ouvrir ensuite [http://localhost:8888](http://localhost:8888).

> Les vidéos et la lightbox requièrent un serveur HTTP — ouvrir `index.html` directement via `file://` peut bloquer le chargement des assets vidéo.

## Déploiement

Le site est déployé sur Vercel via le compte `kehermand76`.

```bash
# Installer Vercel CLI (une seule fois)
npm i -g vercel

# Déployer
vercel --prod
```

## Fonctionnalités notables

- **Curseur custom** — point + anneau avec lag, blend-mode `difference`
- **Loader** — animation de logo + barre de progression au chargement
- **Mode focus** — clic sur le hero masque l'UI pour regarder la vidéo en plein écran
- **Typewriter** — liste de 16 spécialités animées dans le hero
- **Lightbox** — navigation clavier (←/→/Esc) et swipe tactile
- **Reveal on scroll** — `IntersectionObserver` pour les animations d'entrée
- **Responsive** — breakpoints 900px (tablet) et 600px (mobile), menu hamburger

## Contact

- Instagram : [@kev.pics8](https://www.instagram.com/kev.pics8/)
- LinkedIn : [kevin-hermand](https://www.linkedin.com/in/kevin-hermand/)
- Email : ke.hermand76@gmail.com
