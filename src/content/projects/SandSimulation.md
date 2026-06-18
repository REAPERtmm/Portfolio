---
title: 'SandSimulation'
description: 'A sand simultation made in C++ optimized with multi-threading'
pubDate: 'Nov 28 2025'
heroImage: '../../assets/SandSimulation/thumbnail.png'
---

## Contexte du projet

Dans ce projet nous avions comme consigne de faire une simulation de particule massive et d'optimiser cette simulation avec le multi-threading en C++. Mais avec interdiction d'utiliser STD pour la partie threading. Nous avions pour obligation d'utiliser l'API windows C++ de base.
Pour répondre à la consigne, j'ai décidé de créer une simulation de sable avec pour idée de créer un cellular automaton optimisé.

![Simulation](../../assets/SandSimulation/thumbnail.png)

## Solution apportée

Pour gérer le multi-threading, nous avons construit un architecture où le thread fonctionne par pair (Thread et ThreadHandle) le premier sert du côté de la création et l'accession à un thread et l'autre sert à la gestion du thread du côté de celui ci. Ainsi le main thread n'effectue aucune opération directement sur les données du thread et inversement, le thread ne peux manipuler que les données que le main thread aura bien voulu lui laissé. En plus de proposer une multitude de fonction pratique pour vérifier et coordonner différents thread. 
Et en parlant de coordonner les theads, j'ai réfléchi à un autre object qui permettrait de synchroniser plusieurs liste de threads. J'ai appelé cette object un ThreadScheduler. Elle me permet de lancer plusieurs thread en parrallele et d'attendre qu'il ait tous fini pour lancer la liste suivante de thread, synchonisant le relâchement des données pour le proccessus suivant.
Cela a été utile notamment lors du partitionnement de l'espace en sous groupe, il faut impérativement que les thread qui tourne en même temps ne travaille jamais sur deux groupe voisin sinon ils peuvent écrire sur la même case.
Une autre optimisation a été de n'update uniquement les particules qui peuvent bouger. Cela est obtenu en updatant uniquement les groupes qui ont reçu une modification la frame précédente.

![Simulation Video](../../assets/SandSimulation/video.mp4)

## Difficulté rencontré 

Les principale enjeux de ce projet était d'éviter les race condition, notement en évitant les threads voisin comme dis précédement.
une autre difficulté fût aussi quand deux grain des sable sont sensé arriver sur la même case, il faut éviter que l'un override l'autre.

## Conclusion 

Le programme permet l'addition de deux couleurs de sables différents qui sont capable de tomber et de s'empiler, ainsi que de la pierre qui est immobile. Il est aussi possible de supprimer n'importe quel particule. et enfin il existe un générateur à sable qui fait automatiquement apparaitre un grain de sable sur une case voisine à chaque iteration. 
Niveau performance, je peux remplir l'écran de particule et garder un framerate élevée, sachant que chaque pixel est une particule (je lance le programme sur un proccesseur avec 12 thread simultané max). 