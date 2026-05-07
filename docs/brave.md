# Brave Search — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de Brave Search

- **Index 100 % indépendant** : Brave ne dépend ni de Google ni de Bing (avec un fallback optionnel vers Google configurable par l'utilisateur).
- **Vie privée maximale** : pas de tracking, pas de profil utilisateur, pas de collecte de données.
- Fonctionnalités uniques : **Goggles** (re-classement personnalisé des résultats) et **Bangs** (comme DuckDuckGo).
- Les opérateurs sont encore **en phase expérimentale** — leur comportement peut varier selon la requête.
- Brave peut afficher un message « Search operators were not applied » si trop peu de résultats correspondent.

---

## 1 — Opérateurs de base

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte | `"apprentissage profond"` |
| `-` | Exclure un terme | `office -microsoft` |
| `AND` | Les deux conditions requises | `visa loc:gb AND lang:en` |
| `OR` | L'une ou l'autre condition | `voyage inpage:australie OR inpage:japon` |
| `NOT` | Exclure une condition | `brave search NOT brave.com` |

> Les opérateurs logiques `AND`, `OR`, `NOT` doivent être en **majuscules**.

---

## 2 — Filtres de site et de fichier

| Opérateur | Rôle | Exemple |
|---|---|---|
| `site:` | Limiter à un domaine | `site:github.com rust` |
| `-site:` | Exclure un domaine | `python -site:w3schools.com` |
| `filetype:` | Type de fichier | `filetype:pdf deep learning` |
| `ext:` | Extension de fichier | `ext:csv données open data` |

---

## 3 — Filtres de contenu

| Opérateur | Rôle | Exemple |
|---|---|---|
| `intitle:` | Terme dans le titre | `intitle:tutorial kubernetes` |
| `inbody:` | Terme dans le corps de la page | `nvidia 1080 ti inbody:"founders edition"` |
| `inpage:` | Terme n'importe où dans la page (titre + corps) | `inpage:"machine learning" cours` |

### `inpage:` — opérateur propre à Brave

Contrairement à `intitle:` et `inbody:` qui ciblent une zone spécifique, `inpage:` cherche le terme dans l'ensemble de la page (titre, corps, URL). C'est un raccourci pratique.

---

## 4 — Filtres de localisation et de langue

| Opérateur | Rôle | Exemple |
|---|---|---|
| `loc:` | Résultats d'un pays (code ISO 2 lettres) | `startup loc:fr` |
| `lang:` | Langue des résultats | `tutoriel lang:fr` |

On peut combiner les deux :

```
visa loc:gb AND lang:en
```

---

## 5 — Les Bangs

Comme DuckDuckGo, Brave supporte les bangs pour rediriger vers d'autres moteurs :

| Bang | Site cible | Exemple |
|---|---|---|
| `!g` | Google | `!g machine learning` |
| `!w` | Wikipedia | `!w photosynthèse` |
| `!r` | Reddit | `!r homelab` |
| `!a` | Amazon | `!a clavier mécanique` |
| `!yt` | YouTube | `!yt docker tutoriel` |

---

## 6 — Les Goggles

Les **Goggles** sont une fonctionnalité unique à Brave. Ce sont des fichiers de règles créés par la communauté qui permettent de re-classer les résultats selon vos propres critères.

### Goggles populaires

| Goggle | Effet |
|---|---|
| Tech blogs | Booste les blogs techniques indépendants |
| News from the Left | Favorise les médias de gauche |
| News from the Right | Favorise les médias de droite |
| Small Web | Met en avant les petits sites et blogs personnels |
| Academic | Priorise les sources académiques |

### Utilisation

1. Faites une recherche sur [search.brave.com](https://search.brave.com)
2. Cliquez sur **Goggles** dans la barre de filtres
3. Choisissez un Goggle dans la liste ou créez le vôtre

Vous pouvez aussi créer vos propres Goggles en suivant la [documentation officielle](https://search.brave.com/help/goggles).

---

## 7 — Combinaisons utiles

### Rechercher des PDF en français depuis la France

```
filetype:pdf lang:fr loc:fr "cybersécurité"
```

### Exclure un site tout en ciblant un type de contenu

```
intitle:tutorial kubernetes -site:medium.com
```

### Combiner filtres logiques

```
coffee OR tea recipe NOT starbucks
```

---

## Ressources

- [Documentation officielle — Search Operators](https://search.brave.com/help/operators)
- [Documentation officielle — Goggles](https://search.brave.com/help/goggles)
- [Documentation officielle — Bangs](https://search.brave.com/help/bangs)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
