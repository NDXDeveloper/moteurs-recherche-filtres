# Bing — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de Bing

- Les opérateurs booléens `AND`, `OR`, `NOT` doivent être écrits **en majuscules**, sinon Bing les traite comme des mots ordinaires.
- Bing ignore automatiquement la ponctuation et les mots vides (a, and, or…). Utilisez `""` ou `+` pour les forcer.
- **`inurl:` n'existe pas sur Bing** — Microsoft l'a désactivé en 2007. Utilisez `url:` pour vérifier une URL précise.
- Bing propose des opérateurs uniques comme `ip:`, `contains:`, `instreamset:`, `near:` et `location:`.

---

## 1 — Opérateurs de base

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte | `"apprentissage profond"` |
| `-` ou `NOT` | Exclure un terme | `jaguar NOT voiture` |
| `+` | Forcer l'inclusion d'un mot | `chat +musical` |
| `AND` ou `&` | Les deux termes requis | `python AND django` |
| `OR` ou `\|` | L'un ou l'autre | `marathon Paris OR Lyon` |
| `( )` | Grouper des conditions | `(iOS OR Android) tutoriel` |

---

## 2 — Filtres de site et d'URL

| Opérateur | Rôle | Exemple |
|---|---|---|
| `site:` | Limiter à un domaine | `site:github.com python` |
| `-site:` | Exclure un domaine | `react -site:w3schools.com` |
| `url:` | Vérifier si une URL est indexée | `url:example.com/page` |
| `feed:` | Trouver des flux RSS | `feed:cybersécurité` |

> ⚠️ `site:` ne retourne les sous-domaines que sur deux niveaux de profondeur maximum.

---

## 3 — Filtres de contenu

| Opérateur | Rôle | Exemple |
|---|---|---|
| `intitle:` | Terme dans le titre | `intitle:cheatsheet git` |
| `inbody:` | Terme dans le corps de la page | `inbody:kubernetes déploiement` |
| `inanchor:` | Terme dans le texte d'ancrage d'un lien | `inanchor:"sky diving"` |
| `instreamset:` | Terme dans une propriété spécifique | `instreamset:(title url):seo` |

### `instreamset:` en détail

Cet opérateur est propre à Bing. Il permet de cibler une ou plusieurs propriétés de la page entre parenthèses :

```
instreamset:(title body):machine learning
```

Propriétés disponibles : `title`, `body`, `url`, `anchor`.

---

## 4 — Filtres de type de fichier

| Opérateur | Rôle | Exemple |
|---|---|---|
| `filetype:` | Pages qui **sont** du type spécifié | `filetype:pdf deep learning` |
| `ext:` | Pages dont l'extension est spécifiée | `ext:csv données` |
| `contains:` | Pages qui contiennent un **lien** vers un type de fichier | `rapport contains:xlsx` |

La différence est importante : `filetype:pdf` retourne des PDF, tandis que `contains:pdf` retourne des pages HTML qui **lient** vers des PDF.

---

## 5 — Filtres spéciaux (propres à Bing)

| Opérateur | Rôle | Exemple |
|---|---|---|
| `ip:` | Pages hébergées à une adresse IP | `ip:203.0.113.50 blog` |
| `language:` | Résultats dans une langue | `futbol language:es` |
| `location:` | Résultats d'une région | `oiseaux location:fr` |
| `near:` | Proximité entre deux termes | `Python near:5 asynchrone` |
| `prefer:` | Favorise un terme sans exclure le reste | `prefer:python développement web` |
| `imagesize:` | Taille d'image (small / medium / large) | `logo imagesize:large` |

### Opérateur `near:`

Équivalent du `AROUND(n)` de Google. Trouve des pages où deux mots apparaissent à ≤ n mots d'écart :

```
intelligence near:3 artificielle
```

---

## 6 — Combinaisons utiles

### Trouver des opportunités de guest blogging

```
intitle:"write for us" OR intitle:"guest post" site:.com
```

### Vérifier l'indexation d'un concurrent

```
site:concurrent.com intitle:"politique de confidentialité"
```

### Recherche de documents internes par type

```
site:entreprise.com (filetype:pdf OR filetype:docx) rapport
```

---

## Ressources

- [Documentation Bing — Advanced Search Options](https://support.microsoft.com/en-us/topic/advanced-search-options-b92e25f1-0085-4271-bdf9-14aaea720930)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
