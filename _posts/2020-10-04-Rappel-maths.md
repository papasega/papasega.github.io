---
layout: post
title: Rappel Mathématique -- Algèbre linéaire 
subtitle: Algébre Linéaire  
bigimg: img/posts/1 1oE1nC3-7H1oz5WWe_gH6Q.jpeg
share-img: img/ML_intro.png
tags: [IA, maths, algébre, PSW]
comments: true
---



# Notations générales

# Définitions 



## 1. Vecteur 

On note  <img src="https://latex.codecogs.com/svg.latex?\Large&space; x\in\mathbb{R}^{n} " title=" x\in\mathbb{R}^{n} " /> un vecteur à <img src="https://latex.codecogs.com/svg.latex?\Large&space; n " title=" n " />  entrées, où <img src="https://latex.codecogs.com/svg.latex?\Large&space; x_{i} \in \mathbb{R} " title=" x_{i} \in \mathbb{R} "/> est la <img src="https://latex.codecogs.com/svg.latex?\Large&space; i^{eme} " title=" i^{ieme} " /> entrée :  

<img src="https://latex.codecogs.com/svg.latex?\Large&space; X " title=" X " /> = 
<img src="https://latex.codecogs.com/svg.latex?\Large&space; \left (
   \begin{array}{ccc}
      x_1 \\
      x_2 \\
      \vdots \\
      x_n \\
   \end{array}
   \right ) " title=" \left (
   \begin{array}{ccc}
      x_1 \\
      x_2 \\
       \vdots \\
      x_n \\
   \end{array}
   \right ) " /> <img src="https://latex.codecogs.com/svg.latex?\Large&space; \in \mathbb{R}^{n}" title=" \in \mathbb{R}^{n}" />
   
   
## 2. Matrice


![image](https://drive.google.com/uc?export=view&id=1Bfh-Mb6Vij_JwKYOMHHN28zXevk133tF)

On note  <img src="https://latex.codecogs.com/svg.latex?\Large&space; M \in\mathbb{R}^{m} \times \mathbb{R}^{n}" title=" M \in\mathbb{R}^{m} \times \mathbb{R}^{n}" /> une matrice à  <img src="https://latex.codecogs.com/svg.latex?\Large&space;m" title="m" /> lignes et  <img src="https://latex.codecogs.com/svg.latex?\Large&space; n" title="n" /> colonnes, où  <img src="https://latex.codecogs.com/svg.latex?\Large&space; M_{i,j} \in \mathbb{R}" title="M_{i,j} \in \mathbb{R}" /> est l'entrée située à la <img src="https://latex.codecogs.com/svg.latex?\Large&space; i^{ieme}" title="i^{ieme}" /> ligne et <img src="https://latex.codecogs.com/svg.latex?\Large&space; j^{ieme}" title="j^{ieme}" /> colonne :

<img src="https://latex.codecogs.com/svg.latex?\Large&space; M = \left (
      \begin{array}{cccc}
      M_{1,1}  & \cdots & M_{1,n} \\
      \vdots & & \vdots \\
      M_{m,1} & \cdots  & M_{m,n} \\
      \end{array}
    \right )  " title="M = \left (
     \begin{array}{cccc}
      M_{1,1}  & \cdots & M_{1,n} \\
      \vdots & & \vdots \\
      M_{m,1} & \cdots  & M_{m,n} \\
        \end{array}
         \right )  " /> <img src="https://latex.codecogs.com/svg.latex?\Large&space; \in \mathbb{R}^{m \times n} " title="\in \mathbb{R}^{m \times n} " />
       
 Remarque: le vecteur <img src="https://latex.codecogs.com/svg.latex?\Large&space; X " title=" X " /> défini ci-dessus peut être vu comme une matrice de taille <img src="https://latex.codecogs.com/svg.latex?\Large&space; n \times 1 " title=" n \times 1 " />, aussi appelé vecteur colonne. 
 
# 3. Matrices particulières

## 3.1 Matrice identité 

 La matrice <img src="https://latex.codecogs.com/svg.latex?\Large&space; I \in \mathbb{R}^{n \times n}" title=" I \in \mathbb{R}^{n \times n} " /> est une matrice carrée n lignes et n colonnes. Tous les éléments de sa diagonale sont égaux à 1 et tous les autres éléments sont égaux à 0. 
 
 <img src="https://latex.codecogs.com/svg.latex?\Large&space;  I = \begin{pmatrix}
    1    & \cdots & 0 \\ 
    \vdots & \ddots & \vdots \\ 
    0      & \cdots & 1 
\end{pmatrix}" title="  I = \begin{pmatrix}
    1    & \cdots & 0 \\ 
    \vdots & \ddots & \vdots \\ 
    0      & \cdots & 1 
\end{pmatrix} " />

Remarquons pour toute matrice <img src="https://latex.codecogs.com/svg.latex?\Large&space; A \in \mathbb{R}^{n \times n}" title=" I \in \mathbb{R}^{n \times n} " />,  on a <img src="https://latex.codecogs.com/svg.latex?\Large&space; A \times I" title=" A \times I " /> = <img src="https://latex.codecogs.com/svg.latex?\Large&space; I \times A" title=" I \times A " /> = <img src="https://latex.codecogs.com/svg.latex?\Large&space; A " title=" A " />. On peut le consider comme l'élément neutre de la multiplication. 

## 3.2 Matrice diagonale

Une matrice diagonale <img src="https://latex.codecogs.com/svg.latex?\Large&space; D \in \mathbb{R}^{n \times n}" title=" D \in \mathbb{R}^{n \times n} " /> est une matrice carrée dont les coefficients en dehors de la **diagonale** principale sont nuls. 

<img src="https://latex.codecogs.com/svg.latex?\Large&space; D = \begin{pmatrix}
    a & 0 & \dots & 0 \\
    0 & 1 & \dots & 0 \\
    \vdots & \vdots & \ddots & \vdots \\
    0 & 0 & \dots & 1
  \end{matrix}" title=" D= \begin{matrix}
    a & 0 & \dots & 0 \\
    0 & 1 & \dots & 0 \\
    \vdots & \vdots & \ddots & \vdots \\
    0 & 0 & \dots & 1
  \end{matrix} " />


## 3.3 Opérations matricielles 

### 3.3.1 Multiplication 


#### Multiplication vecteur vecteur 

On distingue des types de multiplication vecteur-vecteur: 
   - **Produit scalaire**:  Le produit scalaire est différent de la multilication d'un vecteur par un scalaire puisque:
   
        -le produit scalire de deux vecteurs est un nombre réel; les deux opérandes d’un produit scalaire sont des vecteurs;
        
        - les opérandes de la multiplication d’un vecteur par un scalaire sont un vecteur et un nombre réel; le résultat de la multiplication d’un vecteur par un scalaire est un vecteur.
        
        - L’expression « multiplication vectorielle », qui devrait référer à une opération interne dans l’ensemble des vecteurs et qui aurait pour résultat un vecteur, est inappropriée, car le produit scalaire de deux vecteurs est un nombre réel et non un vecteur, alors que la multiplication d’un vecteur par un scalaire est une opération externe.

   Pour <img src="https://latex.codecogs.com/svg.latex?\Large&space; x , y \in \mathbb{R}^{n} " title=" x, y \in \mathbb{R}^{n} " />, on a : 
   
   <img src="https://latex.codecogs.com/svg.latex?\Large&space; x^{T}y = \sum_{i=1}^{n}x_iy_i  \in \mathbb{R}" title=" x^{T}y = \sum_{i=1}^{n}x_iy_i  \in \mathbb{R} " />
        
   - **Produit dyadique** : Le produit dyadique de deux vecteurs, dont chacun ayant la même dimension, est le **produit tensoriel** de ces vecteurs, lequel est un tenseur d'ordre deux et de rang un. Ce produit est souvent utilisé en **mécanique des milieux continus**
   Pour <img src="https://latex.codecogs.com/svg.latex?\Large&space; x \in \mathbb{R}^{m},  y \in \mathbb{R}^{n} " title="x \in \mathbb{R}^{m},  y \in \mathbb{R}^{n} " /> on a : 
   
   <img src="https://latex.codecogs.com/svg.latex?\Large&space; xy^{T} = \left (
      \begin{array}{cccc}
      x_1y_1  & \cdots & x_1y_n \\
      \vdots & & \vdots \\
      x_my_1 & \cdots  & x_my_n \\
      \end{array}
    \right )  " title="xy^{T} = \left (
      \begin{array}{cccc}
      x_1y_1  & \cdots & x_1y_n \\
      \vdots & & \vdots \\
      x_my_1 & \cdots  & x_my_n \\
      \end{array}
    \right )   " /> <img src="https://latex.codecogs.com/svg.latex?\Large&space; \in \mathbb{R}^{m \times n} " title="\in \mathbb{R}^{m \times n} " />
   
   
   
   
#### Matrice- vecteur 

Le produit de la matrice <img src="https://latex.codecogs.com/svg.latex?\Large&space; A \in \mathbb{R}^{m \times n} " title="A \in \mathbb{R}^{m \times n} " /> et du vecteur  <img src="https://latex.codecogs.com/svg.latex?\Large&space; x \in \mathbb{R}^{n} " title="A \in \mathbb{R}^{n} " /> est un vecteur de taille de <img src="https://latex.codecogs.com/svg.latex?\Large&space; \mathbb{R}^{m} " title=" \mathbb{R}^{n} " />, tel que: 


<img src="https://latex.codecogs.com/svg.latex?\Large&space; Ax = \left (
   \begin{array}{ccc}
      a^T_{r,1}x \\
      a^T_{r,2}x \\
      \vdots \\
     a^T_{r,m}x \\
   \end{array}
   \right ) = \sum_{i=1}^{n}a_{c,i}x_i  \in \mathbb{R}^{m} " title=" Ax = \left (
   \begin{array}{ccc}
      a^T_{r,1}x \\
      a^T_{r,2}x \\
      \vdots \\
     a^T_{r,m}x \\
   \end{array}
   \right )  = \sum_{i=1}^{n}a_{c,i}x_i  \in \mathbb{R}^{m} " /> où les
   <img src="https://latex.codecogs.com/svg.latex?\Large&space; a^{T}_{r,i}  " title="a^{T}_{r,i} "/> sont les vecteurs-ligne et <img src="https://latex.codecogs.com/svg.latex?\Large&space; a_{c,i}  " title="a_{c,i} "/> sont les vecteurs-colonne de <img src="https://latex.codecogs.com/svg.latex?\Large&space; A \ et \  x_i  " title=" A et x_i "/> sont les entrées de x. 
   
   
   
#### Matrice-Matrice.

Le produit des matrices <img src="https://latex.codecogs.com/svg.latex?\Large&space; A \in \mathbb{R}^{m \times n }  , \   B \in \mathbb{R}^{n \times p}  " title="A \in \mathbb{R}^{m \times n }  et B \in \mathbb{R}^{n \times p}  "/> est une matrice de taille <img src="https://latex.codecogs.com/svg.latex?\Large&space; \mathbb{R}^{n \times p}  " title="\mathbb{R}^{n \times p} "/> tel que :
   
   <img src="https://latex.codecogs.com/svg.latex?\Large&space; AB = \left (
      \begin{array}{cccc}
      a^T_{r,1}b_{c,1}  & \cdots & a^T_{r,1}b_{c,p} \\
      \vdots & & \vdots \\
      a^T_{r,m}b_{c,1} & \cdots  & a^T_{r,m}b_{c,p} \\
      \end{array}
    \right ) = \sum_{i=1}^{n}a_{c,i}b^{T}_{r,i}  \in \mathbb{R}^{n \times p} " title=" AB = \left (
      \begin{array}{cccc}
      a^T_{r,1}b_{c,1}  & \cdots & a^T_{r,1}b_{c,p} \\
      \vdots & & \vdots \\
      a^T_{r,m}b_{c,1} & \cdots  & a^T_{r,m}b_{c,p} \\
      \end{array}
    \right ) =  \sum_{i=1}^{n}a_{c,i}b^{T}_{r,i}  \in \mathbb{R}^{n \times p} " />


##### Exemples: 

![image](https://drive.google.com/uc?export=view&id=1vm3vRTynlSlqKo8Ysk_vBjx7oyIYrxBk)


#### Produit matriciel Sur python: 

```python
# On définit la fonction permettant de calculer le produit de deux matrices. 
def produit(A, B):
    return [[sum(L[k] * B[k][j] for k in range(len(L))) for j in range(len(B[0]))] for L in A]
   
# On définit les deux matrices A et B 
A = [[1, 7], [2,4]]

B = [[3, 3], [5, 2]]

produit(A, B)
[[38, 17], [26, 14]]

produit(B, A)
[[9, 33], [9, 43]]
````

## 3.4 Autres opérations 

### Transposé
La transposée d'une matrice <img src="https://latex.codecogs.com/svg.latex?\Large&space; A \in \mathbb{R}^{m \times n} " title="A \in \mathbb{R}^{m \times n} " /> est notée <img src="https://latex.codecogs.com/svg.latex?\Large&space; A^T  " title="A^T  " /> et est dans <img src="https://latex.codecogs.com/svg.latex?\Large&space;  \mathbb{R}^{n \times m} " title=" \mathbb{R}^{n \times m} " /> tel que: 

<img src="https://latex.codecogs.com/svg.latex?\Large&space; \forall i, j  A^{T}_{i,j} = A_{j,i} " title="\forall i, j  A^{T}_{i,j} = A_{j,i} " />.


**Remarque** : pour des matrices <img src="https://latex.codecogs.com/svg.latex?\Large&space; A, B  " title=" A, B  " /> on a <img src="https://latex.codecogs.com/svg.latex?\Large&space; (AB)^T " title="B^TA^T " />. 


### Inverse:
L'inverse d'une matrice carrée inversible <img src="https://latex.codecogs.com/svg.latex?\Large&space; A" title="A " /> est notée <img src="https://latex.codecogs.com/svg.latex?\Large&space; A^{-1} " title="A^{-1} " /> et est l'unique matrice telle que: 

<img src="https://latex.codecogs.com/svg.latex?\Large&space; AA^{-1} = A^{-1}A = I  " title=" AA^{-1} = A^{-1}A = I  " />.

#### Exemple 
la matrice de départ 
<img src="https://latex.codecogs.com/svg.latex?\Large&space;   A = \left (
      \begin{array}{cccc}
1 & 2 & 3\\
4 & 5 & 6 \\
7 & 8 & 9 
\end{array}
   \right )   " title=" A = \left (
      \begin{array}{cccc}
1 & 2 & 3\\
4 & 5 & 6 \\
7 & 8 & 9 
\end{array}
   \right )    " />    
   
   
et la matrice transposée           <img src="https://latex.codecogs.com/svg.latex?\Large&space;  A^T = \left (
      \begin{array}{cccc}
1 & 4 & 7\\
2 & 5 & 8 \\
3 & 6 & 9 
\end{array}
   \right )   " title=" A^T = \left (
      \begin{array}{cccc}
1 & 4 & 7\\
2 & 5 & 8 \\
3 & 6 & 9 
\end{array}
   \right )    " />

```python 
import numpy as np 
# On définit la matrice A
A = np.array([[1,2,3],[4,5,6],[7,8,9]])
# On affiche la matrice A
print(A)
# La transposer de la matrice de A
tranposer (A) = A.T
#Avec la fonction transpose de numpy
np.transpose(A)

```



### Trace

La trace d'une matrice carrée <img src="https://latex.codecogs.com/svg.latex?\Large&space; A  " title=" A " />, notée <img src="https://latex.codecogs.com/svg.latex?\Large&space; tr(A) " title=" tr(A)  " />, est la somme de ses entrées diagonales: 

<img src="https://latex.codecogs.com/svg.latex?\Large&space; tr(A) = \sum_{i=1}^{n}A_{i,i}  " title=" tr(A) = \sum_{i=1}^{n}A_{i,i}  " />.

Remarque:  pour toutes matrices <img src="https://latex.codecogs.com/svg.latex?\Large&space; A, B  " title=" A, B " /> on a <img src="https://latex.codecogs.com/svg.latex?\Large&space; tr(A^T) = tr(A)  " title=" tr(A^T) = tr(A) " /> et <img src="https://latex.codecogs.com/svg.latex?\Large&space; tr(A) = \sum_{i=1}^{n}A_{i,i}  " title=" tr(A) = \sum_{i=1}^{n}A_{i,i}  " />. 


# 4. Analyse matricielle

### 4.1 Gradient
Soit <img src="https://latex.codecogs.com/svg.latex?\Large&space; f  " title=" f  " /> une fonction définie  <img src="https://latex.codecogs.com/svg.latex?\Large&space;  \mathbb{R}^{ m \times n}  " title=" \mathbb{R}^{ m \times n}  " /> dans <img src="https://latex.codecogs.com/svg.latex?\Large&space;  \mathbb{R}  " title=" \mathbb{R} " />. Le gradient de <img src="https://latex.codecogs.com/svg.latex?\Large&space; f  " title=" f " /> à  la matrice <img src="https://latex.codecogs.com/svg.latex?\Large&space; A  " title=" A " /> est une matrice de taille <img src="https://latex.codecogs.com/svg.latex?\Large&space; m \times n " title=" m \times n " />, notée <img src="https://latex.codecogs.com/svg.latex?\Large&space; \nabla_{A} f(A)  " title=" \nabla_{A} f(A) " /> tel que: 

 <img src="https://latex.codecogs.com/svg.latex?\Large&space; \left (
      \begin{array}{cccc} \nabla_{A} f(A) \end{array}
   \right )_{i,j}  = \frac{\partial f(A)}{\partial A_{i,j}} " title=" \left (
      \begin{array}{cccc} \nabla_{A} f(A) \end{array}
   \right )_{i,j} = \frac{\partial f(A)}{\partial A_{i,j}}  " />


**Remarque**: Le gradient de f est seulement définit lorsque f est une fonction donnant un scalaire. 

### 4.2 Hessienne 
Soit <img src="https://latex.codecogs.com/svg.latex?\Large&space; f  " title=" f  " /> une fonction définie  <img src="https://latex.codecogs.com/svg.latex?\Large&space;  \mathbb{R}^{ n}  " title=" \mathbb{R}^{n}  " /> dans <img src="https://latex.codecogs.com/svg.latex?\Large&space;  \mathbb{R}  " title=" \mathbb{R} " /> et <img src="https://latex.codecogs.com/svg.latex?\Large&space; x \in \mathbb{R}^{n}  " title=" x \in \mathbb{R}^{n} " /> un vecteur.  La hessienne de  de <img src="https://latex.codecogs.com/svg.latex?\Large&space; f  " title=" f " /> par rapport à <img src="https://latex.codecogs.com/svg.latex?\Large&space; x  " title=" x " /> est une matrice de taille <img src="https://latex.codecogs.com/svg.latex?\Large&space; n \times n " title=" n \times n " />, notée <img src="https://latex.codecogs.com/svg.latex?\Large&space; \nabla_{x}^2 f(A)  " title=" \nabla_{x}^2 f(A) " /> , telle que: 

 <img src="https://latex.codecogs.com/svg.latex?\Large&space; \left (
      \begin{array}{cccc} \nabla_{x}^2 f(x) \end{array}
   \right )_{i,j}  = \frac{\partial^2 f(x)}{\partial x_i \partial x_j} " title=" \left (
      \begin{array}{cccc} \nabla_{x}^2 f(x) \end{array}
   \right )_{i,j}  = \frac{\partial^2 f(x)}{\partial x_i \partial x_j}  " />
   
   **Remarque** La hessienne de f est seulement définie lorsque f est une fonction qui donne un scalaire. 
   
   
   
                                                  PSW 
                                                  

## 4.3 Application: Gradient Descent in Python (la descente du grndient) 

```python 
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
plt.style.use(['ggplot'])
```

### Création de données 

 Soient <img src="https://latex.codecogs.com/svg.latex?\Large&space; \theta_0 = 4  \  \theta_1 = 3  " title=" \theta_0 = 4  \  \theta_1 = 3 " /> 
 
```python 
X = 2 * np.random.rand(100,1)
y = 4 +3 * X+np.random.randn(100,1)
```
**Affichage des données**
```python
plt.plot(X,y,'b.')
plt.xlabel("$x$", fontsize=18)
plt.ylabel("$y$", rotation=0, fontsize=18)
_ =plt.axis([0,2,0,15])
```

![image](https://drive.google.com/uc?export=view&id=1eygYRmMw_dEspG9-7wWuFRfNA2lFKfyP)


**Faisons une première approche de regression linéaire**

```pyhon 
X_b = np.c_[np.ones((100,1)),X]
theta_best = np.linalg.inv(X_b.T.dot(X_b)).dot(X_b.T).dot(y)
print(theta_best)
```
[[3.8635763 ]
 [3.08973657]]


```python
X_new = np.array([[0],[2]])
X_new_b = np.c_[np.ones((2,1)),X_new]
y_predict = X_new_b.dot(theta_best)
y_predict
```
array([[ 3.8635763 ],
       [10.04304945]])

**affichage de la droite de regression**

```python
plt.plot(X_new,y_predict,'r-')
plt.plot(X,y,'b.')
plt.xlabel("$x_1$", fontsize=18)
plt.ylabel("$y$", rotation=0, fontsize=18)
plt.axis([0,2,0,15])

```

![image](https://drive.google.com/uc?export=view&id=1bNog0oFQyZeUuirW0TUuHFmzYQRNcUzS)

### Gardient Descent 
Dans un nouveau poste ! On verra comment implémenter l'équation du gradient et de la fonction coût sur python. 

             coming soon 
