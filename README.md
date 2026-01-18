<p align="center">
  <img src="docs/images/Palks_Studio.png" alt="Palks Studio">
</p>

> 🇬🇧 English | [🇫🇷 Français](./README_FR.md)

![License](https://img.shields.io/badge/License-LICENSE.md-lightgreen.svg)

# Palks Studio — Static site + digital storefront  

This repository contains the public website of Palks Studio, which combines:  

- a clean, tracking-free static HTML website  
- a lightweight server-side digital storefront  
- an autonomous PDF invoicing system  
- and secure token-based delivery of downloadable files  

The system operates without a CMS, without a database, and without unnecessary SaaS dependencies,  
relying solely on flat files (JSON/CSV) and minimalist PHP scripts.  

The repository includes:  

- the public website (pages, styles, images, content)  
- payment and digital delivery components  
- as well as publicly accessible documentation  
with the aim of clarity, readability, and transparency  

This repository is not a turnkey product, a framework, or a software library.  
It serves as a reference artifact to understand the approach,  
tools, and technical choices carried by Palks Studio.  

---

## About Palks Studio  

Palks Studio designs technical tools, documentation structures,  
and working environments intended to be:  

- readable  
- understandable  
- autonomous  
- maintainable over time  

The emphasis is placed on:  

- functional simplicity  
- control of dependencies  
- transparency of technical choices  
- durability rather than trends  

---

## Project structure

```
/palks-studio_website/
│
├── index.html                               → Landing neutre, choix de langue (FR) / Neutral entry, language selector (EN)
│
├── fr/
│   ├── index.html                           → Accueil principal
│   ├── studio.html                          → Présentation de Palks Studio
│   ├── approche.html                        → Approche et principes de travail
│   ├── ressources.html                      → Ressources techniques
│   ├── static-site.html                     → Socle de site statique
│   ├── chatbot-flask.html                   → Chatbot Flask auto-hébergé
│   ├── framework-documentation.html         → Framework de documentation
│   ├── pack-formatage-vscode.html           → Pack de formatage VS Code
│   ├── liens.html                           → Liens, ressources, produits
│   ├── mentions-legales.html                → Mentions légales (FR) / Legal notice (EN)
│   ├── contact.html                         → Page de contact
│   ├── cgv.html                             → Conditions générales de vente
│   ├── faq.html                             → Foire aux questions
│   └── politique-confidentialite.html       → Politique de confidentialité (FR) / Privacy policy (EN)
│
│
├── en/
│   ├── index.html                           → Home page
│   ├── studio.html                          → Studio overview
│   ├── approach.html                        → Method & principles
│   ├── resources.html                       → Technical resources
│   ├── static-site.html                     → Professional static foundation
│   ├── flask-chatbot.html                   → Self-hosted Flask chatbot
│   ├── documentation-framework.html         → Documentation framework
│   ├── vscode-formatting-pack.html          → VS Code formatting pack
│   ├── links.html                           → Links & resources
│   ├── contact.html                         → Contact page
│   ├── faq.html                             → Frequently Asked Questions
│   └── terms.html                           → Terms and Conditions
│
├── assets/
│   ├── css/
│   │   └── style.css                        → Global stylesheet (FR) / Feuille de styles globale (EN)
│   └── img/                                 → Images et visuels (FR) / Images and visuals (EN)
│
├── robots.txt                               → Règles pour moteurs de recherche (FR) / Search engine directives (EN)
├── sitemap.xml                              → Plan du site pour indexation (FR) / Sitemap for indexing (EN)
│
├── LICENCE.md                               → Conditions d’utilisation et cadre légal (FR)
├── LICENSE.md                               → Terms of use and legal Framework (EN)
│
├── README_FR.md                             → Documentation générale du système (FR)
├── README.md                                → General system documentation (EN)
│
├── downloads_tokens/
│   ├── downloads.log                        → Journal des téléchargements réels (FR) / Download activity log (EN)
│   ├── security.log                         → Journal des accès sécurisés aux fichiers (FR) / Secure download access log (EN)
│   └── tokens.json                          → Stockage des tokens de téléchargement (FR) / Download token storage (EN)
│
├── config/
│   └── download.php                         → Configuration centrale des téléchargements (FR) / Central download configuration (EN)
│
├── library/
│   ├── cancel.html                          → Page d’annulation de paiement (FR)/ Payment cancellation page (EN)
│   ├── success.html                         → Page de paiement validé (FR) / Payment success page (EN)
│   ├── counter.json                         → Compteur persistant de factures (FR) / Persistent invoice counter (EN)
│   ├── get_counter.php                      → Lecture sécurisée du compteur de factures (FR) / Secure invoice counter reader (EN)
│   ├── lib_*.php                            → Incrémentation atomique du numéro de facture (FR) / Secure invoice counter reader (EN)
│   ├── lib_*.php                            → Génération HTML des factures (FR) / Atomic invoice number increment (EN)
│   ├── lib_*.php                            → Envoi e-mails transactionnels (FR) / Transactional email delivery (EN)
│   ├── lib_*.php                            → Génération PDF via DomPDF (FR) / PDF generation via DomPDF (EN)
│   └── template_invoice.html                → Template HTML de facture (FR) / Invoice HTML template (EN)
│
├── products/
│   └── (store files)                        → Fichiers produits numériques (FR) / Digital product files (EN)
│
└── endpoint/
    ├── endpoint_checkout.php                → Initialisation d’une session de paiement (FR) / Checkout session initialization (EN)
    ├── endpoint_payment.php                 → Traitement des événements de paiement (FR) / Payment event handler (EN)
    ├── endpoint_delivery.php                → Traitement post-paiement (FR) / Post-payment fulfillment handler (EN)
    └── endpoint_access.php                  → Point d’accès sécurisé aux fichiers (FR) / Secure file access endpoint (EN)
```


---

## Repository contents

### 1. The Palks Studio website (public version)

The site pages present:  

- the studio and its approach  
- the resources offered  
- the conceptual foundations  
- the technical tools developed  
- legal and informational pages  
- as well as access to the digital storefront  

The site is intentionally sober, static, and readable in the browser.  
It serves both as a showcase of the Palks Studio approach and as the entry point  
for the sale and distribution of digital products.

On the server side, the site relies on a minimal pipeline:  
`Stripe → Webhook → PDF invoice → secure token → download`,  
without a CMS and without a database.

---

### 2. Resources and digital distribution

Some resources are provided as documents, archives, or downloadable files,  
particularly when the content includes:  

- multiple files  
- complete structures  
- examples or educational materials  
- reusable tools or templates  

These elements are grouped in dedicated folders to preserve  
repository clarity and deliverable traceability.

File distribution is handled via a secure system based on temporary,  
single-use links, logged on the server side.

---

## What this repository is

- A public static site + lightweight digital storefront  
- A technical and documentary showcase  
- A public reference point  
- A support for understanding  
- A demonstration of structure and method  
- A concrete example of a sober architecture without CMS or database.

---

## What this repository is not

- An e-commerce framework  
- A SaaS platform  
- A generic turnkey product  
- A software library  
- A support or contractual update space  

Keys, secrets, and certain production paths are not exposed here.

---

## Transparency and approach

Palks Studio chooses to:  

- seriously document its projects  
- explain choices and limits  
- avoid vague promises  
- not hide work behind marketing  
- prioritize readability and traceability over complexity  

The code, structures, and documentation are designed to be understood  
before any decision of use or purchase.

This repository fully participates in this transparency approach.  

---

## Languages

- French (reference)  
- English (separate README)

---

© Palks Studio — see LICENSE.md  
- https://palks-studio.com
