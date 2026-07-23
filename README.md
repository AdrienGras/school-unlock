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
- La propagation peut prendre quelques secondes (le site contourne le cache du CDN
  GitHub, mais l'étudiant doit recharger la page).
- Ce dépôt est **public** : n'y écrire aucun secret, aucun commentaire confidentiel.
