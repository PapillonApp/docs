# Parution dans l'application final (stable)

## Les branches

Papillon a plusieurs branches sur son repo :

- `stable` est la branche dont le publique à accès via les stores. 
- `beta` est la branche de test où les nouvelles fonctionnalités sont testées avant d'être publiées dans la branche stable.
- `developement` est la branche de développement où les nouvelles fonctionnalités sont ajoutées et les bugs sont corrigés.

## Processus de publication

Lorsqu'une nouvelle fonctionnalité est prête à être publiée, elle est fusionnée dans la branche de développement.

Les nouvelles publications sont gérées par l'équipe de coordination. Lorsqu'une nouvelle publication est prête, elle est soumise à une demande de fusion dans la branche bêta. GitHub Actions est utilisé pour automatiser le processus de publication ainsi, la publier sur les stores de test. Une fois que la publication est testée et prête à être publiée, elle est fusionnée dans la branche stable. GitHub Actions est utilisé pour automatiser le processus de publication ainsi, la publier sur les stores.

<center>

``` mermaid
graph TD
    A(Development) -->|Test par les devs| B(Bêta)
    B -->|Publié sur le stores de test| ST(Testflight, Google Play Beta)
    ST -->|Test par le public| C(Stable)
    C -->|Publié sur le store| S(App Store, Google Play)
    S -->|Téléchargé par le public| U(Utilisateurs final)
```

</center>

