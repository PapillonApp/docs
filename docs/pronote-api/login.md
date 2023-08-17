Un client doit faire la requête initiale `POST /generatetoken` avec le body suivant :

| Paramètre | Utilité | Exemple |
|--|--|--|
| `url: str(url)` | URL vers l'instance pronote **(avec le eleve.html)** | `https://0152054e.index-education.net/pronote/eleve.html` |
| `username: str` | Nom d'utilisateur **PRONOTE** | `l.martin` |
| `password: str` | Mot de passe en clair | `azertyuiop12345` |
| `ent: str(ent)` | Nom de l'ENT tel que listé [ici](https://github.com/bain3/pronotepy/blob/master/pronotepy/ent/ent.py) | `ac_rennes` |

Le client doit ensuite garder le token généré. Si il ya eu un délai d'au moins 5 minutes entre deux interactions, le client doit regénérer un nouveau token.