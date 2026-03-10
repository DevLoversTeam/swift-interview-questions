**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Swift <img src="./assets/swift.svg" width="40" height="40" />
</h1>

<h2>Die beliebtesten Swift-Interviewfragen und Antworten</h2>

<details>
<summary>1. Wofür wird Swift in der modernen Entwicklung hauptsächlich verwendet?</summary>

#### Swift

Swift wird hauptsächlich für die Entwicklung von Apps für Apples Plattformen verwendet:

- iOS
- macOS
- watchOS
- tvOS
- visionOS

Swift wird vor allem genutzt für:

- Mobile App-Entwicklung
- Native Entwicklung für Apple-Plattformen
- Backend-Entwicklung mit Frameworks wie Vapor
- Kommandozeilen-Tools und Skripte

Swift wird für seine Sicherheit, Performance und moderne Syntax geschätzt.

</details>

<details>
<summary>2. Was ist der Unterschied zwischen `let` und `var`?</summary>

#### Swift

`let` erstellt eine Konstante, und `var` erstellt eine Variable.

- Verwende `let`, wenn sich der Wert nicht ändern soll.
- Verwende `var`, wenn sich der Wert später ändern kann.

```swift
let name = "Alice"
var age = 25

age = 26 // Erlaubt
// name = "Bob" // Fehler
```

Die standardmäßige Verwendung von `let` macht Code sicherer und leichter verständlich.

</details>

<details>
<summary>3. Erkläre type inference in Swift.</summary>

#### Swift

Type inference bedeutet, dass Swift den Typ eines Werts anhand der
zugewiesenen Daten automatisch bestimmen kann, sodass man den Typ nicht immer
explizit angeben muss.

```swift
let title = "Swift"      // String
let year = 2025          // Int
let isActive = true      // Bool
```

Du kannst den Typ trotzdem manuell angeben, wenn du deine Absicht klarer machen willst:

```swift
let score: Double = 99
```

Type inference macht den Code kürzer und bleibt dabei typsicher.

</details>

<details>
<summary>4. Was sind Optionals und warum sind sie wichtig?</summary>

#### Swift

Ein Optional ist ein Typ, der entweder Folgendes enthalten kann:

- einen Wert
- `nil`

Optionals sind wichtig, weil sie das Fehlen eines Werts explizit machen und
Laufzeitabstürze verhindern helfen, die durch fehlende Daten entstehen.

```swift
var nickname: String? = "Sam"
nickname = nil
```

Ohne Optionals könnte Swift Werte, die fehlen können, nicht sicher darstellen,
zum Beispiel:

- Benutzereingaben
- Felder aus Netzwerkantworten
- Datenbankwerte
- URLs, deren Initialisierung fehlschlagen kann

</details>

<details>
<summary>5. Was ist der Unterschied zwischen optional binding und force unwrapping?</summary>

#### Swift

Optional binding extrahiert den Wert eines Optionals sicher.
Force unwrapping extrahiert den Wert direkt und führt zu einem Absturz, wenn
das Optional `nil` ist.

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

Verwende in den meisten Fällen optional binding.
Verwende force unwrapping nur dann, wenn du absolut sicher bist, dass der Wert nicht `nil` ist.

</details>

<details>
<summary>6. Was ist optional chaining und wann sollte man es verwenden?</summary>

#### Swift

Optional chaining ist eine Möglichkeit, sicher auf Eigenschaften, Methoden oder
Subscripts eines optionalen Werts zuzugreifen.

Wenn das Optional `nil` ist, gibt der gesamte Ausdruck `nil` zurück, anstatt
abzustürzen.

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

Verwende optional chaining bei verschachtelten Optional-Werten, besonders in:

- Model-Objekten
- API-Antworten
- UI-Referenzen, die möglicherweise nicht existieren

</details>

<details>
<summary>7. Was ist der nil coalescing operator?</summary>

#### Swift

Der nil coalescing operator ist `??`.
Er liefert einen Standardwert, wenn ein Optional `nil` ist.

```swift
let username: String? = nil
let displayName = username ?? "Guest"
```

In diesem Beispiel wird `displayName` zu `"Guest"`.

Verwende `??`, wenn du einen Fallback-Wert für ein Optional brauchst.

</details>

<details>
<summary>8. Was sind Tuples und wann sollte man sie verwenden?</summary>

#### Swift

Ein Tuple ist eine Gruppe von Werten, die zu einem zusammengesetzten Wert
kombiniert werden.

```swift
let person = ("Alice", 28)
```

Tuple-Werte können auch benannt werden:

```swift
let httpResponse = (statusCode: 200, message: "OK")
print(httpResponse.statusCode)
```

Verwende Tuples für kurzlebige gruppierte Werte, zum Beispiel:

- Um mehrere Werte aus einer Funktion zurückzugeben
- Um einen kleinen zusammengehörigen Datensatz darzustellen
- Für temporäre lokale Daten

Für komplexere oder wiederverwendbare Daten sind `struct` oder `class` besser geeignet.

</details>

<details>
<summary>9. Was sind die wichtigsten Collection-Typen in Swift?</summary>

#### Swift

Die wichtigsten Collection-Typen in Swift sind:

1. `Array`
2. `Set`
3. `Dictionary`

#### Array

Speichert eine geordnete Liste von Werten.

```swift
let numbers = [1, 2, 3]
```

#### Set

Speichert eindeutige, ungeordnete Werte.

```swift
let uniqueNumbers: Set = [1, 2, 3]
```

#### Dictionary

Speichert Schlüssel-Wert-Paare.

```swift
let userAges = ["Alice": 25, "Bob": 30]
```

Diese Collections werden in der Swift-Entwicklung ständig verwendet.

</details>

<details>
<summary>10. Was ist der Unterschied zwischen Array, Set und Dictionary?</summary>

#### Swift

Der Unterschied liegt darin, wie sie Daten speichern und darauf zugreifen.

| Typ | Speichert | Reihenfolge | Eindeutigkeit | Zugriff |
| --- | --- | --- | --- | --- |
| `Array` | Eine Liste von Werten | Geordnet | Duplikate erlaubt | Nach Index |
| `Set` | Eindeutige Werte | Ungeordnet | Duplikate nicht erlaubt | Über Wertsuche |
| `Dictionary` | Schlüssel-Wert-Paare | Ungeordnet | Schlüssel müssen eindeutig sein | Nach Schlüssel |

#### Beispiel

```swift
let array = ["a", "b", "a"]
let set: Set = ["a", "b", "a"]
let dictionary = ["name": "Alice", "city": "Paris"]
```

- `Array` behält die Reihenfolge bei und kann Duplikate enthalten.
- `Set` entfernt Duplikate.
- `Dictionary` ordnet Schlüssel Werten zu.

</details>

<details>
<summary>11. Was sind Value Types im Vergleich zu Reference Types?</summary>

#### Swift

Value Types werden kopiert, wenn sie zugewiesen oder weitergegeben werden.
Reference Types teilen sich dieselbe Instanz.

#### Value Types

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

#### Reference Types

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

Verwende standardmäßig Value Types, außer wenn gemeinsam genutzter veränderbarer Zustand benötigt wird.

</details>

<details>
<summary>12. Was ist der Unterschied zwischen `struct` und `class`?</summary>

#### Swift

Der Hauptunterschied ist, dass `struct` ein Value Type und `class` ein Reference Type ist.

| Merkmal | `struct` | `class` |
| --- | --- | --- |
| Typ | Value Type | Reference Type |
| Kopierverhalten | Wird bei Zuweisung kopiert | Wird per Referenz geteilt |
| Vererbung | Nicht unterstützt | Unterstützt |
| Deinitializer | Nicht unterstützt | Unterstützt |
| Identitätsprüfung | Nein | Ja, mit `===` |

Verwende in den meisten Fällen `struct`.
Verwende `class`, wenn du Folgendes brauchst:

- Gemeinsam genutzten veränderbaren Zustand
- Vererbung
- Identitätssemantik

</details>

<details>
<summary>13. Was ist copy-on-write?</summary>

#### Swift

Copy-on-write ist eine Optimierung, bei der ein Wert nicht sofort kopiert wird.
Swift erstellt erst dann eine echte Kopie, wenn einer der Werte verändert wird.

Das wird häufig bei Standard-Collections verwendet, zum Beispiel:

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

Das bietet die Sicherheit von Value Types bei guter Performance.

</details>

<details>
<summary>14. Was ist Immutability und warum ist sie wichtig?</summary>

#### Swift

Immutability bedeutet, dass ein Wert nach seiner Erstellung nicht mehr verändert werden kann.

In Swift sind Werte, die mit `let` deklariert werden, unveränderlich.

```swift
let name = "Alice"
// name = "Bob" // Fehler
```

Immutability ist wichtig, weil sie:

- Code sicherer macht
- Bugs reduziert
- Zustände leichter nachvollziehbar macht
- Das Verständnis von Concurrency erleichtert

Verwende standardmäßig unveränderliche Werte und mache Dinge nur dann veränderbar, wenn es nötig ist.

</details>

<details>
<summary>15. Was sind Computed Properties?</summary>

#### Swift

Eine Computed Property speichert keinen Wert direkt.
Stattdessen berechnet sie den Wert jedes Mal, wenn auf sie zugegriffen wird.

```swift
struct Rectangle {
    var width: Double
    var height: Double

    var area: Double {
        width * height
    }
}
```

Computed Properties können auch `get` und `set` haben:

```swift
struct Square {
    var side: Double

    var area: Double {
        get { side * side }
        set { side = sqrt(newValue) }
    }
}
```

Verwende Computed Properties, wenn ein Wert von anderen Werten abhängt.

</details>

<details>
<summary>16. Was sind Property Observers (`willSet` / `didSet`)?</summary>

#### Swift

Property Observers ermöglichen es dir, auf Änderungen eines gespeicherten Property-Werts zu reagieren.

- `willSet` wird ausgeführt, bevor der neue Wert gespeichert wird
- `didSet` wird ausgeführt, nachdem der neue Wert gespeichert wurde

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

Verwende sie, wenn du:

- Änderungen protokollieren willst
- UI aktualisieren musst
- Seiteneffekte nach einer Wertänderung auslösen willst

</details>

<details>
<summary>17. Was sind Lazy Properties?</summary>

#### Swift

Eine Lazy Property wird erst dann initialisiert, wenn sie zum ersten Mal verwendet wird.

Sie wird mit dem Schlüsselwort `lazy` deklariert und muss eine `var` sein.

```swift
class DataManager {
    lazy var formatter: DateFormatter = {
        let formatter = DateFormatter()
        formatter.dateStyle = .medium
        return formatter
    }()
}
```

Verwende Lazy Properties, wenn:

- Die Initialisierung teuer ist
- Die Property möglicherweise nie verwendet wird
- Die Property nach der Initialisierung von `self` abhängt

</details>

<details>
<summary>18. Was sind Key Paths in Swift?</summary>

#### Swift

Key Paths sind typsichere Referenzen auf Properties.
Sie ermöglichen es, indirekt auf eine Property zuzugreifen.

```swift
struct User {
    let name: String
}

let keyPath = \User.name
let user = User(name: "Alice")

print(user[keyPath: keyPath]) // Alice
```

Key Paths sind nützlich für:

- Sortierung
- Mapping
- Generische APIs
- Das typsichere Beobachten oder Zugreifen auf verschachtelte Properties

</details>

<details>
<summary>19. Was ist Type Casting (`is`, `as`, `as?`, `as!`)?</summary>

#### Swift

Type Casting wird verwendet, um den Typ eines Werts zur Laufzeit zu prüfen oder umzuwandeln.

- `is` prüft, ob ein Wert von einem bestimmten Typ ist
- `as` upcastet zu einem Obertyp
- `as?` downcastet sicher und gibt ein Optional zurück
- `as!` downcastet erzwungen und führt zu einem Absturz, wenn es fehlschlägt

```swift
class Animal {}
class Dog: Animal {}

let animal: Animal = Dog()

print(animal is Dog) // true

let dog1 = animal as? Dog // Sicher
let dog2 = animal as! Dog // Unsicher bei falschem Typ
```

Verwende in den meisten Fällen `as?`.
Verwende `as!` nur dann, wenn ein Fehlschlag unmöglich ist.

</details>

<details>
<summary>20. Was ist der Unterschied zwischen `==` und `===`?</summary>

#### Swift

`==` prüft Wertgleichheit.
`===` prüft Referenzidentität.

#### `==`

Wird verwendet, um zu vergleichen, ob zwei Werte gleich sind.

```swift
let a = 5
let b = 5

print(a == b) // true
```

#### `===`

Wird nur bei Klassen verwendet, um zu prüfen, ob zwei Referenzen auf dieselbe
Instanz zeigen.

```swift
class User {}

let user1 = User()
let user2 = user1
let user3 = User()

print(user1 === user2) // true
print(user1 === user3) // false
```

Also:

- `==` bedeutet „gleicher Wert“
- `===` bedeutet „dasselbe Objekt im Speicher“

</details>

<details>
<summary>21. Wie funktioniert `switch` in Swift (pattern matching)?</summary>

#### Swift

`switch` in Swift ist leistungsfähig und unterstützt Pattern Matching.
Es kann Folgendes abgleichen:

- Exakte Werte
- Mehrere Werte
- Bereiche
- Tuples
- Enum-Cases
- Werte mit Bedingungen

Anders als in manchen Sprachen muss `switch` in Swift vollständig sein.
Das bedeutet, dass jeder mögliche Fall behandelt werden muss.

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

Swift-`switch` wird oft verwendet, weil es sicherer und ausdrucksstärker ist als eine lange Kette von `if`-Anweisungen.

</details>

<details>
<summary>22. Was ist `fallthrough` und wann sollte es vermieden werden?</summary>

#### Swift

`fallthrough` bewirkt, dass die Ausführung in einem `switch` von einem `case`
zum nächsten weiterläuft.

Standardmäßig fällt Swift nicht automatisch durch.

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

Ausgabe:

```swift
One
Two
```

Vermeide `fallthrough` in den meisten Fällen, weil es:

- Die Logik weniger klar macht
- Unerwartetes Verhalten verursachen kann
- Meistens sauberere Alternativen hat

Verwende es nur dann, wenn du bewusst möchtest, dass auch der nächste `case` ausgeführt wird.

</details>

<details>
<summary>23. Was ist eine `guard`-Anweisung und wann sollte man sie verwenden?</summary>

#### Swift

`guard` wird für einen frühen Ausstieg verwendet.
Es prüft eine Bedingung, und wenn die Bedingung fehlschlägt, muss die Ausführung
den aktuellen Scope verlassen.

```swift
func printName(_ name: String?) {
    guard let name = name else {
        print("Name is missing")
        return
    }

    print(name)
}
```

Verwende `guard`, wenn:

- Ein erforderlicher Wert fehlt
- Vorbedingungen nicht erfüllt sind
- Du tiefe Verschachtelungen vermeiden willst

Es macht den Code flacher und leichter lesbar.

</details>

<details>
<summary>24. Was ist der Unterschied zwischen `if let` und `guard let`?</summary>

#### Swift

Beide werden für optional binding verwendet, aber auf unterschiedliche Weise.

| Merkmal | `if let` | `guard let` |
| --- | --- | --- |
| Hauptverwendung | Bedingter Zweig | Früher Ausstieg |
| Scope des entpackten Werts | Innerhalb des `if`-Blocks | Nach der `guard`-Anweisung |
| Lesbarkeit | Gut für kurze Prüfungen | Besser für notwendige Bedingungen |

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

Verwende `if let` für optionale Arbeit innerhalb eines lokalen Zweigs.
Verwende `guard let`, wenn der Wert für den Rest der Funktion erforderlich ist.

</details>

<details>
<summary>25. Was ist ein half-open range?</summary>

#### Swift

Ein half-open range schließt die untere Grenze ein, aber die obere Grenze aus.

Er verwendet `..<`

```swift
for i in 0..<5 {
    print(i)
}
```

Ausgabe:

```swift
0
1
2
3
4
```

Half-open ranges sind nützlich für:

- Schleifen
- Array-Indizierung
- Situationen, in denen der Endwert nicht eingeschlossen werden soll

</details>

<details>
<summary>26. Was ist eine `where`-Klausel?</summary>

#### Swift

Eine `where`-Klausel fügt einem Pattern, einer Schleife, einer generischen
Einschränkung oder einem `catch`-Block eine zusätzliche Bedingung hinzu.

#### In `switch`

```swift
let point = (2, 2)

switch point {
case let (x, y) where x == y:
    print("x equals y")
default:
    print("No match")
}
```

#### In Schleifen

```swift
for number in 1...10 where number.isMultiple(of: 2) {
    print(number)
}
```

Verwende `where`, wenn du ein präziseres Matching oder Filtering möchtest.

</details>

<details>
<summary>27. Was macht `defer`?</summary>

#### Swift

`defer` plant Code so ein, dass er direkt vor dem Verlassen des aktuellen
Scopes ausgeführt wird.

Er wird ausgeführt, egal wie der Scope verlassen wird:

- Normale Rückgabe
- Frühe Rückgabe
- Geworfener Fehler

```swift
func performTask() {
    print("Start")

    defer {
        print("Cleanup")
    }

    print("Work")
}
```

Ausgabe:

```swift
Start
Work
Cleanup
```

`defer` ist nützlich für Aufräumarbeiten wie:

- Dateien schließen
- Ressourcen entsperren
- Zustand zurücksetzen

</details>

<details>
<summary>28. Was sind `break` und `continue`?</summary>

#### Swift

`break` beendet die aktuelle Schleife oder den aktuellen `switch`.
`continue` überspringt die aktuelle Schleifeniteration und geht zur nächsten weiter.

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

Verwende `break`, um die Verarbeitung zu beenden.
Verwende `continue`, um eine Iteration zu überspringen.

</details>

<details>
<summary>29. Wofür wird `stride()` verwendet?</summary>

#### Swift

`stride()` wird verwendet, um Sequenzen zu erzeugen, die sich in Schritten bewegen.

Es ist nützlich, wenn du nicht um `1` erhöhen willst.

#### Beispiel mit `through`

```swift
for number in stride(from: 0, through: 10, by: 2) {
    print(number)
}
```

#### Beispiel mit `to`

```swift
for number in stride(from: 0, to: 10, by: 2) {
    print(number)
}
```

Unterschied:

- `through` schließt den Endwert ein, wenn möglich
- `to` schließt den Endwert aus

</details>

<details>
<summary>30. Was sind Raw Strings?</summary>

#### Swift

Raw Strings erlauben es dir, String-Literale zu schreiben, ohne Backslashes und
Anführungszeichen als normale Escape-Zeichen zu behandeln.

Sie verwenden `#` um den String herum.

```swift
let path = #"C:\Users\Name\Documents"#
let text = #"He said "Hello""#
```

Wenn du Interpolation innerhalb eines Raw Strings möchtest, verwende `\#(...)`:

```swift
let name = "Alice"
let message = #"Hello, \#(name)"#
```

Raw Strings sind nützlich für:

- Reguläre Ausdrücke
- Dateipfade
- JSON-Snippets
- Strings mit vielen Backslashes oder Anführungszeichen

</details>

<details>
<summary>31. Was sind Closures in Swift?</summary>

#### Swift

Closures sind eigenständige Codeblöcke, die weitergegeben und später
ausgeführt werden können.

Sie ähneln Funktionen, können aber in Variablen gespeichert werden und Werte
aus dem umgebenden Scope erfassen.

```swift
let greet = { (name: String) in
    print("Hello, \(name)")
}

greet("Alice")
```

Closures werden häufig verwendet für:

- Callbacks
- Completion Handler
- Sortierung
- Funktionale Operationen wie `map` und `filter`

</details>

<details>
<summary>32. Escaping vs non-escaping closures?</summary>

#### Swift

Eine non-escaping closure wird ausgeführt, bevor die Funktion zurückkehrt.
Eine escaping closure kann gespeichert und nach der Rückgabe der Funktion
ausgeführt werden.

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

Verwende standardmäßig non-escaping closures.
Verwende escaping closures für asynchrone Arbeit, Callbacks oder gespeicherte closures.

</details>

<details>
<summary>33. Was bedeutet `@escaping`?</summary>

#### Swift

`@escaping` bedeutet, dass die closure länger leben kann als die Funktion, an
die sie übergeben wurde.

Mit anderen Worten: Es ist nicht garantiert, dass die closure vor der Rückgabe
der Funktion ausgeführt wird.

```swift
class Downloader {
    var completion: (() -> Void)?

    func fetch(completion: @escaping () -> Void) {
        self.completion = completion
    }
}
```

`@escaping` wird normalerweise benötigt, wenn die closure:

- In einer Property gespeichert wird
- Asynchron ausgeführt wird
- An eine andere Funktion weitergegeben wird, die sie speichert

</details>

<details>
<summary>34. Was sind Trailing Closures?</summary>

#### Swift

Eine trailing closure ist eine closure, die nach den Klammern einer Funktion geschrieben wird.

Diese Syntax ist sauberer, wenn das letzte Argument eine closure ist.

```swift
func perform(action: () -> Void) {
    action()
}

perform {
    print("Done")
}
```

Trailing Closures kommen häufig vor in:

- Asynchronen APIs
- UIKit- und SwiftUI-Callbacks
- Collection-Operationen

</details>

<details>
<summary>35. Was ist Value Capturing in Closures?</summary>

#### Swift

Closures können Werte aus dem umgebenden Scope erfassen und weiterverwenden,
selbst wenn dieser Scope normalerweise schon beendet wäre.

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

Hier erfasst die closure `count` und hält ihn am Leben.

Das ist nützlich, kann aber auch zu Speicherproblemen führen, wenn Objekte
versehentlich stark erfasst werden.

</details>

<details>
<summary>36. Wie verwaltet Swift Speicher in Closures?</summary>

#### Swift

Swift verwendet ARC (Automatic Reference Counting).
Closures sind Reference Types, deshalb können sie Objekte stark erfassen.

Wenn eine closure `self` stark erfasst und `self` die closure ebenfalls stark
hält, kann ein retain cycle entstehen.

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

Um Memory Leaks zu vermeiden, verwende bei Bedarf Capture Lists:

- `[weak self]`, wenn `self` zu `nil` werden kann
- `[unowned self]`, wenn `self` weiterhin existieren muss

</details>

<details>
<summary>37. Was sind Higher-Order Functions (`map`, `filter`, `reduce`)?</summary>

#### Swift

Higher-Order Functions sind Funktionen, die andere Funktionen oder closures als
Argumente annehmen oder zurückgeben.

In Swift sind häufige Higher-Order Functions für Collections:

- `map`
- `filter`
- `reduce`

#### `map`

Transformiert jedes Element.

```swift
let numbers = [1, 2, 3]
let doubled = numbers.map { $0 * 2 }
```

#### `filter`

Behält nur passende Elemente.

```swift
let evenNumbers = numbers.filter { $0.isMultiple(of: 2) }
```

#### `reduce`

Kombiniert alle Elemente zu einem Ergebnis.

```swift
let sum = numbers.reduce(0) { $0 + $1 }
```

Diese Funktionen machen Code kürzer und ausdrucksstärker.

</details>

<details>
<summary>38. Was ist der Unterschied zwischen `map` und `compactMap`?</summary>

#### Swift

`map` transformiert jedes Element und behält die gleiche Anzahl an Elementen.
`compactMap` transformiert Elemente und entfernt `nil`-Ergebnisse.

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

Verwende `map`, wenn alle transformierten Ergebnisse im Output bleiben sollen.
Verwende `compactMap`, wenn du fehlgeschlagene Konvertierungen oder `nil`-Werte ignorieren willst.

</details>

<details>
<summary>39. Was ist Currying (konzeptionell)?</summary>

#### Swift

Currying ist die Idee, eine Funktion mit mehreren Argumenten in eine Folge von
Funktionen umzuwandeln, die jeweils ein Argument annehmen.

Konzeptionell:

```swift
func add(_ a: Int) -> (Int) -> Int {
    return { b in
        a + b
    }
}

let addFive = add(5)
print(addFive(3)) // 8
```

Currying ist nützlich für:

- Partial Application
- Wiederverwendbare spezialisierte Funktionen
- Konzepte der funktionalen Programmierung

Es ist eher ein Konzept als etwas, das man täglich in typischem Swift-App-Code verwendet.

</details>

<details>
<summary>40. Was ist `@autoclosure`?</summary>

#### Swift

`@autoclosure` verpackt einen Ausdruck automatisch in eine closure.

Dadurch kannst du einen Ausdruck dort übergeben, wo eine closure erwartet wird,
ohne die closure-Syntax manuell zu schreiben.

```swift
func logIfTrue(_ condition: @autoclosure () -> Bool) {
    if condition() {
        print("True")
    }
}

logIfTrue(2 > 1)
```

Ohne `@autoclosure` würdest du schreiben:

```swift
logIfTrue({ 2 > 1 })
```

Es wird oft in APIs wie `assert` verwendet.
Verwende es vorsichtig, weil es verbergen kann, dass eine closure erstellt wird.

</details>

<details>
<summary>41. Was sind Generics und warum sind sie nützlich?</summary>

#### Swift

Generics ermöglichen es dir, flexiblen, wiederverwendbaren Code zu schreiben,
der mit verschiedenen Typen funktioniert und dabei typsicher bleibt.

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

Hier ist `T` ein Platzhalter für einen generischen Typ.

Generics sind nützlich, weil sie:

- Code-Duplizierung reduzieren
- Starke Typsicherheit erhalten
- APIs wiederverwendbarer machen

</details>

<details>
<summary>42. Was sind Protocols?</summary>

#### Swift

Ein Protocol definiert eine Menge von Anforderungen, die ein Typ erfüllen muss.

Es kann Folgendes verlangen:

- Properties
- Methoden
- Initializer

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

Protocols werden verwendet, um gemeinsames Verhalten zu definieren, ohne Vererbung zu erzwingen.

</details>

<details>
<summary>43. Was ist protocol-oriented programming (POP)?</summary>

#### Swift

Protocol-oriented programming ist ein Ansatz, bei dem Verhalten mit Protocols
und Protocol Extensions aufgebaut wird, anstatt sich hauptsächlich auf
Klassenvererbung zu stützen.

In Swift ist das ein zentraler Designstil.

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

POP ist nützlich, weil es:

- Komposition statt Vererbung fördert
- Code-Wiederverwendung verbessert
- Gut mit Value Types wie `struct` funktioniert

</details>

<details>
<summary>44. Was sind Associated Types?</summary>

#### Swift

Ein Associated Type ist ein Platzhaltertyp innerhalb eines Protocols.

Er erlaubt dem konformen Typ zu entscheiden, welcher konkrete Typ verwendet wird.

```swift
protocol Container {
    associatedtype Item
    var items: [Item] { get set }
}

struct IntContainer: Container {
    var items: [Int]
}
```

Associated Types sind nützlich, wenn ein Protocol mit verschiedenen Datentypen
arbeiten soll und trotzdem typsicher bleiben muss.

</details>

<details>
<summary>45. Was ist Protocol Composition?</summary>

#### Swift

Protocol Composition bedeutet, mehrere Protocols zu einer einzigen
Typanforderung zu kombinieren.

Dabei wird `&` verwendet.

```swift
protocol Readable {}
protocol Writable {}

func process(file: Readable & Writable) {
    print("Can read and write")
}
```

Verwende Protocol Composition, wenn ein Wert mehrere Verhaltensweisen gleichzeitig erfüllen muss.

</details>

<details>
<summary>46. Was sind Protocol Extensions?</summary>

#### Swift

Protocol Extensions ermöglichen es dir, Protocols Standardimplementierungen hinzuzufügen.

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

Das bedeutet, dass konforme Typen gemeinsames Verhalten automatisch erhalten können.

Protocol Extensions sind ein zentraler Bestandteil von protocol-oriented programming.

</details>

<details>
<summary>47. Was ist Conditional Conformance?</summary>

#### Swift

Conditional Conformance bedeutet, dass ein generischer Typ nur dann einem
Protocol entspricht, wenn bestimmte Bedingungen erfüllt sind.

```swift
extension Array: Equatable where Element: Equatable {}
```

Das bedeutet, dass `Array` nur dann `Equatable` ist, wenn seine Elemente `Equatable` sind.

Das ist nützlich, um generische APIs zu bauen, die präzise und typsicher bleiben.

</details>

<details>
<summary>48. Was ist Type Erasure?</summary>

#### Swift

Type Erasure verbirgt einen bestimmten konkreten Typ hinter einem gemeinsamen
Wrapper oder einer abstrakten Schnittstelle.

Das wird oft benötigt, wenn man mit Protocols arbeitet, die Folgendes haben:

- Associated Types
- `Self`-Anforderungen

Zum Beispiel verwendet SwiftUI `AnyView` als type-erased Wrapper.

```swift
let views: [AnyView] = [
    AnyView(Text("Hello")),
    AnyView(Image(systemName: "star"))
]
```

Type Erasure hilft dabei, Werte mit unterschiedlichen konkreten Typen
einheitlich zu speichern oder weiterzugeben.

</details>

<details>
<summary>49. Was ist der Unterschied zwischen `Self` und `self`?</summary>

#### Swift

`Self` und `self` sind unterschiedlich.

- `Self` bezieht sich auf den Typ selbst
- `self` bezieht sich auf die aktuelle Instanz

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

Verwende `self`, wenn du mit dem aktuellen Objekt oder Wert arbeitest.
Verwende `Self`, wenn du auf Typsystem-Ebene auf den konkreten Typ verweist.

</details>

<details>
<summary>50. Wie funktioniert ARC in Swift?</summary>

#### Swift

ARC steht für Automatic Reference Counting.

Es ist Swifts Speicherverwaltungssystem für Klasseninstanzen.
ARC verfolgt automatisch, wie viele starke Referenzen auf ein Objekt zeigen.

- Wenn die Referenzanzahl steigt, bleibt das Objekt im Speicher
- Wenn die Referenzanzahl auf null fällt, wird das Objekt freigegeben

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

ARC verwaltet Value Types wie `struct` und `enum` nicht auf dieselbe Weise,
weil sie keine Reference Types sind.

Das Hauptrisiko bei ARC ist ein retain cycle, der normalerweise mit `weak`- oder `unowned`-Referenzen gelöst wird.

</details>

<details>
<summary>51. Was ist ein Retain Cycle?</summary>

#### Swift

Ein retain cycle entsteht, wenn zwei oder mehr Objekte vom Reference Type
starke Referenzen aufeinander halten, sodass keines von ihnen freigegeben
werden kann.

Das verursacht normalerweise ein memory leak.

```swift
class Person {
    var apartment: Apartment?
}

class Apartment {
    var tenant: Person?
}
```

Wenn beide Referenzen stark sind, halten sich die Objekte gegenseitig am Leben.

Retain Cycles treten häufig auf bei:

- Closures, die `self` erfassen
- Parent-Child-Beziehungen zwischen Objekten
- Falsch implementierten Delegate-Patterns

</details>

<details>
<summary>52. Was ist der Unterschied zwischen `weak` und `unowned`?</summary>

#### Swift

Sowohl `weak` als auch `unowned` werden verwendet, um retain cycles zu
vermeiden, aber sie verhalten sich unterschiedlich.

| Merkmal | `weak` | `unowned` |
| --- | --- | --- |
| Optional | Ja | Nein |
| Kann `nil` werden | Ja | Nein |
| Sicherheit | Sicherer | Weniger sicher |
| Verwenden, wenn | Das referenzierte Objekt verschwinden kann | Das referenzierte Objekt existieren muss |

#### Beispiel

```swift
weak var delegate: SomeDelegate?
unowned var owner: Owner
```

Verwende `weak`, wenn die Referenz `nil` werden kann.
Verwende `unowned`, wenn die Referenz immer auf ein gültiges Objekt zeigen soll.

</details>

<details>
<summary>53. Wann würdest du `unowned` statt `weak` verwenden?</summary>

#### Swift

Verwende `unowned`, wenn das referenzierte Objekt immer existieren muss,
solange diese Referenz verwendet wird.

Das ist häufig der Fall, wenn zwei Objekte verknüpft sind, aber eines die
Lebensdauer des anderen klar besitzt.

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

Verwende `unowned` nur dann, wenn du sicher bist, dass auf die Referenz nie
zugegriffen wird, nachdem das Objekt freigegeben wurde.

Andernfalls verwende `weak`.

</details>

<details>
<summary>54. Was ist ein Memory Leak?</summary>

#### Swift

Ein memory leak entsteht, wenn Speicher nicht mehr benötigt wird, aber trotzdem
nicht freigegeben wird.

In Swift passiert das meistens, weil Objekte noch stark referenziert werden,
oft aufgrund von retain cycles.

Anzeichen für ein memory leak:

- Objekte werden nie freigegeben
- Der Speicherverbrauch wächst ständig
- Screens oder View Models bleiben nach dem Schließen im Speicher

Memory Leaks können zu Folgendem führen:

- Höherem Speicherverbrauch
- Performance-Problemen
- Beendigung der App durch das System

</details>

<details>
<summary>55. Wie debuggt man Speicherprobleme?</summary>

#### Swift

Übliche Wege, Speicherprobleme in Swift zu debuggen, sind:

1. Xcode Memory Graph Debugger
2. Instruments mit dem Leaks-Tool
3. Instruments mit Allocations
4. Prüfen, ob `deinit` aufgerufen wird

#### Beispiel

```swift
deinit {
    print("Deallocated")
}
```

Wenn `deinit` nicht wie erwartet aufgerufen wird, hält noch etwas das Objekt fest.

Ein typischer Workflow ist:

- Den Screen-Flow reproduzieren
- Den Screen schließen
- Den Memory Graph prüfen
- Nach retain cycles oder unerwarteten starken Referenzen suchen

</details>

<details>
<summary>56. Wie verwaltet Swift Speicher für Value Types und Reference Types?</summary>

#### Swift

Swift verwaltet Speicher für Value Types und Reference Types unterschiedlich.

#### Value Types

- `struct`
- `enum`
- `tuple`

Sie werden bei Zuweisung oder bei der Übergabe an Funktionen kopiert.
Sie verwenden ARC nicht auf dieselbe Weise wie Klasseninstanzen.

#### Reference Types

- `class`

Sie werden per Referenz geteilt.
Swift verwendet ARC, um ihre Lebensdauer zu verwalten.

Der Hauptunterschied ist also:

- Value Types kopieren Daten
- Reference Types teilen sich dieselbe Instanz

</details>

<details>
<summary>57. Was ist async/await in Swift?</summary>

#### Swift

`async/await` ist Swifts moderne Syntax für asynchrone Programmierung.

Dadurch sieht asynchroner Code eher wie normaler sequentieller Code aus.

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

Vorteile:

- Saubererer asynchroner Code
- Bessere Lesbarkeit
- Einfachere Fehlerbehandlung mit `try`

</details>

<details>
<summary>58. Was ist Structured Concurrency?</summary>

#### Swift

Structured concurrency bedeutet, dass asynchrone Arbeit in einer klaren
Hierarchie aus Parent- und Child-Tasks organisiert ist.

Das hilft Swift bei der Verwaltung von:

- Der Lebensdauer von Tasks
- Cancellation
- Error Propagation

Bei structured concurrency gehören Child-Tasks normalerweise zu dem Scope, in
dem sie erstellt wurden, und laufen nicht unkontrolliert weiter.

Häufige Werkzeuge für structured concurrency sind:

- `async let`
- `TaskGroup`

Das macht nebenläufigen Code sicherer und leichter nachvollziehbar.

</details>

<details>
<summary>59. Was sind Tasks und Task Groups?</summary>

#### Swift

Ein `Task` ist eine Einheit asynchroner Arbeit.
Eine `TaskGroup` erlaubt es dir, mehrere Child-Tasks parallel auszuführen und
ihre Ergebnisse zu sammeln.

#### Task

```swift
Task {
    print("Running async work")
}
```

#### Task Group

```swift
await withTaskGroup(of: Int.self) { group in
    group.addTask { 1 }
    group.addTask { 2 }

    for await value in group {
        print(value)
    }
}
```

Verwende:

- `Task` für eine asynchrone Operation
- `TaskGroup` für mehrere parallele Child-Tasks

</details>

<details>
<summary>60. Was ist `MainActor` und warum ist er wichtig?</summary>

#### Swift

`MainActor` ist ein global actor, der sicherstellt, dass Code auf dem Hauptthread ausgeführt wird.

Das ist wichtig, weil UI-Aktualisierungen auf dem Hauptthread stattfinden müssen.

```swift
@MainActor
class ViewModel {
    var title = ""

    func updateTitle() {
        title = "Updated"
    }
}
```

Du kannst auch explizit zu ihm wechseln:

```swift
await MainActor.run {
    print("Update UI")
}
```

`MainActor` hilft, Threading-Bugs zu vermeiden, und macht UI-bezogenen Code sicherer.

</details>

<details>
<summary>61. Was sind Actors und wie verhindern sie Race Conditions?</summary>

#### Swift

Actors sind Reference Types, die ihren veränderbaren Zustand vor unsicherem
gleichzeitigem Zugriff schützen.

Sie helfen, race conditions zu verhindern, indem sie Zustand isolieren, sodass
jeweils nur ein Task auf diesen veränderbaren Zustand zugreifen kann.

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

Um von außen auf actor-isolierten Zustand zuzugreifen, verwendet man
normalerweise `await`.

Actors sind in moderner Swift Concurrency wichtig, weil sie in vielen Fällen
eine sicherere Alternative zu manuellem Locking bieten.

</details>

<details>
<summary>62. Was ist eine Data Race und wie verhindert Swift sie?</summary>

#### Swift

Eine data race entsteht, wenn mehrere Threads oder Tasks gleichzeitig auf
dieselben veränderbaren Daten zugreifen und mindestens einer davon schreibt.

Das kann zu unvorhersehbarem Verhalten und Abstürzen führen.

Swift hilft, data races zu verhindern mit:

- Actor Isolation
- `Sendable`
- Structured Concurrency
- Main-Actor-Isolation für UI-Code

In modernem Swift sind die Concurrency-Features darauf ausgelegt, unsicheren
gemeinsam genutzten veränderbaren Zustand früher zu erkennen und leichter zu vermeiden.

</details>

<details>
<summary>63. Was ist der Unterschied zwischen GCD und moderner Concurrency?</summary>

#### Swift

Sowohl GCD als auch moderne Swift Concurrency behandeln asynchrone Arbeit, aber
sie verwenden unterschiedliche Modelle.

| Merkmal | GCD | Moderne Concurrency |
| --- | --- | --- |
| Stil | Callback-basiert | `async/await` |
| Lesbarkeit | Mehr Verschachtelung | Linearer |
| Cancellation | Manuell | Eingebaute Unterstützung |
| Sicherheit | Niedrigeres Level | Sicherer und strukturierter |
| Werkzeuge | `DispatchQueue` | `Task`, actors, `TaskGroup`, `MainActor` |

#### GCD-Beispiel

```swift
DispatchQueue.global().async {
    print("Background work")
}
```

#### Modernes-Concurrency-Beispiel

```swift
Task {
    print("Async work")
}
```

Moderne Concurrency wird für neuen Swift-Code normalerweise bevorzugt.

</details>

<details>
<summary>64. Wie synchronisiert man den Zugriff auf gemeinsamen Zustand?</summary>

#### Swift

Du synchronisierst gemeinsamen Zustand, indem du sicherstellst, dass
nebenläufiger Code dieselben veränderbaren Daten nicht unsicher liest und schreibt.

Häufige Ansätze:

- Actors
- Serielle Queues
- Locks
- `MainActor` für UI-Zustand

#### Bevorzugter moderner Ansatz

```swift
actor Store {
    private var items: [String] = []

    func add(_ item: String) {
        items.append(item)
    }
}
```

In modernem Swift sind actors normalerweise der sicherste Standard für gemeinsam genutzten veränderbaren Zustand.

</details>

<details>
<summary>65. Was ist `Sendable` in Swift?</summary>

#### Swift

`Sendable` ist ein Protocol, das einen Typ als sicher für die Übertragung
zwischen Concurrency-Domänen kennzeichnet.

Das ist wichtig, wenn Werte zwischen Tasks oder Actors übergeben werden.

```swift
struct User: Sendable {
    let id: Int
    let name: String
}
```

Value Types mit unveränderlichen gespeicherten Properties sind oft von Natur aus `Sendable`.

`Sendable` hilft Swift, unsichere gemeinsame Nutzung von veränderbarem Zustand
in nebenläufigem Code zu erkennen.

</details>

<details>
<summary>66. Wie funktioniert Fehlerbehandlung in Swift?</summary>

#### Swift

Swift verwendet typisierte Fehlerbehandlung mit `throw`, `throws`, `do`, `try`
und `catch`.

#### Beispiel

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

Das macht Fehlerbehandlung explizit und sicherer als stillschweigendes Ignorieren von Fehlern.

</details>

<details>
<summary>67. Was ist der Unterschied zwischen `try`, `try?` und `try!`?</summary>

#### Swift

Alle drei werden mit Funktionen verwendet, die Fehler werfen können, aber sie
behandeln Fehler unterschiedlich.

| Schlüsselwort | Verhalten |
| --- | --- |
| `try` | Propagiert oder behandelt den Fehler normal |
| `try?` | Wandelt das Ergebnis in ein Optional um und gibt bei Fehler `nil` zurück |
| `try!` | Erzwingt Erfolg und stürzt ab, wenn ein Fehler geworfen wird |

#### Beispiel

```swift
let value1 = try someThrowingFunction()
let value2 = try? someThrowingFunction()
let value3 = try! someThrowingFunction()
```

Verwende:

- `try` für normale Fehlerbehandlung
- `try?`, wenn ein Fehlschlag als `nil` ignoriert werden kann
- `try!` nur dann, wenn ein Fehlschlag unmöglich ist

</details>

<details>
<summary>68. Was ist `throws` vs `rethrows`?</summary>

#### Swift

`throws` bedeutet, dass eine Funktion ihren eigenen Fehler werfen kann.
`rethrows` bedeutet, dass eine Funktion nur dann wirft, wenn eines ihrer
Funktionsargumente einen Fehler wirft.

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

Verwende `rethrows` für Wrapper-Funktionen, die selbst keine Fehler werfen,
aber eine closure aufrufen, die werfen kann.

</details>

<details>
<summary>69. Was ist der Typ Result?</summary>

#### Swift

`Result` ist ein Enum, das entweder Folgendes darstellt:

- Erfolg mit einem Wert
- Fehlschlag mit einem Fehler

```swift
let result: Result<String, Error> = .success("Done")
```

Er ist ungefähr so definiert:

```swift
enum Result<Success, Failure: Error> {
    case success(Success)
    case failure(Failure)
}
```

`Result` ist nützlich, wenn du Erfolg oder Fehlschlag explizit weitergeben
willst, besonders in Callbacks oder asynchronen APIs.

</details>

<details>
<summary>70. Wie propagiert man Fehler?</summary>

#### Swift

Du propagierst Fehler, indem du eine Funktion mit `throws` markierst und `try`
verwendest, wenn du eine andere Funktion aufrufst, die Fehler werfen kann.

```swift
func loadData() throws {
    throw NSError(domain: "Example", code: 1)
}

func processData() throws {
    try loadData()
}
```

Hier behandelt `processData()` den Fehler nicht selbst.
Es gibt den Fehler an seinen Aufrufer weiter.

Das ist nützlich, wenn eine Funktion auf niedrigerer Ebene einen Fehler melden
soll und eine höhere Ebene entscheiden soll, wie damit umgegangen wird.

</details>

<details>
<summary>71. Was sind Property Wrappers?</summary>

#### Swift

Property Wrappers sind ein Swift-Feature, mit dem du wiederverwendbares Verhalten
um gespeicherte Properties herum hinzufügen kannst.

Sie werden mit `@propertyWrapper` deklariert.

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

Property Wrappers sind nützlich für:

- Validierung
- Formatierung
- Persistenz
- Dependency Injection

</details>

<details>
<summary>72. Was sind opaque return types (`some`)?</summary>

#### Swift

Opaque Return Types erlauben es einer Funktion, einen Wert eines bestimmten
Typs zurückzugeben, ohne diesen genauen Typ im API offenzulegen.

Sie verwenden das Schlüsselwort `some`.

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Der Aufrufer weiß, dass der zurückgegebene Wert `View` entspricht, muss aber
den konkreten Typ nicht kennen.

Opaque Types werden in SwiftUI häufig verwendet.

</details>

<details>
<summary>73. Was ist der Unterschied zwischen opaque types und generics?</summary>

#### Swift

Sowohl opaque types als auch generics arbeiten mit abstrakten Typen, aber sie
lösen unterschiedliche Probleme.

| Merkmal | Generics | Opaque Types |
| --- | --- | --- |
| Wer wählt den konkreten Typ? | Aufrufer | Implementierung |
| Syntax | `<T>` | `some Protocol` |
| Hauptverwendung | Flexible wiederverwendbare APIs | Konkrete Rückgabetypen verbergen |

#### Generics-Beispiel

```swift
func echo<T>(_ value: T) -> T {
    value
}
```

#### Opaque-Type-Beispiel

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Verwende Generics, wenn der Aufrufer den Typ liefert.
Verwende Opaque Types, wenn die Implementierung den Typ liefert, ihn aber verbirgt.

</details>

<details>
<summary>74. Was sind Result Builders?</summary>

#### Swift

Result Builders sind ein Feature, mit dem Swift komplexe Werte aus einem Block
deklarativen Codes aufbauen kann.

Sie werden in SwiftUI intensiv verwendet.

```swift
@resultBuilder
struct StringBuilder {
    static func buildBlock(_ components: String...) -> String {
        components.joined(separator: " ")
    }
}
```

Ein Result Builder transformiert mehrere Ausdrücke in ein einziges Endergebnis.

Das ist nützlich für DSL-artige APIs.

</details>

<details>
<summary>75. Was sind Custom Operators?</summary>

#### Swift

Custom Operators erlauben es dir, eigene Operatoren in Swift zu definieren.

```swift
infix operator +++

func +++ (lhs: Int, rhs: Int) -> Int {
    lhs + rhs + 1
}
```

Du kannst erstellen:

- Prefix-Operatoren
- Infix-Operatoren
- Postfix-Operatoren

Sie können mächtig sein, sollten aber vorsichtig verwendet werden.

Wenn sie übermäßig verwendet werden, wird der Code schwerer lesbar.

</details>

<details>
<summary>76. Was ist dynamic dispatch vs static dispatch?</summary>

#### Swift

Dispatch beschreibt, wie Swift entscheidet, welche Methodenimplementierung aufgerufen wird.

#### Static Dispatch

Der Methodenaufruf wird zur Compile-Zeit aufgelöst.
Er ist normalerweise schneller.

Das ist häufig bei:

- `struct`
- `enum`
- `final`-Methoden

#### Dynamic Dispatch

Der Methodenaufruf wird zur Laufzeit aufgelöst.
Er ist flexibler, hat aber mehr Overhead.

Das ist häufig bei:

- Klassen mit Vererbung
- `@objc dynamic`

Static Dispatch konzentriert sich auf Performance.
Dynamic Dispatch konzentriert sich auf Laufzeitflexibilität.

</details>

<details>
<summary>77. Was ist ein Phantom Type?</summary>

#### Swift

Ein Phantom Type ist ein generischer Typ-Parameter, der nur zur Compile-Zeit
verwendet und nicht zur Laufzeit gespeichert wird.

Er hilft dabei, APIs sicherer zu machen, indem zusätzliche Typinformation im
Typsystem codiert wird.

```swift
struct ID<Tag> {
    let value: String
}

enum UserTag {}
enum OrderTag {}

let userID = ID<UserTag>(value: "123")
let orderID = ID<OrderTag>(value: "123")
```

Obwohl beide Werte einen `String` enthalten, behandelt Swift sie als unterschiedliche Typen.

</details>

<details>
<summary>78. Was ist Escape Analysis?</summary>

#### Swift

Escape Analysis ist ein Optimierungskonzept des Compilers, mit dem bestimmt
wird, ob ein Wert oder eine closure den Scope verlässt, in dem sie erstellt wurde.

Wenn etwas den Scope nicht verlässt, kann Swift Speicherverbrauch und
Aufrufverhalten effizienter optimieren.

Dieses Konzept hängt zusammen mit:

- Escaping vs non-escaping closures
- Entscheidungen zur Optimierung von Stack vs Heap

In typischen Swift-Interviews reicht es meistens zu wissen, dass non-escaping
closures für den Compiler leichter zu optimieren sind.

</details>

<details>
<summary>79. Was ist ein Function Builder (Result Builder)?</summary>

#### Swift

Function Builder ist der alte Name für das, was Swift heute Result Builder nennt.

Es ist ein Feature, das einen Block von Ausdrücken in ein einzelnes Ergebnis
transformiert, häufig für deklarative APIs.

SwiftUI verwendet das stark bei der View-Building-Syntax.

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

Also gilt heute:

- `function builder` ist der ältere Begriff
- `result builder` ist der aktuelle offizielle Begriff

</details>

<details>
<summary>80. Was ist SwiftUI und wie unterscheidet es sich von UIKit?</summary>

#### Swift

SwiftUI ist Apples deklaratives UI-Framework zum Erstellen von Oberflächen auf
den Apple-Plattformen.

UIKit ist das ältere imperative Framework zum Erstellen von iOS-Oberflächen.

| Merkmal | SwiftUI | UIKit |
| --- | --- | --- |
| Stil | Deklarativ | Imperativ |
| UI-Aktualisierungen | Zustandsgetrieben | Manuelle Updates |
| Syntax | Swift-basiertes DSL | Klassen und Lifecycle-APIs |
| Typische Nutzung | Moderne UI-Entwicklung für Apple | Reifes iOS-UI-Framework |

#### SwiftUI-Beispiel

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
    }
}
```

#### UIKit-Beispiel

```swift
let label = UILabel()
label.text = "Hello"
```

SwiftUI ermöglicht normalerweise schnellere UI-Entwicklung und eine bessere
Integration mit modernen Swift-Features.
UIKit bietet mehr Kontrolle auf niedriger Ebene und ein größeres Legacy-Ökosystem.

</details>

<details>
<summary>81. Was ist deklaratives UI?</summary>

#### Swift

Deklaratives UI bedeutet, dass du beschreibst, wie das UI für einen bestimmten
Zustand aussehen soll, anstatt Schritt-für-Schritt-Anweisungen zum Aktualisieren zu schreiben.

In SwiftUI deklarierst du die Oberfläche auf Basis von Daten, und das
Framework aktualisiert den Bildschirm, wenn sich der Zustand ändert.

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

Das unterscheidet sich von imperativem UI, bei dem du Views manuell erstellst
und direkt veränderst.

</details>

<details>
<summary>82. Was ist `@State`?</summary>

#### Swift

`@State` ist ein Property Wrapper, der in SwiftUI verwendet wird, um lokalen
veränderbaren Zustand innerhalb einer View zu speichern.

Wenn sich ein `@State`-Wert ändert, rendert SwiftUI die View neu.

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

Verwende `@State` für einfachen Zustand, der der View selbst gehört.

</details>

<details>
<summary>83. Was ist `@StateObject` vs `@ObservedObject`?</summary>

#### Swift

Beide werden mit beobachtbaren Reference Types verwendet, unterscheiden sich
aber in der Besitzverantwortung.

| Wrapper | Ownership |
| --- | --- |
| `@StateObject` | Die View erstellt und besitzt das Objekt |
| `@ObservedObject` | Das Objekt wird woanders erstellt und an die View übergeben |

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

Verwende `@StateObject`, wenn die View das Objekt am Leben halten soll.
Verwende `@ObservedObject`, wenn die View nur ein externes Objekt beobachtet.

</details>

<details>
<summary>84. Was ist `@EnvironmentObject`?</summary>

#### Swift

`@EnvironmentObject` wird verwendet, um ein beobachtbares Objekt durch die
SwiftUI-View-Hierarchie zu teilen, ohne es manuell durch jede View zu übergeben.

```swift
class AppState: ObservableObject {
    @Published var isLoggedIn = false
}

struct ContentView: View {
    @EnvironmentObject var appState: AppState
}
```

Es ist nützlich für gemeinsam genutzten app-weiten Zustand wie:

- Benutzersitzung
- Theme
- Einstellungen

Das Objekt muss in die Environment injiziert werden, bevor die View es verwendet.

</details>

<details>
<summary>85. Was ist `@Published`?</summary>

#### Swift

`@Published` ist ein Property Wrapper, der innerhalb eines `ObservableObject` verwendet wird.

Wenn sich die Property ändert, benachrichtigt sie SwiftUI oder andere
Abonnenten darüber, dass sich das Objekt geändert hat.

```swift
class UserViewModel: ObservableObject {
    @Published var name = "Alice"
}
```

`@Published` wird häufig für View-Model-Zustand verwendet, der das UI aktualisieren soll.

</details>

<details>
<summary>86. Wie funktioniert State Management in SwiftUI?</summary>

#### Swift

State Management in SwiftUI basiert darauf, dass Daten das UI steuern.

Wenn sich der Zustand ändert, berechnet SwiftUI die betroffenen Views neu.

Häufige Werkzeuge:

- `@State` für lokalen View-Zustand
- `@StateObject` für besessene beobachtbare Objekte
- `@ObservedObject` für externe beobachtbare Objekte
- `@EnvironmentObject` für gemeinsam genutzte app-weite Objekte
- `@Binding` zum Weitergeben veränderbaren Zustands zwischen Views

Die Kernidee ist einfach:

- Zustand ändert sich
- SwiftUI aktualisiert die View-Hierarchie

</details>

<details>
<summary>87. Was ist ein `ViewModifier`?</summary>

#### Swift

Ein `ViewModifier` ist eine wiederverwendbare Möglichkeit, SwiftUI-Views Stil
oder Verhalten hinzuzufügen.

```swift
struct TitleStyle: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.title)
            .foregroundColor(.blue)
    }
}
```

Verwendung:

```swift
Text("Hello").modifier(TitleStyle())
```

View Modifiers helfen dabei, dieselbe View-Styling-Logik nicht zu wiederholen.

</details>

<details>
<summary>88. Was ist die SwiftUI Environment?</summary>

#### Swift

Die SwiftUI Environment ist ein System, um Werte implizit durch die
View-Hierarchie nach unten weiterzugeben.

Sie liefert gemeinsamen Kontext wie:

- Color Scheme
- Locale
- Size Category
- Benutzerdefinierte Environment-Werte

Environment-Werte liest du mit `@Environment`.

```swift
struct ContentView: View {
    @Environment(\.colorScheme) var colorScheme
}
```

Die Environment hilft dabei, gemeinsame Konfiguration nicht manuell durch viele View-Ebenen weiterzureichen.

</details>

<details>
<summary>89. Was ist `GeometryReader`?</summary>

#### Swift

`GeometryReader` ist ein SwiftUI-Container, der Zugriff auf Layout-Informationen
über den verfügbaren Platz und die Geometrie einer View gibt.

```swift
GeometryReader { geometry in
    Text("Width: \(geometry.size.width)")
}
```

Er ist nützlich, wenn du Folgendes brauchst:

- Dynamisches Layout basierend auf verfügbarer Größe
- Positionsberechnungen
- Responsives UI-Verhalten

Er sollte vorsichtig verwendet werden, weil übermäßige Nutzung den Layout-Code schwerer nachvollziehbar machen kann.

</details>

<details>
<summary>90. Wie funktioniert Navigation in SwiftUI?</summary>

#### Swift

Navigation in SwiftUI wird typischerweise mit `NavigationStack` aufgebaut.

Du navigierst, indem du Ziele auf einen Stack pushst.

```swift
NavigationStack {
    NavigationLink("Open Details") {
        DetailView()
    }
}
```

Du kannst auch wertbasierte Navigation mit `navigationDestination` verwenden.

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

SwiftUI-Navigation ist zustandsgetrieben und deklarativer als UIKit-Navigation-Controller.

</details>

<details>
<summary>91. Was ist der Lifecycle einer SwiftUI-View?</summary>

#### Swift

SwiftUI-Views sind Value Types, daher unterscheidet sich ihr Lifecycle von dem
von UIKit-View-Controllern.

Eine SwiftUI-View wird häufig erstellt und bei Zustandsänderungen neu erstellt.
Wichtig ist nicht die Lebensdauer der Struct selbst, sondern die Lebensdauer des
damit verbundenen Zustands.

Häufige Lifecycle-Hooks sind:

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

In SwiftUI sind Zustand und Datenfluss wichtiger als die Lebensdauer des Objekts.

</details>

<details>
<summary>92. Warum sind SwiftUI-Views Structs?</summary>

#### Swift

SwiftUI-Views sind Structs, weil Value Types gut mit deklarativem UI funktionieren.

Vorteile:

- Leichtgewichtig
- Einfach neu zu erstellen
- Sichererer Datenfluss
- Bessere Performance-Möglichkeiten für SwiftUI

Da sie Value Types sind, kann SwiftUI View-Werte häufig neu aufbauen und bei
Zustandsänderungen effizient vergleichen.

Die tatsächlich persistenten Teile des UI werden vom Framework verwaltet, nicht von der View-Struct selbst.

</details>

<details>
<summary>93. Was ist der Unterschied zwischen UIKit und SwiftUI?</summary>

#### Swift

UIKit und SwiftUI sind beide UI-Frameworks von Apple, aber sie verwenden
unterschiedliche Ansätze.

| Merkmal | UIKit | SwiftUI |
| --- | --- | --- |
| Stil | Imperativ | Deklarativ |
| Hauptbausteine | `UIView`, `UIViewController` | `View` |
| Zustandsaktualisierung | Manuell | Zustandsgetrieben |
| Typische Nutzung | Reife UI-Kontrolle auf niedriger Ebene | Moderne deklarative UI-Entwicklung |

UIKit gibt dir mehr direkte Kontrolle.
SwiftUI bietet dir einen moderneren und kompakteren Weg, UI zu bauen.

</details>

<details>
<summary>94. Was ist Auto Layout?</summary>

#### Swift

Auto Layout ist Apples System zur Positionierung und Größenbestimmung von
UI-Elementen mithilfe von Constraints.

Anstatt Frames für jede Bildschirmgröße manuell zu setzen, definierst du Regeln
dafür, wie Views zueinander stehen.

Beispiele:

- Ein Label ist 16 Punkte vom linken Rand entfernt
- Ein Button ist horizontal zentriert
- Ein Bild behält gleiche Breite und Höhe

Auto Layout hilft beim Erstellen adaptiver Oberflächen für verschiedene Geräte und Bildschirmgrößen.

</details>

<details>
<summary>95. Was ist Intrinsic Content Size?</summary>

#### Swift

Intrinsic Content Size ist die natürliche Größe, die eine View basierend auf
ihrem Inhalt bevorzugt.

Zum Beispiel:

- Ein Label richtet seine Größe nach seinem Text aus
- Eine Image View richtet ihre Größe nach dem Bild aus

Das hilft Auto Layout zu wissen, wie groß eine View sein sollte, auch ohne
explizite Breiten- und Höhen-Constraints.

Views wie `UILabel` und `UIButton` haben oft eine Intrinsic Content Size.

</details>

<details>
<summary>96. Was sind Constraints und Anchors?</summary>

#### Swift

Constraints sind Layout-Regeln, die von Auto Layout verwendet werden.
Anchors sind eine codefreundliche Möglichkeit, diese Constraints zu erstellen.

Häufige Anchors:

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

Anchors machen Auto-Layout-Code sicherer und leichter lesbar als ältere Constraint-APIs.

</details>

<details>
<summary>97. Was sind Reusable Cells?</summary>

#### Swift

Reusable Cells sind Table-View- oder Collection-View-Zellen, die
wiederverwendet werden, anstatt für jedes Element neu erstellt zu werden.

Das verbessert:

- Performance
- Speicherverbrauch
- Scroll-Effizienz

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
```

Reuse funktioniert, indem Zellen außerhalb des Bildschirms für neuen Inhalt recycelt werden.

</details>

<details>
<summary>98. Was ist der Unterschied zwischen UITableView und UICollectionView?</summary>

#### Swift

Beide zeigen Listen von Daten an, sind aber für unterschiedliche Layout-Anforderungen konzipiert.

| Merkmal | `UITableView` | `UICollectionView` |
| --- | --- | --- |
| Layout-Stil | Meist vertikale Liste | Flexible Layouts |
| Komplexität | Einfacher | Anpassbarer |
| Typische Nutzung | Einfache Listen, Formulare, Einstellungen | Raster, benutzerdefinierte Layouts, komplexe Listen |

Verwende `UITableView` für einfaches listenbasiertes UI.
Verwende `UICollectionView`, wenn du flexiblere oder benutzerdefinierte Layouts brauchst.

</details>

<details>
<summary>99. Was ist `@IBOutlet` vs `@IBAction`?</summary>

#### Swift

Beide werden mit Interface Builder in UIKit-Storyboards oder XIB-Dateien verwendet.

- `@IBOutlet` verbindet ein UI-Element mit Code
- `@IBAction` verbindet ein UI-Ereignis mit Code

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

`@IBOutlet` ist für Referenzen auf UI-Elemente.
`@IBAction` ist für die Behandlung von Benutzeraktionen.

</details>

<details>
<summary>100. Was ist der Lifecycle von `UIViewController`?</summary>

#### Swift

Der `UIViewController`-Lifecycle ist die Abfolge von Methoden, die aufgerufen
werden, wenn ein View Controller erstellt, angezeigt, gelayoutet und entfernt wird.

Häufige Lifecycle-Methoden:

1. `viewDidLoad`
2. `viewWillAppear`
3. `viewDidAppear`
4. `viewWillDisappear`
5. `viewDidDisappear`

#### Beispielrollen

- `viewDidLoad`: initiales Setup
- `viewWillAppear`: UI aktualisieren, bevor es sichtbar wird
- `viewDidAppear`: Animationen oder Tracking starten
- `viewWillDisappear`: Auf das Verlassen des Screens vorbereiten
- `viewDidDisappear`: Aufräumarbeiten

Das Verständnis dieses Lifecycles ist wesentlich für die UIKit-App-Entwicklung.

</details>

<details>
<summary>101. Was ist MVC?</summary>

#### Swift

MVC steht für Model-View-Controller.

Es ist ein Design Pattern, das eine App in drei Teile trennt:

- Model: Daten und Geschäftslogik
- View: UI
- Controller: übernimmt die Interaktion zwischen Model und View

In iOS übernimmt `UIViewController` oft die Rolle des Controllers.

MVC ist einfach und verbreitet, kann in UIKit-Apps aber leicht zu einem
"Massive View Controller" führen, wenn zu viel Logik im Controller landet.

</details>

<details>
<summary>102. Was ist MVVM?</summary>

#### Swift

MVVM steht für Model-View-ViewModel.

Es trennt Verantwortlichkeiten wie folgt:

- Model: Daten und Geschäftsregeln
- View: UI
- ViewModel: Präsentationslogik und Zustand für die View

Das ViewModel bereitet Daten für die Darstellung auf und reduziert Logik in der
View oder im View Controller.

MVVM ist in SwiftUI beliebt und wird auch häufig in UIKit-Apps verwendet.

</details>

<details>
<summary>103. Was ist Dependency Injection?</summary>

#### Swift

Dependency Injection bedeutet, einem Objekt die benötigten Abhängigkeiten von
außen zu geben, anstatt sie im Objekt selbst zu erstellen.

Zum Beispiel wird ein Netzwerkservice in ein ViewModel hineingegeben, statt
dass das ViewModel ihn selbst erstellt.

Vorteile:

- Bessere Testbarkeit
- Geringere Kopplung
- Einfacherer Austausch von Implementierungen

</details>

<details>
<summary>104. Wie implementierst du DI in Swift?</summary>

#### Swift

Der häufigste Weg ist Constructor Injection.

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

Weitere häufige Ansätze:

- Property Injection
- Method Injection
- Dependency Container

Constructor Injection wird normalerweise bevorzugt, weil sie Abhängigkeiten explizit macht.

</details>

<details>
<summary>105. Was ist das Delegation Pattern?</summary>

#### Swift

Delegation ist ein Pattern, bei dem ein Objekt Verantwortung für bestimmte
Arbeit oder Ereignisse an ein anderes Objekt übergibt.

Es wird häufig mit Protocols implementiert.

```swift
protocol ButtonHandler: AnyObject {
    func didTapButton()
}
```

Delegation wird in UIKit häufig verwendet, zum Beispiel mit:

- `UITableViewDelegate`
- `UITextFieldDelegate`

Es hilft dabei, Verantwortlichkeiten getrennt und Kommunikation flexibel zu halten.

</details>

<details>
<summary>106. Wann sollte man einen Singleton verwenden?</summary>

#### Swift

Ein Singleton sollte verwendet werden, wenn es in der App genau eine
gemeinsam genutzte Instanz geben muss.

Typische Beispiele:

- App-weite Konfiguration
- Logging-Service
- Cache-Manager

```swift
final class Logger {
    static let shared = Logger()

    private init() {}
}
```

Verwende Singletons mit Vorsicht.
Ihr übermäßiger Einsatz kann versteckte Abhängigkeiten erzeugen und Tests erschweren.

</details>

<details>
<summary>107. Was ist KVO?</summary>

#### Swift

KVO steht für Key-Value Observing.

Es ist ein Mechanismus zur Beobachtung von Änderungen an Properties bestimmter
Objekte, insbesondere solcher, die mit Objective-C kompatibel sind.

Es ist überwiegend mit Cocoa und dem Objective-C-Runtime-Verhalten verbunden.

KVO wird in modernem Swift-Code seltener verwendet als:

- Combine
- `@Published`
- SwiftUI-State-Tools

Es taucht aber weiterhin in einigen UIKit- und Foundation-APIs auf.

</details>

<details>
<summary>108. Was ist `NotificationCenter`?</summary>

#### Swift

`NotificationCenter` ist ein System zum Senden von Nachrichten an mehrere
Beobachter.

Ein Objekt veröffentlicht eine Notification, und andere Objekte können darauf hören.

```swift
NotificationCenter.default.post(name: .didLogout, object: nil)
```

Es ist nützlich für lose Kommunikation zwischen Teilen der App, besonders wenn
direkte Referenzen nicht ideal sind.

Verwende es vorsichtig, weil übermäßiger Einsatz den Datenfluss schwerer nachvollziehbar machen kann.

</details>

<details>
<summary>109. Wie macht man einen Netzwerk-Request in Swift?</summary>

#### Swift

Der Standardweg ist die Verwendung von `URLSession`.

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

In modernem Swift kannst du mit `URLSession` auch `async/await` verwenden.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>110. Was ist `Codable`?</summary>

#### Swift

`Codable` ist ein Type Alias für:

- `Encodable`
- `Decodable`

Es erlaubt Swift-Typen, einfach in Formate wie JSON konvertiert zu werden und daraus zurück.

```swift
struct User: Codable {
    let id: Int
    let name: String
}
```

Häufige Anwendungsfälle:

- Parsen von API-Antworten
- Speichern lokaler Daten
- Codieren von Request-Bodies

`Codable` reduziert Boilerplate bei der Serialisierung erheblich.

</details>

<details>
<summary>111. Was sind Decoding Strategies?</summary>

#### Swift

Decoding Strategies sind Optionen, die von `JSONDecoder` verwendet werden, um zu steuern, wie eingehende Daten dekodiert werden.

Häufige Strategien sind:

- `dateDecodingStrategy`
- `keyDecodingStrategy`
- `dataDecodingStrategy`

```swift
let decoder = JSONDecoder()
decoder.keyDecodingStrategy = .convertFromSnakeCase
decoder.dateDecodingStrategy = .iso8601
```

Sie sind nützlich, wenn das API-Format nicht direkt zum Format deines Swift-Modells passt.

</details>

<details>
<summary>112. Was ist `URLSession`?</summary>

#### Swift

`URLSession` ist Apples wichtigste API für Netzwerk-Requests.

Sie wird verwendet für:

- Das Herunterladen von Daten
- Das Hochladen von Daten
- Das Abrufen von Dateien
- Das Verwalten von Netzwerk-Tasks

Sie unterstützt sowohl den Completion-Handler-Stil als auch `async/await`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>113. Was ist eine Caching Strategy?</summary>

#### Swift

Eine Caching Strategy ist der Plan dafür, welche Daten gecacht werden, wo sie
gecacht werden und wann sie aktualisiert oder invalidiert werden.

Häufige Cache-Ebenen in iOS-Apps:

- In-Memory-Cache
- Disk-Cache
- HTTP-Cache

Wichtige Entscheidungen umfassen normalerweise:

- Cache-Lebensdauer
- Invalidation Rules
- Memory-vs-Disk-Trade-offs
- Frische vs Geschwindigkeit

Eine gute Caching Strategy verbessert die Performance, reduziert
Netzwerknutzung und lässt die App schneller wirken.

</details>

<details>
<summary>114. Wie debuggt man Crashes?</summary>

#### Swift

Häufige Wege zum Debuggen von Crashes sind:

1. Das Lesen des Crash Logs
2. Das Prüfen des Stack Trace
3. Das lokale Reproduzieren des Problems
4. Die Verwendung des Xcode-Debuggers und von Breakpoints
5. Die Verwendung von Crash-Reporting-Tools wie Firebase Crashlytics

Wichtige Dinge, auf die man achten sollte:

- Der abgestürzte Thread
- Der Exception-Typ
- Zuletzt aufgerufene Methoden
- Geräte- und OS-Version

Das Ziel ist es, den Crash zu reproduzieren, die Root Cause zu identifizieren und den Fix zu bestätigen.

</details>

<details>
<summary>115. Wie erkennt man Memory Leaks?</summary>

#### Swift

Häufige Wege, Memory Leaks zu erkennen, sind:

- Xcode Memory Graph Debugger
- Instruments Leaks Tool
- Instruments Allocations
- Das Prüfen von `deinit`

```swift
deinit {
    print("Object deallocated")
}
```

Wenn ein Objekt verschwinden sollte, aber im Speicher bleibt, kann ein retain
cycle oder eine andere unerwartete starke Referenz vorliegen.

</details>

<details>
<summary>116. Wie verbessert man die Performance in iOS-Apps?</summary>

#### Swift

Häufige Wege zur Performance-Verbesserung sind:

- Arbeit auf dem Main Thread reduzieren
- Rendering und Scrolling optimieren
- Unnötige Allokationen vermeiden
- Teure Ergebnisse cachen
- Hintergrundarbeit für schwere Aufgaben verwenden
- Mit Instruments profilieren

Man sollte zuerst messen und dann den echten Bottleneck optimieren.

Typische Werkzeuge:

- Time Profiler
- Allocations
- Memory Graph
- Network Instruments

</details>

<details>
<summary>117. Wie optimiert man den Batterieverbrauch?</summary>

#### Swift

Um den Batterieverbrauch zu optimieren, reduziere unnötige Arbeit und vermeide,
Hardware oder Hintergrundaufgaben länger aktiv zu halten als nötig.

Häufige Praktiken:

- Hintergrundaktivität minimieren
- Übermäßige Standort-Updates vermeiden
- Netzwerk-Requests bündeln
- Häufige Timer und Polling reduzieren
- Unnötige Animationen und Redraws vermeiden

Die Hauptregel ist einfach:

- Weniger Arbeit machen
- Es seltener tun

</details>

<details>
<summary>118. Was ist Keychain und wann sollte man sie verwenden?</summary>

#### Swift

Keychain ist Apples sicheres Speichersystem für kleine sensible Daten.

Verwende Keychain für Dinge wie:

- Tokens
- Passwörter
- Zugangsdaten
- Sensible Geheimnisse

Verwende sie nicht als allgemeine Datenbank.

Keychain ist für vertrauliche Daten sicherer als `UserDefaults`.

</details>

<details>
<summary>119. Was ist App Transport Security?</summary>

#### Swift

App Transport Security (ATS) ist eine iOS-Sicherheitsfunktion, die standardmäßig sichere Netzwerkverbindungen fördert.

Sie verlangt im Allgemeinen:

- HTTPS
- Starke TLS-Einstellungen

Wenn eine App unsicheres HTTP oder schwächere Sicherheitseinstellungen
benötigt, müssen explizite Ausnahmen in der App-Konfiguration hinzugefügt werden.

ATS hilft, Netzwerkverkehr vor Abfangen und unsicherem Transport zu schützen.

</details>

<details>
<summary>120. Wie speichert man Daten sicher?</summary>

#### Swift

Das hängt von der Sensibilität der Daten ab.

Typische Regeln:

- Verwende Keychain für Passwörter, Tokens und Geheimnisse
- Verwende File Protection für sensible Dateien
- Speichere Geheimnisse nicht im Klartext
- Speichere vertrauliche Daten nicht in `UserDefaults`
- Verschlüssele Daten bei Bedarf

Außerdem wichtig:

- Begrenze, was du speicherst
- Speichere es nur so lange wie nötig
- Schütze es sowohl im Ruhezustand als auch während der Übertragung

</details>

<details>
<summary>121. Was ist `XCTest`?</summary>

#### Swift

`XCTest` ist Apples Test-Framework zum Schreiben und Ausführen von Tests in Xcode.

Es wird verwendet für:

- Unit Tests
- UI Tests
- Performance Tests

```swift
func testAddition() {
    XCTAssertEqual(2 + 2, 4)
}
```

Es ist das Standard-Testwerkzeug für die Entwicklung auf Apple-Plattformen.

</details>

<details>
<summary>122. Was ist Unit Testing vs UI Testing?</summary>

#### Swift

Unit Testing prüft kleine Teile der Logik in Isolation.
UI Testing prüft die App über die Benutzeroberfläche.

| Typ | Fokus |
| --- | --- |
| Unit Test | Geschäftslogik, Funktionen, Klassen |
| UI Test | Echte User Flows und Interaktionen auf dem Screen |

Unit Tests sind normalerweise:

- Schneller
- Stärker isoliert
- Leichter zu debuggen

UI Tests sind nützlich, um End-to-End-Verhalten zu validieren.

</details>

<details>
<summary>123. Was ist Mocking?</summary>

#### Swift

Mocking bedeutet, eine echte Abhängigkeit durch eine gefälschte Testversion zu ersetzen.

Das hilft, eine Einheit in Isolation zu testen.

Zum Beispiel gibt ein Mock-Netzwerkservice statt eines echten API-Aufrufs
vordefinierte Daten zurück.

Mocking ist nützlich für:

- Schnellere Tests
- Vorhersagbare Ergebnisse
- Das Testen von Fehlerszenarien

</details>

<details>
<summary>124. Wie bleibst du bei Swift auf dem Laufenden?</summary>

#### Swift

Eine starke Antwort kombiniert offizielle Quellen mit praktischem Lernen.

Häufige Wege:

- Swift-Evolution-Vorschläge lesen
- WWDC-Sessions verfolgen
- Apple-Dokumentation lesen
- Neue Sprachfeatures in Side Projects ausprobieren
- Respektierten Swift- und iOS-Ingenieuren folgen

Wichtig ist nicht nur, Updates zu lesen, sondern sie auch in echtem Code anzuwenden.

</details>

<details>
<summary>125. Erzähl mir von einer komplexen Funktion, die du gebaut hast.</summary>

#### Swift

Eine gute Interview-Antwort sollte so aufgebaut sein:

1. Die Funktion kurz erklären
2. Die wichtigsten technischen Herausforderungen beschreiben
3. Die Entscheidungen und Trade-offs erklären
4. Das Ergebnis zeigen

#### Beispielstruktur für eine Antwort

"Ich habe eine Offline-First-Synchronisationsfunktion für eine mobile App
gebaut. Die größten Herausforderungen waren Konfliktauflösung, lokale
Persistenz, Retry-Logik und die Reaktionsfähigkeit des UI während der
Synchronisation. Ich habe das Problem in Networking-, lokale Datenspeicher- und
Sync-Orchestrierungs-Schichten aufgeteilt. Außerdem habe ich Retry-Policies,
Background-Sync-Handling und Logging hinzugefügt. Das Ergebnis war eine höhere
gefühlte Performance, bessere Zuverlässigkeit in instabilen Netzwerken und
weniger Support-Fälle."

Die besten Antworten sind konkret und messbar.

</details>

<details>
<summary>126. Wie gehst du an Code Review heran?</summary>

#### Swift

Ein starker Code-Review-Ansatz konzentriert sich zuerst auf Korrektheit und
dann auf Wartbarkeit.

Typische Prioritäten:

- Bugs und Edge Cases
- Passung zu Architektur und Design
- Lesbarkeit
- Benennung
- Testabdeckung
- Performance und Sicherheit, wenn relevant

Ein gutes Review sollte klar, respektvoll und konkret sein.

Das Ziel ist nicht nur, Probleme zu finden, sondern auch die Codequalität zu
verbessern und Wissen zu teilen.

</details>

<details>
<summary>127. Wie entwirfst du eine skalierbare iOS-Architektur?</summary>

#### Swift

Bei skalierbarer Architektur geht es darum, Features mit wachsender App
einfach erweiterbar, testbar und wartbar zu halten.

Wichtige Prinzipien:

- Klare Trennung der Verantwortlichkeiten
- Modulares Design
- Dependency Injection
- Testbare Geschäftslogik
- Vorhersagbarer Datenfluss

Eine skalierbare Architektur sollte Teams helfen, Features hinzuzufügen, ohne
bestehenden Code ständig neu schreiben zu müssen.

</details>

<details>
<summary>128. Welche Trade-offs berücksichtigst du bei der Wahl einer Architektur?</summary>

#### Swift

Architektur ist immer eine Frage von Trade-offs.

Häufige Faktoren:

- Teamgröße und Erfahrung
- App-Komplexität
- Entwicklungsgeschwindigkeit
- Testbarkeit
- Wartbarkeit
- Flexibilität für zukünftiges Wachstum

Eine einfache App braucht möglicherweise keine schwere Architektur.
Eine große App profitiert meist von stärkerer Trennung, klareren Grenzen und
besserem Dependency Management.

Die beste Wahl ist die einfachste Architektur, die trotzdem gut zum Problem passt.

</details>
