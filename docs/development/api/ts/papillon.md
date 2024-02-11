## Node.js

!!! npm "Node Package Manager"
    Pour utiliser l'API, vous pouvez utiliser le package npm `papillon-turboself-core` disponible sur [npmjs.com :octicons-link-external-24:](https://www.npmjs.com/package/papillon-turboself-core){target='_blank'}.

Le répo du module est disponible sur [Github :octicons-link-external-24:](https://github.com/PapillonApp/Papillon-Turboself-Core/){target='_blank'}.

## Documentation
### Sommaire
- [Installation](#installation)
- [Gestion des erreurs](#erreurs)
- [Fonctions](#fonctions)
	- [login()](#login())
	- [getUserInfo()](#getUserInfo())
	- [getHome()](#getHome())
	- [getBooking()](#getBooking())
	- [setBooking()](#setBooking())
	- [getHistory()](#getHistory())
	- [getBalance()](#getBalance())
	- [canBookEvening()](#canBookEvening())
	- [getEtabInfo()](#getEtabInfo())

<a name="installation"></a>
### Installation
With NPM :

```bash
npm install papillon-turboself-core
```
<a name="erreurs"></a>
### Gestion des erreurs
Chaque réponse retourner de ce package retourne la même forme de réponse.
```javascript
{
  error: false, //BOOL : Y'a t'il une erreur
  errorMessage: '', //STRING : Raison de l'erreur (vide si il y a pas d'erreur)
  data: {
	...
  }
}
```
<a name="fonctions"></a>
### Fonctions
<a name="login()"></a>
##### login()
**Description:**<br>
Permet de se connecter au service MyTurboself
<br><br>**Paramètres:**<br>
```javascript
login(username, password)
```
**Exemple:**<br>
```javascript
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	let result = await ts.login('username@mail.com', 'Password1234')
	console.log(result)
}

main()
```
**Retour:**<br>
```javascript
{
  error: false,
  errorMessage: '',
  data: {
    token: 'XXXXXXXXXXXX...',
    userId: XXXXXXX,
    etabId: XXXXXX
  }
}
```
<a name="getUserInfo()"></a>
##### getUserInfo()
**Description:**<br>
Obtient les informations de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getUserInfo()
```
**Exemple:**<br>
```javascript
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.getUserInfo()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: {
    id: XXXXXX,
    origId: XXXXX,
    type: 0,
    lastName: 'Doe',
    firstName: 'Jonh',
    class: 'CE1',
    method: 'Argent',
    quality: 'TICKET',
    authorization: {
		pay: true,
		book: true,
		cafeteria: false
	},
    lastSync: '20XX-XX-XXTXX:XX:XX.XXXZ',
    disabled: false,
    isPasswordSecure: true,
    cardData: null
  }
}
```
<a name="getHome()"></a>
##### getHome()
**Description:**<br>
Obtient l'écran d'acceuil de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getHome()
```
**Exemple:**<br>
```json
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.getHome()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: {
    userInfo: {
      id: 'XXXXXXXXXX',
      balance: -10.5,
      estimatedBalance: -150.10,
      estimatedFor: '20XX-XX-XX'
    },
    history: [
      {
        id: XXXXXXXXX,
        name: 'Self',
        date: '20XX-XX-XXTXX:XX:XX.000Z',
        cost: -40.8
      },
      ...
	]
  }
}
```
<a name="getBooking()"></a>
##### getBooking()
**Description:**<br>
Obtient les réservations d'une semaine de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getBooking(date = new Date())
```
**Exemple:**<br>
```json
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.getBooking()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: {
    weekId: 'XXXXXXXXXXX',
    days: [
      {
        id: 'XXXXXXXXXXX',
        dayNumber: 1, //(1: Lundi, 5: Vendredi)
        booked: true,
        lastSyncBooked: 1,
        canEdit: false,
        label: 'Lundi 11 Déc.',
        date: '11-12-2023'
      },
      ...
    ]
  }
}
```
<a name="setBooking()"></a>
##### setBooking()
**Description:**<br>
Défini une réservation de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
setBooking(weekId : Int, dayNumber : Int, booked : Bool)
```
**Exemple:**<br>
```json
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.setBooking(XXXXXXXXXXX, 3 (Mercredi), false)
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: {
	id: 'XXXXXXXXXXX',
	dayNumber: 3,
	booked: false
  }
}
```
<a name="getHistory()"></a>
##### getHistory()
**Description:**<br>
Obtient l'historique complet de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getHistory()
```
**Exemple:**<br>
```json
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.getHistory()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: [
    {
      id: XXXXXXXXX,
      name: 'Self',
      cost: -40.70,
      date: '20XX-XX-XXTXX:XX:XX.XXXZ'
    },
	...
  }
]
}
```
<a name="getBalance()"></a>
#### getBalance()
**Description:**<br>
Obtient le solde de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getBalance()
```
**Exemple:**<br>
```javascript
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.getBalance()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: {
    id: 'XXXXXXXXXX',
    balance: 10.0,
    estimatedBalance: -45.13,
    estimatedFor: '20XX-XX-XX'
  }
}
```
<a name="canBookEvening()"></a>
#### canBookEvening()
**Description:**<br>
Retourne si l'utilisateur connecté peut réserver le soir
<br><br>**Paramètres:**<br>
```javascript
canBookEvening()
```
**Exemple:**<br>
```javascript
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.canBookEvening()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: false
}
```
<a name="getEtabInfo()"></a>
#### getEtabInfo()
**Description:**<br>
Obtient les informations de l'établissement de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getEtabInfo()
```
**Exemple:**<br>
```javascript
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts. getEtabInfo()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
  error: false,
  errorMessage: '',
  data: {
    id: XXXX,
    TSid: 1,
    code2p5: XXXX,
    name: 'Lycée/Collège XXX',
    version: 'XXX',
    disabled: false,
    symbol: '€',
    minCreditAdd: 15.5,
    prixDej: 2.87,
    address: {
      line1: '1 Rue Doe Jonh',
      line2: '',
      postalCode: '10000',
      city: 'Ville connu'
    },
    contact: {
      url: 'http://mon.lycee-ou-college.com/',
      email: 'mail@college-lycee.com',
      tel: '0606060606'
    },
    sync: {
      first: '20XX-XX-XXTXX:XX:XX.XXXZ',
      last: '20XX-XX-XXTXX:XX:XX.XXXZ'
    }
  }
}
```

<a name="getLastPayment()"></a>
#### getLastPayment()
**Description:**<br>
Obtient le dernier paiments de l'utilisateur connecté
<br><br>**Paramètres:**<br>
```javascript
getLastPayment()
```
**Exemple:**<br>
```javascript
const TurboSelf = require('papillon-turboself-core')
let ts = new TurboSelf();

async function main() {
	await ts.login('username@mail.com', 'Password1234')
	let result = ts.getLastPayment()
	console.log(result)
}

main()
```
**Retour:**<br>
```json
{
	error: false,
	errorMessage:'',
	data: {
		id: 0000000,
		etabId: 0000000,
		date: '20XX-XX-XXTXX:XX:XX.XXXZ',
		amount: 20,
		method: 'CB',
		updateDate: '20XX-XX-XXTXX:XX:XX.XXXZ',
		status: 'OK',
		transactionId: 'XXXXXXXXXXXXXX',
		token: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX',
		message: 'Paiement accepté'
	}
}
```