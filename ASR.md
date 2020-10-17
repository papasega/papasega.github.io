---
layout: post
title: La reconnaissance vocale en Wolof
subtitle: Comment ça marche ?
bigimg: img/Websites_Redesign_Backgrounds_DT_Robotics1_2018.jpg
#share-img: https://github.com/papasega/psw_blog/tree/master/img/posts/ARS.png
tags: [ASR, Speech Recognition, NLP]
comments: true
---


Table of contents
=================
<!--ts-->
   * [Introduction](#introduction)
   * [Définition et Objectif](#definition-et-objectif)
<!--te-->

Système de reconnaissance automatique de la parole (Automatic Speech Recongnition -- ASR)
==============

Introduction 
============

Les technologies d'ingénierie linguistique font fonctionner de nombreuses applications au sein des moteurs de recherche, des chatbots, forums, etc. Pour traiter le langage et la parole, ces technologies combinent des domaines tels que la syntaxe ou la sématique, laquelle constitue un champ de recherche en progrès continu pour offrir une compréhension toujours plus affinée de sens. 


Comment fonctionne un sydtème de Reconnaissance Automatique de la Parole (RAP) en anglais Automatic Speech Recognition (ASR) ? 

![image](https://drive.google.com/uc?export=view&id=1VCXxTcHy-dTFS-osDPdVQNnYgvCfR0ad)

Nous verrons la réponse de cette question dans la suite de l'article.  


 Nous allons parler, dans cet article, le système de reconnaissance automatique de la parole des **langues d'Afrique subsaharienne**. 
 En particulier le **wolof**, une langue parlée par plus de 90% de la population sénégalaise. 

# La Reconnaisance automatique de la parole
## 1 Definition et Objectifs  
"La reconnaisance automatique de la parole est définie comme étant une technique qui vise à faire reconnaître par un ordinateur les mots ou les phrases prononcées par une ou plusieurs personnes". 
Un tel système analyse ainsi un ﬂux audio et transcrit, le plus ﬁdèlement possible, les paroles prononcées en texte. 
C’est donc une technique informatique qui permet d’analyser la voix humaine captée au moyen d’un microphone pour la transcrire sous la forme d’un texte exploitable par une machine.


**La reconnaissance de la parole** a pour objectif d’extraire une information lexicale (mots, suite de mots ou hypothéses de mots) à partir d’une information acoustique (le signal de parole). 
Cependant la **compréhension de la parole** (pour des applications de dialogue naturel) essaye d’extraire en plus une information sémantique qui permet d’avoir une connaissance des intentions de l’utilisateur.


Dans la suite de cet article, je vais vous parler, certaines de mes expériences académiques dans le  domaine de la parole et de l'audio.
En effet il s'agira en particulier de la reconnaissance vocale et la gestion du dialogue dans une langue d'Afrique subsaharienne: le Wolof.

Avant de commencer à developper sujet, parlons de la noble cause de cette technologie qui lutte contre les inégalités numériques. En effet, imaginons un pêcheur qui veut aller sur mer et qui ne sait pas utiliser son smartphone pour regarder les conditions météorologiques.  Si toutefois il pouvait recevoir ces informations sur son terminal en sa langue locale cela lui facilitera drastiquement sa vie et son activé. De même pour un agriculteur du monde rural qui veut avoir des informations sur les semences et la fertilité des sols en sa langue locale et en vocale.

### Parlons un peu du Sénégal. 

Le Sénégal étant un pays riche de par sa diversité éthnique avec une multitude de langues locales (environs plus 30) dont le wolof qui est parlé par plus de **90%** de la population bien que le français soit la langue officielle, n'est compris que moins de **25%**.

Comme les **60 %**  de cette population ne savent ni lire, ni écrire. Ainsi une infime partie de la population est connectée et bénéficie de toutes les commodités du numérique. 

Ainsi l'utilisation de l'intelligence artificielle peut relever ce défi tout en permettant à tout un chacun de communiquer à  temps avec sa langue natale.

 

## 2. Pourquoi la parole ?

Tout simplement parce que la parole et l'audio sont très pertinents dans les tendances liées à l'intelligence artificielle. La première tendance étant la voix. Ces dernières années, nous avons vu une tendance remarquable de personnes s'engageant avec des haut-parleurs intelligents pour être assistées sur divers produits, logiciels et matériels différents en utilisant uniquement leur voix, c'est incroyable! Que ce soit pour obtenir des informations sur ce qui se passe dans leur journée pour le savoir, appeler vos amis et votre famille, etc.
La voix est une interface très naturelle que les gens trouvent très utile et facile à utiliser et l'autre tendance que nous avons remarquée est l'audio.
Si vous êtes tenu au courant de toute forme de nouvelles, vous verrez que le contenu audio et vidéo est en constante augmentation dans la production. Et la question est de savoir comment nous pouvons aider les personnes réputées d'illettrisme à vivre une expérience formidable dans ce monde du numérique. Aussi comment les aidons-nous à avoir le pouvoir de gérer des services, sur leurs activités économiques, autour de la parole et de l'audio dans leur langue maternelle ou locale.

### 2.1 L'importance de la parole et de l'audio 

La première chose à laquelle nous pensons est de savoir comment utiliser la voix pour aider les gens à dialoguer avec un robot en vocal et à vivre une expérience naturelle, facile et légère. La parole et l'audio sont vraiment importants, et à long terme nous devons continuer à y investir pour réussir le defi de lutte contre l'inégalité numérique. L'Afrique compte plus de 2000 langues très liées aux ethnies et peu liées aux nations. Ainsi l’expression linguistique est donc nécessaire. Il est important que nous ayons une grande expérience dans les différentes langues d'Afrique Subsaharienne. La mise à l'échelle pour prendre en charge cela n'est pas nécessairement facile. La création de modèles d'apprentissage automatique comporte de nombreux défis différents. 

## 3. Le système de reconnaissance vocale  

![image](https://drive.google.com/uc?export=view&id=1VCXxTcHy-dTFS-osDPdVQNnYgvCfR0ad)

### 3.1 Le modèle acoustique**
Le modèle acoustique étant le modèle utilisé dans la reconnaissance automatique de la parole pour représenter la relation entre un signal audio et les phonèmes ou autres entités linguistiques qui composent la parole. Ce modèle est tiré d'un ensemble d'enregistrement audio et de leurs transcriptions correspondantes. Il est créé en prenant des enregistrements audio de la parole et de leurs transcriptions de texte, et en utilisant un logiciel pour créer des représentations statistiques des sons qui composent chaque mot. Cela peut être pour chaque langue différente, tout le vocabulaire, les modèles de discours, l'argot local etc.
Passons à certains de ces défis à un très bref aperçu.

![image](https://drive.google.com/uc?export=view&id=1TtPTYB5ft89yo_OGPBtsviwF94JGuSHo)

**Comment la reconnaissance vocale fonctionne à un niveau avancé ?** 

Le but des tâches de la reconnaissance vocale est de prendre un fichier audio et de faire maping avec un fichier texte qui est une prédiction de ce qui a été prononcé dans le signal audio. Pour cela il faut des fonctionnalités, pas toutes faciles à appréhender. Nous pouvons le soumettre à différents modèles entraînés sur des données, puis faire une prédiction de ce qui a été dite. 
Passons à un exemple explicite.

**La phonologie d'une langue et modèle acoustique de l'ASR**.

![image](https://drive.google.com/uc?export=view&id=1pkUeNuDGJ3ID3n1dgdRexMYEnpzuN1xa)

Le travail du modèle acoustique consiste à prendre des phonèmes audio et de sortir des unités sonores qui représentent une sorte de phonologie de la langue, toutes les différentes unités de son qui composent les mots.
Vous pourriez bien dire comment donner un sens à toutes ces différentes unités de sons.
Heureusement, nous avons un dictionnaire qui représente le vocabulaire en quelque sorte phonétisé. Il s'agit d'une correspondance entre les mots et la façon dont vous les prononcez dans les unités sonores. Ce dictionnaire est ce que nous utilisons pour donner un sens à tout cela. Les différents phonèmes et passez de votre modèle acoustique aux mots sensibles. Mais maintenant, nous avons un tas de mots qui doivent être mis dans une phrase ou plusieurs phrases. 

![image](https://drive.google.com/uc?export=view&id=18CCGCCdAiT8KpxkgNHbvSd3V9QTQVDnb)

Nous pouvons utiliser de nombreuses combinaisons différentes pour donner une phrase à ces differents mots. La question est alors comment déterminez-vous quelle est la bonne combinaison ? C'est là que vous utiliserez un **modèle de langage** qui vous aidera à comprendre le contexte d'une phrase sur les mots et à déterminer la combinaison la plus probable, la séquence de ces mots qui ont du sens. Ainsi nous avons là notre sortie du ASR c'est à dire la transcription du signal d'entré. 
Le rôle du **modèle de langage** est d’estimer la probabilité à priori de séquence de mot <img src="https://latex.codecogs.com/svg.latex?\Large&space; P(W)} " title="  " />. Il existe dans les faits deux façons de procéder pour créer un modèle de langage. Il s’agit soit de définir un système utilisant une grammaire formelle définie par des linguistes (approche dans les faits trop compliquée à mettre en place) soit d’utiliser un modèle statistique appris automatiquement à partir de vastes corpus de textes.
Les modèles statistiques du langage sont la plupart du temps des modèles N-grammes, car ces derniers ont l’avantage d’être performants et simples.

**Exemple:**

             Na ngen deef 
             Dala ak jàmm si Reewu Terannga bi 
             =================================
             Comment allez-vous ? 
             Bienvenu dans le pays de la Terannga
             
![image](https://drive.google.com/uc?export=view&id=1CAZlm7wwfTeYKPgQtNVEg2IKympUpX-u)

Maintenant, si vous souhaitez créer cette combinaison dans toutes les langues. Vous allez faire la même tâche pour ces trois composants et les construire pour chaque langue que vous souhaitez prendre en charge, ce qui devient un peu complexe, comme nous le verrons dans la suite.
Alors, quel est exactement le grand défi de la mise à l'échelle vers toutes ces différentes langues ? 

**La problèmatique des données**
Toute la difficulté de ce domaine repose sur les resources linguinstiques et surtout quand ces derniers sont rares. Comme le cas du wolof qui est une langue peu dotée.
Il y a évidemment un composant de collecte de données dont nous avons besoin pour former nos modèles acoustiques et nos modèles de langage. Mais lorsque nous avons un dictionnaire de prononciation ou nous devons avoir une connaissance phonologique linguistique approfondie d'une langue, c'est ce genre de chose que les gens vont à l'école pour étudier pendant des années dans une langue donnée. C'est là que ça devient difficile. Vous pourriez vous dire, pourquoi ne pas trouver tous les experts linguistes ?
Eh bien, imaginez qu'il n'y a que 5 millions de personnes qui parlent une langue donnée dans le monde et que sur ces 5 millions, vous devez trouver les quelques experts qui existent qui connaissent réellement toutes les nuances de cette langue. Vous pouvez voir à quel point cela devient difficile à mesure que vous évoluez vers de plus en plus de langues.
N'oubliez pas non plus que ce n'est pas un langage de tâche unique. La langue n’est pas statique. La langue évolue au fil du temps, de nouveaux mots apparaissent, les anciens mots s’évanouissent, les changements de sens, les prononciations changent, la langue vernaculaire et l’argot apparaissent, il s’agit donc d’un problème permanent auquel vous devez faire face. Alors, comment pouvons-nous mettre à l'échelle la fabrication artisanale de ces dictionnaires asiatiques. C’est assez difficile.

Eh bien, prenons un peu de recul et ré-évaluons simplement ce que nous faisons de bout en bout dans le processus ASR.Y a-t-il une meilleure façon d'avoir de l'audio, de le faire passer par un modèle acoustique et d'obtenir un tas de phonèmes, vous prenez ces phonèmes, obtenez des mots à partir d'un dictionnaire, puis à partir des mots, vous obtenez une phrase et se termine si vous y réfléchissez, le gros problème que nous avons est cette grande dépendance aux systèmes phonétiques.

![image](https://drive.google.com/uc?export=view&id=1pwP0gfrYmjZRQukvrDpWvKY4FrA1h_Ea)

## Modélisation mathélatique:

![image](https://drive.google.com/uc?export=view&id=1Zd0kjX86n4DNlaBXunMn75AEjytgzLJm)



Suite en construction .....
