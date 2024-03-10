# Développer Papillon avec

!!! warning ""
    Ce tutoriel n'est pas complet. Il est en cours de rédaction. Si vous avez des questions, n'hésitez pas à demander sur le [Discord](https://discord.gg/ywkBZx2jFB){target=\_blank}.

    Il ne s'adresse pour l'instant qu'aux développeurs **Android**, mais un tutoriel pour **iOS** est en cours de rédaction.

## **Pré-requis**

-   [x] Un ordinateur sous :
    -   Windows 8 ou ultérieur
    -   macOS 10.14 Mojave ou ultérieur
    -   Linux 64 bit qui prend en charge GNU C Library (glibc) en version 2.31
-   [x] Des bases en JavaScript
-   [x] Des connaissances du terminal de Windows
-   [x] Un compte Expo-EAS

!!! info "Eas, c'est quoi ?"
    EAS ou Expo Application Services est un service cloud qui permet de construire, déployer et gérer des applications Expo ou React Native. Créé par la team derrière le framework Expo, EAS permet dans cette usage, de build une application Papillon gratuitement (même si il existe un plan payant pour des fonctionnalités avancées). Il est à utiliser notamment si vous avez peu de mémoire, de performance ou de stockage mais cela offre moins de flexibilité et de contrôle sur le build.

## **Installation des dépendances**

### Node.js

[Node.js](https://nodejs.org){target=\_blank} est nécessaire pour installer le reste des outils nécessaires.

Vous pouvez le télécharger sur le site suivant : [https://nodejs.org](https://nodejs.org){target=\_blank}

## Environnement

Commencez par cloner le [repo de Papillon](https://github.com/PapillonApp/Papillon){target=\_blank} et mettre en place votre environnement de développement.

Une fois le repo cloné, installez simplement les packages npm liés :

```
npm i
```

Il sera aussi nécessaire d'avoir [**Expo CLI**](https://docs.expo.dev/more/expo-cli/){target=\_blank} ainsi que [**EAS CLI**](https://docs.expo.dev/build/setup/){target=\_blank} :

```
npm install -g expo-cli eas-cli
```

## **Développement**

Pour lancer l'application en mode développement, vous devez installer l'application de développement (un mini Expo Go qui permet de charger l'application depuis votre PC avec un live reload)

Pour commencer :

1- Se connecter à son compte EAS et à son projet

Si vous ne possedez pas de compte EAS, vous pouvez en créer un en suivant ce lien : [Créer un compte EAS](https://expo.dev/signup){target=\_blank}. Ensuite reste à créer un projet EAS en vous rendant dans "Projects" puis "New project". Le nom est libre, mais le `slug` doit être **`papillonvex`**.

Dans votre terminale, vous pouvez ensuite vous connecter via la commande :
```sh
eas login
```

2- Modifiez le fichier **`app.json`** afin de changer le nom de l'application ainsi que son package, pour éviter de remplacer la vraie appli, et enfin le relier à son projet EAS

-   Ligne 3, variable **`name`**: remplacer par le nom de votre choix (exemple "Papillon Dev").

-   Ligne 71, variable **`package`**: remplacer par exemple par **`xyz.getpapillon.app.dev`**. Ne pas changer cette variable entraînera une erreur à l'installation et un remplacement de l'appli officielle.

Rendez-vous sur la page de votre projet EAS, vous y trouverez deux informations utiles, l'ID et l'Owner à recopier dans le fichier **`app.json`**:

-   Ligne 83, variable **`projectId`** (dans `extra` puis `eas`): remplacer par l'identifiant de votre projet EAS. (champ "_ID_" sur la page EAS)

-   Ligne 220, variable **`owner`**: remplacer par votre nom de compte EAS. (champ "_Owner_" sur la page EAS)

!!! warning "Ne pas ajouter dans un commit git ce fichier si vous l'avez modifié de la sorte !"

3- Exécutez la commande suivante dans votre terminal :

```sh
npx expo prebuild
```

4- Créer un build

Pour android :

```sh
eas build --profile development --platform android
```

Et pour iOS :

```sh
eas build --profile development --platform ios
```

Cette commande sert à créer un build de développement, permettant d'offrir les fonctionnalités d'Expo Go.
Cependant, il est possible de créer un build de "production" en remplaçant `development` par `production`.

5- Configurer son téléphone pour le développement avec une application Expo-EAS :

Une fois le build terminé, vous pouvez le télécharger en se rendant sur le lien du deploiement que vous avez reçu dans votre terminal.

Nous vous conseillons de vous envoyer de lien à votre téléphone, et d'y télécharger le fichier APK pour Android, ou le fichier IPA pour iOS et de l'installer.
Pour installer un APK, il vous sera demandé d'activer une option dans les paramètres de votre téléphone, "Installer des applications inconnues".

6- Sur le PC, exécutez la commande suivante dans votre terminal :

```sh
npm start
```

Si ça ne marche pas, il est possible d'exécuter la commande suivante :

```sh
npx expo start --dev-client
```

7- Lancer l'application de developpement sur le téléphone/émulateur. Le serveur doit automatiquement s'afficher en haut, cliquez dessus pour commencer le chargement. <br>

Si ce n'est pas le cas, vérifiez que :

-   Le wifi du PC est en mode privé (visible via les paramètres réseaux).
-   Le téléphone et le PC sont connectés au même réseau. Si malgré tout le serveur ne s'affiche pas, un QR Code est généré dans le terminal. Utilisez votre appareil photo pour le scanner.
