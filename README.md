# Radar Emploi Geomark

Carte interactive mondiale des annonces liées à la cartographie / SIG / géomatique
(offres d'emploi et appels d'offres), repérées par une veille automatisée quotidienne.

**Démo en ligne :** _(lien GitHub Pages à ajouter une fois activé — Settings → Pages → branch `main` /root)_

## Ce que ça fait

- Regroupe des annonces d'emploi (CDI, CDD, volontariat, freelance, stage, apprentissage)
  et des appels d'offres liés à la cartographie/SIG/géomatique, en France et à l'international.
- Les positionne sur une carte (OpenStreetMap / imagerie satellite Esri), avec regroupement
  automatique des points proches qui se séparent au zoom.
- Filtres indépendants : ancienneté de l'annonce (aujourd'hui, J-1…J-6, 8-15j, 16-30j, +30j),
  statut (en cours / expirée / écartée / non datée), type de contrat.
- Fiche détail au clic : intitulé, employeur, lieu, type, source, date de repérage, lien direct
  vers l'annonce d'origine.

## Pile technique

Page statique unique (`index.html`), aucune dépendance serveur :

- [Leaflet](https://leafletjs.com/) + [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster)
  pour la carte et le regroupement par zoom.
- Fonds de carte [OpenStreetMap](https://www.openstreetmap.org/copyright) et
  [Esri World Imagery](https://www.esri.com/).
- Données embarquées directement dans la page (pas d'API, pas de base de données).

## Données

Les données sont produites par une veille automatisée (recherche + vérification manuelle
assistée) sur un ensemble de sites d'emploi et de portails de marchés publics. Le statut
affiché publiquement est simplifié (en cours / expirée / écartée / non datée) : le détail
du raisonnement de veille (notes internes) n'est pas publié ici.

## Licence

[MIT](./LICENSE) — Robin Maume / Geomark SIG Solutions.
