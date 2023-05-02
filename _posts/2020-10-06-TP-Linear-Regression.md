---
layout: post
title: TP -- Régression Linéaire sur python
subtitle: Linear Regression  
bigimg: img/The-linear-regression-model.png
share-img: img/ML_intro.png
tags: [IA, maths, algébre, PSW]
comments: true
categories: machine-learning
---

# TP -- Régression Linéaire

## 1. Introduction 

Le but de cet article est de s'entraîner à implémenter une algèbre linéaire (avec des équations fournies) et d'explorer certaines propriétés de la régression linéaire.

## 2. Definition


L'objectif de la régression simple (resp. multiple) est d'expliquer une variable  <img src="https://latex.codecogs.com/svg.latex?\Large&space; Y  " title="Y  " /> à l'aide d'une variable <img src="https://latex.codecogs.com/svg.latex?\Large&space; X  " title="X  " /> (resp. plusieurs variables <img src="https://latex.codecogs.com/svg.latex?\Large&space; X_1,  X_2, ..., X_p " title= "X_1,  X_2, ..., X_p  " /> ). 

La variable <img src="https://latex.codecogs.com/svg.latex?\Large&space; Y  " title="Y  " /> est appelée variable dépendante, ou variable à expliquer et les
variables <img src="https://latex.codecogs.com/svg.latex?\Large&space; X_j, \ (j=1,..., p)  " title="X_j, \ (j=1,..., p) " />  sont appelées variables indépendantes, ou variables explicatives.

![image](https://drive.google.com/uc?export=view&id=1lhGMOB_QVY8HFQBOPPKYheWaqnferFLY)


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
![image](https://drive.google.com/uc?export=view&id=1b4_e9tVtuEotgemC7JJjXPAIt1_OZ-O-)

## 3. Maximum Likelihood (où Maximum de vraisemblance)

Nous commencerons par l'estimation du **maximum de vraisemblance** des paramètres θ. Dans l'estimation du maximum de vraisemblance, nous trouvons les paramètres <img src="https://latex.codecogs.com/svg.latex?\Large&space; \theta^{ML}  " title=" " /> qui maximisent la vraisemblance. 


**L'estimateur du maximum de vraisemblance** est un estimateur statistique utilisé pour inférer les paramètres de la loi de probabilité d'un échantillon donné en recherchant les valeurs des paramètres maximisant la fonction de vraisemblance. Un **estimateur** est une statistique permettant d'évaluer un paramètre inconnu relatif à une loi de probabilité (comme son espérance ou sa variance).

<img src="https://latex.codecogs.com/svg.latex?\Large&space; p(\mathcal Y | \mathcal X, \boldsymbol\theta) = \prod_{n=1}^N p(y_n | \boldsymbol x_n, \boldsymbol\theta)\,.  " title=" " />. 


J'avais mentioné dans un précedent poste *[introduit en machine learning](https://papasega.github.io/psw_blog/2020-09-27-into-ML/)* un lien de la demontration de  <img src="https://latex.codecogs.com/svg.latex?\Large&space; \theta^{ML}  " title=" " /> definie par:
<img src="https://latex.codecogs.com/svg.latex?\Large&space; \boldsymbol\theta^{\text{ML}} = (\boldsymbol X^T\boldsymbol X)^{-1}\boldsymbol X^T\boldsymbol y\in\mathbb{R}^D\,,  " title=" " />   avec   <img src="https://latex.codecogs.com/svg.latex?\Large&space; \boldsymbol X = [\boldsymbol x_1, \ldots, \boldsymbol x_N]^T\in\mathbb{R}^{N\times D}\,,\quad \boldsymbol y = [y_1, \ldots, y_N]^T \in\mathbb{R}^N\,.  " title=" " />. 

Evaluons l'estimation du maximum de vraisemblance pour un ensemble de données d'apprentissage. 
```python
def max_lik_estimate(X, y): 
    
    # X: N x D matrix of training inputs
    # y: N x 1 vector of training targets/observations
    # returns: maximum likelihood parameters (D x 1)
    
    N, D = X.shape
    theta_ml = np.linalg.solve(X.T @ X, X.T @ y) 
    return theta_ml 
```
```python 
# get maximum likelihood estimate
theta_ml = max_lik_estimate(X,y)
```
Nous maintenant faire une préduction utilisant le résultat trouver de l'estimateur du maximum de vraisemblance.


```python

def predict_with_estimate(Xtest, theta):
    
    # Xtest: K x D matrix of test inputs
    # theta: D x 1 vector of parameters
    # returns: prediction of f(Xtest); K x 1 vector
    
    prediction = Xtest @ theta 
    
    return prediction 
```
Regardons maintenant le résultat

```python 
# define a test set
Xtest = np.linspace(-5,5,100).reshape(-1,1) # 100 x 1 vector of test inputs

# predict the function values at the test points using the maximum likelihood estimator
ml_prediction = predict_with_estimate(Xtest, theta_ml)

# plot
plt.figure()
plt.plot(X, y, 'o', markersize=10)
plt.plot(Xtest, ml_prediction)
plt.xlabel("$x$")
plt.ylabel("$y$");
```

![image](https://drive.google.com/uc?export=view&id=1yjDb4-IoZdWB1l1UZrulr5CffEZBWTef)


Ainsi on peut se poser les questions suivantes: 
    - Est ce que la solution obetue ci-dessu semble-t-elle raisonable ? 
    - En modifiant les valeurs de θ, comment les fonctions correspondantes changent-elle ? 
    -En modifiant la variable à expliquer <img src="https://latex.codecogs.com/svg.latex?\Large&space; \mathcal Y " title=" " /> , qules changements observe--on ? 



Examinons maintenant un ensemble d'apprentissage différent, où nous ajoutons 2.0 à chaque valeur y, et calculons l'estimation du maximum de vraisemblance.

```python
ynew = y + 2.0

plt.figure()
plt.plot(X, ynew, '*', markersize=10)
plt.xlabel("$x$")
plt.ylabel("$y$");
```
![image](https://drive.google.com/uc?export=view&id=12v4d93P5Xn6e_2to2cyiL5HFYCxnRKbB)

```python
# get maximum likelihood estimate
theta_ml = max_lik_estimate(X, ynew)
print(theta_ml)

# define a test set
Xtest = np.linspace(-5,5,100).reshape(-1,1) # 100 x 1 vector of test inputs

# predict the function values at the test points using the maximum likelihood estimator
ml_prediction = predict_with_estimate(Xtest, theta_ml)

# plot
plt.figure()
plt.plot(X, ynew, 'o', markersize=10)
plt.plot(Xtest, ml_prediction)
plt.xlabel("$x$")
plt.ylabel("$y$");
```
![image](https://drive.google.com/uc?export=view&id=13kV72b_10xgBldTmuYitErVtYuN-h5iR)


        Le suite en construction! 







***********************************************
Great tuto by Marc Deisenroth (english version)
