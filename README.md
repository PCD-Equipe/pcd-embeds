# pcd-embeds — Créations HTML pour Notion

Pages HTML autonomes hébergées sur **GitHub Pages**, intégrées dans Notion via
des blocs `/embed`. Chaque création (issue de Claude design) = un fichier HTML +
ses images dans `assets/`.

- **Dépôt :** https://github.com/PCD-Equipe/pcd-embeds
- **Site :** https://pcd-equipe.github.io/pcd-embeds/

## Créations en ligne

| Création   | URL à coller dans Notion (`/embed`)                          |
|------------|--------------------------------------------------------------|
| Fiche livre — *Le Guide de la Permaculture* | https://pcd-equipe.github.io/pcd-embeds/fiche-livre.html |
| Page auteur du livre | https://pcd-equipe.github.io/pcd-embeds/livre-auteur.html |
| Carte compacte (livre) | https://pcd-equipe.github.io/pcd-embeds/carte-compacte.html |
| Fiche recette — *Crukies* | https://pcd-equipe.github.io/pcd-embeds/fiche-recette.html |
| Contributeur | https://pcd-equipe.github.io/pcd-embeds/contributeur.html |
| Glossaire | https://pcd-equipe.github.io/pcd-embeds/glossaire/ |
| Fiche plante — *Tomate* (3 colonnes) | https://pcd-equipe.github.io/pcd-embeds/plante/ |
| Vidéo (4 maquettes) | https://pcd-equipe.github.io/pcd-embeds/video/ |
| Toilette — *TLB* | https://pcd-equipe.github.io/pcd-embeds/toilette/ |
| Fiche variété — *Cœur de Bœuf* (côte à côte) | https://pcd-equipe.github.io/pcd-embeds/variete/ |
| Simulateur assainissement | https://pcd-equipe.github.io/pcd-embeds/simulateur-assainissement.html |

> ⚙️ Le **Glossaire** utilise le nouveau format « design system » de Claude design
> (composants React chargés depuis le CDN unpkg au runtime). Il vit dans son propre
> dossier `glossaire/` avec ses dépendances (`_ds/`, `support.js`).
> Nécessite une connexion internet pour s'afficher (OK dans un embed Notion).
| Contributeur — version impression | https://pcd-equipe.github.io/pcd-embeds/contributeur-print.html |

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
