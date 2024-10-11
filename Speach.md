# Bilan des tâches réalisées

## 1. Configuration initiale du serveur Debian 12
- Le serveur a été installé et configuré de manière standard.
- Il reste à finaliser la configuration de Plex et de NFS.

## 2. Planification de l’intégration de NFS
- Nous avons planifié l’utilisation de NFS pour le partage des fichiers multimédia entre le serveur et les clients.
- NFS permettra de centraliser et de partager efficacement les contenus sur le réseau local.

## 3. Prochaines étapes

### a. Configuration de NFS sur le serveur Debian
- Finalisation de l’installation de NFS.
- Montage des répertoires multimédia partagés sur le serveur afin que Plex puisse y accéder.

### b. Installation et configuration de Plex
- Installation de Plex sur le serveur.
- Configuration des bibliothèques Plex pour qu’elles pointent vers les répertoires NFS partagés, permettant ainsi à Plex de lire et organiser les fichiers multimédia.

### c. Test de la diffusion sur clients
- Validation que les clients peuvent accéder aux contenus via Plex et lire les fichiers multimédia en streaming sans problème de latence ou d’accès.

## 4. Pourquoi utiliser NFS avec Plex ?
L’utilisation de NFS (Network File System) avec Plex présente plusieurs avantages clés :

### a. Partage centralisé des fichiers multimédia
- NFS permet de stocker tous les fichiers multimédia sur un seul serveur, et de les rendre accessibles sur plusieurs appareils du réseau.
- Cela simplifie la gestion des fichiers et évite la duplication des contenus.

### b. Performance améliorée
- Comparé à d’autres méthodes de partage comme SMB ou FTP, NFS offre souvent une meilleure performance pour le partage de fichiers sur un réseau local.
- Cela est crucial pour le streaming multimédia en temps réel avec Plex, qui nécessite une bande passante stable et rapide.

### c. Gestion centralisée
- Avec NFS, l'administration des fichiers (ajout, suppression, modification) est centralisée sur le serveur.
- Cela facilite les sauvegardes et simplifie la gestion des contenus multimédia.

## 5. Ce qui est prévu pour la démonstration finale

### a. Finalisation de la configuration NFS
- Assurer que les répertoires multimédia sont correctement partagés et montés sur le serveur Debian.

### b. Installation et configuration de Plex
- Installer Plex sur le serveur.
- Configurer les bibliothèques Plex pour utiliser les répertoires NFS partagés.

### c. Test de la diffusion sur clients
- Vérifier que les clients peuvent accéder aux fichiers multimédia via Plex et s’assurer que le streaming se déroule sans latence ni problèmes d'accès.


---

### 1. NFS (Network File System)
- Qu’est-ce que c’est ?
- NFS est un protocole qui permet de partager des fichiers entre ordinateurs sur un réseau local comme s'ils étaient stockés localement.

**Comment ça marche ?**
- Le serveur NFS partage des répertoires, et les clients les montent comme s’ils étaient sur leur propre machine.

**Avantages :**
- Rapide pour les réseaux locaux.
- Centralisation des fichiers.
- Pas de duplication de fichiers.

**Inconvénients :**
- Les permissions (UID/GID) doivent être bien configurées.
### 2. Plex
- Qu’est-ce que c’est ?
- Plex est un logiciel de diffusion de contenu multimédia depuis un serveur vers différents appareils (TV, smartphones).

**Comment ça marche avec NFS ?**
- Plex peut lire directement les fichiers via NFS sans avoir à les copier sur le serveur Plex.

**Avantages :**
- Organise et diffuse films/séries avec infos automatiques.
- Streaming sur plusieurs appareils.

**Inconvénients :**
- Nécessite un réseau rapide pour le streaming HD.

**Configurer Plex avec NFS :**
- Ajoutez un dossier de bibliothèque qui pointe vers un répertoire NFS monté.

### 3. Questions fréquentes
- NFS vs SMB ?
- NFS : Plus rapide pour Linux/Unix.
- SMB : Plus adapté pour Windows.
- Plex peut-il lire depuis NFS ?
- Oui, Plex peut lire directement depuis un partage NFS.

**Que faire si NFS ne fonctionne pas ?**
- Vérifiez les permissions et assurez-vous que le partage est monté correctement.

### 4. Comparaison rapide : SMB, FTP, NFS

**1. SMB (Server Message Block)**
- Usage : Réseaux Windows.
- Avantages : Partage fichiers, imprimantes, droits d'accès.
- Inconvénients : Plus lent sur Linux/Unix.

### 2. FTP (File Transfer Protocol)
- Usage : Transfert de fichiers ponctuels.
- Avantages : Simple à configurer, multi-OS.
- Inconvénients : Pas optimisé pour les partages réseau.

### 3. NFS (Network File System)
- Usage : Partage de fichiers en réseau local (Linux/Unix).
- Avantages : Rapide, optimisé pour Linux.
- Inconvénients : Moins adapté à Windows.

### 5. Pourquoi NFS n'est pas d'autre "N" ?
- Le "N" dans NFS signifie Network car NFS permet de partager des fichiers sur un réseau local. Il pourrait être "Node" ou "Named", mais "Network" est le terme qui définit l'idée principale : accès aux fichiers via un réseau.
