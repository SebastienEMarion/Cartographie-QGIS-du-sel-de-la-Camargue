# Cartographie QGIS de la Camargue (NDSI) :
Cartographie QGIS de la salinité de la Camargue, utilisant des données du satellite Sentinel-2 de l'Agence Spatiale Européenne (ESA) pour représenter l'indice de salinité par différence normalisée (NDSI), données datant de janvier 2026. La topographie provient d'OpenStreetMap (OSM).

<img width="3507" height="2480" alt="image" src="https://github.com/user-attachments/assets/06112582-a685-42c6-911a-98a17e75cd1b" />

# L'indice de salinité par différence normalisée (NDSI) en _remote sensing_ (télédétection)
L'indice de salinité par différence normalisée est une technique de télédétection, qui sert à superposer sur un système de géolocalisation mondiale, différentes couches issues de missions effectuées par des satellites. Sur celui utilisé pour cette cartographie de la salinité de la Camargue, en février 2026, c'est le satellite Sentinel-2 de l'Agence Spatiale Européenne (ESA) qui est utilisé. La mission spécifique est Sentinel-2 L2A. D'après sa documentation [2], "_Dédié à fournir des données pour les services Copernicus, Sentinel-2 est équipé d'un assortiment de technologies, comme des caméras multi-spectrales pour la surveillance terrestre, océanique et atmosphérique. Il délivre des images optiques en haute résolution pour le suivi terrestre, la réponse d'urgence et les services de sécurité. L'imageur multi-spectal donne un ensemble versatile de 13 bandes spectrales allant du visible et du proche infrarouge aux ondes courtes infrarouge._".

Ici, deux bandes sont utilisées [2] :

| Nom | Description | Résolution |
|-----|-------------|------------|
| B04 | Red, 664.6 nm (S2A), 665.0 nm (S2B) | 10 m |
| B08 | NIR, 832.8 nm (S2A), 833.0 nm (S2B) | 10 m |

Et la formule suivante : <br />
$\mathrm{NDSI} = \frac{B_8 - B_4}{B_8 + B_4}$ [3, 4]

Cette équation n'est qu'une des variétés possibles. Par ailleurs l'usage de ce type d'indice possède des avantages inhérents. "_Les stations de surveillance au sol peuvent éviter des coûts en main d'œuvre, mais impliquent des limites, comme des étendues de surveillance réduites et des coûts élevés. Récemment, la télédétection satellite a émergé comme méthode pour une surveillance quantitative comme qualitative de surveillance de la salinisation des sols grâce à ses avantages uniques, comme la capacité de couvrir de larges zones, d'offrir diférents types de produits de données, l'accessibilité, un faible coût économique, et la possibilité d'une cartographie convéniente. (Cao et al., 2022). La salinité du sol varie avec l'irrigation, la précipitation, l'évaporation, la fertilisation [...], résultant un en mouvement horizontal et vertical du sol (Tibhirine et al., 2023)._" [1]

Le NDVI (indice de végétation par différence normalisée) semble correspondre à cette équation [6] aussi. "Le NDVI (Normalized Difference Vegetation Index) ou indice de végétation, est construit à partir des canaux rouges et proche infrarouge. Il met en valeur la différence entre la bande visible du rouge et celle du proche infrarouge pour mettre en valeur l’intensité des espaces chlorophylliens." On peut donc en conclure que les deux indices peuvent être utilisés conjointement selon que la surface étudiée est un corps d'eau ou une étendue où de la végétation peut pousser. En effet, les deux pourraient être corrélés en les sansouïres mentionnées dans la partie suivante. 

# Intérêt de la cartographie de la salinité en Camargue

Dans un contexte de changement climatique, l'élévation des eaux est un aléa complexe. Comme l'eau salée monte, elle pénètre les aquifères, réduisant les réserves d'eau douce pour les populations. Par ailleurs, la Camargue est un territoire particulier car une activité de riziculture s'y est développée, riziculture menacée par la pénétration du biseau salé. Sans compter les adaptations biologiques particulières au milieu du marais salin, qui font partie du patrimoine régional : le tauros et les chevaux. Il en va aussi de la flore, car dans le schorre camarguais la salicorne, la soude et la saladelle sont des espèces qui apprécient la présence salée. On les dit halophytes. "L’aggravation de cette situation est inscrite dans les prévisions climatiques jusqu’en 2100." [5]

# Bibliographie : 
* [1] Xin Cui, Wenting Han, Huihui Zhang, Yuxin Dong, Weitong Ma, Xuedong Zhai, Liyuan Zhang, Guang Li,
« Estimating and mapping the dynamics of soil salinity under different crop types using Sentinel-2 satellite imagery »,
_Geoderma_, Volume 440, 2023, 116738, ISSN 0016-7061, https://doi.org/10.1016/j.geoderma.2023.116738. (https://www.sciencedirect.com/science/article/pii/S0016706123004159)

* [2] "Sentinel-2 L2A",
_Sentinel Hub_, (https://docs.sentinel-hub.com/api/latest/data/sentinel-2-l2a/)

* [3] "Normalized Difference Salinity Index | Calculate NDSI (Salinity) in QGIS & ArcMap",
_Dawn Of Geospatial World_, 25 septembre 2023 (https://www.youtube.com/watch?v=KmFXmDo1ekc)

* [4] Khan, N.M., Rastoskuev, V.V., Shalina, E.V. and Sato,Y. (2001), <br />
"Mapping Salt-Affected Soils Using Remote Sensing Indicators—A Simple Approach with the Use of GIS IDRISI". <br />
_Proceedings of the 22nd Asian Conference on Remote Sensing_, 5-9 November 2001, Singapore. Center for Remote Imaging, Sensing and Processing (CRISP), National University of Singapore; Singapore Institute of Surveyors and Valuers; Asian Association on Remote Sensing, 5 p.

* [5] Bruno CINOTTI (IGEDD), Bruno DEPRESLE (IGEDD), Christophe PATIER (CGAAER),<br />
"L’adaptation de la Camargue au changement climatique - Améliorer la gouvernance pour prendre en charge les dérèglements",<br />
17 novembre 2023, _Ministère de l'Agriculture, de l'Agro-alimentaire et de la Souveraineté alimentaire_ (https://agriculture.gouv.fr/ladaptation-de-la-camargue-au-changement-climatique-ameliorer-la-gouvernance-pour-prendre-en-charge)

* [6] Hervé PARMENTIER,
"[invité] Calcul d’indices avec QGIS sur image Sentinelle 2A. De l’indice de végétation (NDVI) à celui de la construction de différence normalisée (NDBI)",<br />
17 janvier 2022 |_ Cartographie et SIG, QGIS_, _NaturaGIS_ (https://naturagis.fr/cartographie-sig/imageries-sentinelles-collectes-et-calculs-dindices-de-vegetation/)
