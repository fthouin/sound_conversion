# Sub Sound-Conversion
Convertissons 4 boites de transport en merisier baltique de lasers femtoseconde Lituanniens (Light Conversion) en subwoofers!

## Objectifs
- Obtenir des basses plus profondes pour bien rendre la diversité de styles musicaux du collectif Cocktail Sonore
- Avoir des enceintes efficaces pour permettre l'utilisation de batteries
- Permettre le transport à vélo
- Donner une nouvelle vie à des matériaux usagés


## Matériaux
Les dimensions des boites sont contenues dans le fichier `boite_lightcon_C231999.FCStd` (voir le tableur `dim` à l'intérieur). Ce fichier peut être ouvert avec [FreeCAD](https://www.freecad.org/). Une photo des boites se trouve dans le fichier `boite.jpg`

## Moteur

La conception s'articule autour du [Eminence 12LFA](https://eminence.com/products/delta_12lfa) dont la feuille de spécification se trouve dans `\Datasheets`.

## Concept original

Nous basons notre conception sur le [POC7 de Brian Steele](https://www.diysubwoofers.org/projects/other/POC7/) modifié pour faciliter la construction avec les matériaux disponibles

## Modèles

Les modèles de conception et de fabrication sont contenus dans le fichier FreeCAD V1 `./Simulations/gfold.FCStd`. Les paramètres ajustables du modèle se trouvent dans le chiffrier `dims` du fichier. Les dimensions internes, le rapport entre la hauteure des premières et deuxièmes segments du chemin acoustique pliés et la hauteure totale de la boite ainsi que le décalage du driver par rapport au premier plis du tube peuvent être ajustés pour optimiser les performances acoustiques.

### Simulations
 Dans ce fichier, le dossier Simulations contient un objet `soundpath`. Celui-ci contient un dessin de la cavité acoustique et des quatres segments (`sound_path_X`) qui la compose. Leur longueur est automatiquement calculée et transcrite dans le chiffrier `hornresp`. Ce classeur contient aussi l'aire des sections de ces segments, elles-aussi automatiquement calculées.

![soundpath]

Ces paramètres géométriques sont importés dans [HornResp](http://www.hornresp.net/) ainsi que les paramètres Thiele-Small du moteur. Le fichier contenant les dernières simulations est dans `Simulations\hornresp_sound_conversion.txt`

### Fabrication

Un modèle de la fabrication fidèle aux simulations est aussi automatiquement généré avec les paramètres entrées dans le chiffrier `dims`. Les dimensions qui en découlent se trouvent dans le chiffrier `bdim`. Les morceaux individuels se trouvent dans le dossier `Models` et sont importés dans `Assembly` pour le modèle d'assemblage. L'assemblage utilisent le module d'assemblage natif de FreeCad V1.

![assembly]

Des dessins techniques imprimables se trouvent dans le dossier `Drawings` du fichier. Ceux-ci sont automatiquement ajustés lorsque le modèle est changé. Ceux-ci décrivent les dimensions des matériaux originaux, les plans de coupe ainsi que les plans d'assemblage.

## Performance

### Simulations

Les performances attendues après avoir optimisé le concept sont présentées ci-dessous. Les paramètres de la simulation utilisé sont d'abord présentés. Ceux-ci considère le volume occupé par les supports et poutres dans les sections du chemin acoustique en soustrayant leur aire à l'aire calculée dans le chiffrier `hornresp` du fichier CAD. L'amplitude du signal est choisie pour garder l'excursion du moteur sous sa limite linéaire (Xmax=4.8mm) 

![parameters]

Le système simulé est schématisé ici:

![schematic]

L'impédance acoustique et électrique vue du driver:

![acoustic_impedance]
![electrical_impedance]

Afin de protéger le moteur de sur-excursions et de l'intégrer dans un système de son complets, un filter électronique en amont du subwoofer doit être conçu et utilisé. Nous avons posé la limite d'excursion maximale à celle du seuil de non-linéarité du manufacturier (Xmax=4.8mm).

![filter]

Le spectre d'excursion sans et avec filtre électronique en amont:

![displacement_filteroff]
![displacement_filteron]

Le spectre de puissance acoustique combiné du driver et de la flute de résonnance sans et avec filtre électronique en amont:

![acoustic_power_filteroff]
![acoustic_power_filteron]

Le spectre de phase combiné du driver et de la flute de résonnance sans et avec filtre électronique en amont:

![acoustic_phase_filteroff]
![acoustic_phase_filteron]

Le délai de vitesse de groupe sans et avec filtre électronique en amont:

![group_delay_filteron]
![group_delay_filteroff]

[soundpath]: pictures/soundpath.png "Sound path calculated in the CAD model"
[assembly]: pictures/cad_assembly.png "Assembly model"
[parameters]: Simulations/parameters.png "Parameters of HornResp simulation"
[schematic]: Simulations/schematic.png "Schematic of HornResp simulation"
[acoustic_impedance]: Simulations/acoustic_impedance.png "Simulated acoustic impedance of HornResp simulation"
[electrical_impedance]: Simulations/electrical_impedance.png "Simulated electrical impedance of HornResp simulation"
[filter]: Simulations/filter.png "Electronic filter characteristics"
[acoustic_power_filteron]: Simulations/acoustic_power_filteron.png "Simulated acoustic power with filter"
[acoustic_power_filteroff]: Simulations/acoustic_power_filteroff.png "Simulated acoustic power without filter"
[displacement_filteroff]: Simulations/displacement_filteroff.png "Simulated acoustic power without filter"
[displacement_filteron]: Simulations/displacement_filteron.png "Simulated acoustic power with filter"
[acoustic_phase_filteron]: Simulations/acoustic_phase_filteron.png "Simulated acoustic phase with filter"
[acoustic_phase_filteroff]: Simulations/acoustic_phase_filteroff.png "Simulated acoustic phase without filter"
[group_delay_filteron]: Simulations/group_delay_filteron.png "Simulated acoustic group delay with filter"
[group_delay_filteroff]: Simulations/group_delay_filteroff.png "Simulated acoustic group delay without filter"
