# SAMUELSONFRAMES — Guide complet

## 📁 Structure du projet

```
samuelsonframes/
├── index.html          ← Page d'accueil (grille 6 photos)
├── galerie.html        ← Page galerie par thème
├── about.html          ← Page À propos + Vidéo + Formulaire
├── css/
│   └── style.css       ← Tout le CSS (commun aux 3 pages)
├── images/             ← CRÉE CE DOSSIER et mets tes photos
│   ├── portrait1.jpg   ← Photo miniature thème Portrait (grille d'accueil)
│   ├── urbain1.jpg     ← Photo miniature thème Urbain
│   ├── nature1.jpg     ← Photo miniature thème Nature
│   ├── mode1.jpg       ← Photo miniature thème Mode
│   ├── archi1.jpg      ← Photo miniature thème Architecture
│   ├── sport1.jpg      ← Photo miniature thème Sport
│   │
│   ├── portrait2.jpg … portrait6.jpg   ← Photos galerie Portrait
│   ├── urbain2.jpg    … urbain6.jpg    ← Photos galerie Urbain
│   ├── nature2.jpg    … nature6.jpg    ← Photos galerie Nature
│   ├── mode2.jpg      … mode6.jpg      ← Photos galerie Mode
│   ├── archi2.jpg     … archi6.jpg     ← Photos galerie Architecture
│   ├── sport2.jpg     … sport6.jpg     ← Photos galerie Sport
│   └── portrait-samuelson.jpg          ← Ta photo (page About)
│
└── videos/             ← CRÉE CE DOSSIER
    └── showreel.mp4    ← Ta vidéo (page About, plein écran automatique)
```

---

## 🚀 Lancer le site

### Option recommandée — Live Server (VS Code)
1. Ouvre le dossier `samuelsonframes/` dans VS Code
2. Installe l'extension **Live Server** (ritwickdey.LiveServer)
3. Clic droit sur `index.html` → **Open with Live Server**

### Option simple
Double-clique sur `index.html` pour l'ouvrir dans le navigateur.

---

## 🖼️ Ajouter tes photos

1. Crée le dossier `images/` à la racine du projet
2. Place tes photos avec les noms exacts indiqués ci-dessus
3. Si tu n'as pas encore toutes tes photos, ne t'inquiète pas : des placeholders s'affichent automatiquement

**Conseil :** utilise des photos de bonne résolution (minimum 1200px de large)

---

## 🎬 Ajouter ta vidéo

1. Crée le dossier `videos/` à la racine
2. Place ta vidéo et renomme-la `showreel.mp4`
3. La vidéo se lancera automatiquement (muette, en boucle) sur la page About

**Formats supportés :** MP4 (recommandé), WebM, OGG

**Si tu veux utiliser YouTube :**
Dans `about.html`, remplace la balise `<video>` par :
```html
<iframe
  src="https://www.youtube.com/embed/TON_ID_VIDEO?autoplay=1&mute=1&loop=1&playlist=TON_ID_VIDEO"
  style="position:absolute;inset:0;width:100%;height:100%;border:none;"
  allow="autoplay"
></iframe>
```

---

## ✏️ Personnaliser le contenu

### Changer ton nom / ville
Dans les 3 fichiers HTML, remplace :
- `SAMUELSONFRAMES` → ton nom de portfolio
- `Strasbourg` → ta ville
- `Samuel Sonframes` → ton vrai nom

### Changer l'email
Dans `about.html`, remplace `ameliayengo180@gmail.com` par ton email.
Il y en a 3 occurrences :
- L'action du formulaire (`action="mailto:..."`)
- Le lien email dans les infos
- L'email affiché dans le footer et le bloc info

### Ajouter des photos à une galerie
Dans `galerie.html`, duplique un bloc `<div class="galerie-item">` :
```html
<div class="galerie-item" data-theme="portrait">
  <img src="images/portrait8.jpg" alt="Portrait 8" onerror="this.style.display='none'" />
  <div class="galerie-fallback" style="--n:8">08</div>
</div>
```

### Changer les thèmes
Si tu veux renommer "Sport" en "Reportage" par exemple :
1. Dans `index.html` : change le texte du `<span class="photo-title">`
2. Dans `galerie.html` : change `data-theme="sport"` en `data-theme="reportage"` sur tous les items
3. Dans le lien de la home : change `href="galerie.html#sport"` en `href="galerie.html#reportage"`

---

## 📬 Formulaire de contact

Le formulaire utilise `mailto:` — il ouvre le logiciel mail de l'utilisateur.

**Pour un envoi automatique sans logiciel mail :**
1. Crée un compte gratuit sur [formspree.io](https://formspree.io)
2. Crée un formulaire → tu obtiens un ID (ex: `xrgvkpqz`)
3. Dans `about.html`, remplace :
   ```html
   action="mailto:samuelsonpindyphoto@gmail.com" method="GET" enctype="text/plain"
   ```
   par :
   ```html
   action="https://formspree.io/f/xrgvkpqz" method="POST"
   ```

---

## 🎨 Changer les couleurs

Dans `css/style.css`, modifie les variables au début du fichier :
```css
:root {
  --black:  #0b0b0b;     /* Fond général */
  --white:  #f2f0eb;     /* Texte principal */
  --accent: #d4af7a;     /* Couleur dorée (titres italiques, accents) */
}
```

---

## ✅ Fonctionnalités

- ✅ Zéro JavaScript
- ✅ Entièrement responsive (mobile, tablette, desktop)
- ✅ Grille 2×3 sur la page d'accueil
- ✅ Assombrissement + titre au survol des photos
- ✅ Navigation par thème (clic → galerie dédiée)
- ✅ Galerie masonry (colonnes, photos de hauteurs variées)
- ✅ Menu hamburger CSS pur sur mobile
- ✅ Vidéo plein écran auto-play muette
- ✅ Formulaire de devis complet (prénom, nom, email, téléphone, type, date, budget, message)
- ✅ Email pré-rempli visible sur la page
- ✅ Animations CSS au chargement
