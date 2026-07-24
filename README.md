# school-unlock

État des verrous du site de cours [school.adriengras.fr](https://school.adriengras.fr).

Le site lit `unlock.txt` au runtime. **Éditer ce fichier suffit à ouvrir ou fermer
un contenu — aucun rebuild, aucun redéploiement.**

## Comment ça marche

Une ligne = un chemin d'URL verrouillé, qui verrouille aussi tout ce qui est en
dessous. Une ligne commentée (`#`) ne verrouille rien. Un chemin absent est ouvert.

La liste des chemins disponibles est publiée par le site sur `/unlock-keys.json`.

## Précautions

- **Ce n'est pas un contrôle d'accès.** Le site est un export statique : le contenu
  d'une page verrouillée reste sur le serveur, joignable par URL directe pour qui
  sait la construire. Le verrou masque, il ne protège pas.
- La propagation prend jusqu'à ~90 s : le serveur du site interroge l'API GitHub
  toutes les ~90 s, écrit l'état localement et le sert à l'étudiant sans cache. Un
  changement est donc visible au prochain rechargement de page, dans la minute et demie.
- Ce dépôt est **public** : n'y écrire aucun secret, aucun commentaire confidentiel.
