**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Swift <img src="./assets/swift.svg" width="40" height="40" />
</h1>

<h2>Les questions et réponses les plus populaires en entretien Swift</h2>

<details>
<summary>1. À quoi sert principalement Swift dans le développement moderne ?</summary>

#### Swift

Swift est principalement utilisé pour créer des applications pour les plateformes Apple :

- iOS
- macOS
- watchOS
- tvOS
- visionOS

Il est principalement utilisé pour :

- Le développement d'applications mobiles
- Le développement natif pour les plateformes Apple
- Le développement backend avec des frameworks comme Vapor
- Les outils en ligne de commande et les scripts

Swift est apprécié pour sa sécurité, ses performances et sa syntaxe moderne.

</details>

<details>
<summary>2. Quelle est la différence entre `let` et `var` ?</summary>

#### Swift

`let` crée une constante, et `var` crée une variable.

- Utilisez `let` lorsque la valeur ne doit pas changer.
- Utilisez `var` lorsque la valeur peut changer plus tard.

```swift
let name = "Alice"
var age = 25

age = 26 // Autorisé
// name = "Bob" // Erreur
```

Utiliser `let` par défaut rend le code plus sûr et plus facile à comprendre.

</details>

<details>
<summary>3. Expliquez la type inference en Swift.</summary>

#### Swift

La type inference signifie que Swift peut déterminer automatiquement le type
d'une valeur à partir des données assignées, donc vous n'avez pas toujours
besoin d'écrire le type explicitement.

```swift
let title = "Swift"      // String
let year = 2025          // Int
let isActive = true      // Bool
```

Vous pouvez toujours préciser le type manuellement si vous voulez exprimer plus clairement votre intention :

```swift
let score: Double = 99
```

La type inference raccourcit le code tout en conservant la sûreté des types.

</details>

<details>
<summary>4. Que sont les optionals et pourquoi sont-ils importants ?</summary>

#### Swift

Un optional est un type qui peut contenir soit :

- une valeur
- `nil`

Les optionals sont importants parce qu'ils rendent explicite l'absence de
valeur et aident à éviter les crashs à l'exécution dus à des données manquantes.

```swift
var nickname: String? = "Sam"
nickname = nil
```

Sans les optionals, Swift ne pourrait pas représenter en toute sécurité des
valeurs qui peuvent être absentes, par exemple :

- Les saisies utilisateur
- Les champs des réponses réseau
- Les valeurs de base de données
- Les URLs dont l'initialisation peut échouer

</details>

<details>
<summary>5. Quelle est la différence entre optional binding et force unwrapping ?</summary>

#### Swift

L'optional binding extrait en toute sécurité la valeur d'un optional.
Le force unwrapping extrait directement la valeur et provoque un crash si
l'optional vaut `nil`.

#### Optional binding

```swift
let name: String? = "Alice"

if let unwrappedName = name {
    print(unwrappedName)
}
```

#### Force unwrapping

```swift
let name: String? = "Alice"
print(name!)
```

Utilisez l'optional binding dans la plupart des cas.
Utilisez le force unwrapping uniquement lorsque vous êtes totalement sûr que la valeur n'est pas `nil`.

</details>

<details>
<summary>6. Qu'est-ce que l'optional chaining et quand l'utiliser ?</summary>

#### Swift

L'optional chaining est une manière d'accéder en toute sécurité aux propriétés,
méthodes ou subscripts d'une valeur optionnelle.

Si l'optional vaut `nil`, toute l'expression renvoie `nil` au lieu de provoquer
un crash.

```swift
class User {
    var address: Address?
}

class Address {
    var city: String = "London"
}

let user = User()
let city = user.address?.city
```

Utilisez l'optional chaining lorsque vous travaillez avec des valeurs
optionnelles imbriquées, en particulier dans :

- Les objets de modèle
- Les réponses d'API
- Les références d'UI qui peuvent ne pas exister

</details>

<details>
<summary>7. Qu'est-ce que l'opérateur nil coalescing ?</summary>

#### Swift

L'opérateur nil coalescing est `??`.
Il fournit une valeur par défaut lorsqu'un optional vaut `nil`.

```swift
let username: String? = nil
let displayName = username ?? "Guest"
```

Dans cet exemple, `displayName` devient `"Guest"`.

Utilisez `??` lorsque vous souhaitez une valeur de remplacement pour un optional.

</details>

<details>
<summary>8. Que sont les tuples et quand faut-il les utiliser ?</summary>

#### Swift

Un tuple est un groupe de valeurs combinées en une seule valeur composée.

```swift
let person = ("Alice", 28)
```

Vous pouvez aussi nommer les valeurs d'un tuple :

```swift
let httpResponse = (statusCode: 200, message: "OK")
print(httpResponse.statusCode)
```

Utilisez les tuples pour des valeurs groupées temporaires, par exemple :

- Retourner plusieurs valeurs depuis une fonction
- Représenter un petit ensemble de données liées
- Stocker des données locales temporaires

Pour des données plus complexes ou réutilisables, préférez `struct` ou `class`.

</details>

<details>
<summary>9. Quels sont les principaux types de collections en Swift ?</summary>

#### Swift

Les principaux types de collections en Swift sont :

1. `Array`
2. `Set`
3. `Dictionary`

#### Array

Stocke une liste ordonnée de valeurs.

```swift
let numbers = [1, 2, 3]
```

#### Set

Stocke des valeurs uniques non ordonnées.

```swift
let uniqueNumbers: Set = [1, 2, 3]
```

#### Dictionary

Stocke des paires clé-valeur.

```swift
let userAges = ["Alice": 25, "Bob": 30]
```

Ces collections sont constamment utilisées en développement Swift.

</details>

<details>
<summary>10. Quelle est la différence entre Array, Set et Dictionary ?</summary>

#### Swift

La différence réside dans la manière dont ils stockent les données et y accèdent.

| Type | Stocke | Ordre | Unicité | Accès |
| --- | --- | --- | --- | --- |
| `Array` | Une liste de valeurs | Ordonné | Doublons autorisés | Par index |
| `Set` | Des valeurs uniques | Non ordonné | Doublons non autorisés | Par recherche de valeur |
| `Dictionary` | Des paires clé-valeur | Non ordonné | Les clés doivent être uniques | Par clé |

#### Exemple

```swift
let array = ["a", "b", "a"]
let set: Set = ["a", "b", "a"]
let dictionary = ["name": "Alice", "city": "Paris"]
```

- `Array` conserve l'ordre et peut contenir des doublons.
- `Set` supprime les doublons.
- `Dictionary` associe des clés à des valeurs.

</details>

<details>
<summary>11. Que sont les value types et les reference types ?</summary>

#### Swift

Les value types sont copiés lorsqu'ils sont assignés ou transmis.
Les reference types partagent la même instance.

#### Value types

- `struct`
- `enum`
- `tuple`

```swift
struct User {
    var name: String
}

var user1 = User(name: "Alice")
var user2 = user1
user2.name = "Bob"

print(user1.name) // Alice
print(user2.name) // Bob
```

#### Reference types

- `class`

```swift
class Person {
    var name: String

    init(name: String) {
        self.name = name
    }
}

let person1 = Person(name: "Alice")
let person2 = person1
person2.name = "Bob"

print(person1.name) // Bob
print(person2.name) // Bob
```

Utilisez les value types par défaut, sauf si un état mutable partagé est nécessaire.

</details>

<details>
<summary>12. Quelle est la différence entre `struct` et `class` ?</summary>

#### Swift

La principale différence est que `struct` est un value type et `class` est un
reference type.

| Caractéristique | `struct` | `class` |
| --- | --- | --- |
| Type | Value type | Reference type |
| Comportement à la copie | Copié à l'assignation | Partagé par référence |
| Héritage | Non pris en charge | Pris en charge |
| Deinitializer | Non pris en charge | Pris en charge |
| Vérification d'identité | Non | Oui avec `===` |

Utilisez `struct` dans la plupart des cas.
Utilisez `class` lorsque vous avez besoin de :

- Un état mutable partagé
- L'héritage
- Une sémantique d'identité

</details>

<details>
<summary>13. Qu'est-ce que copy-on-write ?</summary>

#### Swift

Copy-on-write est une optimisation où une valeur n'est pas copiée immédiatement.
Swift ne crée une vraie copie que lorsqu'une des valeurs est modifiée.

Cela est couramment utilisé par les collections standard telles que :

- `Array`
- `Dictionary`
- `Set`

```swift
var numbers1 = [1, 2, 3]
var numbers2 = numbers1

numbers2.append(4)

print(numbers1) // [1, 2, 3]
print(numbers2) // [1, 2, 3, 4]
```

Cela offre la sécurité des value types avec de bonnes performances.

</details>

<details>
<summary>14. Qu'est-ce que l'immutability et pourquoi est-elle importante ?</summary>

#### Swift

L'immutability signifie qu'une valeur ne peut pas être modifiée après sa création.

En Swift, les valeurs déclarées avec `let` sont immuables.

```swift
let name = "Alice"
// name = "Bob" // Erreur
```

L'immutability est importante parce qu'elle :

- Rend le code plus sûr
- Réduit les bugs
- Rend l'état plus facile à suivre
- Aide à raisonner sur la concurrence

Utilisez des valeurs immuables par défaut, et ne rendez les choses mutables qu'en cas de besoin.

</details>

<details>
<summary>15. Que sont les computed properties ?</summary>

#### Swift

Une computed property ne stocke pas une valeur directement.
À la place, elle calcule la valeur à chaque accès.

```swift
struct Rectangle {
    var width: Double
    var height: Double

    var area: Double {
        width * height
    }
}
```

Les computed properties peuvent aussi avoir `get` et `set` :

```swift
struct Square {
    var side: Double

    var area: Double {
        get { side * side }
        set { side = sqrt(newValue) }
    }
}
```

Utilisez les computed properties lorsqu'une valeur dépend d'autres valeurs.

</details>

<details>
<summary>16. Que sont les property observers (`willSet` / `didSet`) ?</summary>

#### Swift

Les property observers vous permettent de réagir lorsqu'une stored property change de valeur.

- `willSet` s'exécute avant que la nouvelle valeur soit stockée
- `didSet` s'exécute après que la nouvelle valeur soit stockée

```swift
class Profile {
    var name: String = "" {
        willSet {
            print("New value: \(newValue)")
        }
        didSet {
            print("Old value: \(oldValue)")
        }
    }
}
```

Utilisez-les lorsque vous devez :

- Journaliser les changements
- Mettre à jour l'UI
- Déclencher des effets secondaires après un changement de valeur

</details>

<details>
<summary>17. Que sont les lazy properties ?</summary>

#### Swift

Une lazy property n'est initialisée que lorsqu'elle est utilisée pour la première fois.

Elle est déclarée avec le mot-clé `lazy` et doit être une `var`.

```swift
class DataManager {
    lazy var formatter: DateFormatter = {
        let formatter = DateFormatter()
        formatter.dateStyle = .medium
        return formatter
    }()
}
```

Utilisez les lazy properties lorsque :

- L'initialisation est coûteuse
- La propriété peut ne jamais être utilisée
- La propriété dépend de `self` après l'initialisation

</details>

<details>
<summary>18. Que sont les key paths en Swift ?</summary>

#### Swift

Les key paths sont des références typées et sûres vers des propriétés.
Ils vous permettent d'accéder indirectement à une propriété.

```swift
struct User {
    let name: String
}

let keyPath = \User.name
let user = User(name: "Alice")

print(user[keyPath: keyPath]) // Alice
```

Les key paths sont utiles pour :

- Le tri
- Le mapping
- Les API génériques
- L'observation ou l'accès à des propriétés imbriquées de manière sûre

</details>

<details>
<summary>19. Qu'est-ce que le type casting (`is`, `as`, `as?`, `as!`) ?</summary>

#### Swift

Le type casting est utilisé pour vérifier ou convertir le type d'une valeur à l'exécution.

- `is` vérifie si une valeur est d'un type spécifique
- `as` effectue un upcast vers un supertype
- `as?` effectue un downcast sûr et renvoie un optional
- `as!` effectue un downcast forcé et provoque un crash en cas d'échec

```swift
class Animal {}
class Dog: Animal {}

let animal: Animal = Dog()

print(animal is Dog) // true

let dog1 = animal as? Dog // Sûr
let dog2 = animal as! Dog // Dangereux si le type est incorrect
```

Utilisez `as?` dans la plupart des cas.
Utilisez `as!` seulement lorsqu'un échec est impossible.

</details>

<details>
<summary>20. Quelle est la différence entre `==` et `===` ?</summary>

#### Swift

`==` vérifie l'égalité de valeur.
`===` vérifie l'identité de référence.

#### `==`

Utilisé pour comparer si deux valeurs sont égales.

```swift
let a = 5
let b = 5

print(a == b) // true
```

#### `===`

Utilisé uniquement avec des classes pour vérifier si deux références pointent
vers la même instance.

```swift
class User {}

let user1 = User()
let user2 = user1
let user3 = User()

print(user1 === user2) // true
print(user1 === user3) // false
```

Donc :

- `==` signifie « même valeur »
- `===` signifie « même objet en mémoire »

</details>

<details>
<summary>21. Comment fonctionne `switch` en Swift (pattern matching) ?</summary>

#### Swift

`switch` en Swift est puissant et prend en charge le pattern matching.
Il peut correspondre à :

- Des valeurs exactes
- Plusieurs valeurs
- Des plages
- Des tuples
- Des cas d'enum
- Des valeurs avec conditions

Contrairement à certains langages, `switch` en Swift doit être exhaustif.
Cela signifie que chaque cas possible doit être géré.

```swift
let number = 7

switch number {
case 1:
    print("One")
case 2...9:
    print("Between 2 and 9")
default:
    print("Other")
}
```

Le `switch` de Swift est souvent utilisé parce qu'il est plus sûr et plus expressif qu'une longue chaîne de `if`.

</details>

<details>
<summary>22. Qu'est-ce que `fallthrough` et quand faut-il l'éviter ?</summary>

#### Swift

`fallthrough` fait continuer l'exécution d'un `case` au `case` suivant dans un
`switch`.

Par défaut, Swift ne passe pas automatiquement au cas suivant.

```swift
let number = 1

switch number {
case 1:
    print("One")
    fallthrough
case 2:
    print("Two")
default:
    break
}
```

Sortie :

```swift
One
Two
```

Évitez `fallthrough` dans la plupart des cas parce que :

- Cela rend la logique moins claire
- Cela peut provoquer un comportement inattendu
- Il existe généralement des alternatives plus propres

Utilisez-le uniquement lorsque vous voulez intentionnellement exécuter aussi le `case` suivant.

</details>

<details>
<summary>23. Qu'est-ce qu'une instruction `guard` et quand l'utiliser ?</summary>

#### Swift

`guard` est utilisé pour une sortie anticipée.
Il vérifie une condition, et si cette condition échoue, l'exécution doit quitter
le scope courant.

```swift
func printName(_ name: String?) {
    guard let name = name else {
        print("Name is missing")
        return
    }

    print(name)
}
```

Utilisez `guard` lorsque :

- Une valeur requise est absente
- Les préconditions ne sont pas remplies
- Vous voulez éviter un code trop imbriqué

Il rend le code plus plat et plus lisible.

</details>

<details>
<summary>24. Quelle est la différence entre `if let` et `guard let` ?</summary>

#### Swift

Les deux sont utilisés pour l'optional binding, mais ils s'utilisent différemment.

| Caractéristique | `if let` | `guard let` |
| --- | --- | --- |
| Usage principal | Branche conditionnelle | Sortie anticipée |
| Portée de la valeur déballée | À l'intérieur du bloc `if` | Après l'instruction `guard` |
| Lisibilité | Bien pour les vérifications courtes | Mieux pour les conditions obligatoires |

#### `if let`

```swift
if let name = optionalName {
    print(name)
}
```

#### `guard let`

```swift
guard let name = optionalName else {
    return
}

print(name)
```

Utilisez `if let` pour un traitement optionnel dans une branche locale.
Utilisez `guard let` lorsque la valeur est requise pour le reste de la fonction.

</details>

<details>
<summary>25. Qu'est-ce qu'une half-open range ?</summary>

#### Swift

Une half-open range inclut la borne inférieure mais exclut la borne supérieure.

Elle utilise `..<`

```swift
for i in 0..<5 {
    print(i)
}
```

Sortie :

```swift
0
1
2
3
4
```

Les half-open ranges sont utiles pour :

- Les boucles
- L'indexation des tableaux
- Les situations où la valeur de fin ne doit pas être incluse

</details>

<details>
<summary>26. Qu'est-ce qu'une clause `where` ?</summary>

#### Swift

Une clause `where` ajoute une condition supplémentaire à un pattern, une
boucle, une contrainte générique ou un bloc `catch`.

#### Dans `switch`

```swift
let point = (2, 2)

switch point {
case let (x, y) where x == y:
    print("x equals y")
default:
    print("No match")
}
```

#### Dans les boucles

```swift
for number in 1...10 where number.isMultiple(of: 2) {
    print(number)
}
```

Utilisez `where` lorsque vous voulez un filtrage ou un matching plus précis.

</details>

<details>
<summary>27. Que fait `defer` ?</summary>

#### Swift

`defer` planifie l'exécution de code juste avant la sortie du scope courant.

Il s'exécute quelle que soit la façon dont le scope se termine :

- Retour normal
- Retour anticipé
- Erreur lancée

```swift
func performTask() {
    print("Start")

    defer {
        print("Cleanup")
    }

    print("Work")
}
```

Sortie :

```swift
Start
Work
Cleanup
```

`defer` est utile pour les tâches de nettoyage comme :

- Fermer des fichiers
- Libérer des ressources verrouillées
- Réinitialiser un état

</details>

<details>
<summary>28. Que sont `break` et `continue` ?</summary>

#### Swift

`break` arrête la boucle courante ou le `switch`.
`continue` ignore l'itération courante de la boucle et passe à la suivante.

#### `break`

```swift
for number in 1...5 {
    if number == 3 {
        break
    }
    print(number)
}
```

#### `continue`

```swift
for number in 1...5 {
    if number == 3 {
        continue
    }
    print(number)
}
```

Utilisez `break` pour arrêter le traitement.
Utilisez `continue` pour ignorer une itération.

</details>

<details>
<summary>29. À quoi sert `stride()` ?</summary>

#### Swift

`stride()` sert à créer des séquences qui avancent par pas.

Il est utile lorsque vous ne voulez pas incrémenter de `1`.

#### Exemple avec `through`

```swift
for number in stride(from: 0, through: 10, by: 2) {
    print(number)
}
```

#### Exemple avec `to`

```swift
for number in stride(from: 0, to: 10, by: 2) {
    print(number)
}
```

Différence :

- `through` inclut la valeur de fin si possible
- `to` exclut la valeur de fin

</details>

<details>
<summary>30. Que sont les raw strings ?</summary>

#### Swift

Les raw strings vous permettent d'écrire des string literals sans traiter les
backslashes et les guillemets comme des caractères d'échappement normaux.

Ils utilisent `#` autour de la chaîne.

```swift
let path = #"C:\Users\Name\Documents"#
let text = #"He said "Hello""#
```

Si vous voulez de l'interpolation dans une raw string, utilisez `\#(...)` :

```swift
let name = "Alice"
let message = #"Hello, \#(name)"#
```

Les raw strings sont utiles pour :

- Les expressions régulières
- Les chemins de fichiers
- Les extraits JSON
- Les chaînes contenant beaucoup de backslashes ou de guillemets

</details>

<details>
<summary>31. Que sont les closures en Swift ?</summary>

#### Swift

Les closures sont des blocs de code autonomes qui peuvent être transmis et
exécutés plus tard.

Elles ressemblent à des fonctions, mais elles peuvent être stockées dans des
variables et capturer des valeurs du scope environnant.

```swift
let greet = { (name: String) in
    print("Hello, \(name)")
}

greet("Alice")
```

Les closures sont couramment utilisées pour :

- Les callbacks
- Les completion handlers
- Le tri
- Les opérations fonctionnelles comme `map` et `filter`

</details>

<details>
<summary>32. Escaping vs non-escaping closures ?</summary>

#### Swift

Une non-escaping closure est exécutée avant que la fonction ne retourne.
Une escaping closure peut être stockée et exécutée après le retour de la fonction.

#### Non-escaping closure

```swift
func runNow(action: () -> Void) {
    action()
}
```

#### Escaping closure

```swift
var storedAction: (() -> Void)?

func runLater(action: @escaping () -> Void) {
    storedAction = action
}
```

Utilisez les non-escaping closures par défaut.
Utilisez les escaping closures pour le travail asynchrone, les callbacks ou les closures stockées.

</details>

<details>
<summary>33. Que signifie `@escaping` ?</summary>

#### Swift

`@escaping` signifie que la closure peut vivre plus longtemps que la fonction à
laquelle elle a été passée.

Autrement dit, il n'est pas garanti que la closure s'exécute avant que la
fonction retourne.

```swift
class Downloader {
    var completion: (() -> Void)?

    func fetch(completion: @escaping () -> Void) {
        self.completion = completion
    }
}
```

`@escaping` est généralement nécessaire lorsque la closure est :

- Stockée dans une propriété
- Exécutée de manière asynchrone
- Passée à une autre fonction qui la stocke

</details>

<details>
<summary>34. Que sont les trailing closures ?</summary>

#### Swift

Une trailing closure est une closure écrite après les parenthèses de la fonction.

Cette syntaxe est plus lisible lorsque le dernier argument est une closure.

```swift
func perform(action: () -> Void) {
    action()
}

perform {
    print("Done")
}
```

Les trailing closures sont fréquentes dans :

- Les API asynchrones
- Les callbacks UIKit et SwiftUI
- Les opérations sur les collections

</details>

<details>
<summary>35. Qu'est-ce que la capture de valeur dans les closures ?</summary>

#### Swift

Les closures peuvent capturer des valeurs du scope environnant et continuer à
les utiliser même après que ce scope aurait normalement disparu.

```swift
func makeCounter() -> () -> Int {
    var count = 0

    return {
        count += 1
        return count
    }
}

let counter = makeCounter()
print(counter()) // 1
print(counter()) // 2
```

Ici, la closure capture `count` et le garde en vie.

C'est utile, mais cela peut aussi entraîner des problèmes de mémoire si des
objets sont capturés fortement par erreur.

</details>

<details>
<summary>36. Comment Swift gère-t-il la mémoire dans les closures ?</summary>

#### Swift

Swift utilise ARC (Automatic Reference Counting).
Les closures sont des reference types, donc elles peuvent capturer fortement des objets.

Si une closure capture fortement `self`, et que `self` conserve fortement la
closure, un retain cycle peut se produire.

```swift
class Example {
    var completion: (() -> Void)?

    func setup() {
        completion = { [weak self] in
            self?.doWork()
        }
    }

    func doWork() {
        print("Working")
    }
}
```

Pour éviter les memory leaks, utilisez des capture lists quand c'est nécessaire :

- `[weak self]` lorsque `self` peut devenir `nil`
- `[unowned self]` lorsque `self` doit encore exister

</details>

<details>
<summary>37. Que sont les higher-order functions (`map`, `filter`, `reduce`) ?</summary>

#### Swift

Les higher-order functions sont des fonctions qui prennent d'autres fonctions
ou closures comme arguments, ou les renvoient.

En Swift, les higher-order functions courantes sur les collections sont :

- `map`
- `filter`
- `reduce`

#### `map`

Transforme chaque élément.

```swift
let numbers = [1, 2, 3]
let doubled = numbers.map { $0 * 2 }
```

#### `filter`

Conserve uniquement les éléments correspondants.

```swift
let evenNumbers = numbers.filter { $0.isMultiple(of: 2) }
```

#### `reduce`

Combine tous les éléments en un seul résultat.

```swift
let sum = numbers.reduce(0) { $0 + $1 }
```

Ces fonctions rendent le code plus court et plus expressif.

</details>

<details>
<summary>38. Quelle est la différence entre `map` et `compactMap` ?</summary>

#### Swift

`map` transforme chaque élément et conserve le même nombre d'éléments.
`compactMap` transforme les éléments et supprime les résultats `nil`.

#### `map`

```swift
let values = ["1", "two", "3"]
let mapped = values.map { Int($0) }
// [Optional(1), nil, Optional(3)]
```

#### `compactMap`

```swift
let values = ["1", "two", "3"]
let compactMapped = values.compactMap { Int($0) }
// [1, 3]
```

Utilisez `map` lorsque tous les résultats transformés doivent rester dans la sortie.
Utilisez `compactMap` lorsque vous voulez ignorer les conversions échouées ou les valeurs `nil`.

</details>

<details>
<summary>39. Qu'est-ce que le currying (conceptuellement) ?</summary>

#### Swift

Le currying est l'idée de transformer une fonction qui prend plusieurs
arguments en une séquence de fonctions qui prennent chacune un seul argument.

Conceptuellement :

```swift
func add(_ a: Int) -> (Int) -> Int {
    return { b in
        a + b
    }
}

let addFive = add(5)
print(addFive(3)) // 8
```

Le currying est utile pour :

- L'application partielle
- Les fonctions spécialisées réutilisables
- Les concepts de programmation fonctionnelle

C'est davantage un concept qu'une technique utilisée au quotidien dans le code d'application Swift classique.

</details>

<details>
<summary>40. Qu'est-ce que `@autoclosure` ?</summary>

#### Swift

`@autoclosure` enveloppe automatiquement une expression dans une closure.

Cela vous permet de passer une expression là où une closure est attendue, sans
écrire la syntaxe de closure manuellement.

```swift
func logIfTrue(_ condition: @autoclosure () -> Bool) {
    if condition() {
        print("True")
    }
}

logIfTrue(2 > 1)
```

Sans `@autoclosure`, vous écririez :

```swift
logIfTrue({ 2 > 1 })
```

Il est souvent utilisé dans des API comme `assert`.
Utilisez-le avec précaution, car il peut masquer le fait qu'une closure est créée.

</details>

<details>
<summary>41. Que sont les generics et pourquoi sont-ils utiles ?</summary>

#### Swift

Les generics permettent d'écrire du code flexible et réutilisable qui
fonctionne avec différents types tout en conservant la sûreté des types.

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

Ici, `T` est un placeholder de type générique.

Les generics sont utiles parce qu'ils :

- Réduisent la duplication du code
- Conservent une forte sûreté des types
- Rendent les API plus réutilisables

</details>

<details>
<summary>42. Que sont les protocols ?</summary>

#### Swift

Un protocol définit un ensemble d'exigences qu'un type doit respecter.

Il peut exiger :

- Des propriétés
- Des méthodes
- Des initialiseurs

```swift
protocol Drivable {
    func drive()
}

struct Car: Drivable {
    func drive() {
        print("Driving")
    }
}
```

Les protocols sont utilisés pour définir un comportement partagé sans imposer l'héritage.

</details>

<details>
<summary>43. Qu'est-ce que la protocol-oriented programming (POP) ?</summary>

#### Swift

La protocol-oriented programming est une approche dans laquelle le comportement
est construit à l'aide de protocols et d'extensions de protocols plutôt qu'en
s'appuyant principalement sur l'héritage de classes.

En Swift, c'est un style de conception fondamental.

```swift
protocol Identifiable {
    var id: String { get }
}

extension Identifiable {
    func printID() {
        print(id)
    }
}
```

La POP est utile parce qu'elle :

- Encourage la composition plutôt que l'héritage
- Améliore la réutilisation du code
- Fonctionne bien avec les value types comme `struct`

</details>

<details>
<summary>44. Que sont les associated types ?</summary>

#### Swift

Un associated type est un type placeholder à l'intérieur d'un protocol.

Il permet au type conforme de décider quel type concret sera utilisé.

```swift
protocol Container {
    associatedtype Item
    var items: [Item] { get set }
}

struct IntContainer: Container {
    var items: [Int]
}
```

Les associated types sont utiles lorsqu'un protocol doit fonctionner avec
différents types de données tout en restant type-safe.

</details>

<details>
<summary>45. Qu'est-ce que la protocol composition ?</summary>

#### Swift

La protocol composition consiste à combiner plusieurs protocols en une seule
exigence de type.

Elle utilise `&`.

```swift
protocol Readable {}
protocol Writable {}

func process(file: Readable & Writable) {
    print("Can read and write")
}
```

Utilisez la protocol composition lorsqu'une valeur doit satisfaire plusieurs comportements en même temps.

</details>

<details>
<summary>46. Que sont les protocol extensions ?</summary>

#### Swift

Les protocol extensions vous permettent d'ajouter des implémentations par
défaut aux protocols.

```swift
protocol Greetable {
    var name: String { get }
    func greet()
}

extension Greetable {
    func greet() {
        print("Hello, \(name)")
    }
}
```

Cela signifie que les types conformes peuvent obtenir automatiquement un
comportement partagé.

Les protocol extensions sont une partie essentielle de la protocol-oriented programming.

</details>

<details>
<summary>47. Qu'est-ce que la conditional conformance ?</summary>

#### Swift

La conditional conformance signifie qu'un type générique se conforme à un
protocol uniquement lorsque certaines conditions sont remplies.

```swift
extension Array: Equatable where Element: Equatable {}
```

Cela signifie que `Array` est `Equatable` uniquement si ses éléments sont `Equatable`.

C'est utile pour construire des API génériques qui restent précises et type-safe.

</details>

<details>
<summary>48. Qu'est-ce que le type erasure ?</summary>

#### Swift

Le type erasure masque un type concret spécifique derrière un wrapper commun ou
une interface abstraite.

Il est souvent nécessaire lorsqu'on travaille avec des protocols qui ont :

- Des associated types
- Des exigences `Self`

Par exemple, SwiftUI utilise `AnyView` comme wrapper avec type erasure.

```swift
let views: [AnyView] = [
    AnyView(Text("Hello")),
    AnyView(Image(systemName: "star"))
]
```

Le type erasure aide à stocker ou transmettre de manière uniforme des valeurs
ayant des types concrets différents.

</details>

<details>
<summary>49. Quelle est la différence entre `Self` et `self` ?</summary>

#### Swift

`Self` et `self` sont différents.

- `Self` fait référence au type lui-même
- `self` fait référence à l'instance courante

#### `self`

```swift
struct User {
    var name: String

    func printName() {
        print(self.name)
    }
}
```

#### `Self`

```swift
protocol Copyable {
    func copy() -> Self
}
```

Utilisez `self` lorsque vous travaillez avec l'objet ou la valeur courante.
Utilisez `Self` lorsque vous faites référence au type concret au niveau du type.

</details>

<details>
<summary>50. Comment fonctionne ARC en Swift ?</summary>

#### Swift

ARC signifie Automatic Reference Counting.

C'est le système de gestion de mémoire de Swift pour les instances de classes.
ARC suit automatiquement le nombre de références fortes qui pointent vers un objet.

- Lorsque le nombre de références augmente, l'objet reste en mémoire
- Lorsque le nombre de références tombe à zéro, l'objet est libéré

```swift
class Person {
    let name: String

    init(name: String) {
        self.name = name
        print("\(name) initialized")
    }

    deinit {
        print("\(name) deallocated")
    }
}
```

ARC ne gère pas les value types comme `struct` et `enum` de la même manière,
car ce ne sont pas des reference types.

Le principal risque avec ARC est le retain cycle, généralement résolu avec des références `weak` ou `unowned`.

</details>

<details>
<summary>51. Qu'est-ce qu'un retain cycle ?</summary>

#### Swift

Un retain cycle se produit lorsque deux objets ou plus de type référence
conservent des références fortes l'un vers l'autre, de sorte qu'aucun ne peut
être libéré.

Cela provoque généralement une memory leak.

```swift
class Person {
    var apartment: Apartment?
}

class Apartment {
    var tenant: Person?
}
```

Si les deux références sont fortes, les objets se gardent mutuellement en vie.

Les retain cycles sont fréquents avec :

- Les closures qui capturent `self`
- Les relations parent-enfant entre objets
- Les delegate patterns mal implémentés

</details>

<details>
<summary>52. Quelle est la différence entre `weak` et `unowned` ?</summary>

#### Swift

`weak` et `unowned` servent tous deux à éviter les retain cycles, mais leur
comportement est différent.

| Caractéristique | `weak` | `unowned` |
| --- | --- | --- |
| Optional | Oui | Non |
| Peut devenir `nil` | Oui | Non |
| Sécurité | Plus sûr | Moins sûr |
| À utiliser lorsque | L'objet référencé peut disparaître | L'objet référencé doit exister |

#### Exemple

```swift
weak var delegate: SomeDelegate?
unowned var owner: Owner
```

Utilisez `weak` lorsque la référence peut devenir `nil`.
Utilisez `unowned` lorsque la référence doit toujours pointer vers un objet valide.

</details>

<details>
<summary>53. Quand utiliseriez-vous `unowned` au lieu de `weak` ?</summary>

#### Swift

Utilisez `unowned` lorsque l'objet référencé doit toujours exister tant que
cette référence est utilisée.

C'est fréquent lorsque deux objets sont liés, mais que l'un possède clairement
la durée de vie de l'autre.

```swift
class Customer {
    let name: String

    init(name: String) {
        self.name = name
    }
}

class CreditCard {
    unowned let customer: Customer

    init(customer: Customer) {
        self.customer = customer
    }
}
```

Utilisez `unowned` uniquement si vous êtes sûr que la référence ne sera jamais
accédée après la libération de l'objet.

Sinon, utilisez `weak`.

</details>

<details>
<summary>54. Qu'est-ce qu'une memory leak ?</summary>

#### Swift

Une memory leak se produit lorsque de la mémoire n'est plus nécessaire mais
n'est toujours pas libérée.

En Swift, cela arrive généralement parce que des objets sont encore fortement
référencés, souvent à cause de retain cycles.

Signes d'une memory leak :

- Les objets ne sont jamais libérés
- L'utilisation mémoire continue d'augmenter
- Des écrans ou des view models restent en mémoire après leur fermeture

Les memory leaks peuvent entraîner :

- Une utilisation mémoire plus élevée
- Des problèmes de performance
- L'arrêt de l'application par le système

</details>

<details>
<summary>55. Comment déboguer les problèmes de mémoire ?</summary>

#### Swift

Les moyens courants de déboguer les problèmes de mémoire en Swift sont :

1. Xcode Memory Graph Debugger
2. Instruments avec l'outil Leaks
3. Instruments avec Allocations
4. Vérifier si `deinit` est appelé

#### Exemple

```swift
deinit {
    print("Deallocated")
}
```

Si `deinit` n'est pas appelé au moment attendu, quelque chose retient encore l'objet.

Un workflow courant est :

- Reproduire le parcours d'écran
- Fermer l'écran
- Vérifier le Memory Graph
- Rechercher des retain cycles ou des références fortes inattendues

</details>

<details>
<summary>56. Comment Swift gère-t-il la mémoire pour les value types et les reference types ?</summary>

#### Swift

Swift gère différemment la mémoire des value types et des reference types.

#### Value types

- `struct`
- `enum`
- `tuple`

Ils sont copiés à l'assignation ou lorsqu'ils sont passés à des fonctions.
Ils n'utilisent pas ARC de la même manière que les instances de classes.

#### Reference types

- `class`

Ils sont partagés par référence.
Swift utilise ARC pour gérer leur durée de vie.

La principale différence est donc :

- Les value types copient les données
- Les reference types partagent la même instance

</details>

<details>
<summary>57. Qu'est-ce que async/await en Swift ?</summary>

#### Swift

`async/await` est la syntaxe moderne de Swift pour la programmation asynchrone.

Elle donne au code asynchrone une apparence plus proche d'un code séquentiel classique.

```swift
func loadUser() async throws -> String {
    return "Alice"
}

func fetchData() async {
    do {
        let user = try await loadUser()
        print(user)
    } catch {
        print(error)
    }
}
```

Avantages :

- Un code asynchrone plus propre
- Une meilleure lisibilité
- Une gestion des erreurs plus simple avec `try`

</details>

<details>
<summary>58. Qu'est-ce que la structured concurrency ?</summary>

#### Swift

La structured concurrency signifie que le travail asynchrone est organisé dans
une hiérarchie claire de tâches parent et enfant.

Cela aide Swift à gérer :

- La durée de vie des tâches
- L'annulation
- La propagation des erreurs

Avec la structured concurrency, les tâches enfants appartiennent généralement
au scope dans lequel elles ont été créées et ne restent pas actives sans contrôle.

Les outils courants de structured concurrency sont :

- `async let`
- `TaskGroup`

Cela rend le code concurrent plus sûr et plus facile à comprendre.

</details>

<details>
<summary>59. Que sont les Tasks et les Task groups ?</summary>

#### Swift

Une `Task` est une unité de travail asynchrone.
Un `TaskGroup` vous permet d'exécuter plusieurs tâches enfants en parallèle et
de collecter leurs résultats.

#### Task

```swift
Task {
    print("Running async work")
}
```

#### Task group

```swift
await withTaskGroup(of: Int.self) { group in
    group.addTask { 1 }
    group.addTask { 2 }

    for await value in group {
        print(value)
    }
}
```

Utilisez :

- `Task` pour une opération asynchrone unique
- `TaskGroup` pour plusieurs tâches enfants parallèles

</details>

<details>
<summary>60. Qu'est-ce que `MainActor` et pourquoi est-il important ?</summary>

#### Swift

`MainActor` est un global actor qui garantit que le code s'exécute sur le thread principal.

Il est important parce que les mises à jour de l'UI doivent se faire sur le thread principal.

```swift
@MainActor
class ViewModel {
    var title = ""

    func updateTitle() {
        title = "Updated"
    }
}
```

Vous pouvez également basculer explicitement vers lui :

```swift
await MainActor.run {
    print("Update UI")
}
```

`MainActor` aide à éviter les bugs de threading et rend le code lié à l'UI plus sûr.

</details>

<details>
<summary>61. Que sont les actors et comment empêchent-ils les race conditions ?</summary>

#### Swift

Les actors sont des reference types qui protègent leur état mutable contre un
accès concurrent non sécurisé.

Ils aident à éviter les race conditions en isolant l'état, de sorte qu'une
seule tâche peut accéder à cet état mutable à la fois.

```swift
actor Counter {
    private var value = 0

    func increment() {
        value += 1
    }

    func getValue() -> Int {
        value
    }
}
```

Pour accéder à l'état isolé d'un actor depuis l'extérieur, on utilise
généralement `await`.

Les actors sont importants dans la Swift concurrency moderne, car ils offrent
une alternative plus sûre au verrouillage manuel dans de nombreux cas.

</details>

<details>
<summary>62. Qu'est-ce qu'une data race et comment Swift l'empêche-t-il ?</summary>

#### Swift

Une data race se produit lorsque plusieurs threads ou tâches accèdent en même
temps aux mêmes données mutables, et qu'au moins l'un d'eux y écrit.

Cela peut entraîner un comportement imprévisible et des crashs.

Swift aide à prévenir les data races avec :

- L'isolation par actor
- `Sendable`
- La structured concurrency
- L'isolation du main actor pour le code UI

En Swift moderne, les fonctionnalités de concurrence sont conçues pour détecter
plus tôt l'état mutable partagé non sûr et faciliter son évitement.

</details>

<details>
<summary>63. Quelle est la différence entre GCD et la concurrence moderne ?</summary>

#### Swift

GCD et la Swift concurrency moderne gèrent tous deux le travail asynchrone,
mais ils utilisent des modèles différents.

| Caractéristique | GCD | Concurrence moderne |
| --- | --- | --- |
| Style | Basé sur des callbacks | `async/await` |
| Lisibilité | Plus imbriqué | Plus linéaire |
| Annulation | Manuelle | Prise en charge intégrée |
| Sécurité | Plus bas niveau | Plus sûre et plus structurée |
| Outils | `DispatchQueue` | `Task`, actors, `TaskGroup`, `MainActor` |

#### Exemple GCD

```swift
DispatchQueue.global().async {
    print("Background work")
}
```

#### Exemple de concurrence moderne

```swift
Task {
    print("Async work")
}
```

La concurrence moderne est généralement préférée pour le nouveau code Swift.

</details>

<details>
<summary>64. Comment synchronise-t-on l'accès à un état partagé ?</summary>

#### Swift

Vous synchronisez l'état partagé en vous assurant que le code concurrent ne lit
et n'écrit pas les mêmes données mutables de manière non sûre.

Approches courantes :

- Actors
- Files sérielles
- Verrous
- `MainActor` pour l'état de l'UI

#### Approche moderne privilégiée

```swift
actor Store {
    private var items: [String] = []

    func add(_ item: String) {
        items.append(item)
    }
}
```

En Swift moderne, les actors sont généralement l'option par défaut la plus
sûre pour l'état mutable partagé.

</details>

<details>
<summary>65. Qu'est-ce que `Sendable` en Swift ?</summary>

#### Swift

`Sendable` est un protocol qui marque un type comme étant sûr à transférer
entre domaines de concurrence.

Cela importe lorsque des valeurs sont transmises entre tâches ou actors.

```swift
struct User: Sendable {
    let id: Int
    let name: String
}
```

Les value types avec des stored properties immuables sont souvent naturellement `Sendable`.

`Sendable` aide Swift à détecter le partage non sûr d'un état mutable dans le code concurrent.

</details>

<details>
<summary>66. Comment fonctionne la gestion des erreurs en Swift ?</summary>

#### Swift

Swift utilise une gestion des erreurs typée avec `throw`, `throws`, `do`,
`try` et `catch`.

#### Exemple

```swift
enum LoginError: Error {
    case invalidCredentials
}

func login(success: Bool) throws {
    if !success {
        throw LoginError.invalidCredentials
    }
}

do {
    try login(success: false)
} catch {
    print(error)
}
```

Cela rend la gestion des erreurs explicite et plus sûre que le fait d'ignorer silencieusement les échecs.

</details>

<details>
<summary>67. Quelle est la différence entre `try`, `try?` et `try!` ?</summary>

#### Swift

Les trois sont utilisés avec des fonctions qui peuvent lancer des erreurs, mais
ils gèrent ces erreurs différemment.

| Mot-clé | Comportement |
| --- | --- |
| `try` | Propage ou gère l'erreur normalement |
| `try?` | Convertit le résultat en optional et renvoie `nil` en cas d'erreur |
| `try!` | Force le succès et provoque un crash si une erreur est lancée |

#### Exemple

```swift
let value1 = try someThrowingFunction()
let value2 = try? someThrowingFunction()
let value3 = try! someThrowingFunction()
```

Utilisez :

- `try` pour la gestion normale des erreurs
- `try?` lorsqu'un échec peut être ignoré sous forme de `nil`
- `try!` uniquement lorsqu'un échec est impossible

</details>

<details>
<summary>68. Qu'est-ce que `throws` vs `rethrows` ?</summary>

#### Swift

`throws` signifie qu'une fonction peut lancer sa propre erreur.
`rethrows` signifie qu'une fonction ne lance une erreur que si l'un de ses
arguments fonctionnels en lance une.

#### `throws`

```swift
func load() throws {
    // may throw
}
```

#### `rethrows`

```swift
func perform(_ action: () throws -> Void) rethrows {
    try action()
}
```

Utilisez `rethrows` pour les fonctions wrapper qui ne lancent pas d'erreur par
elles-mêmes, mais qui appellent une closure pouvant en lancer une.

</details>

<details>
<summary>69. Qu'est-ce que le type Result ?</summary>

#### Swift

`Result` est un enum qui représente soit :

- Un succès avec une valeur
- Un échec avec une erreur

```swift
let result: Result<String, Error> = .success("Done")
```

Il est défini approximativement comme ceci :

```swift
enum Result<Success, Failure: Error> {
    case success(Success)
    case failure(Failure)
}
```

`Result` est utile lorsque vous voulez transmettre explicitement un succès ou
un échec, en particulier dans les callbacks ou les API asynchrones.

</details>

<details>
<summary>70. Comment propage-t-on les erreurs ?</summary>

#### Swift

Vous propagez les erreurs en marquant une fonction avec `throws` et en
utilisant `try` lorsque vous appelez une autre fonction qui peut lancer une erreur.

```swift
func loadData() throws {
    throw NSError(domain: "Example", code: 1)
}

func processData() throws {
    try loadData()
}
```

Ici, `processData()` ne gère pas l'erreur elle-même.
Elle la transmet à son appelant.

C'est utile lorsqu'une fonction de niveau inférieur doit signaler un échec et
laisser une couche de niveau supérieur décider comment le gérer.

</details>

<details>
<summary>71. Que sont les property wrappers ?</summary>

#### Swift

Les property wrappers sont une fonctionnalité de Swift qui permet d'ajouter un
comportement réutilisable autour des stored properties.

Ils sont déclarés avec `@propertyWrapper`.

```swift
@propertyWrapper
struct Uppercased {
    private var value: String = ""

    var wrappedValue: String {
        get { value }
        set { value = newValue.uppercased() }
    }
}

struct User {
    @Uppercased var name: String
}
```

Les property wrappers sont utiles pour :

- La validation
- Le formatage
- La persistance
- La dependency injection

</details>

<details>
<summary>72. Que sont les opaque return types (`some`) ?</summary>

#### Swift

Les opaque return types permettent à une fonction de renvoyer une valeur d'un
type spécifique sans exposer ce type exact dans l'API.

Ils utilisent le mot-clé `some`.

```swift
func makeView() -> some View {
    Text("Hello")
}
```

L'appelant sait que la valeur retournée est conforme à `View`, mais n'a pas
besoin de connaître le type concret.

Les opaque types sont largement utilisés dans SwiftUI.

</details>

<details>
<summary>73. Quelle est la différence entre opaque types et generics ?</summary>

#### Swift

Les opaque types et les generics travaillent tous deux avec des types
abstraits, mais ils résolvent des problèmes différents.

| Caractéristique | Generics | Opaque types |
| --- | --- | --- |
| Qui choisit le type concret ? | L'appelant | L'implémentation |
| Syntaxe | `<T>` | `some Protocol` |
| Usage principal | API flexibles et réutilisables | Masquer les types de retour concrets |

#### Exemple générique

```swift
func echo<T>(_ value: T) -> T {
    value
}
```

#### Exemple d'opaque type

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Utilisez les generics lorsque l'appelant fournit le type.
Utilisez les opaque types lorsque l'implémentation fournit le type tout en le masquant.

</details>

<details>
<summary>74. Que sont les result builders ?</summary>

#### Swift

Les result builders sont une fonctionnalité qui permet à Swift de construire
des valeurs complexes à partir d'un bloc de code déclaratif.

Ils sont largement utilisés dans SwiftUI.

```swift
@resultBuilder
struct StringBuilder {
    static func buildBlock(_ components: String...) -> String {
        components.joined(separator: " ")
    }
}
```

Un result builder transforme plusieurs expressions en un seul résultat final.

C'est utile pour les API de style DSL.

</details>

<details>
<summary>75. Que sont les custom operators ?</summary>

#### Swift

Les custom operators vous permettent de définir vos propres opérateurs en Swift.

```swift
infix operator +++

func +++ (lhs: Int, rhs: Int) -> Int {
    lhs + rhs + 1
}
```

Vous pouvez créer :

- Des opérateurs préfixes
- Des opérateurs infixes
- Des opérateurs postfixes

Ils peuvent être puissants, mais doivent être utilisés avec prudence.

S'ils sont trop utilisés, ils rendent le code plus difficile à lire.

</details>

<details>
<summary>76. Qu'est-ce que dynamic dispatch vs static dispatch ?</summary>

#### Swift

Le dispatch est la manière dont Swift décide quelle implémentation de méthode appeler.

#### Static dispatch

L'appel de méthode est résolu à la compilation.
Il est généralement plus rapide.

C'est courant avec :

- `struct`
- `enum`
- Les méthodes `final`

#### Dynamic dispatch

L'appel de méthode est résolu à l'exécution.
Il est plus flexible, mais a plus de surcharge.

C'est courant avec :

- Les classes avec héritage
- `@objc dynamic`

Le static dispatch privilégie la performance.
Le dynamic dispatch privilégie la flexibilité à l'exécution.

</details>

<details>
<summary>77. Qu'est-ce qu'un phantom type ?</summary>

#### Swift

Un phantom type est un paramètre de type générique utilisé uniquement à la
compilation et non stocké à l'exécution.

Il aide à rendre les API plus sûres en encodant des informations de type
supplémentaires dans le système de types.

```swift
struct ID<Tag> {
    let value: String
}

enum UserTag {}
enum OrderTag {}

let userID = ID<UserTag>(value: "123")
let orderID = ID<OrderTag>(value: "123")
```

Même si les deux valeurs contiennent un `String`, Swift les traite comme des types différents.

</details>

<details>
<summary>78. Qu'est-ce que l'escape analysis ?</summary>

#### Swift

L'escape analysis est un concept d'optimisation du compilateur utilisé pour
déterminer si une valeur ou une closure sort du scope dans lequel elle a été créée.

Si quelque chose ne s'échappe pas, Swift peut optimiser plus efficacement
l'utilisation mémoire et le comportement d'appel.

Ce concept est lié à :

- Escaping vs non-escaping closures
- Les décisions d'optimisation stack vs heap

Dans les entretiens Swift du quotidien, il suffit généralement de savoir que
les non-escaping closures sont plus faciles à optimiser pour le compilateur.

</details>

<details>
<summary>79. Qu'est-ce qu'un function builder (result builder) ?</summary>

#### Swift

Function builder est l'ancien nom de ce que Swift appelle aujourd'hui un result builder.

Il s'agit d'une fonctionnalité qui transforme un bloc d'expressions en un seul
résultat, souvent pour des API déclaratives.

SwiftUI l'utilise intensivement avec la syntaxe de construction de vues.

```swift
@ViewBuilder
func makeContent(isLoggedIn: Bool) -> some View {
    if isLoggedIn {
        Text("Welcome")
    } else {
        Text("Please log in")
    }
}
```

Donc aujourd'hui :

- `function builder` est l'ancien terme
- `result builder` est le terme officiel actuel

</details>

<details>
<summary>80. Qu'est-ce que SwiftUI et en quoi diffère-t-il d'UIKit ?</summary>

#### Swift

SwiftUI est le framework UI déclaratif d'Apple pour construire des interfaces
sur les plateformes Apple.

UIKit est l'ancien framework impératif pour construire des interfaces iOS.

| Caractéristique | SwiftUI | UIKit |
| --- | --- | --- |
| Style | Déclaratif | Impératif |
| Mises à jour de l'UI | Pilotées par l'état | Mises à jour manuelles |
| Syntaxe | DSL basé sur Swift | Classes et API de cycle de vie |
| Usage typique | Développement UI moderne sur Apple | Framework UI iOS mature |

#### Exemple SwiftUI

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
    }
}
```

#### Exemple UIKit

```swift
let label = UILabel()
label.text = "Hello"
```

SwiftUI permet généralement un développement UI plus rapide et une meilleure
intégration avec les fonctionnalités modernes de Swift.
UIKit offre un contrôle plus bas niveau et un écosystème historique plus large.

</details>

<details>
<summary>81. Qu'est-ce que l'UI déclarative ?</summary>

#### Swift

L'UI déclarative signifie que vous décrivez à quoi l'interface doit ressembler
pour un état donné, au lieu d'écrire des instructions étape par étape pour la mettre à jour.

En SwiftUI, vous déclarez l'interface en fonction des données, et le framework
met à jour l'écran lorsque l'état change.

```swift
struct ContentView: View {
    let isLoggedIn: Bool

    var body: some View {
        if isLoggedIn {
            Text("Welcome")
        } else {
            Text("Please log in")
        }
    }
}
```

Cela diffère de l'UI impérative, où vous créez les vues manuellement et les modifiez directement.

</details>

<details>
<summary>82. Qu'est-ce que `@State` ?</summary>

#### Swift

`@State` est un property wrapper utilisé dans SwiftUI pour stocker un état
mutable local à l'intérieur d'une vue.

Quand une valeur `@State` change, SwiftUI re-render la vue.

```swift
struct CounterView: View {
    @State private var count = 0

    var body: some View {
        Button("Count: \(count)") {
            count += 1
        }
    }
}
```

Utilisez `@State` pour un état simple appartenant à la vue elle-même.

</details>

<details>
<summary>83. Qu'est-ce que `@StateObject` vs `@ObservedObject` ?</summary>

#### Swift

Les deux sont utilisés avec des reference types observables, mais ils diffèrent
par la propriété de l'objet.

| Wrapper | Ownership |
| --- | --- |
| `@StateObject` | La vue crée et possède l'objet |
| `@ObservedObject` | L'objet est créé ailleurs et passé à la vue |

#### `@StateObject`

```swift
struct ParentView: View {
    @StateObject private var viewModel = UserViewModel()
}
```

#### `@ObservedObject`

```swift
struct ChildView: View {
    @ObservedObject var viewModel: UserViewModel
}
```

Utilisez `@StateObject` lorsque la vue doit garder l'objet en vie.
Utilisez `@ObservedObject` lorsque la vue observe simplement un objet externe.

</details>

<details>
<summary>84. Qu'est-ce que `@EnvironmentObject` ?</summary>

#### Swift

`@EnvironmentObject` est utilisé pour partager un objet observable à travers
la hiérarchie des vues SwiftUI sans le passer manuellement à chaque vue.

```swift
class AppState: ObservableObject {
    @Published var isLoggedIn = false
}

struct ContentView: View {
    @EnvironmentObject var appState: AppState
}
```

Il est utile pour un état partagé à l'échelle de l'application, comme :

- La session utilisateur
- Le thème
- Les réglages

L'objet doit être injecté dans l'environment avant que la vue l'utilise.

</details>

<details>
<summary>85. Qu'est-ce que `@Published` ?</summary>

#### Swift

`@Published` est un property wrapper utilisé à l'intérieur d'un `ObservableObject`.

Lorsque la propriété change, elle notifie SwiftUI ou d'autres abonnés que
l'objet a changé.

```swift
class UserViewModel: ObservableObject {
    @Published var name = "Alice"
}
```

`@Published` est couramment utilisé pour l'état d'un view model qui doit mettre à jour l'UI.

</details>

<details>
<summary>86. Comment fonctionne la gestion d'état dans SwiftUI ?</summary>

#### Swift

La gestion d'état dans SwiftUI repose sur le fait que les données pilotent l'UI.

Lorsque l'état change, SwiftUI recalcule les vues concernées.

Outils courants :

- `@State` pour l'état local d'une vue
- `@StateObject` pour les objets observables possédés
- `@ObservedObject` pour les objets observables externes
- `@EnvironmentObject` pour les objets partagés à l'échelle de l'application
- `@Binding` pour transmettre un état mutable entre les vues

L'idée centrale est simple :

- L'état change
- SwiftUI met à jour la hiérarchie de vues

</details>

<details>
<summary>87. Qu'est-ce qu'un `ViewModifier` ?</summary>

#### Swift

Un `ViewModifier` est une façon réutilisable d'appliquer un style ou un
comportement à des vues SwiftUI.

```swift
struct TitleStyle: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.title)
            .foregroundColor(.blue)
    }
}
```

Utilisation :

```swift
Text("Hello").modifier(TitleStyle())
```

Les view modifiers aident à éviter de répéter la même logique de style de vue.

</details>

<details>
<summary>88. Qu'est-ce que l'environnement SwiftUI ?</summary>

#### Swift

L'environnement SwiftUI est un système permettant de transmettre implicitement
des valeurs à travers la hiérarchie des vues.

Il fournit un contexte partagé tel que :

- Le color scheme
- La locale
- La size category
- Des valeurs d'environnement personnalisées

Vous lisez les valeurs d'environnement avec `@Environment`.

```swift
struct ContentView: View {
    @Environment(\.colorScheme) var colorScheme
}
```

L'environnement aide à éviter de transmettre manuellement une configuration
commune à travers de nombreuses couches de vues.

</details>

<details>
<summary>89. Qu'est-ce que `GeometryReader` ?</summary>

#### Swift

`GeometryReader` est un conteneur SwiftUI qui donne accès aux informations de
layout sur l'espace disponible et la géométrie de la vue.

```swift
GeometryReader { geometry in
    Text("Width: \(geometry.size.width)")
}
```

Il est utile lorsque vous avez besoin de :

- Un layout dynamique basé sur la taille disponible
- Calculs de position
- Un comportement d'UI responsive

Il doit être utilisé avec précaution, car un usage excessif peut rendre le code de layout plus difficile à raisonner.

</details>

<details>
<summary>90. Comment fonctionne la navigation dans SwiftUI ?</summary>

#### Swift

La navigation dans SwiftUI est généralement construite avec `NavigationStack`.

Vous naviguez en empilant des destinations sur une pile.

```swift
NavigationStack {
    NavigationLink("Open Details") {
        DetailView()
    }
}
```

Vous pouvez aussi utiliser une navigation basée sur des valeurs avec `navigationDestination`.

```swift
NavigationStack {
    List(["A", "B"], id: \.self) { item in
        NavigationLink(value: item) {
            Text(item)
        }
    }
    .navigationDestination(for: String.self) { item in
        Text("Selected: \(item)")
    }
}
```

La navigation SwiftUI est pilotée par l'état et plus déclarative que les contrôleurs de navigation UIKit.

</details>

<details>
<summary>91. Quel est le lifecycle d'une vue SwiftUI ?</summary>

#### Swift

Les vues SwiftUI sont des value types, donc leur lifecycle est différent de
celui des contrôleurs de vue UIKit.

Une vue SwiftUI est fréquemment créée et recréée lorsque l'état change.
L'idée importante n'est pas la durée de vie de la struct elle-même, mais celle
de l'état qui lui est associé.

Les hooks de lifecycle courants incluent :

- `init`
- `body`
- `onAppear`
- `onDisappear`
- `.task`

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
            .onAppear {
                print("Appeared")
            }
            .onDisappear {
                print("Disappeared")
            }
    }
}
```

En SwiftUI, l'état et le flux de données comptent davantage que la durée de vie de l'objet.

</details>

<details>
<summary>92. Pourquoi les vues SwiftUI sont-elles des structs ?</summary>

#### Swift

Les vues SwiftUI sont des structs parce que les value types fonctionnent bien
avec l'UI déclarative.

Avantages :

- Légères
- Faciles à recréer
- Flux de données plus sûr
- Meilleures opportunités de performance pour SwiftUI

Comme ce sont des value types, SwiftUI peut reconstruire fréquemment les vues
et les comparer efficacement lorsque l'état change.

Les parties réellement persistantes de l'UI sont gérées par le framework, et non par la struct de vue elle-même.

</details>

<details>
<summary>93. Quelle est la différence entre UIKit et SwiftUI ?</summary>

#### Swift

UIKit et SwiftUI sont tous deux des frameworks UI d'Apple, mais ils utilisent
des approches différentes.

| Caractéristique | UIKit | SwiftUI |
| --- | --- | --- |
| Style | Impératif | Déclaratif |
| Blocs de construction principaux | `UIView`, `UIViewController` | `View` |
| Mises à jour de l'état | Manuelles | Pilotées par l'état |
| Usage typique | Contrôle UI mature et bas niveau | Développement UI déclaratif moderne |

UIKit vous donne plus de contrôle direct.
SwiftUI vous offre une manière plus moderne et plus concise de créer l'UI.

</details>

<details>
<summary>94. Qu'est-ce qu'Auto Layout ?</summary>

#### Swift

Auto Layout est le système d'Apple pour positionner et dimensionner les
éléments d'UI à l'aide de contraintes.

Au lieu de définir manuellement les frames pour chaque taille d'écran, vous
définissez des règles sur la relation entre les vues.

Exemples :

- Un label est à 16 points du bord gauche
- Un bouton est centré horizontalement
- Une image conserve une largeur et une hauteur égales

Auto Layout aide à construire des interfaces adaptatives pour différents appareils et tailles d'écran.

</details>

<details>
<summary>95. Qu'est-ce que l'intrinsic content size ?</summary>

#### Swift

L'intrinsic content size est la taille naturelle qu'une vue préfère en fonction de son contenu.

Par exemple :

- Un label dimensionne sa taille selon son texte
- Une image view dimensionne sa taille selon l'image

Cela aide Auto Layout à savoir quelle taille une vue doit avoir même sans
contraintes explicites de largeur et de hauteur.

Des vues comme `UILabel` et `UIButton` ont souvent une intrinsic content size.

</details>

<details>
<summary>96. Que sont les constraints et les anchors ?</summary>

#### Swift

Les constraints sont des règles de layout utilisées par Auto Layout.
Les anchors sont une manière plus pratique en code de créer ces contraintes.

Anchors courants :

- `topAnchor`
- `bottomAnchor`
- `leadingAnchor`
- `trailingAnchor`
- `widthAnchor`
- `heightAnchor`

```swift
button.translatesAutoresizingMaskIntoConstraints = false

NSLayoutConstraint.activate([
    button.centerXAnchor.constraint(equalTo: view.centerXAnchor),
    button.topAnchor.constraint(equalTo: view.topAnchor, constant: 20)
])
```

Les anchors rendent le code Auto Layout plus sûr et plus lisible que les anciennes API de contraintes.

</details>

<details>
<summary>97. Que sont les reusable cells ?</summary>

#### Swift

Les reusable cells sont des cellules de table view ou de collection view qui
sont réutilisées au lieu d'être recréées pour chaque élément.

Cela améliore :

- Les performances
- L'utilisation mémoire
- L'efficacité du défilement

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
```

Le mécanisme de reuse fonctionne en recyclant les cellules hors écran pour un nouveau contenu.

</details>

<details>
<summary>98. Quelle est la différence entre UITableView et UICollectionView ?</summary>

#### Swift

Les deux affichent des listes de données, mais ils sont conçus pour des besoins
de layout différents.

| Caractéristique | `UITableView` | `UICollectionView` |
| --- | --- | --- |
| Style de layout | Principalement liste verticale | Layouts flexibles |
| Complexité | Plus simple | Plus personnalisable |
| Usage typique | Listes simples, formulaires, réglages | Grilles, layouts personnalisés, listes complexes |

Utilisez `UITableView` pour une UI simple basée sur des listes.
Utilisez `UICollectionView` lorsque vous avez besoin de layouts plus flexibles ou personnalisés.

</details>

<details>
<summary>99. Qu'est-ce que `@IBOutlet` vs `@IBAction` ?</summary>

#### Swift

Les deux sont utilisés avec Interface Builder dans les storyboards UIKit ou les fichiers XIB.

- `@IBOutlet` connecte un élément d'UI au code
- `@IBAction` connecte un événement d'UI au code

#### `@IBOutlet`

```swift
@IBOutlet weak var titleLabel: UILabel!
```

#### `@IBAction`

```swift
@IBAction func buttonTapped(_ sender: UIButton) {
    print("Tapped")
}
```

`@IBOutlet` sert aux références vers les éléments d'UI.
`@IBAction` sert à gérer les actions utilisateur.

</details>

<details>
<summary>100. Qu'est-ce que le lifecycle de `UIViewController` ?</summary>

#### Swift

Le lifecycle de `UIViewController` est la séquence de méthodes appelées lorsqu'un
view controller est créé, affiché, mis en page et retiré.

Méthodes de lifecycle courantes :

1. `viewDidLoad`
2. `viewWillAppear`
3. `viewDidAppear`
4. `viewWillDisappear`
5. `viewDidDisappear`

#### Exemples de rôles

- `viewDidLoad` : configuration initiale
- `viewWillAppear` : mise à jour de l'UI avant qu'elle devienne visible
- `viewDidAppear` : démarrer les animations ou le suivi
- `viewWillDisappear` : préparer la sortie de l'écran
- `viewDidDisappear` : travail de nettoyage

Comprendre ce lifecycle est essentiel dans le développement d'applications UIKit.

</details>

<details>
<summary>101. Qu'est-ce que MVC ?</summary>

#### Swift

MVC signifie Model-View-Controller.

C'est un pattern de conception qui sépare une application en trois parties :

- Model : les données et la logique métier
- View : l'interface utilisateur
- Controller : gère l'interaction entre le modèle et la vue

En iOS, `UIViewController` joue souvent le rôle du contrôleur.

MVC est simple et courant, mais dans les applications UIKit il peut facilement
conduire à un "Massive View Controller" si trop de logique est placée dans le
contrôleur.

</details>

<details>
<summary>102. Qu'est-ce que MVVM ?</summary>

#### Swift

MVVM signifie Model-View-ViewModel.

Il sépare les responsabilités de cette manière :

- Model : les données et les règles métier
- View : l'interface utilisateur
- ViewModel : la logique de présentation et l'état pour la vue

Le ViewModel prépare les données pour l'affichage et réduit la logique à
l'intérieur de la vue ou du view controller.

MVVM est populaire en SwiftUI et aussi couramment utilisé dans les applications UIKit.

</details>

<details>
<summary>103. Qu'est-ce que l'injection de dépendances ?</summary>

#### Swift

L'injection de dépendances consiste à fournir à un objet les dépendances dont
il a besoin depuis l'extérieur, au lieu de les créer à l'intérieur de l'objet.

Par exemple, au lieu qu'un view model crée son propre service réseau, le
service lui est transmis.

Avantages :

- Meilleure testabilité
- Couplage plus faible
- Remplacement plus simple des implémentations

</details>

<details>
<summary>104. Comment implémente-t-on la DI en Swift ?</summary>

#### Swift

La manière la plus courante est l'injection par constructeur.

```swift
protocol NetworkService {
    func fetchData()
}

final class ViewModel {
    private let service: NetworkService

    init(service: NetworkService) {
        self.service = service
    }
}
```

Autres approches courantes :

- Injection par propriété
- Injection par méthode
- Conteneurs de dépendances

L'injection par constructeur est généralement préférée, car elle rend les
dépendances explicites.

</details>

<details>
<summary>105. Qu'est-ce que le delegation pattern ?</summary>

#### Swift

La délégation est un pattern dans lequel un objet transmet à un autre objet la
responsabilité d'un certain travail ou de certains événements.

Il est généralement implémenté avec des protocoles.

```swift
protocol ButtonHandler: AnyObject {
    func didTapButton()
}
```

La délégation est largement utilisée dans UIKit, par exemple avec :

- `UITableViewDelegate`
- `UITextFieldDelegate`

Elle aide à séparer les responsabilités et à garder une communication flexible.

</details>

<details>
<summary>106. Quand faut-il utiliser un singleton ?</summary>

#### Swift

Un singleton doit être utilisé lorsqu'il doit exister exactement une seule
instance partagée dans l'application.

Exemples typiques :

- Configuration globale de l'application
- Service de journalisation
- Gestionnaire de cache

```swift
final class Logger {
    static let shared = Logger()

    private init() {}
}
```

Utilisez les singletons avec prudence.
En abuser peut créer des dépendances cachées et rendre les tests plus difficiles.

</details>

<details>
<summary>107. Qu'est-ce que KVO ?</summary>

#### Swift

KVO signifie Key-Value Observing.

C'est un mécanisme permettant d'observer les changements de propriétés de
certain objets, en particulier ceux compatibles avec Objective-C.

Il est surtout associé à Cocoa et au comportement du runtime Objective-C.

KVO est moins souvent utilisé dans le code Swift moderne qu'avec :

- Combine
- `@Published`
- Les outils de state de SwiftUI

Mais il apparaît encore dans certaines API UIKit et Foundation.

</details>

<details>
<summary>108. Qu'est-ce que NotificationCenter ?</summary>

#### Swift

`NotificationCenter` est un système permettant de diffuser des messages à
plusieurs observateurs.

Un objet publie une notification, et d'autres objets peuvent l'écouter.

```swift
NotificationCenter.default.post(name: .didLogout, object: nil)
```

Il est utile pour une communication souple entre différentes parties de
l'application, en particulier lorsque les références directes ne sont pas idéales.

Utilisez-le avec prudence, car un usage excessif peut rendre le flux de données
plus difficile à suivre.

</details>

<details>
<summary>109. Comment effectue-t-on une requête réseau en Swift ?</summary>

#### Swift

La manière standard consiste à utiliser `URLSession`.

```swift
let url = URL(string: "https://example.com")!

URLSession.shared.dataTask(with: url) { data, response, error in
    if let error = error {
        print(error)
        return
    }

    if let data = data {
        print(data)
    }
}.resume()
```

En Swift moderne, vous pouvez aussi utiliser `async/await` avec `URLSession`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>110. Qu'est-ce que Codable ?</summary>

#### Swift

`Codable` est un alias de type pour :

- `Encodable`
- `Decodable`

Il permet de convertir facilement des types Swift vers et depuis des formats
comme JSON.

```swift
struct User: Codable {
    let id: Int
    let name: String
}
```

Cas d'usage courants :

- Analyse des réponses d'API
- Sauvegarde de données locales
- Encodage des corps de requête

`Codable` réduit fortement le code répétitif lié à la sérialisation.

</details>

<details>
<summary>111. Que sont les decoding strategies ?</summary>

#### Swift

Les decoding strategies sont des options utilisées par `JSONDecoder` pour
contrôler la manière dont les données entrantes sont décodées.

Les stratégies courantes incluent :

- `dateDecodingStrategy`
- `keyDecodingStrategy`
- `dataDecodingStrategy`

```swift
let decoder = JSONDecoder()
decoder.keyDecodingStrategy = .convertFromSnakeCase
decoder.dateDecodingStrategy = .iso8601
```

Elles sont utiles lorsque le format de l'API ne correspond pas directement au
format de votre modèle Swift.

</details>

<details>
<summary>112. Qu'est-ce que URLSession ?</summary>

#### Swift

`URLSession` est l'API principale d'Apple pour effectuer des requêtes réseau.

Elle est utilisée pour :

- Télécharger des données
- Envoyer des données
- Récupérer des fichiers
- Gérer des tâches réseau

Elle prend en charge à la fois le style completion-handler et `async/await`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>113. Qu'est-ce qu'une stratégie de cache ?</summary>

#### Swift

Une stratégie de cache est le plan qui définit quelles données mettre en cache,
où les stocker, et quand les rafraîchir ou les invalider.

Couches de cache courantes dans les applications iOS :

- Cache en mémoire
- Cache sur disque
- Cache HTTP

Les décisions importantes incluent généralement :

- La durée de vie du cache
- Les règles d'invalidation
- Les compromis mémoire vs disque
- Fraîcheur vs vitesse

Une bonne stratégie de cache améliore les performances, réduit l'usage réseau
et rend l'application plus rapide à l'usage.

</details>

<details>
<summary>114. Comment déboguer des crashs ?</summary>

#### Swift

Les moyens courants pour déboguer des crashs incluent :

1. Lire le crash log
2. Vérifier la stack trace
3. Reproduire le problème localement
4. Utiliser le debugger Xcode et les breakpoints
5. Utiliser des outils de crash reporting comme Firebase Crashlytics

Points importants à examiner :

- Le thread qui a crashé
- Le type d'exception
- Les dernières méthodes appelées
- L'appareil et la version de l'OS

L'objectif est de reproduire le crash, d'identifier la cause racine et de
confirmer le correctif.

</details>

<details>
<summary>115. Comment détecter des memory leaks ?</summary>

#### Swift

Les moyens courants de détecter des memory leaks sont :

- Xcode Memory Graph Debugger
- Instruments Leaks tool
- Instruments Allocations
- Vérifier `deinit`

```swift
deinit {
    print("Object deallocated")
}
```

Si un objet devrait disparaître mais reste en mémoire, il peut y avoir un
retain cycle ou une autre référence forte inattendue.

</details>

<details>
<summary>116. Comment améliore-t-on les performances dans les applications iOS ?</summary>

#### Swift

Les moyens courants d'améliorer les performances incluent :

- Réduire le travail sur le main thread
- Optimiser le rendu et le défilement
- Éviter les allocations inutiles
- Mettre en cache les résultats coûteux
- Utiliser des tâches en arrière-plan pour le travail lourd
- Profiler avec Instruments

Il faut d'abord mesurer, puis optimiser le véritable goulot d'étranglement.

Outils typiques :

- Time Profiler
- Allocations
- Memory Graph
- Network instruments

</details>

<details>
<summary>117. Comment optimise-t-on l'utilisation de la batterie ?</summary>

#### Swift

Pour optimiser l'utilisation de la batterie, il faut réduire le travail
inutile et éviter de garder le matériel ou les tâches d'arrière-plan actifs
plus longtemps que nécessaire.

Pratiques courantes :

- Minimiser l'activité en arrière-plan
- Éviter les mises à jour de localisation excessives
- Regrouper les requêtes réseau
- Réduire les timers fréquents et le polling
- Éviter les animations et redraws inutiles

La règle principale est simple :

- Faire moins de travail
- Le faire moins souvent

</details>

<details>
<summary>118. Qu'est-ce que Keychain et quand l'utiliser ?</summary>

#### Swift

Keychain est le système de stockage sécurisé d'Apple pour de petites données sensibles.

Utilisez Keychain pour des éléments comme :

- Les tokens
- Les mots de passe
- Les identifiants
- Les secrets sensibles

Ne l'utilisez pas comme base de données générale.

Keychain est plus sûr que `UserDefaults` pour les données confidentielles.

</details>

<details>
<summary>119. Qu'est-ce que l'App Transport Security ?</summary>

#### Swift

App Transport Security (ATS) est une fonctionnalité de sécurité iOS qui
encourage par défaut l'utilisation de connexions réseau sécurisées.

Elle exige généralement :

- HTTPS
- Des paramètres TLS robustes

Si une application a besoin de HTTP non sécurisé ou de paramètres de sécurité
plus faibles, des exceptions explicites doivent être ajoutées dans la
configuration de l'application.

ATS aide à protéger le trafic réseau contre l'interception et les transports non sécurisés.

</details>

<details>
<summary>120. Comment stocke-t-on des données de manière sécurisée ?</summary>

#### Swift

Cela dépend de la sensibilité des données.

Règles typiques :

- Utiliser Keychain pour les mots de passe, tokens et secrets
- Utiliser la protection des fichiers pour les fichiers sensibles
- Éviter de stocker des secrets en texte brut
- Ne pas stocker de données confidentielles dans `UserDefaults`
- Chiffrer les données lorsque c'est nécessaire

Également important :

- Limiter ce que vous stockez
- Le stocker seulement aussi longtemps que nécessaire
- Le protéger à la fois au repos et en transit

</details>

<details>
<summary>121. Qu'est-ce que XCTest ?</summary>

#### Swift

`XCTest` est le framework de test d'Apple pour écrire et exécuter des tests dans Xcode.

Il est utilisé pour :

- Les tests unitaires
- Les tests UI
- Les tests de performance

```swift
func testAddition() {
    XCTAssertEqual(2 + 2, 4)
}
```

C'est l'outil de test standard pour le développement sur les plateformes Apple.

</details>

<details>
<summary>122. Qu'est-ce que les unit tests vs les UI tests ?</summary>

#### Swift

Les unit tests vérifient de petits morceaux de logique de manière isolée.
Les UI tests vérifient l'application à travers l'interface utilisateur.

| Type | Focus |
| --- | --- |
| Unit test | Logique métier, fonctions, classes |
| UI test | Parcours utilisateur réels et interactions avec les écrans |

Les unit tests sont généralement :

- Plus rapides
- Plus isolés
- Plus faciles à déboguer

Les UI tests sont utiles pour valider le comportement de bout en bout.

</details>

<details>
<summary>123. Qu'est-ce que le mocking ?</summary>

#### Swift

Le mocking consiste à remplacer une dépendance réelle par une fausse version de test.

Cela aide à tester une unité de manière isolée.

Par exemple, au lieu d'appeler une vraie API, un mock network service renvoie
des données prédéfinies.

Le mocking est utile pour :

- Des tests plus rapides
- Des résultats prévisibles
- Le test des scénarios d'échec

</details>

<details>
<summary>124. Comment restez-vous à jour avec Swift ?</summary>

#### Swift

Une bonne réponse consiste à combiner des sources officielles avec un
apprentissage pratique.

Méthodes courantes :

- Lire les propositions Swift Evolution
- Suivre les sessions WWDC
- Lire la documentation Apple
- Essayer de nouvelles fonctionnalités du langage dans des side projects
- Suivre des ingénieurs Swift et iOS reconnus

L'important n'est pas seulement de lire les nouveautés, mais de les appliquer
dans du vrai code.

</details>

<details>
<summary>125. Parlez-moi d'une fonctionnalité complexe que vous avez développée.</summary>

#### Swift

Une bonne réponse en entretien devrait être structurée ainsi :

1. Expliquer brièvement la fonctionnalité
2. Décrire les principaux défis techniques
3. Expliquer vos décisions et vos trade-offs
4. Montrer le résultat

#### Exemple de structure de réponse

"J'ai développé une fonctionnalité de synchronisation offline-first pour une
application mobile. Les principaux défis étaient la résolution des conflits, la
persistance locale, la logique de retry et le maintien de la réactivité de l'UI
pendant la synchronisation. J'ai séparé le problème en couches de networking,
de stockage local des données et d'orchestration de la synchronisation. J'ai
aussi ajouté des politiques de retry, la gestion de la synchronisation en
arrière-plan et du logging. Le résultat a été une meilleure performance perçue,
une meilleure fiabilité sur des réseaux instables et moins de problèmes de support."

Les meilleures réponses sont concrètes et mesurables.

</details>

<details>
<summary>126. Comment abordez-vous la code review ?</summary>

#### Swift

Une bonne approche de code review se concentre d'abord sur la correction, puis
sur la maintenabilité.

Priorités typiques :

- Les bugs et les edge cases
- L'adéquation de l'architecture et du design
- La lisibilité
- Le naming
- La couverture de tests
- Les performances et la sécurité lorsque c'est pertinent

Une bonne review doit être claire, respectueuse et spécifique.

Le but n'est pas seulement de trouver des problèmes, mais aussi d'améliorer la
qualité du code et de partager des connaissances.

</details>

<details>
<summary>127. Comment concevez-vous une architecture iOS scalable ?</summary>

#### Swift

Une architecture scalable consiste à garder les fonctionnalités faciles à
étendre, tester et maintenir à mesure que l'application grandit.

Principes importants :

- Séparation claire des responsabilités
- Design modulaire
- Injection de dépendances
- Logique métier testable
- Flux de données prévisible

Une architecture scalable doit aider les équipes à ajouter des fonctionnalités
sans réécrire en permanence le code existant.

</details>

<details>
<summary>128. Quels trade-offs prenez-vous en compte lors du choix d'une architecture ?</summary>

#### Swift

L'architecture est toujours une question de trade-offs.

Facteurs courants :

- La taille et l'expérience de l'équipe
- La complexité de l'application
- La vitesse de développement
- La testabilité
- La maintenabilité
- La flexibilité pour la croissance future

Une application simple n'a pas forcément besoin d'une architecture lourde.
Une grande application bénéficie généralement d'une séparation plus forte, de
frontières plus claires et d'une meilleure gestion des dépendances.

Le meilleur choix est l'architecture la plus simple qui reste bien adaptée au problème.

</details>
