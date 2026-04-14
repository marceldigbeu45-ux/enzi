# Exemples Guides ENZI

Utilisez ce fichier quand l'utilisateur a besoin d'un apprentissage guide, pas seulement d'une reponse directe.

Pour chaque exemple :
- commencez par la vue d'ensemble
- isolez le noeud critique
- montrez le pseudocode quand il aide
- expliquez ligne par ligne quand l'apprenant le demande
- nommez explicitement les types d'operations
- ajoutez un ancrage memoire a la fin

## 1. Recherche Binaire

### `(Systeme)`
- La recherche binaire est un systeme de recherche dans une liste triee.
- Elle reduit la zone de recherche de moitie a chaque iteration.

### `[Noeud Critique]`
- **Noeud Critique :** la liste doit etre triee.

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
| Ligne | Type d'operation | Explication |
| --- | --- | --- |
| `start = 0` | Affectation, Hors boucle | Initialise la borne gauche. |
| `end = len(L) - 1` | Affectation, Arithmetique, Hors boucle | Initialise la borne droite. |
| `while start <= end` | Condition, Comparaison, Controle de boucle | Continue tant que la zone de recherche existe. |
| `mid = floor((start + end) / 2)` | Affectation, Arithmetique, Dans boucle | Calcule l'indice du milieu. |
| `if L[mid] == x` | Acces / indexation, Comparaison, Condition, Dans boucle | Verifie si la valeur centrale est la cible. |
| `return mid` | Retour, Dans boucle | S'arrete immediatement si l'element est trouve. |
| `start = mid + 1` | Affectation, Arithmetique, Dans boucle | Se deplace vers la droite. |
| `end = mid - 1` | Affectation, Arithmetique, Dans boucle | Se deplace vers la gauche. |
| `return -1` | Retour, Hors boucle | Signale l'echec apres la boucle. |

### Ancrage Memoire
- Liste triee -> test du milieu -> reduction de moitie.

## 2. Tri Fusion

### `(Systeme)`
- Le tri fusion decoupe un grand probleme de tri en deux plus petits problemes.
- Puis il reconstruit le resultat en fusionnant deux moities deja triees.

### `[Noeud Critique]`
- **Noeud Critique :** `merge` doit combiner correctement deux listes deja triees.

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
| Ligne | Type d'operation | Explication |
| --- | --- | --- |
| `n = len(L)` | Affectation, Appel, Hors boucle | Stocke la taille de la liste. |
| `if n <= 1` | Condition, Comparaison, Hors boucle | Detecte le cas de base. |
| `return L` | Retour, Hors boucle | Arrete la recursion sur une liste triviale. |
| `mid = floor(n / 2)` | Affectation, Arithmetique, Hors boucle | Calcule le point de decoupe. |
| `left = merge_sort(L[0:mid])` | Affectation, Appel, Acces / indexation, Hors boucle | Trie recursivement la moitie gauche. |
| `right = merge_sort(L[mid:n])` | Affectation, Appel, Acces / indexation, Hors boucle | Trie recursivement la moitie droite. |
| `return merge(left, right)` | Retour, Appel, Hors boucle | Fusionne les deux moities triees. |

### Ancrage Memoire
- Decouper, trier plus petit, fusionner proprement.

## 3. Somme Dans Une Boucle

### `(Systeme)`
- Cet algorithme accumule les valeurs de `0` a `n` dans un total courant.
- Il se comporte comme un compteur avec un registre memoire.

### `[Noeud Critique]`
- **Noeud Critique :** `tmp` doit toujours contenir la somme partielle deja traitee.

### `[Pseudo-code]`
```text
sum_int(n):
    tmp = 0
    for i in range(n + 1):
        tmp = tmp + i
    return tmp
```

### `[Audit Ligne]`
| Ligne | Type d'operation | Explication |
| --- | --- | --- |
| `tmp = 0` | Affectation, Hors boucle | Initialise l'accumulateur. |
| `for i in range(n + 1)` | Controle de boucle, Appel, Arithmetique, Hors boucle | Met en place l'iteration de `0` a `n`. |
| `tmp = tmp + i` | Affectation, Arithmetique, Dans boucle | Ajoute la valeur courante au total cumule. |
| `return tmp` | Retour, Hors boucle | Renvoie la somme finale accumulee. |

### Ancrage Memoire
- `tmp` est le reservoir de stockage ; chaque boucle ajoute une unite de plus.
