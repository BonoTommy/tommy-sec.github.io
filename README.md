# 🌐 Portfolio – Administration Système & Cybersécurité

Bienvenue sur mon portfolio professionnel.  
Je m'appelle **Tommy**, passionné par l'administration système, la cybersécurité et la virtualisation.

Ce portfolio présente mes projets techniques, dont un laboratoire Active Directory complet configuré dans un environnement sécurisé.

---

## 🛠️ Projet : Laboratoire Active Directory (VirtualBox + Windows Server)

### 🎯 Objectif
Mettre en place un environnement Active Directory complet dans VirtualBox, en respectant les bonnes pratiques de sécurité.

---

## 🧱 Architecture du laboratoire

**DC01 – Windows Server 2022**
- Rôle : Contrôleur de domaine  
- IP : 192.168.56.10  
- Réseau : Host‑Only  
- Pare‑feu : Profil Public (activé)

**PC‑Client – Windows 11**
- Rôle : Client du domaine  
- IP : 192.168.56.20  
- Réseau : Host‑Only

---

## 🌐 Réseau & VirtualBox

### ⚙️ Configuration du réseau Host‑Only
![Réseau Host‑Only VirtualBox](images/reseau_virtualbox/host-only.png)

---

### 🧩 Paramètres IP des machines

**DC01 – Windows Server 2022**  
![Paramètres réseau DC01](images/reseau_virtualbox/parametre_reseau_DC01.png)

**PC‑Client – Windows 11**  
![Paramètres réseau PC‑Client](images/reseau_virtualbox/parametre_reseau_pc-client.png)

---

### 🔍 Vérification de la connectivité
![ARP DC01](images/reseau_virtualbox/arp_DC01.png)
![Ping DC01](images/reseau_virtualbox/ping_DC01.png)
![Ping PC‑Client](images/reseau_virtualbox/ping_pc-client.png)

---

## 🔐 Sécurité – Pare‑feu Windows

### 🧱 DC01 – Windows Server 2022
![Pare‑feu DC01 – Profil Public](images/pare-feu_windows/public_DC01.png)
![Règle ICMPv4‑In DC01](images/pare-feu_windows/icmpv4-in_DC01.png)

---

### 💻 PC‑Client – Windows 11
![Pare‑feu PC‑Client](images/pare-feu_windows/pare-feu_pc.png)
![Règle ICMPv4‑In PC‑Client](images/pare-feu_windows/icmpv4-in_pc.png)

---

## 🧱 Installation du rôle Active Directory Domain Services (AD DS)

### ⚙️ Ajout du rôle AD DS
![Ajout du rôle AD DS](images/ad_ds/ad_ds_installation.png)
![Rôles et fonctionnalités cochés](images/ad_ds/roles_fonctionnalites.png)
![Installation en cours](images/ad_ds/installation.png)

---

### 🧩 Promotion du serveur en contrôleur de domaine
![Promotion du serveur](images/ad_ds/promouvoir.png)
![Nom du domaine](images/ad_ds/nom_domaine.png)
![Configuration du contrôleur](images/ad_ds/configuration_controleur.png)
![Validation avant installation](images/ad_ds/ad_ds-checked.png)

---

### 🧠 Vérification post‑installation
![Contrôleur de domaine](images/ad_ds/controleur_domaine.png)
![Console ADUC](images/ad_ds/console_aduc.png)

---

## 👥 Création des utilisateurs et groupes dans ADUC

### 🧭 Ouverture de la console ADUC
![Console ADUC](images/aduc/console_aduc.png)

---

### 🗂️ Création d’une unité d’organisation
![Création de l’OU](images/aduc/unite_organisation.png)
![Arborescence du domaine](images/aduc/arborescence.png)

---

### 👤 Création des utilisateurs
![Création d’un utilisateur](images/aduc/creation_utilisateur.png)
![Liste des employés](images/aduc/3_employes.png)

---

### 🧩 Création des groupes
![Création d’un groupe](images/aduc/creation_groupe.png)
![Liste des groupes](images/aduc/2_groupes.png)

---

### 🔗 Ajout des utilisateurs aux groupes
![Ajout d’un utilisateur à un groupe](images/aduc/ajout_utilisateur_groupe.png)
![Membres du groupe](images/aduc/membres.png)

---

## 🌐 Configuration DNS

### ⚙️ Création de la zone directe
![Zone directe DNS](images/dns/forward_lookup_zones.png)
![Type de zone DNS](images/dns/zone_type.png)
![Mode de réplication DNS](images/dns/mode_replication_dns.png)

---

### 🧩 Création de la zone inversée
![Assistant New Zone Wizard](images/dns/new_zone_wizard.png)
![Network ID](images/dns/network_id.png)
![Zone inversée créée](images/dns/56_168_192_in-addr_arpa.png)

---

### 🔧 Configuration de l’enregistrement PTR
![Configuration PTR](images/dns/configuration_ptr.png)
![Zone inversée avec PTR](images/dns/zone_inverse_ptr_visible.png)

---

### 🧠 Vérification des enregistrements DNS
![Vérification DNS](images/dns/verification_enregistrements_dns.png)

---

### 🧪 Tests de résolution DNS
![Résolution directe](images/dns/ns_lookup_directe.png)
![Résolution inversée fonctionnelle](images/dns/resolution_inversee_fonctionnelle.png)

---

## 🧩 Création du poste client et intégration DNS
![Création du poste client dans VirtualBox](images/jonction_pc_client/creation_vm_pc.png)
![Configuration DNS du poste client](images/jonction_pc_client/forward_new_host.png)

---

## 🔐 Attribution des permissions
![Ajout des permissions](images/jonction_pc_client/join_device_active_directory_domain.png)

---

## 🧠 Compétences démontrées
- Virtualisation (VirtualBox)  
- Administration Windows Server  
- Active Directory  
- DNS  
- Sécurité Windows  
- GPO  
- Documentation professionnelle  

---
