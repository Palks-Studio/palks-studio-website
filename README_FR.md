<p align="center">
  <img src="docs/images/palks_studio_fr.png"
       alt="Palks Studio homepage — static-first development and automation services overview"
       width="1200">
</p>

> 🇫🇷 Français | [🇬🇧 English](./README.md)

![License](https://img.shields.io/badge/License-LICENSE.md-lightgreen.svg)
![Static Website](https://img.shields.io/badge/Type-Static%20Website-151b1c?style=flat)
![Documentation](https://img.shields.io/badge/Focus-Documentation-0095b1?style=flat)
![Bilingual](https://img.shields.io/badge/Lang-FR%20%2F%20EN-0a5645?style=flat)

<p align="center">
  <a href="https://palks-studio.com">
    <img src="https://img.shields.io/badge/Palks%20Studio-Website-0095b1?style=for-the-badge" />
  </a>
</p>

# Palks Studio — Site statique + boutique numérique  

> Ce dépôt constitue une présentation technique et une documentation du projet.  
> Il ne contient pas de code source téléchargeable ni de fichiers de production.

Ce dépôt contient le site public de **Palks Studio**, qui combine :  

- un site statique en HTML, sobre et sans tracking  
- une boutique numérique légère côté serveur  
- un système autonome de facturation PDF  
- une distribution sécurisée de fichiers téléchargeables par token  

L’ensemble fonctionne sans CMS, sans base de données et sans dépendance SaaS inutile,  
en s’appuyant uniquement sur des fichiers plats (JSON/CSV) et des scripts PHP minimalistes.  

Le dépôt regroupe :  

- le site public (pages, styles, images, contenus)  
- les composants de paiement et de livraison numérique  
- ainsi que les documents accessibles publiquement  
dans un objectif de clarté, de lisibilité et de transparence  

Ce dépôt n’est pas un produit clé en main, ni un framework, ni une bibliothèque logicielle.  
Il s’agit d’un support de référence permettant de comprendre la démarche,  
les outils et les choix techniques portés par Palks Studio.  

---

## À propos de Palks Studio  

Palks Studio conçoit des outils techniques, des structures de documentation  
et des environnements de travail pensés pour être :  

- lisibles  
- compréhensibles  
- autonomes  
- maintenables dans le temps  

L’accent est mis sur :  

- la simplicité fonctionnelle  
- la maîtrise des dépendances  
- la transparence des choix techniques  
- la durabilité plutôt que la mode  

---

## Structure du projet

```
/palks-studio-website/
│
├── fr/                         → Pages du site (FR)
├── en/                         → Pages du site (EN)
│
├── assets/
│   ├── css/
│   │   └── style.css           → Feuille de styles globale
│   └── img/                    → Images et visuels
│
├── robots.txt                  → Règles pour moteurs de recherche
├── sitemap.xml                 → Plan du site pour indexation
├── manifest.json               → Configuration PWA du système
│
├── LICENCE.md                  → Conditions d’utilisation et cadre légal
│
├── core/                       → Backend génération PDF
├── endpoint/                   → Moteur de traitement du formulaire CSV
│
├── storage/
│   └── protected/              → Stockage sécurisé interne
│
├── config/
│   └── download/               → Configuration interne des téléchargements
│
├── library/
│   ├── contracts/              → Génération et templates de contrats
│   ├── batch/                  → Interface d’import et traitement CSV
│   ├── payments/               → Pages de gestion des paiements
│   ├── counters/               → Gestion de la numérotation
│   ├── core/                   → Fonctions internes (génération, email, PDF)
│   └── templates/              → Modèles de documents
│
├── docs/
│   ├── VUE_D_ENSEMBLE.md       → Vue d’ensemble du système
│   ├── PROJECT-OVERVIEW_FR.md  → Vue d’ensemble du projet
│   └── README_FR.md            → Présentation générale
│
├── store/                      → Fichiers produits numériques
│
└── endpoint/
    ├── endpoint_a.php          → Initialisation d’une session de paiement
    ├── endpoint_b.php          → Traitement des événements de paiement
    ├── endpoint_c.php          → Traitement post-paiement
    └── endpoint_d.php          → Point d’accès sécurisé aux fichiers
```


---

## Architecture (résumé)

Le système repose sur une architecture volontairement minimale :  

- Frontend statique (HTML/CSS)  
- Endpoints PHP côté serveur  
- Stockage fichiers plats (JSON / CSV)  
- Stripe comme processeur de paiement  
- Aucune base de données

Objectifs techniques :  

- comportement déterministe  
- traçabilité des opérations  
- dépendances minimales  
- maintenabilité long terme

### Architecture en couches

Le système distingue clairement :  

- la façade web publique (`palks-studio.com`)  
- les points d’ingestion contrôlés (contrat, upload CSV)  
- le moteur de facturation privé (`automation_finance/`)

La présence des formulaires côté site ne signifie  
pas une exécution de la facturation côté web.

Toute génération financière reste strictement  
pilotée par les scripts CLI du moteur.

---

## Le site Palks Studio (version publique)

Les pages du site présentent :  

- le studio et sa démarche  
- les ressources proposées  
- les fondations conceptuelles  
- les outils techniques développés  
- les notes techniques et réflexions d’ingénierie  
- les pages légales et informatives  
- ainsi que l’accès à la boutique numérique  
- ainsi qu'un générateur de devis PDF gratuit, bilingue et entièrement côté navigateur.

Cet outil fonctionne entièrement côté client (JavaScript + jsPDF) et ne transmet  
aucune donnée à un serveur. Il permet de créer rapidement un devis professionnel  
avec plusieurs lignes de prestations, calcul automatique HT / TVA / TTC,  
et export direct en PDF.

Le générateur est totalement indépendant du pipeline de facturation  
(Stripe → Webhook → Facture → Token → Téléchargement) et ne crée  
ni transaction ni archive côté serveur.

### Ressources et distribution numérique

Certaines ressources sont fournies sous forme de documents, archives ou fichiers téléchargeables, notamment lorsque le contenu comprend :  

- plusieurs fichiers  
- des structures complètes  
- des exemples ou supports pédagogiques  
- des outils ou gabarits réutilisables  

Ces éléments sont regroupés dans des dossiers dédiés afin de préserver  
la clarté du dépôt et la traçabilité des livrables.

La distribution des fichiers se fait via un système sécurisé à lien temporaire  
et usage unique, journalisé côté serveur.

---

## Ce que ce dépôt est

- Un site public statique + boutique numérique légère  
- Une vitrine technique et documentaire  
- Un point de référence public  
- Un support de compréhension  
- Une démonstration de structure et de méthode  
- Un exemple concret d’architecture sobre sans CMS ni base de données

---

## Ce que ce dépôt n’est pas

- Un framework e-commerce  
- Une plateforme SaaS  
- Un produit générique clé en main  
- Une bibliothèque logicielle  
- Un espace de support ou de mises à jour contractuelles  

Les clés, secrets et certains chemins de production ne sont pas exposés ici.

---

## Principes de conception

Palks Studio repose sur quelques principes constants :  

- simplicité fonctionnelle  
- maîtrise des dépendances  
- transparence technique  
- lisibilité du code et des structures  
- stabilité dans le temps plutôt que complexité

---

## Transparence et démarche

Palks Studio fait le choix de :  

- documenter sérieusement ses projets  
- expliquer les choix et les limites  
- éviter les promesses floues  
- ne pas masquer le travail derrière du marketing  
- privilégier la lisibilité et la traçabilité plutôt que la complexité  

Le code, les structures et la documentation sont pensés pour être compris  
avant toute décision d’utilisation ou d’achat.

Ce dépôt participe pleinement à cette démarche de transparence.

---

© Palks Studio — voir LICENSE.md  
- https://palks-studio.com
