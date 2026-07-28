# Tableau à Craie — Maths CP1 → Terminale

Application web installable (PWA) : jeu de maths avec tes propres questions,
5 niveaux par classe, jusqu'à 20 questions par niveau. Fonctionne hors-ligne
une fois installée, et tes données (les questions que tu ajoutes) restent
sur ton téléphone.

## 1. Mettre le site en ligne (obligatoire pour installer sur un téléphone)

Un téléphone ne peut pas "installer" des fichiers ouverts en local : il faut
d'abord héberger ces fichiers sur une adresse https://. Deux façons gratuites,
sans rien installer sur ton ordinateur :

### Option A — Netlify Drop (le plus simple)
1. Va sur https://app.netlify.com/drop
2. Glisse-dépose le dossier entier (ce dossier contenant index.html, app.js,
   style.css, manifest.json, sw.js, icons/) dans la zone indiquée.
3. Netlify te donne une adresse du type `https://nom-au-hasard.netlify.app`.
4. Ouvre cette adresse sur ton téléphone.

### Option B — GitHub Pages
1. Crée un dépôt GitHub et mets-y tous les fichiers de ce dossier (en
   conservant la structure, notamment le sous-dossier `icons/`).
2. Dans les paramètres du dépôt → Pages, active GitHub Pages sur la branche
   principale.
3. Ouvre l'adresse fournie (`https://tonpseudo.github.io/tonrepo/`) sur ton
   téléphone.

## 2. Installer l'application sur le téléphone

### Android (Chrome)
1. Ouvre l'adresse du site dans Chrome.
2. Un bandeau "Ajouter à l'écran d'accueil" peut apparaître automatiquement ;
   sinon, ouvre le menu ⋮ (trois points) → **Installer l'application** (ou
   "Ajouter à l'écran d'accueil").
3. L'icône craie apparaît sur l'écran d'accueil, et l'app s'ouvre en plein
   écran comme une vraie application.

### iPhone / iPad (Safari)
1. Ouvre l'adresse du site dans **Safari** (obligatoire, ça ne marche pas
   depuis Chrome sur iPhone).
2. Appuie sur le bouton Partager (le carré avec la flèche vers le haut).
3. Choisis **Sur l'écran d'accueil**, puis **Ajouter**.
4. L'icône apparaît sur l'écran d'accueil.

## 3. Où sont sauvegardées les questions ?

Les questions que tu ajoutes sont stockées directement dans le navigateur du
téléphone (`localStorage`), donc elles restent même hors connexion. Attention :
- Si tu désinstalles l'app ou effaces les données du navigateur, les questions
  ajoutées sont perdues.
- Les questions ne sont **pas partagées automatiquement** entre plusieurs
  téléphones : chaque appareil a ses propres questions, sauf si tout le monde
  utilise le même navigateur/profil.

## 4. Fichiers du projet

- `index.html` — **un seul fichier** qui contient tout : la structure de la
  page, le style "tableau noir / craie" (CSS) et toute la logique du jeu
  (JavaScript : classes, niveaux, quiz, ajout de questions)
- `manifest.json` — rend le site installable
- `sw.js` — service worker (fonctionnement hors-ligne)
- `icons/` — icônes de l'application

Seul `index.html` doit être ouvert/modifié pour le contenu du site ; les
autres fichiers ne servent qu'à l'installation en PWA.
