# Agona · Guide de la peer-review (/30)

> Le protocole d'évaluation par les pairs, sur 30 points, pour la journée du j9. Écrit pour les équipes, remis au démarrage de la promotion.

## 0. Avant de commencer

**Les mots du guide.** *Gel* : la version de la base figée par un tag **à la fin du j8, 18h** ;
plus aucun commit ne compte, et les deux derniers jours du sprint ne produisent
plus une ligne de code. *j9, j10* : neuvième et dixième
jours du sprint. *Livret* : votre dossier individuel de compétences, tenu
par le formateur, consultable à tout moment. *B1 à B3* : les trois blocs de
compétences du programme. *Registre de décisions* : la page où l'équipe
évaluée a écrit ses choix (options, raisons, inconvénients), déposée au gel.
*Changement sonde* : une petite modification imposée, faite pour sonder la
base (se laisse-t-elle modifier sans douleur ?). *Erreur avalée* : un
`try/except` ou `catch` qui attrape l'erreur et ne fait rien. *Relecture de
note* : vous pouvez demander par écrit au formateur de réexaminer une note.

**À 9h00 le j9, le formateur publie sur le canal de la promotion** : les URL
des **quatre archives gelées** que vous évaluez, **l'ordre dans lequel vous les
relisez** et les commandes pour les récupérer, les trois éléments à localiser, le changement sonde, et les quatre
fiches pré-renseignées (sprint, base, équipe, consignes, rôles à remplir). Les
consignes sont identiques pour les quatre bases : mêmes éléments à localiser,
même changement sonde. Si vous n'avez pas ces quatre choses, vous ne commencez
pas.

**Vous travaillez sur vos machines, dans l'environnement de référence de la
promotion** (versions listées, Docker installé, images et dépendances
standard téléchargées la veille). Le formateur a lui-même démarré chaque base
et réalisé le changement sonde avant de les annoncer : il sait ce qui est
faisable.

**Les fiches** sont les fichiers `peer-review-sprint-N-base-X.md`, une par
base évaluée, dupliqués depuis le gabarit au début de la journée et remis par
le canal de la promotion **avant 16h30 le j9**.

## 1. Pourquoi c'est vous qui notez

À chaque sprint, votre équipe évalue la base d'une autre équipe : 30 points
sur les 100 du sprint.

1. **Vous avez résolu le même problème.** Vous savez où étaient les
   difficultés, quels cas limites piégeaient, ce qui était dur à bien faire.
2. **Vous allez peut-être hériter de cette base.** Au sprint suivant, la
   meilleure base devient la base commune. La question de la grille,
   *« voudrais-je hériter de cette base ? »*, vous y répondez pour de vrai.
3. **Relire du code est une compétence** (objectif 8 : évaluer le travail
   d'un pair contre des critères publiés et formuler une critique
   argumentée). En entreprise, une large part du temps se passe à relire. La
   qualité de votre revue est observée au livret (§5), sans points : une
   bonne revue compte pour vous, autrement que par la note.

**Il n'y a pas d'appariement : chaque équipe relit les quatre autres bases**,
avec les mêmes consignes pour toutes. Vous ne recevez vos propres notes
qu'après avoir rendu vos quatre fiches. Chaque base reçoit donc quatre regards
indépendants, et sa note est la médiane des quatre totaux : personne ne dépend
d'un relecteur unique, ni dans un sens ni dans l'autre.

## 2. Ce que vous évaluez : la reprenabilité vécue

La revue de code (/35) mesure ce qui est écrit, avec la grille. La soutenance
orale (/35) mesure ce qui est compris. La peer-review mesure ce que **vous
vivez en reprenant la base** : vous ne re-notez pas la grille, vous faites
l'expérience de l'héritage et vous la racontez. P2 et P4 mesurent l'**effet**
des critères de la grille (le temps qu'il faut pour s'y retrouver), pas leur
re-notation : c'est une seconde façon de mesurer la même chose, et c'est
voulu.

| # | Critère | Points | Ce que ça mesure chez l'équipe évaluée |
|---|---------|:------:|---|
| P1 | Reprise en main | 8 | objectif 5, bloc B2 |
| P2 | Architecture lisible | 7 | objectifs 2 et 3, bloc B2 |
| P3 | Le changement sonde | 8 | objectifs 3 et 5, bloc B2 |
| P4 | Confiance : « on en hériterait ? » | 7 | objectif 3, bloc B2 |
| | **Total** | **30** | |

La revue que vous **donnez** mesure, chez vous, l'objectif 8 (blocs B3,
critique argumentée, et B2, revues données).

**Chaque base reçoit quatre fiches, une par équipe évaluatrice**. Sa
note de peer-review est la **médiane des quatre totaux**, après modération du
formateur. Deux conséquences : une fiche isolée, trop dure ou trop douce, ne
décide plus de rien ; et **l'écart entre les quatre fiches devient lui-même une
information**, parce que quatre équipes qui n'arrivent pas à la même conclusion
sur une base disent quelque chose de cette base. Le formateur traite ces écarts
au débrief.

Quatre niveaux par critère, **maîtrisé / solide / fragile / absent**. Les
points de chaque niveau sont dans les tableaux ci-dessous, et le total /30 est
la somme des quatre.

**Comment choisir le niveau.** Chaque niveau est décrit par ce que vous devez
observer. **Vous retenez le niveau dont vous observez tout** : s'il manque un
seul élément de sa description, ce niveau n'est pas atteint. Si vous hésitez
entre deux, prenez le plus bas et écrivez ce qui manquait pour l'autre. Chaque
critère est justifié sur la fiche par **un fait constaté et une piste
d'amélioration**.

### P1 · Reprise en main (/8)

Le binôme P1 récupère l'archive gelée et suit **uniquement le README**, sans
contacter l'équipe évaluée ni le formateur (votre binôme, oui). Chacun des
deux sur sa machine ; on retient le temps le plus long et ce qui a différé.

**Le chrono** démarre à la première commande d'installation ou de démarrage
du README et s'arrête quand l'application répond et que les tests sont
verts ; les téléchargements **imposés par la base** comptent, une image ou des dépendances lourdes étant un fait du dépôt. Un écart entre les deux membres qui s'explique par la connexion et non par le dépôt est neutralisé par le formateur, qui dispose de sa propre référence. Les horodatages de début et de fin vont
sur la fiche. Si un outil manque sur votre machine : ça compte contre le
README seulement s'il ne le liste pas en prérequis ; sinon, chrono en pause
le temps de l'installer, et vous le notez. « Les tests passent » est en plus
attesté par l'intégration continue au tag de gel : P1 mesure les étapes
humaines, pas la machine.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 8 | L'application démarre **et** les tests passent, en 10 minutes ou moins, en suivant les commandes du README sans aucune correction |
| Solide | 5 | Démarre et tests verts, mais en 10 à 20 minutes, ou avec une ou deux corrections (variable, commande, version) |
| Fragile | 3 | Démarre ou tests verts, pas les deux ; ou plus de 20 minutes ; ou trois corrections et plus ; ou pas de tests dans la base |
| Absent | 0 | Ni démarrage ni tests en suivant le README |

*Pourquoi 10 minutes alors que la grille demande un README « en moins de
5 minutes » ?* Cinq minutes, c'est la cible de l'auteur sur sa machine
chaude ; dix, c'est la tolérance d'un relecteur qui part de zéro.

**Plan B.** **À 20 minutes le chrono s'arrête**, P1 est noté au niveau
atteint, et vous demandez au formateur la commande de démarrage : P2 et P3 se
font sur une base qui tourne. L'équipe évaluée n'y perd rien de plus que le
niveau constaté.

### P2 · Se repérer dans la base (/7)

Le formateur a donné **trois éléments à localiser**, choisis dans ce que le
sprint a ajouté ou modifié (par exemple : la règle métier X, la validation
des entrées de la nouvelle route, l'accès à la nouvelle table). **Trois
chercheurs** désignés, quelle que soit la taille de l'équipe, hors binôme P1
si possible. Chacun cherche **seul et en silence**, note son temps et son
chemin sans rien dire, stop à 10 minutes. Sur la fiche : pour chaque élément,
le temps médian des trois et le nombre de chercheurs qui ont trouvé (ex. :
« 3/3 en 6 min, `src/rules/discount.py` »). Un élément est *trouvé* si au
moins deux des trois arrivent au même chemin.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 7 | Les trois éléments localisés, temps médian de 5 minutes ou moins |
| Solide | 5 | Les trois éléments localisés, temps médian entre 5 et 10 minutes ; ou un élément se trouve à un endroit que le nommage contredit |
| Fragile | 2 | Un élément non localisé dans les dix minutes, ou éclaté sur trois fichiers ou plus |
| Absent | 0 | Deux éléments ou plus non localisés dans les dix minutes |

### P3 · Le changement sonde (/8)

Le formateur a fixé **un petit changement, identique pour toutes les
équipes**, dans le périmètre du sprint : ajouter un champ, modifier une règle,
changer un message. Il est **fictif et sans valeur productive** : il ne
correspond ni au besoin du sprint suivant, ni à une demande de l'entreprise
partenaire, et il est consigné au registre de la promotion avec son objectif
pédagogique avant le gel. Le formateur l'a réalisé lui-même sur chaque base
(en cinq minutes ou moins, sinon il l'a remplacé par un changement de même
taille).

Le binôme P3 travaille sur l'archive gelée, **sans droit d'écriture sur le
dépôt évalué** : `git checkout -b sonde-<votre-equipe>`, et ne tapez jamais
`git push`. **20 minutes chrono** pour réaliser le changement (30 au sprint 1,
ou la fourchette fixée par le formateur au gel), puis 5 minutes pour consigner le patch et les observations.
À la fin du chrono, on s'arrête là où on en est, et c'est ce qu'on note. Le
`git diff` (fichier patch) est joint à la fiche ; la branche et le clone sont
supprimés après remise. Vous n'êtes pas obligés d'écrire le test : dites si
un test existant a cassé quand vous avez fait le changement, et sinon dans
quel fichier vous l'ajouteriez ; un « test ajouté » ne compte que s'il est
dans le patch.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 8 | Changement fait en un seul endroit logique ; un test existant a réagi (cassé puis corrigé), ou un test ajouté figure dans le patch ; aucune surprise |
| Solide | 5 | Changement fait, mais deux endroits touchés qui auraient dû n'en faire qu'un, ou aucun test ne le protège |
| Fragile | 3 | Changement fait avec trois endroits touchés ou plus ; ou des tests sans rapport ont cassé, mais la cause a été identifiée et corrigée dans le temps imparti |
| Absent | 0 | Pas de patch fonctionnel à la fin du chrono, ou la suite de tests du dépôt reste en échec après le changement |

P1 et P3 sont des **faits**, et le formateur a sa propre référence sur chaque
base : si votre résultat s'en écarte (vous n'avez pas pu faire en 20 minutes
ce qu'il a fait en cinq), il corrige au niveau constaté, sans pénaliser
l'équipe évaluée.

### P4 · Confiance : « on en hériterait ? » (/7)

Votre jugement d'ensemble, synthèse assumée de P1 à P3 et de votre lecture,
**obligatoirement ancré** : des forces et des faiblesses, chacune avec un
chemin de fichier, chaque faiblesse avec une piste. Visez trois de chaque ;
si vous n'en trouvez pas trois, écrivez-en deux et dites en une ligne
pourquoi. Une case justifiée vide vaut mieux qu'une invention. Lisez le
**ADR** de l'équipe : une faiblesse qu'elle y a documentée
et assumée se note « assumée », pas « oubliée ». Une *zone* est un module ou
un dossier.

| Niveau | Pts | On observe |
|---|:-:|---|
| Maîtrisé | 7 | Vous pourriez poursuivre le développement immédiatement : les faiblesses relevées sont localisées, comprises et documentées |
| Solide | 5 | Une zone à refaire avant de pouvoir avancer, que vous savez nommer |
| Fragile | 2 | Deux zones ou plus à refaire |
| Absent | 0 | La structure elle-même serait à refaire, et vous savez dire pourquoi |

## 3. Comment vous organiser : la journée du j9

Le code est gelé à la fin du j8. **Le j9 est entièrement consacré à la
peer-review**, le j10 aux soutenances et au classement. Vous relisez les
**quatre autres bases**, l'une après l'autre, environ soixante-quinze minutes
chacune.

| Temps | Quoi |
|---|---|
| 9h00 à 9h20 | Brief du formateur, récupération des quatre archives, duplication des quatre fiches, répartition des rôles |
| 9h20 à 10h35 | **Base 1** |
| 10h45 à 12h00 | **Base 2** |
| 13h00 à 14h15 | **Base 3** |
| 14h25 à 15h40 | **Base 4** |
| 15h40 à 16h30 | Relecture des quatre fiches par l'équipe, mise au propre, remise |

**Les soixante-quinze minutes, par base** : 20 minutes de démarrage
chronométré (archive, README, lancement, tests), 10 minutes de localisation des
trois éléments en silence, 20 minutes de changement sonde puis 5 minutes de
consignation du patch et des observations, 10 minutes de verdict collectif,
10 minutes de fiche.

**Les rôles tournent d'une base à l'autre**, et c'est voulu : sur les quatre
bases d'un même sprint, chacun tient au moins une fois le démarrage et une fois
le changement sonde. Le formateur tient le registre pour que chacun ait aussi
rédigé au moins une fiche avant le sprint 3.

**Un gardien du temps est désigné pour la journée.** Sans lui, la quatrième
base est bâclée.

**L'ordre des bases tourne d'une équipe à l'autre**, et le formateur le publie
au brief : l'équipe A commence par la base B, l'équipe B par la base C, et ainsi
de suite. Sans cette rotation, les cinq équipes attaqueraient dans le même ordre
et la même base serait systématiquement relue par des gens fatigués : ce ne
serait pas un aléa, ce serait un biais. Avec la rotation, chaque base est relue
une fois en première position et une fois en dernière.

**Au sprint 1**, comptez trente minutes de plus sur la première base, le temps
de prendre le protocole en main.

## 4. Comment bien relire

- **Lisez comme quelqu'un qui va en hériter**, pas comme un juge : « si je
  devais continuer à développer dessus lundi, qu'est-ce qui m'arrêterait ? »
- **Partez de la grille de revue** comme liste de contrôle, mais ne la
  re-notez pas : servez-vous-en pour nommer précisément ce que vous voyez
  (« critère 7 : l'erreur est avalée dans `services/order.py` »).
- **Chaque faiblesse vient avec un chemin et une piste.** « `api/users.js`
  valide à la main ce que le schéma de validation (Zod, Pydantic) ferait »
  est une revue ; « c'est pas propre » n'en est pas une.
- **Cherchez aussi ce qui est mieux que chez vous.** C'est la première ligne
  de la fiche, « ce qu'on reprendrait chez nous ». Reprendre une idée ou un
  pattern vu chez eux dans votre base au sprint suivant est autorisé et
  encouragé, en le citant dans votre README (« repris de la base de
  l'équipe B »). Copier des fichiers entiers, non.
- **Ne devinez pas les intentions** : lisez les ADR ; si la
  justification manque, notez qu'elle manque, la soutenance tranchera.
- **Ne modifiez jamais la base évaluée** : archive gelée, branche locale
  pour la sonde, rien n'est poussé, rien n'est partagé hors de la fiche.
- **Les outils d'IA** (ceux listés au règlement du programme) peuvent vous
  expliquer un fichier ou une commande. Les forces et faiblesses viennent de
  fichiers que vous avez ouverts vous-mêmes ; vous n'avez pas accès au
  rapport de l'agent de revue, et au débrief, une personne tirée au sort
  montre à l'écran une faiblesse de la fiche et le fichier concerné.

## 5. Comment votre revue est observée

La qualité de la revue donnée est une compétence (objectif 8). Elle est
observée au livret, **sans points** : elle n'entre pas dans les 100 du
sprint. Quatre observables **sur chacune de vos quatre fiches**, à trois niveaux (oui / partiel / non) :

- **Ancrage** : chaque force et faiblesse porte un chemin qui existe au tag
  de gel.
- **Justesse** : aucune contradiction non expliquée avec la référence P1/P3
  du formateur ni avec la base elle-même.
- **Utilité** : chaque faiblesse a une piste actionnable ; « ce qu'on
  reprendrait chez nous » cite des éléments concrets.
- **Conformité** : aucun nom, tous les niveaux justifiés, patch joint, remise
  à l'heure.

La fiche a deux parties. La **partie partagée** (communiquée à l'équipe
évaluée) ne porte aucun nom. La **partie individuelle** (formateur
seulement) note qui a tenu P1, P3, la recherche P2 et la rédaction, et
l'initiale de l'auteur de chaque force et faiblesse : c'est la trace
nominative de la même observation, reportée au livret. Chaque observation
est montrée à l'apprenant dans la semaine, avec droit de commentaire
consigné, formulée en niveau de compétence avec le fait observé (« critique
argumentée : fragile, trois niveaux sans justification ancrée »), jamais en
jugement d'intention.

## 6. Les règles

1. **Mêmes consignes pour tous** : éléments à localiser et changement sonde,
   conçus par le formateur à partir du brief avant le gel, vérifiés sur chaque
   base au gel, identiques pour les N équipes. **Seul l'ordre de passage change d'une
   équipe à l'autre**, publié au brief.
2. **Aucune note sans justification.** Une fiche dont un niveau n'est pas
   justifié est renvoyée en fin de j9, retour avant 9h le j10 ; sinon le
   formateur substitue sa référence sur le critère concerné, et le consigne.
3. **On évalue le code, jamais les personnes** : pas de nom dans la partie
   partagée, pas de jugement sur le travail « de quelqu'un ». La base est
   collective.
4. **La référence du formateur et la modération.** Le formateur a démarré
   chaque base et réalisé la sonde avant la séance, et arbitre la grille /35
   avant de lire les fiches. Sur P1 et P3 (des faits), il corrige au niveau
   constaté par sa référence. Sur P2 et P4 (du jugement), il ajuste d'un
   niveau au plus, motivé par écrit ; un écart de deux niveaux ou plus donne
   d'abord lieu à un échange de dix minutes avec l'équipe évaluatrice. Une
   fiche dont les justifications ne sont pas ancrées dans la base, ou sont
   contredites par elle (un chemin qui n'existe pas, un fait inventé), **est
   écartée du calcul** : la note de la base devient la médiane des trois
   fiches restantes. **L'équipe évaluée n'est jamais pénalisée par une fiche
   défaillante**, et l'équipe évaluatrice peut compléter la sienne jusqu'au
   j10 matin, à son initiative. Si trois fiches ou plus sont écartées sur une
   même base, le formateur la note lui-même sur les quatre critères. Une différence d'avis argumentée n'est jamais
   un motif. Tout arbitrage est notifié aux deux équipes avec la fiche
   publiée, droit de commentaire consigné sous une semaine. **Aucune
   conséquence disciplinaire.**

   ⚠ **Une note n'est jamais modérée parce qu'elle est sévère ou généreuse**,
   uniquement sur les faits et les justifications produits. Le formateur ne
   remet pas les notes qui lui conviennent : il corrige celles qui ne sont pas
   étayées.
5. **Le suivi de calibration des équipes évaluatrices.** Après chaque sprint,
   le formateur compare la note donnée par chaque équipe à la **médiane des
   trois autres** sur la même base, et suit cet écart d'un sprint à l'autre.
   Un écart systématique, dans un sens comme dans l'autre, signale un problème
   de calibration de l'équipe évaluatrice, pas une faute : il se traite au
   débrief, par un rappel des descripteurs et un exemple travaillé en commun.
   **Ce suivi ne produit aucune sanction, n'entre dans aucune note et ne figure
   sur aucune fiche d'équipe.**
6. **Du score à l'appréciation** : 21 à 30, niveau attendu ; 12 à 20, en
   cours ; moins de 12, ou un niveau « absent » après modération, constat
   consigné au livret. L'équipe évaluée peut demander une remédiation
   (réallocation du temps d'encadrement), consignée au livret : constat,
   objectif, réévaluation au sprint suivant.
7. **Publication** : les **quatre parties partagées** sont transmises à l'équipe
   évaluée le j10 après-midi, avec la revue de code et la soutenance. L'équipe
   évaluée renvoie une ligne par faiblesse : utile / pas utile / pas compris.
   Une relecture de note (procédure du barème oral, règle 11) peut modifier
   le score publié et le livret, jamais la sélection de la base commune déjà
   déployée.
8. **Destinataires et confidentialité** : la fiche est communiquée aux deux
   équipes, conservée au dossier de la promotion, et accompagne la base
   sélectionnée à la passation (avec les fiches de revue de code et de
   soutenance). **Elle n'est jamais transmise à l'entreprise marraine,
   ni en extrait ni en synthèse** ; le débrief des peer-reviews se tient hors
   sa présence ; la fiche ne conditionne pas la remise du résultat et n'en
   documente pas la qualité.
9. **Absence** : un membre absent est noté « non observé » au livret, son
   rôle est réattribué ; la fiche d'équipe est maintenue dès que trois
   membres sont présents ; à moins, le formateur fusionne avec une autre
   équipe ou substitue sa référence, et le consigne.
10. **Adaptations** (à l'entrée ou à tout moment) : l'adaptation porte sur la
   personne, jamais sur les seuils de la base. L'apprenant adapté tient P1 ou
   P3 en binôme et le chrono retenu est celui du binôme ; en P2, la médiane
   absorbe l'écart ; la timebox de l'équipe est étendue d'un tiers (remise
   tolérée jusqu'à 12h55). Consignée au livret seulement, jamais sur la
   fiche.
11. **Non-enregistrement** : la séance n'est pas enregistrée par défaut
    (volontariat strict du programme) ; la fiche écrite est l'unique trace,
    d'où son caractère obligatoire. Les fiches sont conservées au dossier de
    la promotion pendant la durée fixée dans l'information RGPD remise à
    l'entrée (même durée que les fiches de soutenance).
12. **Calibrage** : au sprint 1, le formateur ou le suppléant déroule le
    protocole complet sur deux bases ; l'écart avec les fiches est analysé et
    consigné (amélioration continue).

## 7. Le débrief : la phase réflexive

Au j10, **débrief de peer-review** (30 minutes, équipe évaluatrice, équipe
évaluée, formateur, hors présence de l'entreprise marraine) : chaque
faiblesse est confrontée à la réponse de l'équipe évaluée ; une personne
tirée au sort dans l'équipe évaluatrice montre à l'écran une faiblesse et le
fichier ; puis dix minutes où chaque équipe dit ce qu'elle reprend de la base
qu'elle a relue. Le formateur cite les deux fiches les plus utiles de la
promotion, et pourquoi. Chacun consigne ensuite au livret, dans sa
rétrospective écrite, trois lignes : « ce que j'ai appris en relisant une
autre base ». Cette phase est distincte de la pratique : on a fait, puis on
analyse ce qu'on a fait.

## 8. La fiche de peer-review (gabarit)

**Partie partagée**
- Une fiche **par base évaluée** (`peer-review-sprint-N-base-X.md`).
- Sprint · base évaluée · équipe évaluatrice · membres présents (émargement)
  · horodatages de début et de remise · mention pré-imprimée : *changement
  sonde : exercice d'évaluation, fictif, branche locale supprimée, rien n'est
  poussé.*
- **Ce qu'on reprendrait chez nous** (trois lignes, en tête).
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

**Partie individuelle (formateur seulement)** : binôme P1 · trois chercheurs
P2 · binôme P3 · rédacteur · initiale de l'auteur de chaque force et
faiblesse · observations (ancrage, justesse, utilité, conformité) ·
adaptations et absences (« non observé »).

## 9. Rappel : les dix critères de la grille de revue

1. Le problème est résolu (/8) · 2. Lisibilité et propreté (/2) ·
3. Nommage (/2) · 4. Structure et responsabilités (/4) · 5. Duplication et
abstraction (/2) · 6. Tests (/6) · 7. Robustesse et gestion d'erreurs (/4) ·
8. Documentation (/2) · 9. Idiomes du langage et du framework (/2) ·
10. Décisions d'architecture écrites (/3). Trois
cas de sécurité mettent le critère 7 (robustesse) à zéro (entrée qui devient du code,
secret en clair, authentification contournable) et ouvrent un malus d'au plus
cinq points par faille décidé par le formateur, sans bloquer la revue ni écarter la
base ; le reste de l'hygiène est noté au même critère. Et le barème récompense le jugement : **un écart justifié
par écrit vaut autant qu'une règle suivie**. Le détail et les exemples sont
dans la grille, remise avec ce guide.

## 10. À produire avant la première promotion, à affiner après

- Une **fiche exemple remplie** sur une base fictive, avec en face une
  version faible annotée (« ici : pas de chemin », « ici : ressenti sans
  preuve »), et l'évaluation du formateur sur la même base pour se calibrer.
- L'environnement de référence (versions, images pré-tirées) et le gabarit
  de fiche sur le canal de la promotion.
- Calibrer les seuils de temps (10 et 20 minutes) et la durée de séance
  (2h30 au sprint 1) sur de vraies bases ; vérifier que la sonde reste
  faisable sur les bases des sprints 4 et 5.
- Si la première promotion montre des notes stratégiques malgré la
  référence du formateur, sortir le /30 du calcul du rang (retour et livret
  seulement) à la promotion suivante.
