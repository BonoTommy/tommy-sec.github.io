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

## 🧱 Installation du rôle Active Directory Domain Services (AD DS)

Cette section illustre l’installation du rôle AD DS sur le serveur DC01 et sa promotion en contrôleur de domaine.

### ⚙️ Ajout du rôle AD DS
Le rôle Active Directory Domain Services est ajouté via le Gestionnaire de serveur.

![Ajout du rôle AD DS](images/ad_ds/ad_ds_installation.png)
> Sélection du rôle AD DS dans l’assistant d’ajout de rôles et fonctionnalités.

![Rôles et fonctionnalités cochés](images/ad_ds/roles_fonctionnalites.png)
> Vérification des rôles et fonctionnalités nécessaires avant installation.

![Installation en cours](images/ad_ds/installlation.png)
> Progression de l’installation du rôle AD DS sur DC01.

---

### 🧩 Promotion du serveur en contrôleur de domaine
Une fois le rôle installé, le serveur est promu pour créer une nouvelle forêt Active Directory.

![Promotion du serveur](images/ad_ds/promouvoir.png)
> Lancement de la promotion du serveur en contrôleur de domaine.

![Nom du domaine](images/ad_ds/nom_domaine.png)
> Définition du nom de domaine pour la nouvelle forêt (exemple : *exemple.local*).

![Configuration du contrôleur](images/ad_ds/configuration_controleur.png)
> Paramètres du contrôleur de domaine : niveau fonctionnel, mot de passe DSRM et options DNS.

![Validation avant installation](images/ad_ds/ad_ds-checked.png)
> Vérification des prérequis avant la promotion du serveur.

---

### 🧠 Vérification post‑installation
Après redémarrage, le serveur DC01 est opérationnel comme contrôleur de domaine.

![Contrôleur de domaine](images/ad_ds/controleur_domaine.png)
> DC01 est maintenant le contrôleur de domaine de la forêt Active Directory.

![Console ADUC](images/ad_ds/console_aduc.png)
> Console “Utilisateurs et ordinateurs Active Directory” affichant le domaine configuré.

---

### 🧾 Résumé
Cette installation démontre :
- la maîtrise du rôle AD DS sous Windows Server 2022 ;
- la création d’une forêt et d’un domaine fonctionnel ;
- la promotion réussie du serveur DC01 en contrôleur de domaine ;
- la validation de la configuration via la console ADUC.

---

## 👥 Création des utilisateurs et groupes dans ADUC

Cette section illustre la configuration des unités d’organisation, des utilisateurs et des groupes dans Active Directory à l’aide de la console ADUC.

### 🧭 Ouverture de la console ADUC
![Console ADUC](images/aduc/console_aduc.png)
> Console “Utilisateurs et ordinateurs Active Directory” ouverte sur le domaine *exemple.local*.

---

### 🗂️ Création d’une unité d’organisation
Une unité d’organisation (OU) nommée **Employés** est créée pour regrouper les comptes utilisateurs.

![Création de l’OU](images/aduc/unite_organisation.png)
> Création de l’unité d’organisation “Employés”.

![Arborescence du domaine](images/aduc/arborescence.png)
> L’OU “Employés” apparaît dans l’arborescence du domaine.

---

### 👤 Création des utilisateurs
Trois utilisateurs sont ajoutés à l’OU : **Alice Tremblay**, **Bob Gagnon** et **Charlie Dubois**.

![Création d’un utilisateur](images/aduc/creation_utilisateur.png)
> Fenêtre de création d’un utilisateur dans ADUC.

![Liste des employés](images/aduc/3_employes.png)
> Les trois utilisateurs créés apparaissent dans l’OU “Employés”.

---

### 🧩 Création des groupes
Deux groupes sont créés pour organiser les permissions : **Groupe_IT** et **Groupe_RH**.

![Création d’un groupe](images/aduc/creation_groupe.png)
> Création du groupe “Groupe_IT” (type : sécurité, portée : globale).

![Liste des groupes](images/aduc/2_groupes.png)
> Les deux groupes visibles dans la console ADUC.

---

### 🔗 Ajout des utilisateurs aux groupes
Les utilisateurs sont ensuite ajoutés aux groupes correspondants :
- Alice et Charlie → Groupe_IT  
- Bob → Groupe_RH

![Ajout d’un utilisateur à un groupe](images/aduc/ajout_utilisateur_groupe.png)
> Ajout d’un utilisateur au groupe via l’onglet “Membre de”.

![Membres du groupe](images/aduc/membres.png)
> Vérification des membres du groupe “Groupe_IT”.

---

### 🧠 Résumé
Cette configuration démontre :
- la création d’une structure logique dans Active Directory ;
- la gestion des utilisateurs et des groupes ;
- la mise en place d’une organisation claire pour les permissions et la sécurité.

---

## 🌐 Configuration DNS

Cette section illustre la mise en place du service DNS sur le contrôleur de domaine DC01, essentiel au bon fonctionnement d’Active Directory.

### ⚙️ Création de la zone directe
![Zone directe DNS](images/dns/forward_lookup_zones.png)
> Création de la zone de recherche directe pour le domaine *corp.local*.

![Type de zone DNS](images/dns/zone_type.png)
> Sélection du type de zone : Primary Zone.

![Mode de réplication DNS](images/dns/mode_replication_dns.png)
> Choix du mode de réplication DNS pour les contrôleurs du domaine *corp.local*.

---

### 🧩 Création de la zone inversée
![Assistant New Zone Wizard](images/dns/new_zone_wizard.png)
> Assistant de création d’une zone de recherche inversée IPv4.

![Network ID](images/dns/network_id.png)
> Définition du Network ID : 192.168.56.

![Zone inversée créée](images/dns/56_168_192_in-addr_arpa.png)
> Zone inversée 56.168.192.in‑addr.arpa créée avec succès.

---

### 🔧 Configuration de l’enregistrement PTR
![Configuration PTR](images/dns/configuration_ptr.png)
> Ajout d’un enregistrement PTR pour l’adresse IP 192.168.56.10 pointant vers *dc01.corp.local*.

![Zone inversée avec PTR](images/dns/zone_inversee_ptr_visible.png)
> Enregistrement PTR visible dans la zone inversée.

---

### 🧠 Vérification des enregistrements DNS
![Vérification DNS](images/dns/verification_enregistrements_dns.png)
> Vérification des enregistrements A et PTR dans la console DNS.

---

### 🧪 Tests de résolution DNS
![Résolution directe](images/dns/ns_lookup_directe.png)
> Test `nslookup dc01.corp.local` : résolution directe réussie.

![Résolution inversée fonctionnelle](images/dns/resolution_inversee_fonctionnelle.png)
> Test `nslookup 192.168.56.10` : résolution inversée fonctionnelle.

---

### 🧾 Résumé
Cette configuration DNS démontre :
- la création des zones directe et inversée ;
- la mise en place d’un enregistrement PTR pour DC01 ;
- la validation de la résolution directe et inversée via `nslookup`.

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
