<div align="center">

# ESR lexicon

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![Build Status](https://travis-ci.com/eonm-abes/esr-lexicon.svg?branch=master)](https://travis-ci.com/eonm-abes/esr-lexicon)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/Eonm/zotero/issues)
[![dependency status](https://deps.rs/repo/github/eonm/zotero/status.svg)](https://deps.rs/repo/github/eonm-abes/esr-lexicon)

</div>

ESR lexicon permet de constituer des dictionnaires d'entitées nommées relative aux structures de recherche françaises :

* Établissements de l'ESR (libéllés, sigles)
* Laboratoires de recherche (libéllés, sigles)
* Autres structure de recherche (libéllés, sigles)
* Écoles doctorales
* Noms et prénoms des chercheurs

ESR lexicon récupère ses informations depuis [HAL](https://api.archives-ouvertes.fr/search) et [ScanR](https://scanr.enseignementsup-recherche.gouv.fr).

## Usage

__En utilisant un fichier de configuration__

```sh
./esr-lexicon -c config.json
```

__En ligne de commande exclusivement__

```sh
./esr-lexicon -o scanr.structure.recherche -j '.["facet_groups"][0]["facets"]|map(.["name"])' -u "https://data.enseignementsup-recherche.gouv.fr/api/records/1.0/search/?dataset=fr-esr-repertoire-national-structures-recherche&rows=0&facet=libelle"
```

### Utilisation des expressions jq

ESR lexicon utilise des [expressions jq](https://stedolan.github.io/jq/manual/) pour extraire les données json. Pour constituer les dictionnaires ESR lexicon attend que l'expression jq utilisée retourne un tableau ou une chaine de cractères.
