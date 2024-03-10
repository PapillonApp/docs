# Développer Papillon sous Android

## **Pré-requis**
- [x] Un ordinateur sous :
    - Windows 8 ou ultérieur
    - macOS 10.14 Mojave ou ultérieur
    - Linux 64 bit qui prend en charge GNU C Library (glibc) en version 2.31
- [x] Des bases en JavaScript
- [x] Des connaissances du terminal de Windows

## **Installation des dépendances**

### Node.js
[Node.js](https://nodejs.org){target=_blank} est nécessaire pour installer le reste des outils nécessaires.

Vous pouvez le télécharger sur le site suivant : [https://nodejs.org](https://nodejs.org){target=_blank}

### Android Studio

[Android Studio](https://developer.android.com/studio) est nécessaire pour développer sous Android.

Vous pouvez le télécharger sur le site suivant : [https://developer.android.com/studio](https://developer.android.com/studio){target=_blank}

!!! tip "macOS"

    Si vous êtes sous macOS, vous pouvez aussi installer Android Studio via [Homebrew](https://brew.sh/){target=_blank}

    ```sh
    brew install --cask android-studio
    ```

## Environnement
Commencez par cloner le  [repo de Papillon](https://github.com/PapillonApp/Papillon){target=_blank} et mettre en place votre environnement de développement.

Une fois le repo cloné, installez simplement les packages npm liés :

```
npm i
```

Il sera aussi nécessaire d'avoir [**Expo CLI**](https://docs.expo.dev/more/expo-cli/){target=_blank} :

```
npm install -g expo-cli
```

## **Développement**

Pour lancer l'application en mode développement, vous devez installer l'application de développement (un mini Expo Go qui permet de charger l'application depuis votre PC avec un live reload)

Pour commencer :

1- Modifiez le fichier **`app.json`** afin de modifier le nom de l'application ainsi que son package, pour éviter de remplacer la vraie appli.

- Ligne 3, variable **`name`**: remplacer par le nom de votre choix (exemple "Papillon Dev").

- Ligne 67, variable **`package`**: remplacer par **`xyz.getpapillon.app.dev`**. Ne pas changer cette variable entraînera une erreur à l'installation et un remplacement de l'appli officielle.

2- Exécutez la commande suivante dans votre terminal :
```sh
npx expo prebuild
```

3- Ouvrir Android Studio et ouvrir le dossier Android. 

!!! notes
    Si c'est la première fois que vous lancez Android Studio, de nombreux fichiers se téléchargeront automatiquement et cela prendra plus ou moins de temps en fonction de votre connexion internet.

4- Attendre que Android Studio ai terminé ses processus (visible en bas à droite). 

5- Si le Gradle Sync ne s'est pas automatiquement exécuté, le faire manuellement via Files > Sync project with graddle Files ou en pressant les touches `Ctrl + Maj + O`.

6- Configurer son téléphone pour le développement :  [Comment configurer son téléphone pour le développement](https://developer.android.com/studio/run/device?hl=fr#setting-up){target=_blank}

Une fois que ceci est fait, vous pouvez soit :
    
- Connecter votre téléphone à votre PC via USB : [Comment connecter son téléphone via USB](https://developer.android.com/studio/run/device?hl=fr#connect){target=_blank}
- Connecter votre téléphone via wifi : [Comment connecter son téléphone via wifi](https://developer.android.com/studio/run/device?hl=fr#wireless){target=_blank}
- Créer un émulateur : [Comment créer un émulateur android](https://developer.android.com/studio/run/emulator?hl=fr#avd){target=_blank}

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

