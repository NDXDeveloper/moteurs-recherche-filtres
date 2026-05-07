# Google — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## 1 — Opérateurs de base

### Guillemets `" "`

Force une correspondance exacte de l'expression.

```
"machine learning pipeline"
```

Google ne retournera que les pages contenant ces trois mots dans cet ordre précis.

### Signe moins `-`

Exclut un terme des résultats.

```
jaguar -voiture
```

Retourne des résultats sur le félin, pas sur la marque automobile.

### OR (ou `|`)

Recherche l'un ou l'autre terme.

```
marathon Paris OR Lyon
marathon Paris | Lyon
```

### Astérisque `*`

Joker qui remplace un ou plusieurs mots inconnus.

```
"le * est l'ennemi du bien"
```

Utile pour retrouver une citation dont on a oublié un passage.

### Parenthèses `( )`

Groupent des opérateurs pour contrôler la logique.

```
(iOS OR Android) développement tutoriel
```

---

## 2 — Filtres de site et d'URL

| Opérateur | Rôle | Exemple |
|---|---|---|
| `site:` | Limite la recherche à un domaine | `site:github.com python scraper` |
| `site:.edu` | Limite à une extension de domaine | `site:.edu intelligence artificielle` |
| `-site:` | Exclut un domaine | `react tutoriel -site:w3schools.com` |
| `inurl:` | Le terme doit apparaître dans l'URL | `inurl:api documentation rest` |
| `allinurl:` | Tous les termes doivent être dans l'URL | `allinurl:blog python fastapi` |

### Exemples pratiques

Rechercher uniquement sur Wikipedia en français :

```
site:fr.wikipedia.org réchauffement climatique
```

Trouver des pages dont l'URL contient « docs » sur le domaine de Stripe :

```
site:stripe.com inurl:docs paiement
```

---

## 3 — Filtres de contenu

| Opérateur | Rôle | Exemple |
|---|---|---|
| `intitle:` | Le terme doit être dans le titre de la page | `intitle:cheatsheet git` |
| `allintitle:` | Tous les termes dans le titre | `allintitle:guide débutant docker` |
| `intext:` | Le terme doit être dans le corps du texte | `intext:"erreur 503" nginx` |
| `allintext:` | Tous les termes dans le corps | `allintext:configurer SSL certificat` |
| `inanchor:` | Le terme figure dans le texte d'un lien pointant vers la page | `inanchor:"code source"` |

### Exemple combiné

```
intitle:"VS Code" intext:productivité extensions
```

---

## 4 — Filtres temporels

### Via l'interface

Après une recherche : **Outils → Date** → Moins d'une heure / 24 h / semaine / mois / an / période personnalisée.

### Via les paramètres d'URL

| Paramètre | Période |
|---|---|
| `&tbs=qdr:h` | Dernière heure |
| `&tbs=qdr:d` | Dernier jour |
| `&tbs=qdr:w` | Dernière semaine |
| `&tbs=qdr:m` | Dernier mois |
| `&tbs=qdr:y` | Dernière année |

### Opérateurs `before:` et `after:`

Format `AAAA-MM-JJ` :

```
"intelligence artificielle" after:2025-01-01 before:2025-06-01
```

---

## 5 — Filtres de type de fichier

```
filetype:pdf machine learning cours
```

| Extension | Description |
|---|---|
| `pdf` | Documents PDF |
| `docx` | Documents Word |
| `xlsx` | Feuilles de calcul Excel |
| `pptx` | Présentations PowerPoint |
| `csv` | Fichiers CSV |
| `json` | Fichiers JSON |

---

## 6 — Opérateurs avancés

| Opérateur | Rôle | Exemple |
|---|---|---|
| `cache:` | Version en cache de Google | `cache:example.com` |
| `related:` | Sites similaires | `related:stackoverflow.com` |
| `define:` | Définition d'un mot | `define:idempotent` |
| `AROUND(n)` | Deux termes à ≤ n mots de distance | `Python AROUND(3) asynchrone` |

---

## 7 — Combinaisons utiles

### Veille technologique

```
site:news.ycombinator.com OR site:dev.to "rust" after:2025-04-01
```

### Trouver des listes « awesome »

```
site:github.com intitle:awesome "machine learning"
```

### Ressources éducatives gratuites

```
filetype:pdf site:.edu "deep learning" cours
```

### Surveiller les mentions d'une marque

```
"nom-de-la-marque" -site:nom-de-la-marque.com after:2025-04-01
```

---

## Ressources

- [Documentation officielle — Affiner les recherches](https://support.google.com/websearch/answer/2466433)
- [Google Advanced Search](https://www.google.com/advanced_search)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
