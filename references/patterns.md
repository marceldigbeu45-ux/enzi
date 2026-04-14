# ENZI Patterns

Use this file when ENZI needs a stable response pattern for a recurring explanation type.

Pick the smallest matching pattern. Do not combine all patterns unless the user explicitly wants a full teaching pack.

## 1. Algorithm Pattern

Use for sorting, graph traversal, dynamic programming, recursion, search, or pipeline logic.

Output shape:
- `(System)` what the algorithm is doing globally
- `[Critical Node]` the correctness bottleneck
- `[Blueprint]` a `graph TD` or `sequenceDiagram`
- `[Pseudo-code]` a compact pseudocode block when the user is learning the algorithm
- `[Mechanics]` the ordered steps
- `[Line Audit]` line-by-line explanation with operation type labels when the user asks to understand each line
- `[Deployment]` one engineering analogy and one memory cue

Questions to answer:
- what enters the algorithm
- what transformation happens
- where correctness can fail
- what the base case or stopping condition is
- which lines are outside loops, inside loops, assignments, conditions, comparisons, or returns

Operation labels to use when relevant:`r`n- `Assignment`
- `Condition`
- `Comparison`
- `Loop control`
- `Arithmetic`
- `Access / indexing`
- `Call`
- `Return`
- `Outside loop`
- `Inside loop`

Compact line-audit table:
| Line | Role | Operation type | Explanation |
| --- | --- | --- | --- |
| 1 | Initialize | Assignment, Outside loop | Store the starting value |
| 2 | Test | Condition, Comparison | Decide whether to continue |
| 3 | Update | Assignment, Arithmetic, Inside loop | Advance the state |

## 2. Proof Pattern

Use for correctness, recurrence, invariants, induction, or termination arguments.

Output shape:
- `(System)` theorem or claim map
- `[Critical Node]` the load-bearing logical step
- `[Blueprint]` proof flow as Mermaid
- `[Mechanics]` base / hypothesis / step / conclusion
- `[Deployment]` one engineering interpretation of the proof

Compact proof skeleton:
| Block | Purpose |
| --- | --- |
| Base | Show the property starts correctly |
| Hypothesis | Assume it holds on smaller or earlier cases |
| Step | Show the assumption forces the next case |
| Conclusion | Close the recurrence or invariant loop |

## 3. Architecture Pattern

Use for software systems, APIs, services, modules, data movement, and component relationships.

Output shape:
- `(System)` architecture map
- `[Critical Node]` control boundary or dependency bottleneck
- `[Blueprint]` `graph TD` or `classDiagram`
- `[Mechanics]` request or data flow
- `[Deployment]` operational implication or scaling note

Questions to answer:
- who talks to whom
- what each block owns
- where state lives
- where failure propagates

## 4. Code Flow Pattern

Use for functions, methods, program flow, and execution order.

Output shape:
- `(System)` purpose of the code path
- `[Critical Node]` branch, invariant, or side effect to watch
- `[Blueprint]` `sequenceDiagram` or `graph TD`
- `[Pseudo-code]` simplified control flow when helpful
- `[Mechanics]` ordered control flow
- `[Line Audit]` line-by-line explanation when the user wants to understand each instruction
- `[Deployment]` debugging or maintenance angle

Questions to answer:
- what starts the flow
- what branches exist
- what mutates state
- what ends the flow

## 5. Comparison Pattern

Use for queue vs stack, BFS vs DFS, SQL vs NoSQL, recursion vs iteration, and similar pairs.

Output shape:
- `(System)` same problem, two strategies
- `[Critical Node]` the real decision criterion
- `[Blueprint]` one compact diagram if useful
- `[Mechanics]` one comparison table
- `[Deployment]` one scenario for choosing each option

Compact comparison table:
| Option | Strength | Weakness | Best fit |
| --- | --- | --- | --- |
| A | ... | ... | ... |
| B | ... | ... | ... |

## Pattern Selection Rule

If the user asks:
- "explain how it works" -> start with Algorithm or Code Flow
- "prove that it is correct" -> use Proof
- "show me the system" -> use Architecture
- "which one should I choose" -> use Comparison
- "explain each line" or "give pseudocode" -> add `[Pseudo-code]` and `[Line Audit]`

If the request mixes two modes, use the primary mode first and borrow only one support element from the second.

