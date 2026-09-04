# Agona · Barème de la soutenance (/35)

> Le barème de l'oral, sur 35 points. Remis aux apprenants au démarrage de la promotion ; la version remise à l'entrée s'applique à toute la promotion.

## 1. Ce que la soutenance évalue

La grille de revue de code mesure **ce qui est écrit**. La soutenance
mesure **ce qui est compris** : la pensée derrière le code, les arbitrages,
la capacité à expliquer son travail devant un regard exigeant, technique ou
non. C'est le volet qui ne se délègue pas : un outil peut produire du code,
il ne répond pas à votre place quand on vous pousse dans vos retranchements
sur votre propre base de code.

Elle vaut **35 points sur 100** à chaque sprint (revue de code /35,
peer-review /30). La note est une note **d'équipe** ; les observations
**individuelles** (critère 3 et porteurs de séquence) alimentent le livret
de chaque apprenant.

Le « besoin » évalué est toujours **le besoin tel que cadré par le formateur au démarrage du sprint**, adapté à des fins
d'apprentissage : jamais l'attente de l'entreprise marraine.

| Critère | Objectif pédagogique | Bloc alimenté |
|---|---|---|
| C1 Compréhension du besoin | objectif 11 | B3 (6 points de l'oral) |
| C2 Arbitrages techniques | objectifs 7 et 12 | B3 |
| C3 Maîtrise de la base | objectif 3 | B2 (observation individuelle) et B3 |
| C4 Démonstration et communication | objectif 7 | B3 |
| C5 Réflexivité | objectif 8, phase réflexive (AFEST) | B3 (collectif ; la rétrospective écrite du livret est individuelle) |

## 2. Les cinq critères et la règle des points

| # | Critère | Points |
|---|---------|:------:|
| 1 | Compréhension du besoin | 6 |
| 2 | Arbitrages techniques | 10 |
| 3 | Maîtrise de la base | 8 |
| 4 | Démonstration et communication | 6 |
| 5 | Réflexivité | 5 |
| | **Total** | **35** |

Quatre niveaux par critère : **maîtrisé / solide / fragile / absent**. Les
points sont **dérivés d'une proportion unique** (100 %, deux tiers, un tiers,
zéro, arrondis à l'entier) : C1 6/4/2/0, C2 10/7/3/0, C3 8/5/3/0, C4 6/4/2/0,
C5 5/3/2/0. Toute retouche future passe par cette règle, pas par des points
posés à la main.

**Règle de décision** : le niveau attribué est le plus élevé dont **toutes**
les composantes sont observées. Entre deux niveaux, on retient l'inférieur et
on écrit ce qui manquait pour le supérieur. Chaque critère est **justifié
par écrit** sur la fiche (fait observé + conseil) : une note non justifiée
n'est pas une note.

## 3. Le détail des critères

### C1 · Compréhension du besoin (/6)

L'équipe a compris le **problème** à résoudre, pas seulement la
fonctionnalité à produire. La note de cadrage du sprint fixe d'avance, pour
les cinq équipes, **3 à 5 contraintes et cas limites attendus** et le
périmètre que le formateur s'attend à voir écarté ; la fiche les
pré-renseigne.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 6 | Reformulation juste du problème ; tous les attendus nommés sauf un au plus ; périmètre écarté assumé et justifié |
| Solide | 4 | Reformulation juste ; deux attendus ou plus manquent |
| Fragile | 2 | L'équipe décrit ce qu'elle a fait, pas le problème qu'elle résout |
| Absent | 0 | L'équipe ne peut pas reformuler le problème, ou le reformule en contradiction avec le cadrage |

### C2 · Arbitrages techniques (/10)

Le cœur de l'exercice. Sur les **thèmes de décision** du sprint (découpage,
modèle de données, bibliothèque, abstraction ou duplication...), fixés et
annoncés **à toutes les équipes en même temps** au début de la matinée, le
formateur déroule les **quatre questions** :

1. **Quelles alternatives avez-vous envisagées ?**
2. **Pourquoi avez-vous choisi celle-ci ?**
3. **Quels sont ses inconvénients ?**
4. **À quelles conditions faudrait-il revoir cette décision ?**

Ce critère existe pour que SOLID, DRY ou un pattern ne soient jamais récités
comme des règles absolues : on évalue le **jugement**. Un choix non
conventionnel bien argumenté vaut plus qu'un choix « propre » que personne ne
sait justifier. Une **alternative réelle** est une option techniquement
viable dans le contexte du sprint, décrite au point de dire ce qu'elle
aurait changé dans le code. Une équipe qui n'en voyait pas et explique
pourquoi se note « fragile », jamais « absent ».

**Notation compositionnelle, cochable pendant la soutenance** : deux thèmes en
sprint (trois en soutenance finale) × quatre questions = 8 cases (12). Une
case vaut 1 si la réponse est spécifique au contexte, 0,5 si elle n'apparaît
qu'à la relance, 0 si elle est générique ou absente.

| Niveau | Pts | Sprint (sur 8) | Soutenance (sur 12) |
|---|:-:|:-:|:-:|
| Maîtrisé | 10 | ≥ 6,5 | ≥ 10 |
| Solide | 7 | 4,5 à 6 | 7 à 9,5 |
| Fragile | 3 | 2 à 4 | 3 à 6,5 |
| Absent | 0 | < 2 | < 3 |

Les **ADR du sprint** (`docs/adr/`, fiches numérotées : contexte,
options, décision, conséquences), déposés au gel du j9, sont lus par le
formateur avant la soutenance ; l'oral vérifie que l'équipe sait les
défendre, et que le code leur correspond. Une justification retenue en C2 peut amener le
formateur à écarter un signalement du rapport de l'agent de revue sur la
grille /35 ; la décision est consignée sur les deux fiches.

*Exemple ancré.* Maîtrisé : « On a hésité entre une table unique avec un
champ type et deux tables ; on a pris deux tables parce que les règles de
validation divergent ; ça coûte une jointure sur la liste ; si un troisième
type arrive, on repasse sur une table unique avec un schéma JSON. » Fragile :
« On a fait deux tables parce que c'est plus propre. »

### C3 · Maîtrise de la base (/8)

Chaque membre peut expliquer **n'importe quelle partie** de la base, y
compris ce qu'il n'a pas écrit lui-même et ce qu'un outil a généré. Ce qui
est dit correspond à ce qui est dans le dépôt.

**Protocole** (8 minutes) :
- **Deux membres** sont désignés par le sort (outil de tirage visible par
  l'équipe, parmi les présents), 4 minutes chacun. Le nombre tiré ne dépend
  pas de la taille de l'équipe. Un **registre de tirage sans remise** est
  tenu sur le parcours : ceux qui n'ont jamais été tirés sont prioritaires,
  chaque apprenant est interrogé au moins une fois tous les deux sprints.
- Les **éléments** sont tirés parmi trois présélectionnés par le formateur
  lors de l'arbitrage du j9, des mêmes catégories pour toutes les équipes
  (une fonction non triviale, un test, une requête ou migration), en visant
  un élément que le membre tiré n'a pas écrit seul (la fiche note s'il en
  est l'auteur). Jamais un fichier au hasard (README, config). « Le chemin
  d'une requête de l'entrée à la base » est réservé à la soutenance finale.
- Le formateur partage lui-même le dépôt gelé sur son écran et navigue à la
  demande du membre interrogé. **60 secondes de lecture silencieuse** avant
  la première question, une question à la fois, reformulée une fois si
  besoin, silence toléré. « Je ne sais pas, mais je chercherais là » compte
  comme partiel : naviguer dans la base est une compétence. Passe de main à
  l'équipe possible après 2 minutes (plafond : solide).
- La question « où est la dette que vous connaissez ? » est **toujours
  posée** ; on note la précision de la réponse (emplacement, conséquence, ce
  qu'il faudrait faire).
- Entraînement : un **mini-tirage de 3 minutes** à chaque revue formative
  hebdomadaire (j2 à j8), hors notation, qui alimente déjà le livret.

| Niveau | Pts | On observe (deux membres interrogés) |
|---|:-:|---|
| Maîtrisé | 8 | Les deux expliquent juste, le discours correspond au dépôt, la dette est localisée avec sa conséquence |
| Solide | 5 | L'un des deux fait une imprécision factuelle mineure (nom, ordre d'appel, valeur) corrigée à la relance, ou passe la main |
| Fragile | 3 | L'un des deux ne sait pas expliquer son élément, ou le discours ne correspond pas au code |
| Absent | 0 | Aucun des deux ne sait expliquer son élément |

**Observation individuelle** : pour chaque membre interrogé, la fiche porte
*maîtrise : oui / partielle / non* avec une ligne de justification. C'est la
**trace nominative de la même observation** que celle qui fonde le niveau
d'équipe, reportée au livret (hors fiche d'équipe partagée).

### C4 · Démonstration et communication (/6)

Ce qu'on mesure : la **présentation**, pas le fonctionnel (déjà noté par la
revue de code) ni les réponses aux questions (C2, C3). La démo tourne sur le
poste de l'équipe, jamais sur la production du programme.

**Protocole** (6 minutes) : 4 minutes de démo, chemin principal puis **un cas
d'erreur tiré par le formateur** dans la liste du brief, identique pour les
cinq équipes ; puis **2 minutes où le formateur joue l'interlocuteur
métier**, à chaque sprint : « je suis le métier, expliquez-moi ce que ça
change pour moi ». La fiche porte la mention *séquence métier : jeu de rôle
pédagogique, fictif, sans suite productive*.

**Repli obligatoire** : un screencast de 3 minutes (chemin principal + cas
d'erreur) est déposé au gel du j9, et l'intégration continue doit avoir passé
le démarrage et un test de fumée. Si la démo échoue en direct : 2 minutes de
diagnostic à voix haute, puis le formateur tranche la cause. **Externe à la
base** (réseau, partage d'écran, poste, plateforme) : on joue le screencast,
aucun effet sur C4. **Interne à la base** : fragile ou absent selon que le
diagnostic est posé ou non ; le diagnostic à voix haute est lui-même une
observation C3 pour le livret.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 6 | Démo complète (chemin principal + cas d'erreur tiré) bouclée dans ses 4 minutes ; explication métier sans terme technique non défini ; limites connues énoncées d'elle-même |
| Solide | 4 | Démo complète ; explication métier qui s'appuie sur du jargon non expliqué, ou limites connues non énoncées |
| Fragile | 2 | Démo partielle, ou échec pour une cause interne à la base diagnostiquée sur le moment |
| Absent | 0 | Échec pour une cause interne à la base, sans diagnostic |

La durée n'est pas notée : le formateur tient le chrono et coupe.

### C5 · Réflexivité (/5)

L'équipe apprend de sprint en sprint. **Règle de preuve** : toute affirmation
doit pouvoir être ancrée dans le dépôt (fichier, commit, PR) ou dans un
moment daté du sprint ; le formateur peut dire « montrez-moi ».

**Sprint 1** : notée sur « appris » et « à refaire », et sur l'écart entre le
plan du j1 et ce qui a été livré. **À partir du sprint 2** : les « retours
précédents » sont ceux reçus par **chaque membre dans son ancienne équipe**
(livret) et les trois fiches de la **base héritée** (revue de code, soutenance
orale, peer-review), transmises avec la passation ; le formateur les a sous
les yeux.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 5 | Au moins deux apprentissages rattachés à un fait précis (commit, bug, retour) ; au moins un retour précédent cité avec l'endroit où il a été traité, ou la raison de ne pas l'avoir fait ; une difficulté de passation nommée avec une proposition |
| Solide | 3 | Apprentissages cités sans fait précis, ou retours cités sans traitement montré |
| Fragile | 2 | Formules générales uniquement (« mieux communiquer ») |
| Absent | 0 | Aucun fait du sprint évoqué, même à la relance |

*Exemple ancré.* Maîtrisé : « On avait reçu "logique métier dans la route"
sur la base héritée : on l'a sortie dans `pricing.py`, commit du mardi ; la
passation a bloqué sur les migrations, on propose un README de reprise avec
l'ordre des commandes. » Fragile : « On a appris à mieux s'organiser. »

## 4. Le déroulé

### En sprint : 30 minutes par équipe, en cinq temps

| | Séquence | Critère |
|---|---|---|
| 01 | **Le besoin** : reformulation, contraintes, périmètre écarté | C1 |
| 02 | **La démo** : chemin principal, cas d'erreur tiré, puis séquence métier | C4 |
| 03 | **Les arbitrages** : deux thèmes, quatre questions, relances | C2 |
| 04 | **Le tirage** : deux membres, un élément chacun | C3 |
| 05 | **La rétro express** : appris, à refaire, héritage | C5 |

L'ordre est fixe et le formateur tient le chrono. Les durées de chaque temps
ne sont pas publiées : elles sont ajustées par le formateur pour que les cinq
équipes reçoivent le même traitement, dans la même enveloppe de 30 minutes.

Les cinq soutenances tiennent sur une matinée, à partir de 8h30, avec une pause
après la troisième équipe. Chaque créneau ménage un temps de transition et un
temps de notation sur fiche après le passage de l'équipe.
**L'arbitrage des rapports de l'agent de revue a lieu la veille** (j9 après-midi), avec la présélection des éléments du tirage : le
formateur arrive en connaissant chaque dépôt.

- Les thèmes d'arbitrage du jour sont annoncés à 8h30 à toutes les équipes
  en même temps ; l'ordre de passage est tiré au sort et publié la veille.
- Les soutenances sont **ouvertes aux autres équipes** (on apprend des cinq
  architectures) ; la séquence de tirage peut se tenir en comité restreint à
  la demande d'un apprenant. Les équipes en attente rédigent leur
  rétrospective écrite et relisent les bases des autres.
- **Porteurs de séquence** : au début de la soutenance, le formateur désigne le
  porteur de chaque séquence (pas l'équipe), en veillant à ce que chaque
  apprenant porte C2 ou C4 au moins une fois avant la soutenance ; toute
  question peut être redirigée vers n'importe quel membre. La fiche note les
  séquences portées par chaque membre présent et une ligne d'observation.
- Les notes sont arrêtées **à chaud** sur la fiche pré-imprimée, puis
  **relues en bloc** (15 minutes d'harmonisation) avant publication
  l'après-midi ; un ajustement d'un niveau au plus est possible, motivé par
  écrit. Le débrief collectif revient sur les arbitrages les plus
  instructifs.
- **L'entreprise marraine est invitée aux soutenances de sprint**, dans le même
  régime qu'en soutenance finale : comme **invitée métier**, sans prise de
  parole pendant les séquences notées, sans participation à la notation et
  sans accès aux notes. Ses questions, remises par écrit au formateur avant
  la séance et **identiques pour les cinq équipes**, sont posées ou non par le
  formateur, en son nom. Elle est également invitée au **débrief collectif de
  l'après-midi** : démonstration de la base sélectionnée, architectures
  comparées, apprentissages du sprint, sans question directe aux apprenants.

### En soutenance finale : 45 minutes par équipe, devant le jury

Même structure, temps allongés (démo 10 min, trois thèmes d'arbitrage
15 min, tirage sur deux membres avec « le chemin d'une requête »).

- **Le jury** est composé du **formateur-évaluateur, qui le préside**, et
  d'un **second évaluateur pédagogique** (un formateur suppléant, ou un expert indépendant de l'entreprise marraine).
- **L'entreprise marraine n'est pas membre du jury : elle est invitée**,
  comme **invité métier**, sans prise de parole pendant les séquences notées.
  Ses questions, remises par écrit au formateur avant la séance, identiques
  pour les cinq équipes, sont posées ou non par le formateur, en son nom,
  uniquement sur la compréhension du métier (C1). La séquence de tirage (C3)
  se tient hors sa présence.
- **La base présentée est gelée avant la soutenance et remise en l'état.**
  La remise du résultat n'est conditionnée ni au résultat de la soutenance
  ni à l'appréciation de l'entreprise ; aucune demande de modification ne
  peut en découler. Ses remarques sont consignées par le formateur au bilan
  de promotion et à la note de cadrage suivante, jamais transmises aux
  équipes comme tâches.
- La note de soutenance alimente l'appréciation par bloc et l'attestation ;
  elle n'entre pas dans le cumul indicatif des sprints.

## 5. Du score à l'appréciation

- **Par sprint, pour l'équipe** : 24 à 35 = niveau attendu ; 14 à 23 = en
  cours ; **moins de 14, ou un critère « absent »** = constat consigné au
  livret. **La remédiation se fait à la demande de l'équipe** : réallocation
  du temps d'encadrement, consignée au livret :
  constat, objectif, moyens, réévaluation à la soutenance suivante.
- **En fin de parcours, pour l'apprenant (bloc B3)** : *acquis* si au moins
  deux observations C3 « oui » dont aucune « non » sur les deux derniers
  sprints, et au moins une séquence C2 ou C4 portée à « solide » ou mieux ;
  *non acquis* si la dernière observation C3 est « non » et qu'aucune
  séquence n'a été portée ; *en cours d'acquisition* sinon. Aucune
  appréciation de bloc n'est fondée sur moins de deux observations C3.
- Ces seuils sont **à calibrer après la première promotion** ; ils sont
  publiés tels quels à l'entrée et ne changent pas en cours de promotion.

## 6. Les règles

1. **Tout est publié à l'entrée** : critères, niveaux, déroulé, banque de
   questions, fiche de notation. Aucune question piège hors du périmètre
   enseigné (référentiel commenté, ateliers tenus, retours de revue
   formative consignés) ; les questions-mères viennent de la banque, les
   relances sont libres dans ce périmètre.
2. **Mêmes thèmes de décision, mêmes catégories d'éléments, même cas
   d'erreur** pour les cinq équipes d'un même sprint ; les choix, eux,
   diffèrent, c'est le but.
3. **Les outils d'IA sont autorisés** pour produire le code. La soutenance
   est précisément le lieu où l'on vérifie que le code produit est compris :
   ne pas savoir expliquer une partie générée, c'est C3 en « fragile » ou
   « absent », exactement comme pour du code écrit à la main.
4. **On évalue la démarche et la compréhension, jamais la forme** : la forme
   linguistique (accent, grammaire, recherche de mots, recours à un terme
   anglais) n'entre pas dans la note ; une réponse peut être donnée en
   montrant le code ou un schéma ; l'hésitation ne compte pas.
5. **Chaque note est justifiée par écrit** sur la fiche, transmise à
   l'équipe le jour même. L'observation individuelle C3 est montrée à
   l'apprenant dans la semaine, avec droit de commentaire consigné ; le
   livret est consultable par l'apprenant à tout moment. Les fiches et
   observations sont conservées au dossier de la promotion pendant la durée
   fixée dans l'information RGPD remise à l'entrée (proposition : cinq ans
   après la fin de la promotion, à confirmer avec le conseil juridique).
   **Les soutenances sont enregistrées**, pour le livret et l'usage pédagogique
   interne. Toutes les sessions se tenant à distance, la caméra reste
   facultative. L'apprenant qui ne souhaite pas être enregistré passe en fin
   de séance, enregistrement coupé, et sa soutenance se déroule à l'identique.
   Rien n'est publié sans consentement explicite. **La fiche écrite reste
   l'unique trace évaluative** : l'enregistrement sert le livret et la
   relecture, jamais la note.
6. **Confidentialité** : notes, justifications, classement des bases et observations
   individuelles sont communiqués à l'équipe et à l'apprenant concerné, et
   archivés. **L'entreprise marraine n'en reçoit aucun**, ni individuel ni
   collectif ; elle reçoit en fin de promotion un bilan pédagogique agrégé,
   sans donnée nominative.
7. **Aucune conséquence disciplinaire** : la soutenance classe des
   apprentissages et nourrit le livret. La remédiation (§5) intervient à la
   demande de l'équipe.
8. **Absence** : un membre absent est retiré du tirage ; son livret porte
   « non observé » (distinct de « non ») et il est tiré d'office à la
   soutenance suivante. La note d'équipe n'est pas modifiée ; la soutenance est
   maintenue dès qu'un membre est présent. La justification de l'absence
   relève de l'assiduité (règlement), pas du barème.
9. **Le tirage est le protocole, pas une option** : si le membre désigné ne
   répond pas, ou si l'équipe substitue un volontaire, l'élément est réputé
   non expliqué (C3 se constate) et le livret porte « non observé : refus ».
   Ce n'est pas une sanction, c'est une absence d'observation ; elle
   déclenche un entretien avec le formateur. Une adaptation se demande avant
   la soutenance, jamais pendant.
10. **Adaptations** : demande recevable à l'entrée **ou à tout moment du
    parcours** (handicap, situation particulière) ; adaptations possibles :
    temps majoré d'un tiers, questions de la banque remises par écrit,
    réponse en montrant le code, pause, séquence de tirage en petit comité,
    interprète LSF, support visuel. L'adaptation est consignée au livret
    seulement, jamais sur la fiche d'équipe ; le temps d'équipe est étendu
    d'autant sans pénalité ; au-delà des moyens du programme, orientation
    vers Ressources Handicap Formation.
11. **Relecture de note** : demande écrite sous cinq jours ouvrés ; relecture
    par le formateur avec le suppléant (ou un senior externe) sur la base de
    la fiche ; réponse écrite sous quinze jours ; issue archivée au dossier
    de la promotion. Distincte de la réclamation du règlement du programme.
12. **Calibrage et suivi** (révisé le 27/08) : le suppléant **assiste aux
    soutenances de chaque sprint**, afin de juger en soutenance finale une
    trajectoire qu'il a suivie et non un seul instantané. Au sprint 1, il
    double la notation du formateur sur les cinq soutenances. **À mi-parcours,
    il re-note deux soutenances** pour mesurer la dérive de la grille, celle-ci
    ayant été calibrée sur le sprint le moins représentatif du parcours. Les
    écarts sont analysés et consignés au titre de l'amélioration continue.

## 7. Comment se préparer (pour les équipes)

- Chaque membre **lit tout le dépôt** avant le j10 : n'importe qui peut être
  interrogé sur n'importe quoi.
- Les **ADR du sprint** (`docs/adr/`) sont à jour au gel du j9.
- Le **screencast de repli** (3 minutes) est déposé au gel.
- L'équipe relit la **fiche de revue de la base héritée** et les retours
  individuels reçus par chacun.
- On répète la **séquence métier** : expliquer le sprint sans un seul terme
  technique.

## 8. Banque de questions (publiée)

Règle de preuve : toute réponse doit pouvoir être ancrée dans le dépôt ou
dans un moment daté du sprint ; le formateur peut dire « montrez-moi ».

**C1 · Besoin** : « Reformulez le problème en une phrase, sans parler de
technique. » « Quel cas limite vous a posé le plus de questions ? » « Qu'avez-
vous volontairement laissé de côté, et pourquoi ? » « Si le besoin était mal
compris, où le verrait-on dans votre code ? »

**C2 · Arbitrages** : les quatre questions, appliquées aux thèmes du jour.
Relances : « qu'est-ce qui vous aurait fait choisir l'autre option ? »,
« qu'est-ce que ce choix coûtera au prochain sprint ? », « montrez-moi
l'endroit du code où ce choix se voit. »

**C3 · Maîtrise** : « Que fait cette fonction, et que se passe-t-il si on la
supprime ? » « Pourquoi ce test existe-t-il, que protège-t-il ? » « Cette
partie a été générée ou écrite à la main ? Qu'est-ce que vous y avez
changé ? » « Où est la dette que vous connaissez ? » (toujours posée).
Soutenance finale : « Montrez-moi le chemin d'une requête, de l'entrée à la
base de données. »

**C4 · Séquence métier** (le formateur joue le métier, jeu de rôle
pédagogique) : « Expliquez-moi ce que ça change pour moi, sans mot
technique. » « Quelles limites connues de votre solution expliqueriez-vous à
un utilisateur, et où sont-elles documentées ? » « Qu'est-ce qui, dans votre
architecture, rendrait telle évolution simple ou coûteuse, et pourquoi ? »
Ces questions sont réservées au formateur dans son rôle ; elles ne sont
jamais posées par l'entreprise marraine.

**C5 · Réflexivité** : « Qu'avez-vous appris ce sprint que vous ne saviez pas
au début ? Un exemple précis, un commit, un jour. » « Qu'est-ce que vous
referiez autrement ? » « Chacun de vous a reçu des retours au sprint
précédent, dans une autre équipe : citez-en un que vous avez appliqué ici, et
montrez-le. » « Comment s'est passée la reprise de la base héritée, et
qu'est-ce qui aurait aidé ? »

## 9. La fiche de soutenance (modèle)

Promotion · sprint · date · équipe · membres présents (émargement) ·
formateur · second évaluateur (soutenance) · ordre de passage · thèmes
d'arbitrage du jour · cas d'erreur tiré · séquence métier (jeu de rôle
pédagogique, fictif, sans suite productive) · pour chaque critère : niveau,
fait observé, conseil · grille C2 (cases) · éléments tirés + membres tirés
(auteur : oui/non) · observations individuelles C3 (hors fiche partagée) ·
séquences portées par membre · total /35 · seuil atteint / remédiation
demandée par l'équipe (renvoi livret) · incidents (cause externe/interne) ·
harmonisation (ajustement motivé) · signature · date de communication à
l'équipe.

## 10. À affiner après la première promotion

- Calibrer les descripteurs et les seuils (§5) sur de vraies soutenances.
- Vérifier la tenue de l'enveloppe de 30 minutes par équipe.
- Décider si l'observation individuelle C3 doit un jour peser dans une note
  individuelle (choix actuel : observation de livret seulement).
