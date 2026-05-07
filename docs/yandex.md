# Yandex — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de Yandex

- **Moteur russe** avec son propre index, particulièrement performant pour le web russophone et les pays de la CEI.
- Syntaxe d'opérateurs **très différente** des autres moteurs : utilise `&&`, `&`, `~~`, `~`, `/n` et d'autres symboles uniques.
- L'opérateur de type de fichier s'appelle **`mime:`** et non `filetype:`.
- Yandex offre une **recherche d'images inversée** avec reconnaissance faciale, souvent meilleure que celle de Google.
- L'opérateur `host:` attend le domaine principal (ex : `host:archive.org`, pas `host:www.archive.org`).

---

## 1 — Opérateurs de base

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte | `"deep learning"` |
| `+` | Force l'inclusion d'un mot vide | `+le +petit prince` |
| `!` | Force la forme exacte du mot (pas de déclinaison) | `!running shoes` |
| `\|` | OU logique (l'un ou l'autre) | `dell \| toshiba \| macbook` |
| `( )` | Grouper des conditions | `(python \| rust) tutoriel` |

---

## 2 — Opérateurs booléens avancés

Yandex a un système booléen plus riche que la plupart des moteurs :

| Opérateur | Rôle | Exemple |
|---|---|---|
| `&&` | ET logique — les deux termes sur la **même page** | `python && machine learning` |
| `&` | ET logique — les deux termes dans la **même phrase** | `python & asynchrone` |
| `~~` | NON — exclure un terme de la **page** | `mobile phone ~~ windows` |
| `~` | NON — exclure un terme de la **phrase** | `mobile phone ~ windows` |

La distinction page / phrase est propre à Yandex et permet un contrôle très fin.

---

## 3 — Opérateurs de proximité

| Opérateur | Rôle | Exemple |
|---|---|---|
| `/n` | Les deux termes à ≤ n mots de distance | `python /4 asynchrone` |
| `/-n` | Le second terme doit être **avant** le premier, à ≤ n mots | `asynchrone /-3 python` |

L'opérateur `/n` est l'équivalent du `AROUND(n)` de Google, mais avec la possibilité de contrôler l'ordre des mots (signe négatif).

---

## 4 — Filtres de site et d'URL

| Opérateur | Rôle | Exemple |
|---|---|---|
| `site:` | Limiter à un domaine | `site:habr.com python` |
| `host:` | Limiter à un hôte précis (sans sous-domaines) | `host:docs.python.org` |
| `rhost:` | Comme `host:` mais domaine écrit à l'envers | `rhost:org.python.docs.*` |
| `url:` | Recherche dans l'URL exacte | `url:github.com/torvalds/*` |

### `rhost:` — le domaine inversé

C'est un opérateur unique à Yandex. Le domaine est écrit du TLD vers le sous-domaine. Ajoutez `*` à la fin pour inclure tous les sous-domaines :

```
rhost:com.github.* python
```

Cette requête cherche « python » sur tous les sous-domaines de github.com.

---

## 5 — Filtres de contenu et de fichier

| Opérateur | Rôle | Exemple |
|---|---|---|
| `title:` | Terme dans le titre | `title:cheatsheet docker` |
| `mime:` | Type de fichier (remplace `filetype:`) | `mime:pdf cours linux` |
| `lang:` | Langue de la page (code ISO 2 lettres) | `passport lang:en` |
| `date:` | Année de publication | `machine learning date:2025` |

### Types MIME courants

| Valeur | Format |
|---|---|
| `pdf` | PDF |
| `doc` | Word (.doc) |
| `docx` | Word (.docx) |
| `xls` | Excel (.xls) |
| `xlsx` | Excel (.xlsx) |
| `ppt` | PowerPoint |
| `rtf` | Rich Text |
| `swf` | Flash |
| `odt` | OpenDocument |

---

## 6 — Opérateur `<<` (AND non-ranking)

```
machine learning << Python
```

Cet opérateur ajoute le mot « Python » comme condition de filtrage **sans modifier le classement** des résultats. La page doit contenir « Python », mais le ranking reste basé sur « machine learning » uniquement.

---

## 7 — Combinaisons utiles

### Recherche de documents académiques en anglais

```
mime:pdf site:arxiv.org "neural network" lang:en
```

### Trouver des profils professionnels

```
site:linkedin.com/in "data engineer" (Python | Spark)
```

### Recherche de proximité fine

```
"intelligence" /2 "artificielle" && cours && site:edu
```

### Recherche d'images inversée

Rendez-vous sur [yandex.com/images](https://yandex.com/images) et utilisez l'icône appareil photo pour uploader une image. Yandex utilise la reconnaissance faciale, ce qui le rend particulièrement efficace pour identifier des personnes.

---

## 8 — Les autres moteurs russes

Yandex domine le marché russe à ~74 % (fin 2024), suivi de Google.ru à ~24 %. Les autres moteurs se partagent moins de 1 % du trafic, mais méritent d'être connus pour comprendre l'écosystème :

### Mail.ru

- **Part de marché** : ~0,09 %
- Portail multiservice majeur (email, réseaux sociaux VK, jeux, actualités) appartenant au groupe **VK**.
- Le moteur de recherche de Mail.ru utilise **Yandex en backend** — les mêmes opérateurs s'appliquent donc.
- L'intérêt de Mail.ru est son **écosystème social** (VK, Odnoklassniki), pas son moteur.

### Rambler

- **Part de marché** : ~0,04 %
- L'un des plus anciens portails russes (1996). Racheté par **Sberbank** (banque d'État) en 2020.
- Aujourd'hui principalement un **portail d'actualités et de médias** (Lenta.ru, service vidéo Okko).
- Le moteur de recherche est secondaire et n'offre pas d'opérateurs avancés.
- À noter : en 2012, une fuite a exposé **98 millions de comptes** Rambler avec des mots de passe stockés en clair.

### Sputnik

- **Part de marché** : < 0,5 %
- Moteur de recherche **étatique**, développé par Rostelecom.
- Spécialisé dans l'indexation de **documents officiels**, rapports parlementaires et médias d'État.
- Utilisé principalement par les fonctionnaires et chercheurs en politiques publiques.
- Aucun opérateur avancé documenté.

### En résumé

Pour toute recherche sérieuse sur le web russophone, **Yandex est le seul moteur à maîtriser**. Les autres sont soit des portails sans moteur propre (Mail.ru utilise Yandex), soit des acteurs marginaux (Rambler, Sputnik).

---

## Ressources

- [Documentation officielle — Opérateurs de recherche](https://yandex.com/support/search/en/query-language/search-operators.html)
- [Documentation officielle — Recherche de pages et sites](https://yandex.com/support/search/en/query-language/qlanguage.html)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
