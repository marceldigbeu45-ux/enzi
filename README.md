# ENZI

ENZI est un skill Codex con?u pour expliquer des sujets techniques avec une m?thode architecturale, visuelle et structur?e.

Il s'adresse aux utilisateurs qui comprennent mieux quand ils voient :
- le syst?me entier avant les d?tails locaux
- le concept porteur principal tr?s t?t
- un plan logique avec Mermaid
- du pseudocode compact et un audit ligne par ligne quand c'est n?cessaire

## Positionnement

ENZI ne cherche pas seulement ? r?pondre. Il cherche ? faire comprendre.

Le skill transforme une explication technique en parcours p?dagogique lisible :
- une cartographie descendante du syst?me
- un `[N?ud Critique]` explicite
- des sections structur?es et peu bruyantes
- des analogies d'ing?nierie ancr?es dans le m?canisme r?el
- des exemples r?solus au lieu d'une longue prose abstraite

## Cas d'usage

ENZI est particuli?rement utile pour :
- algorithmes
- preuves et invariants
- parcours du flux de code
- architecture syst?me
- comparaisons entre concepts techniques

## Format de sortie

Les sorties ENZI suivent g?n?ralement cette s?quence :
1. `(Syst?me)`
2. `[N?ud Critique]`
3. `[Plan]`
4. `[Pseudo-code]`
5. `[M?canique]`
6. `[Audit Ligne]`
7. `[D?ploiement]`

L'objectif est de faire passer l'utilisateur du global vers le local, sans surcharge cognitive.

## Structure du d?p?t

- `SKILL.md` : d?finition principale du skill et r?gles de fonctionnement
- `references/patterns.md` : mod?les de r?ponse stables
- `references/examples.md` : exemples p?dagogiques r?solus
- `references/identity.md` : identit? visuelle et de marque
- `agents/openai.yaml` : m?tadonn?es d'interface
- `assets/` : ic?nes ENZI

## Utiliser ENZI

Dans Codex, invoquez-le avec :

```text
Utilise $enzi pour expliquer cela avec une carte descendante, un n?ud critique nomm?, un plan Mermaid et des sections architecturales courtes.
```

Exemples de demandes adapt?es :
- ? Explique cet algorithme en me montrant d'abord la structure globale ?
- ? Donne-moi la vue d'ensemble avant la preuve ?
- ? Cartographie le flux de ce code et montre le n?ud critique ?
- ? Explique chaque ligne avec les types d'op?rations ?

## Publication GitHub

Ce d?p?t est autonome et peut ?tre versionn? directement comme d?p?t GitHub.
