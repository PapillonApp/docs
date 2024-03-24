# papillon-ed-core

`papillon-ed-core` est un module de base pour l'application Papillon. Il contient des classes et des fonctions qui sont utilisées pour récupérer des données, les envoyer à `IndexDataInstance` pour les afficher.

## Installation

!!! npm "Node Package Manager"
     Le module est disponible sur [npmjs.com :octicons-link-external-24:](https://www.npmjs.com/package/papillon-ed-core){target='_blank'} sous le nom de `papillon-ed-core`.

Le répo du module est disponible sur [Github :octicons-link-external-24:](https://github.com/PapillonApp/Papillon-ED-Core/){target='_blank'}.


## Documentation

### Sommaire
- [Installation](#installation)
- [Fonctions](#fonctions)
     - [auth](#auth)
          - [login()](#login)
          - [setToken()](#settoken)


### Installation
```bash
npm i papillon-ed-core
```
> **Note**
> Vous pouvez installer une version spécifique du module via la commande suivante :
```sh
npm i papillon-ed-core@<version>
```

### Fonctions

#### auth
L'étape suivante consiste à se connecter avec un compte EcoleDirecte existant.
Pour cela, deux moyens :

##### login()
**Description:**<br>
Permet de se connecter à EcoleDirecte avec des identifiants.

**Paramètres:**

```javascript
login("identifiant", "mot de passe")
```

**Exemple:**

```javascript
const ED = require("Papillon-ED-Core")
ED.auth.login("identifiant", "mot de passe").then(() => {
    let token = ed._token;
    let prenom = ed.student.prenom

    // ...
})
.catch(err => { //en cas d'erreur à la connexion
    console.log(err)
})
```

##### setToken()
**Description:**<br>

Permet de se connecter à EcoleDirecte avec un token déjà généré.

**Paramètres:**
```javascript
setToken("token", userID)
```

**Exemple:**
```javascript
const ED = require("Papillon-ED-Core")
let ed = new ED()

ed.auth.setToken("token", userID)

//...
```
