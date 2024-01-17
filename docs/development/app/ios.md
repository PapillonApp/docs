# Développer Papillon sous iOS

## Pré-requis
- [ ] Un ordinateur sous macOS 11 ou ultérieur
- [ ] Des bases en JavaScript 
- [ ] Une connaissance du terminal de macOS

## Installation des dépendances
### Homebrew
[Homebrew](https://brew.sh/) est nécéssaire pour installer le reste des outils nécessaires.

Vous pouvez l'installer simplement en indiquant cette commande dans un terminal macOS :

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
### Node & Watchman
Si ce n'est pas déjà fait, installez Node.js et Watchmen

```sh
brew install node
brew install watchman
```
### Xcode
[Xcode](https://developer.apple.com/xcode/) est nécéssaire pour développer sous iOS. Installez le depuis le [Mac App Store](https://apps.apple.com/us/app/xcode/id497799835?mt=12)

#### Outils de ligne de commande
Vous devez aussi installer les "Command Line Tools".
Ouvrez Xcode, puis dans **Préférences > Locations**, Sélectionnez la version la plus récente de Xcode dans l'onglet "Command Line Tools"
![Screenshot de Xcode](https://reactnative.dev/assets/images/GettingStartedXcodeCommandLineTools-8259be8d3ab8575bec2b71988163c850.png)

### CocoaPods
Pour terminer, il est nécéssaire d'avoir CocoaPods d'installé pour les dépendances de l'app.

```sh
sudo gem install cocoapods
```


## Environnement
Commencez par cloner le  [repo de Papillon](https://github.com/PapillonApp/Papillon) et mettre en place votre environnement de développement.

Une fois le repo cloné, installez simplement les packages npm liés :

```
npm i
```

Il sera aussi nécéssaire d'avoir [**Expo CLI**](https://docs.expo.dev/more/expo-cli/) :

```
npm install -g expo-cli
```

Vous devrez aussi installer les dépendances de [**Cocoapods**](https://cocoapods.org/) dans le dossier *`/ios`*:

```
pod install
```


## Les devbuilds
Pour modifier Papillon et voir vos modifications, un "devbuild" est nécéssaire.

C'est une version spéciale de l'app qui se connecte a votre environnement de développement pour afficher vos changements en temps réel sans avoir a recompiler Papillon.

Pour installer une devbuild, rien de plus simple :

Commencez par **prébuilder** Papillon. On expliquera en quoi cela consiste plus tard. Cette étape est nécéssaire avant chaque compilation de l'app

```
npx expo prebuild
```

Une fois cela terminé, ouvrez Papillon dans Xcode en ouvrant le fichier *`/iOS/Papillon.xcworkspace`*.

Vous n'avez plus qu'a démarrer l'app avec votre iPhone branché ou sur un simulateur iOS en sélectionnant un appareil et **en appuyant sur l'icône "Play" en haut de Xcode**.

### Démarrer une session de développement
Une fois la prébuild installée, démarrez le serveur de développement via la commande suivante :

```
npx expo start
```

*(Vous n'êtes pas obligé de développer sur la même machine que celle qui a compilé la prébuild)*
Une fois la commande démarrée, ouvrez l'app de prebuild sur votre iPhone et indiquez l'adresse du serveur ou alors scannez le QR-Code affiché dans la console depuis l'app Appareil photo

**(Vous devez avoir votre iPhone et votre ordinateur sur le même réseau local)**

## Les prébuilds
La fonction ***`prebuild`*** permet de préparer l'app a être compilée en code natif pour iOS, cela indique :
- Empaqueter les icônes, images, polices, et autres fichiers de l'app
- Installer automatiquement les pods et modules de Papillon
- Mettre a jour certaines parties natives de l'app.

Tout cela se fait simplement et automatiquement avec une commande : 

```
npx expo prebuild
```

Une fois effectuée, vous pouvez archiver ou démarrer l'app comme d'habitude.

## Compiler une version "release"
Normalement, cela n'est pas nécéssaire, mais vous pouvez créer une version release (donc indépendante) telle que vous l'obtiendrez sur l'App Store en utilisant l'option **Archive** sur Xcode.
