# Exemples guid?s ENZI

Utilisez ce fichier quand l'utilisateur a besoin d'un apprentissage guid?, pas seulement d'une r?ponse directe.

Pour chaque exemple :
- commencez par la vue d'ensemble
- isolez le n?ud critique
- montrez le pseudocode quand il aide
- expliquez ligne par ligne quand l'apprenant le demande
- nommez explicitement les types d'op?rations
- ajoutez un ancrage m?moire ? la fin

## 1. Recherche binaire

### `(Syst?me)`
- La recherche binaire est un syst?me de recherche dans une liste tri?e.
- Elle r?duit la zone de recherche de moiti? ? chaque it?ration.

### `[N?ud Critique]`
- **N?ud Critique :** la liste doit ?tre tri?e.

### `[Pseudo-code]`
```text
binary_search(L, x):
    start = 0
    end = len(L) - 1

    while start <= end:
        mid = floor((start + end) / 2)

        if L[mid] == x:
            return mid
        else if L[mid] < x:
            start = mid + 1
        else:
            end = mid - 1

    return -1
```

### `[Audit Ligne]`
| Ligne | Type d'op?ration | Explication |
| --- | --- | --- |
| `start = 0` | Affectation, Hors boucle | Initialise la borne gauche. |
| `end = len(L) - 1` | Affectation, Arithm?tique, Hors boucle | Initialise la borne droite. |
| `while start <= end` | Condition, Comparaison, Contr?le de boucle | Continue tant que la zone de recherche existe. |
| `mid = floor((start + end) / 2)` | Affectation, Arithm?tique, Dans boucle | Calcule l'indice du milieu. |
| `if L[mid] == x` | Acc?s / indexation, Comparaison, Condition, Dans boucle | V?rifie si la valeur centrale est la cible. |
| `return mid` | Retour, Dans boucle | S'arr?te imm?diatement si l'?l?ment est trouv?. |
| `start = mid + 1` | Affectation, Arithm?tique, Dans boucle | Se d?place vers la droite. |
| `end = mid - 1` | Affectation, Arithm?tique, Dans boucle | Se d?place vers la gauche. |
| `return -1` | Retour, Hors boucle | Signale l'?chec apr?s la boucle. |

### Ancrage m?moire
- Liste tri?e -> test du milieu -> r?duction de moiti?.

## 2. Tri fusion

### `(Syst?me)`
- Le tri fusion d?coupe un grand probl?me de tri en deux plus petits probl?mes.
- Puis il reconstruit le r?sultat en fusionnant deux moiti?s d?j? tri?es.

### `[N?ud Critique]`
- **N?ud Critique :** `merge` doit combiner correctement deux listes d?j? tri?es.

### `[Pseudo-code]`
```text
merge_sort(L):
    n = len(L)
    if n <= 1:
        return L

    mid = floor(n / 2)
    left = merge_sort(L[0:mid])
    right = merge_sort(L[mid:n])
    return merge(left, right)
```

### `[Audit Ligne]`
| Ligne | Type d'op?ration | Explication |
| --- | --- | --- |
| `n = len(L)` | Affectation, Appel, Hors boucle | Stocke la taille de la liste. |
| `if n <= 1` | Condition, Comparaison, Hors boucle | D?tecte le cas de base. |
| `return L` | Retour, Hors boucle | Arr?te la r?cursion sur une liste triviale. |
| `mid = floor(n / 2)` | Affectation, Arithm?tique, Hors boucle | Calcule le point de d?coupe. |
| `left = merge_sort(L[0:mid])` | Affectation, Appel, Acc?s / indexation, Hors boucle | Trie r?cursivement la moiti? gauche. |
| `right = merge_sort(L[mid:n])` | Affectation, Appel, Acc?s / indexation, Hors boucle | Trie r?cursivement la moiti? droite. |
| `return merge(left, right)` | Retour, Appel, Hors boucle | Fusionne les deux moiti?s tri?es. |

### Ancrage m?moire
- D?couper, trier plus petit, fusionner proprement.

## 3. Somme dans une boucle

### `(Syst?me)`
- Cet algorithme accumule les valeurs de `0` ? `n` dans un total courant.
- Il se comporte comme un compteur avec un registre m?moire.

### `[N?ud Critique]`
- **N?ud Critique :** `tmp` doit toujours contenir la somme partielle d?j? trait?e.

### `[Pseudo-code]`
```text
sum_int(n):
    tmp = 0
    for i in range(n + 1):
        tmp = tmp + i
    return tmp
```

### `[Audit Ligne]`
| Ligne | Type d'op?ration | Explication |
| --- | --- | --- |
| `tmp = 0` | Affectation, Hors boucle | Initialise l'accumulateur. |
| `for i in range(n + 1)` | Contr?le de boucle, Appel, Arithm?tique, Hors boucle | Met en place l'it?ration de `0` ? `n`. |
| `tmp = tmp + i` | Affectation, Arithm?tique, Dans boucle | Ajoute la valeur courante au total cumul?. |
| `return tmp` | Retour, Hors boucle | Renvoie la somme finale accumul?e. |

### Ancrage m?moire
- `tmp` est le r?servoir de stockage ; chaque boucle ajoute une unit? de plus.
