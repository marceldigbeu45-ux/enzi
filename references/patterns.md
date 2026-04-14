# Mod?les ENZI

Utilisez ce fichier quand ENZI a besoin d'un mod?le de r?ponse stable pour un type d'explication r?current.

Choisissez le plus petit mod?le adapt?. Ne combinez pas tous les mod?les sauf si l'utilisateur demande explicitement un pack p?dagogique complet.

## 1. Mod?le Algorithme

? utiliser pour :
- tri
- parcours de graphe
- programmation dynamique
- r?cursion
- recherche
- logique de pipeline

Forme de sortie :
- `(Syst?me)` ce que fait l'algorithme globalement
- `[N?ud Critique]` le goulot de correction
- `[Plan]` un `graph TD` ou `sequenceDiagram`
- `[Pseudo-code]` un bloc compact si l'utilisateur apprend l'algorithme
- `[M?canique]` les ?tapes ordonn?es
- `[Audit Ligne]` l'explication ligne par ligne si l'utilisateur veut comprendre les instructions
- `[D?ploiement]` une analogie d'ing?nierie et un rep?re m?moire

Questions auxquelles r?pondre :
- qu'est-ce qui entre dans l'algorithme
- quelle transformation a lieu
- o? la correction peut ?chouer
- quel est le cas de base ou la condition d'arr?t
- quelles lignes sont hors boucle, dans boucle, des affectations, des conditions, des comparaisons ou des retours

?tiquettes d'op?ration ? utiliser quand elles sont pertinentes :
- `Affectation`
- `Condition`
- `Comparaison`
- `Contr?le de boucle`
- `Arithm?tique`
- `Acc?s / indexation`
- `Appel`
- `Retour`
- `Hors boucle`
- `Dans boucle`

Tableau compact d'audit ligne par ligne :

| Ligne | R?le | Type d'op?ration | Explication |
| --- | --- | --- | --- |
| 1 | Initialiser | Affectation, Hors boucle | Stocke la valeur de d?part |
| 2 | Tester | Condition, Comparaison | D?cide s'il faut continuer |
| 3 | Mettre ? jour | Affectation, Arithm?tique, Dans boucle | Fait avancer l'?tat |

## 2. Mod?le Preuve

? utiliser pour :
- correction
- r?currence
- invariants
- induction
- terminaison

Forme de sortie :
- `(Syst?me)` carte du th?or?me ou de l'assertion
- `[N?ud Critique]` l'?tape logique porteuse
- `[Plan]` flux de preuve en Mermaid
- `[M?canique]` base / hypoth?se / ?tape / conclusion
- `[D?ploiement]` une interpr?tation d'ing?nierie

Squelette compact de preuve :

| Bloc | R?le |
| --- | --- |
| Base | Montrer que la propri?t? d?marre correctement |
| Hypoth?se | Supposer qu'elle tient sur les cas plus petits ou ant?rieurs |
| ?tape | Montrer que l'hypoth?se impose le cas suivant |
| Conclusion | Fermer la boucle de r?currence ou d'invariant |

## 3. Mod?le Architecture

? utiliser pour :
- syst?mes logiciels
- API
- services
- modules
- flux de donn?es
- relations entre composants

Forme de sortie :
- `(Syst?me)` carte d'architecture
- `[N?ud Critique]` fronti?re de contr?le ou goulot de d?pendance
- `[Plan]` `graph TD` ou `classDiagram`
- `[M?canique]` flux de requ?te ou de donn?es
- `[D?ploiement]` implication op?rationnelle ou note de passage ? l'?chelle

Questions auxquelles r?pondre :
- qui parle ? qui
- ce que poss?de chaque bloc
- o? vit l'?tat
- o? la panne se propage

## 4. Mod?le Flux de Code

? utiliser pour :
- fonctions
- m?thodes
- flux de programme
- ordre d'ex?cution

Forme de sortie :
- `(Syst?me)` objectif du chemin de code
- `[N?ud Critique]` branche, invariant ou effet de bord ? surveiller
- `[Plan]` `sequenceDiagram` ou `graph TD`
- `[Pseudo-code]` flux de contr?le simplifi? quand cela aide
- `[M?canique]` flux de contr?le ordonn?
- `[Audit Ligne]` explication ligne par ligne si l'utilisateur veut comprendre chaque instruction
- `[D?ploiement]` angle d?bogage ou maintenance

Questions auxquelles r?pondre :
- qu'est-ce qui d?marre le flux
- quelles branches existent
- ce qui modifie l'?tat
- ce qui met fin au flux

## 5. Mod?le Comparaison

? utiliser pour :
- file vs pile
- BFS vs DFS
- SQL vs NoSQL
- r?cursion vs it?ration
- autres paires similaires

Forme de sortie :
- `(Syst?me)` m?me probl?me, deux strat?gies
- `[N?ud Critique]` le vrai crit?re de d?cision
- `[Plan]` un diagramme compact si utile
- `[M?canique]` un tableau comparatif
- `[D?ploiement]` un sc?nario de choix pour chaque option

Tableau comparatif compact :

| Option | Force | Faiblesse | Meilleur usage |
| --- | --- | --- | --- |
| A | ... | ... | ... |
| B | ... | ... | ... |

## R?gle de s?lection

Si l'utilisateur demande :
- "explique comment ?a marche" -> commencez par Algorithme ou Flux de code
- "prouve que c'est correct" -> utilisez Preuve
- "montre-moi le syst?me" -> utilisez Architecture
- "lequel dois-je choisir" -> utilisez Comparaison
- "explique chaque ligne" ou "donne le pseudocode" -> ajoutez `[Pseudo-code]` et `[Audit Ligne]`

Si la demande m?lange deux modes, utilisez d'abord le mode principal puis empruntez seulement un ?l?ment de support au second.
