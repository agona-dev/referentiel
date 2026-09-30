# Livret de progression individuel

> Le dossier individuel de compétences de l'apprenant, tenu par le formateur tout au long du parcours.

## Ce que le livret est

Le livret est un constat individuel, objectif par objectif, sans note, sans
rang, sans cumul et sans pouvoir d'exclusion. La décision du 24/08 tient : la
compétition se joue entre les bases de code, et entre elles seulement. La
non-exclusion pour insuffisance de résultats reste absolue.

## Les 4 statuts

Les statuts sont `non abordé` (l'objectif reste à travailler à ce stade du
parcours), `en cours`, `atteint` et `non atteint` (travaillé, encore à
acquérir en fin de parcours).

## Les 12 objectifs et leur preuve naturelle

Chaque objectif possède déjà un dispositif qui le documente. Le livret
**attribue individuellement** ce que ces dispositifs produisent déjà.

| # | Objectif | Où se trouve la preuve individuelle |
|---|---|---|
| 1 | Concevoir et implémenter une fonctionnalité de bout en bout | Contributions git sur une fonctionnalité complète |
| 2 | Écrire un code lisible et structuré, couvert par des tests | Constats de la grille de revue rapportés aux contributions |
| 3 | Reprendre une base écrite par une autre équipe et la faire évoluer | Sprint d'héritage de la base commune |
| 4 | Travailler à 5 sur la même base de code | Historique git, pull requests, revues croisées |
| 5 | Industrialiser une application | Dockerfile, démarrage en une commande, documentation de reprise |
| 6 | Réflexes de sécurité élémentaires | Critère sécurité gradué de la grille de revue |
| 7 | Défendre des choix techniques à l'oral | Observation en soutenance, sprint par sprint |
| 8 | Évaluer le travail d'un pair | Fiches de peer-review rédigées par la personne |
| 9 | Diagnostiquer et résoudre un dysfonctionnement | Épreuves scriptées : bug injecté, diagnostic de performance |
| 10 | Exploiter une application en production | Épreuve scriptée : incident de production |
| 11 | Comprendre un problème métier avant d'écrire du code | Critère C1 de la soutenance, sprint par sprint |
| 12 | Arbitrer un choix technique et l'assumer | ADR versionnés au dépôt et critère C2 de la soutenance |

## La ligne de départ

La ligne de départ est établie **sans étape supplémentaire**, à partir de ce
qui existe déjà au moment de l'admission : le rendu du test d'entrée et la
fiche d'entretien. Seuls les objectifs 1 à 4 sont partiellement observables à
ce moment. Les 8 autres partent en `non abordé`.

Le livret ouvre donc sur une photographie datée, signée par l'apprenant et par
le formateur, qui rend la progression mesurable.

## Le rythme

Le livret est mis à jour **à chaque sprint** par le formateur. Chaque objectif
touché reçoit 3 éléments : le statut, la preuve qui l'appuie, une phrase de
commentaire. L'entretien de sprint se tient le j8, 15 minutes par apprenant. Le
constat reste provisoire jusqu'au j10 à 17h00, où le formateur l'arrête, au
même moment que les évaluations collectives. Le suppléant lit les livrets, sans
les remplir.

L'apprenant remplit un **auto-positionnement** sur les mêmes objectifs. Il est
ouvert dès le j1 du sprint et modifiable jusqu'à l'ouverture de l'entretien. Le
formateur le découvre à cette ouverture. L'écart entre cet auto-positionnement
et le constat de l'évaluateur est le matériau de l'échange. S'il n'est pas rendu, l'entretien porte sur le seul constat du
formateur, et la page du sprint indique « auto-positionnement non rendu ».

L'apprenant écrit sa **rétrospective personnelle** du j10 à 9h00 au samedi à
00h00. Le formateur lit les 2 rétrospectives, la personnelle et celle de
l'équipe, et l'apprenant le sait dès le formulaire. Une rétrospective vide
s'affiche « non écrite ».

La page du sprint (constat final, rétrospective, 3 lignes de la peer-review,
PDF) **se fige le samedi à 00h00**. Si l'entretien n'a pas eu lieu, le
formateur le tient dès que possible, et la page se fige à la fin de
l'entretien. Une erreur de saisie du formateur se corrige : il rouvre la page,
corrige, la page se refige et son PDF remplace l'ancien.

La page du sprint montre aussi les **observations individuelles** :
l'observation de soutenance (C3) si l'apprenant a été tiré, ou « non observé »,
et celle de sa revue en peer-review. L'apprenant les commente à tout moment,
même après que la page est figée, sans effet sur les notes.

## Le sprint suivant

À l'entretien de sprint, après le constat, l'apprenant et l'évaluateur fixent
ensemble le sprint suivant, en 2 lignes écrites au livret : les **objectifs
prioritaires** parmi les 12, les **aménagements** s'il y en a (ceux à la portée
du format sont listés dans la procédure d'accueil des publics en situation de
handicap). Le livret dit ainsi où en est la personne, et ce qui
est ajusté pour elle.

Un objectif prioritaire dont le statut reste le même qu'au sprint d'avant est
signalé au formateur : c'est un objectif « en arrière ». Le sprint 1, sans
objectif prioritaire, n'a pas ce signal. Si la situation persiste, le suppléant
la reprend avec le formateur (`/encadrement/`).

## L'instrument de saisie

Une **grille d'observation individuelle** est remplie par sprint. Elle étend la
grille B2 déjà prévue à l'item 3 des documents à produire et porte les 12
objectifs.

Le **gabarit du livret** est l'instrument remis à chaque apprenant :
`agona-livret-progression-gabarit.pdf`, 8 pages (identité et mode d'emploi,
ligne de départ, une page par sprint avec le sprint suivant, bilan), généré par
`scripts/gabarit_livret.py` depuis la table des objectifs de ce document. Le
livret se tient dans l'espace : l'apprenant le lit dans « Mon livret », et
chaque page figée produit son PDF. Le gabarit documente ce format.

## Le bilan de fin de parcours

Le bilan reprend les 12 objectifs, leur statut final, la ligne de départ en
regard, et une synthèse écrite. Le formateur le pré-rédige à partir du livret.
L'apprenant écrit sa partie dès le j1 du sprint 5, jusqu'à l'ouverture de
l'entretien de fin de parcours. Au sprint 5, le statut final qu'il donne tient
lieu d'auto-positionnement.

L'**entretien de fin de parcours** se tient le j8 du sprint 5, 15 minutes par
apprenant, à la place de l'entretien de sprint. Il relit et complète le bilan.
L'apprenant puis le formateur le signent dans l'espace, par signature
électronique simple, et le PDF signé est figé. **Ce bilan alimente
l'attestation de fin de formation**, obligatoire et individuelle.

Un objectif en `non atteint` en fin de parcours est écrit tel quel.

## Usage de l'historique git (tranché le 26/08)

L'attribution individuelle s'appuie en partie sur **l'historique git**. Le
[contrat de sortie du rapport de revue](contrat-rapport-revue.md) interdit
`git blame` à l'agent de revue, dont la note porte sur la base de code de l'équipe.
Le livret est formatif, individuel, sans note, sans classement et sans pouvoir
d'exclusion, et il identifie les auteurs. La portée limitée de l'interdiction
est écrite symétriquement dans le contrat de sortie du rapport de revue.
