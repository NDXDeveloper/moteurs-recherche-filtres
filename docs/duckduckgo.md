# DuckDuckGo — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de DuckDuckGo

- **Vie privée** : aucun tracking, aucun profil utilisateur, aucune bulle de filtre.
- DuckDuckGo utilise principalement l'index de **Bing** en arrière-plan, complété par d'autres sources.
- Les opérateurs avancés ne fonctionnent **pas toujours à 100 %** sur toutes les requêtes (DuckDuckGo le reconnaît dans sa documentation).
- Fonctionnalités uniques : les **!bangs** et le raccourci `\` (I'm Feeling Ducky).

---

## 1 — Opérateurs de base

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte | `"deep learning"` |
| `-` | Exclure un terme | `jaguar -voiture` |
| `OR` | L'un ou l'autre terme | `marathon Paris OR Lyon` |
| `\` | Aller directement au premier résultat | `\wikipedia france` |

> **Note** : DuckDuckGo ne supporte pas `*` (joker) ni `AROUND(n)`.

---

## 2 — Filtres de site et d'URL

| Opérateur | Rôle | Exemple |
|---|---|---|
| `site:` | Limiter à un domaine | `site:github.com python` |
| `-site:` | Exclure un domaine | `react -site:w3schools.com` |

On peut combiner plusieurs domaines avec `OR` :

```
site:stackoverflow.com OR site:github.com rust async
```

Le raccourci `s:` fonctionne aussi à la place de `site:`.

---

## 3 — Filtres de contenu

| Opérateur | Rôle | Exemple |
|---|---|---|
| `intitle:` | Terme dans le titre | `intitle:cheatsheet docker` |
| `intext:` | Terme dans le corps | `intext:"erreur 404" nginx` |
| `allintext:` | Tous les termes dans le corps | `allintext:python flask déploiement` |
| `filetype:` | Type de fichier | `filetype:pdf cours linux` |

---

## 4 — Filtres temporels

DuckDuckGo permet de filtrer par date via la syntaxe :

```
climat date:2024-01-01..2024-12-31
```

Via l'interface, après une recherche, un menu de filtrage par date est également disponible.

---

## 5 — Les !Bangs

C'est la fonctionnalité signature de DuckDuckGo. Un **!bang** redirige votre recherche vers le moteur interne d'un autre site.

| Bang | Site cible | Exemple |
|---|---|---|
| `!g` | Google | `!g machine learning` |
| `!w` | Wikipedia | `!w photosynthèse` |
| `!yt` | YouTube | `!yt tutoriel docker` |
| `!a` | Amazon | `!a clavier mécanique` |
| `!gh` | GitHub | `!gh react boilerplate` |
| `!so` | Stack Overflow | `!so python async await` |
| `!maps` | Google Maps | `!maps Tour Eiffel` |
| `!r` | Reddit | `!r homelab` |
| `!mdn` | MDN Web Docs | `!mdn fetch API` |

Il existe **des milliers** de bangs. Liste complète : [duckduckgo.com/bangs](https://duckduckgo.com/bangs)

> ⚠️ Quand vous utilisez un bang, la recherche est effectuée **directement sur le site cible**. Vous êtes alors soumis à la politique de confidentialité de ce site.

---

## 6 — Autres fonctionnalités

### Réponses instantanées

DuckDuckGo affiche des réponses directes pour certains mots-clés :

```
ip address              → affiche votre IP publique
password 20 strong      → génère un mot de passe de 20 caractères
color #3498db           → affiche un aperçu de la couleur
stopwatch               → lance un chronomètre
```

### Catégories de résultats

Ajoutez un mot-clé de catégorie à la fin de votre recherche pour prioriser ce type :

```
python tutoriel images
python tutoriel videos
python tutoriel news
```

---

## 7 — Combinaisons utiles

### Rechercher des PDF éducatifs

```
filetype:pdf site:.edu "machine learning" intitle:cours
```

### Veille sur un sujet récent

```
"intelligence artificielle" date:2025-01-01..2025-12-31 site:arxiv.org
```

### Trouver rapidement une doc officielle

```
!mdn array methods
```

---

## Ressources

- [Documentation officielle — Syntaxe de recherche](https://duckduckgo.com/duckduckgo-help-pages/results/syntax)
- [Liste complète des !bangs](https://duckduckgo.com/bangs)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
