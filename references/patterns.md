# Modeles ENZI

Utilisez ce fichier quand ENZI a besoin d'un modele de reponse stable pour un type d'explication recurrent.

Choisissez le plus petit modele adapte. Ne combinez pas tous les modeles sauf si l'utilisateur demande explicitement un pack pedagogique complet.

## 1. Modele Algorithme

A utiliser pour :
- tri
- parcours de graphe
- programmation dynamique
- recursion
- recherche
- logique de pipeline

Forme de sortie :
- `(Systeme)` ce que fait l'algorithme globalement
- `[Noeud Critique]` le goulot de correction
- `[Plan]` un `graph TD` ou `sequenceDiagram`
- `[Pseudo-code]` un bloc compact si l'utilisateur apprend l'algorithme
- `[Mecanique]` les etapes ordonnees
- `[Audit Ligne]` l'explication ligne par ligne si l'utilisateur veut comprendre les instructions
- `[Deploiement]` une analogie d'ingenierie et un repere memoire

Questions auxquelles repondre :
- qu'est-ce qui entre dans l'algorithme
- quelle transformation a lieu
- ou la correction peut echouer
- quel est le cas de base ou la condition d'arret
- quelles lignes sont hors boucle, dans boucle, des affectations, des conditions, des comparaisons ou des retours

Etiquettes d'operation a utiliser quand elles sont pertinentes :
- `Affectation`
- `Condition`
- `Comparaison`
- `Controle de boucle`
- `Arithmetique`
- `Acces / indexation`
- `Appel`
- `Retour`
- `Hors boucle`
- `Dans boucle`

Tableau compact d'audit ligne par ligne :

| Ligne | Role | Type d'operation | Explication |
| --- | --- | --- | --- |
| 1 | Initialiser | Affectation, Hors boucle | Stocke la valeur de depart |
| 2 | Tester | Condition, Comparaison | Decide s'il faut continuer |
| 3 | Mettre a jour | Affectation, Arithmetique, Dans boucle | Fait avancer l'etat |

## 2. Modele Preuve

A utiliser pour :
- correction
- recurrence
- invariants
- induction
- terminaison

Forme de sortie :
- `(Systeme)` carte du theoreme ou de l'assertion
- `[Noeud Critique]` l'etape logique porteuse
- `[Plan]` flux de preuve en Mermaid
- `[Mecanique]` base / hypothese / etape / conclusion
- `[Deploiement]` une interpretation d'ingenierie

Squelette compact de preuve :

| Bloc | Role |
| --- | --- |
| Base | Montrer que la propriete demarre correctement |
| Hypothese | Supposer qu'elle tient sur les cas plus petits ou anterieurs |
| Etape | Montrer que l'hypothese impose le cas suivant |
| Conclusion | Fermer la boucle de recurrence ou d'invariant |

## 3. Modele Architecture

A utiliser pour :
- systemes logiciels
- API
- services
- modules
- flux de donnees
- relations entre composants

Forme de sortie :
- `(Systeme)` carte d'architecture
- `[Noeud Critique]` frontiere de controle ou goulot de dependance
- `[Plan]` `graph TD` ou `classDiagram`
- `[Mecanique]` flux de requete ou de donnees
- `[Deploiement]` implication operationnelle ou note de passage a l'echelle

Questions auxquelles repondre :
- qui parle a qui
- ce que possede chaque bloc
- ou vit l'etat
- ou la panne se propage

## 4. Modele Flux de Code

A utiliser pour :
- fonctions
- methodes
- flux de programme
- ordre d'execution

Forme de sortie :
- `(Systeme)` objectif du chemin de code
- `[Noeud Critique]` branche, invariant ou effet de bord a surveiller
- `[Plan]` `sequenceDiagram` ou `graph TD`
- `[Pseudo-code]` flux de controle simplifie quand cela aide
- `[Mecanique]` flux de controle ordonne
- `[Audit Ligne]` explication ligne par ligne si l'utilisateur veut comprendre chaque instruction
- `[Deploiement]` angle debogage ou maintenance

Questions auxquelles repondre :
- qu'est-ce qui demarre le flux
- quelles branches existent
- ce qui modifie l'etat
- ce qui met fin au flux

## 5. Modele Comparaison

A utiliser pour :
- file vs pile
- BFS vs DFS
- SQL vs NoSQL
- recursion vs iteration
- autres paires similaires

Forme de sortie :
- `(Systeme)` meme probleme, deux strategies
- `[Noeud Critique]` le vrai critere de decision
- `[Plan]` un diagramme compact si utile
- `[Mecanique]` un tableau comparatif
- `[Deploiement]` un scenario de choix pour chaque option

Tableau comparatif compact :

| Option | Force | Faiblesse | Meilleur usage |
| --- | --- | --- | --- |
| A | ... | ... | ... |
| B | ... | ... | ... |

## Regle de Selection

Si l'utilisateur demande :
- "explique comment ca marche" -> commencez par Algorithme ou Flux de code
- "prouve que c'est correct" -> utilisez Preuve
- "montre-moi le systeme" -> utilisez Architecture
- "lequel dois-je choisir" -> utilisez Comparaison
- "explique chaque ligne" ou "donne le pseudocode" -> ajoutez `[Pseudo-code]` et `[Audit Ligne]`

Si la demande melange deux modes, utilisez d'abord le mode principal puis empruntez seulement un element de support au second.
