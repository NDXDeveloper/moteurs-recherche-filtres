# 🔍 Maîtriser les filtres de recherche — Guide multi-moteurs

> Trouvez exactement ce que vous cherchez sur Google, Bing, DuckDuckGo, Yandex et Brave Search.

---

## Moteurs couverts

### 🌍 Internationaux

| Moteur | Vie privée | Index propre | Page du guide |
|---|---|---|---|
| **Google** | ⭐ | ✅ | [→ docs/google.md](/docs/google.md) |
| **Bing** | ⭐⭐ | ✅ | [→ docs/bing.md](/docs/bing.md) |
| **DuckDuckGo** | ⭐⭐⭐⭐ | ❌ (Bing) | [→ docs/duckduckgo.md](/docs/duckduckgo.md) |
| **Yandex** | ⭐⭐ | ✅ | [→ docs/yandex.md](/docs/yandex.md) |
| **Brave Search** | ⭐⭐⭐⭐⭐ | ✅ | [→ docs/brave.md](/docs/brave.md) |

### 🌏 Asie

| Moteur | Pays dominant | Index propre | Page du guide |
|---|---|---|---|
| **Baidu** (百度) | 🇨🇳 Chine | ✅ | [→ docs/baidu.md](/docs/baidu.md) |
| **Yahoo! JAPAN** (ヤフー) | 🇯🇵 Japon | ❌ (Google) | [→ docs/yahoo-japan.md](/docs/yahoo-japan.md) |
| **Naver** (네이버) | 🇰🇷 Corée du Sud | ✅ | [→ docs/naver.md](/docs/naver.md) |

### 🌍 Europe de l'Est

| Moteur | Pays dominant | Index propre | Page du guide |
|---|---|---|---|
| **Seznam.cz** | 🇨🇿 Tchéquie | ✅ | [→ docs/seznam.md](/docs/seznam.md) |
| Mail.ru, Rambler, Sputnik | 🇷🇺 Russie | ❌ (Yandex) | [→ mentionnés dans docs/yandex.md](/docs/yandex.md#8--les-autres-moteurs-russes) |

### 🔒 Sécurité / OSINT / Hacking éthique

| Outil | Spécialité | Page du guide |
|---|---|---|
| **Google Dorking** | Trouver des données exposées via les opérateurs Google | [→ docs/securite-osint.md](/docs/securite-osint.md) |
| **Shodan** | Appareils et IoT connectés à Internet | [→ docs/securite-osint.md](/docs/securite-osint.md#2--shodan) |
| **Censys** | Certificats TLS et infrastructure réseau | [→ docs/securite-osint.md](/docs/securite-osint.md#3--censys) |
| **ZoomEye / FOFA** | Cyberespace chinois et scan mondial | [→ docs/securite-osint.md](/docs/securite-osint.md#4--zoomeye) |

📊 **[Tableau comparatif de tous les opérateurs](/docs/comparatif.md)**

---

## Structure du repo

```
moteurs-recherche-filtres/
├── README.md              ← vous êtes ici
├── SOMMAIRE.md            ← table des matières détaillée
├── LICENSE
└── docs/
    ├── google.md          ← opérateurs Google
    ├── bing.md            ← opérateurs Bing
    ├── duckduckgo.md      ← opérateurs DuckDuckGo
    ├── yandex.md          ← opérateurs Yandex
    ├── brave.md           ← opérateurs Brave Search
    ├── baidu.md           ← opérateurs Baidu (Chine)
    ├── yahoo-japan.md     ← Yahoo! JAPAN (Japon)
    ├── naver.md           ← opérateurs Naver (Corée du Sud)
    ├── seznam.md          ← opérateurs Seznam (Tchéquie)
    ├── securite-osint.md  ← Google Dorking, Shodan, Censys, ZoomEye…
    └── comparatif.md      ← tableau croisé de compatibilité
```

---

## Aide-mémoire express — Opérateurs universels

Ces opérateurs fonctionnent sur **tous** les moteurs (ou presque) :

```
"expression exacte"      →  Correspondance exacte
-terme                   →  Exclure un mot
site:domaine.com         →  Limiter à un domaine
filetype:pdf             →  Filtrer par type de fichier
intitle:mot              →  Mot dans le titre de la page
```

Pour les différences et particularités de chaque moteur, consultez les pages individuelles ou le [comparatif](/docs/comparatif.md).

---

## Comment utiliser ce guide

1. **Débutant** — Commencez par la page [Google](/docs/google.md), c'est le moteur le plus complet en opérateurs.
2. **Intermédiaire** — Consultez le [comparatif](/docs/comparatif.md) pour savoir quels opérateurs fonctionnent sur quel moteur.
3. **Avancé** — Explorez les spécificités de [Yandex](/docs/yandex.md) (opérateurs de proximité uniques) et [Brave](/docs/brave.md) (Goggles).
4. **Marchés asiatiques** — Consultez [Baidu](/docs/baidu.md) pour la Chine, [Yahoo! JAPAN](/docs/yahoo-japan.md) pour le Japon et [Naver](/docs/naver.md) pour la Corée du Sud.
5. **Sécurité / OSINT** — La page [securite-osint.md](/docs/securite-osint.md) couvre le Google Dorking, Shodan, Censys, ZoomEye et les outils de threat intelligence.

---

## Contribuer

Les contributions sont les bienvenues. Pour proposer un ajout :

1. Forkez le repo
2. Créez une branche (`git checkout -b feat/nouveau-moteur`)
3. Committez vos changements
4. Ouvrez une Pull Request

---

## Licence

Ce contenu est mis à disposition sous licence [MIT](/LICENSE).

---

## Auteur

**Nicolas DEOUX** — [LinkedIn](https://www.linkedin.com/in/nicolas-deoux-ab295980) · [GitHub](https://github.com/NDXDeveloper)
