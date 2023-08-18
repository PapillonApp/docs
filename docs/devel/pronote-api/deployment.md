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
Une fois les pré-requis en place vous pouvez executer le serveur avec la commande suivante :
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
