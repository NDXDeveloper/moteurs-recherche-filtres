# Seznam.cz — Filtres de recherche

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

---

## Particularités de Seznam

- **Moteur tchèque indépendant**, fondé en 1996 par Ivo Lukačovič. C'est le seul moteur d'Europe de l'Est (hors Yandex) à posséder son propre index et crawler (**SeznamBot**).
- Environ **10-11 % de parts de marché** en Tchéquie (2025), derrière Google (~82 %) mais devant Bing. Il reste incontournable pour cibler le public tchécophone.
- Seznam fonctionne comme un **portail intégré** : moteur de recherche, email (Email.cz), cartes (Mapy.cz), actualités (Novinky.cz), vidéo (Stream.cz), shopping (Zboží.cz), et plus de 30 services.
- Possède sa propre régie publicitaire : **Sklik** (équivalent de Google Ads, souvent moins cher en CPC).
- L'interface et les résultats sont **entièrement en tchèque**. Pas de version anglaise du moteur.
- SeznamBot crawle les domaines tchèques plus agressivement que les domaines internationaux.

---

## 1 — Opérateurs de recherche

Seznam supporte un ensemble limité d'opérateurs, inspirés de la syntaxe Google/Bing :

| Opérateur | Rôle | Exemple |
|---|---|---|
| `" "` | Correspondance exacte | `"strojové učení"` |
| `-` | Exclure un terme | `jaguar -auto` |
| `site:` | Limiter à un domaine | `site:seznam.cz` |
| `filetype:` | Type de fichier | `filetype:pdf kurz python` |
| `intitle:` | Terme dans le titre | `intitle:návod docker` |

> **Note** : Seznam ne supporte pas `OR`, `inurl:`, `intext:`, `AROUND()`, `before:`/`after:`, ni la plupart des opérateurs avancés disponibles sur Google. Le filtrage se fait principalement via l'interface.

---

## 2 — Filtrage via l'interface

### Catégories de résultats

Après une recherche, Seznam affiche des onglets pour filtrer par type :

| Onglet | Contenu |
|---|---|
| Web | Résultats classiques |
| Obrázky (Images) | Recherche d'images |
| Videa (Vidéos) | Contenus vidéo (Stream.cz et autres) |
| Zprávy (Actualités) | Articles de presse tchèques |
| Mapy (Cartes) | Résultats géolocalisés via Mapy.cz |
| Zboží (Shopping) | Produits du comparateur Zboží.cz |
| Firmy (Entreprises) | Annuaire d'entreprises Firmy.cz |

### Filtres temporels

Disponibles via l'interface après une recherche :

- Dernières 24 heures
- Dernière semaine
- Dernier mois
- Dernière année
- Période personnalisée

---

## 3 — L'écosystème Seznam

Ce qui fait la force de Seznam, ce n'est pas ses opérateurs (limités) mais son **écosystème intégré** très utilisé en Tchéquie :

### Services principaux

| Service | URL | Équivalent |
|---|---|---|
| **Mapy.cz** | [mapy.cz](https://mapy.cz) | Google Maps — cartes très détaillées de la Tchéquie, avec sentiers de randonnée |
| **Email.cz** | [email.cz](https://email.cz) | Gmail — des millions de comptes actifs en Tchéquie |
| **Novinky.cz** | [novinky.cz](https://www.novinky.cz) | Google News — principal agrégateur d'actualités tchèques |
| **Stream.cz** | [stream.cz](https://www.stream.cz) | YouTube — plateforme vidéo tchèque |
| **Zboží.cz** | [zbozi.cz](https://www.zbozi.cz) | Google Shopping — comparateur de prix dominant en Tchéquie |
| **Firmy.cz** | [firmy.cz](https://www.firmy.cz) | Google Business — annuaire d'entreprises locales |
| **Sreality.cz** | [sreality.cz](https://www.sreality.cz) | Immobilier — portail leader en Tchéquie |

### Mapy.cz — un atout unique

Mapy.cz est considéré comme **supérieur à Google Maps** pour la Tchéquie et les pays voisins (Slovaquie, Autriche, Pologne). Il propose des cartes touristiques très détaillées, des sentiers de randonnée et de cyclisme, et fonctionne hors-ligne.

---

## 4 — Outils pour webmasters

### Seznam Webmaster Tools

Équivalent de Google Search Console, indépendant et dédié à Seznam :

- Soumettre un sitemap
- Vérifier l'indexation par SeznamBot
- Diagnostiquer des erreurs d'exploration
- Suivre les performances de recherche

> Indispensable si vous ciblez le marché tchèque.

### Sklik (publicité)

| Caractéristique | Détail |
|---|---|
| Modèle | PPC (pay-per-click), similaire à Google Ads |
| CPC moyen | Généralement **moins cher** que Google Ads pour le marché tchèque |
| Ciblage | Mots-clés, démographique, retargeting |
| Diffusion | Résultats Seznam + réseau de sites partenaires |

---

## 5 — Conseils pratiques

### Pour le SEO sur Seznam

- SeznamBot respecte le `robots.txt` et se comporte comme Googlebot
- Pas de soumission manuelle nécessaire — assurez-vous simplement que votre site est crawlable
- Le contenu en **tchèque de qualité** est fortement favorisé
- Seznam intègre ses propres médias (Novinky.cz, Stream.cz) directement dans les résultats — la concurrence organique est donc différente de Google
- Enregistrez votre site dans **Firmy.cz** si vous avez une présence locale

### Pour les non-tchécophones

- Utilisez la traduction automatique du navigateur
- Les résultats de Seznam sont très orientés contenu local — peu utile pour des recherches internationales
- Pour le shopping, Zboží.cz donne souvent de meilleurs résultats que Google Shopping pour les produits disponibles en Tchéquie

---

## 6 — Limites

- **Très peu d'opérateurs avancés** — le filtrage repose sur l'interface
- **Langue unique** : optimisé exclusivement pour le tchèque
- **Portée géographique limitée** : pertinent uniquement pour la Tchéquie (et partiellement la Slovaquie)
- **Pas de `OR`, `inurl:`, `intext:`, `cache:`, `related:`, `AROUND()`**
- **Pas de filtrage temporel via opérateur** — uniquement via l'interface
- L'index est plus petit que celui de Google — certaines pages internationales ne sont pas indexées

---

## Ressources

- [Seznam — Aide sur la recherche (en anglais)](https://o-seznam.cz/napoveda/vyhledavani/en/)
- [Seznam Webmaster Tools](https://search.seznam.cz/webmaster/)
- [Sklik (plateforme publicitaire)](https://www.sklik.cz/)
- [Mapy.cz](https://mapy.cz)

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
