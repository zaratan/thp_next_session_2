# Projet 2: Un projet pour l'enseignement

Dans ce projet on va essayer d'expérimenter autant que possible les interactions client ainsi que les problématiques de mise en production. De plus, on va faire plein d'Ajax ♥

L'idée est donc de:
* Vous présenter un projet avec des requirements qui vont changer/s'ajouter au cours des 4-5 semaines;
* Mettre votre app en production: Avoir une application en production sur Heroku avec tout le monitoring nécessaire;
* Travailler sur une single-page app et voir des problématiques d'API.

## Le projet

### Le pitch

En tant que professeur, je suis souvent confronté à la problématique de savoir ce que veut ma classe, ce qu'elle a compris et où en sont les différents élèves. Je n'ai pas besoin de le savoir individuellement mais plus de manière globale. Le but est de savoir quelles sont les notions comprises ou non.

Pour ça je propose de faire une app où le professeur pourra prévoir sa classe et suivre en temps réel les besoin de ses élèves.

### Les premières specs

##### Les personas:

* Il y a deux roles, professeur et étudiant.
* Un professeur peut organiser et donner une classe.
* Un étudiant peut participer a une classe.

##### Organiser une classe

Organiser une classe c'est:

* Lui donner un nom et une description. (Et pouvoir les modifier plus tard).
* Avoir des étapes de compréhension de la classe. Par exemple, dans le cadre d'une classe sur le CI:
  * Comprendre ce qu'est CircleCI;
  * Mettre en place sa première configuration;
  * Ajouter rubocop à CircleCI;
  * Ajouter rspec à CircleCI;
  * Ajouter Cypress à CircleCI.
* Chaque étape doit avoir un titre et une description;
* Pouvoir inviter des élèves.

##### Donner une classe

Quand le professeur donne une classe, l'interface devrait lui permettre de:

* Savoir quel élève est connecté;
* Voir quel de pourcentage/nombre d'élèves ont fini une étape (prédéfinie);
* Voir les question posées par les élèves (triées par nombre de vote);
* Supprimer une question (soit parce qu'elle est idiote/troll, soit parce qu'il y a déjà répondu)

##### Suivre une classe

En tant qu'élève, quand je suis une classe, je veux:

* Pouvoir signaler anonymement que j'ai fini une étape;
* Pouvoir poser une question de manière anonyme;
* Pouvoir voter pour une question dont la réponse m'intéresse;
* Voir la progression de la classe.

### Les points importants

* Des fois les élèves auront pas de compte sur la plateforme et ajouter un email devrait inviter l'élève à rejoindre l'app.
* Ça devrait être une app et donc il ne devrait pas y avoir de changement de page. (voir les modes de difficulté plus bas)
* L'information devrait se mettre a jour toute seule sur la page sans que l'utilisateur doive rafraichir sans arrêt

## Mon rôle

Mon rôle au cours de ce projet sera celui d'un vrai client et je répondrai a vos interrogations autant que possible.
N'hésitez pas a me poser des questions quand à l'app de manière publique (des demandes de précision, des validations d'affichage, …) car ces questions intéressent tout le monde.

N'hésitez pas a poser des question en publique aussi si vous avez besoin d'un coup de pouce pour résoudre les quelques défis techniques ;)

## Les deux modes de difficulté

### Rails as a SPA (single page app) 📐

C'est le mode normal et relativement progressif.

L'idée est de mettre en place l'application sans aucun Ajax puis de transférer tout en Ajax petit à petit.

### Rails as an API + React with webpacker ☣

C'est le mode Hardcore difficile.

Rails servira uniquement d'API et webpacker fera le travail de packager l'application React pour vous.

J'ai un expliqué comment ça marche [ici](https://www.zaratan.fr/posts/migrate_from_erb_to_react/).

C'est (très) difficile car il faudra apprendre React et toute la stack JS en même temps.

## La mise en production

Je suis un client sérieux 😆 je veux que mon app soit solide. Je vais donc vouloir en production:

* Que les logs soit propres, lisibles et accessibles même si personne ne les regarde sur Heroku (en effet si jamais quelque chose d'étrange se passe (genre une visite intempestive de pirates chinois à 2h du matin) il faut pouvoir investiguer).
* Avoir un système que référence les différents bugs et permettent les développeurs de comprendre quand ça arrive, a qui et pourquoi.
* Avoir configuré un nom de domaine custom configuré (si il vous manque un domaine, on s'arrangera 😏). (Comme vous allez être en free heroku il n'y aura pas de https mais ce n'est pas grave).
* Heroku doit parler et être pilotable sur/depuis slack.

## Conclusion

Bon courage 💙💚💕💞
