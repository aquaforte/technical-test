# Technical test - *(Comments & Feedback)*

## - What bugs did you find ? How did you solve these and why ?

- Lors de l'exécution dans un navigateur, la console Javascript de l'outil de développement remonte d'une manière récurrente des erreurs de binding des champs de formulaires (*“A component is changing an uncontrolled input to be controlled”*). Un composant auquel on attribue une valeur `null` ou `undefined` n'est pas contrôlé par React.

- Sur la page d'édition d'un *User*, le bouton *"Update"* n'avait pas d'action sur le handler `onClick`, mais sur `onChange`, ce qui n'avait aucun effet.

- Le `state` de certaines popins de formulaire étaient mises à jour après que la popin soit sortie du DOM (fermeture de la popin ou bien changement de page).

- La popin de création de *User* ne prenait pas en compte le nom à cause d'une erreur de variable (`username` au lieu de `name`), ce qui provoquait la création d'un *User* sans nom.

- La page *Account* ne permettait pas de mettre à jour le champ d'email à cause de l'absence d'un handler `onChange`.

- La liste des *Activités* remontait une erreur de `key` (*"Each child in a list should have a unique “key” prop"*) provoqué par un mauvaise valeur.

- Sur la page d'édition de *Project*, la redirection après validation provoque une erreur à cause d'un paramètre mal formé (`/project/edit/${project?._id}`au lieu de `/project/edit/${id}`). D'autre part, le nom du projet était affiché via un `.toString()` inutile qui provoquait une erreur.


## - Which feature did you develop and why ? 

Quand un utilisateur veut éditer son activité, il ajoute une activité ou bien il contribue à une activité commencée par un autre utilisateur. L'appli ne fait pas la distinction entre les utilisateurs à partir du moment où un projet a été commencé par quelqu'un.
À présent, quand un utilisateur veut déclarer des heures d'activités sur un projet, on est en mesure de savoir qui a travaillé et combien de temps.


## - Do you have any feedback about the code / architecture of the project and what was the difficulty you encountered while doing it ?

La structure du projet est claire et ne pose aucun problème de compréhension. La difficulté est plutôt au niveau ergonomique. Il manque une notion de rôle dans l'entité *User* (`admin` ou `user`), ce qui permettrait de limiter l'action de chaque utilisateur à ses propres données et ainsi ne pas pouvoir modifier les activités des autres. C'est plutôt à ce niveau que le fonctionnement de l'application est un peu déroutante.
Mis à part cet aspect, l'application devrait être facile à améliorer et à enrichir.

