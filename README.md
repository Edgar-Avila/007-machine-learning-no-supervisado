---
title: "Aprendizaje no supervisado"
author: ["Avila Agramonte, Edgar"]
date: "19/09/2026"
subject: "Aprendizaje no supervisado"
keywords: [Aprendizaje no supervisado, Machine Learning]
subtitle: "MCD202 - Machine Learning"
lang: "es"
titlepage: true,
titlepage-text-color: "FFFFFF"
titlepage-rule-color: "360049"
titlepage-rule-height: 0
titlepage-background: "background.pdf"
---

## Análisis de los modelos y sus hiperparámetros

### Naturaleza de los modelos

K-Means es un modelo lineal: Usa fronteras de decisión lineales. Con Iris
funciona bien porque las clases están agrupadas en formas compactas, pero falla
en Moons y Circles porque no captura geometrías complejas.

DBSCAN es un modelo no lineal: agrupa puntos según la densidad local de la
vecindad y descubre clusters de cualquier forma geométrica. Funciona bien en
Moons y Circles. 

Spectral Clustering es un modelo no lineal: Proyecta los datos en un espacio de
menor dimensión y después aplica K-means sobre ese espacio. Captura bien
estructuras no lineales complejas, como Moons y Circles.

### Hiperparámetros

K-Means, `n_clusters` indica el número de centroides a ubicar. `init` define la
estrategia de inicialización (por defecto `k-means++`, para evitar mínimos
locales deficientes).

En DBSCAN, `eps` es la distancia máxima para que dos puntos se consideren
vecinos. Si es muy pequeña, los datos se clasifican como ruido (clase -1); si
es muy grande, todos se unen en un único cluster. `min_samples` es el número
mínimo de puntos que necesita la vecindad de un punto para considerarlo punto
núcleo y controla la tolerancia al ruido.

En Spectral Clustering, `n_clusters` define el número de clusters. `affinity` y
`gamma` definen cómo se mide la similitud entre los puntos.
