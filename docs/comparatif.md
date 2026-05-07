# Tableau comparatif des opérateurs de recherche

[← Retour au sommaire](../SOMMAIRE.md)

---

## Légende

- ✅ Supporté
- ❌ Non supporté
- ⚠️ Support partiel ou comportement différent
- 🔄 Équivalent sous un autre nom

---

## Opérateurs de base

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Guillemets `" "` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Exclure `-` | ✅ | ✅ | ✅ | 🔄 `~~` | ✅ | ✅ | ❌ | ✅ |
| `OR` / `\|` | ✅ | ✅ (maj.) | ✅ | ✅ `\|` | ✅ (maj.) | ✅ `\|` | ❌ | ❌ |
| `AND` | implicite | ✅ `AND`/`&` | implicite | ✅ `&&`/`&` | ✅ (maj.) | implicite | implicite | implicite |
| `NOT` | 🔄 `-` | ✅ | 🔄 `-` | 🔄 `~~` | ✅ | 🔄 `-` | ❌ | 🔄 `-` |
| Joker `*` | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| Parenthèses `( )` | ✅ | ✅ | ⚠️ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Forcer un mot vide `+` | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |

---

## Filtres de site et d'URL

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `site:` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `-site:` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `inurl:` | ✅ | ❌ | ⚠️ | 🔄 `url:` | ❌ | ✅ | ❌ | ❌ |
| `allinurl:` | ✅ | ❌ | ⚠️ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `url:` (URL exacte) | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| `host:` | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| `rhost:` (domaine inversé) | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |

---

## Filtres de contenu

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `intitle:` | ✅ | ✅ | ✅ | 🔄 `title:` | ✅ | ✅ | ❌ | ✅ |
| `allintitle:` | ✅ | ❌ | ⚠️ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `intext:`/`inbody:` | ✅ `intext:` | ✅ `inbody:` | ✅ `intext:` | ❌ | ✅ `inbody:` | ❌ | ❌ | ❌ |
| `allintext:` | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `inanchor:` | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `inpage:` (titre + corps) | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| `instreamset:` | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

---

## Filtres de fichier

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `filetype:` | ✅ | ✅ | ✅ | 🔄 `mime:` | ✅ | ✅ | ✅ | ✅ |
| `ext:` | 🔄 `filetype:` | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| `contains:` (lien vers un type) | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

---

## Filtres temporels

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `before:` / `after:` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `date:` (plage) | ❌ | ❌ | ✅ | ✅ (année) | ❌ | ❌ | ❌ | ❌ |
| Filtre temporel via l'interface | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Paramètre d'URL temporel | ✅ `&tbs=qdr:` | ❌ | ❌ | ❌ | ❌ | ✅ `lm=` | ❌ | ❌ |

---

## Filtres de langue et localisation

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `lang:` / `language:` | ❌ | ✅ `language:` | ❌ | ✅ `lang:` | ✅ `lang:` | ⚠️ interface | ❌ | ❌ |
| `loc:` / `location:` | ❌ | ✅ `location:` | ❌ | ❌ | ✅ `loc:` | ❌ | ❌ | ❌ |
| `region:` | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Filtre régional via l'interface | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ limité | ✅ | ⚠️ CZ only |

---

## Opérateurs de proximité

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Proximité entre termes | ✅ `AROUND(n)` | ✅ `near:n` | ❌ | ✅ `/n` | ❌ | ❌ | ❌ | ❌ |
| Contrôle de l'ordre des mots | ❌ | ❌ | ❌ | ✅ `/-n` | ❌ | ❌ | ❌ | ❌ |

---

## Opérateurs spéciaux

| Fonction | Google | Bing | DuckDuckGo | Yandex | Brave | Baidu | Naver | Seznam |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `cache:` | ✅ | ❌ | ❌ | ❌ | ❌ | ⚠️ snapshot | ❌ | ❌ |
| `related:` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `define:` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `ip:` | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `feed:` (flux RSS) | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `prefer:` | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `imagesize:` | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `<<` (AND non-ranking) | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| `!` (forme exacte du mot) | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| !bangs | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ |
| Goggles (re-ranking) | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| `\` (Feeling Lucky/Ducky) | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Recherche intégrée par catégorie | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

---

## Quel moteur pour quel usage ?

| Besoin | Meilleur choix | Pourquoi |
|---|---|---|
| Opérateurs les plus complets | **Google** | Plus grand nombre d'opérateurs fonctionnels |
| Vie privée maximale | **Brave Search** | Index indépendant + pas de tracking |
| Recherche rapide multi-sites | **DuckDuckGo** | !bangs vers des milliers de sites |
| Web russophone / CEI | **Yandex** | Meilleur index pour cette zone (~74 % en Russie) |
| Recherche d'images inversée | **Yandex** | Reconnaissance faciale intégrée |
| Contrôle fin de proximité | **Yandex** | Opérateur `/n` avec contrôle d'ordre |
| Personnalisation des résultats | **Brave Search** | Goggles (re-ranking communautaire) |
| Opérateurs Bing-specific | **Bing** | Opérateurs uniques : `ip:`, `contains:`, `near:` |
| Web chinois | **Baidu** | Index dominant en Chine, écosystème intégré |
| Marché sud-coréen | **Naver** | Portail intégré, contenu local + communautaire |
| Marché tchèque | **Seznam** | Index local indépendant, Mapy.cz, Zboží.cz |
| Sécurité / OSINT | **Shodan, Censys** | Scan d'appareils, certificats, ports ouverts |
| Google Dorking | **Google + GHDB** | Base de dorks pour trouver des données exposées |

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) 
