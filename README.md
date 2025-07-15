# 🐳 Commandes Docker Essentielles et Avancées

## 📦 Gestion des images

- `docker pull <image>`  
  Télécharger une image depuis Docker Hub.

- `docker build -t <nom_image> .`  
  Construire une image à partir d’un `Dockerfile` dans le répertoire courant.

- `docker images`  
  Lister les images locales.

- `docker rmi <image>`  
  Supprimer une image locale.

- `docker image prune`  
  Supprimer les images inutilisées pour libérer de l’espace.

---

## 🛳️ Gestion des conteneurs

- `docker run <options> <image>`  
  Lancer un conteneur à partir d’une image.

  Exemples :
  - `-d` : Mode détaché (background).
  - `-p 8080:80` : Redirige le port 80 du conteneur vers le port 8080 local.
  - `--name <nom>` : Nom personnalisé du conteneur.
  - `-v volume:/chemin` : Attache un volume.

- `docker ps`  
  Lister les conteneurs en cours d'exécution.

- `docker ps -a`  
  Lister tous les conteneurs, même arrêtés.

- `docker stop <container>`  
  Arrêter un conteneur.

- `docker start <container>`  
  Démarrer un conteneur arrêté.

- `docker restart <container>`  
  Redémarrer un conteneur.

- `docker rm <container>`  
  Supprimer un conteneur arrêté.

- `docker container prune`  
  Supprimer tous les conteneurs arrêtés.

---

## 🛠️ Commandes pratiques sur les conteneurs

- `docker exec -it <container> <commande>`  
  Exécuter une commande dans un conteneur (ex : bash, sh).

- `docker attach <container>`  
  Se connecter au terminal d’un conteneur déjà en cours.

- `docker logs <container>`  
  Afficher les logs d’un conteneur.

- `docker inspect <container>`  
  Afficher toutes les informations détaillées d’un conteneur.

- `docker cp <container>:<chemin_dans_conteneur> <chemin_local>`  
  Copier un fichier du conteneur vers la machine hôte.

- `docker top <container>`  
  Voir les processus en cours dans un conteneur.

---

## 📂 Volumes et réseaux

### Volumes

- `docker volume create <nom>`  
  Créer un volume Docker.

- `docker volume ls`  
  Lister les volumes.

- `docker volume inspect <nom>`  
  Voir les détails d’un volume.

- `docker volume rm <nom>`  
  Supprimer un volume.

- `docker volume prune`  
  Supprimer les volumes inutilisés.

### Réseaux

- `docker network ls`  
  Lister les réseaux existants.

- `docker network create <nom>`  
  Créer un nouveau réseau.

- `docker network inspect <nom>`  
  Détails sur le réseau.

- `docker network connect <réseau> <container>`  
  Connecter un conteneur à un réseau.

- `docker network disconnect <réseau> <container>`  
  Déconnecter un conteneur d’un réseau.

---

## 🧱 Dockerfile – Création d’images personnalisées

Exemple de Dockerfile :

```dockerfile
# Utilise une image de base officielle
FROM python:3.10-slim

# Définit le répertoire de travail
WORKDIR /app

# Copie les fichiers du projet dans le conteneur
COPY . .

# Installe les dépendances
RUN pip install -r requirements.txt

# Définit la commande de démarrage
CMD ["python", "main.py"]
