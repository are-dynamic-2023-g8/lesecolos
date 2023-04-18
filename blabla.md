<h1 style="text-align: center;">Dynamique proie-prédateur</h1>
<h2 style="text-align: center;">Étude et modélisation numérique d'un système de Lotka-Volterra</h2>

---
&nbsp;&nbsp;&nbsp;&nbsp;La dynamique des populations est une branche de l’écologie mathématique qui s’intéresse  aux variations d’une population dans un milieu donné.  De nos jours, la surexploitation des ressources animales et halieutiques entraîne la raréfaction des espèces et mettent péril les écosystèmes. Ce domaine des sciences est donc crucial à la préservation de la faune et de la flore.

---

### Sommaire
* [Introduction](#introduction)
* [Plan d'étude](#plan-détude)
* [Conclusion](#conclusion)
* [Bibliographie](#bibliographie)

---
![predateur](https://www.agc3pa02.fr/uploaded/image/pra-dateur.jpg)



## Introduction 

---

&nbsp;&nbsp;&nbsp;&nbsp;En écologie, un écosystème est un ensemble de populations qui intéragissent entre elles. Il existe différents types de relation entre les espèces d'un même milieu : compétition, mutualisme, parasitisme etc.  

Le caractère quantitatif de ces phénomènes se manifeste dans les variations des nombres d’individus d’un écosystème. 

Il existe de nombreux modèles qui permettent de rendre compte de la réalité de ces fluctuations au cours du temps : Les premiers datent des années 1920 et sont basés sur des équations différentielles, c'est à dire des équations dont les inconnues sont des fonctions.

À chaque population correspond une équation dont les paramètres sont régis par leurs intéractions : taux de mortalité intrinsèque, taux de prédation etc. 

Ici nous nous intéressons à la prédation et aux conséquences de l'action directe ou indirecte de l'Homme sur les écosystèmes.

Dans quelle mesure les activités de l'Homme perturbent les écosystèmes?

---

## Plan d'étude

---

### Modèle d'un système proie-prédateur à deux espèces

---

<h3 style = "text-align : center;">Implémentation du modèle de Lotka-Volterra</h3>

Voici les équations différentielles du modèle que nous avons implémentées : 

$$
\frac{dx}{dt} = b x - h x y \\
\frac{dy}{dt} = \epsilon h x y - d y
$$

Elles sont initalisées par des paramétrées par les intéractions entre les deux populations (taux de prédation) mais aussi par des constantes intrinsèques à chaque espèces (taux de reproduction, taux de mortalité naturelle).

La première équation modélise l'évolution de la densité de population de la proie au cours du temps. La densité de proie augmente grâce au taux de reproduction de l'espèce mais diminue du fait de la prédation de l'espèce prédatrice.

La deuxième équation modélise l'évolution de la densité du prédateur au cours du temps. La densité de prédateur augmente grâce à la prédation de l'espèce sur la proie mais diminue du fait de son taux de mortalité naturelle.

Ainsi, les densités de population de la proie et du prédateur oscillent périodiquement au cours du temps, comme nous pouvons le voir sur le graphique suivant :

![graphe1](https://github.com/are-dynamic-2023-g8/lesecolos/blob/main/graphes/graphe1.png)

La densité de proie atteind un maximum, puis diminue à mesure que la population prédatrice la chasse, tandis que la densité de population prédatrice augmente en réponse à l'abondance de proies, ce qui conduit à une diminution subséquente de la population de proie. Cela crée un cycle proie-prédateur où les densités de population des deux espèces augmentent et diminuent en phases opposées.

L'interaction cyclique entre la population de proies et la population de prédateurs est représentée par cette boucle, dans l'état de phase. 

![graphe2](https://github.com/are-dynamic-2023-g8/lesecolos/blob/main/graphes/graphe2.png)

---

<h3 style = "text-align : center;">Équilibre du système de Lotka-Volterra</h3>

L'équilibre un état stable ou les densités de populations des espèces de l'écosystème n'évoluent pas au cours du temps. L'étude de l'équilibre permet de comprendre comment les populations réagissent aux perturbations ou comment l'action de l'Homme peut influencer les écosystèmes.

L'équilibre est atteint lorsque les dérivées de chacune des composantes du système s'annulent. En effectuant la simulation numérique avec une légère perturbation des valeurs d'équilibre, on remarque que l'équilibre est instable et converge vers un cyle limite. On en déduit que le système est sujet à des fluctuations intrinsèques et qu'il peut être difficle de maintenir les densités de population à un état stable.

![cyclelim](https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Poincar%C3%A9-Bendixon-%282%29.jpg/220px-Poincar%C3%A9-Bendixon-%282%29.jpg)

--- 

## Perturbation du modèle : introduction d'une espèce invasive

--- 
<h3 style = "text-align : center;">Qu'est ce qu'une espèce invasive?</h3>
Une espèce invasive est une espèce déplacée de son milieu d'origine et introduite dans un nouvel écosystème. Les espèces invasives prolifèrent souvent au détriment des espèces autochtones de l'écosystème dans lequel elle se sont établies par manque de prédateurs naturels ou de parasites dans ce nouveau milieu. Ceci peut entraîner la supplantation d'une ou de plusieurs espèces autochtones, voire leur extinction.

Sans intervention de l'Homme, ce genre de phénomène est extrêmement rare car l'équilibre entre les espèces d'un écosystème est établi. Depuis le développement de la chasse, l'agriculture et l'élevage et surtout de la mondialisation des échanges, l'Homme est devenu le principal vecteur de déplacements d'espèces. 

---

<h3 style = "text-align : center;">Mise en équation du modèle étendu</h3>
Nous avons étendu les équations du modèle en y ajoutant une espèce invasive :

$$
\frac{dx}{dt} = b x - h x y - k x z\\
\frac{dy}{dt} = \epsilon h x y - d y - l y z \\
\frac{dz}{dt} =  - m z + n y z
$$

En supposant que l'espèce introduite prédate à la même échelle les deux espèces autochtones, on obtient une évolution périodique des densités de population des trois espèces analogue au premier modèle.

![graphe3](https://github.com/are-dynamic-2023-g8/lesecolos/blob/main/graphes/graphe3.png)


En revanche, en modifiant les paramètres initiaux du système et en particulier le taux de prédation de l'espèce invasive sur chacune des deux espèces autochtones, on remarque que les conséquences sur les densités de population de chaque espèce sont drastiquement différentes.

Dans le cas ou l'espèce introduite ne prédate que la proie autochtone, les deux espèces prédatrices entrent en compétition. Lorsque le taux de prédation de l'espèce invasive sur la proie est suffisamment élevé, la population de proie autochtone diminue jusqu'à s'éteindre en raison de la pression de prédation accrue. En l'absence de sa source d'alimentation principale, l'espèce prédatrice n'est plus en mesure de se reproduire de manière viable et s'éteind. L'espèce invasive finira également par s'éteindre en l'absence de proie autochtone.

![graphe4](https://github.com/are-dynamic-2023-g8/lesecolos/blob/main/graphes/graphe4.png)

À l'inverse, si l'espèce invasive à un fort taux de prédation de l'espèce prédatrice autochtone comparativement à son taux de prédation sur la proie autochtone, la population de prédateur diminue ce qui entraîne une prolifération de la proie autochtone qui n'est plus régulée par son prédateur naturel. Dans le cas ou le taux de prédation de l'espèce invasive sur la proie autochtone est nul, la population de proie autochtone croît de manière exponentielle. L'espèce proie autochtone peut devenir à son tour une espèce invasive et mettre en péril d'autres écosystèmes, les activités de l'Homme ou causer un risque sanitaire comme la peste portée par le rat noir envahissant l'Europe au Moyen-Âge, ou le Chikungunya transmis aujourd’hui par le moustique tigre.

![[graphe5.png](https://github.com/are-dynamic-2023-g8/lesecolos/blob/main/graphes/graphe5.png)

---

<h3 style = "text-align : center;">Équilibre du modèle étendu</h3>

Dans le modèle à trois espèces, les populations oscillent au tour d'un point d'équilibre instable. Analytiquement, nous savons que l'équilibre est un point col, ce qui explique les variations brusque des densités de population des espèces en fonction des paramètres initiaux

---
<h3 style = "text-align : center;">Quelques exemples</h3>

Il existe malheureusement de nombreux exemples qui démontrent les effets destructeurs des espèces invasives introduites par l'Homme sur les écosystèmes :

La perche carnivore du Nil, introduite dans les années 1950 pour la pêche dans le lac Victoria, a en quelques décennies fait disparaître ou menacé d'extinction 200 des 300 espèces de petits poissons cichlidés du lac. Comme les cichlidés étaient herbivores, détritivores ou insectivores, l’écosystème entier a été bouleversé. 

<img src = "https://www.guidedesespeces.org/sites/zeevruchtengids.org/files/styles/photo_soort/public/soort/perche%20du%20nil.2.jpg" alt = "perche carnivore">

Ou encore le miconia, un arbre originaire d'Amérique du Sud, apporté accidentellement sur de nombreuses îles du Pacifique dans de la terre « contaminée » et par des engins de chantier, a envahi les deux tiers de Tahiti. Formant des fourrés denses empêchant les autres plantes d'accéder à la lumière, il menace aujourd’hui près de 70 espèces endémiques de l'île française.

<img src ="https://dlnr.hawaii.gov/hisc/files/2013/02/miconia.jpg" alt = "miconia">

---

## Conclusion

&nbsp;&nbsp;&nbsp;&nbsp;En conclusion, nous avons modélisé numériquement les équations représentatives de la dynamique proie-prédateur de Lotka-Volterra en Python 3. Grâce aux bibliothèques graphiques Matplotlib et Plotly, nous avons pu visualiser l'évolution des densités de population de chaque espèce dans le temps. En introduisant une espèce invasive dans notre modèle, nous avons constaté les conséquences destructrices de l'action directe et indirecte de l'Homme sur les écosystèmes.  Des réglementations et accords existent pour faire face.
Toutefois, leur mise en place reste partielle.

---
 
## Bibliographie
1) ROSS, Allan. « Le modèle proie-prédateur de Lotka-Volterra implémenté en Python ».
Page web (2013) . https://complexe.jimdofree.com/la-th%C3%A9orie-du-chaos/dynamique-des-popu-
lations/programmation-en-python/

2) Slimani, Safia. « Système dynamique stochastique de certains modèles proies-prédateurs et applica-
tions. ». Systèmes dynamiques [math.DS]. Normandie Université; Université Badji Mokhtar-Annaba,
2018. Français. ffNNT : 2018NORMR123ff.

3) VIAL, Grégory. « Le système proie-prédateur de Volterra-Lotka ». École normale supérieure de
Rennes, 18 mars 2011. https://w3.ens-rennes.fr/math/people/gregory.vial/files/cplts/volterra.pdf

4) Walid, Abid. Analyse de la dynamique de certains modèles proie-prédateur et applications. Mathé-
matiques générales [math.GM]. Université du Havre; Université de Tunis El Manar, 2016. Français.
NNT : 2016LEHA0001 . tel-01409769. https://theses.hal.science/tel-01409769

5) Wu, Shi-Liang, et al. « Propagation Dynamics in Periodic Predator-Prey Systems with Nonlocal
Dispersal ». Journal de Mathématiques Pures et Appliquées, vol. 170, février 2023, p. 57‑95. DOI.org
(Crossref), https://doi.org/10.1016/j.matpur.2022.12.003.

6) Yoav, Ram. « Lotka-Volterra equations: deterministic continuous time models / Scientific Compu-
ting with Python ». https://github.com/yoavram/SciComPy/blob/master/notebooks/lotka-volterra.ipynb
