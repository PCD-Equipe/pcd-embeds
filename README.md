# pcd-embeds — Créations HTML pour Notion

Pages HTML autonomes hébergées sur **GitHub Pages**, intégrées dans Notion via
des blocs `/embed`. Chaque création (issue de Claude design) = un fichier HTML +
ses images dans `assets/`.

- **Dépôt :** https://github.com/PCD-Equipe/pcd-embeds
- **Site :** https://pcd-equipe.github.io/pcd-embeds/

## Créations en ligne

Ce dépôt est la vitrine publique : il ne contient que des copies publiées, intégrées dans Notion.
Les sources de travail des outils sont dans le dépôt privé `PCD-Equipe/permaculture-design-outils`.

### Charte graphique

| Création | URL à coller dans Notion (`/embed`) |
|---|---|
| Charte graphique | https://pcd-equipe.github.io/pcd-embeds/charte-graphique.html |
| Variables CSS de la charte | https://pcd-equipe.github.io/pcd-embeds/pcd-tokens.css |

### Outils

| Outil | URL |
|---|---|
| Simulateur assainissement | https://pcd-equipe.github.io/pcd-embeds/simulateur-assainissement.html |
| Toilette (*TLB*) | https://pcd-equipe.github.io/pcd-embeds/toilette/ |

### Maquettes de CPT

| Maquette | URL | Statut |
|---|---|---|
| Vidéo (4 maquettes) | https://pcd-equipe.github.io/pcd-embeds/video/ | En cours |
| Fiche plante (*Tomate*, 3 colonnes) | https://pcd-equipe.github.io/pcd-embeds/plante/ | Référence |
| Glossaire | https://pcd-equipe.github.io/pcd-embeds/glossaire/ | Référence |
| Fiche recette (*Crukies*) | https://pcd-equipe.github.io/pcd-embeds/fiche-recette.html | Référence |
| Contributeur | https://pcd-equipe.github.io/pcd-embeds/contributeur.html | Référence |
| Fiche livre (*Le Guide de la Permaculture*) | https://pcd-equipe.github.io/pcd-embeds/fiche-livre.html | Périmée (bandeau) |
| Page auteur du livre | https://pcd-equipe.github.io/pcd-embeds/livre-auteur.html | Périmée (bandeau) |
| Carte compacte (livre) | https://pcd-equipe.github.io/pcd-embeds/carte-compacte.html | Périmée (bandeau) |

Les maquettes livre ont été remplacées par le template Bricks de la fiche livre (dépôt `pcd-site`).
Elles restent en ligne parce que les onglets Rendu des CPT Livres et Auteurs les intègrent encore.

Retirées le 5 octobre 2026 (copies dans `pcd-site/docs/historique/maquettes-pcd-embeds/`) :
`variete/` (CPT Variétés abandonné) et `contributeur-print.html` (intégré nulle part).

> Le **Glossaire**, la **Toilette**, la **Plante** et la **Vidéo** utilisent le format « design system » de Claude design
> (composants React chargés depuis le CDN unpkg au runtime), chacun dans son dossier avec `_ds/` et `support.js`.
> Il faut une connexion internet pour les afficher (pas de souci dans un embed Notion).

> Les images de chaque création sont rangées dans `assets/<création>/` pour
> éviter toute collision de noms entre fiches.

> 🔗 **Ces URLs sont définitives** : une mise à jour du contenu ne change PAS
> l'URL. Notion affiche automatiquement la nouvelle version.

---

## 🔁 Mettre à jour une création (workflow automatique)

1. Dans **Claude design** : modifie la création, puis **Share → Export →
   Project archive (.zip) → Download**.
2. Dépose le `.zip` dans le dossier Dropbox :
   `09. Site, contenus & RAG / 01. Contenus / pcd-embeds / _inbox/`
3. Demande à Claude Code : **« mets à jour <nom de la création> »**.

Claude se charge alors de : dézipper → garder le HTML + `assets/` (compresser
les images lourdes) → committer → pousser sur GitHub. En ligne ~1 min plus tard,
**même URL**.

## ➕ Ajouter une nouvelle création

Même principe : dépose le `.zip` dans `_inbox/` et dis à Claude
« publie la nouvelle création <nom> ». Claude crée le fichier `<nom>.html` +
ses assets et te donne la nouvelle URL d'embed (à coller une fois dans Notion).

## ✏️ Modifier directement sur GitHub (option ponctuelle)

Pour une petite retouche texte sans repasser par Claude design :
ouvre le fichier `.html` sur GitHub → icône **crayon** ✏️ → modifie →
**Commit changes**. En ligne en ~1 min.

---

## Notes techniques

- `.nojekyll` : sert les fichiers tels quels (pas de traitement Jekyll).
- `_inbox/` : boîte de réception des exports `.zip` — **exclue du dépôt**
  (voir `.gitignore`), ne sera jamais publiée.
- Les images sont dans `assets/` et référencées en chemins relatifs.
- Dépôt **public** = GitHub Pages gratuit.
- Outil de publication : `gh` (GitHub CLI), authentifié sur le compte **PCD33**.
