# Minuterie numérique sur FPGA

Projet de conception numérique visant à réaliser une minuterie matérielle sur FPGA en VHDL.

## Objectif

Décomposer une minuterie en blocs synchrones simples afin de mettre en pratique :

- la conception d'une machine à états ;
- les compteurs et diviseurs d'horloge ;
- la gestion de boutons poussoirs ;
- le multiplexage d'un afficheur ;
- la simulation et la validation temporelle ;
- la synthèse sur FPGA.

## Architecture prévue

```text
Horloge FPGA
     |
     v
Diviseur d'horloge
     |
     v
Compteur de temps <---- Commandes utilisateur
     |
     v
Conversion d'affichage
     |
     v
Afficheur 7 segments
```

## Fonctions visées

- démarrage et pause ;
- remise à zéro ;
- réglage de la durée ;
- décompte à la seconde ;
- affichage des minutes et secondes ;
- signal de fin de minuterie.

## Méthode de validation

Chaque bloc doit être testé séparément avec un banc de test avant l'intégration :

1. vérifier la période générée par le diviseur d'horloge ;
2. contrôler les transitions de la machine à états ;
3. tester les limites et la remise à zéro du compteur ;
4. valider le multiplexage de l'afficheur ;
5. comparer les chronogrammes simulés au comportement attendu sur la carte.

## Technologies

- VHDL
- FPGA
- simulation RTL
- synthèse et implémentation matérielle

## État du dépôt

Le dépôt contient actuellement la documentation initiale du projet. Les sources VHDL, contraintes de brochage, bancs de test et résultats de simulation seront ajoutés au fur et à mesure de leur validation.

## Auteure

Tedj El Moulk Sinacer
