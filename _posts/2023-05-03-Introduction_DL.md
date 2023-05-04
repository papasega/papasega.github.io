---
layout: post
title: Introduction au Deep Learning partie 1
subtitle: Comprendre les concepts fondamentaux
date: 2023-05-03
bigimg: img/deep_learning.gif
share-img: img/neural_network.jpg
tags: [Deep Learning, AI, Neural Networks]
comments: true
categories: deep-learning
---

# Introduction au Deep Learning : Tutoriel et Exemples de Code

Dans cet article, nous allons vous initier au monde fascinant du deep learning. N'ayez crainte, nous utiliserons un langage simple et accessible pour expliquer les concepts clés et vous aider à démarrer.

## Qu'est-ce que le Deep Learning ?

Le deep learning est une branche de l'intelligence artificielle (IA) qui se concentre sur l'apprentissage des réseaux de neurones artificiels, appelés réseaux de neurones profonds. Ces réseaux sont inspirés du fonctionnement du cerveau humain et permettent aux machines d'apprendre par elles-mêmes à partir de grandes quantités de données.

## Les réseaux de neurones artificiels

Un réseau de neurones est composé de couches de neurones interconnectés. Chaque neurone reçoit des entrées, effectue un calcul et produit une sortie. Les entrées sont pondérées par des poids, qui sont ajustés lors de l'apprentissage pour améliorer la performance du réseau. Les calculs effectués par un neurone peuvent être représentés par l'équation suivante :

$$
y = f\left(\sum_{i=1}^n w_i x_i + b\right)
$$

où $x_i$ sont les entrées, $w_i$ sont les poids, $b$ est le biais et $f$ est la fonction d'activation.


<img src="/img/neural_net.gif" alt="Neural Network Architecture" title="Architecture d'un Réseau de Neurone: source 3Blue1Brown">


Les réseaux de neurones profonds (DNN) sont des réseaux de neurones avec un grand nombre de couches cachées entre l'entrée et la sortie. Ces couches supplémentaires permettent au réseau d'apprendre des représentations de plus en plus abstraites et complexes des données.

## Entraînement des réseaux de neurones

L'entraînement d'un réseau de neurones consiste à ajuster les poids et les biais des connexions entre les neurones afin de minimiser l'erreur entre les prédictions du réseau et les valeurs réelles.

Le processus d'entraînement utilise généralement la rétropropagation ou (Back Propagation en anglais), qui est une méthode pour calculer les gradients de l'erreur par rapport aux poids et aux biais. Ces gradients sont ensuite utilisés pour mettre à jour les poids et les biais à l'aide d'un algorithme d'optimisation, tel que la descente de gradient stochastique (SGD).

### Premiers pas : Installation des bibliothèques

Pour commencer, vous devez installer les bibliothèques nécessaires. Dans cet exemple, nous utiliserons TensorFlow et Keras, deux bibliothèques populaires pour le deep learning en Python. Pour les installer, ouvrez votre terminal et tapez :

```python
pip install tensorflow
```

### Création d'un modèle simple de deep learning

Maintenant que les bibliothèques sont installées, nous allons créer un modèle de deep learning simple pour illustrer comment fonctionne un réseau de neurones. Dans cet exemple, nous utiliserons un réseau de neurones pour résoudre un problème de classification d'images.

#### Importation des bibliothèques

Tout d'abord, importons les bibliothèques nécessaires :

```python
import tensorflow as tf
from tensorflow import keras
```

#### Chargement des données
Nous utiliserons l'ensemble de données Fashion MNIST pour cet exemple. Il s'agit d'un ensemble de 70 000 images en niveaux de gris, représentant 10 catégories de vêtements. Chaque image a une résolution de 28x28 pixels. Importons et chargeons ces données :


```python
fashion_mnist = keras.datasets.fashion_mnist
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
```
#### Prétraitement des données
Avant de créer le modèle, il est important de normaliser les données. Cela signifie que nous devons convertir les valeurs de chaque pixel (0 à 255) en une valeur comprise entre 0 et 1. Voici comment faire :


```python
train_images = train_images / 255.0
test_images = test_images / 255.0
```
#### Création du modèle
Maintenant que les données sont prêtes, nous pouvons créer notre modèle de deep learning. Dans cet exemple, nous utiliserons un modèle séquentiel simple avec trois couches :

    - Une couche d'aplatissement pour transformer les images 2D (28x28 pixels) en un tableau 1D (784 pixels)
    - Une couche dense avec 128 neurones et une fonction d'activation ReLU
    - Une couche dense avec 10 neurones (un pour chaque catégorie) et une fonction d'activation softmax
Voici comment créer ce modèle avec Keras :

```python
model = keras.Sequential([
    keras.layers.Flatten(input_shape=(28, 28)),
    keras.layers.Dense(128, activation='relu'),
    keras.layers.Dense(10, activation='softmax')
])
```

#### Compilation du modèle
Avant de commencer l'entraînement, nous devons compiler notre modèle. Pour cela, nous devons définir la fonction de perte, l'optimiseur et les métriques que nous souhaitons suivre pendant l'entraînement. Dans cet exemple, nous utiliserons :

    - La fonction de perte sparse_categorical_crossentropy, adaptée aux problèmes de classification avec plusieurs catégories
    - L'optimiseur Adam, qui ajuste automatiquement le taux d'apprentissage pour une meilleure convergence
    - La métrique accuracy pour suivre la précision de notre modèle
Voici comment compiler le modèle :



```python
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
```
#### Entraînement du modèle
Il est maintenant temps d'entraîner notre modèle. Pour cela, nous utiliserons la méthode fit() en fournissant nos données d'entraînement et en définissant le nombre d'époques (itérations sur l'ensemble des données). Dans cet exemple, nous utiliserons 10 époques :

```python
model.fit(train_images, train_labels, epochs=10)
```
#### Évaluation du modèle
Une fois l'entraînement terminé, nous pouvons évaluer la performance de notre modèle sur l'ensemble de données de test en utilisant la méthode evaluate() :


```python
test_loss, test_acc = model.evaluate(test_images, test_labels)
print(f"Précision du modèle sur les données de test : {test_acc:.2f}")
```

#### Prédictions
Enfin, nous pouvons utiliser notre modèle entraîné pour prédire les catégories des images de test en utilisant la méthode predict() :



```python
Prédictions
Enfin, nous pouvons utiliser notre modèle entraîné pour prédire les catégories des images de test en utilisant la méthode predict() :
```

Les prédictions sont représentées sous forme de tableaux contenant les scores de confiance pour chaque catégorie. Pour obtenir l'indice de la catégorie avec le score le plus élevé, nous pouvons utiliser la fonction argmax() de NumPy :

```python
import numpy as np
predicted_labels = np.argmax(predictions, axis=1)

```

#### Visualisation des prédictions
Pour rendre notre tutoriel plus interactif, nous pouvons ajouter une visualisation des prédictions de notre modèle. Nous allons créer une fonction pour afficher les images de test avec les prédictions et les étiquettes réelles.

Tout d'abord, importons les bibliothèques nécessaires :


```python
import matplotlib.pyplot as plt

```
Ensuite, créons la fonction de visualisation :

```python
def plot_image(i, predictions_array, true_label, img):
    predicted_label = np.argmax(predictions_array)
    plt.grid(False)
    plt.xticks([])
    plt.yticks([])
    plt.imshow(img, cmap=plt.cm.binary)
    
    if predicted_label == true_label:
        color = 'blue'
    else:
        color = 'red'
    
    plt.xlabel(f"{predicted_label} ({100*np.max(predictions_array):2.0f}%), vrai : {true_label}", color=color)

def plot_predictions(i, predictions_array, true_label):
    plt.grid(False)
    plt.xticks(range(10))
    plt.yticks([])
    thisplot = plt.bar(range(10), predictions_array, color="#777777")
    plt.ylim([0, 1])
    predicted_label = np.argmax(predictions_array)
    
    thisplot[predicted_label].set_color('red')
    thisplot[true_label].set_color('blue')


```

Maintenant, utilisons cette fonction pour afficher quelques exemples de prédictions :

```python
num_rows = 5
num_cols = 3
num_images = num_rows * num_cols
plt.figure(figsize=(2 * 2 * num_cols, 2 * num_rows))

for i in range(num_images):
    plt.subplot(num_rows, 2 * num_cols, 2 * i + 1)
    plot_image(i, predictions[i], test_labels[i], test_images[i])
    plt.subplot(num_rows, 2 * num_cols, 2 * i + 2)
    plot_predictions(i, predictions[i], test_labels[i])

plt.tight_layout()
plt.show()

```


# Applications du Deep Learning
Le Deep Learning a été utilisé avec succès dans divers domaines, tels que la vision par ordinateur, le traitement automatique du langage naturel (TALN), la reconnaissance vocale et la synthèse vocale. Parmi les exemples notables d'applications, on peut citer la classification d'images, la traduction automatique, la génération de texte et la détection d'objets.

Le Deep Learning continue de révolutionner notre façon de résoudre des problèmes complexes et de créer des solutions innovantes. Les recherches se poursuivent pour améliorer les performances, l'efficacité et la compréhension des modèles de Deep Learning.

## Les défis du Deep Learning

Malgré les succès du Deep Learning, il reste des défis à surmonter. Parmi ces défis, on peut citer :

1. **L'interprétabilité des modèles** : Les modèles de Deep Learning sont souvent considérés comme des "boîtes noires" car il est difficile de comprendre comment ils prennent des décisions. Des recherches sont en cours pour développer des méthodes permettant d'expliquer les prédictions des modèles et d'améliorer leur interprétabilité.

2. **Les exigences en matière de données** : Le Deep Learning nécessite généralement de grandes quantités de données pour entraîner des modèles performants. L'acquisition et l'étiquetage de ces données peuvent être coûteux et fastidieux. Des approches telles que l'apprentissage par transfert et l'apprentissage peu supervisé sont explorées pour réduire la dépendance aux ensembles de données étiquetées volumineux.

3. **La complexité computationnelle** : Les modèles de Deep Learning peuvent être très gourmands en ressources computationnelles, ce qui peut entraîner des coûts élevés et un impact environnemental. Des recherches sont menées pour développer des modèles plus efficaces et des techniques d'entraînement accéléré.

4. **Le biais et l'équité** : Les modèles de Deep Learning apprennent à partir de données qui peuvent contenir des biais implicites ou explicites. Cela peut entraîner des prédictions discriminatoires ou injustes. Des efforts sont déployés pour développer des méthodes permettant d'identifier et de corriger ces biais dans les modèles et les données.

## Conclusion

Le Deep Learning est un domaine en pleine expansion qui continue de révolutionner divers secteurs et applications. En comprenant les concepts fondamentaux et en suivant les développements récents, les praticiens peuvent tirer parti de cette technologie pour résoudre des problèmes complexes et créer des solutions innovantes. La recherche continue de relever les défis associés au Deep Learning et d'élargir ses possibilités pour l'avenir.

Cela conclut notre tutoriel d'introduction au deep learning. Vous devriez maintenant avoir une compréhension de base des réseaux de neurones et de la manière de créer et d'entraîner un modèle simple en utilisant TensorFlow et Keras. Continuez à explorer le monde passionnant du deep learning et à approfondir vos connaissances en expérimentant différents types de modèles, d'architectures et de techniques d'apprentissage. Bonne chance et amusez-vous bien !


