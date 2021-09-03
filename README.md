# Analyse des dispositifs de soutien des marchés immobiliers résidentiels en France depuis 2003

Pierre Le Brun, février-juin 2020
Direction de stage : Renaud Le Goix
Encadrement de stage : Ronan Ysebaert


## Mémoire accessible [ici](Memoire_Pierre_Le-Brun.pdf)

## Organisation du dépôt

### Analyse des dispositifs de marché

* L'ensemble de la chaine de traitement mobilisée est résumée ici

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



