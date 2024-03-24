# Documentation de Papillon
Vous pouvez contribuer à la documentation de Papillon via ce dépôt GitHub.

## Ajouter des pages
Le contenu du site est écrit en [**Markdown**](https://docs.github.com/fr/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) et se trouve dans `/docs`.

Le site web est ensuite généré par [MkDocs](https://www.mkdocs.org/) avec le modèle [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/).

Vous pouvez vous aider de la [référence de Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/).

Forkez ce dépôt, faites vos propositions et envoyez une **pull request**. On l'acceptera au plus vite.

## Compiler localement
Pour tester vos changements sur votre ordinateur avant l'envoi:

1. Installez [Python](https://python.org)
	- Sur Windows, cochez l'option pour *ajouter Python au PATH* lors de l'installation
2. Clonez le référentiel et ouvrez un terminal dans le dossier du clone
3. Installez les outils nécessaires avec:
```shell
pip3 install -r requirements.txt
```
4. Démarrez un serveur compilant automatiquement les modifications :
```shell
mkdocs serve
```
