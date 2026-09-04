# Livret de progression individuel

> Le dossier individuel de compétences de l'apprenant, tenu par le formateur tout au long du parcours.

## Ce que le livret n'est pas

Ce n'est **ni une note, ni un rang, ni un cumul**. La décision du 24/08 tient :
aucune compétition individuelle, ce sont les bases de code qui sont mises en
compétition. Constater qu'une personne a atteint un objectif n'est pas la
classer. Le livret ne produit aucun classement et ne sert jamais à exclure :
la non-exclusion pour insuffisance de résultats reste absolue.

## Les quatre statuts

`non abordé` (l'objectif n'a pas encore été travaillé à ce stade du parcours) ·
`en cours` · `atteint` · `non atteint` (travaillé, pas encore acquis en fin de
parcours).

## Les douze objectifs et leur preuve naturelle

Chaque objectif possède déjà un dispositif qui le documente. Rien de nouveau à
inventer : il s'agit d'**attribuer individuellement** ce qui est déjà produit.

| # | Objectif | Où se trouve la preuve individuelle |
|---|---|---|
| 1 | Concevoir et implémenter une fonctionnalité de bout en bout | Contributions git sur une fonctionnalité complète |
| 2 | Écrire un code lisible et structuré, couvert par des tests | Constats de la grille de revue rapportés aux contributions |
| 3 | Reprendre une base écrite par une autre équipe et la faire évoluer | Sprint d'héritage de la base commune, cœur du modèle |
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

Établie **sans étape supplémentaire**, à partir de ce qui existe déjà au moment
de l'admission : le rendu du test d'entrée et la fiche d'entretien. Seuls les
objectifs 1 à 4 sont partiellement observables à ce moment ; les huit autres
partent en `non abordé`, ce qui est le constat honnête et non un déficit.

Le livret ouvre donc sur une photographie datée, signée par l'apprenant et par
le formateur, qui rend la progression mesurable au lieu d'être affirmée.

## Le rythme

Mise à jour **à chaque fin de sprint**, au même moment que les évaluations
collectives, par le formateur ou le suppléant. Trois éléments par objectif
touché : le statut, la preuve qui l'appuie, une phrase de commentaire.

**Auto-positionnement de l'apprenant** sur les mêmes objectifs, rempli avant
l'entretien de sprint. L'écart entre son auto-positionnement et le constat de
l'évaluateur est le matériau de l'échange.

## L'instrument de saisie

Une **grille d'observation individuelle** remplie par sprint, extension de la
grille B2 déjà prévue à l'item 3 des documents à produire. Elle porte les douze
objectifs, pas seulement la collaboration.

## Le bilan de fin de parcours

Reprend les douze objectifs, leur statut final, la ligne de départ en regard, et
une synthèse écrite. **C'est la pièce qui alimente l'attestation de fin de
formation**, obligatoire et individuelle.

Un objectif en `non atteint` en fin de parcours est écrit tel quel. Ce n'est ni
un échec ni une sanction : c'est ce qui rend le document crédible, pour
l'apprenant comme pour l'auditeur.

## Usage de l'historique git (tranché le 26/08)

L'attribution individuelle s'appuie en partie sur **l'historique git**, alors que
le [contrat de sortie du rapport de revue](contrat-rapport-revue.md) interdit
`git blame` à l'agent de revue. Les deux règles coexistent parce qu'elles ne
visent pas la même chose.

**Ce qui produit une note ignore les auteurs.** L'agent de revue note une base de
code, jamais une personne : l'interdiction protège l'évaluation collective de la
mise en cause individuelle.

**Ce qui constate une acquisition les identifie.** Le livret est formatif,
individuel, sans note, sans classement, et il ne peut pas servir à exclure. Il
lui faut donc savoir qui a écrit quoi.

La portée limitée de l'interdiction est écrite symétriquement dans le contrat de
sortie du rapport de revue.
