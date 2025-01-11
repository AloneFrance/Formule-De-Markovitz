Optimisation de Portefeuille - Minimisation de la Volatilité
Ce projet propose une méthode d'optimisation de portefeuille basée sur la minimisation de la volatilité sous certaines contraintes. L'objectif est de trouver les poids optimaux des actifs qui minimisent la variance du portefeuille tout en satisfaisant les contraintes classiques de portefeuille. Cette méthode repose sur des formules de base issues de la théorie de la gestion de portefeuille moderne, en utilisant des matrices de covariance et des coefficients de corrélation.

Introduction
L'optimisation de portefeuille vise à répartir les investissements entre différents actifs de manière optimale, en tenant compte du rendement et du risque (volatilité). Ce projet se concentre sur la minimisation de la volatilité globale du portefeuille, tout en garantissant que la somme des poids des actifs soit égale à 1 et que tous les investissements soient longs (pas de vente à découvert).

Objectifs
Minimiser la volatilité totale du portefeuille.
Respecter les contraintes suivantes :
La somme des poids des actifs doit être égale à 1.
Les poids des actifs doivent être positifs (pas de vente à découvert).
Formules Mathématiques
Variance du Portefeuille
La variance du portefeuille 
𝜎
𝑝
2
σ 
p
2
​
  est une combinaison pondérée des variances et des covariances des actifs. Elle est calculée comme suit :

𝜎
𝑝
2
=
∑
𝑖
=
1
𝑛
∑
𝑗
=
1
𝑛
𝑤
𝑖
𝑤
𝑗
𝜌
𝑖
𝑗
𝜎
𝑖
𝜎
𝑗
σ 
p
2
​
 = 
i=1
∑
n
​
  
j=1
∑
n
​
 w 
i
​
 w 
j
​
 ρ 
ij
​
 σ 
i
​
 σ 
j
​
 
𝑤
𝑖
w 
i
​
  : Poids de l'actif 
𝑖
i dans le portefeuille.
𝜌
𝑖
𝑗
ρ 
ij
​
  : Coefficient de corrélation entre les actifs 
𝑖
i et 
𝑗
j.
𝜎
𝑖
σ 
i
​
 , 
𝜎
𝑗
σ 
j
​
  : Écarts-types des rendements des actifs 
𝑖
i et 
𝑗
j.
Vecteur des Poids du Portefeuille
Le vecteur des poids 
𝑊
W représente les proportions investies dans chaque actif du portefeuille. Il est défini par :

𝑊
=
[
𝑤
1
,
𝑤
2
,
…
,
𝑤
𝑛
]
W=[w 
1
​
 ,w 
2
​
 ,…,w 
n
​
 ]
Contraintes
Somme des poids égale à 1 :
∑
𝑙
=
1
𝑛
𝑤
𝑙
=
1
l=1
∑
n
​
 w 
l
​
 =1
Cela garantit que l'ensemble du capital est investi.

Positivité des poids :
𝑤
𝑖
≥
0
∀
 
𝑖
w 
i
​
 ≥0∀i
Cela impose que les investissements soient longs (pas de vente à découvert).

Formule pour un Poids Individuel
Le poids optimal 
𝑤
𝑖
w 
i
​
  d'un actif 
𝑖
i peut être calculé à partir de l'expression suivante qui découle de l'optimisation des poids pour minimiser la variance du portefeuille :

𝑤
𝑖
=
1
𝜎
𝑖
2
(
1
−
∑
𝑖
≠
𝑗
𝜌
𝑖
𝑗
𝜎
𝑗
𝜎
𝑖
)
∑
𝑘
=
1
𝑛
1
𝜎
𝑘
2
(
1
−
∑
𝑙
≠
𝑘
𝜌
𝑘
𝑙
𝜎
𝑙
𝜎
𝑘
)
w 
i
​
 = 
σ 
i
2
​
 
1
​
  
​
 1− 
i

=j
∑
​
 ρ 
ij
​
  
σ 
i
​
 
σ 
j
​
 
​
  
​
  
k=1
∑
n
​
  
σ 
k
2
​
 
1
​
  
​
 1− 
l

=k
∑
​
 ρ 
kl
​
  
σ 
k
​
 
σ 
l
​
 
​
  
​
 
Expression Matricielle des Poids Optimaux
Les poids optimaux peuvent être calculés de manière plus compacte en utilisant une formulation matricielle :

𝑊
=
(
𝐶
−
1
⋅
1
)
⋅
1
1
𝑇
⋅
𝐶
−
1
⋅
1
W=(C 
−1
 ⋅1)⋅ 
1 
T
 ⋅C 
−1
 ⋅1
1
​
 
𝐶
C : Matrice de covariance des rendements des actifs.
1
1 : Vecteur colonne de 1 (représentant la contrainte de somme des poids égale à 1).
𝐶
−
1
C 
−1
  : Inverse de la matrice de covariance.
Méthodologie
Étapes de l'Optimisation
Calcul des rendements et de la matrice de covariance :

Calculer les rendements historiques des actifs.
Calculer la matrice de covariance des rendements des actifs.
Formulation du problème d'optimisation :

Minimiser la variance sous la contrainte que la somme des poids soit égale à 1.
Imposer la contrainte que tous les poids soient positifs (pas de vente à découvert).
Calcul des poids optimaux :

Résoudre le problème d'optimisation en utilisant la méthode de l'inverse de la matrice de covariance.
Validation des résultats :

Vérifier que la somme des poids est égale à 1.
Vérifier que les poids sont positifs.
Ajustement en fonction des objectifs :

Si vous avez un objectif de volatilité spécifique, ajustez les poids en conséquence en ajoutant des contraintes supplémentaires.
Exemple d'Application
Calcul des Poids Optimaux
Supposons que vous ayez un portefeuille avec 3 actifs, dont les rendements historiques et les écarts-types sont les suivants :

Actif 1 : 
𝜇
1
=
0.12
μ 
1
​
 =0.12, 
𝜎
1
=
0.2
σ 
1
​
 =0.2
Actif 2 : 
𝜇
2
=
0.08
μ 
2
​
 =0.08, 
𝜎
2
=
0.15
σ 
2
​
 =0.15
Actif 3 : 
𝜇
3
=
0.1
μ 
3
​
 =0.1, 
𝜎
3
=
0.18
σ 
3
​
 =0.18
La matrice de covariance des rendements est calculée à partir des rendements historiques des actifs.

Vous pouvez ensuite appliquer la méthode matricielle pour calculer les poids optimaux.

Prérequis
Python (version 3.6 ou supérieure)
Bibliothèques Python : numpy, pandas, cvxpy, matplotlib
Installation des Dépendances
bash
Copier le code
pip install numpy pandas cvxpy matplotlib
Utilisation
Voici un exemple de code en Python pour calculer les poids optimaux à partir des rendements des actifs et de leur matrice de covariance :

python
Copier le code
import numpy as np
import pandas as pd
import cvxpy as cp

# Exemples de rendements des actifs (cette partie doit être calculée à partir des données historiques)
rendements = np.array([0.12, 0.08, 0.10])  # Rendements moyens
covariance = np.array([[0.04, 0.02, 0.01],
                       [0.02, 0.03, 0.015],
                       [0.01, 0.015, 0.03]])  # Matrice de covariance

# Poids initiaux
n = len(rendements)
poids = cp.Variable(n)

# Contrainte de somme des poids égale à 1
contraintes = [cp.sum(poids) == 1, poids >= 0]

# Fonction de coût : minimisation de la variance du portefeuille
variance_portefeuille = cp.quad_form(poids, covariance)

# Problème d'optimisation
probleme = cp.Problem(cp.Minimize(variance_portefeuille), contraintes)

# Résolution
probleme.solve()

# Affichage des poids optimaux
print("Poids optimaux : ", poids.value)
Conclusion
Ce projet permet d'optimiser un portefeuille en minimisant la volatilité tout en respectant des contraintes classiques comme la somme des poids égale à 1 et la positivité des poids. L'approche matricielle permet de résoudre efficacement le problème d'optimisation, offrant une solution robuste pour la gestion de portefeuille.
