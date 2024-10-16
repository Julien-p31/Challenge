# Questions Potentielles pour la Présentation du Projet Plex

### 1. Pourquoi avez-vous utilisé deux cartes réseau sur chaque machine ?
- **Réponse :** Une carte NAT permet d'accéder à Internet pour les mises à jour et les services Plex, tandis que la carte réseau interne assure une connexion locale stable entre le serveur et le client pour le partage NFS.

### 2. Comment avez-vous résolu les problèmes de routage entre le réseau interne et Internet ?
- **Réponse :** En définissant des routes statiques pour le réseau interne sur `enp0s8` et en utilisant `enp0s3` comme passerelle par défaut pour le trafic Internet.

### 3. Quels étaient les problèmes de droits sur le partage NFS ?
- **Réponse :** Le client Ubuntu ne pouvait pas écrire sur le partage NFS du serveur Debian à cause de permissions différentes. La solution a été d’aligner les droits utilisateur sur les deux machines.

### 4. Pourquoi avez-vous choisi un partage NFS pour Plex ?
- **Réponse :** NFS est simple à configurer et performant pour un partage de fichiers en réseau local, permettant à la fois au client Ubuntu et à Plex de lire et écrire des fichiers multimédias.

### 5. Pourquoi utiliser Debian et Ubuntu pour ce projet ?
- **Réponse :** Debian est stable et sécurisé pour un serveur, tandis qu'Ubuntu offre une interface conviviale et est compatible avec Debian, facilitant la gestion du client.

### 6. Quels outils ou commandes avez-vous utilisés pour configurer le réseau ?
- **Réponse :** Netplan pour configurer les interfaces réseau et `ip route` pour gérer les routes et la passerelle par défaut.

### 7. Comment avez-vous testé que la configuration fonctionnait correctement ?
- **Réponse :** En vérifiant la connectivité Internet via la carte NAT, et en testant l'accès au serveur depuis le client via des pings et le montage NFS.

### 8. Quelles ont été les principales difficultés rencontrées pendant le projet ?
- **Réponse :** Les problèmes de connexion simultanée au réseau local et à Internet, ainsi que les permissions sur le partage NFS.

### 9. Comment avez-vous configuré les adresses IP statiques sur les cartes internes ?
- **Réponse :** Avec Netplan, en définissant des IP statiques (`172.16.10.10` pour le serveur et `172.16.10.20` pour le client) dans le fichier de configuration réseau.

### 10. Pensez-vous que cette configuration est facilement extensible ?
- **Réponse :** Oui, il serait possible d'ajouter plus de clients ou d'étendre les partages NFS en ajustant simplement les adresses IP et permissions.
