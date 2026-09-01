# BET-Suite — mises à jour

Hébergement des **binaires de mise à jour** et du **feed** de BET-Suite (GitHub
Releases — gratuit, sans billing R2).

- `feed.json` (branch `main`) : décrit la dernière version publiée.
  Le Worker Cloudflare (`bet-suite-licence`) sert ce fichier sur
  `/update/feed`.
- Binaires : pièces jointes des **Releases GitHub** (liens stables
  `…/releases/download/<tag>/BET-Suite-<version>.exe`).

## Publier une mise à jour

1. Générer le nouvel exécutable (`pyinstaller betsuite.spec`).
2. Créer la Release avec le binaire :
   ```
   gh release create v0.4.1 "dist\BET-Suite.exe#BET-Suite-0.4.1.exe" \
     --repo zakihm122/bet-suite-updates --title "BET-Suite 0.4.1"
   ```
3. Calculer le SHA256 du binaire et mettre à jour `feed.json`
   (version > version courante pour déclencher l'app), puis pousser `main`.
