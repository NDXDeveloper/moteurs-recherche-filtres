# Baidu (百度) — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de Baidu

- **Moteur dominant en Chine** avec plus de 60 % de parts de marché. Indispensable pour toute recherche ciblant le web chinois.
- L'interface et la documentation officielle sont **entièrement en chinois**. La page de recherche avancée est accessible à : `baidu.com/gaoji/advanced.html`
- Baidu **découpe automatiquement** les requêtes longues en sous-mots (segmentation du chinois). Utilisez les guillemets `" "` pour forcer une expression exacte.
- Les résultats sont fortement orientés vers le **contenu hébergé en Chine** et soumis à la censure gouvernementale.
- Baidu privilégie les contenus de son propre écosystème : Baidu Baike (encyclopédie), Baidu Zhidao (Q&A), Baidu Tieba (forums).
- Les langues disponibles se limitent à : toutes, chinois simplifié, chinois traditionnel.

---

## 1 — Opérateurs de base

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte (empêche la segmentation) | `"人工智能应用"` |
| `-` | Exclure un terme | `苹果 -手机` (pomme sans téléphone) |
| `\|` | OU logique | `深度学习 \| 机器学习` |
| `( )` | Grouper des conditions | `(Python \| Java) 教程` |

> **Important** : l'opérateur `-` (exclusion) doit être précédé d'un **espace** et directement suivi du terme à exclure, sans espace après le tiret.

---

## 2 — Filtres de site et d'URL

| Opérateur | Rôle | Exemple |
|---|---|---|
| `site:` | Limiter à un domaine | `site:zhihu.com 人工智能` |
| `inurl:` | Terme dans l'URL | `inurl:blog Python 教程` |

### Exemples

Rechercher sur l'encyclopédie Baidu :

```
site:baike.baidu.com 量子计算
```

Trouver des pages dont l'URL contient « download » :

```
inurl:download Python
```

---

## 3 — Filtres de contenu

| Opérateur | Rôle | Exemple |
|---|---|---|
| `intitle:` | Terme dans le titre de la page | `intitle:教程 Docker` |
| `filetype:` | Type de fichier | `filetype:pdf 机器学习 课程` |

### Types de fichier supportés

| Extension | Format |
|---|---|
| `pdf` | PDF |
| `doc` | Word |
| `xls` | Excel |
| `ppt` | PowerPoint |
| `rtf` | Rich Text |
| `all` | Tous les formats supportés |

---

## 4 — Filtres temporels

Baidu propose un filtrage temporel **via l'interface** ou les paramètres d'URL.

### Via l'interface

Après une recherche, cliquez sur « 搜索工具 » (outils de recherche), puis filtrez par :

- Dernière semaine (一周内)
- Dernier mois (一月内)
- Dernière année (一年内)
- Plage personnalisée

### Via le paramètre d'URL `lm=`

| Paramètre | Période |
|---|---|
| `lm=1` | Dernier jour |
| `lm=7` | Dernière semaine |
| `lm=30` | Dernier mois |
| `lm=365` | Dernière année |

---

## 5 — Recherche avancée via l'interface

La page de recherche avancée (`baidu.com/gaoji/advanced.html`) offre des champs pour :

- Tous les mots (含以下全部的关键词)
- Expression exacte (含以下的完整关键词)
- Au moins un mot (含以下任意一个关键词)
- Exclure des mots (不含以下关键词)
- Limiter au titre (关键词位置 → 标题)
- Limiter à un site
- Type de fichier
- Plage temporelle

> **Astuce** : si vous ne lisez pas le chinois, utilisez la traduction automatique de votre navigateur sur cette page.

---

## 6 — Combinaisons utiles

### Trouver des cours gratuits en PDF

```
filetype:pdf intitle:教程 "深度学习"
```

### Rechercher sur un forum spécifique

```
site:tieba.baidu.com Python 入门
```

### Chercher sur Zhihu (Q&A populaire en Chine)

```
site:zhihu.com "机器学习" 入门指南
```

### Exclure les résultats commerciaux

```
Python 教程 -site:baidu.com -广告
```

---

## 7 — Limites à connaître

- **Censure** : certains termes sont filtrés ou bloqués par le gouvernement chinois. Les résultats ne reflètent pas toujours l'ensemble du web.
- **Écosystème fermé** : Baidu favorise fortement ses propres services (Baike, Zhidao, Tieba, Wenku). Les sites externes apparaissent souvent plus bas.
- **Pas de `AROUND(n)`** : aucun opérateur de proximité n'est disponible.
- **Pas de `related:`** : pas d'équivalent pour trouver des sites similaires.
- **Pas de `cache:`** : Baidu propose un « 百度快照 » (snapshot) mais il est accessible uniquement via un lien dans les résultats, pas via un opérateur.
- Le support des opérateurs peut être **moins fiable** que sur Google — certains sont parfois ignorés silencieusement.

---

## Ressources

- [Page de recherche avancée](https://www.baidu.com/gaoji/advanced.html)
- [Baidu Webmaster Tools](https://ziyuan.baidu.com/)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
