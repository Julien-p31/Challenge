# 4 pôles informatiques. Le réseau est en 172.16.1.0/24.

- Le Pôle informatique (6 bureaux, environ 50 équipements au total) => 2^6 - 2 = 64 - 2 = 62
- Le Pôle Administratif (4 bureaux, environ 20 équipements au total) => 2^5 - 2 = 32 - 2 = 30
- Le Pôle Technicien (4 bureaux, environ 15 équipements au total) => 2^5 - 2 = 32 - 2 = 30
- Le Pôle développement (6 bureaux, environ 12 équipements au total) => 2^4 - 2 = 16 - 2 = 14


## **Découpage symétrique :**

- Sous-réseau 1 : Le Pôle informatique
- Adresse de réseau : 172.16.1.0/26
- Début de plage IP disponible : 172.16.1.1
- Fin de plage IP disponible : 172.16.1.62
- Adresse de broadcast : 172.16.1.63
---
- Sous-réseau 2 : Le Pôle Administratif
- Adresse de réseau : 172.16.1.64/26
- Début de plage IP disponible : 172.16.1.65
- Fin de plage IP disponible : 172.16.1.126
- Adresse de broadcast : 172.16.1.127
 ---
- Sous-réseau 3 : Le Pôle Technicien
- Adresse de réseau : 172.16.1.128/26
- Début de plage IP disponible : 172.16.1.129
- Fin de plage IP disponible : 172.16.1.190
- Adresse de broadcast : 172.16.1.191
---
- Sous-réseau 4 : Le Pôle développement
- Adresse de réseau : 172.16.1.192/26
- Début de plage IP disponible : 172.16.1.193
- Fin de plage IP disponible : 172.16.1.254
- Adresse de broadcast : 172.16.1.255
---


## **Découpage asymétrique :**

- Sous-réseau 1 : Le Pôle informatique
- Adresse de réseau : 172.16.1.0/26 
- Début de plage IP disponible : 172.16.1.1
- Fin de plage IP disponible : 172.16.1.62
- Adresse de broadcast : 172.16.1.63
---
- Sous-réseau 2 : Le Pôle Administratif
- Adresse de réseau : 172.16.1.64/27
- Début de plage IP disponible : 172.16.1.65
- Fin de plage IP disponible : 172.16.1.94
- Adresse de broadcast : 172.16.1.95
 ---
- Sous-réseau 3 : Le Pôle Technicien
- Adresse de réseau : 172.16.1.96/27
- Début de plage IP disponible : 172.16.1.97
- Fin de plage IP disponible : 172.16.1.126
- Adresse de broadcast : 172.16.1.127
---
- Sous-réseau 4 : Le Pôle développement
- Adresse de réseau : 172.16.1.128/28
- Début de plage IP disponible : 172.16.1.129
- Fin de plage IP disponible : 172.16.1.142
- Adresse de broadcast : 172.16.1.143
