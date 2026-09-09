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
- IP : 192.168.56.1  
- Réseau : Host‑Only

---

## 🔍 Étapes techniques

1. Configuration réseau  
2. Sécurité : Pare‑feu Windows  
3. Installation AD DS  
4. Configuration Active Directory  
5. Configuration DNS  
6. Tests de connectivité et de résolution  
7. Jonction du client au domaine  
8. Attribution des permissions  
9. Validation finale

---

## 🌐 Réseau & VirtualBox

### ⚙️ Configuration du réseau Host‑Only
![Réseau Host‑Only VirtualBox](images/reseau_virtualbox/host-only-vb.png)

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
![Règle ICMPv4‑In DC01](images/pare-feu_windows/icmpv4-in-DC01.png)

---

### 💻 PC‑Client – Windows 11
![Pare‑feu PC‑Client](images/pare-feu_windows/pare-feu_pc.png)
![Règle ICMPv4‑In PC‑Client](images/pare-feu_windows/icmpv4-in-pc.png)

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
![Création de l’OU](images/aduc
