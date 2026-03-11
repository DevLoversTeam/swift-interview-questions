**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Swift <img src="./assets/swift.svg" width="40" height="40" />
</h1>

<h2>Najpopularniejsze pytania i odpowiedzi na rozmowie kwalifikacyjnej ze Swift</h2>

<details>
<summary>1. Do czego Swift jest przede wszystkim używany we współczesnym programowaniu?</summary>

#### Swift

Swift jest używany przede wszystkim do tworzenia aplikacji na platformy Apple:

- iOS
- macOS
- watchOS
- tvOS
- visionOS

Najczęściej wykorzystuje się go do:

- Tworzenia aplikacji mobilnych
- Natywnego programowania na platformy Apple
- Programowania backendu z użyciem frameworków takich jak Vapor
- Narzędzi wiersza poleceń i skryptów

Swift jest ceniony za bezpieczeństwo, wydajność i nowoczesną składnię.

</details>

<details>
<summary>2. Jaka jest różnica między `let` a `var`?</summary>

#### Swift

`let` tworzy stałą, a `var` tworzy zmienną.

- Używaj `let`, gdy wartość nie powinna się zmieniać.
- Używaj `var`, gdy wartość może się później zmienić.

```swift
let name = "Alice"
var age = 25

age = 26 // Dozwolone
// name = "Bob" // Błąd
```

Używanie `let` domyślnie sprawia, że kod jest bezpieczniejszy i łatwiejszy do
zrozumienia.

</details>

<details>
<summary>3. Wyjaśnij type inference w Swift.</summary>

#### Swift

Type inference oznacza, że Swift potrafi automatycznie określić typ wartości na
podstawie przypisanych danych, więc nie zawsze trzeba jawnie podawać typ.

```swift
let title = "Swift"      // String
let year = 2025          // Int
let isActive = true      // Bool
```

Typ nadal można określić ręcznie, jeśli chcesz wyraźniej pokazać intencję:

```swift
let score: Double = 99
```

Type inference skraca kod, zachowując bezpieczeństwo typów.

</details>

<details>
<summary>4. Czym są optionals i dlaczego są ważne?</summary>

#### Swift

Optional to typ, który może przechowywać:

- wartość
- `nil`

Optionals są ważne, ponieważ wprost pokazują brak wartości i pomagają zapobiegać
awariom w czasie działania wynikającym z użycia brakujących danych.

```swift
var nickname: String? = "Sam"
nickname = nil
```

Bez optionali Swift nie mógłby bezpiecznie reprezentować wartości, które mogą
być nieobecne, takich jak:

- Dane wejściowe od użytkownika
- Pola odpowiedzi z sieci
- Wartości z bazy danych
- URL-e, których inicjalizacja może się nie udać

</details>

<details>
<summary>5. Jaka jest różnica między optional binding a force unwrapping?</summary>

#### Swift

Optional binding bezpiecznie wyciąga wartość z optionala.
Force unwrapping wyciąga wartość bezpośrednio i powoduje błąd, jeśli optional ma
wartość `nil`.

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

W większości przypadków używaj optional binding.
Force unwrapping stosuj tylko wtedy, gdy masz całkowitą pewność, że wartość nie
jest `nil`.

</details>

<details>
<summary>6. Czym jest optional chaining i kiedy go używać?</summary>

#### Swift

Optional chaining to sposób bezpiecznego dostępu do właściwości, metod lub
subscriptów na wartości optional.

Jeśli optional ma wartość `nil`, całe wyrażenie zwróci `nil` zamiast powodować
błąd.

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

Używaj optional chaining podczas pracy ze zagnieżdżonymi optionalami, szczególnie w:

- Obiektach modelu
- Odpowiedziach API
- Referencjach do UI, które mogą nie istnieć

</details>

<details>
<summary>7. Czym jest operator nil coalescing?</summary>

#### Swift

Operator nil coalescing to `??`.
Zapewnia wartość domyślną, gdy optional ma wartość `nil`.

```swift
let username: String? = nil
let displayName = username ?? "Guest"
```

W tym przykładzie `displayName` przyjmie wartość `"Guest"`.

Używaj `??`, gdy chcesz ustawić wartość zastępczą dla optionala.

</details>

<details>
<summary>8. Czym są tuples i kiedy warto ich używać?</summary>

#### Swift

Tuple to grupa wartości połączonych w jedną złożoną wartość.

```swift
let person = ("Alice", 28)
```

Wartości w tuple można również nazwać:

```swift
let httpResponse = (statusCode: 200, message: "OK")
print(httpResponse.statusCode)
```

Tuple warto używać do krótkotrwałych, powiązanych ze sobą wartości, na przykład:

- Zwracania wielu wartości z funkcji
- Reprezentowania niewielkiego zestawu powiązanych danych
- Tymczasowych danych lokalnych

W przypadku bardziej złożonych lub wielokrotnie używanych danych lepiej
stosować `struct` albo `class`.

</details>

<details>
<summary>9. Jakie są główne typy kolekcji w Swift?</summary>

#### Swift

Główne typy kolekcji w Swift to:

1. `Array`
2. `Set`
3. `Dictionary`

#### Array

Przechowuje uporządkowaną listę wartości.

```swift
let numbers = [1, 2, 3]
```

#### Set

Przechowuje unikalne, nieuporządkowane wartości.

```swift
let uniqueNumbers: Set = [1, 2, 3]
```

#### Dictionary

Przechowuje pary klucz-wartość.

```swift
let userAges = ["Alice": 25, "Bob": 30]
```

Te kolekcje są stale używane w programowaniu w Swift.

</details>

<details>
<summary>10. Jaka jest różnica między Array, Set i Dictionary?</summary>

#### Swift

Różnica polega na tym, jak przechowują dane i jak uzyskuje się do nich dostęp.

| Typ | Co przechowuje | Kolejność | Unikalność | Dostęp |
| --- | --- | --- | --- | --- |
| `Array` | Lista wartości | Uporządkowana | Duplikaty dozwolone | Po indeksie |
| `Set` | Unikalne wartości | Nieuporządkowany | Duplikaty niedozwolone | Wyszukiwanie po wartości |
| `Dictionary` | Pary klucz-wartość | Nieuporządkowany | Klucze muszą być unikalne | Po kluczu |

#### Przykład

```swift
let array = ["a", "b", "a"]
let set: Set = ["a", "b", "a"]
let dictionary = ["name": "Alice", "city": "Paris"]
```

- `Array` zachowuje kolejność i może zawierać duplikaty.
- `Set` usuwa duplikaty.
- `Dictionary` mapuje klucze na wartości.

</details>

<details>
<summary>11. Czym są value types i reference types?</summary>

#### Swift

Value types są kopiowane podczas przypisania lub przekazywania dalej.
Reference types współdzielą tę samą instancję.

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

Domyślnie warto używać value types, chyba że potrzebny jest współdzielony
mutowalny stan.

</details>

<details>
<summary>12. Jaka jest różnica między struct a class?</summary>

#### Swift

Najważniejsza różnica polega na tym, że `struct` jest value type, a `class` jest
reference type.

| Cecha | `struct` | `class` |
| --- | --- | --- |
| Typ | Value type | Reference type |
| Zachowanie przy kopiowaniu | Kopiowany przy przypisaniu | Współdzielony przez referencję |
| Dziedziczenie | Nieobsługiwane | Obsługiwane |
| Deinitializer | Nieobsługiwany | Obsługiwany |
| Sprawdzanie tożsamości | Nie | Tak, przez `===` |

W większości przypadków używaj `struct`.
`class` stosuj wtedy, gdy potrzebujesz:

- Współdzielonego mutowalnego stanu
- Dziedziczenia
- Semantyki tożsamości

</details>

<details>
<summary>13. Czym jest copy-on-write?</summary>

#### Swift

Copy-on-write to optymalizacja, w której wartość nie jest kopiowana od razu.
Swift tworzy rzeczywistą kopię dopiero wtedy, gdy jedna z wartości zostanie
zmodyfikowana.

Jest to powszechnie używane przez standardowe kolekcje, takie jak:

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

Daje to bezpieczeństwo value types przy dobrej wydajności.

</details>

<details>
<summary>14. Czym jest immutability i dlaczego jest ważna?</summary>

#### Swift

Immutability oznacza, że wartości nie można zmienić po jej utworzeniu.

W Swift wartości zadeklarowane przez `let` są niemutowalne.

```swift
let name = "Alice"
// name = "Bob" // Błąd
```

Immutability jest ważna, ponieważ:

- Zwiększa bezpieczeństwo kodu
- Zmniejsza liczbę błędów
- Ułatwia śledzenie stanu
- Pomaga lepiej rozumieć współbieżność

Domyślnie używaj wartości niemutowalnych, a mutowalne twórz tylko wtedy, gdy to
naprawdę potrzebne.

</details>

<details>
<summary>15. Czym są computed properties?</summary>

#### Swift

Computed property nie przechowuje wartości bezpośrednio.
Zamiast tego oblicza wartość za każdym razem, gdy następuje do niej dostęp.

```swift
struct Rectangle {
    var width: Double
    var height: Double

    var area: Double {
        width * height
    }
}
```

Computed properties mogą także mieć `get` i `set`:

```swift
struct Square {
    var side: Double

    var area: Double {
        get { side * side }
        set { side = sqrt(newValue) }
    }
}
```

Używaj computed properties, gdy wartość zależy od innych wartości.

</details>

<details>
<summary>16. Czym są property observers (`willSet` / `didSet`)?</summary>

#### Swift

Property observers pozwalają reagować na zmianę wartości stored property.

- `willSet` uruchamia się przed zapisaniem nowej wartości
- `didSet` uruchamia się po zapisaniu nowej wartości

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

Używaj ich, gdy potrzebujesz:

- Logować zmiany
- Aktualizować UI
- Uruchamiać side effects po zmianie wartości

</details>

<details>
<summary>17. Czym są lazy properties?</summary>

#### Swift

Lazy property jest inicjalizowana dopiero wtedy, gdy zostanie użyta po raz
pierwszy.

Jest deklarowana słowem kluczowym `lazy` i musi być typu `var`.

```swift
class DataManager {
    lazy var formatter: DateFormatter = {
        let formatter = DateFormatter()
        formatter.dateStyle = .medium
        return formatter
    }()
}
```

Używaj lazy properties, gdy:

- Inicjalizacja jest kosztowna
- Właściwość może nigdy nie zostać użyta
- Właściwość zależy od `self` po inicjalizacji

</details>

<details>
<summary>18. Czym są key paths w Swift?</summary>

#### Swift

Key paths to type-safe referencje do właściwości.
Pozwalają uzyskać dostęp do właściwości pośrednio.

```swift
struct User {
    let name: String
}

let keyPath = \User.name
let user = User(name: "Alice")

print(user[keyPath: keyPath]) // Alice
```

Key paths są przydatne do:

- Sortowania
- Mapowania
- Generic API
- Obserwowania lub uzyskiwania dostępu do zagnieżdżonych właściwości w
  bezpieczny typowo sposób

</details>

<details>
<summary>19. Czym jest type casting (`is`, `as`, `as?`, `as!`)?</summary>

#### Swift

Type casting służy do sprawdzania lub konwertowania typu wartości w czasie
wykonania.

- `is` sprawdza, czy wartość jest określonego typu
- `as` wykonuje upcast do nadtypu
- `as?` bezpiecznie wykonuje downcast i zwraca optional
- `as!` wymusza downcast i powoduje błąd, jeśli się nie powiedzie

```swift
class Animal {}
class Dog: Animal {}

let animal: Animal = Dog()

print(animal is Dog) // true

let dog1 = animal as? Dog // Bezpieczne
let dog2 = animal as! Dog // Niebezpieczne przy złym typie
```

W większości przypadków używaj `as?`.
`as!` stosuj tylko wtedy, gdy błąd jest niemożliwy.

</details>

<details>
<summary>20. Jaka jest różnica między `==` a `===`?</summary>

#### Swift

`==` sprawdza równość wartości.
`===` sprawdza tożsamość referencji.

#### `==`

Służy do porównywania, czy dwie wartości są równe.

```swift
let a = 5
let b = 5

print(a == b) // true
```

#### `===`

Używane jest tylko z klasami, aby sprawdzić, czy dwie referencje wskazują na tę
samą instancję.

```swift
class User {}

let user1 = User()
let user2 = user1
let user3 = User()

print(user1 === user2) // true
print(user1 === user3) // false
```

Czyli:

- `==` oznacza „ta sama wartość”
- `===` oznacza „ten sam obiekt w pamięci”

</details>

<details>
<summary>21. Jak działa `switch` w Swift (pattern matching)?</summary>

#### Swift

`switch` w Swift jest bardzo rozbudowany i wspiera pattern matching.
Może dopasowywać:

- Dokładne wartości
- Wiele wartości
- Zakresy
- Tuple
- Enum cases
- Wartości z warunkami

W przeciwieństwie do niektórych języków `switch` w Swift musi być wyczerpujący.
Oznacza to, że każdy możliwy przypadek musi zostać obsłużony.

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

`switch` w Swift jest często używany, ponieważ jest bezpieczniejszy i bardziej
wyrazisty niż długi łańcuch instrukcji `if`.

</details>

<details>
<summary>22. Czym jest `fallthrough` i kiedy należy go unikać?</summary>

#### Swift

`fallthrough` powoduje przejście wykonania z jednego `case` do kolejnego `case`
w `switch`.

Domyślnie Swift nie przechodzi automatycznie do następnego przypadku.

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

Wynik:

```swift
One
Two
```

W większości przypadków należy unikać `fallthrough`, ponieważ:

- Sprawia, że logika jest mniej czytelna
- Może prowadzić do nieoczekiwanego zachowania
- Zwykle istnieją czystsze alternatywy

Używaj go tylko wtedy, gdy świadomie chcesz wykonać również następny `case`.

</details>

<details>
<summary>23. Czym jest instrukcja `guard` i kiedy jej używać?</summary>

#### Swift

`guard` służy do wczesnego wyjścia.
Sprawdza warunek, a jeśli warunek nie jest spełniony, wykonanie musi opuścić
bieżący zakres.

```swift
func printName(_ name: String?) {
    guard let name = name else {
        print("Name is missing")
        return
    }

    print(name)
}
```

Używaj `guard`, gdy:

- Brakuje wymaganej wartości
- Wstępne warunki nie są spełnione
- Chcesz uniknąć głębokiego zagnieżdżania kodu

Sprawia on, że kod jest bardziej płaski i łatwiejszy do czytania.

</details>

<details>
<summary>24. Jaka jest różnica między `if let` a `guard let`?</summary>

#### Swift

Obie konstrukcje służą do optional binding, ale używa się ich w inny sposób.

| Cecha | `if let` | `guard let` |
| --- | --- | --- |
| Główne zastosowanie | Gałąź warunkowa | Wczesne wyjście |
| Zasięg rozpakowanej wartości | Wewnątrz bloku `if` | Po instrukcji `guard` |
| Czytelność | Dobre dla krótkich sprawdzeń | Lepsze dla wymaganych warunków |

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

Używaj `if let` do pracy z optionalem wewnątrz lokalnej gałęzi.
Używaj `guard let`, gdy wartość jest potrzebna w dalszej części funkcji.

</details>

<details>
<summary>25. Czym jest half-open range?</summary>

#### Swift

Half-open range zawiera dolną granicę, ale nie zawiera górnej granicy.

Używa operatora `..<`

```swift
for i in 0..<5 {
    print(i)
}
```

Wynik:

```swift
0
1
2
3
4
```

Half-open ranges są przydatne do:

- Pętli
- Indeksowania tablic
- Sytuacji, w których końcowa wartość nie powinna być uwzględniona

</details>

<details>
<summary>26. Czym jest `where` clause?</summary>

#### Swift

`where` clause dodaje dodatkowy warunek do pattern, pętli, generic constraint
albo `catch` block.

#### W `switch`

```swift
let point = (2, 2)

switch point {
case let (x, y) where x == y:
    print("x equals y")
default:
    print("No match")
}
```

#### W pętlach

```swift
for number in 1...10 where number.isMultiple(of: 2) {
    print(number)
}
```

Używaj `where`, gdy chcesz precyzyjniejszego dopasowania lub filtrowania.

</details>

<details>
<summary>27. Co robi `defer`?</summary>

#### Swift

`defer` planuje wykonanie kodu tuż przed opuszczeniem bieżącego zakresu.

Uruchomi się niezależnie od sposobu wyjścia z zakresu:

- Zwykły `return`
- Wczesny `return`
- Rzucony błąd

```swift
func performTask() {
    print("Start")

    defer {
        print("Cleanup")
    }

    print("Work")
}
```

Wynik:

```swift
Start
Work
Cleanup
```

`defer` jest przydatny do działań porządkujących, takich jak:

- Zamykanie plików
- Odblokowywanie zasobów
- Resetowanie stanu

</details>

<details>
<summary>28. Czym są `break` i `continue`?</summary>

#### Swift

`break` zatrzymuje bieżącą pętlę albo `switch`.
`continue` pomija bieżącą iterację pętli i przechodzi do następnej.

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

Używaj `break`, aby przerwać przetwarzanie.
Używaj `continue`, aby pominąć jedną iterację.

</details>

<details>
<summary>29. Do czego służy `stride()`?</summary>

#### Swift

`stride()` służy do tworzenia sekwencji poruszających się określonym krokiem.

Jest przydatny wtedy, gdy nie chcesz zwiększać wartości o `1`.

#### Przykład z `through`

```swift
for number in stride(from: 0, through: 10, by: 2) {
    print(number)
}
```

#### Przykład z `to`

```swift
for number in stride(from: 0, to: 10, by: 2) {
    print(number)
}
```

Różnica:

- `through` uwzględnia wartość końcową, jeśli to możliwe
- `to` nie uwzględnia wartości końcowej

</details>

<details>
<summary>30. Czym są raw strings?</summary>

#### Swift

Raw strings pozwalają zapisywać string literals bez traktowania backslashy i
cudzysłowów jak zwykłych znaków escape.

Używają `#` wokół stringa.

```swift
let path = #"C:\Users\Name\Documents"#
let text = #"He said "Hello""#
```

Jeśli chcesz użyć interpolacji wewnątrz raw string, użyj `\#(...)`:

```swift
let name = "Alice"
let message = #"Hello, \#(name)"#
```

Raw strings są przydatne do:

- Wyrażeń regularnych
- Ścieżek do plików
- Fragmentów JSON
- Stringów z wieloma backslashami lub cudzysłowami

</details>

<details>
<summary>31. Czym są closures w Swift?</summary>

#### Swift

Closures to samodzielne bloki kodu, które można przekazywać i wykonywać później.

Są podobne do funkcji, ale można je przechowywać w zmiennych i mogą
przechwytywać wartości z otaczającego zakresu.

```swift
let greet = { (name: String) in
    print("Hello, \(name)")
}

greet("Alice")
```

Closures są powszechnie używane do:

- Callbacków
- Completion handlerów
- Sortowania
- Operacji funkcyjnych, takich jak `map` i `filter`

</details>

<details>
<summary>32. Escaping vs non-escaping closures?</summary>

#### Swift

Non-escaping closure jest wykonywane przed zakończeniem działania funkcji.
Escaping closure może zostać zapisane i wykonane po zakończeniu działania
funkcji.

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

Domyślnie używaj non-escaping closures.
Escaping closures stosuj do pracy asynchronicznej, callbacków lub przechowywanych closures.

</details>

<details>
<summary>33. Co oznacza `@escaping`?</summary>

#### Swift

`@escaping` oznacza, że closure może żyć dłużej niż funkcja, do której zostało
przekazane.

Innymi słowy, wykonanie closure nie musi nastąpić przed zakończeniem działania
funkcji.

```swift
class Downloader {
    var completion: (() -> Void)?

    func fetch(completion: @escaping () -> Void) {
        self.completion = completion
    }
}
```

`@escaping` jest zwykle potrzebne, gdy closure jest:

- Przechowywane we właściwości
- Wykonywane asynchronicznie
- Przekazywane do innej funkcji, która je przechowuje

</details>

<details>
<summary>34. Czym są trailing closures?</summary>

#### Swift

Trailing closure to closure zapisane po nawiasach funkcji.

Taka składnia jest czytelniejsza, gdy ostatni argument jest closure.

```swift
func perform(action: () -> Void) {
    action()
}

perform {
    print("Done")
}
```

Trailing closures często występują w:

- API asynchronicznych
- Callbackach UIKit i SwiftUI
- Operacjach na kolekcjach

</details>

<details>
<summary>35. Czym jest value capturing w closures?</summary>

#### Swift

Closures mogą przechwytywać wartości z otaczającego zakresu i nadal z nich
korzystać, nawet gdy ten zakres normalnie już by nie istniał.

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

Tutaj closure przechwytuje `count` i utrzymuje go przy życiu.

To jest przydatne, ale może też prowadzić do problemów z pamięcią, jeśli obiekty
zostaną przez pomyłkę silnie przechwycone.

</details>

<details>
<summary>36. Jak Swift zarządza pamięcią w closures?</summary>

#### Swift

Swift używa ARC (Automatic Reference Counting).
Closures są reference types, więc mogą silnie przechwytywać obiekty.

Jeśli closure silnie przechwyci `self`, a `self` silnie przechowuje to closure,
może powstać retain cycle.

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

Aby uniknąć memory leaks, używaj capture lists, gdy to potrzebne:

- `[weak self]`, gdy `self` może stać się `nil`
- `[unowned self]`, gdy `self` musi nadal istnieć

</details>

<details>
<summary>37. Czym są higher-order functions (`map`, `filter`, `reduce`)?</summary>

#### Swift

Higher-order functions to funkcje, które przyjmują inne funkcje lub closures
jako argumenty albo je zwracają.

W Swift typowe higher-order functions dla kolekcji to:

- `map`
- `filter`
- `reduce`

#### `map`

Przekształca każdy element.

```swift
let numbers = [1, 2, 3]
let doubled = numbers.map { $0 * 2 }
```

#### `filter`

Zostawia tylko pasujące elementy.

```swift
let evenNumbers = numbers.filter { $0.isMultiple(of: 2) }
```

#### `reduce`

Łączy wszystkie elementy w jeden wynik.

```swift
let sum = numbers.reduce(0) { $0 + $1 }
```

Te funkcje sprawiają, że kod jest krótszy i bardziej wyrazisty.

</details>

<details>
<summary>38. Jaka jest różnica między `map` a `compactMap`?</summary>

#### Swift

`map` przekształca każdy element i zachowuje tę samą liczbę elementów.
`compactMap` przekształca elementy i usuwa wyniki `nil`.

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

Używaj `map`, gdy wszystkie przekształcone wyniki mają pozostać w wyjściu.
Używaj `compactMap`, gdy chcesz pominąć nieudane konwersje lub wartości `nil`.

</details>

<details>
<summary>39. Czym jest currying (koncepcyjnie)?</summary>

#### Swift

Currying to idea przekształcenia funkcji, która przyjmuje wiele argumentów, w
ciąg funkcji, z których każda przyjmuje jeden argument.

Koncepcyjnie:

```swift
func add(_ a: Int) -> (Int) -> Int {
    return { b in
        a + b
    }
}

let addFive = add(5)
print(addFive(3)) // 8
```

Currying jest przydatne do:

- Partial application
- Wielokrotnego użycia wyspecjalizowanych funkcji
- Koncepcji programowania funkcyjnego

Jest to bardziej koncepcja niż coś używanego codziennie w typowym kodzie aplikacji Swift.

</details>

<details>
<summary>40. Czym jest `@autoclosure`?</summary>

#### Swift

`@autoclosure` automatycznie opakowuje wyrażenie w closure.

Dzięki temu możesz przekazać wyrażenie tam, gdzie oczekiwane jest closure, bez
ręcznego zapisywania składni closure.

```swift
func logIfTrue(_ condition: @autoclosure () -> Bool) {
    if condition() {
        print("True")
    }
}

logIfTrue(2 > 1)
```

Bez `@autoclosure` zapis wyglądałby tak:

```swift
logIfTrue({ 2 > 1 })
```

Jest ono często używane w API takich jak `assert`.
Używaj go ostrożnie, ponieważ może ukrywać fakt, że tworzone jest closure.

</details>

<details>
<summary>41. Czym są generyki i dlaczego są przydatne?</summary>

#### Swift

Generyki pozwalają pisać elastyczny, wielokrotnego użytku kod, który działa z
różnymi typami przy zachowaniu bezpieczeństwa typów.

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

Tutaj `T` jest symbolem zastępczym dla typu generycznego.

Generyki są przydatne, ponieważ:

- Zmniejszają duplikację kodu
- Zachowują silne bezpieczeństwo typów
- Sprawiają, że API są bardziej wielokrotnego użytku

</details>

<details>
<summary>42. Czym są protokoły?</summary>

#### Swift

Protokół definiuje zestaw wymagań, które typ musi spełniać.

Może wymagać:

- Właściwości
- Metod
- Inicjalizatorów

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

Protokoły służą do definiowania wspólnego zachowania bez wymuszania dziedziczenia.

</details>

<details>
<summary>43. Czym jest protocol-oriented programming (POP)?</summary>

#### Swift

Protocol-oriented programming to podejście, w którym zachowanie buduje się za
pomocą protokołów i rozszerzeń protokołów zamiast polegać głównie na
dziedziczeniu klas.

W Swift jest to jeden z podstawowych stylów projektowania.

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

POP jest przydatne, ponieważ:

- Promuje kompozycję zamiast dziedziczenia
- Poprawia ponowne wykorzystanie kodu
- Dobrze współpracuje z value types, takimi jak `struct`

</details>

<details>
<summary>44. Czym są associated types?</summary>

#### Swift

Associated type to zastępczy typ wewnątrz protokołu.

Pozwala typowi zgodnemu z protokołem zdecydować, jaki konkretny typ zostanie
użyty.

```swift
protocol Container {
    associatedtype Item
    var items: [Item] { get set }
}

struct IntContainer: Container {
    var items: [Int]
}
```

Associated types są przydatne, gdy protokół ma działać z różnymi typami danych,
ale nadal pozostać type-safe.

</details>

<details>
<summary>45. Czym jest protocol composition?</summary>

#### Swift

Protocol composition oznacza łączenie wielu protokołów w jedno wymaganie typu.

Używa operatora `&`.

```swift
protocol Readable {}
protocol Writable {}

func process(file: Readable & Writable) {
    print("Can read and write")
}
```

Używaj protocol composition, gdy wartość musi jednocześnie spełniać wiele zachowań.

</details>

<details>
<summary>46. Czym są protocol extensions?</summary>

#### Swift

Protocol extensions pozwalają dodawać domyślne implementacje do protokołów.

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

Oznacza to, że typy zgodne z protokołem mogą automatycznie otrzymać wspólne
zachowanie.

Protocol extensions są kluczową częścią protocol-oriented programming.

</details>

<details>
<summary>47. Czym jest conditional conformance?</summary>

#### Swift

Conditional conformance oznacza, że typ generyczny jest zgodny z protokołem
tylko wtedy, gdy zostaną spełnione określone warunki.

```swift
extension Array: Equatable where Element: Equatable {}
```

Oznacza to, że `Array` jest `Equatable` tylko wtedy, gdy jego elementy są
`Equatable`.

Jest to przydatne przy budowaniu generycznych API, które pozostają precyzyjne i
type-safe.

</details>

<details>
<summary>48. Czym jest type erasure?</summary>

#### Swift

Type erasure ukrywa konkretny typ implementacji za wspólnym wrapperem lub
abstrakcyjnym interfejsem.

Jest często potrzebne podczas pracy z protokołami, które mają:

- Associated types
- Wymagania `Self`

Na przykład SwiftUI używa `AnyView` jako wrappera z type erasure.

```swift
let views: [AnyView] = [
    AnyView(Text("Hello")),
    AnyView(Image(systemName: "star"))
]
```

Type erasure pomaga przechowywać lub przekazywać wartości o różnych konkretnych
typach w jednolity sposób.

</details>

<details>
<summary>49. Jaka jest różnica między `Self` a `self`?</summary>

#### Swift

`Self` i `self` to nie to samo.

- `Self` odnosi się do samego typu
- `self` odnosi się do bieżącej instancji

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

Używaj `self` podczas pracy z bieżącym obiektem lub wartością.
Używaj `Self`, gdy odnosisz się do konkretnego typu na poziomie typu.

</details>

<details>
<summary>50. Jak działa ARC w Swift?</summary>

#### Swift

ARC oznacza Automatic Reference Counting.

Jest to system zarządzania pamięcią w Swift dla instancji klas.
ARC automatycznie śledzi, ile silnych referencji wskazuje na obiekt.

- Gdy liczba referencji rośnie, obiekt pozostaje w pamięci
- Gdy liczba referencji spada do zera, obiekt jest zwalniany z pamięci

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

ARC nie zarządza value types, takimi jak `struct` i `enum`, w ten sam sposób,
ponieważ nie są to reference types.

Głównym ryzykiem związanym z ARC jest retain cycle, które zwykle rozwiązuje się
przy użyciu referencji `weak` lub `unowned`.

</details>

<details>
<summary>51. Czym jest retain cycle?</summary>

#### Swift

Retain cycle powstaje wtedy, gdy dwa lub więcej obiektów typu referencyjnego
utrzymuje do siebie silne referencje, przez co żaden z nich nie może zostać
zwolniony z pamięci.

Zwykle prowadzi to do memory leak.

```swift
class Person {
    var apartment: Apartment?
}

class Apartment {
    var tenant: Person?
}
```

Jeśli obie referencje są silne, obiekty utrzymują się wzajemnie przy życiu.

Retain cycles często pojawiają się przy:

- Closures przechwytujących `self`
- Relacjach parent-child między obiektami
- Nieprawidłowo zaimplementowanym wzorcu delegate

</details>

<details>
<summary>52. Jaka jest różnica między `weak` a `unowned`?</summary>

#### Swift

Zarówno `weak`, jak i `unowned` służą do unikania retain cycles, ale działają
inaczej.

| Cecha | `weak` | `unowned` |
| --- | --- | --- |
| Optional | Tak | Nie |
| Może stać się `nil` | Tak | Nie |
| Bezpieczeństwo | Bezpieczniejsze | Mniej bezpieczne |
| Użycie | Gdy obiekt referencjonowany może zniknąć | Gdy obiekt referencjonowany musi istnieć |

#### Przykład

```swift
weak var delegate: SomeDelegate?
unowned var owner: Owner
```

Używaj `weak`, gdy referencja może stać się `nil`.
Używaj `unowned`, gdy referencja zawsze powinna wskazywać na prawidłowy obiekt.

</details>

<details>
<summary>53. Kiedy użyć `unowned` zamiast `weak`?</summary>

#### Swift

Używaj `unowned`, gdy obiekt referencjonowany musi istnieć przez cały czas,
gdy ta referencja jest używana.

Jest to częste wtedy, gdy dwa obiekty są połączone, ale jeden z nich wyraźnie
kontroluje cykl życia drugiego.

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

Używaj `unowned` tylko wtedy, gdy masz pewność, że referencja nigdy nie zostanie
użyta po zwolnieniu obiektu z pamięci.

W przeciwnym razie użyj `weak`.

</details>

<details>
<summary>54. Czym jest memory leak?</summary>

#### Swift

Memory leak występuje wtedy, gdy pamięć nie jest już potrzebna, ale nadal nie
zostaje zwolniona.

W Swift zwykle dzieje się tak dlatego, że obiekty nadal mają silne referencje,
często z powodu retain cycles.

Oznaki memory leak:

- Obiekty nigdy nie są zwalniane z pamięci
- Zużycie pamięci stale rośnie
- Ekrany lub view modele pozostają w pamięci po zamknięciu

Memory leaks mogą prowadzić do:

- Większego zużycia pamięci
- Problemów z wydajnością
- Zakończenia działania aplikacji przez system

</details>

<details>
<summary>55. Jak debugować problemy z pamięcią?</summary>

#### Swift

Typowe sposoby debugowania problemów z pamięcią w Swift to:

1. Xcode Memory Graph Debugger
2. Instruments z narzędziem Leaks
3. Instruments z Allocations
4. Sprawdzanie, czy `deinit` jest wywoływany

#### Przykład

```swift
deinit {
    print("Deallocated")
}
```

Jeśli `deinit` nie jest wywoływany wtedy, gdy powinien, to znaczy, że coś nadal
utrzymuje obiekt.

Typowy workflow:

- Odtwórz przepływ ekranu
- Zamknij ekran
- Sprawdź Memory Graph
- Poszukaj retain cycles lub nieoczekiwanych silnych referencji

</details>

<details>
<summary>56. Jak Swift zarządza pamięcią dla value types i reference types?</summary>

#### Swift

Swift zarządza pamięcią inaczej dla value types i reference types.

#### Value types

- `struct`
- `enum`
- `tuple`

Są kopiowane przy przypisaniu lub przekazaniu do funkcji.
Nie używają ARC w taki sam sposób jak instancje klas.

#### Reference types

- `class`

Są współdzielone przez referencję.
Swift używa ARC do zarządzania ich cyklem życia.

Główna różnica jest więc taka:

- Value types kopiują dane
- Reference types współdzielą tę samą instancję

</details>

<details>
<summary>57. Czym jest async/await w Swift?</summary>

#### Swift

`async/await` to nowoczesna składnia Swift do programowania asynchronicznego.

Sprawia, że kod asynchroniczny wygląda bardziej jak zwykły kod sekwencyjny.

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

Korzyści:

- Czystszy kod asynchroniczny
- Lepsza czytelność
- Łatwiejsza obsługa błędów za pomocą `try`

</details>

<details>
<summary>58. Czym jest structured concurrency?</summary>

#### Swift

Structured concurrency oznacza, że praca asynchroniczna jest zorganizowana w
jasną hierarchię zadań parent i child.

To pomaga Swift zarządzać:

- Cyklem życia zadań
- Anulowaniem
- Propagacją błędów

W structured concurrency zadania potomne zwykle należą do zakresu, w którym
zostały utworzone, i nie pozostają uruchomione bez kontroli.

Typowe narzędzia structured concurrency to:

- `async let`
- `TaskGroup`

Dzięki temu kod współbieżny jest bezpieczniejszy i łatwiejszy do zrozumienia.

</details>

<details>
<summary>59. Czym są Tasks i Task groups?</summary>

#### Swift

`Task` to jednostka pracy asynchronicznej.
`TaskGroup` pozwala uruchomić wiele zadań potomnych równolegle i zebrać ich
wyniki.

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

Używaj:

- `Task` dla jednej operacji asynchronicznej
- `TaskGroup` dla wielu równoległych zadań potomnych

</details>

<details>
<summary>60. Czym jest `MainActor` i dlaczego jest ważny?</summary>

#### Swift

`MainActor` to global actor, który zapewnia, że kod jest wykonywany na głównym
wątku.

Jest ważny, ponieważ aktualizacje UI muszą odbywać się na głównym wątku.

```swift
@MainActor
class ViewModel {
    var title = ""

    func updateTitle() {
        title = "Updated"
    }
}
```

Możesz też jawnie przełączyć się na niego:

```swift
await MainActor.run {
    print("Update UI")
}
```

`MainActor` pomaga zapobiegać błędom związanym z wątkami i zwiększa bezpieczeństwo kodu związanego z UI.

</details>

<details>
<summary>61. Czym są actors i jak zapobiegają race conditions?</summary>

#### Swift

Actors to reference types, które chronią swój mutowalny stan przed niebezpiecznym współbieżnym dostępem.

Pomagają zapobiegać race conditions przez izolację stanu, dzięki czemu tylko
jedno zadanie może uzyskać dostęp do tego mutowalnego stanu w danym momencie.

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

Aby uzyskać dostęp do stanu izolowanego przez actor z zewnątrz, zwykle używa
się `await`.

Actors są ważne we współczesnej współbieżności Swift, ponieważ w wielu
przypadkach stanowią bezpieczniejszą alternatywę dla ręcznego blokowania.

</details>

<details>
<summary>62. Czym jest data race i jak Swift temu zapobiega?</summary>

#### Swift

Data race występuje wtedy, gdy wiele wątków lub zadań uzyskuje dostęp do tych
samych mutowalnych danych w tym samym czasie, a przynajmniej jedno z nich je
zapisuje.

Może to powodować nieprzewidywalne zachowanie i awarie.

Swift pomaga zapobiegać data races za pomocą:

- Actor isolation
- `Sendable`
- Structured concurrency
- Main actor isolation dla kodu UI

We współczesnym Swift funkcje współbieżności zostały zaprojektowane tak, aby
wcześniej wykrywać niebezpieczny współdzielony mutowalny stan i ułatwiać jego unikanie.

</details>

<details>
<summary>63. Jaka jest różnica między GCD a modern concurrency?</summary>

#### Swift

Zarówno GCD, jak i nowoczesna współbieżność Swift obsługują pracę asynchroniczną,
ale używają różnych modeli.

| Cecha | GCD | Modern concurrency |
| --- | --- | --- |
| Styl | Callback-based | `async/await` |
| Czytelność | Więcej zagnieżdżeń | Bardziej liniowy |
| Anulowanie | Ręczne | Wbudowane wsparcie |
| Bezpieczeństwo | Niższy poziom | Bezpieczniejsze i bardziej uporządkowane |
| Narzędzia | `DispatchQueue` | `Task`, actors, `TaskGroup`, `MainActor` |

#### Przykład GCD

```swift
DispatchQueue.global().async {
    print("Background work")
}
```

#### Przykład modern concurrency

```swift
Task {
    print("Async work")
}
```

Nowoczesna współbieżność jest zwykle preferowana w nowym kodzie Swift.

</details>

<details>
<summary>64. Jak synchronizować dostęp do współdzielonego stanu?</summary>

#### Swift

Synchronizujesz współdzielony stan, upewniając się, że kod współbieżny nie
odczytuje i nie zapisuje tych samych mutowalnych danych w niebezpieczny sposób.

Typowe podejścia:

- Actors
- Kolejki szeregowe
- Blokady
- `MainActor` dla stanu UI

#### Preferowane nowoczesne podejście

```swift
actor Store {
    private var items: [String] = []

    func add(_ item: String) {
        items.append(item)
    }
}
```

We współczesnym Swift actors są zwykle najbezpieczniejszym domyślnym wyborem
dla współdzielonego mutowalnego stanu.

</details>

<details>
<summary>65. Czym jest `Sendable` w Swift?</summary>

#### Swift

`Sendable` to protokół oznaczający, że typ można bezpiecznie przenosić między
domenami współbieżności.

Ma to znaczenie wtedy, gdy wartości są przekazywane między zadaniami lub actors.

```swift
struct User: Sendable {
    let id: Int
    let name: String
}
```

Value types z niemutowalnymi stored properties często są naturalnie `Sendable`.

`Sendable` pomaga Swift wykrywać niebezpieczne współdzielenie mutowalnego stanu
w kodzie współbieżnym.

</details>

<details>
<summary>66. Jak działa obsługa błędów w Swift?</summary>

#### Swift

Swift używa jawnej obsługi błędów z `throw`, `throws`, `do`, `try` i `catch`.

#### Przykład

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

To sprawia, że obsługa błędów jest jawna i bezpieczniejsza niż ciche ignorowanie niepowodzeń.

</details>

<details>
<summary>67. Jaka jest różnica między `try`, `try?` i `try!`?</summary>

#### Swift

Wszystkie trzy są używane z funkcjami rzucającymi błędy, ale obsługują błędy inaczej.

| Słowo kluczowe | Zachowanie |
| --- | --- |
| `try` | Propaguje błąd lub obsługuje go normalnie |
| `try?` | Zamienia wynik na optional i zwraca `nil` przy błędzie |
| `try!` | Wymusza sukces i powoduje crash, jeśli zostanie rzucony błąd |

#### Przykład

```swift
let value1 = try someThrowingFunction()
let value2 = try? someThrowingFunction()
let value3 = try! someThrowingFunction()
```

Używaj:

- `try` w normalnej obsłudze błędów
- `try?`, gdy niepowodzenie można zignorować jako `nil`
- `try!` tylko wtedy, gdy niepowodzenie jest niemożliwe

</details>

<details>
<summary>68. Czym jest `throws` vs `rethrows`?</summary>

#### Swift

`throws` oznacza, że funkcja może rzucić własny błąd.
`rethrows` oznacza, że funkcja rzuca błąd tylko wtedy, gdy rzuci go jeden z jej argumentów funkcyjnych.

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

Używaj `rethrows` dla funkcji opakowujących, które same nie rzucają błędów, ale wywołują closure, które może rzucać.

</details>

<details>
<summary>69. Czym jest typ Result?</summary>

#### Swift

`Result` to enum reprezentujące:

- Sukces z wartością
- Niepowodzenie z błędem

```swift
let result: Result<String, Error> = .success("Done")
```

Jest zdefiniowany w przybliżeniu tak:

```swift
enum Result<Success, Failure: Error> {
    case success(Success)
    case failure(Failure)
}
```

`Result` jest przydatny, gdy chcesz jawnie przekazywać sukces lub błąd,
szczególnie w callbackach albo asynchronicznych API.

</details>

<details>
<summary>70. Jak propagować błędy?</summary>

#### Swift

Propagujesz błędy, oznaczając funkcję słowem `throws` i używając `try` podczas
wywoływania innej funkcji rzucającej błędy.

```swift
func loadData() throws {
    throw NSError(domain: "Example", code: 1)
}

func processData() throws {
    try loadData()
}
```

Tutaj `processData()` samo nie obsługuje błędu.
Przekazuje błąd wyżej do swojego wywołującego.

Jest to przydatne wtedy, gdy funkcja niższego poziomu ma zgłosić niepowodzenie,
a warstwa wyższego poziomu ma zdecydować, jak je obsłużyć.

</details>

<details>
<summary>71. Czym są property wrappers?</summary>

#### Swift

Property wrappers to funkcja Swift, która pozwala dodawać wielokrotnego użytku
zachowanie wokół stored properties.

Są deklarowane za pomocą `@propertyWrapper`.

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

Property wrappers są przydatne do:

- Walidacji
- Formatowania
- Persistencji
- Dependency injection

</details>

<details>
<summary>72. Czym są opaque return types (`some`)?</summary>

#### Swift

Opaque return types pozwalają funkcji zwracać wartość jakiegoś konkretnego typu
bez ujawniania tego dokładnego typu w API.

Używają słowa kluczowego `some`.

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Wywołujący wie, że zwracana wartość jest zgodna z `View`, ale nie musi znać
konkretnego typu.

Opaque types są szeroko używane w SwiftUI.

</details>

<details>
<summary>73. Jaka jest różnica między opaque types a generykami?</summary>

#### Swift

Zarówno opaque types, jak i generyki działają z abstrakcyjnymi typami, ale
rozwiązują różne problemy.

| Cecha | Generyki | Opaque types |
| --- | --- | --- |
| Kto wybiera konkretny typ? | Wywołujący | Implementacja |
| Składnia | `<T>` | `some Protocol` |
| Główne zastosowanie | Elastyczne API wielokrotnego użytku | Ukrywanie konkretnych typów zwracanych |

#### Przykład generyka

```swift
func echo<T>(_ value: T) -> T {
    value
}
```

#### Przykład opaque type

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Używaj generyków, gdy typ dostarcza wywołujący.
Używaj opaque types, gdy typ dostarcza implementacja, ale go ukrywa.

</details>

<details>
<summary>74. Czym są result builders?</summary>

#### Swift

Result builders to funkcja, która pozwala Swift budować złożone wartości z
bloku deklaratywnego kodu.

Są intensywnie używane w SwiftUI.

```swift
@resultBuilder
struct StringBuilder {
    static func buildBlock(_ components: String...) -> String {
        components.joined(separator: " ")
    }
}
```

Result builder przekształca wiele wyrażeń w jeden końcowy rezultat.

Jest to przydatne dla API w stylu DSL.

</details>

<details>
<summary>75. Czym są custom operators?</summary>

#### Swift

Custom operators pozwalają definiować własne operatory w Swift.

```swift
infix operator +++

func +++ (lhs: Int, rhs: Int) -> Int {
    lhs + rhs + 1
}
```

Możesz tworzyć:

- Operatory prefiksowe
- Operatory infiksowe
- Operatory postfiksowe

Mogą być bardzo przydatne, ale należy używać ich ostrożnie.

Jeśli są nadużywane, utrudniają czytanie kodu.

</details>

<details>
<summary>76. Czym jest dynamic dispatch vs static dispatch?</summary>

#### Swift

Dispatch to sposób, w jaki Swift decyduje, którą implementację metody wywołać.

#### Static dispatch

Wywołanie metody jest rozstrzygane w czasie kompilacji.
Jest zwykle szybsze.

To jest typowe dla:

- `struct`
- `enum`
- Metod `final`

#### Dynamic dispatch

Wywołanie metody jest rozstrzygane w czasie działania programu.
Jest bardziej elastyczne, ale ma większy narzut.

To jest typowe dla:

- Klas z dziedziczeniem
- `@objc dynamic`

Static dispatch koncentruje się na wydajności.
Dynamic dispatch koncentruje się na elastyczności w czasie działania.

</details>

<details>
<summary>77. Czym jest phantom type?</summary>

#### Swift

Phantom type to generyczny parametr typu, który jest używany tylko w czasie
kompilacji i nie jest przechowywany w czasie działania programu.

Pomaga zwiększyć bezpieczeństwo API przez zakodowanie dodatkowych informacji w systemie typów.

```swift
struct ID<Tag> {
    let value: String
}

enum UserTag {}
enum OrderTag {}

let userID = ID<UserTag>(value: "123")
let orderID = ID<OrderTag>(value: "123")
```

Mimo że obie wartości zawierają `String`, Swift traktuje je jako różne typy.

</details>

<details>
<summary>78. Czym jest escape analysis?</summary>

#### Swift

Escape analysis to koncepcja optymalizacji kompilatora używana do określenia,
czy wartość lub closure opuszcza zakres, w którym zostało utworzone.

Jeśli coś nie opuszcza zakresu, Swift może wydajniej zoptymalizować użycie
pamięci i sposób wywołania.

Ta koncepcja wiąże się z:

- Escaping vs non-escaping closures
- Decyzjami optymalizacyjnymi stack vs heap

W codziennych rozmowach kwalifikacyjnych ze Swift zwykle wystarczy wiedzieć, że
non-escaping closures są łatwiejsze do zoptymalizowania przez kompilator.

</details>

<details>
<summary>79. Czym jest function builder (result builder)?</summary>

#### Swift

Function builder to starsza nazwa tego, co Swift dziś nazywa result builder.

Jest to funkcja, która przekształca blok wyrażeń w jeden wynik, często dla
deklaratywnych API.

SwiftUI intensywnie korzysta z tego w składni budowania widoków.

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

Dzisiaj więc:

- `function builder` to starszy termin
- `result builder` to obecny oficjalny termin

</details>

<details>
<summary>80. Czym jest SwiftUI i czym różni się od UIKit?</summary>

#### Swift

SwiftUI to deklaratywny framework Apple do budowania interfejsów na platformach Apple.

UIKit to starszy imperatywny framework do budowania interfejsów iOS.

| Cecha | SwiftUI | UIKit |
| --- | --- | --- |
| Styl | Deklaratywny | Imperatywny |
| Aktualizacje UI | Oparte na stanie | Ręczne aktualizacje |
| Składnia | DSL oparty na Swift | Klasy i API cyklu życia |
| Typowe użycie | Nowoczesne UI na platformach Apple | Dojrzały framework UI dla iOS |

#### Przykład SwiftUI

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
    }
}
```

#### Przykład UIKit

```swift
let label = UILabel()
label.text = "Hello"
```

SwiftUI zwykle pozwala szybciej tworzyć UI i lepiej integruje się z nowoczesnymi funkcjami Swift.
UIKit daje niższy poziom kontroli i ma większy ekosystem starszych rozwiązań.

</details>

<details>
<summary>81. Czym jest declarative UI?</summary>

#### Swift

Declarative UI oznacza, że opisujesz, jak interfejs powinien wyglądać dla
danego stanu, zamiast pisać krok po kroku instrukcje jego aktualizacji.

W SwiftUI deklarujesz interfejs na podstawie danych, a framework aktualizuje
ekran, gdy stan się zmienia.

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

Różni się to od imperative UI, gdzie ręcznie tworzysz widoki i bezpośrednio je zmieniasz.

</details>

<details>
<summary>82. Czym jest `@State`?</summary>

#### Swift

`@State` to property wrapper używany w SwiftUI do przechowywania lokalnego
mutowalnego stanu wewnątrz widoku.

Gdy wartość `@State` się zmienia, SwiftUI renderuje widok ponownie.

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

Używaj `@State` dla prostego stanu należącego do samego widoku.

</details>

<details>
<summary>83. Czym jest `@StateObject` vs `@ObservedObject`?</summary>

#### Swift

Oba są używane z obserwowalnymi typami referencyjnymi, ale różnią się własnością.

| Wrapper | Własność |
| --- | --- |
| `@StateObject` | Widok tworzy i posiada obiekt |
| `@ObservedObject` | Obiekt jest tworzony gdzie indziej i przekazywany do widoku |

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

Używaj `@StateObject`, gdy widok ma utrzymywać obiekt przy życiu.
Używaj `@ObservedObject`, gdy widok tylko obserwuje obiekt zewnętrzny.

</details>

<details>
<summary>84. Czym jest `@EnvironmentObject`?</summary>

#### Swift

`@EnvironmentObject` służy do współdzielenia obserwowalnego obiektu przez
hierarchię widoków SwiftUI bez ręcznego przekazywania go przez każdy widok.

```swift
class AppState: ObservableObject {
    @Published var isLoggedIn = false
}

struct ContentView: View {
    @EnvironmentObject var appState: AppState
}
```

Jest przydatny dla współdzielonego stanu całej aplikacji, takiego jak:

- Sesja użytkownika
- Motyw
- Ustawienia

Obiekt musi zostać wstrzyknięty do environment, zanim widok go użyje.

</details>

<details>
<summary>85. Czym jest `@Published`?</summary>

#### Swift

`@Published` to property wrapper używany wewnątrz `ObservableObject`.

Gdy właściwość się zmienia, powiadamia SwiftUI lub innych subskrybentów, że
obiekt uległ zmianie.

```swift
class UserViewModel: ObservableObject {
    @Published var name = "Alice"
}
```

`@Published` jest powszechnie używany dla stanu view modelu, który powinien aktualizować UI.

</details>

<details>
<summary>86. Jak działa state management w SwiftUI?</summary>

#### Swift

State management w SwiftUI opiera się na tym, że to dane sterują UI.

Gdy stan się zmienia, SwiftUI ponownie oblicza widoki, których to dotyczy.

Typowe narzędzia:

- `@State` dla lokalnego stanu widoku
- `@StateObject` dla posiadanych obserwowalnych obiektów
- `@ObservedObject` dla zewnętrznych obserwowalnych obiektów
- `@EnvironmentObject` dla współdzielonych obiektów całej aplikacji
- `@Binding` do przekazywania mutowalnego stanu między widokami

Główna idea jest prosta:

- Stan się zmienia
- SwiftUI aktualizuje hierarchię widoków

</details>

<details>
<summary>87. Czym jest `ViewModifier`?</summary>

#### Swift

`ViewModifier` to wielokrotnego użytku sposób stosowania stylu lub zachowania
do widoków SwiftUI.

```swift
struct TitleStyle: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.title)
            .foregroundColor(.blue)
    }
}
```

Użycie:

```swift
Text("Hello").modifier(TitleStyle())
```

View modifiers pomagają uniknąć powtarzania tej samej logiki stylowania widoków.

</details>

<details>
<summary>88. Czym jest SwiftUI environment?</summary>

#### Swift

SwiftUI environment to system niejawnego przekazywania wartości w dół hierarchii widoków.

Zapewnia współdzielony kontekst, taki jak:

- Schemat kolorów
- Locale
- Kategoria rozmiaru
- Własne wartości środowiskowe

Wartości środowiskowe odczytuje się za pomocą `@Environment`.

```swift
struct ContentView: View {
    @Environment(\.colorScheme) var colorScheme
}
```

Environment pomaga uniknąć ręcznego przekazywania wspólnej konfiguracji przez wiele warstw widoków.

</details>

<details>
<summary>89. Czym jest `GeometryReader`?</summary>

#### Swift

`GeometryReader` to kontener SwiftUI, który daje dostęp do informacji o układzie
dostępnej przestrzeni i geometrii widoku.

```swift
GeometryReader { geometry in
    Text("Width: \(geometry.size.width)")
}
```

Jest przydatny, gdy potrzebujesz:

- Dynamicznego układu zależnego od dostępnego rozmiaru
- Obliczeń pozycji
- Responsywnego zachowania UI

Należy używać go ostrożnie, ponieważ nadmierne użycie może utrudnić zrozumienie kodu layoutu.

</details>

<details>
<summary>90. Jak działa nawigacja w SwiftUI?</summary>

#### Swift

Nawigacja w SwiftUI jest zazwyczaj budowana za pomocą `NavigationStack`.

Przechodzisz dalej, dodając destination do stosu.

```swift
NavigationStack {
    NavigationLink("Open Details") {
        DetailView()
    }
}
```

Możesz też używać nawigacji opartej na wartościach z `navigationDestination`.

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

Nawigacja SwiftUI jest oparta na stanie i bardziej deklaratywna niż kontrolery nawigacji UIKit.

</details>

<details>
<summary>91. Czym jest lifecycle widoku SwiftUI?</summary>

#### Swift

Widoki SwiftUI są value types, więc ich lifecycle różni się od kontrolerów widoków UIKit.

Widok SwiftUI jest często tworzony i odtwarzany ponownie, gdy zmienia się stan.
Ważna jest nie żywotność samej struktury, lecz żywotność stanu z nią powiązanego.

Typowe hooki lifecycle obejmują:

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

W SwiftUI stan i przepływ danych mają większe znaczenie niż żywotność obiektu.

</details>

<details>
<summary>92. Dlaczego widoki SwiftUI są strukturami?</summary>

#### Swift

Widoki SwiftUI są strukturami, ponieważ value types dobrze współpracują z declarative UI.

Korzyści:

- Lekkość
- Łatwość ponownego tworzenia
- Bezpieczniejszy przepływ danych
- Lepsze możliwości optymalizacji wydajności w SwiftUI

Ponieważ są value types, SwiftUI może często odtwarzać wartości widoków i
wydajnie je porównywać, gdy stan się zmienia.

Rzeczywiste trwałe części UI są zarządzane przez framework, a nie przez samą strukturę widoku.

</details>

<details>
<summary>93. Jaka jest różnica między UIKit a SwiftUI?</summary>

#### Swift

UIKit i SwiftUI to oba frameworki UI od Apple, ale używają różnych podejść.

| Cecha | UIKit | SwiftUI |
| --- | --- | --- |
| Styl | Imperatywny | Deklaratywny |
| Główne elementy | `UIView`, `UIViewController` | `View` |
| Aktualizacje stanu | Ręczne | Oparte na stanie |
| Typowe użycie | Dojrzała, niższopoziomowa kontrola UI | Nowoczesne deklaratywne tworzenie UI |

UIKit daje bardziej bezpośrednią kontrolę.
SwiftUI daje nowocześniejszy i bardziej zwięzły sposób tworzenia UI.

</details>

<details>
<summary>94. Czym jest Auto Layout?</summary>

#### Swift

Auto Layout to system Apple do pozycjonowania i określania rozmiaru elementów UI za pomocą constraints.

Zamiast ręcznie ustawiać frame dla każdego rozmiaru ekranu, definiujesz reguły
opisujące relacje między widokami.

Przykłady:

- Label jest 16 punktów od lewej krawędzi
- Button jest wyśrodkowany poziomo
- Obraz zachowuje równą szerokość i wysokość

Auto Layout pomaga budować adaptacyjne interfejsy dla różnych urządzeń i rozmiarów ekranów.

</details>

<details>
<summary>95. Czym jest intrinsic content size?</summary>

#### Swift

Intrinsic content size to naturalny rozmiar, jaki widok preferuje na podstawie swojej zawartości.

Na przykład:

- Label dopasowuje swój rozmiar do tekstu
- Image view dopasowuje swój rozmiar do obrazu

Pomaga to Auto Layout zrozumieć, jak duży powinien być widok nawet bez jawnych constraints szerokości i wysokości.

Widoki takie jak `UILabel` i `UIButton` często mają intrinsic content size.

</details>

<details>
<summary>96. Czym są constraints i anchors?</summary>

#### Swift

Constraints to reguły układu używane przez Auto Layout.
Anchors to wygodny w kodzie sposób tworzenia tych constraints.

Typowe anchors:

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

Anchors sprawiają, że kod Auto Layout jest bezpieczniejszy i łatwiejszy do czytania niż starsze API constraints.

</details>

<details>
<summary>97. Czym są reusable cells?</summary>

#### Swift

Reusable cells to komórki tabeli lub collection view, które są ponownie używane
zamiast tworzone od zera dla każdego elementu.

Poprawia to:

- Wydajność
- Zużycie pamięci
- Płynność przewijania

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
```

Mechanizm reuse działa przez ponowne wykorzystanie komórek, które zeszły poza ekran, dla nowej zawartości.

</details>

<details>
<summary>98. Jaka jest różnica między `UITableView` a `UICollectionView`?</summary>

#### Swift

Oba wyświetlają listy danych, ale zostały zaprojektowane pod różne potrzeby układu.

| Cecha | `UITableView` | `UICollectionView` |
| --- | --- | --- |
| Styl układu | Głównie pionowa lista | Elastyczne układy |
| Złożoność | Prostszy | Bardziej konfigurowalny |
| Typowe użycie | Proste listy, formularze, ustawienia | Siatki, niestandardowe układy, złożone listy |

Używaj `UITableView` dla prostego UI opartego na listach.
Używaj `UICollectionView`, gdy potrzebujesz bardziej elastycznych lub niestandardowych układów.

</details>

<details>
<summary>99. Czym jest `@IBOutlet` vs `@IBAction`?</summary>

#### Swift

Oba są używane z Interface Builder w storyboardach UIKit lub plikach XIB.

- `@IBOutlet` łączy element UI z kodem
- `@IBAction` łączy zdarzenie UI z kodem

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

`@IBOutlet` służy do referencji do elementów UI.
`@IBAction` służy do obsługi działań użytkownika.

</details>

<details>
<summary>100. Czym jest lifecycle `UIViewController`?</summary>

#### Swift

Lifecycle `UIViewController` to sekwencja metod wywoływanych podczas tworzenia,
pokazywania, układania i usuwania kontrolera widoku.

Typowe metody lifecycle:

1. `viewDidLoad`
2. `viewWillAppear`
3. `viewDidAppear`
4. `viewWillDisappear`
5. `viewDidDisappear`

#### Przykładowe role

- `viewDidLoad`: początkowa konfiguracja
- `viewWillAppear`: aktualizacja UI przed pokazaniem
- `viewDidAppear`: uruchamianie animacji lub śledzenia
- `viewWillDisappear`: przygotowanie do opuszczenia ekranu
- `viewDidDisappear`: prace porządkowe

Zrozumienie tego lifecycle jest kluczowe w tworzeniu aplikacji UIKit.

</details>

<details>
<summary>101. Czym jest MVC?</summary>

#### Swift

MVC oznacza Model-View-Controller.

Jest to wzorzec projektowy, który dzieli aplikację na trzy części:

- Model: dane i logika biznesowa
- View: UI
- Controller: obsługuje interakcję między modelem a widokiem

W iOS `UIViewController` często pełni rolę kontrolera.

MVC jest proste i powszechne, ale w aplikacjach UIKit łatwo może prowadzić do
"Massive View Controller", jeśli zbyt dużo logiki trafi do kontrolera.

</details>

<details>
<summary>102. Czym jest MVVM?</summary>

#### Swift

MVVM oznacza Model-View-ViewModel.

Rozdziela odpowiedzialności w następujący sposób:

- Model: dane i reguły biznesowe
- View: UI
- ViewModel: logika prezentacji i stan dla widoku

ViewModel przygotowuje dane do wyświetlenia i ogranicza ilość logiki w widoku
lub kontrolerze widoku.

MVVM jest popularne w SwiftUI i powszechnie używane także w aplikacjach UIKit.

</details>

<details>
<summary>103. Czym jest dependency injection?</summary>

#### Swift

Dependency injection oznacza dostarczanie obiektowi potrzebnych zależności z
zewnątrz, zamiast tworzenia ich wewnątrz obiektu.

Na przykład zamiast tego, by view model tworzył własny serwis sieciowy, serwis
jest przekazywany do niego z zewnątrz.

Korzyści:

- Lepsza testowalność
- Mniejsze sprzężenie
- Łatwiejsza wymiana implementacji

</details>

<details>
<summary>104. Jak implementujesz DI w Swift?</summary>

#### Swift

Najczęstszym sposobem jest constructor injection.

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

Inne typowe podejścia:

- Property injection
- Method injection
- Kontenery zależności

Constructor injection jest zwykle preferowane, ponieważ czyni zależności jawnymi.

</details>

<details>
<summary>105. Czym jest delegation pattern?</summary>

#### Swift

Delegation to wzorzec, w którym jeden obiekt przekazuje odpowiedzialność za
część pracy lub zdarzenia innemu obiektowi.

Jest on zwykle implementowany za pomocą protokołów.

```swift
protocol ButtonHandler: AnyObject {
    func didTapButton()
}
```

Delegation jest szeroko stosowane w UIKit, na przykład z:

- `UITableViewDelegate`
- `UITextFieldDelegate`

Pomaga oddzielać odpowiedzialności i zachować elastyczną komunikację.

</details>

<details>
<summary>106. Kiedy należy używać singletona?</summary>

#### Swift

Singleton powinien być używany wtedy, gdy w aplikacji musi istnieć dokładnie
jedna współdzielona instancja.

Typowe przykłady:

- Konfiguracja całej aplikacji
- Serwis logowania
- Menedżer cache

```swift
final class Logger {
    static let shared = Logger()

    private init() {}
}
```

Używaj singletonów ostrożnie.
Ich nadużywanie może tworzyć ukryte zależności i utrudniać testowanie.

</details>

<details>
<summary>107. Czym jest KVO?</summary>

#### Swift

KVO oznacza Key-Value Observing.

Jest to mechanizm obserwowania zmian właściwości niektórych obiektów,
szczególnie tych zgodnych z Objective-C.

Jest głównie związany z Cocoa i zachowaniem runtime Objective-C.

KVO jest rzadziej używane we współczesnym kodzie Swift w porównaniu z:

- Combine
- `@Published`
- Narzędziami stanu SwiftUI

Nadal jednak pojawia się w niektórych API UIKit i Foundation.

</details>

<details>
<summary>108. Czym jest `NotificationCenter`?</summary>

#### Swift

`NotificationCenter` to system rozgłaszania komunikatów do wielu obserwatorów.

Jeden obiekt publikuje powiadomienie, a inne obiekty mogą go nasłuchiwać.

```swift
NotificationCenter.default.post(name: .didLogout, object: nil)
```

Jest przydatny do luźnej komunikacji między częściami aplikacji, szczególnie
gdy bezpośrednie referencje nie są idealne.

Używaj go ostrożnie, ponieważ nadużywanie może utrudnić śledzenie przepływu danych.

</details>

<details>
<summary>109. Jak wykonać żądanie sieciowe w Swift?</summary>

#### Swift

Standardowym sposobem jest użycie `URLSession`.

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

We współczesnym Swift możesz również używać `async/await` z `URLSession`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>110. Czym jest `Codable`?</summary>

#### Swift

`Codable` to alias typu dla:

- `Encodable`
- `Decodable`

Pozwala typom Swift łatwo konwertować się do i z formatów takich jak JSON.

```swift
struct User: Codable {
    let id: Int
    let name: String
}
```

Typowe przypadki użycia:

- Parsowanie odpowiedzi API
- Zapisywanie danych lokalnych
- Kodowanie request body

`Codable` znacznie ogranicza ilość boilerplate przy serializacji.

</details>

<details>
<summary>111. Czym są decoding strategies?</summary>

#### Swift

Decoding strategies to opcje używane przez `JSONDecoder` do kontrolowania tego,
jak dane wejściowe są dekodowane.

Typowe strategie obejmują:

- `dateDecodingStrategy`
- `keyDecodingStrategy`
- `dataDecodingStrategy`

```swift
let decoder = JSONDecoder()
decoder.keyDecodingStrategy = .convertFromSnakeCase
decoder.dateDecodingStrategy = .iso8601
```

Są przydatne, gdy format API nie odpowiada bezpośrednio formatowi twojego modelu Swift.

</details>

<details>
<summary>112. Czym jest `URLSession`?</summary>

#### Swift

`URLSession` to główne API Apple do wykonywania żądań sieciowych.

Jest używane do:

- Pobierania danych
- Wysyłania danych
- Pobierania plików
- Zarządzania zadaniami sieciowymi

Obsługuje zarówno styl completion-handler, jak i `async/await`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>113. Czym jest caching strategy?</summary>

#### Swift

Caching strategy to plan określający, jakie dane кешować, gdzie je кешować oraz
kiedy je odświeżać lub unieważniać.

Typowe warstwy cache w aplikacjach iOS:

- Cache w pamięci
- Cache na dysku
- Cache HTTP

Kluczowe decyzje zwykle obejmują:

- Czas życia cache
- Reguły unieważniania
- Kompromisy pamięć vs dysk
- Świeżość vs szybkość

Dobra caching strategy poprawia wydajność, zmniejsza użycie sieci i sprawia, że
aplikacja działa szybciej z perspektywy użytkownika.

</details>

<details>
<summary>114. Jak debugować crashe?</summary>

#### Swift

Typowe sposoby debugowania crashy obejmują:

1. Odczyt crash logu
2. Sprawdzenie stack trace
3. Odtworzenie problemu lokalnie
4. Użycie debuggera Xcode i breakpointów
5. Użycie narzędzi do raportowania crashy, takich jak Firebase Crashlytics

Ważne rzeczy do sprawdzenia:

- Wątek, który uległ awarii
- Typ wyjątku
- Ostatnio wywołane metody
- Wersja urządzenia i systemu operacyjnego

Celem jest odtworzenie awarii, znalezienie root cause i potwierdzenie poprawki.

</details>

<details>
<summary>115. Jak wykrywać memory leaks?</summary>

#### Swift

Typowe sposoby wykrywania memory leaks to:

- Xcode Memory Graph Debugger
- Instruments Leaks tool
- Instruments Allocations
- Sprawdzanie `deinit`

```swift
deinit {
    print("Object deallocated")
}
```

Jeśli obiekt powinien zniknąć, ale pozostaje w pamięci, może istnieć retain
cycle albo inna nieoczekiwana silna referencja.

</details>

<details>
<summary>116. Jak poprawiasz wydajność aplikacji iOS?</summary>

#### Swift

Typowe sposoby poprawy wydajności obejmują:

- Ograniczanie pracy na głównym wątku
- Optymalizację renderowania i przewijania
- Unikanie zbędnych alokacji
- Cache’owanie kosztownych wyników
- Używanie pracy w tle dla ciężkich zadań
- Profilowanie za pomocą Instruments

Najpierw należy mierzyć, a dopiero potem optymalizować rzeczywiste wąskie gardło.

Typowe narzędzia:

- Time Profiler
- Allocations
- Memory Graph
- Network instruments

</details>

<details>
<summary>117. Jak optymalizujesz zużycie baterii?</summary>

#### Swift

Aby zoptymalizować zużycie baterii, ograniczaj zbędną pracę i unikaj
utrzymywania aktywnego sprzętu lub zadań w tle dłużej, niż to konieczne.

Typowe praktyki:

- Minimalizowanie aktywności w tle
- Unikanie nadmiernych aktualizacji lokalizacji
- Grupowanie żądań sieciowych
- Ograniczanie częstych timerów i polling
- Unikanie zbędnych animacji i redraw

Główna zasada jest prosta:

- Wykonuj mniej pracy
- Rób to rzadziej

</details>

<details>
<summary>118. Czym jest Keychain i kiedy go używać?</summary>

#### Swift

Keychain to bezpieczny system przechowywania Apple dla małych, wrażliwych fragmentów danych.

Używaj Keychain do takich rzeczy jak:

- Tokeny
- Hasła
- Dane uwierzytelniające
- Wrażliwe sekrety

Nie używaj go jako ogólnej bazy danych.

Keychain jest bezpieczniejszy niż `UserDefaults` dla poufnych danych.

</details>

<details>
<summary>119. Czym jest App Transport Security?</summary>

#### Swift

App Transport Security (ATS) to funkcja bezpieczeństwa iOS, która domyślnie
promuje bezpieczne połączenia sieciowe.

Zwykle wymaga:

- HTTPS
- Silnych ustawień TLS

Jeśli aplikacja potrzebuje niezabezpieczonego HTTP lub słabszych ustawień
bezpieczeństwa, trzeba dodać jawne wyjątki w konfiguracji aplikacji.

ATS pomaga chronić ruch sieciowy przed przechwyceniem i niezabezpieczonym transportem.

</details>

<details>
<summary>120. Jak bezpiecznie przechowywać dane?</summary>

#### Swift

To zależy od wrażliwości danych.

Typowe zasady:

- Używaj Keychain dla haseł, tokenów i sekretów
- Używaj file protection dla wrażliwych plików
- Unikaj przechowywania sekretów w postaci zwykłego tekstu
- Nie przechowuj poufnych danych w `UserDefaults`
- Szyfruj dane, gdy to potrzebne

Ważne jest także:

- Ograniczanie tego, co przechowujesz
- Przechowywanie danych tylko tak długo, jak to konieczne
- Ochrona danych zarówno w spoczynku, jak i w trakcie przesyłania

</details>

<details>
<summary>121. Czym jest `XCTest`?</summary>

#### Swift

`XCTest` to framework testowy Apple do pisania i uruchamiania testów w Xcode.

Jest używany do:

- Testów jednostkowych
- Testów UI
- Testów wydajności

```swift
func testAddition() {
    XCTAssertEqual(2 + 2, 4)
}
```

Jest to standardowe narzędzie testowe dla rozwoju na platformach Apple.

</details>

<details>
<summary>122. Czym różni się unit testing od UI testing?</summary>

#### Swift

Unit testing sprawdza małe fragmenty logiki w izolacji.
UI testing sprawdza aplikację przez interfejs użytkownika.

| Typ | Fokus |
| --- | --- |
| Unit test | Logika biznesowa, funkcje, klasy |
| UI test | Rzeczywiste przepływy użytkownika i interakcje z ekranem |

Testy jednostkowe są zwykle:

- Szybsze
- Bardziej izolowane
- Łatwiejsze do debugowania

Testy UI są przydatne do walidacji zachowania end-to-end.

</details>

<details>
<summary>123. Czym jest mocking?</summary>

#### Swift

Mocking oznacza zastąpienie prawdziwej zależności fałszywą wersją testową.

Pomaga to testować jednostkę w izolacji.

Na przykład zamiast wywoływać prawdziwe API, mock serwisu sieciowego zwraca
z góry zdefiniowane dane.

Mocking jest przydatny do:

- Szybszych testów
- Przewidywalnych wyników
- Testowania scenariuszy błędów

</details>

<details>
<summary>124. Jak pozostajesz na bieżąco ze Swift?</summary>

#### Swift

Mocna odpowiedź łączy oficjalne źródła z praktyczną nauką.

Typowe sposoby:

- Czytanie propozycji Swift Evolution
- Śledzenie sesji WWDC
- Czytanie dokumentacji Apple
- Testowanie nowych funkcji języka w side projects
- Obserwowanie cenionych inżynierów Swift i iOS

Ważne jest nie tylko czytanie aktualizacji, ale też stosowanie ich w prawdziwym kodzie.

</details>

<details>
<summary>125. Opowiedz o złożonej funkcji, którą zbudowałeś.</summary>

#### Swift

Dobra odpowiedź na rozmowie powinna mieć taką strukturę:

1. Krótko wyjaśnij funkcję
2. Opisz główne wyzwania techniczne
3. Wyjaśnij swoje decyzje i kompromisy
4. Pokaż rezultat

#### Przykładowa struktura odpowiedzi

"Zbudowałem funkcję synchronizacji offline-first dla aplikacji mobilnej. Główne
wyzwania dotyczyły rozwiązywania konfliktów, lokalnej persystencji, logiki
ponawiania oraz utrzymania responsywności UI podczas synchronizacji. Podzieliłem
problem na warstwy networkingu, lokalnego przechowywania danych i orkiestracji
sync. Dodałem też polityki retry, obsługę synchronizacji w tle i logowanie.
Rezultatem była szybsza odczuwalna wydajność, lepsza niezawodność przy
niestabilnych sieciach i mniej zgłoszeń do supportu."

Najlepsze odpowiedzi są konkretne i mierzalne.

</details>

<details>
<summary>126. Jak podchodzisz do code review?</summary>

#### Swift

Mocne podejście do code review skupia się najpierw na poprawności, a potem na utrzymywalności.

Typowe priorytety:

- Błędy i edge cases
- Dopasowanie do architektury i projektu
- Czytelność
- Nazewnictwo
- Pokrycie testami
- Wydajność i bezpieczeństwo, gdy to istotne

Dobra recenzja powinna być jasna, rzeczowa i konkretna.

Celem nie jest tylko znalezienie problemów, ale też poprawa jakości kodu i dzielenie się wiedzą.

</details>

<details>
<summary>127. Jak projektujesz skalowalną architekturę iOS?</summary>

#### Swift

Skalowalna architektura polega na tym, aby wraz ze wzrostem aplikacji funkcje
pozostawały łatwe do rozwijania, testowania i utrzymania.

Ważne zasady:

- Wyraźny podział odpowiedzialności
- Modułowy projekt
- Dependency injection
- Testowalna logika biznesowa
- Przewidywalny przepływ danych

Skalowalna architektura powinna pomagać zespołom dodawać funkcje bez ciągłego
przepisywania istniejącego kodu.

</details>

<details>
<summary>128. Jakie trade-offy bierzesz pod uwagę przy wyborze architektury?</summary>

#### Swift

Architektura zawsze wiąże się z trade-offami.

Typowe czynniki:

- Rozmiar i doświadczenie zespołu
- Złożoność aplikacji
- Szybkość rozwoju
- Testowalność
- Utrzymywalność
- Elastyczność pod przyszły rozwój

Prosta aplikacja może nie potrzebować ciężkiej architektury.
Duża aplikacja zwykle korzysta na mocniejszym rozdzieleniu odpowiedzialności,
jaśniejszych granicach i lepszym zarządzaniu zależnościami.

Najlepszym wyborem jest najprostsza architektura, która nadal dobrze pasuje do problemu.

</details>
