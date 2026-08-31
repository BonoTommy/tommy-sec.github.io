# Portfolio – Administration Système & Cybersécurité

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
- Réseau : Host-Only
- Pare-feu : Profil Public (activé)

**PC-Client – Windows 11**
- Rôle : Client du domaine
- IP : 192.168.56.1
- Réseau : Host-Only

---

## 🔍 Étapes techniques

### 1. Configuration réseau
- Création du réseau Host-Only
- Attribution des IP statiques
- Vérification ARP
- Tests ICMP

### 2. Sécurité : Pare-feu Windows
- Profil Public conservé sur DC01
- Activation ciblée de ICMPv4-In
- Justification : diagnostic minimal + sécurité maximale

### 3. Installation AD DS
- Ajout du rôle Active Directory Domain Services
- Promotion du serveur en contrôleur de domaine
- Création du domaine : exemple.local

### 4. Configuration AD
- Création des OU
- Création des utilisateurs
- Création des groupes
- Attribution des permissions

### 5. GPO
- Mot de passe complexe
- Verrouillage de session
- Restrictions logicielles

### 6. Tests
- Joindre le PC-Client au domaine
- Connexion avec un utilisateur du domaine
- Application des GPO

---

## 📸 Captures d’écran
## 🧱



---

## 🧠 Compétences démontrées
- Virtualisation (VirtualBox)
- Administration Windows Server
- Active Directory
- Sécurité Windows
- GPO
- Documentation professionnelle

---

## 📬 Contact
Pour toute question ou opportunité professionnelle :  
bonneautommy00@gmail.com
