# SNCF
L'objectif de ce défi pour Transilien SNCF Voyageurs est de vous faire prédire, à court terme, le temps d'attente pour un train situé à deux gares en amont. Pour évaluer les performances de notre algorithme, nous proposons de prédire la différence entre le temps d'attente théorique et le temps d'attente réel à chaque station sur plusieurs jours.
Structure des données

Un ensemble de données x-train.csv avec 667,265 lignes (c'est-à-dire 667,265 buttes k, s, d) et 10 colonnes.
Un ensemble de données x.test.csv avec 20 658 lignes (c'est-à-dire 20 658 arrêts k, s, d) et 12 colonnes.
Un ensemble de données y-train.csv avec 667,265 lignes et une colonne, fournissant la variable pour prédire l'ensemble de données d'apprentissage.


Ces données proviennent d'applications commerciales qui fournissent des heures d'arrivée et de départ théoriques et observées dans les gares.
Les données anonymisées sont structurées comme suit: une observation représente une escale de train (cle-train) à une gare donnée (c'gare) un jour (date) spécifique. La variable p0q0 est la différence entre les temps d'attente théorique et réel. S'il est négatif, le temps d'attente est plus long que prévu; sinon, il est plus court. Le décalage temporel d'attente est un entier, car, par souci de simplicité, nous n'exhibons qu'à nos passagers sur les écrans.

p définit les valeurs passées pour le train précédent à la même gare.
q définit les valeurs passées pour les arrêts précédents pour un même train.
Le décalage temporel d'attente observé est p0q0, qui est la différence de temps d'attente, noté Y(k,s,d), pour un arrêt, c'est-à-dire un train k à la gare du jour d.

Les colonnes, c'est-à-dire les variables explicatives, correspondent à 4 variables contextuelles et 6 valeurs passées:
Variables contextuelles:

    train (k): numéro de train (unique par jour).
    la gare (s): l'identifiant de la station.
    d) : AAAA-MM-JJ, la date à laquelle le train circule.
    arret: numéro d'arrêt.

Variables passées:

    p2q0: différence de temps d'attente pour le même train k à la deuxième gare précédente s-2.
    p3q0: différence de temps d'attente pour le même train k à la troisième gare précédente s-3.
    p4q0: différence de temps d'attente pour le même train k à la quatrième gare précédente s-4.
    p0q2: différence de temps d'attente pour le deuxième train précédent k-2 à la gare s.
    p0q3: différence de temps d'attente pour le troisième train précédent k-3 à la gare s.
    p0q4: différence de temps d'attente pour le quatrième train précédent k-4 à la gare s.


Critères de référence :

Le modèle de référence utilisé dans ce défi est un modèle de forêt aléatoire classique.
Mesure :

La métrique utilisée pour ce défi est une MAE (Mean Absolute Error).
