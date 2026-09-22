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

## Travail réalisé

### 1. Création des VLAN

Création de plusieurs VLAN afin de séparer logiquement les différents réseaux.

### 2. Configuration des ports

Attribution des ports du switch aux VLAN correspondants.

### 3. Configuration du trunk

Configuration d'un lien trunk entre le switch et le routeur afin de transporter les différents VLAN.

### 4. Routage inter-VLAN

Configuration de sous-interfaces sur le routeur avec `802.1Q` afin de permettre la communication entre les différents VLAN.

### 5. Sécurisation des VLAN

Mise en place de plusieurs mesures de sécurité :

- Désactivation des ports inutilisés
- Placement des ports inutilisés dans un VLAN isolé
- Limitation des VLAN autorisés sur le trunk
- Modification du VLAN natif par défaut

## Vérifications

Utilisation de commandes Cisco IOS telles que :

```text
show vlan brief
show interfaces trunk
show ip interface brief
