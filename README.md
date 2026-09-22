 Projet de routage inter-VLAN et sécurisation des VLAN

## Objectif

Mettre en place une communication entre plusieurs VLAN grâce au routage inter-VLAN, puis appliquer des mesures de sécurisation de base sur le réseau.

## Environnement

- Cisco Packet Tracer
- 1 routeur
- 1 switch
- Plusieurs postes clients
- VLAN
- Routage inter-VLAN
- <img width="823" height="391" alt="topologie" src="https://github.com/user-attachments/assets/39e8a02a-ae04-450e-98fb-b6a083a6d61d" />


## Travail réalisé

### 1. Création des VLAN

Création de plusieurs VLAN afin de séparer logiquement les différents réseaux.
<img width="591" height="136" alt="vlan" src="https://github.com/user-attachments/assets/2a8ecea2-fa19-4aaf-a36e-f5afa1f58449" />

### 2. Configuration des ports

Attribution des ports du switch aux VLAN correspondants.
avec la commande "switchport access" 

### 3. Configuration du trunk

Configuration d'un lien trunk entre le switch et le routeur afin de transporter les différents VLAN.
avec la commande "switchport mode trunk"<img width="467" height="53" alt="trunk" src="https://github.com/user-attachments/assets/327fb6ae-425f-4176-b413-5ff16a9adaa9" />


### 4. Routage inter-VLAN

Configuration de sous-interfaces sur le routeur avec `802.1Q` afin de permettre la communication entre les différents VLAN.
avec les commandes
interfaces fastethernet0/0/0.10 (sous interfaces appartenant au vlan 10 )
encapsulation dot1q 10 (pour la provenance du packet)
ip address 192.168.10.254 255.255.255.0 (passserelle par defaut et le masque de sous reseau)

j'ai fais les configuration adapter pour tous mes sous reseau pour que la communication sois possibble entre les vlan 

### 5. Sécurisation des VLAN

Mise en place de plusieurs mesures de sécurité :

- Désactivation des ports inutilisés
  avec la commande
  shutdown
- Placement des ports inutilisés dans un VLAN isolé
  avec la commande "switchport access"
  <img width="573" height="380" alt="port non utiliser" src="https://github.com/user-attachments/assets/80103cd3-6742-4bc0-a47c-97d53839c963" />
 
- Limitation des VLAN autorisés sur le trunk
  avec la commande "switchport trunk allowed"
  <img width="472" height="178" alt="vlan alowed" src="https://github.com/user-attachments/assets/8db78d76-3183-4811-8a4b-47991511e1bd" />


- Modification du VLAN natif par défaut
  avec la commande "switchport trunk native vlan"
 
<img width="472" height="178" alt="vlan alowed" src="https://github.com/user-attachments/assets/4f36b1a2-5a62-4873-b792-582600b6c362" />

-mettre tous les port connecter au poste utilisateur en mode access 
 avec la commande "switchport mode access"

-desactiver le DTP (dinamic trunking protocole) de tous les port connecté au poste utilisateur 
avec la commande "switchport nonegociate<img width="503" height="710" alt="ping" src="https://github.com/user-attachments/assets/f31a2282-ff98-430e-b7f6-f641037fda4c" />


## Vérifications

Utilisation de commandes Cisco IOS telles que :

```text
show vlan brief
show interfaces trunk
show ip interface brief
