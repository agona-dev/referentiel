# Consigne de développement

> Remise aux apprenants au démarrage de la promotion. À lire une fois en entier, puis à garder ouvert pendant les sprints.

## 1. Ce qui se passe pendant un sprint

Cinq équipes traitent le même sujet, chacune dans son dépôt. À la fin du sprint,
les cinq bases de code sont revues contre une grille que vous avez sous les yeux depuis
le premier jour. **Une base est retenue et devient la base commune : tout le
monde repart de celle-là au sprint suivant.**

Une seule question gouverne tout le reste, la vôtre comme la nôtre :

> **Voudrais-je hériter de cette base au prochain sprint ?**

Ce n'est pas une formule. Au prochain sprint, ce sera littéralement le cas :
une seule base continue, les quatre autres s'arrêtent, et vous avez quatre
chances sur cinq de travailler sur du code que vous n'avez pas écrit. Tout ce
qui suit en découle.

## 2. Deux règles à connaître avant les détails

**On évalue une base de code, pas une personne.** La grille de revue s'applique
à un dépôt. Elle ne produit pas une note sur vous. Votre progression
individuelle vit ailleurs, dans votre livret, et elle vous appartient.

**Un écart écrit vaut autant qu'une règle suivie.** Aucun principe de ce
document n'est un absolu. Dupliquer du code, contourner une abstraction, écrire
une fonction longue : tout cela peut être le bon choix. La seule chose qui
sépare une décision d'une négligence, c'est qu'elle soit **écrite quelque part**
et que vous puissiez la défendre. Une règle appliquée mécaniquement sans
comprendre pourquoi ne vaut pas mieux qu'une règle ignorée.

## 3. De qui vous prenez vos consignes

Le sujet vient d'un besoin réel, apporté par l'**entreprise marraine** de la
promotion. **Elle ne vous donne aucune consigne.** Le formateur est son unique
interlocuteur : c'est lui qui porte le besoin, qui l'explique et qui l'arbitre.

Elle est invitée à **toutes vos soutenances**, de sprint comme en
soutenance finale, ainsi qu'au débrief collectif. Elle y assiste sans prendre
la parole pendant les séquences notées, sans participer à la notation et sans
accès aux notes. **Ses questions sont remises par écrit avant la séance,
identiques pour les cinq équipes, et c'est le formateur qui les pose, en son
nom.** Vous ne lui répondez donc jamais en direct, et vous ne lui devez ni
compte rendu, ni reporting, ni accès à quoi que ce soit.

Si une direction technique vous est malgré tout suggérée, **vous n'avez rien à
trancher** : le formateur porte la règle et recadre sur place.

## 4. Le dépôt : ce qui est déjà en place

Vous partez d'un dépôt modèle. Vous n'avez rien à installer ni à configurer, et
vous n'avez pas à décider où ranger les choses.

- **La CI est câblée** : linter, formateur et analyse statique tournent à chaque
  poussée. Ces outils ne rapportent aucun point : ils sont un prérequis, comme
  le fait que le code compile. Une CI rouge n'empêche pas la revue : votre base
  est évaluée dans l'état où elle est, et l'écart pèse sur le rang.
- **Les tests ont leur place** : `tests/unit/`, `tests/integration/`,
  `tests/e2e/`. Vous écrivez ce que vous jugez utile, quand vous le jugez utile.
  On vous demande seulement de le ranger là.
- **Les décisions ont leur place** : `docs/adr/`. Voir la section 6.

Ces emplacements ne sont pas une préférence esthétique. Les cinq bases doivent
être comparées de la même façon. Si chaque équipe range ses fichiers où elle
veut, compter les tests par type revient à deviner, et la comparaison ne vaut
plus rien.

## 5. Ce qu'on attend à la fin d'un sprint

- La **CI est verte**.
- Le projet **démarre en une commande**, sur une machine qui ne connaît rien de
  votre contexte.
- Le **README** dit quoi faire, dans l'ordre, sans supposer qu'on vous a parlé.
- Les **tests** couvrent ce qui porte de la logique métier.
- Les **décisions structurelles du sprint ont leur ADR**.
- **Aucun secret** dans le dépôt, aucune donnée réelle.

## 6. Écrire pourquoi

C'est le seul geste vraiment nouveau pour la plupart d'entre vous, et c'est
celui qui rapporte le plus.

**Un ADR (architecture decision record)** est un fichier court dans
`docs/adr/`, numéroté, qui fige une décision structurante. **Ni minimum ni
maximum** : vous en écrivez autant que vous avez pris de décisions qui engagent
la suite. Modèle :

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

Ce qui compte : les **options écartées** et les **conséquences**. Une décision
sans alternative n'est pas une décision, c'est un réflexe.

**Pour les choix locaux**, un commentaire suffit, avec un préfixe reconnu :

```python
# pourquoi : duplication assumée. Factoriser avec le calcul de devis
# créerait un couplage entre facturation et commercial pour trois lignes.
```

Une duplication accompagnée de ces deux lignes est un choix. La même sans rien
est un oubli. La différence est réelle, et elle est visible.

## 7. Les tests

C'est ce qui permet à l'équipe suivante de modifier votre code sans le
craindre.

- L'essentiel de vos tests porte sur la **logique métier**, testée sans base de données ni
  réseau.
- Les tests d'intégration vérifient les **contrats** : une route répond ce
  qu'elle annonce, une requête écrit ce qu'elle prétend.
- Quelques tests bout en bout suffisent, sur les parcours qui comptent.
- **Ne testez pas** les accesseurs, les objets de transport, ni le framework.
- Un test sans assertion utile est pire qu'une absence de test : il donne une
  fausse assurance et il compte dans une couverture qui ne veut alors plus rien
  dire.
- **Ne courez pas après le pourcentage de couverture.** Il indique seulement
  quelles lignes ne sont jamais exécutées pendant les tests, pas si vos tests
  vérifient quelque chose d'utile. Partez des règles du projet : une règle, un
  test.

## 8. Duplication, abstraction, structure

Trois pièges attendus, dans les deux sens.

- **Sur-factoriser** coûte des points autant que dupliquer. Une interface qui
  n'apporte rien, une couche d'abstraction créée pour un besoin qui n'existe
  pas encore : c'est du travail en plus pour celui qui hérite, sans
  contrepartie. Une abstraction se juge à ce qu'elle apporte (isoler une
  dépendance, rendre un test possible), pas au nombre de ses implémentations.
- **Dupliquer** est parfois le bon choix, notamment pour isoler deux domaines
  qui évoluent séparément. Écrivez pourquoi.
- **Séparer les responsabilités** vaut surtout pour la frontière entre le métier
  et le reste : ce qui décide ne doit pas dépendre de ce qui affiche ou de ce
  qui stocke. C'est cette frontière qu'on regarde, pas votre capacité à réciter
  cinq lettres.

## 9. Les outils d'IA

Ils sont **autorisés**, sans restriction ni déclaration. Piloter ces outils fait
partie du métier aujourd'hui, et s'en priver ici serait vous préparer à un
monde qui n'existe plus.

Trois conséquences, à prendre au sérieux :

1. **Vous êtes responsable de ce que vous livrez.** Le code généré est votre
   code. S'il est faux, c'est votre erreur, pas celle de l'outil.
2. **Ce qu'on évalue, c'est ce que vous en faites et ce que vous pouvez
   défendre.** Du code que vous ne savez pas expliquer vaut zéro à la soutenance
   orale, quelle que soit sa qualité apparente.
3. **Relire du code généré est une compétence à part entière.** C'est même
   probablement celle qui vous servira le plus. Traitez une sortie d'agent comme
   une contribution d'un inconnu : lisez-la avant de l'accepter.

L'agent de revue passe aussi sur votre base à chaque fin de sprint. Rien
ne vous empêche de la lancer vous-même avant de rendre : la grille est publiée,
les outils sont autorisés, c'est prévu ainsi.

## 10. Sécurité : trois failles, et seulement celles-là

**Ce qu'elles coûtent** : le **critère 7 de la grille tombe à zéro**, soit
quatre points perdus, et le formateur peut en retirer cinq de plus par faille,
en motivant sa décision par écrit, selon la gravité de la faille et selon
qu'elle était évitable. Une base qui porte les trois failles perd donc **au
maximum dix-neuf points sur trente-cinq** : quatre pour le critère, quinze de
malus. Le total ne descend jamais sous zéro. Aucune ne bloque la
revue ni n'écarte la base de la sélection.

- Une **entrée utilisateur qui devient du code** : requête construite par
  concaténation, commande shell assemblée à la main.
- Un **secret en clair** dans le dépôt ou dans l'historique.
- Une **authentification contournable**.

Le reste de l'hygiène (image de base non figée, dépendance obsolète) est un
signal noté, pas un couperet. Et un signalement automatique n'élimine personne :
il est toujours vérifié par un humain avant d'avoir la moindre conséquence.

## 11. La publication : votre code sera public

Pendant le sprint, votre dépôt est privé : les cinq équipes travaillent chacune
de leur côté. **Après les soutenances, les cinq bases sont publiées en open
source, sous licence Apache 2.0, avec leur historique complet.** Les quatre
bases qui ne sont pas retenues sont publiées elles aussi.

Trois conséquences, à connaître avant votre premier commit.

1. **Vous gardez vos droits d'auteur.** Agona ne vous les prend pas. Vous
   concédez une licence d'usage sur ce que vous écrivez, rien de plus.
2. **Vous signez vos commits.** Chaque commit part avec `git commit -s`. C'est
   cette signature qui porte la licence, commit par commit.
3. **Vous commitez toujours sous pseudonyme.** Si vous voulez que votre nom soit
   public, il figure sur la page de la promotion, sur agona.dev, en face de
   votre pseudonyme. Cette page se modifie, l'historique Git non : vous pouvez
   donc changer d'avis dans les deux sens.

### La configuration à faire au premier jour

- Créez un compte GitHub sous votre pseudonyme. Il vous suivra au-delà de la
  promotion : choisissez-le comme vous choisiriez un nom professionnel.
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
- Le formateur contrôle ces trois points avant le premier envoi de chaque
  équipe.

**Ce que ça change pour vous.** Vous repartez avec une preuve vérifiable, pas
une ligne sur un CV. Un lien vers vos commits montre ce que vous avez écrit,
quand, et ce que vous avez relu chez les autres. Personne ne peut vous le
contester, et personne ne peut vous le retirer.

Une conséquence à retenir dès maintenant : **le dépôt est publié, historique
compris**. C'est la raison pour laquelle un secret en clair déclenche une
**procédure de rotation** : la clé est révoquée et remplacée immédiatement, et
le fait est consigné (section 10). Avant la publication, la valeur est effacée
de l'historique et remplacée par une mention du retrait. L'effacement garde
tous les commits, avec leurs messages, leurs auteurs et leurs dates : seule la
valeur du secret disparaît.

## 12. Comment vous êtes évalués

Cent points par sprint, répartis en trois regards qui ne voient pas la même
chose :

| Bloc | Points | Qui |
|---|:---:|---|
| Qualité de la base | 35 | Revue automatique instruite, points attribués par le formateur |
| Soutenance | 35 | Le formateur, après vos explications |
| Le regard des pairs | 30 | Les quatre autres équipes reprennent votre base en main et la notent ; votre note est la médiane des quatre fiches |

Ce qu'il faut retenir de ce tableau : **la majorité des points ne vient ni
d'une machine ni d'une note descendante**. Trente-cinq points viennent de ce
que vous expliquez à l'oral, trente de ce que constatent les quatre autres équipes en
reprenant votre base en main. La grille de revue pèse trente-cinq points sur
cent, et l'agent de revue ne décide de rien : il prépare le travail du formateur.

## 13. Ce qu'on ne vous reprochera jamais

Vous tromper. Choisir une option qui se révèle mauvaise et le dire. Ne pas
savoir. Poser une question qu'on juge évidente. Rendre une base imparfaite en
expliquant ce que vous auriez fait avec une semaine de plus.

Ce qui se paie, c'est de ne pas écrire pourquoi, de rendre du code que vous ne
comprenez pas, et de laisser à l'équipe suivante un dépôt qu'elle n'arrive pas
à faire tourner.
