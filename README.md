# FIN8311 : stabilité du modèle de Fama-French (OLS, Ridge, Lasso)

Projet de session du cours FIN8311 (Méthodes quantitatives en finance), UQAM.
Équipe: , .

*Cette page est un guide pour l'équipe. Le code à lire et à vérifier est dans le notebook.*

## Problématique
Le modèle de Fama-French explique le rendement d'un panier d'actions avec trois facteurs :
le marché (`Mkt-RF`), la taille (`SMB`) et la valeur (`HML`).
Avec peu de mois de données, les coefficients β estimés par moindres carrés (OLS) peuvent être instables.

**Question** : les β et les facteurs retenus changent-ils entre une période de crise et une période de calme ?
Ridge et Lasso donnent-ils des résultats plus stables ou plus lisibles que l'OLS ?

## Le fichier du dépôt
`FIN8311_Fama_French_Ridge_Lasso.ipynb` : notebook commenté en français, de l'import des données jusqu'au tableau final.

## Données (à télécharger, non incluses)
Source : [bibliothèque de données de Kenneth French](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html)
- `F-F_Research_Data_Factors.csv` : facteurs et taux sans risque, mensuel, en %.
- `6_Portfolios_2x3.csv` : 6 paniers taille x valeur, mensuel, en %.

## Les deux périodes comparées
- **Crise** : 2007-12 à 2009-06 et 2020-02 à 2020-04 (22 mois).
- **Calme** : 2013-01 à 2014-10 (22 mois).
- Robustesse (optionnelle) : calme long 2013-01 à 2019-12 (84 mois).

## Méthode en 5 étapes
1. Rendement excédentaire du panier = rendement − taux sans risque.
2. Régression OLS par période (β et erreurs standards).
3. Standardisation des facteurs, puis Ridge et Lasso.
4. Choix de la pénalité par validation croisée et règle 1-SE pour le Lasso.
5. Tableau final : facteurs éliminés par le Lasso, par panier et par période.

## Comment obtenir les résultats
1. Télécharger les deux fichiers CSV ci-dessus.
2. Ouvrir le notebook dans Google Colab (*Fichier → Importer le notebook*).
3. *Exécution → Tout exécuter*. À la section 2, Colab demande les deux fichiers : les sélectionner.
4. Enregistrer les graphiques (clic droit) et prendre une capture des tableaux pour le rapport et le PowerPoint.

## Pour l'équipe : où on en est
| Partie | État |
| --- | --- |
| Code | Fait |
| Résultats (tableaux, graphiques) | À exécuter dans Colab |
| Rapport écrit (10 pages, sans les annexes) | À faire |
| PowerPoint | À faire |
| Tout le monde comprend la méthode | À faire avant la présentation |

## Plan du rapport
1. Sommaire
2. Problématique
3. Données
4. Méthode (OLS, Ridge, Lasso, validation croisée)
5. Résultats (crise contre calme)
6. Conclusion et limites
7. Annexes : le code complet (non compté dans les 10 pages)

## Limites
22 mois par période, 3 facteurs seulement, facteurs construits à partir des mêmes paniers, un seul réglage de validation croisée, dates de crise choisies par l'équipe.
