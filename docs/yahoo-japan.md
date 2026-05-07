# Yahoo! JAPAN (ヤフージャパン) — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de Yahoo! JAPAN

- **2e moteur de recherche au Japon** avec ~9 % de parts de marché (2025), derrière Google (~82 %) et devant Bing (~7 %).
- Depuis 2010, Yahoo! JAPAN utilise **l'algorithme de Google** pour ses résultats organiques. Les opérateurs de recherche sont donc les mêmes que ceux de Google (voir [docs/google.md](google.md)).
- Malgré ce backend commun, les pages de résultats (SERP) **diffèrent** : Yahoo! JAPAN intègre ses propres services (Shopping, News, enchères) directement dans les résultats.
- En octobre 2023, Yahoo! JAPAN a fusionné avec **LINE** (la plus grande app de messagerie au Japon). Les recherches effectuées dans LINE passent désormais par Yahoo! JAPAN Search.
- L'interface est **entièrement en japonais**. Aucune version anglaise officielle du portail.
- Yahoo! JAPAN fonctionne davantage comme un **portail intégré** que comme un simple moteur de recherche — similaire à Naver en Corée.

---

## 1 — Opérateurs de recherche

Puisque Yahoo! JAPAN utilise l'algorithme de Google, **les mêmes opérateurs fonctionnent** :

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte | `"人工知能 入門"` |
| `-` | Exclure un terme | `ジャガー -車` |
| `OR` | L'un ou l'autre | `東京 OR 大阪 ラーメン` |
| `site:` | Limiter à un domaine | `site:amazon.co.jp ヘッドフォン` |
| `intitle:` | Terme dans le titre | `intitle:チュートリアル Python` |
| `filetype:` | Type de fichier | `filetype:pdf 機械学習 講座` |
| `inurl:` | Terme dans l'URL | `inurl:blog プログラミング` |
| `before:` / `after:` | Filtrer par date | `AI after:2025-01-01` |
| `AROUND(n)` | Proximité | `Python AROUND(3) 非同期` |

> Pour la liste complète, consultez la page [Google](google.md). Tous les opérateurs Google sont applicables sur Yahoo! JAPAN.

---

## 2 — Différences avec Google dans les résultats

Bien que l'algorithme soit le même, les résultats ne sont **pas identiques** à cause des éléments intégrés par Yahoo! JAPAN :

### Éléments propres à Yahoo! JAPAN dans les SERP

| Élément | Description |
|---|---|
| **Yahoo! Shopping** | Listings de produits intégrés (similaire à Google Shopping) |
| **Yahoo! News** | Articles d'actualité du portail Yahoo |
| **Yahoo! Chiebukuro** (知恵袋) | Q&A communautaire (équivalent de Yahoo Answers, toujours actif au Japon) |
| **Yahoo! Auctions** (ヤフオク) | Résultats d'enchères en ligne |
| **PayPay Mall** | Produits du marketplace lié au portefeuille mobile PayPay |
| **LINE intégration** | Contenus issus de l'écosystème LINE depuis la fusion 2023 |

### Biais de classement

Yahoo! JAPAN semble **favoriser le contenu de ses filiales** dans les résultats. Des enquêtes journalistiques ont relevé un traitement préférentiel de certaines propriétés du groupe (comme MyBest, ZOZO, Ikyu). Pour le SEO, cela signifie qu'optimiser uniquement pour Google peut laisser des trous de visibilité sur Yahoo! JAPAN dans certains secteurs concurrentiels.

---

## 3 — L'écosystème Yahoo! JAPAN + LINE

La fusion avec LINE en 2023 a créé un **super-écosystème** unique au Japon :

| Service | Rôle | Utilisateurs |
|---|---|---|
| **LINE** | Messagerie dominante au Japon | ~96 millions d'utilisateurs actifs |
| **Yahoo! JAPAN** | Portail web et recherche | ~54 millions de connectés/mois |
| **PayPay** | Paiement mobile | Leader du paiement sans contact au Japon |
| **Yahoo! Shopping** | E-commerce | Intégré aux résultats de recherche |
| **Yahoo! News** | Agrégateur d'actualités | Source d'info n°1 pour beaucoup de Japonais |
| **Yahoo! Chiebukuro** | Q&A communautaire | Toujours très actif (contrairement à Yahoo Answers) |
| **ヤフオク (Yahoo Auctions)** | Enchères en ligne | Équivalent d'eBay, dominant au Japon |

> La recherche dans l'app **LINE** utilise désormais Yahoo! JAPAN Search, ce qui augmente considérablement le volume de requêtes transitant par Yahoo.

---

## 4 — Publicité : Yahoo! JAPAN Ads vs Google Ads

Yahoo! JAPAN possède sa **propre plateforme publicitaire**, indépendante de Google Ads :

| Caractéristique | Yahoo! JAPAN Ads | Google Ads |
|---|---|---|
| Algorithme organique | Google (identique) | Google |
| Plateforme pub | Indépendante | Indépendante |
| CPC moyen | Souvent **moins cher** | Standard |
| Diffusion | Yahoo! JAPAN + Bing Japon | Google + partenaires |
| Ciblage | Données LINE/PayPay/SoftBank | Données Google |

> Point notable : les annonces textuelles Yahoo! JAPAN apparaissent aussi sur **Bing au Japon**. Pas besoin de compte Bing Ads séparé pour y être visible.

---

## 5 — Conseils pratiques

### Pour le SEO

- **Google first** : puisque Yahoo! JAPAN utilise Google, optimiser pour Google couvre ~90-95 % du marché japonais
- Attention aux **différences de SERP** : vérifiez aussi vos positions sur Yahoo! JAPAN, notamment dans les secteurs e-commerce et actualités
- Le contenu en **japonais natif** est indispensable — une simple traduction ne suffit pas. Les consommateurs japonais attendent des pages plus denses en texte et images que les standards occidentaux
- **Mobile first** : ~80 % des recherches au Japon se font sur mobile

### Pour les non-japonophones

- Utilisez la traduction automatique du navigateur
- Les résultats Yahoo! JAPAN sont très orientés **contenu local japonais**
- Pour le shopping, les résultats intègrent Yahoo Shopping et PayPay Mall — utile pour comparer les prix au Japon

### Pour la publicité

- Si vous ciblez le Japon, lancez des campagnes sur **les deux plateformes** (Google Ads + Yahoo! JAPAN Ads)
- Yahoo! JAPAN Ads offre un ciblage unique grâce aux données LINE et PayPay
- Les CPC sont souvent plus bas sur Yahoo! JAPAN — bon rapport coût/performance

---

## 6 — Limites

- **Pas d'opérateurs exclusifs** : les opérateurs sont ceux de Google, aucune syntaxe spécifique à Yahoo! JAPAN
- **Interface japonaise uniquement** : pas de version anglaise du portail
- **Biais potentiel** vers les propriétés du groupe dans le classement
- **Marché limité** : pertinent uniquement pour le Japon

---

## Ressources

- [Yahoo! JAPAN Search](https://search.yahoo.co.jp/)
- [Yahoo! JAPAN Ads](https://ads-promo.yahoo.co.jp/)
- [LY Corporation (Yahoo + LINE)](https://www.lycorp.co.jp/en/)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
