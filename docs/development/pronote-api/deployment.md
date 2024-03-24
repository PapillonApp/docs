# Déploiement
### Pré-requis

Vous devez installer **Python 3.10 minimum** et **PiP**.<br/>
Ensuite installer les dépendances avec les commandes suivantes :

```sh
pip3 install hug -U
pip3 install pronotepy -U
pip3 install lxml
```

## Installation
### Bare-metal
Une fois les pré-requis en place vous pouvez exécuter le serveur avec la commande suivante :
Veuillez noter que le serveur est prévu pour fonctionner sur notre infrastructure, il est donc possible que vous deviez modifier le code pour qu'il fonctionne sur votre propre serveur. De plus, il est **nécessaire** de modifier le fichier `server.py` et de supprimer les fonctions `get_client_on_instances()` et `token_get_client()` ainsi que les appels à ces fonctions *(si présent dans la branche téléchargée)*.
```sh
git clone -b main https://github.com/PapillonApp/papillon-python
cd papillon-python
python -m hug -f server.py
```
*Cela va lancer le serveur sur le port 8000.*

### Docker 
Une fois docker installé sur votre machine, vous pouvez pull l'image docker : 
```sh
docker pull justtryon/papillonserver:latest
```
Une fois cela fait, vous pouvez déployer l'api avec cette commande : 
```sh
docker run -d -p 8000:8000 -e CRON="*/15 * * * *" justtryon/papillonserver:latest
```
*Vous pouvez changer le temps de redémarrage automatique du serveur en changeant la variable d'environnement CRON*

*Cela va lancer le serveur sur le port 8000.*

### Docker Swarm
Le déploiement de l'api avec docker swarm va vous permettre une redondance de l'api, si un de vos serveurs n'est plus disponible, la node manager de votre cluster swarm va automatiquement prendre le relai pour que l'api soit toujours disponible, et ce sans interruption de service pour les utilisateurs.<br/>
Les commandes suivantes sont à exécuter sur la node manager.
```sh
docker pull justtryon/papillonserver:latest
```
Une fois cela fait, vous pouvez déployer l'api sur les différentes nodes en adaptant cette commande : 

```sh
docker service create \
  --replicas 2 \
  --constraint 'node.role==worker' \
  -p 8000:8000 \
  -e CRON="*/15 * * * *" \
  justtryon/papillonserver:latest

```
Le paramètre "replicas" va définir le nombre de nodes sur lesquelles l'api va être déployée, vous pouvez le modifier en fonction de la taille de votre cluster.<br/>
*Vous pouvez également changer le temps de redémarrage automatique du serveur en changeant la variable d'environnement CRON*

*Cela va lancer le serveur sur le port 8000, en tant que service docker.*
