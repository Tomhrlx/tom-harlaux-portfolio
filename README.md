# Handoff : Portfolio Tom Harlaux — mise en ligne

## Objectif
Publier ce portfolio (site vitrine une page, statique) sur internet, gratuitement, avec une URL publique.

## Contenu du dossier
- `index.html` — **le site complet, autonome** (1,4 Mo). Toutes les images, le CV (PDF) et le code sont inclus dans ce seul fichier. C'est le fichier à héberger. Il n'y a rien à compiler ni à installer.
- `source/` — les fichiers sources (référence uniquement, non nécessaires au déploiement) :
  - `Portfolio Tom Harlaux.dc.html` — source du design
  - `assets/` — images et CV d'origine

## Ce qu'il faut faire
Déployer `index.html` tel quel sur un hébergeur statique gratuit. Ordre de préférence :

1. **GitHub Pages**
   - Créer un dépôt public (ex. `tom-harlaux-portfolio`), y placer `index.html` à la racine.
   - Settings → Pages → Source : branche `main`, dossier `/ (root)`.
   - URL obtenue : `https://<user>.github.io/tom-harlaux-portfolio/`
2. **Netlify** (alternative) : `npx netlify-cli deploy --prod --dir .` depuis un dossier contenant `index.html`, ou dépôt par glisser-déposer sur app.netlify.com/drop.
3. **Vercel** (alternative) : `npx vercel --prod` depuis le même dossier.

Ne pas transformer le site en projet React/Vite ou autre : c'est déjà un fichier HTML final, fonctionnel hors ligne.

## Vérifications après déploiement
- La page s'ouvre, fond sombre, particules animées, curseur personnalisé (point violet).
- Les 6 captures d'écran (Districall ×3, BDE Drakarys ×3) et la photo de profil s'affichent.
- Le bouton « Télécharger le CV » (hero et section Contact) télécharge `CV-Tom-Harlaux.pdf`.
- Le formulaire de contact envoie vers Formspree (`https://formspree.io/f/xbgjydrz`) et affiche « Message envoyé ✓ ». Formspree autorise les envois depuis n'importe quel domaine par défaut ; si les envois sont refusés, ajouter le domaine du site dans les réglages du formulaire Formspree (Settings → Restrict to Domain).
- Aucun appel réseau vers un serveur privé : seules les polices Google Fonts (Unbounded, Outfit) et Formspree sont externes.

## Améliorations possibles (hors périmètre, à ne faire que si demandé)
- Nom de domaine personnalisé (ex. `tomharlaux.fr`) via les réglages DNS de l'hébergeur.
- Balises `<meta>` Open Graph / description pour le partage LinkedIn.
- Version mobile : les grilles sont pensées pour desktop ; l'empilement en une colonne sous 768 px reste à faire.

## Fiche technique du design (référence)
- Style : sombre, glassmorphism (fonds `rgba(255,255,255,.035)`, bordures `rgba(255,255,255,.09)`, `backdrop-filter: blur(24–30px)`, rayons 24–40 px).
- Couleurs : fond `#07070d`, texte `#ecebf5`, secondaire `#b3b1c6`, discret `#8b89a0`, accent `#c2a3ff`, accents secondaires `#7c9cff`, `#5ee1c9`.
- Typographie : titres **Unbounded** (300/400/600/800), texte **Outfit** (300–600), via Google Fonts.
- Sections : Hero, bandeau défilant, À propos, Projets (Districall, BDE Drakarys), Compétences, Parcours, Contact + footer.
- Animations : particules sur canvas qui fuient le curseur, révélation au scroll (IntersectionObserver), compteurs animés, cartes en tilt 3D au survol, boutons magnétiques, barre de progression de lecture.
