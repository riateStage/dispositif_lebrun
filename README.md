# Analyse des dispositifs de soutien des marchés immobiliers résidentiels en France depuis 2003

- Pierre Le Brun, février-juin 2020
- Direction de stage : Renaud Le Goix (UMR Géographie-Cités, UMS RIATE) 
- Encadrement : Thibault Le Corre (UMR Géographie-Cités) et Ronan Ysebaert (UMS RIATE)

## Objet du stage

Ce stage s’inscrit dans le premier axe du projet WIsDHoM, consacré à la construction sociale des marchés immobiliers par les acteurs publics et privés et piloté, pendant la durée de ce stage, par Thibault Le Corre (de l’UMR Géographie-Cité). L’objectif de ce travail était d’initier une réflexion sur la place des dispositifs de soutien aux – et d’encadrement des – marchés immobiliers. En particulier, l’élaboration d’une base de données spatialisée sur ces dispositifs permettant de localiser leurs périmètres dans l’espace et dans le temps pour chacun des trois terrains de l’ANR. L’ensemble des traitements ont été menés sur le logiciel R. Le code, les sources et la description des étapes sont ici précisément documentés. Ils permettront aux personnes familières de cette grammaire de retracer plus précisément le fil des opérations.


## Mémoire accessible [ici](Memoire_Pierre_Le-Brun.pdf)

## Organisation du dépôt

* L'ensemble de la chaine de traitement mobilisée est résumée [ici](https://riatestage.github.io/dispositif_lebrun/)

* fig contient deux graphiques représentant les trajectoires des communes de chaque FUA dans le classement A/B/C (Traj_ABC.png) et en terme d’éligibilité aux aides fiscales à l’investissement locatif (Traj_AFIL.png). 
Il contient également les cartes produites pour chacune des trois FUA, qui possèdent chacune un sous-dossier. Chaque sous-dossier est organisé comme suit :

* ‘2019’ contient quatre (Avignon) ou cinq cartes (Lyon et Paris) en format PNG permettant de synthétiser la situation de chaque territoire en 2019 :
-‘123’ : cartographique du zonage 1/2/3.
-‘ABC’ : zonage A/B/C.
-‘DI’ : dispositifs infra-communaux (TVA réduite pour Paris et Avignon + secteurs mixité sociale pour Lyon).
-‘DNC’ : dispositifs nationaux à l’échelon communal (Pinel, PTZ, APL, Denormandie)
-‘DLC’ [Paris et Lyon seulement] : dispositifs locaux à l’échelon communal.

* ‘Historique’ contient deux planches en format PDF :
  -‘ABC’ : retrace l’évolution du zonage A/B/C depuis sa création en 2003.
  -‘AFIL’ : évolution de l’éligibilité aux dispositifs d’aides fiscales à l’investissement locatif depuis que celle-ci a été restreinte à certaines zones, donc depuis 2009
  -‘TVA’ : évolution de l’éligibilité à la TVA réduite à 5,5% pour la construction de logements en accession.

* ‘Intermediate’ contient des bases intermédiaires utilisées dans l’élaboration des outputs. L’organisation de ce dossier est plus amplement détaillée dans le fichier ‘Dispositifs.html’. 

* ‘Output’ contient les bases finales produites et mobilisables par les autres membres de l’ANR.
  - ‘France’ contient les historiques des classements ABC et 123 sur la France entière.
  - ‘Paris’, ‘Lyon’ et ‘Avignon’ contiennent respectivement :
    * ‘Dispositifs_[FUA].xlsx’ : pour chaque FUA, ensemble des classements ABC et 123 année par année + participation au programme Action cœur de ville (ACV) à partir de 2019 + année de l’agrément préfectoral pour accéder à l’aide fiscale à l’investissement locatif pour les communes qui l’ont obtenu + population au dernier recensement (2016). Chaque fichier comporte deux feuilles :
        - ‘Brut’ comporte l’ensemble des codes communaux année par année. Les communes issues de fusion possèdent donc autant de lignes que de composantes.
        - ‘Def’ : chaque commune de 2019 n’apparaît qu’une seule fois. Dans le cas où il s’agit d’une commune fusionnée dont les communes d’origine possédaient des classements différents, les deux sont concaténés (cf. la fonction « comix » élaborée par Ronan Ysebaert).
    * ‘[FUA]_TVA.gpkg’ : recense les secteurs du programme national pour la rénovation urbaine (PNRU) et les quartiers prioritaires des politiques de la ville (QPV) – avec indication de ceux intégrés au nouveau programme pour la rénovation urbaine (NPNRU). Le fichier se compose de deux couches :
        - ‘PNRU_Fu’ : contient les découpages des secteurs du PNRU, avec leur nom, le numéro de leur convention, l’année de signature et l’année de fin du contrat.
        - ‘QPV_Fu’ : contient les découpages des QPV, avec leur code, leur nom et un champ indiquant s’il s’agit d’un secteur du NPNRU.


Toutes ces informations servent notamment à construire l'application shiny accessible [ici](https://github.com/riateStage/dispositif_lebrun_shiny)


## Application shiny

Ce travail a donné lieu à la réalisation d'une application shiny pour synthétiser et diffuser le volume de données mobilisées dans ce projet, documenté et accessible [ici](https://github.com/riateStage/dispositif_lebrun_shiny) 
