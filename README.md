# SAÉ Cyber 4.0 - Infrastructure Réseau et Cybersécurité 🔒

## 📝 Objectif
Mettre en place une **infrastructure réseau complète** et **sécurisée** incluant plusieurs zones (LAN, DMZ, Internet) connectées via des firewalls, tout en assurant :
- La segmentation réseau 🔗.
- La sécurité des flux 🛡️.
- La supervision et la détection d'intrusions 🔍.

---

## 🌐 Topologie réseau
### Description de l'architecture
1. **LAN interne** :
   - Deux réseaux locaux pour les utilisateurs internes (LAN A et LAN B).
   - Chaque réseau est isolé par un firewall dédié.

2. **DMZ (A1, A2, B)** :
   - Zones démilitarisées contenant les serveurs publics :
     - Serveurs Web et FTP pour la partie A.
     - Accès Wi-Fi sécurisé.
     - Serveur Web pour la partie B.
   - Chaque DMZ est protégée par un firewall spécifique pour limiter les flux entrants/sortants.

3. **Internet** :
   - Connecté via un IDS (Intrusion Detection System) chargé de surveiller les anomalies réseau.

4. **Firewalls (Stormshield)** :
   - Séparent les différentes zones (LAN, DMZ et Internet) et filtrent les flux réseau.

---

## 🔒 Sécurisation réseau
### Politique de sécurité
1. **Segmentation des flux** :
   - Les utilisateurs internes n’ont pas d’accès direct à Internet : tout passe par un firewall.
   - Les serveurs en DMZ sont accessibles uniquement via des ports spécifiques pour chaque service (HTTP/HTTPS, FTP).

2. **Protection des DMZ** :
   - Règles de filtrage strictes empêchant tout trafic initié depuis la DMZ vers le LAN.
   - Contrôle des communications entre DMZ et LAN.

3. **Authentification** :
   - Utilisation de certificats SSL pour sécuriser les échanges avec les serveurs Web.
   - Wi-Fi configuré avec une authentification renforcée (WPA2-Enterprise).

---

## 🔍 Supervision et détection
1. **IDS (Intrusion Detection System)** :
   - Surveillance des anomalies réseau, telles que des attaques DoS ou des scans non autorisés.
   - Analyse du trafic pour détecter les tentatives de compromission.

2. **Outils de supervision** :
   - **Nagios** pour le monitoring en temps réel des équipements réseau.
   - Journaux centralisés sur un serveur Syslog pour analyser les événements.

---

## 🛠️ Fonctionnalités principales
1. **VPN sécurisé** :
   - Tunnel sécurisé entre les deux réseaux internes pour une interconnexion privée.
   - VPN SSL pour les utilisateurs externes.

2. **Wi-Fi sécurisé (DMZ_A2)** :
   - Portail captif pour la gestion des connexions.
   - Isolation des flux Wi-Fi via un VLAN dédié.

3. **Résilience** :
   - Sauvegarde régulière des configurations des équipements réseau.
   - Redondance des connexions entre les zones sensibles.

---

## 🔧 Tests et validations
1. **Scénarios d’attaques simulées** :
   - Test de résistance face à des attaques DoS.
   - Simulation de tentatives de sniffing sur le Wi-Fi.
   - Tests d’intrusion pour valider les politiques de filtrage.

2. **Audit de sécurité** :
   - Utilisation d’outils comme **Nmap** et **Nikto** pour identifier d’éventuelles vulnérabilités.
   - Vérification de la conformité des règles de sécurité mises en place.

---

## 🚀 Conclusion
Ce projet a permis de concevoir une infrastructure réseau segmentée et sécurisée, de mettre en œuvre des politiques de sécurité efficaces et de valider leur robustesse face à des attaques simulées. Une expérience enrichissante pour la gestion de projets en **cybersécurité réseau**.
