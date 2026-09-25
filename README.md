# Radar Emploi SIG & Géomatique

Carte interactive des offres **en cours** en cartographie, SIG, géomatique et télédétection :
emplois (CDI, CDD, intérim, stage, alternance, VSC/VIE/VIA, freelance) et appels d'offres, en
France (métropole et DOM-TOM) et à l'international. Mise à jour chaque jour.

**Carte en ligne : https://geomarksig.github.io/Radar_Emploi/**

## Utilisation

1. Cliquez un **point numéroté** pour déplier les annonces d'un même lieu. Il reste déplié
   tant que vous ne cliquez pas un autre point numéroté, ne dézoomez pas ou ne changez pas de filtre.
2. Cliquez une annonce pour ouvrir sa fiche : intitulé, employeur, commune, type de contrat,
   salaire quand il est indiqué, source, date de repérage et **lien direct vers l'annonce**.
3. **Filtrez par type de contrat** (boutons *Tout cocher* / *Tout décocher*) ou **cherchez un
   mot-clé** (intitulé, employeur, ville, pays, source).
4. Basculez entre fond *Plan* et *Satellite*.

## Ce qui est publié

- Uniquement des annonces **confirmées en cours** : une annonce fermée, pourvue ou dont la date
  limite est dépassée est retirée. L'ancienneté seule n'exclut pas une annonce.
- Chaque point est placé sur la **commune** de l'annonce (géocodage officiel geo.api.gouv.fr pour
  la France), pas sur le chef-lieu du département.
- Le type de contrat est lu sur la fiche d'origine ; « Autre / à préciser » ne regroupe que les
  annonces qui ne l'indiquent pas.
- Sont pris en compte les postes dont le contenu est réellement géospatial (SIG, cartographie,
  géomatique, télédétection, webmapping). La topographie pure n'est pas retenue.

## Sources

France Travail, LinkedIn, Hellowork, Apec, Cadremploi, Glassdoor, Indeed (France et Belgique),
Jobijoba, Emploi-territorial, Emploi-environnement, GeoRezo, BOAMP et Banque mondiale (appels
d'offres), Civiweb (VIE/VIA), CGF Tahiti (Polynésie française) et geomatik.ch (Suisse).
La Nouvelle-Calédonie et la Polynésie sont aussi recherchées, mais très peu d'annonces y sont
publiées. Certains sites (Jooble, parfois Glassdoor et Indeed Belgique) bloquent l'accès
automatisé et ne sont donc pas couverts en continu.

## Pile technique

Page statique unique (`index.html`), sans serveur ni base de données :

- [Leaflet](https://leafletjs.com/) et [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster)
  pour la carte et le regroupement des points.
- Fonds de carte [Esri](https://www.esri.com/) (plan et imagerie), données de base
  [OpenStreetMap](https://www.openstreetmap.org/copyright).
- Données embarquées dans la page ; polices Montserrat et IBM Plex (Google Fonts).
- Dossier `assets/` : logo et bandeau Geomark Solutions SIG.

## Mise à jour

La page est régénérée et republiée chaque jour par une routine automatisée (scripts Python
qui construisent les données puis produisent `index.html`). Les scripts et le fichier de suivi
ne sont pas dans ce dépôt : `index.html` est le résultat prêt à héberger.

## Licence

[MIT](./LICENSE) — Robin Maume / Geomark Solutions SIG.
