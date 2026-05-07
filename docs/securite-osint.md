# Moteurs de recherche pour la sécurité et l'OSINT

[← Retour au sommaire](../SOMMAIRE.md) · [Comparatif →](comparatif.md)

> ⚠️ **Avertissement légal** : les techniques et outils présentés ici sont destinés à un usage **éthique et légal** : tests d'intrusion autorisés, bug bounty, audit de sécurité, recherche académique et OSINT. Accéder à des systèmes ou des données sans autorisation est **illégal** dans la quasi-totalité des juridictions (CFAA aux États-Unis, articles 323-1 et suivants du Code pénal en France, etc.).

---

## Vue d'ensemble

Les professionnels de la sécurité n'utilisent pas (que) Google. Ils s'appuient sur un écosystème de moteurs spécialisés qui indexent non pas des pages web, mais des **appareils connectés**, des **certificats TLS**, des **ports ouverts**, des **fuites de données** et du **code source**.

| Catégorie | Outils principaux |
|---|---|
| Google Dorking | Google + GHDB, DorkSearch |
| Appareils / IoT | Shodan, Censys, ZoomEye, FOFA |
| Threat intelligence | GreyNoise, Pulsedive, VirusTotal |
| Fuites et dark web | Intelligence X, Dehashed, LeakIX |
| Code source | SearchCode, Grep.app |
| Réseau / DNS | DNSDumpster, SecurityTrails, FullHunt |
| Wi-Fi | WiGLE |
| Vulnérabilités | ExploitDB |

---

## 1 — Google Dorking (Google Hacking)

### Qu'est-ce que c'est ?

Le Google Dorking consiste à utiliser les opérateurs avancés de Google (voir [docs/google.md](google.md)) pour trouver des informations sensibles **involontairement exposées** sur le web : pages d'administration, fichiers de configuration, mots de passe, sauvegardes de bases de données, etc.

Le terme « dork » désigne une requête spécifique conçue pour révéler ce type d'information. La technique a été popularisée en 2002 par le chercheur en sécurité Johnny Long.

### Exemples de dorks classiques

```
intitle:"index of" "parent directory"
```

Trouve des répertoires de serveur ouverts et navigables.

```
filetype:sql "insert into" password
```

Recherche des dumps SQL contenant des mots de passe.

```
intitle:"webcam" inurl:view
```

Trouve des webcams accessibles publiquement.

```
filetype:env "DB_PASSWORD"
```

Localise des fichiers `.env` exposés contenant des identifiants de base de données.

```
site:example.com filetype:pdf intitle:"confidentiel" -inurl:public
```

Cherche des PDF confidentiels sur un domaine, excluant les dossiers publics.

### Google Hacking Database (GHDB)

La **GHDB** est une base de données maintenue par Offensive Security (créateurs de Kali Linux) qui répertorie des milliers de dorks classés par catégorie :

- Pages de connexion / panneaux d'administration
- Fichiers contenant des mots de passe
- Répertoires ouverts
- Messages d'erreur révélant des informations serveur
- Appareils connectés mal configurés
- Données sensibles (bases, backups, logs)

🔗 [exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)

### Outils d'automatisation

| Outil | Rôle |
|---|---|
| **DorkSearch / DorkSearch PRO** | Générateur de dorks avec catégories prédéfinies |
| **GoogDork** | Script Python d'automatisation de dorks |
| **GHDB Scripts** | Requêtes GHDB intégrées dans des workflows |

### Se protéger contre le Google Dorking

- Configurer correctement `robots.txt` pour bloquer l'indexation des zones sensibles
- Ne jamais exposer de fichiers `.env`, `.sql`, `.bak`, `.log` sur un serveur web
- Auditer régulièrement son propre site avec des dorks
- Utiliser des headers `X-Robots-Tag: noindex` sur les pages sensibles

---

## 2 — Shodan

🔗 [shodan.io](https://www.shodan.io)

### Qu'est-ce que c'est ?

Shodan est souvent surnommé « le moteur de recherche des hackers ». Contrairement à Google qui indexe des **pages web**, Shodan indexe des **appareils connectés à Internet** : serveurs, routeurs, webcams, systèmes industriels (SCADA/ICS), objets IoT, bases de données, etc.

### Syntaxe de recherche

| Filtre | Rôle | Exemple |
|---|---|---|
| `port:` | Filtrer par port | `port:22` (SSH) |
| `country:` | Filtrer par pays | `country:FR` |
| `city:` | Filtrer par ville | `city:Paris` |
| `org:` | Filtrer par organisation | `org:"Orange S.A."` |
| `os:` | Filtrer par système d'exploitation | `os:linux` |
| `product:` | Filtrer par logiciel/service | `product:nginx` |
| `version:` | Filtrer par version | `product:apache version:2.4.49` |
| `hostname:` | Filtrer par nom d'hôte | `hostname:.gouv.fr` |
| `net:` | Filtrer par plage IP (CIDR) | `net:203.0.113.0/24` |
| `has_screenshot:` | Appareils avec capture d'écran | `has_screenshot:true port:3389` |
| `vuln:` | Filtrer par CVE (compte payant) | `vuln:CVE-2021-44228` |
| `ssl:` | Recherche dans les certificats SSL | `ssl:"example.com"` |
| `http.title:` | Titre de la page HTTP | `http.title:"Dashboard"` |
| `http.status:` | Code de statut HTTP | `http.status:200` |

### Exemples

Trouver des serveurs Apache vulnérables en France :

```
product:apache country:FR port:80
```

Trouver des bases MongoDB exposées sans authentification :

```
product:mongodb port:27017 "authentication"
```

Webcams accessibles :

```
has_screenshot:true port:554
```

---

## 3 — Censys

🔗 [search.censys.io](https://search.censys.io)

### Qu'est-ce que c'est ?

Censys scanne en continu l'ensemble de l'espace IPv4 et indexe les **hôtes**, **services** et **certificats TLS**. Il est particulièrement puissant pour l'analyse de certificats et la découverte de sous-domaines.

### Syntaxe de recherche

| Filtre | Rôle | Exemple |
|---|---|---|
| `services.port:` | Port ouvert | `services.port:443` |
| `services.service_name:` | Nom du service | `services.service_name:SSH` |
| `location.country:` | Pays | `location.country:France` |
| `services.tls.certificates.leaf.subject.common_name:` | Nom dans le certificat | `...common_name:example.com` |
| `services.http.response.html_title:` | Titre HTML | `...html_title:"Login"` |
| `services.software.product:` | Logiciel détecté | `...product:OpenSSH` |
| `autonomous_system.name:` | Nom de l'AS | `autonomous_system.name:OVH` |

### Cas d'usage

- Découvrir tous les sous-domaines d'une organisation via les certificats TLS
- Identifier des serveurs avec des versions obsolètes
- Cartographier l'infrastructure exposée d'une entreprise

---

## 4 — ZoomEye

🔗 [zoomeye.org](https://www.zoomeye.org)

Développé par la société chinoise **Knownsec**, ZoomEye est l'équivalent asiatique de Shodan. Il combine le scan d'appareils (Xmap) et le scan de services web (Wmap).

### Syntaxe de recherche

| Filtre | Rôle | Exemple |
|---|---|---|
| `app:` | Nom de l'application | `app:nginx` |
| `port:` | Port | `port:3306` |
| `os:` | Système d'exploitation | `os:windows` |
| `country:` | Pays | `country:CN` |
| `city:` | Ville | `city:Shanghai` |
| `device:` | Type d'appareil | `device:router` |
| `service:` | Nom du service | `service:ssh` |
| `hostname:` | Nom d'hôte | `hostname:*.edu.cn` |
| `ssl:` | Contenu du certificat SSL | `ssl:"target.com"` |

ZoomEye est particulièrement performant pour le **cyberespace chinois** et offre une API gratuite avec un quota mensuel.

---

## 5 — FOFA

🔗 [fofa.info](https://fofa.info)

Autre moteur chinois, développé par **Baimaohui**. FOFA se distingue par sa couverture très large et ses filtres détaillés.

| Filtre | Rôle | Exemple |
|---|---|---|
| `title=` | Titre de la page | `title="admin panel"` |
| `body=` | Contenu du corps | `body="password"` |
| `domain=` | Domaine | `domain="example.com"` |
| `port=` | Port | `port="8080"` |
| `protocol=` | Protocole | `protocol="https"` |
| `country=` | Pays | `country="FR"` |
| `region=` | Région | `region="Île-de-France"` |
| `os=` | Système d'exploitation | `os="Windows"` |
| `server=` | Serveur HTTP | `server="Apache"` |
| `cert=` | Contenu du certificat | `cert="example.com"` |
| `banner=` | Bannière du service | `banner="SSH-2.0"` |

---

## 6 — Autres moteurs spécialisés

### Threat Intelligence

| Outil | URL | Spécialité |
|---|---|---|
| **GreyNoise** | [viz.greynoise.io](https://viz.greynoise.io) | Filtre le « bruit » Internet (scans massifs) vs. activité ciblée |
| **Pulsedive** | [pulsedive.com](https://pulsedive.com) | Enrichissement d'IOC multi-sources |
| **VirusTotal** | [virustotal.com](https://www.virustotal.com) | Analyse de fichiers, URL et domaines malveillants |

### Fuites de données et dark web

| Outil | URL | Spécialité |
|---|---|---|
| **Intelligence X** | [intelx.io](https://intelx.io) | Archive du dark web, fuites, pastes, données Tor |
| **Dehashed** | [dehashed.com](https://www.dehashed.com) | Recherche dans les bases de données de fuites (emails, mots de passe) |
| **LeakIX** | [leakix.net](https://leakix.net) | Détection et indexation de fuites en temps réel |

### Code source

| Outil | URL | Spécialité |
|---|---|---|
| **SearchCode** | [searchcode.com](https://searchcode.com) | Recherche dans les dépôts open source |
| **Grep.app** | [grep.app](https://grep.app) | Grep dans les repos GitHub publics |

### Réseau et DNS

| Outil | URL | Spécialité |
|---|---|---|
| **DNSDumpster** | [dnsdumpster.com](https://dnsdumpster.com) | Cartographie DNS d'un domaine |
| **SecurityTrails** | [securitytrails.com](https://securitytrails.com) | Historique DNS, sous-domaines, WHOIS |
| **FullHunt** | [fullhunt.io](https://fullhunt.io) | Découverte de la surface d'attaque |

### Wi-Fi

| Outil | URL | Spécialité |
|---|---|---|
| **WiGLE** | [wigle.net](https://wigle.net) | Cartographie mondiale des réseaux Wi-Fi (wardriving) |

### Vulnérabilités et exploits

| Outil | URL | Spécialité |
|---|---|---|
| **ExploitDB** | [exploit-db.com](https://www.exploit-db.com) | Base de données d'exploits et de preuves de concept |
| **GHDB** | [exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database) | Base de dorks Google classés par catégorie |
| **CVE Details** | [cvedetails.com](https://www.cvedetails.com) | Détails des vulnérabilités CVE |

---

## 7 — Tableau comparatif des moteurs d'infrastructure

| Fonction | Shodan | Censys | ZoomEye | FOFA |
|---|:---:|:---:|:---:|:---:|
| Scan IPv4 | ✅ | ✅ | ✅ | ✅ |
| Scan IPv6 | ⚠️ | ✅ | ✅ | ✅ |
| Certificats TLS | ✅ | ✅ (spécialité) | ✅ | ✅ |
| Captures d'écran | ✅ | ❌ | ❌ | ❌ |
| API gratuite | ✅ (limitée) | ✅ (limitée) | ✅ (quota) | ✅ (quota) |
| Filtre par CVE | ✅ (payant) | ❌ | ❌ | ❌ |
| Force : zone géo | 🌍 mondial | 🌍 mondial | 🇨🇳 Chine/Asie | 🇨🇳 Chine/Asie |
| Intégrations | Nmap, Metasploit, Maltego | API REST | API REST | API REST |

---

## 8 — Bonnes pratiques

1. **Obtenez toujours une autorisation** avant de scanner ou tester un système qui ne vous appartient pas
2. **Documentez vos actions** dans un cadre de pentest ou de bug bounty
3. **Ne stockez jamais** de données personnelles découvertes sans base légale
4. **Signalez les vulnérabilités** de manière responsable (disclosure responsable)
5. **Utilisez un VPN** et des comptes dédiés pour vos recherches OSINT
6. **Respectez les conditions d'utilisation** de chaque plateforme

---


🔝 Retour au [Sommaire](/SOMMAIRE.md) · [Comparatif →](comparatif.md)
