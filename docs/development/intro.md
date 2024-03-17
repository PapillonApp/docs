# Introduction à Papillon

> Papillon repose sur une architecture de développement moderne et modulaire. Il est conçu pour être facile à utiliser tout en offrant une expérience agréable aux développeurs. En tant qu'agrégateur de données scolaires, Papillon se doit de fournir une expérience développeur optimisée pour son usage.

!!! note warning "Un niveau de connaissance est requis"
    Cette section s'adresse aux développeurs ayant un niveau de connaissance suffisant pour comprendre les concepts de base de React Native et d'Expo.

## Avant de commencer

Papillon est une application basée sur React Native Expo. Il est important de suivre une certaine rigueur lors de la programmation de l'application.

Voici quelques points importants à prendre en compte :

1. Utilisation de React Native Expo : Papillon est construit sur la plateforme React Native Expo, ce qui signifie que vous pouvez utiliser les fonctionnalités et les composants fournis par Expo pour développer l'application.

2. Respect des bonnes pratiques de codage : Il est essentiel de suivre les bonnes pratiques de codage lors de la programmation dans Papillon. Cela inclut l'utilisation de conventions de nommage cohérentes, l'organisation du code en modules réutilisables et la documentation appropriée.

3. Tests et débogage : Assurez-vous de tester régulièrement votre code et de le déboguer pour identifier et résoudre les erreurs. Utilisez les outils de débogage fournis par Expo pour faciliter ce processus.

4. Collaboration et gestion de version : Si vous travaillez en équipe sur le projet Papillon, il est important de suivre les bonnes pratiques de collaboration et de gestion de version. Utilisez un système de contrôle de version tel que Git pour gérer les modifications du code et faciliter la collaboration entre les membres de l'équipe.

En suivant ces lignes directrices, vous pourrez développer efficacement dans l'application Papillon et garantir la qualité du code produit.

## Installer votre environnement de développement

Pour commencer à développer dans l'application Papillon, vous devez d'abord configurer votre environnement de développement. Voici les étapes à suivre pour installer les outils nécessaires :

<div class="cards">
  <a href="/development/app/ios" class="card">
    <span class="material-symbols-outlined">
      iOS
    </span>
    <h3>iOS</h3>
    <p>
        Ainsi que les autres plateformes Apple. Un Mac est nécessaire pour le développement Apple.
    </p>
  </a>
  <a href="/development/app/android" class="card">
    <span class="material-symbols-outlined">
      android
    </span>
    <h3>Android</h3>
    <p>
        Ainsi que les autres plateformes Google. Windows, macOS ou Linux est nécessaire.
    </p>
  </a>
  <a href="/development/app/eas" class="card">
    <span class="material-symbols-outlined">
      cloud_upload
    </span>
    <h3>EAS</h3>
    <p>
      Utiliser Expo Application Services pour développer l'application dans le cloud.
    </p>
  </a>
</div>

Une fois votre environnement de développement configuré, vous pourrez commencer à développer dans l'application Papillon en utilisant les fonctionnalités et les composants fournis par l'équipe de design et de développement.

## Soumettre des modifications

Si vous souhaitez contribuer à l'application Papillon, vous pouvez consulter la [documentation pour les contributeurs](/contribute/intro.md) pour obtenir des informations sur la manière de soumettre des modifications, de signaler des problèmes et de participer à la communauté de développement.


<style>
  @import url('https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined');

  .material-symbols-outlined {
    font-family: 'Material Symbols Outlined';
    font-weight: normal;
    font-style: normal;
    font-size: 24px;  /* Preferred icon size */
    display: inline-block;
    line-height: 1;
    text-transform: none;
    letter-spacing: normal;
    word-wrap: normal;
    white-space: nowrap;
    direction: ltr;
  }

  #_1, h1 {
    visibility: hidden;
  }
  .head_container {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 16px;
    margin-bottom: 24px;
    margin-top: -78px;
  }
  .logo_main {
    width: 60px;
    height: 60px;
  }
  .head_title {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }
  .head_title_1 {
    margin: 0;
    font-size: 1.3em;
    line-height: 1.2;
    font-weight: bold;
  }

  .head_title_2 {
    margin: 0;
    font-size: 1em;
    line-height: 1.2;
    opacity: 0.7;
  }

  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
  }

  .card {
    display: flex;
    flex-direction: column;
    gap: 0px;
    padding: 0px;
    border-radius: 8px;

    background-color: var(--md-admonition-bg-color);
    border: 1px solid var(--md-default-fg-color--lighter);

    text-decoration: none;
    color: var(--md-default-fg-color);

    overflow: hidden;

    box-shadow: 0px 1px 3px #00000055;
  }

  .card:hover {
    box-shadow: 0px 2px 6px #00000055;
    transform: translateY(-2px);
  }

  .card * {
    margin: 0;
    padding: 0;
    text-decoration: none;
    color: var(--md-default-fg-color);
  }

  .card .material-symbols-outlined {
    padding: 10px;
    background-color: var(--md-primary-fg-color);

    height: 80px;

    display: flex;
    align-items: center;
    justify-content: center;
    
    color: #fff;
    font-size: 40px;
  }

  .card_secondary .material-symbols-outlined {
    background-color: var(--md-default-fg-color--lightest);
    color: var(--md-admonition-fg-color);
  }

  .card h3 {
    font-size: 1.1em;
    font-weight: bold;
    text-align: left;
    margin: 12px 12px;
    padding: 0;
    margin-bottom: 8px;
  }

  .card p {
    font-size: 0.85em;
    opacity: 0.8;
    text-align: left;
    margin: 0 12px;
    padding: 0;
    margin-bottom: 12px;
  }
</style>