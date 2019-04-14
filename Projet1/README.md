# Projet 1: Un E-Commerce de chaton v2

Bienvenue dans ce premier projet en groupe.

Il reste 10 semaines - une pour les entretiens :

- Projet 1 : 4 semaines, 2 sprints
- Projet 2 : 5 semaines, 2 sprints + 1 brush-up

## Les équipes

Comme d'habitude : Dans le [Google doc](https://docs.google.com/spreadsheets/d/1c8EwpxWJ-tP--hGupPMnG4jrtM3Bm9AWl4Q6CAiU-6s/edit?usp=sharing). Page "Projet 1".

Je ne demande pas spécialement le fait d'avoir un "chef" de groupe, mais d'experience si cette personne n'est pas désignée collégialement au début du projet, elle va apparaitre d'elle même et aura juste moins de légitimité.
Un role de "chef" de groupe serait a mon sens celui d'un scrum master : responsable de s'assurer que la cohésion d'équipe se fasse bien, que les gens discutent des problèmes et que tout le monde suive les règles du projet.

## Le planning

Chaque sprint sera découpé comme tel (le premier sera un peu différent car vous avez pas pu vous préparer).

### 1er Lundi : Kick off

On choisit quelles issues on va faire dans la semaine.
Chaque équipe aura 20 min pour exposer son plan de la semaine (prévu le vendredi passé ;) ) puis on verra ensemble quels sont les points importants à aborder.

### 1er Vendredi : Point technique

Le point ou je mets une casquette de CTO/Expert tech, et où je réponds a vos diverses questions techniques en détail.
N'hésitez pas a me soumettre des sujets en avance. Ca me permettra de donner une meilleure explication.
S'il y a trop de sujets, je choisirai ce qui me semble le plus pertinent.

### 2ème Lundi : Point Management

On parle de ce qui va/ne va pas dans les équipes et de comment on peut mieux s'organiser.
En théorie, ce genre de point pourrait être abordé en tout temps. En vrai, il vaut mieux réserver un slot explicitement prévu à cet effet.
Si tout va bien, on parlera de management en général et d'organisation d'équipe (avec retour d'expérience, tout ça).

### 2ème Vendredi : Point client (Demo) + Review + Tickets

Votre 2ème vendredi sera consacré à faire une démo au client (Moi), et me montrer ce que vous avez fait dans la semaine.
Chaque équipe aura 20 min pour présenter + retours client. Puis on fera une review de la formation (ce qui va/ne va pas/à améliorer).

Point **Important** je me comporterai en client, donc pas la peine de me parler de DB, de tests etc. Je veux voir que mon produit avance et je vous donnerai du feedback.

Ensuite chaque équipe retournera dans son coin pour écrire les user story et les tickets correspondants.

### Tous les jours

Chaque personne devra poster dans slack (pour que les autres tech et moi puissions éventuellement aider) le classique : Aujourd'hui, Demain, Problèmes.

J'encourage vivement les équipes à faire un standup journalier IRL ou en vidéo et avoir ce point de vive voix tous les jours à une heure précise (j'encourage le matin car c'est une bonne façon de démarrer sa journée).
Si c'est le matin les topics sont évidement : hier, aujourd'hui, problèmes.

### Le début d'un projet

Pour le début d'un projet ,les premiers jours se passeront comme tel :

- Jour 1: Configuration de l'app, des outils. Choix du workflow de travail. Mise en place du pipeline, de github, du CI. Choix des heures de réunion et de quelles réunions. Pas de code métier. Juste de la configuration et choix de la méthode de travail.
- Jour 2: Écriture des premières User Story et des specs pour la première semaine. Jusqu'ici, à part la configuration, pas de code.
- Jour 3: On vérifie tout ça et on brush-up ce qui a été fait jour 1 et 2. On essaye de prévoir quels seront les points techniques bloquants/difficiles du projet. On envoie le planning du sprint 1 au gentil @zaratan. Et. Toujours. Pas. De. Code.
- Jour 4: Go.

Oui, je sais que ça peut paraitre lourd. Mais croyez moi, en bout de ligne, vous vous rendrez compte que vous gagnerez du temps.

## Les outils

Libre à vous de choisir comment vous organiser pour vos user stories et tickets.
J'encourage cependant à utiliser Github pour tout.
Chaque projet Github a un onglet "Projet" qui se prête très bien à l'exercice des sprints.

Pour le CI, je conseille CircleCI, mais vous pouvez utiliser autre chose au besoin.

## Le projet

Vous connaissez le concept; Un E-Commerce de chatons. Vous pouvez décider de vendre autre chose si ça vous chante.
Je serai votre client et je vous ajouterai des problématiques si vous n'en avez pas assez.
Pensez à bien design le parcours utilisateur ! (Quand il clique ici, ça fait ça, puis il va sur cette page, etc. Avec tous les cas "d'erreur" et limite)

L'idée est ici de s'attaquer à une problématique que vous connaissez déjà, mais de la traiter de manière professionnelle.

## Les topics

Pour le premier projet, vous allez être guidés dans la configuration et les workflow. Vous pouvez en dévier à vos risques et périls :D (Et je ne ferai peut-être pas de support technique si c'est trop n'imp)

- La [configuration](./configuration/readme.md): C'est un gros morceau. Faites ça bien, prenez le temps tous ensemble de bien comprendre chaque étape et ce à quoi sert chaque outil. Vous pouvez lire de la doc en plus et/ou expérimenter dans votre coin pour chaque outil.
- Le [pipeline](./pipeline/readme.md): Ici rien de très magique. Juste une mise au point.
- Le [workflow](./workflow/readme.md): Le workflow de travail que je conseille pour ce projet.
- Les [specs](./specs/readme.md): De la doc sur comment écrire de belles specs :D
