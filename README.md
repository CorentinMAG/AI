# Intelligence artificielle

Les différentes étapes : 

1. Récupérer des données liées à notre champ d'étude, le plus possible
2. Nettoyer les données, s'assurer qu'elles sont bien fiables, qu'il n'en manque pas et qu'elles sont fiables
3. Data mining, on calcule des paramètres, on peut soulever des hypothèses et même y répondre, on fait de la data visualisation (graphiques, ...)
4. Modélisation, utilisation d'algorithmes mathématiques, on passe par deux phases: la phase d'apprentissage, dans laquelle on entraine le modele et la phase de prédiction
5. Evaluer et interpréter les données, on évalue la qualité du modèle, s'il est pertinent
6. Mettre le système en production

## Le machine learning

Pour qu'un programme puisse exécuter une tâche pour laquelle il n'est pas programmé explicitement, il faut:
* des données relatives à ladite tâche
* un algorithme, son objectif est de transformer nos données en un modèle
* c'est l'apprentissage, qui va permettre de construire le modèle.

### Les différents types d'apprentissages

**Apprentissage supervisé**

> :information_source: On possède des données déjà classés/connues/étiquettés servant de base à la prédiction

Permet de répondre à des problématiques de classifications et de régressions.

L'apprentissage est dit supervisé lorsque les données qui entrent dans le processus sont déjà catégorisées et que les algorithmes doivent s'en servir pour prédire un résultat en vue de pouvoir le faire plus tard lorsque les données ne seront plus catégorisées.

L'idée consiste donc à associer un label à des données sur lesquelles on a des mesures.
* si les labels sont discrets on parle de classifications
* si les labels sont continus on parle de regression

**Apprentissage non supervisé**

> :information_source: On ne possède pas de données déjà classés/connues servant de base à la prédiction

Le système va devoir détecter les similarités dans les données qu'il reçoit et les organiser en fonction de ces dernières.
On doit:
1. classer les donner : comme on n'a pas encore les labels/étiquettes, on parle de clustering
2. diminuer le nombre de dimensions de nos données (car souvent on dispose de beaucoup de paramètres), tout en conservant l'essentiel de l'information

**Apprentissage par renforcement**

> :information_source: Le but est d'apprendre, à partir d'expériences successives, ce qu'il convient de faire de façon à trouver la meilleure solution. On laisse l'algorithme apprendre de ses propres erreurs

Le procédé est intéractif et itératif. La machine fait face à un problème, elle observe son environnement, choisit une solution parmi plusieurs possibles, observe la réaction de l'environnement et adapte son comportement pour la prochaine itération afin de trouver la meilleure stratégie.
L'IA est donc confronté à des choix. Si elle se trompe, elle est pénalisée sinon elle est récompensée. Afin d'obtenir toujours plus de récompenses, l'IA va faire de son mieux pour obtimiser sa prise de descisions.
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



