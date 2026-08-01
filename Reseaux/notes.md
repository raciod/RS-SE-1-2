# Reseaux — Notes

<!--
  How to add a note:
  - One "##" heading per topic/lecture
  - Tag your GitHub handle next to the title
  - Example: ## Modele OSI — @raciod
-->


## Introduction — @raciod

### Caractéristiques des réseaux
- **Type des connexions**
  - **Point à point** : un réseau où les machines sont reliées par des canaux dédiés spécifiquement à la connexion de deux machines.
  - **Multipoint** : un canal est partagé par un ensemble de machines.
- **Topologie** : maillage / bus / anneau / étoile / arbre ...
- **Taille du réseau** : LAN / MAN / WAN / Internet

### Modes de transmission
- **Unicasting** : une machine (source) envoie un message à une machine destination.
- **Broadcasting** (diffusion générale) : une machine (source) envoie un message à toutes les machines.
- **Multicasting** (diffusion restreinte) : une machine envoie un message aux machines d'un groupe.

### Modèle de référence OSI
- Mnémonique : **P**lease **D**o **N**ot **T**hrow **S**panish **P**izza **A**way
- **P**hysique → **D**ata Link (liaison) → **N**etwork (réseaux) → **T**ransport → **S**ession → **P**resentation → **A**pplication

### Les couches

**Principe de fonctionnement** — chaque couche :
- Reçoit les données de la couche supérieure
- Effectue un certain traitement
- Transmet les données en ajoutant un en-tête (informations de contrôle)

#### Couche Physique
- **Unité de données** : Bits
- **Rôle** : Transmission des bits de façon brute sur un canal de communication.
- **Protocoles** :

#### Couche Liaison
- **Unité de données** : Trame
- **Rôle** :
  - Gestion des erreurs
  - Régulation du flux
  - Contrôle d'accès à un canal partagé (MAC)
- **Protocoles** : MAC, LLC, CSMA/CD, CSMA/CA

#### Couche Réseaux
- **Unité de données** : Paquet
- **Rôle** :
  - Adressage logique universel
  - Routage
  - Contrôle de congestion
- **Protocoles** : IP

#### Couche Transport
- **Unité de données** : Segment (TCP) / Datagramme (UDP)
- **Rôle** : Assurer une transmission avec une certaine qualité de service entre deux machines quelconques.
- **Protocoles** : TCP, UDP

#### Couche Session
- **Unité de données** : Données
- **Rôle** :
  - Ouvrir et fermer des sessions entre utilisateurs
  - Organiser et synchroniser le dialogue
- **Protocoles** :

#### Couche Présentation
- **Unité de données** : Données
- **Rôle** : Chargée de la représentation des données échangées dans un souci de compatibilité (compression, cryptage).
- **Protocoles** :

#### Couche Application
- **Unité de données** : Données
- **Rôle** : Chargée de l'exécution des applications réseaux.
  - Services offerts :
    - Transfert de fichiers
    - Exécutions de travaux à distance
    - Interrogation de bases de données
- **Protocoles** :
