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
---

## 🌐 Réseau & VirtualBox

Cette section illustre la configuration réseau du laboratoire Active Directory dans VirtualBox.  
L’objectif est de garantir une communication isolée et sécurisée entre le contrôleur de domaine (DC01) et le poste client.

### ⚙️ Configuration du réseau VirtualBox
Le réseau utilisé est de type **Host‑Only**, permettant une connexion directe entre les machines virtuelles sans accès Internet.

![Réseau Host‑Only VirtualBox](images/reseau_virtualbox/host-only_vb.png)
> Configuration du réseau Host‑Only dans VirtualBox – interface privée entre DC01 et PC‑Client.

---

### 🧩 Paramètres IP des machines
**DC01 – Windows Server 2022**
- IP : 192.168.56.10  
- Masque : 255.255.255.0  
- Profil : Public (pare‑feu activé)

![Paramètres réseau DC01](images/reseau_virtualbox/parametre_reseau_DC01.png)
> Paramètres IP statiques du contrôleur de domaine DC01.

**PC‑Client – Windows 11**
- IP : 192.168.56.1  
- Masque : 255.255.255.0  
- Profil : Public (pare‑feu activé)

![Paramètres réseau PC‑Client](images/reseau_virtualbox/parametre_reseau_pc-client.png)
> Paramètres IP statiques du poste client.

---

### 🔍 Vérification de la connectivité
Les tests ARP et ping confirment la communication entre les deux machines.

![ARP DC01](images/reseau_virtualbox/arp_DC01.png)
> Table ARP de DC01 – les deux machines se voient sur le réseau Host‑Only.

![Ping DC01](images/reseau_virtualbox/ping_DC01.png)
> Test de ping depuis DC01 vers le PC‑Client.

![Ping PC‑Client](images/reseau_virtualbox/ping_pc-client.png)
> Test de ping depuis le PC‑Client vers DC01.

---

### 🧠 Résumé
Cette configuration réseau démontre :
- la maîtrise de VirtualBox et du mode Host‑Only ;
- la mise en place d’adresses IP statiques cohérentes ;
- la validation de la connectivité via ARP et ping ;
- la sécurisation du trafic grâce au pare‑feu Windows activé.

---

## 🔐 Sécurité – Pare‑feu Windows

Cette section présente la configuration du pare‑feu Windows sur les deux machines du laboratoire : DC01 (contrôleur de domaine) et PC‑Client.  
L’objectif est de maintenir une sécurité maximale tout en permettant les tests ICMP nécessaires au diagnostic réseau.

### 🧱 DC01 – Windows Server 2022

Le profil **Public** est activé pour renforcer la sécurité du serveur.  
Seule la règle **ICMPv4‑In** est autorisée afin de permettre les tests de connectivité.

![Pare-feu DC01 – Profil Public](images/pare-feu_windows/public_DC01.png)
> Pare‑feu Windows activé sur DC01 – profil Public actif.

![Règle ICMPv4-In DC01](images/pare-feu_windows/icmpv4-in_DC01.png)
> Autorisation ciblée du protocole ICMPv4‑In pour les tests de ping.

---

### 💻 PC‑Client – Windows 11

Le pare‑feu est également activé sur le profil **Public**, avec la même règle ICMPv4‑In autorisée pour les diagnostics.

![Pare-feu PC-Client](images/pare-feu_windows/pare-feu_pc.png)
> Pare‑feu Windows activé sur le PC‑Client – profil Public actif.

![Règle ICMPv4-In PC-Client](images/pare-feu_windows/icmpv4-in_pc.png)
> Autorisation ICMPv4‑In sur le PC‑Client pour les tests de connectivité.

---

### 🧠 Résumé

Cette configuration démontre :
- la maîtrise du pare‑feu Windows sur serveur et poste client ;
- la mise en place d’un profil Public pour une sécurité renforcée ;
- l’autorisation sélective du protocole ICMP pour les diagnostics réseau ;
- la cohérence des règles entre les deux machines du laboratoire.


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
