## 2. Pertinence de l'externalisation de l'hébergement de services

> **Définition :**
> L'**externalisation** consiste à confier à un prestataire externe la responsabilité d'une activité ou d'une tâche, plutôt que de la gérer en interne.
### 2.1 Impact pour IMDEO

L'externalisation permettrait à IMDEO de se concentrer sur la mise en place de nouvelles fonctionnalités au lieu de devoir gérer les équipements physiques (serveurs, climatisation, électricité). De plus, l'entreprise pourrait bénéficier de services comme le CDN[^1], permettant de réduire le temps de chargement du site vitrine, ainsi que d'autres services.

Cependant, cette externalisation impose de respecter les contraintes juridiques qui incombent à IMDEO (voir chapitre 3).
### 2.2 Avantages et inconvénients de l'externalisation

L'externalisation possède des avantages et des inconvénients pour les entreprises. Il convient de les analyser avant la prise de décision pour déterminer s'il est réellement bénéfique pour l'entreprise d'externaliser son hébergement. Voici un tableau récapitulatif :

| **Avantages (Opportunités)**                                                                                                                                                                                                                                                                                                                                                                                                                  | **Inconvénients (Risques)**                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| - Très haute disponibilité sur une ou plusieurs zones de disponibilité.<br><br>- Baisse de latence pour l'utilisateur grâce au CDN[^1].<br><br>- Plus de gestion des composants réseaux et serveurs.<br><br>- Paiement à l'utilisation (OPEX[^7]), plus besoin d'investissement coûteux (CAPEX[^8]).<br><br>- Infrastructure scalable[^9] très facilement.<br><br>- Déchargement du risque de cybersécurité (maintenance pare-feu, routeurs). | - Perte de contrôle sur le matériel.<br><br>- Dépendance vis-à-vis de l'hébergeur (Vendor Lock-in[^6], voir exemple 1).<br><br>- Risque de surfacturation en cas de pic de connexion.<br><br>- Confidentialité des données incertaine en cas d'hébergement chez des prestataires étrangers (ex: AWS et le Cloud Act).<br><br>- Perte de compétences en interne entrainant un risque de dette technique[^10]. |

**Exemple 1 :**

De nombreuses entreprises se retrouvent dépendantes d'AWS pour la gestion de leurs données en utilisant le service DynamoDB. C'est une base de données non relationnelle capable de contenir des milliards d'éléments avec une grande vitesse de lecture et d'écriture. Cependant, sur le marché actuel, aucune solution concurrente identique n'est disponible et la migration de DynamoDB vers un autre prestataire est très complexe.

---
#### Lexique

[^1]: **CDN** = **C**ontent **D**elivery **N**etwork : Réseau de serveurs distribués géographiquement pour diffuser du contenu rapidement.
[^3]: **Clause réversibilité** : disposition contractuelle qui organise la restitution ou le transfert des données, logiciels ou infrastructures critiques en cas de fin de contrat, de faillite du prestataire ou de tout autre événement mettant fin à la collaboration.
[^6]: **Vendor Lock-in** : dépendance d'un client à un produit ou à une technologie.
[^7]: **OPEX** : charge d'exploitation (Ex : cartouche d'encre pour l'imprimante).
[^8]: **CAPEX** : dépenses d'investissement (Ex. imprimante, serveurs).
[^9]: **Scalabilité** : capacité d'un système à gérer un accroissement de la demande sans perdre en efficacité ou en performance.
[^10]: **Dette technique** : concept utilisé en informatique pour décrire le coût à long terme de solutions rapides ou temporaires adoptées lors du développement logiciel.