# Dossier de choix : Stratégie d'externalisation des services

**Problématique 6 : Externaliser les services et le site vitrine**

**Contexte : IMDEO**

![](https://raw.githubusercontent.com/firetoak/medias/main/bts-sio-images/logo_imdeo.png)

***
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
| **Socle Technique** | Dépendances applicatives    | Le serveur doit supporter le CMS **Joomla 6**, un serveur web **NGINX**, le langage **PHP 8.3** et une base de données **MariaDB 11** (ou supérieur).           |
| **Exploitation**    | Accès Développeur           | Le service développement doit pouvoir **ajouter, modifier et supprimer** des fichiers (HTML/CSS/PHP) et accéder directement à la base de données à tout moment. |
| **Sécurité**        | Authentification            | L'accès aux interfaces de gestion de l'hébergeur doit être sécurisé par une **authentification multifacteur (MFA)**.                                            |
| **Sécurité**        | Protection Réseau           | L'hébergeur doit fournir une protection contre les attaques par déni de service (**DoS et DDoS**).                                                              |
| **Disponibilité**   | Engagement de Service (SLA[^2]) | Le contrat doit garantir un taux de disponibilité de **99% (soit maximum 3,65 jours d'indisponibilité par an) par an**.                                         |
| **Sauvegarde**      | Stratégie de Backup         | La solution doit permettre la mise en place d'une stratégie de sauvegarde respectant la règle du **3-2-1**.                                                     |
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

***
### 3. Cadre juridique et contractuel

Le choix du prestataire repose sur sa capacité à respecter le cahier des charges technique et juridique du groupe. Afin de sécuriser le partenariat, les clauses suivantes devront être contractualisées :

#### 3.1 Tableau - clauses obligatoires dans le contrat

| **Clause**                      | **Objectif et Engagement pour IMDEO**                                                                                                                                |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Définition du périmètre**     | Délimiter strictement les responsabilités de l'hébergeur (infrastructure) et celles d'IMDEO (applicatif site vitrine) pour éviter tout litige en cas d'incident.     |
| **Niveau de service (SLA)**     | Garantir une disponibilité de **99% par an**. Inclut une Garantie de Temps d'Intervention (GTI) de **2h maximum** en cas d'incident critique.                        |
| **Pénalités**                   | Appliquer des pénalités financières dissuasives (ex: 5% du CA annuel d'IMDEO par heure d'indisponibilité hors SLA) pour contraindre le prestataire à l'excellence.   |
| **Conformité RGPD**             | Assurer que le traitement des données est conforme à la réglementation européenne, avec un accès aux serveurs strictement limité au personnel habilité.              |
| **Confidentialité**             | Garantir le secret industriel et la protection des brevets via le chiffrement des données et une clause de non-divulgation stricte pour les employés de l'hébergeur. |
| **Sécurité (Authentification)** | Imposer la mise en place d'une authentification multifacteur (**MFA**[^4]) pour sécuriser tout accès aux interfaces d'administration du serveur.                     |
| **Protection réseau**           | Garantir la continuité de service même en cas de cyberattaque massive grâce à une protection anti-DDoS[^5] native.                                                   |
| **Sauvegardes**                 | Contractualiser la stratégie de backup (règle du 3-2-1) pour prévenir toute perte de données accidentelle ou malveillante.                                           |
| **Réversibilité[^3]**           | Obliger le prestataire à fournir, en fin de contrat, un export complet et exploitable des données et applications pour permettre la migration vers un tiers.         |
| **Résiliation**                 | Définir les modalités de fin de contrat (préavis, motifs légitimes) et prévoir une révision annuelle des conditions pour s'adapter aux évolutions d'IMDEO.           |

#### Lexique

[^2]: **SLA** = **S**ervice **L**evel **A**greement : Détermine le niveau de service attendu entre un client et un prestataire.
[^5]: **DDoS** = **D**istributed **D**enial-**o**f-**S**ervice : Attaque informatique qui inonde le service légitime de requête afin d'empêcher son fonctionnement.
[^4]: **MFA** = **M**ulti-**F**actor **A**uthentication : Couche de protection supplémentaire pour l'authentification. Cela combine plusieurs méthode d'authentification comme un mot de passe et un code one time password via une application. 

---

## 4. Analyse des types d'hébergement.

> *Cette partie sert à montrer les différents types d'hébergement pour le site vitrine et le quel serait le plus pertinent pour notre utilisation*

__Types d'hébergement :__

4.1  __Cloud :__ Flexibilité / Haute disponibilité
4.2  __Mutualisé :__ Idéale pour débuter
4.3 __Joomla :__ Manager
4.4 __Eco-Responsable :__ Éthique et Image de marque
4.5 __Serveur privé virtuel :__ Grande souplesse

###  4.1 Hébergement Cloud

-  __Avantage__ : Très grande disponibilité, facturation à l'usage, fonctionnalité robuste de sauvegarde des données. Tolérance à la panne, si un serveur tombe en panne un autre prendra le relais. Dans le cas d'une augmentation de trafic la puissance GPU et la RAM augmentera automatiquement

- __Désavantage__ : Options potentiellement payantes comme les sauvegardes, certificats SSL ou encore le support, les maintenances et les configurations sont à faire manuellement et à notre charge, Le RGPD n'est pas garantie car le serveur est fragmenté a travers le monde ce qui peut poser problème si ces serveurs sortent de l'UE et les serveurs sont dépendant d'internet ce qui peut impacter la réactiver du site 

### 4.2 Hébergement Mutualisé

- **Avantage** : C'est la solution la plus économique et la plus simple à gérer. La maintenance technique, les mises à jour du serveur et la sécurité sont entièrement gérées par l'hébergeur. L'installation de CMS (comme WordPress) se fait souvent en un clic, ce qui est idéal pour les débutants.

- **Désavantage** : Les ressources (CPU, RAM) sont partagées avec des centaines d'autres sites sur le même serveur. Si un voisin subit un pic de trafic, votre site peut ralentir. La personnalisation est très limitée (impossible de modifier les réglages profonds du serveur) et les performances sont généralement plus faibles.

### 4.3 Hébergement Joomla (Manager / Managé)

- **Avantage** : Spécifiquement optimisé pour le CMS Joomla, ce mode offre un environnement pré-configuré pour maximiser la vitesse et la sécurité du site. Le "Manager" s'occupe souvent des sauvegardes automatiques et des mises à jour du noyau, vous permettant de vous concentrer uniquement sur la création de contenu.

- **Désavantage** : Vous êtes restreint à un seul écosystème ; il est difficile, voire impossible, d'installer d'autres types d'applications sur le même hébergement. Le coût est souvent plus élevé qu'un mutualisé classique à cause du service d'accompagnement et d'optimisation spécifique.


### 4.4 Hébergement Éco-Responsable

- **Avantage** : Améliore significativement l'image de marque de l'entreprise auprès d'une clientèle sensible à l'écologie. Ces hébergeurs utilisent des énergies renouvelables, optimisent le refroidissement des serveurs pour limiter le gaspillage énergétique et prolongent la durée de vie de leur matériel.

- **Désavantage** : Le choix de prestataires est plus restreint sur le marché, ce qui peut limiter certaines options technologiques de pointe. Le coût peut être légèrement supérieur en raison de l'investissement de l'hébergeur dans des infrastructures durables et des compensations carbone.


### 4.5 Serveur Privé Virtuel (VPS)

- **Avantage** : Offre une liberté totale de configuration (accès Root) et des ressources dédiées qui ne sont pas impactées par les autres utilisateurs. C'est le compromis parfait entre le mutualisé et le serveur dédié : vous pouvez installer le système d'exploitation et les logiciels de votre choix avec une grande souplesse d'évolution.

- **Désavantage** : Nécessite des compétences techniques solides en administration système pour la configuration et la sécurisation. Contrairement au Cloud, si le serveur physique qui héberge votre partition virtuelle tombe en panne, votre site devient inaccessible. Vous êtes également responsable de la maintenance logicielle.

---

## 5. Solution proposée.