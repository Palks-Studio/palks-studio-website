<p align="center">
  <img src="docs/images/Palks_Studio.png" alt="Palks Studio" width="1200">
</p>

> 🇫🇷 Français | [🇬🇧 English](./README.md)

![Backend](https://img.shields.io/badge/Backend-Architecture-0A66C2?style=flat)
![API](https://img.shields.io/badge/API-Integration-0095b1?style=flat)
![Electronic Invoicing](https://img.shields.io/badge/Electronic-Invoicing-27ae60?style=flat)
![Automation](https://img.shields.io/badge/Automation-Workflows-27ae60?style=flat)
![Factur-X](https://img.shields.io/badge/Factur--X-EN16931-orange?style=flat)
![PHP](https://img.shields.io/badge/PHP-8A2BE2?style=flat)
![Remote](https://img.shields.io/badge/Remote-Worldwide-success?style=flat)
![FR / EN](https://img.shields.io/badge/Languages-FR%20%7C%20EN-blue?style=flat)
[![Malt](https://img.shields.io/badge/Malt-Profile-FF4F8B?style=flat)](https://www.malt.fr/profile/anthonyleignel)
[![YouTube](https://img.shields.io/badge/YouTube-@Palks__Studio-FF0000?style=flat&logo=youtube&logoColor=white)](https://www.youtube.com/@Palks_Studio)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-@Palks__Studio-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/palks-studio/)

<p align="center">
  <a href="https://palks-studio.com">
    <img src="https://img.shields.io/badge/Palks%20Studio-Website-0095b1?style=for-the-badge" />
  </a>
</p>

# Palks Studio

> Ce dépôt constitue une présentation.  
> Il ne contient pas de code source téléchargeable ni de fichiers de production.

## Développement backend et systèmes métier

Conception et développement de systèmes backend, d'applications métier et d'automatisations adaptés à des besoins concrets.

Palks Studio accompagne les entreprises dans la création de nouveaux outils, l'intégration d'API, l'automatisation de processus métier et l'évolution de systèmes backend existants, avec une approche privilégiant des architectures maintenables et des dépendances maîtrisées.

---

## À propos

Palks Studio est un studio indépendant spécialisé dans le développement de systèmes backend, de logiciels métier et d'automatisations techniques.

Chaque projet est conçu selon les mêmes principes : simplicité, maintenabilité, fiabilité sur le long terme et maîtrise des données ainsi que de l'infrastructure.

---

## Expertise principale

- Développement de systèmes backend  
- Applications métier  
- Conception et intégration d’API  
- Automatisation de workflows  
- Facturation électronique (Factur-X / EN16931)  
- Génération de documents (PDF, Factur-X)  
- Intégration de paiements et gestion des événements  
- Sécurité applicative et serveur

### Technologies

PHP • Python • JavaScript

### Collaboration

🌍 Remote • 🇫🇷 Français • 🇬🇧 English

---

## Exemples de réalisations

Les projets présentés ci-dessous illustrent différents systèmes conçus et développés par Palks Studio : outils métier, systèmes backend, automatisations, traitement de données et facturation électronique.

### Billing System

Système de facturation électronique complet, déployé directement sur l’infrastructure du client :

- devis → signature → facture → acquittement  
- génération de factures conformes Factur-X / EN16931  
- génération PDF (client + serveur)  
- archivage structuré  
- numérotation sécurisée et traçabilité  
- envoi automatique des emails  
- interface bilingue FR / EN

Cette réalisation illustre la conception d'un système métier complet, reliant logique commerciale, génération documentaire, automatisation, traçabilité et gestion des données au sein d'une architecture autonome.

### Candidate System

Système de recrutement par scoring automatique, déployé directement sur l'infrastructure du client :  

- formulaire candidat → scoring → dashboard → export  
- scoring déterministe à 3 niveaux : section, question, réponse  
- malus configurables par campagne  
- gestion multi-campagnes sans intervention sur le code  
- stockage JSON sans base de données  
- emails automatiques (accusé de réception + clôture)  
- interface bilingue FR / EN

Conçu pour remplacer le tri manuel des candidatures tout en conservant un contrôle total sur les critères, les données et l'infrastructure.

[Voir le système](https://palks-studio.com/fr/recrutement-sans-saas)

### Data Collection System

Système de collecte de données autonome fonctionnant localement ou sur infrastructure dédiée :

- recherches multi-sources (DuckDuckGo, Bing, Qwant)  
- extraction de sites web, emails et numéros de téléphone  
- nettoyage, normalisation et validation des données  
- suppression automatique des doublons  
- suivi des prospects déjà contactés  
- exports CSV et JSON  
- interface web intégrée  
- fonctionnement local avec dépendances externes limitées

Conçu pour centraliser et exploiter des données structurées tout en conservant un contrôle total sur l'infrastructure et les données collectées.

Livraison possible :

- archive ZIP avec documentation d'installation  
- déploiement serveur sur demande

[Voir le système](https://palks-studio.com/fr/collecte-de-donnees)

---

## Autres systèmes backend sur mesure

- outils internes et workflows métier  
- automatisation de traitements et tâches récurrentes  
- génération et traitement de documents PDF  
- systèmes documentaires et archivage structuré  
- intégration de paiements et traitements sécurisés  
- systèmes backend sans base de données  
- interfaces internes et traitements batch  
- déploiement autonome sur l'infrastructure du client

### Automation Finance

Système de facturation batch PDF :

- génération automatique depuis CSV  
- production de factures structurées  
- archivage et traçabilité complète  
- livraison sécurisée par token  
- traitement en lot reproductible

Utilisé pour automatiser des volumes de facturation récurrents.

[Voir le dépôt](https://github.com/Palks-Studio/automation-system)

---

## Outils complémentaires

**Moteur d’acquittement PDF**  
Outil permettant de traiter des factures en lot, intégré dans les workflows Automation Finance.

- import ZIP  
- détection automatique des PDF  
- génération de factures acquittées  
- export individuel ou batch

[Voir le dépôt](https://github.com/Palks-Studio/invoice-stamper)

### Autres outils

- générateur de devis (100 % navigateur)  
- démonstrateur de facturation électronique Factur-X  
- socles de sites statiques HTML/CSS  
- chatbots locaux (Flask)  
- frameworks de documentation  
- configurations de développement

[Voir les ressources](https://palks-studio.com/fr/ressources)

Ces projets illustrent différentes approches mises en œuvre par Palks Studio : développement backend, automatisation, traitement de données, génération documentaire, sécurité, intégration et déploiement.

Les systèmes présentés constituent des réalisations techniques et ne correspondent pas nécessairement aux services actuellement proposés par le studio.

[![Contact](https://img.shields.io/badge/Contact-0095b1?style=flat)](https://palks-studio.com/fr/contact)

---

## Pour qui

- freelances et indépendants  
- artisans et petites structures  
- PME et équipes métier  
- entreprises souhaitant reprendre le contrôle de leurs systèmes métier  
- projets techniques nécessitant des outils simples, fiables et maintenables

---

## Approche

- architectures adaptées au besoin  
- dépendances maîtrisées  
- simplicité avant complexité  
- systèmes maintenables  
- maîtrise des données et de l'infrastructure

Chaque système présenté ici repose sur les mêmes principes : simplicité, maintenabilité, fiabilité et maîtrise des dépendances.

L'objectif n'est pas d'ajouter de la complexité, mais de construire des solutions adaptées, durables et faciles à faire évoluer.

Lorsque cela est pertinent, les systèmes sont conçus pour fonctionner directement sur l'infrastructure du client afin de limiter les dépendances externes tout en conservant la maîtrise des données et de l'environnement.

- https://palks-studio.com
