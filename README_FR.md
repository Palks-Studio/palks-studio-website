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
├── palks-studio.com/
│    │
│    ├── fr/                                 → Pages du site (FR) / Website pages (EN)
│    ├── en/                                 → Pages du site (FR) / Website pages (EN)
│    │
│    ├── facturx-demo/
│    │   ├── invoice-generator.php           → Point d’entrée de génération de facture (FR) / Invoice generation entry point (EN)
│    │   ├── invoice-template.php            → Modèle HTML de facture (FR) / Invoice HTML template (EN)
│    │   ├── facturx-xml-builder.php         → Construction du XML Factur-X (FR) / Factur-X XML builder (EN)
│    │   ├── inject-facturx-xml.py           → Injection du XML dans le PDF (FR) / XML injection into PDF (EN)
│    │   ├── direct-generation-engine.php    → Pipeline de génération directe (FR) / Direct generation pipeline (EN)
│    │   └── vendor/                         → Dépendances packagées (FR) / Packaged dependencies (EN)
│    │
│    ├── api/
│    │   ├── facturx-generation-engine.php   → Orchestrateur de génération Factur-X (FR) / Factur-X generation orchestrator (EN)
│    │   ├── facturx-xml-builder.php         → Construction du XML Factur-X (FR) / Factur-X XML builder (EN)
│    │   ├── inject-facturx-xml.py           → Injection du XML dans le PDF (FR) / XML injection into PDF (EN)
│    │   ├── invoice-template.php            → Modèle HTML de facture (FR) / Invoice HTML template (EN)
│    │   └── vendor/                         → Dépendances packagées (FR) / Packaged dependencies (EN)
│    │
│    ├── assets/
│    │   ├── css/
│    │   │   └── global-style.css            → Global stylesheet (FR) / Feuille de styles globale (EN)
│    │   └── img/                            → Images et visuels (FR) / Images and visuals (EN)
│    │
│    ├── batch-downloads/
│    │   └── batch-download-access.php       → Point d'accès aux téléchargements batch (FR) / Batch download access endpoint (EN)
│    │
│    ├── store/                              → Fichiers produits numériques (FR) / Digital product files (EN)
│    ├── contract-pdf-generator.php          → Backend génération PDF (FR) / PDF generation backend (EN)
│    ├── batch-upload-engine.php             → Moteur de traitement du formulaire CSV (FR) / CSV upload form processing engine (EN)
│    ├── robots.txt                          → Règles pour moteurs de recherche (FR) / Search engine directives (EN)
│    ├── sitemap.xml                         → Plan du site pour indexation (FR) / Sitemap for indexing (EN)
│    ├── manifest.json                       → Configuration PWA du système (FR) / System PWA configuration (EN)
│    │
│    ├── library/
│    │   ├── contract-client-config-fr.html  → Génération contrat + configuration client (FR)
│    │   ├── contract-client-config-en.html  → Contract generation + client configuration (EN)
│    │   ├── contract-template-fr.html       → Template de contrat (FR)
│    │   ├── contract-template-en.html       → Contract template (EN)
│    │   ├── batch-upload-fr.html            → Formulaire d’envoi CSV client (FR)
│    │   ├── batch-upload-en.html            → Client CSV upload form (EN)
│    │   ├── payment-cancel.html             → Page d’annulation de paiement (FR)/ Payment cancellation page (EN)
│    │   ├── payment-success.html            → Page de paiement validé (FR) / Payment success page (EN)
│    │   └── invoice-template.html           → Template HTML de facture (FR) / Invoice HTML template (EN)
│    │
│    └── stripe/
│        ├── checkout-session.php            → Initialisation d’une session de paiement (FR) / Checkout session initialization (EN)
│        ├── payment-webhook.php             → Traitement post-paiement (FR) / Post-payment fulfillment handler (EN)
│        └── secure-download.php             → Point d’accès sécurisé aux fichiers (FR) / Secure file access endpoint (EN)
│
│
└── palks-studio/
     ├── invoice-counter.json               → Compteur persistant de factures (FR) / Persistent invoice counter (EN)
     ├── invoice-counter-reader.php         → Lecture sécurisée du prochain numéro de facture (FR) / Secure invoice counter reader (EN)
     ├── invoice-html-engine.php            → Génération HTML des factures (FR) / Invoice HTML generation (EN)
     ├── transactional-mailer.php           → Envoi d’e-mails transactionnels (FR) / Transactional email delivery (EN)
     ├── invoice-pdf-engine.php             → Génération PDF via mPDF (FR) / PDF generation via mPDF (EN)
     ├── system-config.php                  → Configuration centralisée des chemins et variables système (FR) / Centralized system paths and variables configuration (EN)
     ├── rate-limit-storage.json            → Stockage des limitations de requêtes IP (FR) / IP request rate limit storage (EN)
     │
     ├── config/
     │   └── download-config.php            → Configuration centrale des téléchargements (FR) / Central download configuration (EN)
     │
     ├── cron/
     │   └── cleanup-expired-data.php       → Nettoyage automatique des journaux et fichiers expirés (FR) / Automatic cleanup of logs and expired files (EN)
     │
     ├── download-tokens/
     │   ├── download-activity.log          → Journal des téléchargements réels (FR) / Download activity log (EN)
     │   └── download-tokens.json           → Stockage des tokens de téléchargement (FR) / Download token storage (EN)
     │
     ├── pdf/
     │   ├── invoices/                      → Factures PDF générées (FR) / Generated PDF invoices (EN)
     │   └── accounting-records/            → Journaux comptables CSV (FR) / Accounting CSV records (EN)
     │
     ├── logs/                              → Journaux système et erreurs (FR) / System logs and errors (EN)
     ├── phpmailer/                         → Bibliothèque d’envoi email (FR) / Email sending library (EN)
     ├── stripe-php/                        → SDK Stripe PHP officiel (FR) / Official Stripe PHP SDK (EN)
     ├── vendor/                            → Dépendances Composer PHP (FR) / Composer PHP dependencies (EN)
     │
     ├── LICENCE.md                         → Conditions d’utilisation et cadre légal (FR)
     ├── LICENSE.md                         → Terms of use and legal framework (EN)
     │
     └── docs/
         ├── SYSTEM-OVERVIEW_FR.md          → Vue d’ensemble du système (FR)
         ├── SYSTEM-OVERVIEW.md             → System overview (EN)
         ├── PROJECT-OVERVIEW_FR.md         → Vue d’ensemble du projet (FR)
         ├── PROJECT-OVERVIEW.md            → Project overview (EN)
         ├── README_FR.md                   → Présentation générale (FR)
         └── README.md                      → General overview (EN)
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

La présence des formulaires côté site ne signifie  
pas une exécution de la facturation côté web.

Toute génération financière est déclenchée par le webhook Stripe  
et traitée côté serveur privé.

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

### Démonstration Factur-X

Une démonstration de génération de facture Factur-X est disponible sur le site.

Cette démonstration est volontairement limitée afin de garantir la stabilité du service et d'éviter tout usage abusif.

Le pipeline de démonstration comprend :  

- rendu du template HTML de facture  
- construction du XML Factur-X (conforme EN16931)  
- injection du XML dans le PDF

Pour une utilisation professionnelle, une intégration complète et conforme peut être mise en place selon les besoins.

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
