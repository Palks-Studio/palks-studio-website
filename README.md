<p align="center">
  <img src="docs/images/palks_studio_en.png"
       alt="Palks Studio homepage — static-first development and automation services overview"
       width="1200">
</p>

> 🇬🇧 English | [🇫🇷 Français](./README_FR.md)

![License](https://img.shields.io/badge/License-LICENSE.md-lightgreen.svg)
![Static Website](https://img.shields.io/badge/Type-Static%20Website-151b1c?style=flat)
![Documentation](https://img.shields.io/badge/Focus-Documentation-0095b1?style=flat)
![Bilingual](https://img.shields.io/badge/Lang-FR%20%2F%20EN-0a5645?style=flat)

<p align="center">
  <a href="https://palks-studio.com">
    <img src="https://img.shields.io/badge/Palks%20Studio-Website-0095b1?style=for-the-badge" />
  </a>
</p>

# Palks Studio — Static site + digital storefront  

> This repository is a technical presentation and documentation repository.  
> It does not contain downloadable source code or production files.

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
/palks-studio-website/
│
├── fr/                                       → Pages du site (FR)
├── en/                                       → Pages du site (EN)
│
├── assets/
│   ├── css/
│   │   └── style.css                         → Global stylesheet (FR) / Feuille de styles globale (EN)
│   └── img/                                  → Images et visuels (FR) / Images and visuals (EN)
│
├── robots.txt                                → Règles pour moteurs de recherche (FR) / Search engine directives (EN)
├── sitemap.xml                               → Plan du site pour indexation (FR) / Sitemap for indexing (EN)
│
├── LICENCE.md                                → Conditions d’utilisation et cadre légal (FR)
├── LICENSE.md                                → Terms of use and legal Framework (EN)
│
├── core/                                     → Backend génération PDF (FR) / PDF generation backend (EN)
├── endpoint/                                 → Moteur de traitement du formulaire CSV (FR) / CSV upload form processing engine (EN)
│
├── storage/
│   └── protected/                            → Stockage sécurisé interne (FR) / Secure internal storage (EN)
│
├── config/
│   └── download/                             → Configuration interne des téléchargements (FR) / Internal download configuration (EN)
│
├── library/
│   ├── contracts/                            → Génération et templates de contrats (FR) / Contract generation and templates (EN)
│   ├── batch/                                → Interface d’import et traitement CSV (FR) / CSV import and processing interface (EN)
│   ├── payments/                             → Pages de gestion des paiements (FR) / Payment handling pages (EN)
│   ├── counters/                             → Gestion de la numérotation (FR) / Numbering management (EN)
│   ├── core/                                 → Fonctions internes (génération, email, PDF) (FR) / Internal functions (generation, email, PDF) (EN)
│   └── templates/                            → Modèles de documents (FR) / Document templates (EN)
│
├── docs/
│   ├── VUE_D_ENSEMBLE.md                     → Vue d’ensemble du système (FR)
│   ├── OVERVIEW.md                           → System Overview (EN)
│   ├── PROJECT-OVERVIEW_FR.md                → Vue d’ensemble du projet (FR)
│   ├── PROJECT-OVERVIEW.md                   → Project Overview (EN)
│   ├── README_FR.md                          → Présentation générale (FR)
│   └── README.md                             → General Overview (EN)
│
├── store/                                    → Fichiers produits numériques (FR) / Digital product files (EN)
│
└── endpoint/
    ├── endpoint_a.php                        → Initialisation d’une session de paiement (FR) / Checkout session initialization (EN)
    ├── endpoint_b.php                        → Traitement des événements de paiement (FR) / Payment event handler (EN)
    ├── endpoint_c.php                        → Traitement post-paiement (FR) / Post-payment fulfillment handler (EN)
    └── endpoint_d.php                        → Point d’accès sécurisé aux fichiers (FR) / Secure file access endpoint (EN)
```


---

## Architecture Summary

The system follows a deliberately minimal architecture:  

- Static frontend (HTML/CSS)  
- PHP backend endpoints  
- Flat file storage (JSON / CSV)  
- Stripe as payment processor  
- No database layer

Design goals:  

- deterministic behavior  
- traceable operations  
- minimal dependencies  
- long-term maintainability

### Layered architecture — reminder

The system clearly separates:  

- the public web facade (`palks-studio.com`)  
- controlled ingestion points (contract, CSV upload)  
- the private billing engine (`automation_finance/`)

The presence of web forms does not imply  
that billing execution occurs on the web layer.

All financial generation remains strictly  
driven by the CLI engine.

---

## The Palks Studio website (public version)

The site pages present:  

- the studio and its approach  
- the available resources  
- the conceptual foundations  
- the technical tools developed  
- the technical notes and engineering reflections  
- the legal and informational pages  
- as well as a free bilingual PDF quote generator that runs entirely in the browser.

This tool operates fully client-side (JavaScript + jsPDF) and does not transmit  
any data to a server. It allows users to quickly create professional quotes  
with multiple service lines, automatic subtotal / VAT / total calculations,  
and direct PDF export.

The generator is completely independent from the billing pipeline  
(Stripe → Webhook → Invoice → Token → Download) and does not create  
any transaction or archive on the server side.

### Resources and digital distribution

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
- A concrete example of a sober architecture without CMS or database  
- as well as a free PDF quote generator, bilingual FR/EN, running entirely in the browser

---

## What this repository is not

- An e-commerce framework  
- A SaaS platform  
- A generic turnkey product  
- A software library  
- A support or contractual update space  

Keys, secrets, and certain production paths are not exposed here.

---

## Design Principles

Palks Studio follows a small set of consistent principles:  

- simplicity over abstraction  
- transparency over automation  
- autonomy over dependency  
- readability over optimization  
- long-term stability over trends

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

© Palks Studio — see LICENSE.md  
- https://palks-studio.com
