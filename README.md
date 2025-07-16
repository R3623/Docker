# ANDRIANJATOVO
## Ricardo Lantoniaina
### 138/LA/24-25


# Commandes Docker - Essentielles et Avancées

## Gestion des images

### Télécharger une image depuis Docker Hub
```
docker pull <image>
```

### Construire une image à partir d’un Dockerfile
```
docker build -t <nom_image> .
```

### Lister les images locales
```
docker images
```

### Supprimer une image locale
```
docker rmi <image>
```

### Supprimer les images inutilisées
```
docker image prune
```

### Supprimer toutes les images non utilisées (dangling et non dangling)
```
docker image prune -a
```

### Sauvegarder une image en fichier tar
```
docker save -o <nom_fichier>.tar <nom_image>
```

### Charger une image à partir d’un fichier tar
```
docker load -i <nom_fichier>.tar
```

---

## Gestion des conteneurs

### Créer et lancer un conteneur
```
docker run <image>
```

### Créer, nommer, détacher un conteneur avec un port exposé
```
docker run -d -p <port_local>:<port_conteneur> --name <nom_conteneur> <image>
```

### Créer un conteneur avec un volume monté
```
docker run -v <chemin_hote>:<chemin_conteneur> <image>
```

### Créer un conteneur en mode interactif avec terminal
```
docker run -it <image>
```

### Lister les conteneurs en cours d’exécution
```
docker ps
```

### Lister tous les conteneurs (en cours ou stoppés)
```
docker ps -a
```

### Arrêter un conteneur
```
docker stop <id_conteneur>
```

### Démarrer un conteneur arrêté
```
docker start <id_conteneur>
```

### Redémarrer un conteneur
```
docker restart <id_conteneur>
```

### Supprimer un conteneur
```
docker rm <id_conteneur>
```

### Supprimer tous les conteneurs stoppés
```
docker container prune
```

### Renommer un conteneur
```
docker rename <ancien_nom> <nouveau_nom>
```

---

## Réseaux Docker

### Lister les réseaux Docker
```
docker network ls
```

### Créer un réseau
```
docker network create <nom_reseau>
```

### Inspecter un réseau
```
docker network inspect <nom_reseau>
```

### Connecter un conteneur à un réseau
```
docker network connect <nom_reseau> <nom_conteneur>
```

### Déconnecter un conteneur d’un réseau
```
docker network disconnect <nom_reseau> <nom_conteneur>
```

---

## Volumes Docker

### Lister les volumes
```
docker volume ls
```

### Créer un volume
```
docker volume create <nom_volume>
```

### Inspecter un volume
```
docker volume inspect <nom_volume>
```

### Supprimer un volume
```
docker volume rm <nom_volume>
```

### Nettoyer les volumes inutilisés
```
docker volume prune
```

---

## Information Système

### Afficher les informations système Docker
```
docker info
```

### Afficher la version Docker
```
docker version
```

---

## Autres commandes utiles

### Afficher les logs d’un conteneur
```
docker logs <id_conteneur>
```

### Afficher les logs en temps réel
```
docker logs -f <id_conteneur>
```

### Exécuter une commande dans un conteneur en cours
```
docker exec -it <id_conteneur> <commande>
```

### Accéder au shell d’un conteneur
```
docker exec -it <id_conteneur> bash
```

### Copier un fichier du conteneur vers l’hôte
```
docker cp <id_conteneur>:<chemin_fichier> <chemin_destination>
```

### Copier un fichier de l’hôte vers le conteneur
```
docker cp <chemin_fichier> <id_conteneur>:<chemin_destination>
```

---

## Nettoyage général

### Supprimer toutes les ressources inutilisées (volumes, réseaux, images, conteneurs)
```
docker system prune
```

### Supprimer absolument tout (avec confirmation)
```
docker system prune -a --volumes
```

---

## Commandes système (à vérifier avant installation)

### Activer Hyper-V sur Windows
```
dism.exe /online /enable-feature /featurename:Microsoft-Hyper-V-All /all /norestart
```

### Activer Virtual Machine Platform
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

### Activer WSL
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

---

## Gestion des images via Docker Hub (login & push)

### Se connecter à Docker Hub
```
docker login
```

### Pousser une image sur Docker Hub
```
docker push <nom_image>
```

### Récupérer l’ID d’une image
```
docker inspect --format='{{.Id}}' <nom_image>
```

---


