---
layout: post
title: TP -- Régression Linéaire sur python
subtitle: Linear Regression  
bigimg: img/The-linear-regression-model.png
share-img: img/ML_intro.png
tags: [IA, maths, algébre, PSW]
comments: true
---

# TP -- Régression Linéaire

## 1. Introduction 

Le but de cet article est de s'entraîner à implémenter une algèbre linéaire (avec des équations fournies) et d'explorer certaines propriétés de la régression linéaire.

## 2. Definition

L'objectif de la régression simple (resp. multiple) est d'expliquer une variable  <img src="https://latex.codecogs.com/svg.latex?\Large&space; Y  " title="Y  " /> à l'aide d'une variable <img src="https://latex.codecogs.com/svg.latex?\Large&space; X  " title="X  " /> (resp. plusieurs variables <img src="https://latex.codecogs.com/svg.latex?\Large&space; X_1,  X_2, ..., X_p " title= "X_1,  X_2, ..., X_p  " /> ). 

La variable <img src="https://latex.codecogs.com/svg.latex?\Large&space; Y  " title="Y  " /> est appelée variable dépendante, ou variable à expliquer et les
variables <img src="https://latex.codecogs.com/svg.latex?\Large&space; X_j, \ (j=1,..., p)  " title="X_j, \ (j=1,..., p) " />  sont appelées variables indépendantes, ou variables explicatives.

![image](https://drive.google.com/uc?export=1lhGMOB_QVY8HFQBOPPKYheWaqnferFLY)

[*Un résumé de lecture théorique*](https://www.math.univ-toulouse.fr/~besse/Wikistat/pdf/st-l-inf-regsim.pdf)

**Importation des librairies**. 

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
plt.style.use(['ggplot'])
```
Nous considérons un problème de régression linéaire de la forme. 

<img src="https://latex.codecogs.com/svg.latex?\Large&space; y = \boldsymbol x^T\boldsymbol\theta + \epsilon\,,\quad \epsilon \sim \mathcal N(0, \sigma^2)  " title=" y = \boldsymbol x^T\boldsymbol\theta + \epsilon\,,\quad \epsilon \sim \mathcal N(0, \sigma^2)  " />

Avce <img src="https://latex.codecogs.com/svg.latex?\Large&space; x \in \mathbb{R}^{D}  " title=" s \in \mathbb{R}^{D} " /> sont les entrées et <img src="https://latex.codecogs.com/svg.latex?\Large&space; y  " title=" y  " /> les observations bruyantes ( le terme <img src="https://latex.codecogs.com/svg.latex?\Large&space; \epsilon  " title=" " />). Le vecteur de parametre <img src="https://latex.codecogs.com/svg.latex?\Large&space; \theta \in \mathbb{R}^{D}  " title=" " /> paramétrise la fonction. 
Nous supposons d'avoir un jeu de données <img src="https://latex.codecogs.com/svg.latex?\Large&space; (x_n, y_n), n=1,...,N  " title=" " />.

Nous allons définir notre jeu de données d'entraîtenement (training set en anglais) comme <img src="https://latex.codecogs.com/svg.latex?\Large&space; \mathcal X = \{\boldsymbol x_1, \ldots, \boldsymbol x_N\}  " title=" " /> et les cibles d'entraînement par  <img src="https://latex.codecogs.com/svg.latex?\Large&space; \mathcal Y = \{y_1, \ldots, y_N\}  " title=" " /> respectivement. 

Dans ce tutoriel, nous souhaitons trouver les bons parametres <img src="https://latex.codecogs.com/svg.latex?\Large&space; \theta  " title=" " />.

```python
# Define training set
X = np.array([-3, -1, 0, 1, 3]).reshape(-1,1) # 5x1 vector, N=5, D=1
y = np.array([-1.2, -0.7, 0.14, 0.67, 1.67]).reshape(-1,1) # 5x1 vector

# Plot the training set
plt.figure()
plt.plot(X, y, 'o', markersize=10)
plt.xlabel("$x$")
plt.ylabel("$y$");
```
![image](https://drive.google.com/uc?export=1b4_e9tVtuEotgemC7JJjXPAIt1_OZ-O-)

## Maximum Likelihood (où Maximum de vraisemblance)

Nous commencerons par l'estimation du maximum de vraisemblance des paramètres θ. Dans l'estimation du maximum de vraisemblance, nous trouvons les paramètres $θ^ML$ qui maximisent la vraisemblance. 


Great tuto by Marc Deisenroth (english version)
