# Sub Sound-Conversion
Convertissons 4 boites de transport en merisier baltique de lasers femtoseconde Lituanniens (Light Conversion) en subwoofers!

## Objectifs
- Obtenir des basses plus profondes que le Kubo le permet
- Avoir des enceintes efficaces
- Permettre le transport à vélo


## Matériaux
Les dimensions des boites sont contenues dans le fichier `boite_lightcon_C231999.FCStd` (voir le tableur `dim` à l'intérieur). Ce fichier peut être ouvert avec [FreeCAD](https://www.freecad.org/). Les dimensions des panneaux et autres morceaux des boites sont dans un des onglets du fichier `boxplan.xls`. Une photo des boites se trouve dans le fichier `boite.jpg`

## Moteur

Pour l'instant, la conception s'articule autour du Dayton PA310 dont la feuille de spécification se trouve dans `\Datasheets`.

## Concepts

Nous basons notre conception sur le [POC7 de Brian Steele](https://www.diysubwoofers.org/projects/other/POC7/) modifié pour faciliter la construction avec les matériaux disponibles. Nous utilisons un version modifiée d'un tableur excel qu'il a construit (`boxplan.xls`) pour planifier les découpes et l'assemblage.

## Simulations
Une fois la conception faites, les paramètres électroacoustiques sont importés dans HornResp. Le fichier contenant les dernières simulations est dans `Simulations\hornresp_sound_conversion.txt`
