# Développer Papillon sous Android

## **Pré-requis**
- Un ordinateur sous :
    - Windows 8 ou ultérieur
    - MacOS 10.14 Mojave ou ultérieur
    - Linux 64 bit qui prend en charge GNU C Library (glibc) en version 2.31
    - Des bases en JavaScript
    - Des connaissances du terminal de Windows

## **Installation des dépendances**

### Node.js
[Node.js](https://nodejs.org) est nécessaire pour installer le reste des outils nécessaires.

Vous pouvez le télécharger sur le site suivant : [https://nodejs.org](https://nodejs.org)

## **Installation**

1. Clonez le repo

```sh
git clone https://github.com/PapillonApp/Papillon.git
```

2. Installez les packages NPM

```sh
npm install
```

## **Développement**

Pour lancer l'application en mode développement, vous devez installer l'application de développement (un mini Expo Go qui permet de charger l'application depuis votre PC avec un live reload)

Il vous faudra aussi télécharger [Android Studio](https://developer.android.com/studio)

Pour commencer :

1- Modifiez le fichier `app.json` afin de modifier le nom de l'application ainsi que son package, pour éviter de remplacer la vraie appli.

- Ligne 3, variable `name`: remplacer par le nom de votre choix (exemple "Papillon Dev").

- Ligne 67, variable `package`: remplacer par `plus.pronote.app.dev`. Ne pas changer cette variable entraînera une erreur à l'installation et un remplacement de l'appli officielle.

2- Exécutez la commande suivante dans votre terminal :
```sh
npx expo prebuild
```

3- Ouvrir Android Studio et ouvrir le dossier Android. 

!!! notes
    Si c'est la première fois que vous lancez Android Studio, de nombreux fichiers se téléchargeront automatiquement et cela prendra plus ou moins de temps en fonction de votre connexion internet.

4- Attendre que Android Studio ai terminé ses processus (visible en bas à droite). 

5- Si le Gradle Sync ne s'est pas automatiquement exécuté, le faire manuellement via Files > Sync project with graddle Files ou en pressant les touches `Ctrl + Maj + O`.

6- Configurer son téléphone pour le développement :  [Comment configurer son téléphone pour le développement](https://developer.android.com/studio/run/device?hl=fr#setting-up)

Une fois que ceci est fait, vous pouvez soit :
    
- Connecter votre téléphone à votre PC via USB : [Comment connecter son téléphone via USB](https://developer.android.com/studio/run/device?hl=fr#connect)
- Connecter votre téléphone via wifi : [Comment connecter son téléphone via wifi](https://developer.android.com/studio/run/device?hl=fr#wireless)
- Créer un émulateur : [Comment créer un émulateur android](https://developer.android.com/studio/run/emulator?hl=fr#avd)

7- Appuyer sur l'îcone "Run" en haut à droite à côté du nom de votre appareil pour démarrer le build et l'installer automatiquement sur votre appareil.

!!! notes
    Vous pouvez consulter le statut du build en vous rendant dans l'onglet "Build" en bas du logiciel, ou dans View > Tool Window > Build.

8- Sur le PC, exécutez la commande suivante dans votre terminal :
```sh
npm start
```

Si ça ne marche pas, il est possible d'exécuter la commande suivante : 
```sh
npx expo start --dev-client
```

9- Lancer l'application de developpement sur le téléphone/émulateur. Le serveur doit automatiquement s'afficher en haut, cliquez dessus pour commencer le chargement. <br>

Si ce n'est pas le cas, vérifiez que :

- Le wifi du PC est en mode privé (visible via les paramètres réseaux).
- Le téléphone et le PC sont connectés au même réseau. Si malgré tout le serveur ne s'affiche pas, un QR Code est généré dans le terminal. Utilisez votre appareil photo pour le scanner.

