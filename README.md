# Radar Emploi

Carte interactive mondiale des annonces **en cours** liées à la cartographie / SIG / géomatique
(offres d'emploi et appels d'offres), France (métropole + DOM-TOM) et international, repérées
par une veille automatisée quotidienne.

**Démo en ligne :** https://geomarksig.github.io/Radar_Emploi/
_(actif dès que GitHub Pages est activé sur ce dépôt — Settings → Pages → Deploy from a branch → `main` / `/ (root)`)_

## Ce que ça fait

- Regroupe des annonces d'emploi (CDI, CDD, volontariat, freelance, stage, apprentissage)
  et des appels d'offres liés à la cartographie/SIG/géomatique, en France (métropole et
  DOM-TOM) et à l'international — sans distinction de priorité géographique.
- Les positionne sur une carte (fond plan / imagerie satellite Esri), avec regroupement
  automatique des points proches qui se séparent progressivement au zoom.
- **Recherche par mot-clé** (intitulé, employeur, ville, pays, source) et filtre par type
  de contrat.
- Fiche détail au clic : intitulé, employeur, lieu, type de contrat, source, **date de
  publication**, lien direct vers l'annonce d'origine.
- **Seules les annonces confirmées en cours et datées sont publiées** — rien d'expiré ou
  de non daté n'apparaît ici (ni dans la page, ni dans les données embarquées).

## Projet indépendant

Radar Emploi est un projet à part entière, sans lien technique avec d'autres services de
veille privés de [Geomark SIG Solutions](https://github.com/GeomarkSIG) (qui maintient ce
dépôt) : données, historique et routine de mise à jour propres, entièrement séparés.

## Pile technique

Page statique unique (`index.html`), aucune dépendance serveur :

- [Leaflet](https://leafletjs.com/) + [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster)
  pour la carte et le regroupement par zoom.
- Fonds de carte [Esri](https://www.esri.com/) (plan et imagerie satellite), données
  cartographiques de base [OpenStreetMap](https://www.openstreetmap.org/copyright).
- Données embarquées directement dans la page (pas d'API, pas de base de données).

## Mise à jour

La carte est régénérée et republiée chaque jour par une routine automatisée (scripts Python
`build_radar_data.py` → `render_radar.py`, non inclus dans ce dépôt public — ils lisent un
fichier de suivi privé, hors dépôt). Le fichier `index.html` de ce dépôt est le résultat déjà
généré, prêt à héberger tel quel.

## Licence

[MIT](./LICENSE) — Robin Maume / Geomark SIG Solutions.
