# Agona · Guide de la peer-review (/30)

> Le protocole d'évaluation par les pairs, sur 30 points, pour la journée du j9. Écrit pour les équipes, remis au démarrage de la promotion.

## 0. Avant de commencer

**Les mots du guide.** *Gel* : la version de la base figée par un tag **le j9
à 00h00**, à la fin du j8. Seuls les commits présents au tag comptent, et la base reste
figée pendant les 2 derniers jours du sprint. *j9, j10* : 9e et 10e jours du
sprint. *Livret* : votre dossier individuel de compétences, tenu par le
formateur, consultable à tout moment. *B1 à B3* : les 3 blocs de compétences
du programme. *Registre de décisions (ADR)* : la page où l'équipe évaluée a écrit
ses choix (options, raisons, inconvénients), déposée au gel. *Changement
sonde* : une petite modification imposée, qui mesure ce qu'il en coûte de
modifier la base. *Erreur avalée* : un `try/except` ou `catch` qui attrape
l'erreur et l'ignore. *Relecture de note* : vous pouvez demander par écrit, dans
l'espace, qu'une note soit réexaminée, de la communication des notes, le j10 à
15h30, jusqu'au j1 à 9h00. Le formateur et le suppléant la réexaminent ensemble
avant l'annonce du classement.

**À 9h00 le j9, le formateur publie les bases gelées dans
le dépôt public de la promotion**, depuis son espace, une branche par équipe
(`sprint-N/equipe-K`). Chaque branche est poussée depuis le tag de gel : elle
porte la base telle qu'elle était à la fin du j8. Une base bloquée par le
contrôle du gel n'est pas publiée, et l'espace dit pourquoi.

Le formateur publie au même moment sur le canal de la promotion **l'ordre dans
lequel vous relisez les 4 bases que vous évaluez** et la commande `git clone`
de chaque branche, les 3 éléments à localiser, le changement sonde, et les
4 fiches pré-renseignées (sprint, base, équipe, consignes, rôles à remplir).
Les consignes sont identiques pour les 4 bases : mêmes éléments à localiser,
même changement sonde. Vous commencez seulement quand vous avez cloné les
4 branches et reçu les éléments à localiser, le changement sonde et les fiches.

**Vous travaillez sur vos machines, dans l'environnement de référence de la
promotion** (versions listées, Docker installé, images et dépendances
standard téléchargées la veille). Le formateur a lui-même démarré chaque base
et réalisé le changement sonde avant la publication de 9h00.

**Les fiches** sont les fichiers `peer-review-sprint-N-base-X.md`, une par
base évaluée, dupliqués depuis le gabarit au début de la journée et remis par
le canal de la promotion **avant 17h00 le j9**.

## 1. Pourquoi c'est vous qui notez

À chaque sprint, votre équipe évalue les bases des 4 autres équipes : 30 points
sur les 100 du sprint.

1. **Vous avez résolu le même problème.** Vous savez où étaient les
   difficultés, quels cas limites piégeaient, ce qui était dur à bien faire.
2. **Vous allez peut-être hériter de cette base.** Au sprint suivant, la
   meilleure base devient la base commune. La question de la grille,
   *« voudrais-je hériter de cette base ? »*, vous concerne donc directement.
3. **Relire du code est une compétence** (objectif 8 : évaluer le travail
   d'un pair contre des critères publiés et formuler une critique
   argumentée). La qualité de votre revue est observée au livret (§5),
   séparément des 100 points du sprint.

**Chaque équipe relit les 4 autres bases**, avec les mêmes consignes pour
toutes. Vous ne recevez vos propres notes qu'après avoir rendu vos 4 fiches.
Chaque base reçoit donc 4 fiches indépendantes, et sa note est la médiane des
4 totaux.

## 2. Ce que vous évaluez : la reprenabilité vécue

La revue de code (/35) mesure ce qui est écrit, avec la grille. La soutenance
orale (/35) mesure ce qui est compris. La peer-review mesure ce que **vous
vivez en reprenant la base** : vous faites l'expérience de l'héritage et vous
la racontez. P2 et P4 mesurent l'**effet** des critères de la grille (le temps
qu'il faut pour se retrouver dans la base).

| # | Critère | Points | Ce que ça mesure chez l'équipe évaluée |
|---|---------|:------:|---|
| P1 | Reprise en main | 8 | objectif 5, bloc B2 |
| P2 | Se repérer dans la base | 7 | objectifs 2 et 3, bloc B2 |
| P3 | Le changement sonde | 8 | objectifs 3 et 5, bloc B2 |
| P4 | Confiance : « on en hériterait ? » | 7 | objectif 3, bloc B2 |
| | **Total** | **30** | |

La revue que vous **donnez** mesure, chez vous, l'objectif 8 (blocs B3,
critique argumentée, et B2, revues données).

**Chaque base reçoit 4 fiches, une par équipe évaluatrice**. Sa
note de peer-review est la **médiane des 4 totaux**, après modération du
formateur. Le formateur traite au débrief les écarts entre les 4 fiches.

Chaque critère a 4 niveaux, **maîtrisé / solide / fragile / absent**, et
chaque niveau est décrit par ce que vous devez observer. **Vous retenez le
niveau dont vous observez tout.** Si vous hésitez entre 2 niveaux, prenez le
plus bas et écrivez ce qui manquait pour l'autre. Chaque critère est justifié
sur la fiche par **un fait constaté et une piste d'amélioration**.

### P1 · Reprise en main (/8)

Le binôme P1 clone la branche de la base évaluée et suit **uniquement le README**. Ses
2 membres échangent seulement entre eux. Chacun travaille sur sa machine. On
retient le temps le plus long et ce qui a différé entre les 2.

**Le chrono** démarre à la première commande d'installation ou de démarrage
du README et s'arrête quand l'application répond et que les tests sont verts.
Les téléchargements **imposés par la base** (image, dépendances lourdes)
comptent. Le formateur, qui dispose de sa propre référence, neutralise un
écart entre les 2 membres dû à la connexion plutôt qu'au dépôt. Les
horodatages de début et de fin vont sur la fiche. Si un outil manque sur votre
machine et que le README le liste en prérequis, le chrono est mis en pause le
temps de l'installer, et vous notez la pause. Si le README omet cet outil, le
chrono tourne pendant l'installation. L'intégration continue atteste en plus,
au tag de gel, que les tests passent. P1 mesure les étapes humaines.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 8 | L'application démarre **et** les tests passent, en 10 minutes ou moins, en suivant les commandes du README sans aucune correction |
| Solide | 5 | Démarre et tests verts, mais en 10 à 20 minutes, ou avec 1 ou 2 corrections (variable, commande, version) |
| Fragile | 3 | Démarre ou tests verts, l'un des 2 seulement ; ou plus de 20 minutes ; ou 3 corrections et plus ; ou une base sans tests |
| Absent | 0 | Ni démarrage ni tests en suivant le README |

**Quand la reprise en main dépasse 20 minutes, le chrono s'arrête** et P1 est
noté au niveau atteint. Vous demandez alors au formateur la commande de
démarrage, pour que P2 et P3 se fassent sur une base qui tourne.

### P2 · Se repérer dans la base (/7)

Le formateur a donné **3 éléments à localiser**, choisis dans ce que le sprint
a ajouté ou modifié (par exemple : la règle métier X, la validation des
entrées de la nouvelle route, l'accès à la nouvelle table). L'équipe désigne
**3 chercheurs**, quelle que soit sa taille, hors du binôme P1 si possible.
Chacun cherche **seul et en silence**, et note son temps et son chemin. La
recherche s'arrête à 10 minutes. La fiche porte, pour chaque élément, le temps
médian des 3 et le nombre de chercheurs qui l'ont trouvé (ex. : « 3/3 en
6 min, `src/rules/discount.py` »). Un élément est *trouvé* si au moins 2 des 3
arrivent au même chemin.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 7 | Les 3 éléments localisés, temps médian de 5 minutes ou moins |
| Solide | 5 | Les 3 éléments localisés, temps médian entre 5 et 10 minutes ; ou un élément se trouve à un endroit que le nommage contredit |
| Fragile | 2 | Un élément non localisé dans les 10 minutes, ou éclaté sur 3 fichiers ou plus |
| Absent | 0 | 2 éléments ou plus non localisés dans les 10 minutes |

### P3 · Le changement sonde (/8)

Le formateur a fixé **un petit changement, identique pour toutes les
équipes**, dans le périmètre du sprint : ajouter un champ, modifier une règle,
changer un message. Il est **fictif et sans valeur productive** : il ne
correspond ni au besoin du sprint suivant, ni à une demande de l'entreprise
marraine. Il est consigné au registre de la promotion, avec son objectif
pédagogique, avant le gel. Le formateur l'a réalisé lui-même sur chaque base,
en 5 minutes ou moins. Au-delà de 5 minutes, il l'a remplacé par un
changement de même taille.

Le binôme P3 travaille sur le clone de la branche gelée, **en lecture seule
sur le dépôt évalué**. Il crée une branche locale
(`git checkout -b sonde-<votre-equipe>`), et tout reste en local : la commande
`git push` est proscrite. Le binôme a
**20 minutes chrono** pour réaliser le changement (30 au sprint 1, ou la
fourchette fixée par le formateur au gel), puis 5 minutes pour consigner le
patch et les observations. À la fin du chrono, le binôme s'arrête là où il en
est, et la note porte sur cet état. Le `git diff` (fichier patch) est joint à
la fiche. La branche et le clone sont supprimés après remise. Écrire le test
est facultatif : dites si un test existant a cassé quand vous avez fait le
changement, et sinon dans quel fichier vous l'ajouteriez. Un « test ajouté »
compte seulement s'il figure dans le patch.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 8 | Changement fait en un seul endroit logique ; un test existant a réagi (cassé puis corrigé), ou un test ajouté figure dans le patch ; aucune surprise |
| Solide | 5 | Changement fait, mais 2 endroits touchés qui auraient dû n'en faire qu'un, ou aucun test ne le protège |
| Fragile | 3 | Changement fait avec 3 endroits touchés ou plus ; ou des tests sans rapport ont cassé, mais la cause a été identifiée et corrigée dans le temps imparti |
| Absent | 0 | Pas de patch fonctionnel à la fin du chrono, ou la suite de tests du dépôt reste en échec après le changement |

P1 et P3 sont des **faits**, et le formateur a sa propre référence sur chaque
base. Si votre résultat s'en écarte (par exemple 20 minutes chez vous pour un
changement que le formateur a fait en 5), le formateur corrige au niveau
constaté par sa référence.

### P4 · Confiance : « on en hériterait ? » (/7)

P4 est votre jugement d'ensemble, synthèse assumée de P1 à P3 et de votre
lecture. Il est **obligatoirement ancré** : chaque force et chaque faiblesse
porte un chemin de fichier, et chaque faiblesse une piste. Vous en relevez
autant que vous en constatez. Lisez les **ADR** de l'équipe : une faiblesse
qu'elle y a documentée et assumée se note « assumée ». Une *zone* est un
module ou un dossier.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 7 | Vous pourriez poursuivre le développement immédiatement : les faiblesses relevées sont localisées, comprises et documentées |
| Solide | 5 | Une zone à refaire avant de pouvoir avancer, que vous savez nommer |
| Fragile | 2 | 2 zones ou plus à refaire |
| Absent | 0 | La structure elle-même serait à refaire, et vous savez dire pourquoi |

## 3. Comment vous organiser : la journée du j9

Le code est gelé à la fin du j8. **Le j9 est entièrement consacré à la
peer-review**, le j10 aux soutenances et aux notes. Le classement est annoncé
le j1 à 11h00. La journée s'ouvre par
la démonstration des 5 bases, puis vous relisez les **4 autres bases**, l'une
après l'autre, pendant environ 75 minutes chacune.

| Temps | Quoi |
|---|---|
| 9h00 à 9h40 | **Démonstration des 5 bases**, 8 minutes par équipe : le produit qui tourne, le code fermé. L'entreprise marraine y est invitée |
| 9h40 à 10h00 | Brief du formateur, clone des 4 bases à relire, duplication des 4 fiches, répartition des rôles |
| 10h00 à 11h15 | **Base 1** |
| 11h15 à 12h30 | **Base 2** |
| 13h30 à 14h45 | **Base 3** |
| 14h55 à 16h10 | **Base 4** |
| 16h10 à 17h00 | Relecture des 4 fiches par l'équipe, mise au propre, remise |

**La démonstration ne se note pas.** Chaque équipe dispose de 8 minutes pour
montrer ce que sa base produit : le produit tourne à l'écran, le code reste
fermé. Vous savez ainsi, avant de relire, ce que chaque base est censée faire :
les 20 minutes de démarrage chronométré et les 10 minutes de localisation
mesurent alors l'écart entre ce que vous avez vu tourner et ce que vous
retrouvez dans le code.

**Les 75 minutes d'une base se répartissent en** 20 minutes de démarrage
chronométré (clone, README, lancement, tests), 10 minutes de localisation
des 3 éléments en silence, 20 minutes de changement sonde puis 5 minutes de
consignation du patch et des observations, 10 minutes de verdict collectif et
10 minutes de fiche.

**Les rôles tournent d'une base à l'autre** : sur les 4 bases d'un même
sprint, chacun tient au moins une fois le démarrage et une fois le changement
sonde. Le formateur tient un registre des rôles pour que chacun ait aussi
rédigé au moins une fiche avant le sprint 3.

**Un gardien du temps est désigné pour la journée.**

**L'ordre des bases tourne d'une équipe à l'autre**, et le formateur le publie
au brief : l'équipe A commence par la base B, l'équipe B par la base C, et ainsi
de suite. Avec cette rotation, chaque base est relue une fois en première
position et une fois en dernière.

**Au sprint 1**, comptez 30 minutes de plus sur la première base, le temps de
prendre le protocole en main.

## 4. Comment bien relire

- **Lisez la base comme quelqu'un qui va en hériter** : « si je devais
  continuer à développer dessus lundi, qu'est-ce qui m'arrêterait ? »
- **Partez de la grille de revue** comme liste de contrôle : servez-vous-en
  pour nommer précisément ce que vous voyez (« critère 7 : l'erreur est avalée
  dans `services/order.py` »).
- **Chaque faiblesse vient avec un chemin et une piste**, par exemple :
  « `api/users.js` valide à la main ce que le schéma de validation (Zod,
  Pydantic) ferait ».
- **Cherchez aussi ce qui est mieux que chez vous.** C'est la première ligne
  de la fiche, « ce qu'on reprendrait chez nous ». Reprendre dans votre base,
  au sprint suivant, une idée ou un pattern vu chez l'équipe évaluée est
  autorisé et encouragé, en le citant dans votre README (« repris de la base
  de l'équipe B »). L'autorisation exclut la copie de fichiers entiers.
- **Lisez les ADR pour connaître les intentions de l'équipe.** Si la
  justification manque, notez qu'elle manque : la soutenance tranchera.
- **La base évaluée reste intacte** : vous travaillez sur un clone de la
  branche gelée, la sonde se fait sur une branche locale, et seule la fiche
  est partagée.
- **Les outils d'IA** peuvent vous
  expliquer un fichier ou une commande. Les forces et faiblesses viennent de
  fichiers que vous avez ouverts vous-mêmes. Pendant la peer-review, le
  rapport de l'agent de revue reste au formateur. Au débrief, l'équipe qui a
  écrit une faiblesse jugée pas utile ou pas comprise la défend devant la
  promotion.

## 5. Comment votre revue est observée

La qualité de la revue donnée est une compétence (objectif 8). Elle est
observée au livret, **séparément des 100 points du sprint**. **Chacune de vos
4 fiches** est observée sur 4 observables, à 3 niveaux (oui / partiel / non) :

- **Ancrage** : chaque force et faiblesse porte un chemin qui existe au tag
  de gel.
- **Justesse** : tout écart avec la référence P1/P3 du formateur ou avec la
  base elle-même est expliqué.
- **Utilité** : chaque faiblesse a une piste actionnable, et « ce qu'on
  reprendrait chez nous » cite des éléments concrets.
- **Conformité** : partie partagée anonyme, tous les niveaux justifiés, patch
  joint, remise à l'heure.

La fiche a 2 parties. La **partie partagée** (communiquée à l'équipe
évaluée) est anonyme. La **partie individuelle** (formateur seulement) note
qui a tenu P1, P3, la recherche P2 et la rédaction, ainsi que l'initiale de
l'auteur de chaque force et faiblesse. Cette partie individuelle est la trace
nominative de l'observation de la revue, reportée au livret. Chaque
observation est montrée à l'apprenant dans la semaine, avec droit de
commentaire consigné. Elle est formulée en niveau de compétence, avec le fait
observé (« critique argumentée : fragile, 3 niveaux sans justification
ancrée »).

## 6. Les règles

1. Les **éléments à localiser et le changement sonde sont identiques pour les
   N équipes**. Le formateur les conçoit à partir du brief avant le gel et les
   vérifie sur chaque base au gel. **Seul l'ordre de passage change d'une
   équipe à l'autre**, et il est publié au brief.
2. **Chaque note porte sa justification.** Une fiche dont un niveau manque de
   justification est renvoyée à l'équipe évaluatrice en fin de j9, pour un
   retour avant 9h le j10. Faute de retour, le formateur substitue sa
   référence sur le critère concerné, et le consigne.
3. **La fiche évalue le code** : la partie partagée est
   anonyme, et chaque jugement porte sur la base, qui est collective.
4. **Le formateur a sa propre référence** : il a démarré chaque base et
   réalisé la sonde avant la séance, et il arbitre la grille /35 avant de lire
   les fiches. Sur P1 et P3 (des faits), il corrige au niveau constaté par sa
   référence. Sur P2 et P4 (du jugement), il ajuste d'un niveau au plus et
   motive l'ajustement par écrit. Un écart de 2 niveaux ou plus donne d'abord
   lieu à un échange de 10 minutes avec l'équipe évaluatrice. Une fiche dont
   les justifications manquent d'ancrage dans la base, ou que la base
   contredit (un chemin inexistant, un fait inventé), **est écartée du
   calcul** : la note de la base devient la médiane des 3 fiches restantes.
   **La note de l'équipe évaluée repose sur les seules fiches valables**, et
   l'équipe évaluatrice peut compléter la sienne jusqu'au j10 matin, à son
   initiative. Si 3 fiches ou plus sont écartées sur une même base, le
   formateur note lui-même la base sur les 4 critères. Une fiche qui porte une
   différence d'avis argumentée reste dans le calcul. Tout arbitrage est
   notifié aux 2 équipes avec la fiche publiée. Les 2 équipes disposent d'un
   droit de commentaire sous une semaine, et chaque commentaire est consigné.
   **Les effets de la modération sont uniquement pédagogiques.**

   ⚠ **Une note se modère uniquement sur les faits et les justifications
   produits.**
5. **Le formateur suit la calibration des équipes évaluatrices.** Après chaque
   sprint, il compare la note donnée par chaque équipe à la **médiane des
   3 autres** sur la même base, et suit cet écart d'un sprint à l'autre. Un
   écart systématique, dans un sens comme dans l'autre, signale un problème de
   calibration de l'équipe évaluatrice. Ce problème se traite au débrief, par
   un rappel des descripteurs et un exemple travaillé en commun. **Ce suivi
   sert uniquement à la calibration.**
6. **Un total de 21 à 30 correspond au niveau attendu**, et un total de 12 à
   20 à un niveau en cours. Avec moins de 12 points, ou un niveau « absent »
   après modération, un constat est consigné au livret. L'équipe évaluée peut
   demander une remédiation (réallocation du temps d'encadrement), consignée
   au livret avec le constat, l'objectif et la réévaluation au sprint suivant.
7. **Le j10 à 13h30, l'équipe évaluée reçoit les faiblesses relevées par
   les 4 fiches**, avec le rapport arbitré de l'agent de revue. Elle renvoie,
   entre 14h30 et 15h30, une ligne par faiblesse : utile / pas utile / pas
   compris. La saisie se ferme à 15h30, et une faiblesse sans réponse reste
   marquée « sans réponse ». À 15h30, les 4 fiches modérées lui sont
   transmises complètes, avec les 3 notes. Une demande de relecture
   (procédure du barème oral, règle 11) se dépose ensuite, jusqu'au j1 à
   9h00, et elle est tranchée avant l'annonce du classement. Chaque « pas
   utile » et chaque « pas compris » est repris au débrief.
8. **La fiche est communiquée aux 2 équipes**, conservée au dossier de la
   promotion, et elle accompagne la base sélectionnée à la passation (avec les
   fiches de revue de code et de soutenance). **Elle n'est jamais
   transmise à l'entreprise marraine, ni en extrait ni en synthèse.** Le débrief des peer-reviews se tient hors la présence de
   l'entreprise marraine. La fiche ne conditionne pas la remise du résultat
   et n'en documente pas la qualité.
9. Un **membre absent** est noté « non observé » au livret, et son rôle est
   réattribué. La fiche d'équipe est maintenue dès que 3 membres sont
   présents. Avec moins de 3 membres présents, le formateur fusionne l'équipe
   avec une autre ou substitue sa référence, et le consigne.
10. Une **adaptation** (à l'entrée ou à tout moment) porte sur la personne :
    les seuils de la base restent les mêmes. L'apprenant qui en bénéficie
    tient P1 ou P3 en binôme, et le chrono retenu est celui du binôme. En P2,
    la médiane absorbe l'écart. La timebox de l'équipe est étendue d'un tiers
    (remise tolérée jusqu'à 12h55). L'adaptation est consignée au livret
    seulement.
11. **La séance est enregistrée uniquement sur volontariat strict**, comme le
    prévoit le programme. Par défaut, la fiche écrite, obligatoire, est l'unique
    trace de la séance. Les fiches sont conservées au dossier de la promotion
    pendant la durée fixée dans l'information RGPD remise à l'entrée (même
    durée que les fiches de soutenance).
12. Pour le **calibrage**, au sprint 1, le formateur ou le suppléant déroule
    le protocole complet sur 2 bases. L'écart avec les fiches est analysé et
    consigné au titre de l'amélioration continue.

## 7. Le débrief : la phase réflexive

Le **débrief de peer-review** réunit les 5 équipes et le formateur au j10, de
15h45 à 17h00, hors la présence de l'entreprise marraine. Le débrief est une
phase réflexive, distincte de la pratique : on y analyse ce qui a été fait.

Entre 14h30 et 15h30 le même jour, l'équipe évaluée répond par écrit à chaque
faiblesse reçue : utile, pas utile ou pas compris. La saisie se ferme à 15h30.

Le débrief se déroule en 5 tours de 13 minutes, un par base. Une personne
tirée au sort dans l'équipe évaluée présente les faiblesses que sa base a
reçues et ce que l'équipe en fait. Chaque « pas utile » et chaque « pas
compris » rend la parole à l'équipe qui a écrit la faiblesse, qui la défend.
Une faiblesse restée « sans réponse » est présentée comme les autres.
Le formateur traite au fil des tours les écarts entre les 4 fiches d'une base
et les problèmes de calibration d'une équipe évaluatrice.

Dans les 10 dernières minutes, chaque équipe dit ce qu'elle reprend de la base
qu'elle a relue, le formateur cite les 2 fiches les plus utiles de la promotion
en disant pourquoi, et chacun consigne au livret 3 lignes : « ce que j'ai
appris en relisant une autre base ». Les 3 lignes se complètent jusqu'au samedi
à 00h00.

## 8. La fiche de peer-review (gabarit)

**Partie partagée**
- Une fiche **par base évaluée** (`peer-review-sprint-N-base-X.md`).
- Sprint · base évaluée · équipe évaluatrice · membres présents (émargement)
  · horodatages de début et de remise · mention pré-imprimée : *changement
  sonde : exercice d'évaluation, fictif, branche locale supprimée, rien n'est
  poussé.*
- **Ce qu'on reprendrait chez nous** (3 lignes, en tête).
- **P1** : horodatages début/fin · démarré (oui / non) · tests : verts /
  échouent / absents · corrections apportées (liste) · fait observé · piste
  · niveau (mot) et points.
- **P2** : par élément : temps médian, nombre de chercheurs ayant trouvé,
  chemin · fait observé · piste · niveau et points.
- **P3** : patch joint · changement réalisé (oui / partiel / non) · endroits
  touchés · test : a réagi / ajouté dans le patch / aucun, à ajouter dans
  `...` · surprises · fait observé · piste · niveau et points.
- **P4** : forces (chemins) · faiblesses (chemins et pistes ; « assumée »
  si documentée dans les ADR) · « on en hériterait ? » · niveau et points.
- **Total /30** · seuil atteint / remédiation demandée par l'équipe.
- Bloc modération (formateur) : niveau initial / niveau arbitré / motif ·
  date de communication · retour de l'équipe évaluée par faiblesse.

**Partie individuelle (formateur seulement)** : binôme P1 · 3 chercheurs
P2 · binôme P3 · rédacteur · initiale de l'auteur de chaque force et
faiblesse · observations (ancrage, justesse, utilité, conformité) ·
adaptations et absences (« non observé »).

## 9. Rappel : les 10 critères de la grille de revue

La grille de revue compte 10 critères : 1. Le problème est résolu
(/8) · 2. Lisibilité et propreté (/2) · 3. Nommage (/2) · 4. Structure et
responsabilités (/4) · 5. Duplication et abstraction (/2) · 6. Tests
(/6) · 7. Robustesse et gestion d'erreurs (/4) · 8. Documentation
(/2) · 9. Idiomes du langage et du framework (/2) · 10. Décisions
d'architecture écrites (/3). Le critère 7 (robustesse) passe à 0 dans
3 cas de sécurité : entrée qui devient du code, secret en clair,
authentification contournable. Chaque faille ouvre en plus un malus d'au
plus 5 points, décidé par le formateur. La revue a lieu dans tous les cas,
et la base reste éligible à la sélection. Le reste de l'hygiène de sécurité
est noté au même critère. **Un écart à une règle, justifié par écrit, est
noté comme la règle suivie.** Le détail et les exemples sont dans la grille,
remise avec ce guide.

## 10. À produire avant la première promotion, à affiner après

- Une **fiche exemple remplie** sur une base fictive, avec en face une
  version faible annotée (« ici : pas de chemin », « ici : ressenti sans
  preuve »), et l'évaluation du formateur sur la même base pour se calibrer.
- L'environnement de référence (versions, images pré-tirées) et le gabarit
  de fiche sur le canal de la promotion.
- Calibrer les seuils de temps (10 et 20 minutes) et la durée de séance
  (2h30 au sprint 1) sur de vraies bases. Vérifier que la sonde reste
  faisable sur les bases des sprints 4 et 5.
- Si la première promotion montre des notes stratégiques malgré la
  référence du formateur, sortir le /30 du calcul du rang (retour et livret
  seulement) à la promotion suivante.
