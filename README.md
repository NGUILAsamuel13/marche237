# Marché237 — Déploiement depuis un téléphone

## ⚠️ À savoir avant de commencer

Ce projet remplace `window.storage` (spécifique à Claude) par `localStorage`
(voir `src/storage.js`). Ça débloque tout de suite le test de l'upload photo
et le déploiement, MAIS `localStorage` est propre à chaque téléphone/navigateur :
deux visiteurs différents ne verront pas les mêmes annonces. C'est une étape
intermédiaire, pas la version finale. La vraie base de données partagée
(Firebase) sera la prochaine brique une fois ce déploiement testé.

## Étapes (tout depuis le téléphone, sans ordinateur)

### 1. Mettre le code sur GitHub

1. Installe l'app **GitHub** (Play Store) ou utilise github.com dans Chrome.
2. Crée un compte si tu n'en as pas.
3. Crée un nouveau dépôt (repository) : nomme-le `marche237`, laisse-le public.
4. Upload tous les fichiers de ce dossier dans le dépôt (GitHub permet
   l'upload de fichiers directement depuis le navigateur mobile : bouton
   "Add file" → "Upload files"). Garde la même structure de dossiers
   (le fichier `src/App.jsx` doit rester dans un dossier `src`).

### 2. Déployer sur Vercel

1. Va sur **vercel.com** dans Chrome, connecte-toi avec ton compte GitHub.
2. "Add New Project" → sélectionne le dépôt `marche237`.
3. Vercel détecte automatiquement Vite — ne change rien, appuie sur "Deploy".
4. Après 1-2 minutes, tu obtiens une vraie URL (ex: `marche237.vercel.app`)
   accessible par n'importe qui, sur n'importe quel téléphone.

### 3. Tester

Ouvre l'URL Vercel dans Chrome sur ton téléphone et refais le parcours complet :
Vendre → créer un espace → ajouter une photo → publier. Si l'upload de photo
fonctionne ici mais pas dans l'app Claude, ça confirme que c'était bien une
restriction de la sandbox de l'artifact, pas ton code.

## Prochaine étape après ce déploiement

Remplacer `src/storage.js` par une vraie intégration Firebase (Firestore +
Storage) pour que les annonces soient partagées entre tous les visiteurs,
pas juste stockées localement sur chaque téléphone.
