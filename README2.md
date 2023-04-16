# Dynamique d'un système proies-prédateurs

Le changement climatique est une problématique au coeur du 21ème siècle, qui implique des modifications des différents écosystèmes, perturbant ainsi les populations animales et végétales qui y vivent. Entre autres, l'introduction d'une espèce exotique envahissante fait partie des perturbations qu'un milieu peut subir, en réponse à l'action humaine mais aussi à cause du changement climatique qui force certaines espèces à migrer pour survivre. Ces dynamiques de populations qui perturbent l'ensemble de l'équilibre naturel des différents milieux sont responsables de la perturbation des dynamiques entre proies et prédateurs d'un même milieu, pouvant conduire à l'extinction ou du moins la mise en danger d'une ou de plusieurs espèces. Ainsi, nous avons fait le choix d'étudier l'évolution de l'effectif des populations dans un milieu selon certains paramètres qui caractérisent ces espèces, avec l'aide d'un modèle dynamique, afin de répondre à la problématique suivante: 
Dans quelle mesure les changements climatiques perturbent-ils la stabilité des systèmes proies-prédateurs ?

## 1-Équations du modèle de Lotka-Volterra :

En effectuant des recherches, nous avons trouvé ces équations différentielles qui permettent d'obtenir une variation de population en fonctions des paramètres détaillés ci-dessous :

                                  𝑑𝑥/𝑑𝑡=𝑏𝑥−ℎ𝑥𝑦 
                                  𝑑𝑦/𝑑𝑡=𝜖ℎ𝑥𝑦−𝑑𝑦

#### Définition des paramètres :
- 𝑥 : densité des proies
- 𝑦 : densité des prédateurs
- 𝑏 : taux de reproducion des proies (constant)
- ℎ : taux de mortalité des proies dû aux prédateurs
- 𝑑 : taux de mortalité des prédateurs (constant)
- 𝜖ℎ : taux de conversion de la densité de proies en densité de prédateurs

#### Modélisation système proie-prédateur en condition normale :

En se servant des différentes informations dont nous disposions nous avons pu générer ces graphiques.

![proiepred](https://user-images.githubusercontent.com/125446625/232338044-ee9dbf41-e349-40bb-a585-13a130ce6e3c.jpg)

Ces graphiques représentent le nombre de proies et de prédateurs en fonction du temps à gauche, et à droite le nombre de prédateurs en fonction du nombre de proies.

On remarque que l'évolution de l'effectif des individus du système en fonction du temps est périodique. Ceci est cohérent avec la réalité biologique : lorsque les proies sont nombreuses, les prédateurs prospèrent jusqu'à épuiser leurs ressources. Lorsque l'effectif de la population prédatrice a suffisamment diminué, les proies se reproduisent et leur population augmente. Ce cycle se reproduit à l'infini dans des conditions normales.

#### Equilibre du système :

Le système est à l'équilibre lorsque les taux de croissance des populations de proies et prédateurs sont nuls, c'est à dire lorsque les dérivées respectives s'annulent. Autrement dit:

                                  𝑥(𝑏−ℎ𝑦)=0 
                                  𝑦(𝜖ℎ𝑥−𝑑)=0
                                  
Une solution triviale à ce système est le couple (x, y) = (0, 0). Cette solution correspond à l'extinction des deux espèces. On s'intéresse au couple de solution positif du système (x,y) tel que:

                                  𝑥=𝑑/𝜖ℎ
                                  𝑦=𝑏/ℎ
                                  
![pp](https://user-images.githubusercontent.com/125446625/232339447-32193369-6f95-42f8-96dd-82184858561c.jpg)

On introduit une perturbation légère aux valeurs d'équilibre

![pp2](https://user-images.githubusercontent.com/125446625/232339618-38683daf-ca72-42df-ba61-8d6eedaae3b7.jpg)

Puisque la dérivée dx/dt est négative et dy/dt positive, la fonction modélisant l'évolution de la population de proie est décroissante tandis que celle des prédateurs croissante. Le système n'est pas à l'équilibre mais converge vers un état stable.

