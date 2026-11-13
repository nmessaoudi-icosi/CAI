# Observatoire SI-HCPN — interface française

Version statique du tableau de bord ICOSI, prévue pour https://nmessaoudi-icosi.github.io/CAI/.

## Activer la publication
Dans le dépôt CAI, ouvrir **Settings → Pages → Build and deployment → Source → GitHub Actions**.
Dans **Actions → Publier l’observatoire SI-HCPN → Run workflow**, sélectionner `main` et lancer le workflow si nécessaire.
L’URL est utilisable seulement après une exécution réussie du déploiement.

## Développement
Node.js 22.13 ou plus récent :
```
cd observatoire
npm ci
npm test
npm run dev
npm run build
```

## Données et limites
- Interface publique ; aucune connexion ChatGPT requise sur GitHub Pages.
- Aucune donnée expérimentale réelle incluse : démonstration explicitement fictive.
- Imports CSV/JSON/ZIP traités dans le navigateur ; les sessions sont stockées localement et exportables en JSON. Les données de l’ancien domaine ne sont pas transférées automatiquement : exporter puis restaurer la session.
- RF reste la référence valide. N/D signifie absent/non calculé, jamais zéro.
- Les totaux par actif proviennent de `asset_totals.csv` (asset,discharge,shift). Les traces cumulatives brutes ne sont pas additionnées automatiquement.
- `metrics.csv` : f1,precision,recall,auc,peaks,ens,ome,shift. Scores dans [0,1].
- `sgrid_history.csv` : step,demand,supply,v2gdischarge.
- `final_sgrid.csv` : dernière ligne de l’état final.
- Rapport PDF via l’impression du navigateur (Enregistrer au format PDF).
- Classement : poids modifiables, normalisation min–max, exécutions complètes seulement ; même scénario et nombre de pas requis. La méthodologie complète est accessible dans l’interface.

Le tableau de bord ne constitue pas un dépôt des artefacts expérimentaux de l’article.
