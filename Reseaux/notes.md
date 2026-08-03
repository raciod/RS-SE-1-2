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
- **Protocoles** : MAC (Media Access Control), LLC (Logical Link Control), CSMA/CD (Carrier Sense Multiple Access with Collision Detection), CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance), HDLC (High-Level Data Link Control), PPP (Point-to-Point Protocol), Ethenet, Token Bus, Token Ring.

#### Couche Réseaux
- **Unité de données** : Paquet
- **Rôle** :
  - Adressage logique universel
  - Routage
  - Contrôle de congestion
- **Protocoles** : IP (Internet Protocol)

#### Couche Transport
- **Unité de données** : Segment (TCP) / Datagramme (UDP)
- **Rôle** : Assurer une transmission avec une certaine qualité de service entre deux machines quelconques.
- **Protocoles** : TCP (Transmission Control Protocol), UDP (User Datagram Protocol)

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


## Couche physique — @raciod
 
### Introduction
Les modes de connexion :
- **Simplex** : unidirectionnelle
- **Half duplex** : bidirectionnelle à l'alternat
- **Full duplex** : bidirectionnelle
### Notions clés (souvent demandées en examen)
- **Bande passante** : intervalle de fréquences que le support peut transmettre (Hz)
- **Débit binaire** (bit rate) : nombre de bits transmis par seconde (bit/s)
- **Rapidité de modulation** (baud rate) : nombre de symboles transmis par seconde (bauds)
  - Un symbole peut coder plusieurs bits → débit binaire = rapidité de modulation × log2(nombre d'états)
- **Théorème de Nyquist** : débit max sans bruit = 2 × B × log2(V), avec B = bande passante, V = nb de niveaux de signal
- **Théorème de Shannon** : capacité max avec bruit = B × log2(1 + S/N), avec S/N = rapport signal/bruit
- **Atténuation** : perte de puissance du signal en fonction de la distance
- **Bruit** : perturbation qui dégrade le signal (thermique, diaphonie, interférence)
### Transmission numérique et codage
Types de codage :
- NRZ (Non Return to Zero)
- NRZI (NRZ Inverted)
- Manchester
- Manchester différentiel
- Miller
- Bipolaire simple
#### Codage utilisé selon la topologie / le protocole
 
| Topologie (historique) | Protocole associé | Codage utilisé |
|---|---|---|
| **Étoile** (10BASE-T) | Ethernet | **Manchester** |
| **Anneau** (Token Ring, IEEE 802.5) | Token Ring | **Manchester différentiel** |
| **Point à point** (liaisons série, WAN) | HDLC, liaisons télécom | **NRZI** |
| **Point à point** (lignes T1/E1) | Téléphonie numérique | **Bipolaire (AMI)** |
| **USB** (bus, mais point à point logique) | USB | **NRZI** |
 
À retenir pour l'examen :
- **Manchester** et **Manchester différentiel** intègrent une transition d'horloge dans chaque bit → utilisés sur les topologies à support partagé (bus, anneau) où toutes les stations doivent rester synchronisées sans ligne d'horloge séparée.
- **NRZ/NRZI** sont plus simples et efficaces en bande passante mais nécessitent une récupération d'horloge externe → plus courants sur liaisons point à point.
- **Miller** et **Bipolaire** apparaissent surtout dans des contextes de téléphonie plus anciens.
### Transmission analogique et modulation
Types de modulation :
- Modulation d'amplitude (ASK)
- Modulation de fréquence (FSK)
- Modulation de phase (PSK)
### Différence entre codage et modulation
- **Codage** : transforme un signal **numérique** (bits) en un autre signal **numérique** adapté au support (bande de base). Pas de porteuse.
- **Modulation** : transforme un signal **numérique ou analogique** en un signal **analogique**, en faisant varier une caractéristique d'une onde porteuse (amplitude, fréquence, phase). Utilisée notamment pour la transmission sur de longues distances ou sur des supports non filaires.
- En résumé : le codage transforme des bits en impulsions électriques directes, tandis que la modulation transforme ces bits en modifiant une onde radio/analogique (la porteuse).

- **Multiplexage**: Permet de partager un même support entre plusieurs communications
### Supports de transmission
- **Guidés** : câble coaxial, paire torsadée, fibre optique
- **Non guidés** : ondes radio, infrarouge, satellite

---

## Couche Liaison — @raciod

### Introduction
Rôle : assurer une transmission exempte d'erreurs sur un canal de communication, en fractionnant les données en trames.

### Délimitation de trames
Il existe trois méthodes :
- Compter les caractères
- Utiliser des champs délimiteurs de trame (fanions)
- Violer le codage normalement utilisé dans la couche physique

**Compter les caractères**
- Un champ dans l'en-tête indique le nombre de caractères de la trame
- Problème : si la valeur du champ est modifiée au cours de la transmission
- Méthode rarement utilisée seule

**Utiliser des délimiteurs (fanions)**
- Un fanion est placé au début et à la fin de chaque trame
- Un fanion = séquence particulière de bits (ex : 01111110)
- Des bits de transparence sont nécessaires (bit stuffing : 0 inséré après cinq 1 successifs) pour éviter qu'une séquence de données soit confondue avec le fanion
- Technique utilisée dans HDLC et PPP

Avantages des fanions :
- Permet toujours de retrouver la synchronisation
- Permet l'envoi de trames de tailles quelconques
- Technique la plus simple

### Détection/Correction d'erreurs
- **Taux d'erreur** sur un canal = nombre de bits erronés / nombre de bits émis
- Deux stratégies possibles pour la destination :
  - **Détecter** les erreurs, puis demander une retransmission → codes détecteurs d'erreurs
  - **Détecter et corriger** les erreurs → codes correcteurs d'erreur (CRC / FCS)
- Explication du CRC : *(à faire)*

### Contrôle de flux
Pourquoi ces mécanismes : l'émetteur peut envoyer plus vite que le récepteur ne traite, et le canal peut perdre/corrompre des trames. Il faut donc des mécanismes pour une transmission fiable et maîtrisée.

Les 4 mécanismes de base :
- **Acquittements (ACK)** : le récepteur confirme « j'ai bien reçu » — sinon l'émetteur ne sait jamais si ses données sont arrivées.
- **Temporisateurs** : chronomètre lancé après chaque envoi ; si aucun ACK avant la fin du délai, l'émetteur suppose une perte et retransmet.
- **Numérotation des trames** : chaque trame a un numéro, pour que le récepteur distingue une trame nouvelle d'une retransmission (due à un ACK perdu) — évite de traiter deux fois le même paquet.
- **Limitation du nombre de trames envoyées** : on ne peut pas envoyer indéfiniment sans attendre d'ACK, sinon il faudrait une mémoire tampon infinie côté récepteur. On limite donc combien de trames peuvent rester « en attente d'ACK » à la fois.

### Protocoles de la couche liaison

Protocoles de couche 2 selon le domaine d'application : réseaux publics (HDLC), point à point (PPP), réseaux locaux (MAC/LLC).

#### 1. HDLC (High-Level Data Link Control)
- **Rôle** : protocole orienté bit, utilisé dans les réseaux publics (couche 2 de X.25/Transpac).
- **Modes** : LAP (non équilibré, maître/esclave) / LAPB (équilibré, point à point).
- **Trame** : fanions (`01111110`) + Adresse + Commande + Données + FCS (CRC-16).
- **Types de trames** :
  - **I** : données, avec N(S)/N(R)
  - **S** : contrôle flux/erreurs (RR, RNR, REJ, SREJ)
  - **U** : gestion de liaison (SABM, DISC, UA)

#### 2. PPP (Point-to-Point Protocol)
- **Rôle** : successeur de SLIP, gère la connexion point à point à Internet.
- **Trame** : proche HDLC, fanions + Adresse (`0xFF`) + Commande (`0x03`) + Protocole (ex : `0021`=IP, `C021`=LCP, `8021`=NCP) + données (≤1500 octets).
- **LCP** : établit/configure/teste la liaison physique.
- **NCP** : négocie les paramètres réseau (ex : IPCP → IP).
- **Cycle** : connexion → LCP → NCP (établissement) ; NCP → LCP → déconnexion (fin).

### 3. MAC et LLC (IEEE 802.x)
**MAC** : accès au support partagé, adressage physique (48 bits : I/G, U/L, code constructeur). Trame Ethernet (802.3) : préambule/SFD, adresses MAC (6+6 octets), Longueur/Type, données (46–1500 octets), FCS.

**LLC (802.2)** : masque les technologies MAC à la couche Réseau.
- **LLC1** : sans connexion, sans acquittement
- **LLC2** : mode connecté, contrôle erreur/flux
- **LLC3** : sans connexion, avec acquittements
- Trame : DSAP/SSAP (ex : `06`=IP) + Contrôle + données

**LLC vs MAC** : le MAC dépend du média (Ethernet, Wi-Fi...) et gère l'adressage physique ; le LLC est commun à toutes les technologies MAC et fait l'interface avec la couche Réseau via DSAP/SSAP — en résumé, MAC = "comment parler sur le câble", LLC = "à qui je m'adresse au-dessus".

