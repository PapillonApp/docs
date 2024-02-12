# Image docker pour la documentation de Papillon

## Déploiement classique avec le Dockerfile
```bash
docker build -t papillondoc .
docker run -d -p 8000:8000 --name PapillonDoc papillondoc
```

## Déploiement au sein d'un cluster swarm avec l'image créée précédemment'
```bash
docker stack deploy -c docker-compose.yml PapillonDoc
```
