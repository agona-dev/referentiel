# Consigne de développement

> Remise aux apprenants au démarrage de la promotion. À lire une fois en entier, puis à garder ouvert pendant les sprints.

## 1. Ce qui se passe pendant un sprint

5 équipes traitent le même sujet, chacune dans son dépôt. À la fin du sprint,
les 5 bases de code sont revues contre une grille que vous avez sous les yeux depuis
le premier jour. **Une base est retenue et devient la base commune : tout le
monde repart de celle-là au sprint suivant.**

Une seule question gouverne tout le reste, la vôtre comme la nôtre :

> **Voudrais-je hériter de cette base au prochain sprint ?**

Au prochain sprint, l'héritage est réel : une seule base continue, les 4 autres
s'arrêtent, et vous avez 4 chances sur 5 de travailler sur du code écrit par une
autre équipe. Toute la consigne en découle.

Chaque semaine, votre équipe a une revue de code formative avec le formateur.
Ses remarques restent dans GitHub, en commentaires de pull request ou en
issues.

## 2. Les 2 règles à connaître avant les détails

**On évalue une base de code.** La grille de revue s'applique à un dépôt, et la
note qu'elle produit porte sur ce dépôt. Votre progression individuelle vit
ailleurs, dans votre livret, et elle vous appartient.

**Un écart écrit vaut autant qu'une règle suivie.** Chaque principe de la
consigne admet un écart. Dupliquer du code, contourner une abstraction ou écrire
une fonction longue peuvent être le bon choix. La seule chose qui sépare une
décision d'une négligence, c'est que la décision soit **écrite quelque part** et
que vous puissiez la défendre.

## 3. De qui vous prenez vos consignes

Le sujet vient d'un besoin réel, apporté par l'**entreprise marraine** de la
promotion. **Vos consignes viennent du formateur.** Il est l'unique
interlocuteur de l'entreprise : c'est lui qui porte le besoin, qui l'explique et
qui l'arbitre.

L'entreprise marraine est invitée à **toutes vos soutenances**, celles de sprint
comme la soutenance finale, ainsi qu'à la démonstration des 5 bases qui ouvre
le j9. Elle y pose ses questions directement, et elle reste à l'écart de la
notation et des notes. **Les échanges avec elle ne sont pas pris en compte dans
votre évaluation.** Elle ne vous donne aucune consigne : le besoin est porté par
le formateur, qui conduit la séance. Vous êtes libres de toute
obligation envers l'entreprise marraine : compte rendu, reporting, accès à quoi
que ce soit.

Si une direction technique vous est malgré tout suggérée, **c'est le formateur
qui tranche** : il porte la règle et recadre sur place.

## 4. Le dépôt : ce qui est déjà en place

Vous partez d'un dépôt modèle : tout y est déjà installé et configuré, et
l'emplacement des fichiers y est fixé.

- **La CI est câblée** : linter, formatter et analyse statique tournent à chaque
  poussée. Ces outils sont un prérequis, comme le fait que le code compile.
  Votre base est évaluée dans l'état où elle est, CI rouge comprise, et l'écart
  pèse sur le rang.
- **Les tests ont leur place** : `tests/unit/`, `tests/integration/`,
  `tests/e2e/`. Vous écrivez ce que vous jugez utile, quand vous le jugez utile.
  On vous demande seulement de le ranger là.
- **Les décisions ont leur place** : `docs/adr/`. La section 6 explique comment
  les écrire.

Les 5 bases suivent ainsi la même structure, et la revue compte les tests par
type dans ces dossiers.

## 5. Ce qu'on attend à la fin d'un sprint

- La **CI est verte**.
- Le projet **démarre en une commande**, sur une machine qui ne connaît rien de
  votre contexte.
- Le **README** dit quoi faire, dans l'ordre, sans supposer qu'on vous a parlé.
- Les **tests** couvrent ce qui porte de la logique métier.
- Les **décisions structurelles du sprint ont leur ADR**.
- Le dépôt est **exempt de tout secret** et de toute donnée réelle.

## 6. Écrire pourquoi

Écrire pourquoi est le seul geste vraiment nouveau pour la plupart d'entre vous.

**Un ADR (architecture decision record)** est un fichier court dans
`docs/adr/`, numéroté, qui fige une décision structurante. Vous en écrivez
autant que vous avez pris de décisions qui engagent la suite. Un ADR suit ce
modèle :

```markdown
# 0004 - Un repository pour l'accès aux commandes

## Contexte
Les requêtes SQL sur les commandes étaient écrites dans les routes HTTP,
ce qui rendait le métier intestable sans base de données.

## Options
1. Laisser en l'état, plus rapide à écrire.
2. Un repository injecté, testable avec un double.
3. Un ORM complet, plus puissant mais plus lourd pour ce périmètre.

## Décision
Option 2.

## Conséquences
Le métier devient testable sans base de données. Un fichier de plus par entité.
Si un jour on a besoin de requêtes complexes, il faudra rouvrir ce choix.
```

Un ADR vaut par ses **options écartées** et ses **conséquences**.

**Pour les choix locaux**, un commentaire suffit, avec un préfixe reconnu :

```python
# pourquoi : duplication assumée. Factoriser avec le calcul de devis
# créerait un couplage entre facturation et commercial pour 3 lignes.
```

Une duplication accompagnée de ces 2 lignes est un choix. La même sans rien
est un oubli.

## 7. Les tests

Les tests permettent à l'équipe suivante de modifier votre code sans le
craindre.

- L'essentiel de vos tests porte sur la **logique métier**, testée sans base de données ni
  réseau.
- Les tests d'intégration vérifient les **contrats** : une route répond ce
  qu'elle annonce, une requête écrit ce qu'elle prétend.
- Quelques tests bout en bout suffisent, sur les parcours qui comptent.
- **Laissez de côté** les accesseurs, les objets de transport et le framework.
- Un test sans assertion utile donne une fausse assurance, et il compte dans une
  couverture qui perd alors son sens.
- **Partez des règles du projet : une règle, un test.** Le pourcentage de
  couverture indique seulement quelles lignes les tests exécutent. L'utilité
  d'un test tient à ce qu'il vérifie.

## 8. Duplication, abstraction, structure

3 pièges sont attendus, et ils vont dans les 2 sens.

- **Sur-factoriser** coûte des points autant que dupliquer. Une interface inutile
  ou une couche d'abstraction créée pour un besoin encore hypothétique donnent
  du travail en plus à l'équipe qui hérite, sans contrepartie. Une abstraction
  se juge à ce qu'elle apporte (isoler une dépendance, rendre un test possible),
  quel que soit le nombre de ses implémentations.
- **Dupliquer** est parfois le bon choix, notamment pour isoler 2 domaines
  qui évoluent séparément. Écrivez pourquoi.
- **Séparer les responsabilités** vaut surtout pour la frontière entre le métier
  et le reste : ce qui décide doit rester indépendant de ce qui affiche et de ce
  qui stocke. C'est cette frontière qu'on regarde.

## 9. Les outils d'IA

Les outils d'IA sont **autorisés**, sans restriction ni déclaration. Piloter ces
outils fait partie du métier aujourd'hui.

L'autorisation a 3 conséquences, à prendre au sérieux :

1. **Vous êtes responsable de ce que vous livrez.** Le code généré est votre
   code. S'il est faux, c'est votre erreur.
2. **Ce qu'on évalue, c'est ce que vous faites de ces outils et ce que vous
   pouvez défendre.** Du code que vous ne savez pas expliquer vaut zéro à la
   soutenance orale, quelle que soit sa qualité apparente.
3. **Relire du code généré est une compétence à part entière.** C'est même
   probablement celle qui vous servira le plus. Traitez une sortie d'agent comme
   une contribution d'un inconnu : lisez-la avant de l'accepter.

L'agent de revue passe aussi sur votre base à chaque fin de sprint. Vous pouvez
lancer l'analyse vous-même avant de rendre : la grille est publiée et les outils
sont autorisés.

## 10. Sécurité : 3 failles, et seulement celles-là

La grille retient 3 failles :

- Une **entrée utilisateur qui devient du code** : requête construite par
  concaténation, commande shell assemblée à la main.
- Un **secret en clair** dans le dépôt ou dans l'historique.
- Une **authentification contournable**.

Avec l'une de ces failles, le **critère 7 de la grille tombe à zéro**, soit 4
points perdus. Le formateur peut en retirer 5 de plus par faille, selon la
gravité de la faille et selon qu'elle était évitable, en motivant sa décision
par écrit. Une base qui porte les 3 failles perd donc **au maximum 19 points sur
35** : 4 pour le critère, 15 de malus. Le total s'arrête à zéro. Avec ou sans
faille, la revue va à son terme et la base reste candidate à la sélection.

Le reste de l'hygiène (image de base non figée, dépendance obsolète) est un
signal noté. Chaque signalement automatique est vérifié par un humain avant
d'avoir la moindre conséquence.

## 11. La publication : votre code sera public

Pendant le sprint, votre dépôt est privé : les 5 équipes travaillent chacune
de leur côté. **Au j9, une fois gelées, les 5 bases sont publiées en open
source, sous licence Apache 2.0, avec leur historique complet.** La
publication précède la peer-review.

La publication a 3 conséquences, à connaître avant votre premier commit.

1. **Vous gardez vos droits d'auteur.** Vous concédez seulement une licence
   d'usage sur ce que vous écrivez.
2. **Vous signez vos commits.** Chaque commit part avec `git commit -s`. C'est
   cette signature qui porte la licence, commit par commit.
3. **Vous commitez toujours sous pseudonyme.** Si vous voulez que votre nom soit
   public, il figure sur la page de la promotion, sur agona.dev, en face de
   votre pseudonyme. La page de la promotion se modifie, alors que l'historique
   Git reste figé : vous pouvez donc changer d'avis dans les 2 sens.

### La configuration à faire au premier jour

- Créez un compte GitHub sous votre pseudonyme. Ce pseudonyme vous suivra
  au-delà de la promotion : choisissez-le comme vous choisiriez un nom
  professionnel.
- Dans `Settings › Emails`, cochez « Keep my email addresses private » et
  « Block command line pushes that expose my email ». La seconde fait refuser
  par GitHub tout envoi qui exposerait votre adresse. Relevez au passage votre
  adresse `@users.noreply.github.com`.
- Configurez Git dans le dépôt de l'équipe :

```
git config user.name "votre-pseudonyme"
git config user.email "ID+pseudonyme@users.noreply.github.com"
git config format.signOff true
```

- Vérifiez avant le premier envoi : `git log -1 --format='%an %ae%n%b'` doit
  afficher votre pseudonyme, l'adresse noreply, et la ligne `Signed-off-by`.
- Le formateur contrôle ces 3 points avant le premier envoi de chaque
  équipe.

Vous repartez avec une preuve vérifiable : un lien vers vos commits montre ce
que vous avez écrit, quand, et ce que vous avez relu chez les autres. Cette
preuve est incontestable, et elle vous reste acquise.

**Le dépôt est publié, historique compris.** Un secret en clair déclenche donc
une **procédure de rotation** : la clé est révoquée et remplacée immédiatement,
et le fait est consigné (section 10). Avant la publication, la valeur est
effacée de l'historique et remplacée par une mention du retrait. L'effacement
garde tous les commits, avec leurs messages, leurs auteurs et leurs dates :
seule la valeur du secret disparaît.

## 12. Comment vous êtes évalués

Chaque sprint est noté sur 100 points, répartis en 3 blocs qui mesurent chacun
une chose différente :

| Bloc | Points | Qui |
|---|:---:|---|
| Qualité de la base | 35 | L'agent de revue instruit, le formateur attribue les points |
| Soutenance | 35 | Le formateur et le suppléant notent chacun sur sa fiche, après vos explications. Votre note est la moyenne des 2 fiches |
| Le regard des pairs | 30 | Les 4 autres équipes reprennent votre base en main et la notent. Votre note est la médiane des 4 fiches |

Les 3 notes sont communiquées le j10 à 15h30, et le classement des 5 bases est
annoncé le j1 suivant à 11h00. À total égal, le regard des pairs départage,
puis la qualité de la base, puis la soutenance. Si tout reste égal, le
formateur tranche par écrit.

## 13. Le droit à l'erreur

Vous pouvez vous tromper, choisir une option qui se révèle mauvaise et le dire,
ne pas savoir, poser une question qu'on juge évidente. Vous pouvez rendre une
base imparfaite en expliquant ce que vous auriez fait avec une semaine de plus.

Ce qui se paie, c'est de ne pas écrire pourquoi, de rendre du code que vous ne
comprenez pas, et de laisser à l'équipe suivante un dépôt qu'elle n'arrive pas
à faire tourner.
