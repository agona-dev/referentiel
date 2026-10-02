# Agona · Barème de la soutenance (/35)

> Le barème de l'oral, sur 35 points. Remis aux apprenants au démarrage de la promotion ; la version remise à l'entrée s'applique à toute la promotion.

## 1. Ce que la soutenance évalue

La grille de revue de code mesure **ce qui est écrit**. La soutenance
mesure **ce qui est compris** : la pensée derrière le code, les arbitrages,
la capacité à expliquer son travail devant un regard exigeant, technique ou
non.

La soutenance vaut **35 points sur 100** à chaque sprint (revue de code /35,
peer-review /30). La note est une note **d'équipe**. Les observations
**individuelles** (critère 3 et porteurs de séquence) alimentent le livret
de chaque apprenant.

Le « besoin » évalué est toujours **le besoin tel que cadré par le formateur au démarrage du sprint**, adapté à des fins
d'apprentissage.

| Critère | Objectif pédagogique | Bloc alimenté |
|---|---|---|
| C1 Compréhension du besoin | objectif 11 | B3 (6 points de l'oral) |
| C2 Arbitrages techniques | objectifs 7 et 12 | B3 |
| C3 Maîtrise de la base | objectif 3 | B2 (observation individuelle) et B3 |
| C4 Démonstration et communication | objectif 7 | B3 |
| C5 Réflexivité | objectif 8, phase réflexive (AFEST) | B3 (collectif). La rétrospective écrite du livret est individuelle |

## 2. Les 5 critères et la règle des points

| # | Critère | Points |
|---|---------|:------:|
| 1 | Compréhension du besoin | 6 |
| 2 | Arbitrages techniques | 10 |
| 3 | Maîtrise de la base | 8 |
| 4 | Démonstration et communication | 6 |
| 5 | Réflexivité | 5 |
| | **Total** | **35** |

Chaque critère se note sur 4 niveaux : **maîtrisé, solide, fragile, absent**.

Le niveau attribué est le plus élevé dont **toutes** les composantes sont
observées. Entre 2 niveaux, on retient l'inférieur et on écrit ce qui manquait
pour le supérieur. Chaque critère est **justifié par écrit** sur la fiche
(fait observé et conseil).

## 3. Le détail des critères

### C1 · Compréhension du besoin (/6)

L'équipe a compris le **problème** à résoudre, au-delà de la fonctionnalité à
produire. La note de cadrage du sprint fixe d'avance, pour les 5 équipes,
**3 à 5 contraintes et cas limites attendus** et le périmètre que le formateur
s'attend à voir écarté. La fiche les pré-renseigne.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 6 | La reformulation du problème est juste, tous les attendus sont nommés sauf un au plus, et le périmètre écarté est assumé et justifié |
| Solide | 4 | La reformulation est juste, mais 2 attendus ou plus manquent |
| Fragile | 2 | L'équipe décrit ce qu'elle a fait au lieu du problème qu'elle résout |
| Absent | 0 | L'équipe échoue à reformuler le problème, ou le reformule en contradiction avec le cadrage |

### C2 · Arbitrages techniques (/10)

Sur les **thèmes de décision** du sprint (découpage, modèle de données,
bibliothèque, abstraction ou duplication...), fixés et annoncés **à toutes les
équipes en même temps** au début de la matinée, le formateur déroule les
**4 questions** :

1. **Quelles alternatives avez-vous envisagées ?**
2. **Pourquoi avez-vous choisi celle-ci ?**
3. **Quels sont ses inconvénients ?**
4. **À quelles conditions faudrait-il revoir cette décision ?**

On évalue le **jugement**. Un choix non conventionnel bien argumenté vaut plus
qu'un choix « propre » que personne ne sait justifier. Une **alternative
réelle** est une option techniquement viable dans le contexte du sprint,
décrite au point de dire ce qu'elle aurait changé dans le code. Une équipe qui
explique l'absence d'alternative se note « fragile ».

La notation se fait par cases, cochées pendant la soutenance : 2 thèmes en
sprint (3 en soutenance finale) et 4 questions par thème, soit 8 cases en
sprint (12 en soutenance finale). Une case vaut 1 si la réponse est spécifique
au contexte, 0,5 si elle n'apparaît qu'à la relance, 0 si elle est générique
ou absente.

| Niveau | Pts | Sprint (sur 8) | Soutenance (sur 12) |
|---|:-:|:-:|:-:|
| Maîtrisé | 10 | ≥ 6,5 | ≥ 10 |
| Solide | 7 | 4,5 à 6 | 7 à 9,5 |
| Fragile | 3 | 2 à 4 | 3 à 6,5 |
| Absent | 0 | < 2 | < 3 |

Les **ADR du sprint** (`docs/adr/`, fiches numérotées : contexte,
options, décision, conséquences), déposés au gel, le j9 à 00h00, sont lus par le
formateur avant la soutenance. L'oral vérifie que l'équipe sait les défendre,
et que le code leur correspond. Une justification retenue en C2 peut amener le
formateur à écarter un signalement du rapport de l'agent de revue sur la
grille /35. La décision est consignée sur les 2 fiches.

Au niveau maîtrisé, une équipe répond : « On a hésité entre une table unique
avec un champ type et 2 tables ; on a pris 2 tables parce que les règles de
validation divergent ; ça coûte une jointure sur la liste ; si un troisième
type arrive, on repasse sur une table unique avec un schéma JSON. » Au niveau
fragile, une équipe répond : « On a fait 2 tables parce que c'est plus
propre. »

### C3 · Maîtrise de la base (/8)

Chaque membre peut expliquer **n'importe quelle partie** de la base, y
compris le code écrit par d'autres et ce qu'un outil a généré. Ce qui est dit
correspond à ce qui est dans le dépôt.

Le protocole dure 8 minutes :
- Le sort désigne **2 membres** parmi les présents, avec un outil de tirage
  visible par l'équipe, pour 4 minutes chacun. Le nombre tiré est fixe,
  quelle que soit la taille de l'équipe. Un **registre de tirage sans remise**
  est tenu sur le parcours : il donne la priorité aux apprenants qui restent à
  tirer, et chaque apprenant est interrogé au moins une fois tous les
  2 sprints.
- Les **éléments** sont tirés parmi 3 éléments présélectionnés par le
  formateur lors de l'arbitrage du j9. Ils relèvent des mêmes catégories pour
  toutes les équipes : une fonction non triviale, un test, une requête ou
  migration. Le formateur vise un élément auquel d'autres que le membre tiré
  ont contribué, et la fiche note si le membre tiré en est l'auteur. « Le
  chemin d'une requête de l'entrée à la base » est réservé à la soutenance
  finale.
- Le formateur partage lui-même le dépôt gelé sur son écran et navigue à la
  demande du membre interrogé. Le membre a **60 secondes de lecture
  silencieuse** avant la première question. Les questions viennent une à la
  fois, chacune reformulée une fois si besoin, et le silence est toléré.
  « Je ne sais pas, mais je chercherais là » compte comme une réponse
  partielle. Après 2 minutes, le membre peut passer la main à l'équipe, et le
  niveau plafonne alors à solide.
- La question « où est la dette que vous connaissez ? » est **toujours
  posée**. On note la précision de la réponse (emplacement, conséquence, ce
  qu'il faudrait faire).
- Pour l'entraînement, un **mini-tirage de 3 minutes** a lieu à chaque revue
  formative hebdomadaire (j2 à j8), hors notation. Il alimente déjà le livret.

| Niveau | Pts | On observe (2 membres interrogés) |
|---|:-:|---|
| Maîtrisé | 8 | Les 2 expliquent juste, le discours correspond au dépôt, et la dette est localisée avec sa conséquence |
| Solide | 5 | L'un des 2 fait une imprécision factuelle mineure (nom, ordre d'appel, valeur) corrigée à la relance, ou passe la main |
| Fragile | 3 | L'un des 2 échoue à expliquer son élément, ou le discours s'écarte du code |
| Absent | 0 | Les 2 échouent à expliquer leur élément |

Pour chaque membre interrogé, la fiche porte une **observation individuelle**,
*maîtrise : oui / partielle / non*, avec une ligne de justification.
L'observation individuelle est la **trace nominative de l'observation** qui
fonde le niveau d'équipe. Elle est reportée au livret, hors fiche d'équipe
partagée.

### C4 · Démonstration et communication (/6)

C4 mesure la **présentation**. Le fonctionnel est noté par la revue de code,
les réponses aux questions par C2 et C3. La démo tourne sur le poste de
l'équipe.

Le protocole dure 6 minutes. La démo occupe 4 minutes : le chemin principal,
puis **un cas d'erreur tiré par le formateur** dans la liste du brief,
identique pour les 5 équipes. Suivent **2 minutes où le formateur joue
l'interlocuteur métier**, à chaque sprint : « je suis le métier, expliquez-moi
ce que ça change pour moi ». La fiche porte la mention *séquence métier : jeu
de rôle pédagogique, fictif, sans suite productive*.

Un **repli est obligatoire** : un screencast de 3 minutes (chemin principal et
cas d'erreur) est déposé au gel, le j9 à 00h00, et l'intégration continue doit avoir
passé le démarrage et un test de fumée. Si la démo échoue en direct, l'équipe
a 2 minutes de diagnostic à voix haute, puis le formateur tranche la cause. Si
la cause est **externe à la base** (réseau, partage d'écran, poste,
plateforme), on joue le screencast, et l'échec est neutre pour C4. Si la cause
est **interne à la base**, C4 se note fragile ou absent selon que le
diagnostic est posé ou non. Le diagnostic à voix haute est lui-même une
observation C3 pour le livret.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 6 | La démo est complète (chemin principal et cas d'erreur tiré) et tient dans ses 4 minutes. L'explication métier définit chaque terme technique employé. L'équipe énonce d'elle-même les limites connues |
| Solide | 4 | La démo est complète. L'explication métier s'appuie sur du jargon non expliqué, ou les limites connues sont passées sous silence |
| Fragile | 2 | La démo est partielle, ou elle échoue pour une cause interne à la base, diagnostiquée sur le moment |
| Absent | 0 | La démo échoue pour une cause interne à la base, sans diagnostic |

Le formateur tient le chrono et coupe à la fin du temps imparti.

### C5 · Réflexivité (/5)

L'équipe apprend de sprint en sprint. Toute affirmation doit pouvoir être
ancrée dans le dépôt (fichier, commit, PR) ou dans un moment daté du sprint.
Le formateur peut dire « montrez-moi ».

Au **sprint 1**, C5 se note sur « appris » et « à refaire », et sur l'écart
entre le plan du j1 et ce qui a été livré. **À partir du sprint 2**, les
« retours précédents » sont ceux reçus par **chaque membre dans son ancienne
équipe** (livret) et les 3 fiches de la **base héritée** (revue de code,
soutenance orale, peer-review), transmises avec la passation. Le formateur a
ces retours sous les yeux.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 5 | L'équipe rattache au moins 2 apprentissages à un fait précis (commit, bug, retour). Elle cite au moins un retour précédent avec l'endroit où il a été traité, ou la raison de l'avoir laissé de côté. Elle nomme une difficulté de passation avec une proposition |
| Solide | 3 | Les apprentissages sont cités sans fait précis, ou les retours sans traitement montré |
| Fragile | 2 | L'équipe s'en tient à des formules générales (« mieux communiquer ») |
| Absent | 0 | Aucun fait du sprint n'est évoqué, même à la relance |

Au niveau maîtrisé, une équipe répond : « On avait reçu "logique métier dans la
route" sur la base héritée : on l'a sortie dans `pricing.py`, commit du mardi ;
la passation a bloqué sur les migrations, on propose un README de reprise avec
l'ordre des commandes. » Au niveau fragile, une équipe répond : « On a appris à
mieux s'organiser. »

## 4. Le déroulé

### En sprint : 30 minutes par équipe, en 5 temps

| | Séquence | Critère |
|---|---|---|
| 01 | **Le besoin** : reformulation, contraintes, périmètre écarté | C1 |
| 02 | **La démo** : chemin principal, cas d'erreur tiré, puis séquence métier | C4 |
| 03 | **Les arbitrages** : 2 thèmes, 4 questions, relances | C2 |
| 04 | **Le tirage** : 2 membres, un élément chacun | C3 |
| 05 | **La rétro express** : appris, à refaire, héritage | C5 |

L'ordre est fixe et le formateur tient le chrono. Il ajuste la durée de chaque
temps, sans la publier, pour que les 5 équipes reçoivent le même traitement
dans la même enveloppe de 30 minutes.

Les 5 soutenances tiennent sur une matinée, de 9h00 à 11h45, avec une pause
après la 3e équipe. Chaque créneau ménage un temps de transition et un temps
de notation sur fiche après le passage de l'équipe.
**L'arbitrage des rapports de l'agent de revue a lieu la veille** (j9 après-midi), avec la présélection des éléments du tirage : le
formateur arrive en connaissant chaque dépôt.

- Les thèmes d'arbitrage du jour sont annoncés à 9h00 à toutes les équipes
  en même temps. L'ordre de passage est tiré au sort et publié la veille.
- Les soutenances sont **ouvertes aux autres équipes**. La séquence de tirage
  peut se tenir en comité restreint à la demande d'un apprenant. Les équipes
  en attente rédigent leur rétrospective écrite et relisent les bases des
  autres.
- Au début de la soutenance, le formateur, et lui seul, désigne le **porteur
  de chaque séquence**. Il veille à ce que chaque apprenant porte C2 ou C4 au
  moins une fois avant la soutenance. Toute question peut être redirigée vers
  n'importe quel membre. La fiche note les séquences portées par chaque membre
  présent et une ligne d'observation.
- Le formateur et le suppléant arrêtent chacun leurs notes **à chaud** sur
  leur fiche, dans l'espace, puis les **relisent en bloc** (15 minutes
  d'harmonisation, avant 15h00). Un ajustement d'un niveau au plus est
  possible, motivé par écrit. La note de soutenance est la moyenne des 2
  fiches arrêtées. Elle est communiquée à 15h30, avec les 2 fiches. Le débrief de peer-review revient sur les arbitrages les plus instructifs.
- **L'entreprise marraine est invitée aux soutenances de sprint**, dans le même
  régime qu'en soutenance finale : comme **invitée métier**, sans participation
  à la notation et sans accès aux notes. Elle pose ses questions directement,
  et **les échanges avec elle ne sont pas pris en compte dans l'évaluation** :
  une équipe qui reçoit 3 questions et une équipe qui n'en reçoit aucune
  passent la même soutenance. Elle ne donne de consigne à personne, et le
  formateur conduit la séance. Elle est également invitée à la **démonstration
  des 5 bases** qui ouvre le j9.

### En soutenance finale : 45 minutes par équipe, devant le jury

La structure est la même, avec des temps allongés : démo de 10 min, 3 thèmes
d'arbitrage en 15 min, tirage sur 2 membres avec « le chemin d'une requête ».

- **Le jury**, identique pour les soutenances de sprint et la soutenance
  finale, est composé du **formateur-évaluateur, qui le préside**, et d'un
  **second évaluateur pédagogique** (un formateur suppléant), extérieur à l'entreprise marraine. Les 2 notent chaque
  soutenance (règle 12).
- **L'entreprise marraine est conviée à la soutenance finale comme invitée
  métier**. Elle pose ses questions directement, sur la compréhension du
  métier (C1), et **les échanges avec elle ne sont pas pris en compte dans
  l'évaluation**. Elle ne donne de consigne à personne, et le formateur conduit
  la séance. La séquence de tirage (C3) se tient hors sa présence.
- **La base présentée est gelée avant la soutenance et remise en l'état.**
  La remise du résultat a lieu quels que soient le résultat de la soutenance
  et l'appréciation de l'entreprise, et aucune demande de modification ne
  peut en découler. Les remarques de l'entreprise sont consignées par le
  formateur au bilan de promotion et à la note de cadrage suivante, jamais
  transmises aux équipes comme tâches.
- La note de la soutenance finale alimente l'appréciation par bloc et
  l'attestation.

## 5. Du score à l'appréciation

- **Par sprint, pour l'équipe**, un total de 24 à 35 correspond au niveau
  attendu, et un total de 14 à 23 à un niveau en cours. **Avec moins de 14
  points, ou un critère « absent »**, un constat est consigné au livret.
  **La remédiation se fait à la demande de l'équipe** : c'est une réallocation
  du temps d'encadrement, consignée au livret
  avec le constat, l'objectif, les moyens et la réévaluation à la soutenance
  suivante.
- **En fin de parcours, pour l'apprenant (bloc B3)**, le bloc est *acquis*
  avec au moins 2 observations C3 « oui » sans « non » sur les 2 derniers
  sprints, et au moins une séquence C2 ou C4 portée à « solide » ou mieux. Il
  est *non acquis* si la dernière observation C3 est « non », sans séquence
  portée. Il est *en cours d'acquisition* dans les autres cas. Toute
  appréciation de bloc repose sur au moins 2 observations C3.
- Ces seuils sont **à calibrer après la première promotion**. Ils sont
  publiés tels quels à l'entrée et restent fixes pendant la promotion.

## 6. Les règles

1. **Tout est publié à l'entrée** : critères, niveaux, déroulé, banque de
   questions, fiche de notation. Les questions restent dans le périmètre
   enseigné (référentiel commenté, ateliers tenus, retours de revue formative
   consignés). Les questions-mères viennent de la banque, et les relances sont
   libres dans ce périmètre.
2. Les **thèmes de décision, les catégories d'éléments et le cas d'erreur sont
   les mêmes** pour les 5 équipes d'un même sprint. Les choix, eux, diffèrent.
3. **Les outils d'IA sont autorisés** pour produire le code. La soutenance
   est précisément le lieu où l'on vérifie que le code produit est compris :
   une partie générée que l'équipe échoue à expliquer place C3 en « fragile »
   ou « absent », exactement comme du code écrit à la main.
4. **On évalue la démarche et la compréhension.** Une réponse vaut par son
   contenu, quels que soient l'accent, la grammaire, la recherche de mots, le
   recours à un terme anglais ou les hésitations. Elle peut être donnée en
   montrant le code ou un schéma.
5. **Chaque note est justifiée par écrit** sur la fiche, transmise à
   l'équipe le jour même. L'observation individuelle C3 est montrée à
   l'apprenant dans son livret dès le j10 à 15h30, avec un droit de commentaire daté,
   à tout moment. Le
   livret est consultable par l'apprenant à tout moment. Les fiches et
   observations sont conservées au dossier de la promotion pendant la durée
   fixée dans l'information RGPD remise à l'entrée (la proposition est de
   5 ans après la fin de la promotion, à confirmer avec le conseil
   juridique). **Les soutenances sont enregistrées**, pour le livret et
   l'usage pédagogique interne. Les sessions se tiennent toutes à distance,
   et la caméra reste facultative. L'apprenant qui refuse l'enregistrement
   passe en fin de séance, enregistrement coupé, et sa soutenance se déroule
   à l'identique. Toute publication requiert un consentement explicite.
   **La fiche écrite reste l'unique trace évaluative** : l'enregistrement sert
   le livret et la relecture.
6. Les **notes, justifications, classement des bases et observations
   individuelles** sont communiqués à l'équipe et à l'apprenant concerné, et
   archivés. **Le seul élément d'évaluation que reçoit l'entreprise marraine
   est un bilan pédagogique agrégé**, remis en fin de promotion, sans donnée
   nominative.
7. **La soutenance classe des apprentissages et nourrit le livret**, sans
   conséquence disciplinaire. La remédiation (§5) intervient à la demande de
   l'équipe.
8. Un **membre absent** est retiré du tirage. Son livret porte « non
   observé » (distinct de « non »), et il est tiré d'office à la soutenance
   suivante. La note d'équipe reste inchangée, et la soutenance est maintenue
   dès qu'un membre est présent. La justification de l'absence relève de
   l'assiduité (règlement).
9. **Le tirage s'applique tel quel** : si le membre désigné ne répond pas, ou
   si l'équipe substitue un volontaire, l'élément est réputé non expliqué (C3
   se constate) et le livret porte « non observé : refus ». C'est une absence
   d'observation, qui déclenche un entretien avec le formateur. Une adaptation
   se demande avant la soutenance.
10. Une **demande d'adaptation** est recevable à l'entrée **ou à tout moment
    du parcours** (handicap, situation particulière). Les adaptations
    possibles sont le temps majoré d'un tiers, les questions de la banque
    remises par écrit, la réponse en montrant le code, la pause, la séquence
    de tirage en petit comité, l'interprète LSF et le support visuel.
    L'adaptation est consignée au livret seulement. Le temps d'équipe est
    étendu d'autant, sans pénalité. Au-delà des moyens du programme,
    l'apprenant est orienté vers Ressources Handicap Formation.
11. Une **relecture de note** se demande par écrit dans l'espace, de la
    communication des 3 notes de la base, le j10 à 15h30, jusqu'au j1 à 9h00.
    Le membre qui la demande choisit la note visée (revue, soutenance,
    peer-review) et écrit son motif. Le formateur et le suppléant réexaminent
    ensemble chaque demande, fiches sous les yeux, et écrivent une décision
    commune avant 10h45. En cas de désaccord, le formateur tranche, et les 2
    positions sont écrites. La réponse s'affiche sous les notes, pour toute
    l'équipe, **avant l'annonce du classement**, le j1 à 11h00. L'issue est
    archivée au dossier de la promotion. Une fois publiés, le classement, la
    base commune et la recomposition des équipes sont acquis. Une note
    corrigée après l'annonce porte la date et le motif de sa correction, et le
    rang ne change plus.
    L'observation individuelle portée au livret se commente à tout moment, sans
    effet sur le classement. La relecture de note est distincte de la
    réclamation du règlement intérieur (article 7).
12. Pour la **notation et le calibrage** (révisé le 30/09), le suppléant
    **note chaque soutenance** sur sa fiche, comme le formateur. La note de
    soutenance est la **moyenne des 2 fiches arrêtées**. Au sprint 1, les 2
    fiches servent au calibrage : les écarts sont analysés, et la lecture
    commune écrite vaut dès le sprint 2. Les écarts sont consignés au titre de
    l'amélioration continue.
13. **À total égal**, au classement des bases, la note de peer-review
    départage, puis la revue de code, puis la soutenance. Si tout reste égal,
    le formateur tranche par écrit.

## 7. Comment se préparer (pour les équipes)

- Chaque membre **lit tout le dépôt** avant le j10.
- Les **ADR du sprint** (`docs/adr/`) sont à jour au gel, le j9 à 00h00.
- Le **plan de tests** (`docs/plan-de-tests.md`) est à jour au gel.
- Le **screencast de repli** (3 minutes) est déposé au gel.
- L'équipe relit la **fiche de revue de la base héritée** et les retours
  individuels reçus par chacun.
- On répète la **séquence métier** : expliquer le sprint uniquement en termes
  métier.

## 8. Banque de questions (publiée)

Toute réponse doit pouvoir être ancrée dans le dépôt ou dans un moment daté du
sprint. Le formateur peut dire « montrez-moi ».

**C1 · Besoin** : « Reformulez le problème en une phrase, sans parler de
technique. » « Quel cas limite vous a posé le plus de questions ? » « Qu'avez-
vous volontairement laissé de côté, et pourquoi ? » « Si le besoin était mal
compris, où le verrait-on dans votre code ? »

**C2 · Arbitrages** : les 4 questions, appliquées aux thèmes du jour. Les
relances possibles sont « qu'est-ce qui vous aurait fait choisir l'autre
option ? », « qu'est-ce que ce choix coûtera au prochain sprint ? » et
« montrez-moi l'endroit du code où ce choix se voit. »

**C3 · Maîtrise** : « Que fait cette fonction, et que se passe-t-il si on la
supprime ? » « Pourquoi ce test existe-t-il, que protège-t-il ? » « Cette
partie a été générée ou écrite à la main ? Qu'est-ce que vous y avez
changé ? » « Où est la dette que vous connaissez ? » (toujours posée).
En soutenance finale, le formateur ajoute : « Montrez-moi le chemin d'une
requête, de l'entrée à la base de données. »

**C4 · Séquence métier** (le formateur joue le métier, jeu de rôle
pédagogique) : « Expliquez-moi ce que ça change pour moi, sans mot
technique. » « Quelles limites connues de votre solution expliqueriez-vous à
un utilisateur, et où sont-elles documentées ? » « Qu'est-ce qui, dans votre
architecture, rendrait telle évolution simple ou coûteuse, et pourquoi ? »
Ces questions sont réservées au formateur dans son rôle.

**C5 · Réflexivité** : « Qu'avez-vous appris ce sprint que vous ne saviez pas
au début ? Un exemple précis, un commit, un jour. » « Qu'est-ce que vous
referiez autrement ? » « Chacun de vous a reçu des retours au sprint
précédent, dans une autre équipe : citez-en un que vous avez appliqué ici, et
montrez-le. » « Comment s'est passée la reprise de la base héritée, et
qu'est-ce qui aurait aidé ? »

## 9. La fiche de soutenance (modèle)

Promotion · sprint · date · équipe · membres présents (émargement) ·
évaluateur (formateur ou suppléant, une fiche chacun) · ordre de passage · thèmes
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
  individuelle (le choix actuel la limite au livret).
