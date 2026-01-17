# Dossier de choix : Stratégie d'externalisation des services

**Problématique 6 : Externaliser les services et le site vitrine**

**Contexte : IMDEO**

![](https://raw.githubusercontent.com/firetoak/medias/main/bts-sio-images/logo_imdeo.png)

---
## Informations

- **Auteurs :** Louis Biseray, Louis MEDO
- **Date de création :** 16/01/2026
- **Validation technique :** non validé

---
## Sommaire

1. Expression des besoins
2. Pertinence de l'externalisation
3. Cadre juridique et contractuel
4. Analyse des types d'hébergement
5. Solution proposée

---
## 1. Expression des besoins

> L'expression des besoins formalise les attentes fonctionnelles tout en intégrant les contraintes techniques, humaines et juridiques de l'organisation.

### 1.1 Tableau - expression des besoins

Le tableau ci-dessous recense l'ensemble des exigences extraites du cahier des charges fourni par l'entreprise pour l'externalisation du site vitrine.

| **Catégorie**       | **Exigence / Besoin**       | **Détails et Contraintes du cahier des charges**                                                                                                                |
| ------------------- | --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Socle Technique** | Dépendances applicatives    | Le serveur doit supporter le CMS **Joomla 6**, un serveur web **NGINX**, le langage **PHP 8.3** et une base de données **MariaDB 11** (ou supérieur)1.          |
| **Exploitation**    | Accès Développeur           | Le service développement doit pouvoir **ajouter, modifier et supprimer** des fichiers (HTML/CSS/PHP) et accéder directement à la base de données à tout moment. |
| **Sécurité**        | Authentification            | L'accès aux interfaces de gestion de l'hébergeur doit être sécurisé par une **authentification multifacteur (MFA)**.                                            |
| **Sécurité**        | Protection Réseau           | L'hébergeur doit fournir une protection contre les attaques par déni de service (**DoS et DDoS**).                                                              |
| **Disponibilité**   | Engagement de Service (SLA) | Le contrat doit garantir un taux de disponibilité de **99% (3 jours) par an**.                                                                                       |
| **Sauvegarde**      | Stratégie de Backup         | La solution doit permettre la mise en place d'une stratégie de sauvegarde respectant la règle du **3-2-1**6.                                                    |
| **Juridique**       | Conformité des données      | L'hébergement doit être strictement conforme au **RGPD** car le site traite des données personnelles.                                                           |
| **Juridique**       | Fin de contrat              | Une clause de **réversibilité** est exigée pour récupérer les données et l'application en cas de changement de prestataire.                                     |

---
## 2. Pertinence de l'externalisation de l'hébergement de services

> **Définition :**
> L'**externalisation** consiste à confier à un prestataire externe la responsabilité d'une activité ou d'une tâche, plutôt que de la gérer en interne.
### 2.1 Impact pour IMDEO

L'externalisation permettrait à IMDEO de se concentrer sur la mise en place de nouvelles fonctionnalités au lieu de devoir gérer les équipements physiques (serveurs, climatisation, électricité). De plus, l'entreprise pourrait bénéficier de services comme le CDN[^1], permettant de réduire le temps de chargement du site vitrine, ainsi que d'autres services.

Cependant, cette externalisation impose de respecter les contraintes juridiques qui incombent à IMDEO (voir chapitre 3).
### 2.2 Avantages et inconvénients de l'externalisation

L'externalisation possède des avantages et des inconvénients pour les entreprises. Il convient de les analyser avant la prise de décision pour déterminer s'il est réellement bénéfique pour l'entreprise d'externaliser son hébergement. Voici un tableau récapitulatif :

| **Avantages (Opportunités)**                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | **Inconvénients (Risques)**                                                                                                                                                                                                                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| - Très haute disponibilité sur une ou plusieurs zones de disponibilité.<br><br>  <br><br>- Baisse de latence pour l'utilisateur grâce au CDN[^1].<br><br>  <br><br>- Plus de gestion des composants réseaux et serveurs.<br><br>  <br><br>- Paiement à l'utilisation (OPEX[^7]), plus besoin d'investissement coûteux (CAPEX[^8]).<br><br>  <br><br>- Infrastructure scalable[^9] très facilement.<br><br>  <br><br>- Déchargement du risque de cybersécurité (maintenance pare-feu, routeurs). | - Perte de contrôle sur le matériel.<br><br>  <br><br>- Dépendance vis-à-vis de l'hébergeur (Vendor Lock-in[^6], voir exemple 1).<br><br>  <br><br>- Risque de surfacturation en cas de pic de connexion.<br><br>  <br><br>- Confidentialité des données incertaine en cas d'hébergement chez des prestataires étrangers (ex: AWS et le Cloud Act). |

**Exemple 1 :**

De nombreuses entreprises se retrouvent dépendantes d'AWS pour la gestion de leurs données en utilisant le service DynamoDB. C'est une base de données non relationnelle capable de contenir des milliards d'éléments avec une grande vitesse de lecture et d'écriture. Cependant, sur le marché actuel, aucune solution concurrente identique n'est disponible et la migration de DynamoDB vers un autre prestataire est très complexe.

#### Lexique

[^1]: **CDN** = **C**ontent **D**elivery **N**etwork : Réseau de serveurs distribués géographiquement pour diffuser du contenu rapidement.
[^3]: **Clause réversibilité** : disposition contractuelle qui organise la restitution ou le transfert des données, logiciels ou infrastructures critiques en cas de fin de contrat, de faillite du prestataire ou de tout autre événement mettant fin à la collaboration.
[^6]: **Vendor Lock-in** : dépendance d'un client à un produit ou à une technologie.
[^7]: **OPEX** : charge d'exploitation (Ex : cartouche d'encre pour l'imprimante).
[^8]: **CAPEX** : dépenses d'investissement (Ex. imprimante, serveurs).
[^9]: **Scalabilité** : capacité d'un système à gérer un accroissement de la demande sans perdre en efficacité ou en performance.

---
### 3. Cadre juridique et contractuel

Le prestataire en charge de l'hébergement doit être en capacité de répondre aux besoins d'IMDEO définis dans le cahier des charges.

| **Contrainte / Clause**               | **Objectif pour IMDEO**                                                                                                                    |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Engagement de Service (SLA[^2])**   | Garantir une disponibilité de 99% par an, assurant ainsi la continuité de service pour les clients.                                        |
| **Clause de réversibilité[^3]**       | Permettre à l'entreprise de récupérer l'intégralité des applications et des données en cas de changement de prestataire ou de résiliation. |
| **Conformité RGPD**                   | Garantir la confidentialité des données personnelles avec un accès strictement limité au personnel autorisé.                               |
| **Sécurité (Authentification)**       | Imposer une authentification multifacteur (MFA[^4]) pour sécuriser l'accès aux interfaces d'administration.                                |
| **Protection réseau (Anti-DDoS[^5])** | Assurer que le site reste accessible même en cas d'attaques par déni de service.                                                           |
#### Lexique

[^2]: **SLA** = **S**ervice **L**evel **A**greement : Détermine le niveau de service attendu entre un client et un prestataire.
[^5]: **DDoS** = **D**istributed **D**enial-**o**f-**S**ervice : Attaque informatique qui inonde le service légitime de requête afin d'empêcher son fonctionnement.
[^4]: **MFA** = **M**ulti-**F**actor **A**uthentication : Couche de protection supplémentaire pour l'authentification. Cela combine plusieurs méthode d'authentification comme un mot de passe et un code one time password via une application. 