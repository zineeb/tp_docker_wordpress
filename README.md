# Déploiement d'une Architecture 3-Tiers avec Docker Compose pour WordPress

Ce projet utilise Docker Compose pour déployer une architecture 3-tiers comprenant WordPress, MySQL, Redis et Nginx.
Cette configuration assure la scalabilité, les performances et la sécurité en séparant les responsabilités entre
plusieurs services.

## Description de l'Architecture

- **WordPress** : CMS open-source utilisé pour gérer et publier du contenu web. WordPress est configuré pour fonctionner
  avec plusieurs réplicas, assurant ainsi une meilleure disponibilité et répartition de charge.
- **MySQL** : Base de données relationnelle utilisée pour stocker les données de WordPress.
- **Redis** : Système de gestion de base de données en mémoire utilisé comme cache pour améliorer les performances de
  WordPress.
- **Nginx** : Serveur web agissant comme reverse proxy, routant les requêtes des clients vers les instances de
  WordPress. Nginx est le seul point de contact pour les utilisateurs, ce qui améliore la sécurité et la gestion du
  trafic.

## Contenu du Projet

- `docker-compose.yml` : Configure et lance tous les services nécessaires pour l'architecture.
- `init-wp.sh` : Script pour activer le cache Redis une fois que WordPress est démarré.
- `nginx/my_server_block.conf` : Configuration pour le serveur Nginx, qui définit la manière dont les requêtes sont
  routées vers les instances WordPress.
- `.env.example` : Fichier contenant des exemples de configurations pour les variables d'environnement.

## Prérequis

Pour exécuter ce projet, vous aurez besoin de :

- Docker
- Docker Compose

## Mise en Place

1. **Cloner le Répertoire**

   Clonez ce répertoire sur votre machine ou serveur où Docker et Docker Compose sont installés.

   ```bash
   git clone <url_du_repository>
   cd <nom_du_dossier_cloné>
   ```
   
2. **Configurer les Variables d'Environnement**

   Copiez le fichier `.env.example` en `.env` et modifiez-le selon vos besoins.

   ```bash
   cp .env.example .env
   ```

3. **Lancer les Services**

   Utilisez Docker Compose pour démarrer tous les services.

   ```bash
   docker-compose up -d
   ```

4. **Vérifier l'État des Services**

   Assurez-vous que tous les conteneurs fonctionnent correctement.

   ```bash
   docker-compose ps
   ```

5. **Accéder à WordPress**

   Ouvrez un navigateur et visitez http://localhost ou l'adresse IP de votre serveur pour accéder à WordPress.


