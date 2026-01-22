# Comparatif Technique & Financier : VPS vs Public Cloud (Écosystème OVHcloud)

**Objectif :** Choisir l'infrastructure la plus pertinente pour le site institutionnel d'iMDEO.
**Contrainte DSI :** Haute disponibilité, crédibilité technique (ESN), souveraineté des données.

---

## 1. Option A : Le Serveur Privé Virtuel (VPS)
**L'offre : OVH VPS Comfort**

### Les Fonctionnalités
* **Ressources :** Garanties mais non flexibles à chaud (redémarrage requis pour upgrader).
* **Administration :** Totale (Root). Gestion de A à Z.
* **Réseau :** IP publique incluse. Bande passante 1 Gbps.
* **Limites :** Pas de réseau privé (vRack) inclus par défaut sur cette gamme, isolation moins forte qu'en Cloud.

### Le Coût Mensuel (HT)
| Poste de dépense | Détail technique | Prix (HT/mois) |
| :--- | :--- | :--- |
| **Serveur VPS** | **4 vCores**, **8 Go RAM**, 160 Go NVMe | 23,50 € |
| **Backup Auto** | Option (Snapshot J-1) | ~3,00 € |
| **Trafic Sortant** | Illimité / Inclus | 0,00 € |
| **TOTAL** | **Coût fixe** | **~26,50 € / mois** |

---

## 2. Option B : Le Public Cloud (Instance)
**L'offre : OVH Public Cloud (Instance B2-7 ou équivalent)**

### Les Fonctionnalités
* **Orchestration :** Pilotable via API / Terraform[^1] (Infrastructure as Code).
* **Haute Dispo :** Stockage Ceph[^2] triplé (données répliquées 3 fois).
* **Réseau Pro :** Compatible **vRack** (Réseau privé isolé entre serveurs) et **Floating IP** (bascule d'IP immédiate en cas de panne).
* **Flexibilité :** Resize à chaud (selon OS) et facturation à l'heure possible.

### Le Coût Mensuel (HT)
*Note : Pour un tarif proche du VPS Comfort, nous sélectionnons l'instance "General Purpose" B2-7.*

| Poste de dépense | Détail technique | Prix (HT/mois) |
| :--- | :--- | :--- |
| **Instance (B2-7)** | **2 vCores**, **7 Go RAM**, 50 Go SSD (Moins puissant que le VPS) | ~24,20 € |
| **Disque add.** | Ajout 100 Go Block Storage (pour égaler les 160Go du VPS) | 4,00 € |
| **Snapshot** | Sauvegarde de l'instance (estimatif 50Go) | ~2,50 € |
| **Trafic Sortant** | Illimité / Inclus (Avantage OVH vs AWS) | 0,00 € |
| **TOTAL** | **Coût modulable** | **~30,70 € / mois** |

---

## 3. Analyse des Écarts & Décision pour le DSI

### Le constat technique
Il y a un piège classique ici : **à prix égal, le VPS est deux fois plus puissant en CPU que le Public Cloud.**
* **VPS Comfort (26,50€) :** 4 vCores, 160 Go Disque.
* **Public Cloud B2-7 (30,70€) :** 2 vCores, 50 Go Disque de base.
*(Pour avoir 4 vCores en Public Cloud, il faudrait passer à l'instance B2-15 à ~68€/mois).*

### Argumentaire de décision

Bien que le VPS offre plus de puissance brute pour moins cher, je recommande tout de même **l'Option B : Public Cloud (Instance B2-7)** pour notre site vitrine iMDEO.

**Pourquoi sacrifier de la puissance pour payer plus cher ?**
1.  **Architecture "ESN" (Dogfooding) :** Nos consultants vendent de l'infrastructure moderne. Notre site doit utiliser les technologies que nous préconisons (OpenStack, vRack, Floating IP). Un simple VPS fait "amateur" pour notre image.
2.  **Sécurité & Isolation :** Le Public Cloud nous permet d'utiliser le **vRack** (réseau privé) pour isoler nos futures bases de données, ce que le VPS Comfort ne permet pas nativement.
3.  **Continuité de service :** En cas de crash critique du serveur, grâce à la **Floating IP** du Public Cloud, nous pouvons remonter une sauvegarde sur une nouvelle instance et y pointer l'IP en quelques secondes via script. Sur un VPS, nous sommes dépendants du temps de réparation physique de l'hôte par OVH.

**Verdict :** Nous choisissons la **flexibilité et la sécurité du Public Cloud (30€/mois)** plutôt que la puissance brute du VPS, car un site vitrine a besoin de haute disponibilité plus que de puissance de calcul.

#### Lexique

[^1]: **Terraform** :Outil d'Infrastructure as Code (IaC) permettant d'automatiser la création et la gestion d'infrastructures cloud via des fichiers de configuration déclaratifs.
[^2]: **Ceph** : Solution de stockage distribué unifiée et évolutive, gérant simultanément le stockage en mode objet, bloc et fichier sur une même plateforme.