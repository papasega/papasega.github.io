---
layout: post
title: TP -- Régression Linéaire sur python
subtitle: Linear Regression  
bigimg: img/The-linear-regression-model.png
share-img: img/ML_intro.png
tags: [IA, maths, algébre, PSW]
comments: true
---

# 1. Introduction 

Le but de cet article est de s'entraîner à implémenter une algèbre linéaire (avec des équations fournies) et d'explorer certaines propriétés de la régression linéaire.

# 2. Definition

L'objectif de la régression simple (resp. multiple) est d'expliquer une variable  <img src="https://latex.codecogs.com/svg.latex?\Large&space; Y \ à  l'aide  d'une  variable  \ X " tittle= " Y \ à  l'aide  d'une  variable  \ X " /> (resp. plusieurs variables <img src="https://latex.codecogs.com/svg.latex?\Large&space; X_1,  X_2, ..., X_p " title= "X_1,  X_2, ..., X_p  " /> ). 
La variable <img src="https://latex.codecogs.com/svg.latex?\Large&space; Y  " title="Y  " /> est appelée variable dépendante, ou variable à expliquer et les
variables <img src="https://latex.codecogs.com/svg.latex?\Large&space; X_j, \ (j=1,..., p)  " title="X_j, \ (j=1,..., p) " /> (j=1,...,q) sont appelées variables indépendantes, ou variables explicatives.

# 3. Importation des librairies. 

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
plt.style.use(['ggplot'])
```
Nous considérons un problème de régression linéaire de la forme. 


Great tuto by Marc Deisenroth (english version)
