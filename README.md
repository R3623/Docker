# Gestion des images
## Télécharger une image depuis Docker Hub.
```bash
docker pull <image>  
```

## Construire une image à partir d’un Dockerfile.
```bash
 docker build -t <nom_image> . 
```

## Lister les images locales.
```bash
docker images
```

# Supprimer une image locale.
```bash
 docker rmi <image>  
```

# Supprimer les images inutilisées.
```bash
docker image prune  
```


##  Gestion des conteneurs
# Lancer un conteneur depuis une image./Exemples d'options : -d, -p, --name, -v
```bash
docker run <options> <image>
```

# Lister les conteneurs en cours.
```bash
docker ps  
```

# Lister tous les conteneurs.
```bash
docker ps -a  
```

# Arrêter un conteneur.
```bash
docker stop <container>  
```

# Démarrer un conteneur.
```bash
docker start <container>  
```

# Redémarrer un conteneur.
```bash
docker restart <container>  
```

# Supprimer un conteneur arrêté.
```bash
docker rm <container>  
```

# Supprimer tous les conteneurs arrêtés.
```bash
docker container prune  
```


##  Commandes pratiques sur les conteneurs
# Exécuter une commande dans un conteneur.
```bash
docker exec -it <container> <commande>
```

# Accéder au terminal du conteneur.
```bash
docker attach <container>
```
# Voir les logs du conteneur.
```bash
docker logs <container>  
```
# Voir les informations détaillées.
```bash
docker inspect <container>  
```
# Copier un fichier du conteneur vers l'hôte.
```bash
docker cp <container>:<chemin_dans_conteneur> <chemin_local>
```  

# Voir les processus en cours.
```bash
docker top <container>  
```

##  Volumes et Réseaux

###  Volumes

# Créer un volume.
```bash
docker volume create <nom>
```

# Lister les volumes.
```bash
docker volume ls
```

# Voir les informations détaillées.
```bash
docker volume inspect <nom>
```

# Supprimer un volume.
```bash
docker volume rm <nom>  
```

# Supprimer les volumes inutilisés.
```bash
docker volume prune  
```

###  Réseaux
# Lister les réseaux.
```bash
docker network ls  
```

# Créer un réseau.
```bash
docker network create <nom>
```

# Voir les informations d'un réseau.
```bash
docker network inspect <nom>  
```

# Connecter un conteneur à un réseau.
```bash
docker network connect <réseau> <container>
```

# Déconnecter un conteneur d’un réseau.
```bash
docker network disconnect <réseau> <container>  
```

##  Exemple Dockerfile – Création d’une image personnalisée
```dockerfile
FROM python:3.10-slim

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["python", "main.py"]
```
