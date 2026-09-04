# La grille de revue de code

**35 points, publiés dès le premier jour.**

Chaque base de code est évaluée contre cette grille, **remise à tous dès le premier jour**. **L'agent de revue l'instruit, le formateur attribue les points, les pairs éprouvent la reprise en main de la base.** L'esprit de la grille tient en une question : _« voudrais-je hériter de cette base au prochain sprint ? »_ Et la question est concrète : à chaque sprint, une seule base continue et les 5 équipes repartent de celle-là. Ce sera la vôtre, ou celle d'une autre équipe.

## Les 10 critères

| # | Critère | Points |
|---|---|---|
| 01 | **Le problème est résolu**<br>_le sujet du sprint est traité de bout en bout_ | /8 |
| 02 | **Lisibilité & propreté**<br>_le code se lit sans effort_ | /2 |
| 03 | **Nommage**<br>_des noms qui disent ce que fait le code_ | /2 |
| 04 | **Structure & responsabilités**<br>_chaque chose à sa place, sans en rajouter_ | /4 |
| 05 | **Duplication & abstraction**<br>_quand factoriser, et quand s'en abstenir_ | /2 |
| 06 | **Tests**<br>_une règle du projet, un test_ | /6 |
| 07 | **Robustesse & gestion d'erreurs**<br>_les erreurs sont prévues et traitées_ | /4 |
| 08 | **Documentation**<br>_un README à jour, et qui dit vrai_ | /2 |
| 09 | **Idiomes du langage & du framework**<br>_utiliser le framework au lieu de le refaire_ | /2 |
| 10 | **Décisions d'architecture écrites**<br>_écrire pourquoi vous avez choisi ça_ | /3 |
| | **Total** | **/35** |

## Les 4 niveaux

- **Maîtrisé** (À bon escient) : La pratique est appliquée là où elle sert, **y compris là où elle est sciemment écartée** et où l'écart est justifié par écrit et défendable.
- **Solide** (Juste, avec un manque) : L'essentiel est là. Un point précis manque, et on sait lequel.
- **Fragile** (Inégal) : L'intention se voit mais elle est irrégulière, ou un écart pertinent n'est justifié nulle part.
- **Absent** (Nul ou nuisible) : Le critère n'est pas appliqué, ou appliqué mécaniquement au point de nuire : sur-abstraction, tests vides, découpage qui complique.

Chaque critère donne ses propres observations, dans son tableau.

## Le détail

### 01 · Le problème est résolu /8

Le sujet du sprint est traité **de bout en bout**, vérifié par les [**tests d'acceptation publiés avec le sujet**](https://agona.dev/consigne/#dod), identiques pour les 5 équipes.

Ces tests sont livrés au démarrage du sprint et vous les lancez quand vous voulez. Ils décrivent **le comportement attendu, pas la façon de l'obtenir** : l'architecture, le découpage et les choix techniques restent les vôtres, et ce sont les 9 autres critères qui les notent.

**Ce qu'on veut voir**
- Les tests d'acceptation passent sur la base gelée, cas d'erreur prévus compris.
- Aucun chemin critique ne plante sur une entrée valide.

**Ce qui fait chuter la note**
- Une partie du sujet reste non traitée, ou traitée « presque » : le cas nominal passe, un cas prévu échoue.
- Des tests d'acceptation modifiés ou contournés pour les faire passer.

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 8 | Tous les tests d'acceptation passent, cas d'erreur prévus compris |
| Solide | 5,5 | Le chemin nominal passe en entier ; un cas d'erreur prévu échoue |
| Fragile | 2,5 | Une partie du sujet n'est pas traitée, ou plusieurs tests d'acceptation échouent |
| Absent | 0 | Le sujet n'est pas traité, ou des tests d'acceptation ont été modifiés pour passer |

### 02 · Lisibilité & propreté /2

Ce critère note la densité cognitive : fonctions courtes, code mort supprimé, commentaires qui expliquent le **pourquoi**.

Le formatage ne rapporte pas de points : le linter s'en occupe déjà, et il tourne à chaque envoi de code. Ce qu'on regarde ici, c'est ce qu'aucun outil ne voit. Une fonction qu'il faut relire 2 fois pour comprendre fera perdre du temps à l'équipe qui reprendra la base, même si elle est parfaitement formatée.

**Ce qu'on veut voir**
- Des fonctions qui tiennent à l'écran, une idée par fonction, retour au plus tôt.

**Ce qui fait chuter la note**
- Des fonctions de 80 lignes, 4 niveaux d'imbrication, du code commenté laissé là.

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 2 | Fonctions courtes, une idée par fonction, aucun code mort ; les commentaires expliquent pourquoi |
| Solide | 1,5 | Lecture fluide dans l'ensemble ; quelques fonctions demandent une seconde lecture |
| Fragile | 0,5 | Fonctions longues ou profondément imbriquées, code commenté laissé en place |
| Absent | 0 | Le code doit être déchiffré ; les choix qui demandent une explication n'en ont pas, ou les commentaires répètent le code |

### 03 · Nommage /2

Ce critère note des noms qui disent l'intention, sans abréviation cryptique. L'exemple Après se lit sans deviner, et les types documentent en prime.

Un bon nom évite d'écrire le commentaire qui aurait expliqué le mauvais.

*Avant*

```
def calc(d, t):
    return d / t if t else 0
```

*Après*

```
def vitesse_moyenne_kmh(distance_km: float, duree_h: float) -> float:
    if duree_h == 0:
        return 0.0
    return distance_km / duree_h
```

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 2 | Les noms disent l'intention, sans abréviation à deviner ; les types complètent |
| Solide | 1,5 | Nommage juste dans l'ensemble, quelques noms vagues ou abrégés |
| Fragile | 0,5 | Beaucoup de noms génériques ; il faut lire le corps pour comprendre l'intention |
| Absent | 0 | Les noms n'informent pas, ou induisent en erreur sur ce que fait le code |

### 04 · Structure & responsabilités /4

On mesure surtout le **S** (une responsabilité par unité) et le **D** (dépendre d'abstractions, pas de détails). Le symptôme n°1 chez le débutant : la route qui valide, calcule et parle à la base en même temps.

On peut se tromper dans les 2 sens. Pas assez de structure : une fonction qui valide, calcule et écrit en base de données en même temps. [Trop de structure](https://agona.dev/consigne/#structure) : une interface qui n'apporte rien, ou un découpage qui oblige à ouvrir 4 fichiers pour suivre une seule règle. La question à se poser est toujours la même : est-ce que le métier est séparé de l'affichage et du stockage ?

*Avant : la route fait tout*

```
@app.post("/orders")
def create_order(payload: dict):
    if "items" not in payload:
        raise HTTPException(400, "items manquant")
    total = 0
    for it in payload["items"]:
        total += it["price"] * it["qty"]
    conn = psycopg2.connect(DSN)
    cur = conn.cursor()
    cur.execute("INSERT INTO orders (total) VALUES (%s)", (total,))
    conn.commit()
    return {"total": total}
```

*Après : chaque responsabilité à sa place*

```
# 1) Validation : le schéma Pydantic
class OrderItem(BaseModel):
    price: Decimal
    qty: int = Field(gt=0)

class OrderIn(BaseModel):
    items: list[OrderItem]

# 2) Métier : une fonction pure, testable sans base de données ni HTTP
def compute_total(items: list[OrderItem]) -> Decimal:
    return sum(item.price * item.qty for item in items)

# 3) Persistance : un repository injecté (dépendance abstraite)
@router.post("/orders", response_model=OrderOut, status_code=201)
def create_order(payload: OrderIn, repo: OrderRepository = Depends(get_order_repo)):
    total = compute_total(payload.items)
    return repo.create(total=total)
```

**Bénéfice concret :** `compute_total` se teste en une ligne, la route devient triviale, changer de base de données ne touche pas au métier.

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 4 | Le métier est séparé de l'affichage et du stockage ; aucune abstraction inutile |
| Solide | 2,5 | Séparation compréhensible ; une responsabilité importante reste mélangée, ou une abstraction complique la lecture |
| Fragile | 1,5 | Plusieurs responsabilités entremêlées, ou découpage qui oblige à ouvrir 4 fichiers pour suivre une règle |
| Absent | 0 | La logique métier est introuvable, ou l'architecture est construite pour un besoin qui n'existe pas |

### 05 · Duplication & abstraction /2

Ce critère note la duplication de **logique**. Copier-coller une mécanique, c'est un bug à corriger à N endroits ; le texte répété n'en relève pas.

Dupliquer n'est pas toujours une faute. 2 morceaux de code qui se ressemblent aujourd'hui mais qui vont évoluer séparément valent mieux séparés. Ce qu'on vous demande, c'est de l'écrire : une duplication avec un commentaire `# pourquoi :` est un choix, la même sans rien est un oubli. [À l'inverse](https://agona.dev/consigne/#structure), regrouper 2 choses qui n'ont rien à voir crée un problème que l'équipe suivante paiera. Une abstraction se juge à ce qu'elle apporte (isoler une dépendance, rendre un test possible), pas au nombre de ses implémentations.

*Avant : la même logique recopiée dans Users, Products, Orders…*

```
function Users() {
  const [data, setData] = useState<User[]>([])
  const [loading, setLoading] = useState(true)
  useEffect(() => {
    fetch("/api/users").then(r => r.json()).then(d => { setData(d); setLoading(false) })
  }, [])
  // …
}
```

*Après : une abstraction unique, réutilisée partout (et plus robuste)*

```
function useResource<T>(url: string) {
  const [data, setData] = useState<T | null>(null)
  const [loading, setLoading] = useState(true)
  const [error, setError] = useState<Error | null>(null)

  useEffect(() => {
    let alive = true
    fetch(url)
      .then(r => { if (!r.ok) throw new Error(`HTTP ${r.status}`); return r.json() })
      .then(d => { if (alive) setData(d) })
      .catch(e => { if (alive) setError(e) })
      .finally(() => { if (alive) setLoading(false) })
    return () => { alive = false }   // nettoyage : pas de setState après démontage
  }, [url])

  return { data, loading, error }
}
```

**Le signe qu'un refactor DRY était justifié :** il corrige souvent des bugs au passage (ici, la gestion d'erreur et une fuite de `setState`).

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 2 | Aucune logique recopiée ; les duplications restantes sont assumées par écrit |
| Solide | 1,5 | Une duplication de logique non justifiée, ou une factorisation qui rapproche deux choses sans rapport |
| Fragile | 0,5 | Plusieurs duplications de logique, ou une abstraction qui n'apporte rien |
| Absent | 0 | La même mécanique est recopiée à N endroits, sans trace d'un choix |

### 06 · Tests /6

Ce critère note la couverture des [**règles métier et de leurs cas limites**](https://agona.dev/consigne/#tests), en priorité là où une erreur coûte cher (argent, données, sécurité, action irréversible), et des tests qui tournent d'une seule commande.

La couverture ne dit pas si vos tests sont bons. Elle dit seulement quelles lignes ne sont jamais exécutées pendant les tests : on peut atteindre 100 % sans rien vérifier du tout. Alors ne visez pas un pourcentage. Partez des règles du projet, par exemple « une commande vide est refusée » ou « une remise ne dépasse jamais 50 % », et écrivez un test par règle, puis un test par cas limite. Un seul gros test qui rejoue tout le parcours ne suffit pas : quand il casse, il ne dit pas où.

```
# Test unitaire du métier : rapide, sans base de données ni réseau
def test_compute_total_somme_prix_fois_quantite():
    items = [OrderItem(price=Decimal("2.50"), qty=3),
             OrderItem(price=Decimal("1.00"), qty=1)]
    assert compute_total(items) == Decimal("8.50")

# Test d'API : le contrat HTTP est-il respecté ?
def test_create_order_refuse_quantite_negative(client):
    resp = client.post("/orders", json={"items": [{"price": "2.5", "qty": -1}]})
    assert resp.status_code == 422        # Pydantic rejette qty <= 0
```

**Ce qu'on veut voir**
- Un test par règle métier, un test par cas limite (entrée vide, zéro, négatif).

**Ce qui fait chuter la note**
- Seul le « chemin heureux » est testé, ou lancer les tests demande un setup manuel.
- Des tests sur les accesseurs, les objets de transport ou le framework lui-même.
- **Un test sans assertion utile** : pire qu'une absence de test, il donne une fausse assurance et gonfle une couverture qui ne veut alors plus rien dire.

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 6 | Les règles métier et leurs cas limites sont couverts au niveau de test qui convient ; la logique métier se teste sans base de données ni réseau ; la suite tourne en une commande |
| Solide | 4 | Les règles principales sont couvertes ; des cas limites manquent, ou le lancement demande un pas manuel |
| Fragile | 2 | Seul le chemin nominal est testé, ou des tests sans assertion utile |
| Absent | 0 | Pas de test sur la logique métier, ou la suite ne tourne pas |

### 07 · Robustesse & gestion d'erreurs /4

Ce critère note des erreurs **attrapées au bon niveau**, avec le bon statut, sans fuite d'information sensible ni `except` fourre-tout.

L'hygiène de sécurité se note ici : une image Docker non figée, une dépendance obsolète, des droits trop larges. Les 3 failles lourdes (entrée qui devient du code, secret en clair, authentification contournable) mettent ce critère à zéro.

*Avant : avale tout, masque la cause, renvoie un 200 mensonger*

```
try:
    user = repo.get(user_id)
    return user
except Exception:
    return {"error": "oops"}
```

*Après : cas explicites, statuts corrects, message sûr*

```
user = repo.get(user_id)
if user is None:
    raise HTTPException(status_code=404, detail="Utilisateur introuvable")
return user
```

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 4 | Erreurs attrapées au bon niveau, statuts corrects, aucune fuite d'information |
| Solide | 2,5 | Cas d'erreur traités dans l'ensemble ; un except large, ou un message qui en dit trop |
| Fragile | 1,5 | Erreurs avalées, statuts faux, ou hygiène négligée : image non figée, dépendance obsolète |
| Absent | 0 | Aucune gestion d'erreur, ou l'une des 3 failles lourdes est vérifiée |

### 08 · Documentation /2

Ce critère note la documentation qui accompagne la base, et sa véracité.

**Ce qu'on veut voir**
- README qui couvre le lancement et l'architecture, document de reprise à jour, commentaires qui expliquent le pourquoi.
- Procédure de lancement documentée, dépendances épinglées, limites connues signalées.

**Ce qui fait chuter la note**
- Doc absente ou mensongère (pire que pas de doc), versions flottantes, « ça marche sur ma machine ».

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 2 | README à jour et exact, architecture expliquée, limites connues signalées |
| Solide | 1,5 | README utile mais incomplet, ou une section décalée par rapport au code |
| Fragile | 0,5 | Documentation minimale, ou qui décrit un état antérieur du dépôt |
| Absent | 0 | Pas de documentation, ou une documentation qui dit faux |

### 09 · Idiomes du langage & du framework /2

Le code utilise le langage et le framework **tels qu'ils sont conçus**, au lieu de réinventer ce qu'ils fournissent déjà, et n'ajoute pas une dépendance pour ce que la bibliothèque standard fait. Beaucoup de manières de faire la même chose se valent ; certaines pas du tout.

On vous demande de vérifier, avant d'écrire, si le langage ou le framework le fait déjà. Refaire à la main ce qui existe, c'est du code en plus à maintenir et des bugs déjà corrigés ailleurs qu'on réintroduit.

*Avant : la validation réécrite à la main, que Pydantic fait déjà*

```
@app.post("/users")
def create_user(payload: dict):
    if "email" not in payload or "@" not in payload["email"]:
        raise HTTPException(400, "email invalide")
    if not isinstance(payload.get("age"), int) or payload["age"] < 0:
        raise HTTPException(400, "age invalide")
    return repo.create(payload["email"], payload["age"])
```

*Après : le framework valide, sérialise et documente pour vous*

```
class UserIn(BaseModel):
    email: EmailStr
    age: int = Field(ge=0)

@app.post("/users", status_code=201)
def create_user(payload: UserIn, repo: UserRepository = Depends(get_user_repo)):
    return repo.create(payload.email, payload.age)
```

**Ce qu'on veut voir**
- Validation par le schéma, injection par `Depends`, hooks React pour l'état et les effets, requêtes via l'ORM ou paramétrées, utilitaires standard (dates, parsing).

**Ce qui fait chuter la note**
- Validation à la main, état global bricolé, un utilitaire réécrit alors que la stdlib le fournit, une dépendance lourde pour une fonction triviale, le framework contourné plutôt qu'utilisé.

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 2 | Le framework et la bibliothèque standard sont utilisés pour ce qu'ils font |
| Solide | 1,5 | Usage globalement idiomatique ; un utilitaire réécrit alors qu'il existe déjà |
| Fragile | 0,5 | Validation à la main, état bricolé, dépendance lourde pour une fonction triviale |
| Absent | 0 | Le framework est contourné plutôt qu'utilisé |

### 10 · Décisions d'architecture écrites /3

Les décisions structurantes du sprint sont écrites, avec leurs **alternatives** et leurs **conséquences**, dans des fichiers numérotés placés dans [`docs/adr/`](https://agona.dev/consigne/#pourquoi).

*Le format attendu, 10 lignes suffisent*

```
# 0004 - Un repository pour l'accès aux commandes

## Contexte
Les requêtes SQL étaient écrites dans les routes HTTP : le métier
n'était pas testable sans base de données.

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

**Ce qu'on veut voir**
- Toute décision qui engage les sprints suivants, ou qui avait plusieurs options raisonnables, est écrite ; les alternatives sont réelles ; les conséquences incluent ce que la décision coûte.
- Les écarts aux critères 04 et 05 sont justifiés là, ou par un commentaire `# pourquoi :` à l'endroit du choix.

**Ce qui fait chuter la note**
- Un changement d'architecture sans trace écrite, un ADR rédigé après coup pour cocher la case, des décisions annoncées à l'oral et introuvables dans le dépôt.

Écrire ce que vous avez écarté et pourquoi prend 10 lignes, et rend votre architecture lisible pour celui qui arrive après. C'est aussi la seule façon de montrer votre raisonnement sans passer par l'oral.

| Niveau | Points | On observe |
|---|---|---|
| Maîtrisé | 3 | Les décisions engageantes sont écrites, avec des alternatives réelles et leur coût |
| Solide | 2 | Décisions écrites, mais alternatives absentes ou conséquences non dites |
| Fragile | 1 | Des décisions structurantes sans trace, ou des ADR rédigés après coup |
| Absent | 0 | Aucune trace écrite des choix structurants |

## Les 3 failles lourdes

**Une entrée utilisateur qui devient du code** (SQL concaténé, commande shell assemblée), **un secret en clair** dans le dépôt ou dans l'historique (le dépôt est publié à la fin du sprint), **une authentification contournable** : le critère 07 tombe à zéro et la faille est nommée dans le rapport de revue et dans la fiche de passation. **La revue reste complète**, les 9 autres critères sont notés, et **la base peut devenir la base commune** si elle est la meilleure : la faille est alors héritée comme le reste, et sa correction devient le premier chantier du sprint suivant. La [consigne de développement](https://agona.dev/consigne/#securite) détaille comment les éviter et comment les corriger. Le formateur vérifie chaque signalement automatique : c'est lui qui décide.

**Le malus.** Le critère 07 tombe à zéro, soit 4 points perdus. Le formateur peut en retirer 5 de plus par faille, en motivant sa décision par écrit, selon la gravité de la faille et selon qu'elle était évitable. Une base qui porte les 3 failles perd donc **au maximum 19 points sur 35** : 4 pour le critère, 15 de malus. Le total ne descend jamais sous zéro.

**Une exception, le secret.** Une requête se réécrit, une authentification se répare. Un secret commité, lui, reste dans l'historique, et l'historique est publié. Il déclenche donc une **procédure de rotation** : la clé est révoquée et remplacée immédiatement, et le fait est consigné. Avant la publication du dépôt, la valeur est effacée de l'historique et remplacée par une mention du retrait. **L'effacement garde tous les commits**, avec leurs messages, leurs auteurs et leurs dates : seule la valeur du secret disparaît.

## L'auto-vérification, avant de se présenter

Avant chaque revue, l'équipe vérifie elle-même sa base contre cette checklist, épaulée par l'intégration continue. C'est un **outil d'apprentissage** : la base est évaluée dans l'état où elle est, et la revue a lieu dans tous les cas.

**Fonctionnel c'est le critère 01, 8 points**
- Les tests d'acceptation du sprint passent sur la base gelée.
- Le problème du sprint est résolu de bout en bout, pas de « presque ».
- Aucun chemin critique ne plante sur une entrée valide.
- Les cas d'erreur prévus renvoient un comportement défini, pas un crash.

**Code**
- Le code compile et démarre sans warning bloquant.
- Aucun secret en dur : tout passe en variable d'environnement.
- Aucun TODO ni code mort laissé sans justification.
- Le linter, le formatter et l'analyse statique passent (Ruff/Black, ESLint/Prettier).

**Le dépôt modèle**
- Tests dans `tests/unit/`, `tests/integration/`, `tests/e2e/`.
- Décisions dans `docs/adr/`, justifications locales préfixées `# pourquoi :`.
- Ces emplacements permettent de mesurer 5 bases à la même aune.

**Tests**
- La logique métier est couverte par des tests automatisés qui passent.
- Au moins un test par cas limite identifié.
- Les tests tournent d'une seule commande, sans setup manuel.

**Reprenabilité**
- README : lancer le projet et les tests en moins de 5 minutes.
- Le projet démarre via une seule commande.
- Un développeur extérieur comprend l'architecture depuis le README.
