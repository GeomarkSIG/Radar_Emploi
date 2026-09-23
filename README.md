# Radar Emploi Geomark

Carte interactive mondiale des annonces **en cours** liées à la cartographie / SIG / géomatique
(offres d'emploi et appels d'offres), repérées par une veille automatisée quotidienne.

**Démo en ligne :** https://geomarksig.github.io/Radar_Emploi/
_(actif dès que GitHub Pages est activé sur ce dépôt — Settings → Pages → Deploy from a branch → `main` / `/ (root)`)_

## Ce que ça fait

- Regroupe des annonces d'emploi (CDI, CDD, volontariat, freelance, stage, apprentissage)
  et des appels d'offres liés à la cartographie/SIG/géomatique, en France (métropole et
  DOM-TOM) et à l'international.
- Les positionne sur une carte (fond plan / imagerie satellite Esri), avec regroupement
  automatique des points proches qui se séparent progressivement au zoom.
- Filtre par type de contrat.
- Fiche détail au clic : intitulé, employeur, lieu, type de contrat, source, **date de
  publication**, lien direct vers l'annonce d'origine.
- **Seules les annonces confirmées en cours et datées sont publiées** — rien d'expiré,
  d'écarté ou de non daté n'apparaît ici (ni dans la page, ni dans les données embarquées).

## Deux volets

Ce projet a deux facettes :

1. **Cette carte publique** — un radar ouvert, mis à jour chaque jour, sur toutes les
   annonces cartographie/SIG/géomatique repérées par la veille, en France et dans le monde.
2. **Une veille personnalisée privée**, propre à [Geomark SIG Solutions](https://github.com/GeomarkSIG) :
   un rapport quotidien plus ciblé (priorité Réunion/Mayotte, appels d'offres France, options
   secondaires métropole), avec vérification détaillée annonce par annonce. Ce volet reste
   un service interne, non publié dans ce dépôt.

## Pile technique

Page statique unique (`index.html`), aucune dépendance serveur :

- [Leaflet](https://leafletjs.com/) + [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster)
  pour la carte et le regroupement par zoom.
- Fonds de carte [Esri](https://www.esri.com/) (plan et imagerie satellite), données
  cartographiques de base [OpenStreetMap](https://www.openstreetmap.org/copyright).
- Données embarquées directement dans la page (pas d'API, pas de base de données).

## Mise à jour

La carte est régénérée et republiée automatiquement chaque jour par la veille (script Python
`build_carte_data.py` → `render_carte_public.py`, non inclus dans ce dépôt public). Le fichier
`index.html` de ce dépôt est le résultat déjà généré, prêt à héberger tel quel.

## Confidentialité des données

Les données proviennent d'une veille automatisée (recherche + vérification) sur un ensemble
de sites d'emploi et de portails de marchés publics. Seul un statut générique est publié
(« En cours ») — le détail du raisonnement de veille et toute note interne sont filtrés avant
publication.

## Licence

[MIT](./LICENSE) — Robin Maume / Geomark SIG Solutions.
