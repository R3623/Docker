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

### Connecter un conteneur à un réseau
```
docker network connect <nom_reseau> <nom_conteneur>
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

### Exécuter une commande dans un conteneur en cours
```
docker exec -it <id_conteneur> <commande>
```

### Accéder au shell d’un conteneur
```
docker exec -it <id_conteneur> bash
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

*Fichier généré le 15 juillet 2025 — Commandes utilisées dans la journée*
