# Intelligence artificielle

Les différentes étapes : 

1. Récupérer des données liées à notre champ d'étude, le plus possible
2. Nettoyer les données, s'assurer qu'elles sont bien fiables, qu'il n'en manque pas, qu'elles sont consistantes, sans valeurs aberrantes et dans le même format
3. Data mining, on calcule des paramètres, on peut soulever des hypothèses et même y répondre, on fait de la data visualisation (graphiques, ...) afin de comprendre les différents comportement et de bien saisir le phénomène sous-jacent
4. Modélisation, l'objectif est de trouver un modèle du phénomène à l'origine des données à l'aide de lequel on va pouvoir effectuer des prédictions. Ensuite, il faut implémenter l'algorithme adéquat, afin de construire de modèle qui se rapprochera le plus des données d'exemple. Il faut enfin entrainer le modèle avant de  pouvoir faire des prédictions
5. Evaluer et interpréter les données, on évalue la qualité du modèle, s'il est pertinent
6. Mettre le système en production

### Le machine learning

Pour qu'un programme puisse exécuter une tâche pour laquelle il n'est pas programmé explicitement, il faut:
* des données relatives à ladite tâche. Ce sont les exemples que l'on va fournir à l'algorithme pour qu'il puisse apprendre et devenir plus performant
* un algorithme, son objectif est de transformer nos données en un modèle
* mesurer la performance de l'algorithme
* c'est l'apprentissage, qui va permettre de construire le modèle.

### Choisir ses données

Il faut utiliser le jeu de données (dataset) à notre disposition à bon escient.
Une bonne pratique est de séparer notre dataset en 3 paquets:
* le dataset d'entrainement, qui sera uniquement utilisé pour entrainer l'algorithme (il faut s'assurer que l'échantillon soit bien représentatif de toutes les données, pour ça généralement on récupère aléatoirement des échantillons dans notre jeu de données)
* le dataset de test, qui servira à mesurer l'erreur (et donc la performance) du modèle sur des données qu'il n'a jamais vues. L'algorithme ne sera donc pas entrainé avec ces données.
* le dataset de validation, qui servira à valider ou non notre modèle en mesurant l'erreur de prédiction (lors d'une validation croisée)

> :information_source: En général, on sépare les données suivant la proportion 80:20

### Les différents types d'apprentissages

**Apprentissage supervisé**

> :information_source: On possède des données déjà classés/connues/étiquettés servant de base à la prédiction. Le but est de minimiser l'erreur entre la réponse de la machine et la réponse attendu (donnée par les données d'entrée).

Permet de répondre à des problématiques de classifications et de régressions.

L'apprentissage est dit supervisé lorsque les données qui entrent dans le processus sont déjà catégorisées et que les algorithmes doivent s'en servir pour prédire un résultat en vue de pouvoir le faire plus tard lorsque les données ne seront plus catégorisées.

L'idée consiste donc à associer un label à des données sur lesquelles on a des mesures.
* si les labels sont discrets on parle de classifications
* si les labels sont continus on parle de regression

Les étapes :
1. dataset (y:target, x:features)
2. modèle (régression linéaire,logistique...)
3. fonction de coût (l'erreur quadratique moyenne)
4. algorithme de minimisation de la fonction de coût (moindres carrées, descente du gradient...)

> :information_source: Ici, la notion principale est celle de perte d'information (loss) dû à l'approximation de la réalité (notre modèle perd de l'information par rapport à la réalité observée à travers les données d'exemple). L'apprentissage se résume à minimiser cette fonction de perte afin que notre modèle soit le meilleur possible.

**Apprentissage non supervisé**

> :information_source: On ne possède pas de données déjà classés/connues servant de base à la prédiction. Le but est que notre programme puisse reconnaitre des structures (des différences/ressemblances) dans les exemples qu'on lui montre

Le système va devoir détecter les similarités dans les données qu'il reçoit et les organiser en fonction de ces dernières.
On doit:
1. classer les donner : comme on n'a pas encore les labels/étiquettes, on parle de clustering
2. diminuer le nombre de dimensions de nos données (car souvent on dispose de beaucoup de paramètres), tout en conservant l'essentiel de l'information

**Apprentissage par renforcement**

> :information_source: Le but est d'apprendre, à partir d'expériences successives, ce qu'il convient de faire de façon à trouver la meilleure solution. On laisse l'algorithme apprendre de ses propres erreurs

Le procédé est intéractif et itératif. La machine fait face à un problème, elle observe son environnement, choisit une solution parmi plusieurs possibles, observe la réaction de l'environnement et adapte son comportement pour la prochaine itération afin de trouver la meilleure stratégie.
L'IA est donc confronté à des choix. Si elle se trompe, elle est pénalisée sinon elle est récompensée. Afin d'obtenir toujours plus de récompenses, l'IA va faire de son mieux pour obtimiser sa prise de descision.
Le développeur se contente de fixer les règles qui détermine si l'IA sera récompensée ou punie.

**Apprentissage par transfert**

> :information_source: On transfère des connaissances d'une/plusieurs tâches sources vers une/plusieurs tâches cibles

On utilise des connaissances acquises pour les ré-appliquer dans un autre environnement. Pour être efficace, l'environnement cible ne doit pas être trop différent de l'environnement source.
Ex: les connaissance acquises pour reconnaitre des voitures peuvent être utilisées pour reconnaitres des camions

Chacun de ces types d'apprentissages peut s'appuyer sur différents algorithmes.

### Les différents algorithmes

**Régression linéaire**

> :information_source: algorithme d'apprentissage supervisée. A partir d'une variable cible, le modèle à pour but de faire une prédiction grâce à des variables dites explicatives

Il faut déterminer une équation de droite/plan qui se rapproche au plus près de l'ensemble de points étudiés.
[La méthode des moindres carrés](https://eli.thegreenplace.net/2014/derivation-of-the-normal-equation-for-linear-regression) nous donne l'estimateur qui minnimise les erreurs: (X<sup>t<sup>X)<sup>-1</sup>X<sup>t<sup>Y
  
**KNN (K-nearest-neighbors)**
  
> :information_source: algorithme d'apprentissage supervisée. Recherche des k plus proches voisins entre la donnée à prédire et les données connus. Cet algorithme est non paramétrique, il se base uniquement sur les données d'entrainement.
> :warning: pour que cette algorithme fonctionne, il faut que le nombre de paramètres soit petit
  
On dispose d'une base de données d'apprentissage constituée de N couples 'entrée-sortie'. Pour estimer la sortie associée à une nouvelle entrée x, on prend en compte les k échantillons d'appprentissage dont l'entrée est la plus proche de la nouvelle entrée x, selon une distance à définir. Le type de la sortie associé à x sera alors le type de sortie le plus représenté parmi les k échantillons.

k est ce qu'on appelle un hyperparamètre, c'est à dire que ce n'est pas un paramètre qui va pouvoir être appris par l'algorithme. On va chercher à trouver la meilleure valeur de k possible pour minimiser l'erreur sur les données de test.

[Plus d'information](https://cache.media.eduscol.education.fr/file/NSI/76/6/RA_Lycee_G_NSI_algo_knn_1170766.pdf)

**Descente de gradient**

> :information source: algorithme d'optimisation pour l'apprentissage supervisée qui permet de trouver le minimum de la fonction de coût qui est convexe

La fonction de coût est convexe, elle admet donc un minimum.


[gradient](./github/gradient.PNG)   | alpha est le learning rate et J est la fonction de coût

### Compromis entre biais et variance

Un modèle est très dépendant du dataset d'entrainement. On le voit très bien avec l'algorithme KNN avec k = 1: l'algorithme sera parfait pour les données d'entrainement mais beaucoup moins pour les données de test!  
Comme on ne veut pas de cette variabilité, on va faire en sorte que la variabilité vis à vis du dataset d'entrainement diminue. Pour ça, dans le cas de KNN, on va augmenter k.  
Cependant, augmenter k vas créer un autre type d'erreur, appelé biais. Le biais est lié à la complexité du modèle: Plus celui ci est complexe et plus le biais diminue.
Dans le cas de KNN, augmenter drastiquement k rend le modèle plus simple, et donc le biais est élevé. Un modèle trop simple ne parvient pas à capturer toute la complexité du problème.

Il faut trouver un bon compromis entre variance forte et biais élevé (bias-variance tradeoff)

1. réduire le nombre de dimensions du modèle (simplifie le modèle et donc diminue la variance ex: PCA,Isomap)
2. utiliser des méthodes ensemblistes (il existe toute une famille d'algorithme appelés les méthodes d'ensembles qui se basent sur la combinaison de plusieurs modèles à haute variance et les agrègent (p. ex. en les moyennant) pour réduire la variance finale)
3. Sélectionner et entrainer le bon modèle

### surapprentissage et sousapprentissage

Le surapprentissage désigne le fais que le modèle choisi est trop collé au dataset d'apprentissage. C'est un problème qui survient quand la complexité du modèle est trop élevée, et il prend en compte du "bruit" non représentatif du modèle sous-jacent. C'est ce qui arrive aux modèles avec une haute variance.

A l'inverse, les modèle avec un biais élevée sont en sousapprentissage, et peuvent rater des informations importantes.

La régularisation est une technique visant à limiter le surapprentissage. On impose au modèle des contraintes, afin de le simplifier.
1. régularisation dropout, les poids des coefficients sont remplacés par 0 de manière aléatoire
2. régularisation euclidienne, on favorise les coefficients faibles
3. early stopping, l'apprentissage s'arrête plus tôt

Une fois qu'on a trouvé le juste milieu l'algorithme est généralisable, il peut effectuer les prédictions les plus performantes possibles avec le moins de données possibles. 

Compromis entre biais et variance | erreur test vs entrainement | surapprentissage vs sousapprentissage |
:--------------------------------:|:---------------------------:|:------------------------------------:
![biais_variance](./.github/biais_variance.PNG) | ![test_vs_train](./.github/training_vs_test_error.PNG) | ![overlifting_underlifting](./.github/overlifting_underlifting.PNG)

### Problème de dimension

Pour un nombre de paramètre donné, plus la dimension de l'espace augmente et plus il faudra de données d'entrainement pour notre modèle. C'est ce qu'on appele le phénomène de curse of dimensionality qui se visualise très bien avec l'alorithme KNN.

Notre modèle doit donc être assez contraint pour pouvoir supporter les variations dimensionnelles sans augmenter en complexité.


### Evaluer les performances d'un modèle

On a vu qu'il fallait couper notre jeu de données en au moins deux parties : 
* un dataset pour l'entrainement
* un dataset pour le test

Il ne faut jamais évaluer un modèle sur des points qui ont été utilisés pour l'entrainer.

Cependant, on utilise du coup qu'une partie de nos données pour entrainer l'algorithme, si le dataset de test est très facile/dificile à prédire, l'estimation de la performance sera biaisé.

A la fin d'éviter ce problème, on utilise la validation croisée, qui va permettre d'utiliser l'intégralité de notre jeu de données pour l'entrainement et pour la validation.

Le principe consiste à découper le jeu de données en k parties (fold) à peu près égales. Tour à tour, chacune des k parties (souvent 5 ou 10) est utilisé comme un dataset de test. Le reste (les k-1 parties) est utilisé pour l'entrainement.

A la fin, chaque donnée a servit 1 fois dans le dataset de test et k-1 fois dans le dataset d'entrainement.  

La stratification consiste à faire des folds les plus variés possibles, afin que chaque fold puisse contenir un maximimum d'informations différentes.




