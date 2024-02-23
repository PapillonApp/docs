## Requêtes

Ensuite, chaque appel à une fonction de l'API doit avoir le paramètre `token` défini. 
Voici la liste des URLs pour obtenir des données :

| URL | Utilité | Paramètres |
|--|--|--|
| `/user` | Obtient les informations sur l'utilisateur (nom, classe...) + les périodes de l'année |  |
| `/timetable` | Affiche l'emploi du temps sur une date donnée | `dateString: str` : date au format **`année-mois-jour`** |
| `/homework` | Affiche les devoirs entre deux dates données | `dateFrom: str` : date de début au format **`année-mois-jour`**, et `dateTo: str` : date de fin au même format |
| `/grades` | Affiche les notes |  |
| `/evaluations` | Affiche les évaluations par compétences |  |
| `/absences` | Affiche les absences |  |
| `/punishments` | Affiche les punitions |  |
| `/news` | Affiche les actualités |  |
| `/discussions` | Affiche les messages |  |
| `/menu` | Affiche les menus entre deux dates données | `dateFrom: str` : date de début au format **`année-mois-jour`**, et `dateTo: str` : date de fin au même format |
| `/recipients` | Liste toutes les personnes que l'utilisateur peut contacter par message |  |

Voici la liste des URLs qui effectuent une simple fonction :

| URL | Utilité | Paramètres | Réponse |
|--|--|--|--|
| `/info` | Envoie des informations sur l'API comme les ENTs et la version |  |  |
| `/export/ical` | Exporte le calendrier en iCal |  | *(l'URL du fichier iCal)* |
| `/homework/changeState` | Change l'état d'un devoir (fait/non fait) | `dateFrom: str` : date de début au format **`année-mois-jour`**, et `dateTo: str` date de fin au même format, et `homeworkId: str` l'id du devoir à changer | *(état du devoir changé)* |
| `/discussion/delete` | Supprime la discussion | `discussionId: str` : Id de la discussion | `ok` si aucun problème |
| `/discussion/readState` | Change l'état de lecture d'une discussion | `discussionId: str` : Id de la discussion | `ok` si aucun problème |
| `/discussion/reply` | Répond à une discussion | `discussionId: str` : Id de la discussion, et `content: str` : Contenu du message | `ok` si aucun problème |
| `/discussion/create` | Crée une discussion | `recipientId: str` : Id du destinataire, `content: str` : Contenu du message et `recipients: list` : La liste de destinataire avec leurs ID (obtenus avec `/recipients`) | `ok` si aucun problème |
