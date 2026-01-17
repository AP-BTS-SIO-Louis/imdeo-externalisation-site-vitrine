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
| **Disponibilité**   | Engagement de Service (SLA) | Le contrat doit garantir un taux de disponibilité de **99% (soit maximum 3,65 jours d'indisponibilité par an) par an**.                                         |
| **Sauvegarde**      | Stratégie de Backup         | La solution doit permettre la mise en place d'une stratégie de sauvegarde respectant la règle du **3-2-1**.                                                     |
| **Juridique**       | Conformité des données      | L'hébergement doit être strictement conforme au **RGPD** car le site traite des données personnelles.                                                           |
| **Juridique**       | Fin de contrat              | Une clause de **réversibilité** est exigée pour récupérer les données et l'application en cas de changement de prestataire.                                     |
