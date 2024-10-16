# Questions Potentielles pour la Présentation du Projet Plex

### 1. Pourquoi avez-vous utilisé deux interfaces réseau sur chaque machine ?
- **Réponse :** Pour séparer les communications. La première interface (`enp0s3`) est configurée en mode NAT avec DHCP pour permettre au serveur et au client d'accéder à Internet (mise à jour du système, connexion aux services Plex). La seconde (`enp0s8`) est dédiée au réseau local interne, avec des adresses IP statiques, pour garantir une connexion fiable et isolée entre le serveur Debian et le client Ubuntu, facilitant ainsi le partage NFS.

### 2. Comment avez-vous résolu les problèmes de routage entre le réseau interne et l'Internet ?
- **Réponse :** En configurant des routes statiques pour le réseau local. Le trafic interne est routé via `enp0s8` avec des adresses IP fixes (`172.16.10.10` pour le serveur et `172.16.10.20` pour le client), tandis que le trafic Internet passe par `enp0s3`, avec une passerelle par défaut fournie par le DHCP. Cela permet de gérer efficacement les paquets entrants et sortants sans conflits.

### 3. Quels problèmes avez-vous rencontrés avec les permissions sur le partage NFS ?
- **Réponse :** Initialement, le client Ubuntu n'avait pas les droits suffisants pour écrire sur le partage NFS hébergé sur le serveur Debian. Cela était dû à une différence de permissions et de propriétaires sur les répertoires partagés. La solution a consisté à synchroniser les UID et GID (User ID et Group ID) entre le serveur et le client pour garantir que les utilisateurs aient les mêmes droits d'accès, permettant ainsi la lecture et l'écriture sur le partage NFS.

### 4. Pourquoi avez-vous opté pour un partage NFS pour le stockage de médias Plex ?
- **Réponse :** NFS (Network File System) est particulièrement adapté aux environnements Linux pour le partage de fichiers en réseau local. Il offre de bonnes performances pour les transferts de fichiers volumineux, une configuration simple, et est natif sur la plupart des distributions Linux, ce qui permet au serveur Plex et au client Ubuntu de monter le même partage sans complication.

### 5. Pourquoi avez-vous choisi Debian pour le serveur et Ubuntu pour le client ?
- **Réponse :** Debian est réputé pour sa stabilité, sa robustesse et sa sécurité, ce qui en fait un excellent choix pour un environnement serveur. Ubuntu, basé sur Debian, offre une interface utilisateur plus accessible et des mises à jour fréquentes, ce qui facilite la gestion et la maintenance sur le client.

### 6. Quels outils ou commandes avez-vous utilisés pour configurer le réseau et les routes ?
- **Réponse :** J'ai utilisé **Netplan** pour la configuration des interfaces réseau sur Debian et Ubuntu, en définissant les paramètres IP et les règles de routage. Les commandes **ip route** et **route** ont été employées pour vérifier et ajuster les routes statiques et la passerelle par défaut, assurant une séparation claire entre le trafic local et celui destiné à Internet.

### 7. Comment avez-vous vérifié que la configuration réseau et NFS fonctionnait correctement ?
- **Réponse :** J'ai effectué des tests de connectivité en utilisant **ping** pour vérifier la communication entre le serveur et le client sur le réseau interne. Ensuite, j'ai monté manuellement le partage NFS sur le client pour m'assurer qu'il était accessible et j'ai tenté de lire et d'écrire des fichiers pour valider les permissions. Enfin, des tests de flux vidéo via Plex ont confirmé que le serveur pouvait diffuser du contenu sans problème.

### 8. Quelles ont été les principales difficultés techniques rencontrées pendant le projet ?
- **Réponse :** Les principales difficultés ont été liées à la configuration de la double interface réseau. Il était complexe de garantir que le serveur puisse simultanément accéder à Internet et rester accessible en local. De plus, des problèmes de permissions sur le partage NFS ont empêché le client de déposer des fichiers sur le serveur, nécessitant des ajustements des droits utilisateurs et des configurations NFS.

### 9. Comment avez-vous configuré les adresses IP statiques sur les interfaces internes (`enp0s8`) ?
- **Réponse :** J'ai utilisé **Netplan** pour définir les adresses IP statiques sur `enp0s8` dans le fichier de configuration YAML, en spécifiant `172.16.10.10/24` pour le serveur et `172.16.10.20/24` pour le client. Cette configuration garantit que les machines puissent se localiser rapidement sur le réseau interne sans dépendre du DHCP, offrant une connexion stable et persistante.

### 10. Pensez-vous que cette architecture est facilement extensible ?
- **Réponse :** Oui, cette configuration est conçue pour être évolutive. Il serait simple d'ajouter d'autres clients en attribuant des IP statiques supplémentaires dans le même sous-réseau et en ajustant les permissions NFS. De plus, le modèle de double interface (NAT et interne) permettrait d’intégrer de nouveaux services ou points d'accès sans perturber la structure existante.
