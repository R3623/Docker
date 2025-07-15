
# 📦 Création d'Images Docker

## 🚀 Méthodes de Création

- **Interactivement**  
  Créer un conteneur, y faire les modifications nécessaires, puis sauvegarder sous forme d'image avec `docker commit`.

- **Avec un Dockerfile**  
  Décrire les étapes de création dans un fichier texte, puis construire avec `docker build`.

---

## 📝 Exemple avec Dockerfile

```Dockerfile
FROM ubuntu
RUN apt-get update
RUN apt-get -y install cowsay
```

- `FROM` : Image de base  
- `RUN` : Commande exécutée lors de la construction  

**Construire l'image**  
```bash
docker build -t cowsay .
```

---

## ⚙️ CMD & ENTRYPOINT

- **CMD** : Définit la commande par défaut si aucun argument n'est passé.
- **ENTRYPOINT** : Commande toujours exécutée.  
- Si combinés, `ENTRYPOINT` + `CMD` => la commande est composée.

**Exemple :**
```Dockerfile
ENTRYPOINT ["/usr/games/cowsay", "-e", "%%"]
CMD ["hello world"]
```

---

## 🗂️ Gestion des Couches

- Chaque commande du Dockerfile = nouvelle couche.
- Les couches sont partagées entre les conteneurs.
- Optimisation par **copy-on-write**.

**Voir l’historique d’une image**
```bash
docker history mycowsay
```

---

## 🛠️ Bonnes pratiques

- Mettre les commandes stables en début de Dockerfile (optimisation du cache).
- Utiliser le **build multi-stage** pour des images légères.

**Exemple multi-stage**
```Dockerfile
FROM ubuntu AS builder
RUN apt-get update && apt-get install -y build-essential
COPY hello.c /
RUN make hello

FROM ubuntu
COPY --from=builder /hello /hello
CMD ["/hello"]
```

---

## 🗃️ Publication des images

- **Taguer l’image**
```bash
docker tag mycowsay mydockeraccount/cowsay:latest
```

- **Se connecter**
```bash
docker login
```

- **Publier**
```bash
docker push mydockeraccount/cowsay
```

---

## 📜 Résumé

- Dockerfile = Infrastructure as Code  
- Multi-stage builds pour des images propres  
- Gestion fine des couches et du cache  
- Publication simplifiée via Docker Hub  

---

**Sources :**  
[Documentation Docker](https://docs.docker.com/engine/reference/builder/)  
[Best practices Dockerfile](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
