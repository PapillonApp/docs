# Pull Request

Les pull requests sont un moyen de contribuer à un projet en apportant des modifications à un dépôt. Elles sont souvent utilisées pour discuter des modifications que vous souhaitez apporter avant de les fusionner dans le dépôt.

## Chez Papillon

Chez Papillon, nous avons une politique de pull request pour les branches de développement. Cela signifie que chaque modification doit être soumise à une pull request avant d'être fusionnée dans la branche de développement.

## Processus de pull request

1. Choisisser la catégorie de la modification
2. Sooummetter votre code pour évaluation
3. Les responsables de la catégorie et de la personne de la coordination évalueront votre code
4. Si votre code est valide, il sera fusionné dans la branche de développement

``` mermaid
stateDiagram-v2
    CE : Code évalué
    RP : Responsable de la catégorie
    PCV : PC valide ?
    RPV : RP valide ?
    PC : Personne de la coordination
    BD : Branche de développement

state PCV <<choice>>
state RPV <<choice>>
state join_state <<join>>

    [*] --> CE

    CE --> RP
    RP --> RPV
    RPV --> join_state : Oui
    RPV --> CE : Suggere des modifications

    CE  --> PC
    PC --> PCV
    PCV --> join_state : Oui
    PCV --> CE : Suggere des modifications

    join_state -->BD : Merge de la demande
```

!!! info ""
    Les pull requests peuvent être refusées si elles ne respectent pas les normes de codage ou si elles ne sont pas valides.

!!! note ""
    Il est inutile de soumettre une pull request si votre code n'est pas prêt à être fusionné. Assurez-vous que votre code est prêt à être fusionné avant de soumettre une pull request.

!!! failure "Harcèlement interdit"
    Il est interdit de harceler les responsables de la catégorie ou la personne de la coordination pour qu'ils fusionnent votre pull request. Ils prendront le temps d'évaluer votre code et de vous donner des retours dèes qu'ils le pourront.