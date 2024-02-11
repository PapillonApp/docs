# Envirement de Travail Numérique

## Définition

Un environnement de travail numérique est un ensemble d'outils et de services numériques utilisés pour travailler. Il peut s'agir d'outils de communication, de gestion de projet, de stockage de fichiers, de développement logiciel, etc.

## Chez Papillon
### Compatibilité

Actuellement, l'application Papillon est **compatible** avec les environnements de travail numérique suivants :

- Pronote
- Skolengo
- EcoleDirecte (en cours de développement)

### Interoptabilité

Papillon est conçu pour être **interopérable** avec plusieurs environnements de travail numérique. Cela signifie que Papillon à une architecture modulaire qui permet d'ajouter facilement de nouveaux environnements de travail numérique.

#### Fonctionnement

<center>

``` mermaid
stateDiagram-v2
    
    skapi : Skolengo-API
    EcoleDirecte : Papillon-ED-Core
    

    Pawnote --> IndexDataInstance
    skapi --> IndexDataInstance
    EcoleDirecte --> IndexDataInstance
    ENT --> IndexDataInstance
    

    IndexDataInstance --> View
    View --> Utilisateur
```

</center>

Les environnements de travail numérique sont connectés à Papillon via des modules spécifiques. Ces modules permettent de récupérer les données de l'environnement de travail numérique. Ces données sont ensuite traitées par Papillon pour être affichées à l'utilisateur.

!!! github "À consulter"
    Il est conseillé de consulter [index.ts:pawnote :octicons-link-external-24:](https://github.com/PapillonApp/Renard/blob/pawnote/fetch/index.ts){target='_blank'} sur Github pour comprendre comment les données sont traitées.

### Documentation

Pour chaque environnement de travail numérique, une documentation est disponible. Elle permet de comprendre comment fonctionne l'environnement de travail numérique et comment l'intégrer à Papillon.

- [Pawnote (compatible avec Pronote)](api/pawnote.md)

## Mentions Légales

!!! info ""
    Pronote est une marque déposée de la société [Index Éducation :octicons-link-external-24:](https://www.index-education.com/){target='_blank'}. Papillon et Pawnote ne sont pas affiliés à Index Éducation.

!!! info ""
    EcoleDirecte est une marque déposée de la société [EcoleDirecte :octicons-link-external-24:](https://www.ecoledirecte.com/){target='_blank'}. Papillon n'est pas affilié à EcoleDirecte.

!!! info ""
    Skolengo est une marque déposée de la société [Komos :octicons-link-external-24:](https://www.skolengo.com/fr/mentions-legales){target='_blank'}. Papillon n'est pas affilié à Skolengo.