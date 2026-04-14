# ENZI Guided Examples

Use this file when the user needs guided learning, not only a direct answer.

For each example:
- start with the big picture
- isolate the critical node
- show pseudocode when it helps
- explain line by line when the learner asks for it
- name operation types explicitly
- add a memory anchor at the end

## 1. Binary Search

### `(System)`
- Binary search is a lookup system for a sorted list.
- It shrinks the search zone by half at each iteration.

### `[Critical Node]`
- **Critical Node:** the list must be sorted.

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

### `[Line Audit]`
| Line | Operation type | Guidance |
| --- | --- | --- |
| `start = 0` | Assignment, Outside loop | Initialize the left boundary. |
| `end = len(L) - 1` | Assignment, Arithmetic, Outside loop | Initialize the right boundary. |
| `while start <= end` | Condition, Comparison, Loop control | Continue while the search zone exists. |
| `mid = floor((start + end) / 2)` | Assignment, Arithmetic, Inside loop | Compute the middle index. |
| `if L[mid] == x` | Access / indexing, Comparison, Condition, Inside loop | Check if the middle value is the target. |
| `return mid` | Return, Inside loop | Stop immediately if found. |
| `start = mid + 1` | Assignment, Arithmetic, Inside loop | Move right. |
| `end = mid - 1` | Assignment, Arithmetic, Inside loop | Move left. |
| `return -1` | Return, Outside loop | Report failure after the loop. |

### Memory anchor
- Sorted list -> middle check -> halve the zone.

## 2. Merge Sort

### `(System)`
- Merge sort breaks a big sorting problem into two smaller sorting problems.
- Then it rebuilds the result by merging two sorted halves.

### `[Critical Node]`
- **Critical Node:** `merge` must correctly combine two already-sorted lists.

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

### `[Line Audit]`
| Line | Operation type | Guidance |
| --- | --- | --- |
| `n = len(L)` | Assignment, Call, Outside loop | Store the list size. |
| `if n <= 1` | Condition, Comparison, Outside loop | Detect the base case. |
| `return L` | Return, Outside loop | Stop recursion on a trivial list. |
| `mid = floor(n / 2)` | Assignment, Arithmetic, Outside loop | Compute the split point. |
| `left = merge_sort(L[0:mid])` | Assignment, Call, Access / indexing, Outside loop | Sort the left half recursively. |
| `right = merge_sort(L[mid:n])` | Assignment, Call, Access / indexing, Outside loop | Sort the right half recursively. |
| `return merge(left, right)` | Return, Call, Outside loop | Merge the two sorted halves. |

### Memory anchor
- Cut, sort smaller, merge cleanly.

## 3. Sum in a Loop

### `(System)`
- This algorithm accumulates values from `0` to `n` into one running total.
- It behaves like a counter with a memory register.

### `[Critical Node]`
- **Critical Node:** `tmp` must always store the partial sum already processed.

### `[Pseudo-code]`
```text
sum_int(n):
    tmp = 0
    for i in range(n + 1):
        tmp = tmp + i
    return tmp
```

### `[Line Audit]`
| Line | Operation type | Guidance |
| --- | --- | --- |
| `tmp = 0` | Assignment, Outside loop | Initialize the accumulator. |
| `for i in range(n + 1)` | Loop control, Call, Arithmetic, Outside loop | Set up the iteration from `0` to `n`. |
| `tmp = tmp + i` | Assignment, Arithmetic, Inside loop | Add the current value to the running total. |
| `return tmp` | Return, Outside loop | Return the final accumulated sum. |

### Memory anchor
- `tmp` is the storage tank; each loop adds one more unit.
