**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Swift <img src="./assets/swift.svg" width="40" height="40" />
</h1>

<h2>Найпопулярніші запитання та відповіді на співбесіді з Swift</h2>

<details>
<summary>1. Для чого Swift переважно використовується в сучасній розробці?</summary>

#### Swift

Swift переважно використовується для створення застосунків для платформ Apple:

- iOS
- macOS
- watchOS
- tvOS
- visionOS

Основні сфери використання:

- Мобільна розробка
- Нативна розробка для платформ Apple
- Бекенд-розробка з фреймворками на кшталт Vapor
- Консольні інструменти та скрипти

Swift цінується за безпечність, продуктивність і сучасний синтаксис.

</details>

<details>
<summary>2. У чому різниця між `let` і `var`?</summary>

#### Swift

`let` створює константу, а `var` створює змінну.

- Використовуйте `let`, коли значення не повинно змінюватися.
- Використовуйте `var`, коли значення може змінитися пізніше.

```swift
let name = "Alice"
var age = 25

age = 26 // Дозволено
// name = "Bob" // Помилка
```

Використання `let` за замовчуванням робить код безпечнішим і простішим для
розуміння.

</details>

<details>
<summary>3. Поясніть type inference у Swift.</summary>

#### Swift

Type inference означає, що Swift може автоматично визначити тип значення на
основі присвоєних даних, тому вам не завжди потрібно явно вказувати тип.

```swift
let title = "Swift"      // String
let year = 2025          // Int
let isActive = true      // Bool
```

Ви все одно можете вказати тип вручну, якщо хочете чіткіше показати намір:

```swift
let score: Double = 99
```

Type inference робить код коротшим, зберігаючи типобезпечність.

</details>

<details>
<summary>4. Що таке optional і чому вони важливі?</summary>

#### Swift

Optional — це тип, який може містити або:

- значення
- `nil`

Optional важливі, тому що вони явно показують відсутність значення і
допомагають запобігати runtime-падінням через роботу з відсутніми даними.

```swift
var nickname: String? = "Sam"
nickname = nil
```

Без optional Swift не міг би безпечно представляти значення, які можуть бути
відсутніми, наприклад:

- Дані з користувацького вводу
- Поля відповіді мережевого запиту
- Значення з бази даних
- URL, який може не ініціалізуватися

</details>

<details>
<summary>5. У чому різниця між optional binding і force unwrapping?</summary>

#### Swift

Optional binding безпечно витягує значення з optional.
Force unwrapping витягує значення напряму і призводить до падіння, якщо
optional дорівнює `nil`.

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

У більшості випадків використовуйте optional binding.
Force unwrapping варто використовувати лише тоді, коли ви повністю впевнені, що
значення не є `nil`.

</details>

<details>
<summary>6. Що таке optional chaining і коли його використовувати?</summary>

#### Swift

Optional chaining — це спосіб безпечно звертатися до властивостей, методів або
subscript у optional-значенні.

Якщо optional дорівнює `nil`, увесь вираз повертає `nil` замість падіння.

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

Використовуйте optional chaining, коли працюєте з вкладеними optional,
особливо в:

- Модельних об'єктах
- Відповідях API
- UI-посиланнях, які можуть не існувати

</details>

<details>
<summary>7. Що таке оператор nil coalescing?</summary>

#### Swift

Оператор nil coalescing — це `??`.
Він задає значення за замовчуванням, якщо optional дорівнює `nil`.

```swift
let username: String? = nil
let displayName = username ?? "Guest"
```

У цьому прикладі `displayName` стане `"Guest"`.

Використовуйте `??`, коли хочете задати запасне значення для optional.

</details>

<details>
<summary>8. Що таке tuple і коли їх варто використовувати?</summary>

#### Swift

Tuple — це група значень, об'єднаних в одне складене значення.

```swift
let person = ("Alice", 28)
```

Також можна задавати tuple іменовані значення:

```swift
let httpResponse = (statusCode: 200, message: "OK")
print(httpResponse.statusCode)
```

Tuple варто використовувати для короткоживучих згрупованих значень, наприклад:

- Повернення кількох значень з функції
- Представлення невеликого пов'язаного набору даних
- Тимчасових локальних даних

Для складніших або повторно використовуваних даних краще використовувати
`struct` або `class`.

</details>

<details>
<summary>9. Які основні типи колекцій є у Swift?</summary>

#### Swift

Основні типи колекцій у Swift:

1. `Array`
2. `Set`
3. `Dictionary`

#### Array

Зберігає впорядкований список значень.

```swift
let numbers = [1, 2, 3]
```

#### Set

Зберігає унікальні невпорядковані значення.

```swift
let uniqueNumbers: Set = [1, 2, 3]
```

#### Dictionary

Зберігає пари ключ-значення.

```swift
let userAges = ["Alice": 25, "Bob": 30]
```

Ці колекції постійно використовуються в розробці на Swift.

</details>

<details>
<summary>10. У чому різниця між Array, Set і Dictionary?</summary>

#### Swift

Різниця полягає в тому, як вони зберігають дані та як до них звертаються.

| Тип | Що зберігає | Порядок | Унікальність | Доступ |
| --- | --- | --- | --- | --- |
| `Array` | Список значень | Впорядкований | Дублікати дозволені | За індексом |
| `Set` | Унікальні значення | Невпорядкований | Дублікати не дозволені | Пошук за значенням |
| `Dictionary` | Пари ключ-значення | Невпорядкований | Ключі мають бути унікальними | За ключем |

#### Приклад

```swift
let array = ["a", "b", "a"]
let set: Set = ["a", "b", "a"]
let dictionary = ["name": "Alice", "city": "Paris"]
```

- `Array` зберігає порядок і може містити дублікати.
- `Set` прибирає дублікати.
- `Dictionary` зіставляє ключі зі значеннями.

</details>

<details>
<summary>11. Що таке value types і reference types?</summary>

#### Swift

Value types копіюються під час присвоєння або передачі далі.
Reference types спільно використовують один і той самий екземпляр.

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

За замовчуванням варто використовувати value types, якщо вам не потрібен
спільний змінний стан.

</details>

<details>
<summary>12. У чому різниця між struct і class?</summary>

#### Swift

Головна різниця в тому, що `struct` — це value type, а `class` — reference
type.

| Властивість | `struct` | `class` |
| --- | --- | --- |
| Тип | Value type | Reference type |
| Поведінка при копіюванні | Копіюється при присвоєнні | Передається за посиланням |
| Наслідування | Не підтримується | Підтримується |
| Деініціалізатор | Не підтримується | Підтримується |
| Перевірка ідентичності | Ні | Так, через `===` |

У більшості випадків використовуйте `struct`.
`class` варто використовувати, коли вам потрібні:

- Спільний змінний стан
- Наслідування
- Семантика ідентичності

</details>

<details>
<summary>13. Що таке copy-on-write?</summary>

#### Swift

Copy-on-write — це оптимізація, за якої значення не копіюється одразу.
Swift створює реальну копію лише тоді, коли одне зі значень змінюється.

Це часто використовується в стандартних колекціях, таких як:

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

Такий підхід дає безпечність value types разом із хорошою продуктивністю.

</details>

<details>
<summary>14. Що таке immutability і чому вона важлива?</summary>

#### Swift

Immutability означає, що значення не можна змінити після його створення.

У Swift значення, оголошені через `let`, є незмінними.

```swift
let name = "Alice"
// name = "Bob" // Помилка
```

Immutability важлива, тому що вона:

- Робить код безпечнішим
- Зменшує кількість помилок
- Полегшує відстеження стану
- Допомагає краще міркувати про concurrency

За замовчуванням використовуйте незмінні значення, а змінними робіть їх лише
тоді, коли це справді потрібно.

</details>

<details>
<summary>15. Що таке computed properties?</summary>

#### Swift

Computed property не зберігає значення напряму.
Натомість вона обчислює його щоразу, коли до неї звертаються.

```swift
struct Rectangle {
    var width: Double
    var height: Double

    var area: Double {
        width * height
    }
}
```

Computed properties також можуть мати `get` і `set`:

```swift
struct Square {
    var side: Double

    var area: Double {
        get { side * side }
        set { side = sqrt(newValue) }
    }
}
```

Використовуйте computed properties, коли значення залежить від інших значень.

</details>

<details>
<summary>16. Що таке property observers (`willSet` / `didSet`)?</summary>

#### Swift

Property observers дають змогу реагувати на зміну значення stored property.

- `willSet` виконується перед збереженням нового значення
- `didSet` виконується після збереження нового значення

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

Використовуйте їх, коли вам потрібно:

- Логувати зміни
- Оновлювати UI
- Запускати side effects після зміни значення

</details>

<details>
<summary>17. Що таке lazy properties?</summary>

#### Swift

Lazy property ініціалізується лише тоді, коли її використовують уперше.

Вона оголошується через ключове слово `lazy` і має бути `var`.

```swift
class DataManager {
    lazy var formatter: DateFormatter = {
        let formatter = DateFormatter()
        formatter.dateStyle = .medium
        return formatter
    }()
}
```

Використовуйте lazy properties, коли:

- Ініціалізація є дорогою
- Властивість може ніколи не знадобитися
- Властивість залежить від `self` після ініціалізації

</details>

<details>
<summary>18. Що таке key paths у Swift?</summary>

#### Swift

Key paths — це type-safe посилання на властивості.
Вони дозволяють звертатися до властивості опосередковано.

```swift
struct User {
    let name: String
}

let keyPath = \User.name
let user = User(name: "Alice")

print(user[keyPath: keyPath]) // Alice
```

Key paths корисні для:

- Сортування
- Mapping
- Generic API
- Спостереження або доступу до вкладених властивостей типобезпечним способом

</details>

<details>
<summary>19. Що таке type casting (`is`, `as`, `as?`, `as!`)?</summary>

#### Swift

Type casting використовується для перевірки або перетворення типу значення під
час виконання.

- `is` перевіряє, чи є значення певного типу
- `as` виконує upcasting до надтипу
- `as?` безпечно виконує downcasting і повертає optional
- `as!` примусово виконує downcasting і призводить до падіння, якщо він не вдасться

```swift
class Animal {}
class Dog: Animal {}

let animal: Animal = Dog()

print(animal is Dog) // true

let dog1 = animal as? Dog // Безпечно
let dog2 = animal as! Dog // Небезпечно, якщо тип неправильний
```

У більшості випадків використовуйте `as?`.
`as!` варто використовувати лише тоді, коли помилка неможлива.

</details>

<details>
<summary>20. У чому різниця між `==` і `===`?</summary>

#### Swift

`==` перевіряє рівність значень.
`===` перевіряє ідентичність посилань.

#### `==`

Використовується для перевірки, чи два значення є рівними.

```swift
let a = 5
let b = 5

print(a == b) // true
```

#### `===`

Використовується лише з class, щоб перевірити, чи два посилання вказують на
один і той самий екземпляр.

```swift
class User {}

let user1 = User()
let user2 = user1
let user3 = User()

print(user1 === user2) // true
print(user1 === user3) // false
```

Отже:

- `==` означає "однакове значення"
- `===` означає "один і той самий об'єкт у пам'яті"

</details>

<details>
<summary>21. Як працює `switch` у Swift (pattern matching)?</summary>

#### Swift

`switch` у Swift є потужним і підтримує pattern matching.
Він може зіставляти:

- Точні значення
- Кілька значень
- Діапазони
- Tuple
- Enum cases
- Значення з умовами

На відміну від деяких мов, `switch` у Swift має бути вичерпним.
Тобто всі можливі варіанти повинні бути оброблені.

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

`switch` у Swift часто використовується, тому що він безпечніший і виразніший,
ніж довгий ланцюжок `if`.

</details>

<details>
<summary>22. Що таке `fallthrough` і коли його варто уникати?</summary>

#### Swift

`fallthrough` змушує виконання перейти з одного `case` до наступного `case` у
`switch`.

За замовчуванням Swift не робить такого переходу автоматично.

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

Результат:

```swift
One
Two
```

У більшості випадків `fallthrough` варто уникати, тому що він:

- Робить логіку менш зрозумілою
- Може спричиняти неочікувану поведінку
- Зазвичай має чистіші альтернативи

Використовуйте його лише тоді, коли ви свідомо хочете виконати також наступний
`case`.

</details>

<details>
<summary>23. Що таке `guard` і коли його використовувати?</summary>

#### Swift

`guard` використовується для раннього виходу.
Він перевіряє умову, і якщо умова не виконується, виконання повинно покинути
поточну область видимості.

```swift
func printName(_ name: String?) {
    guard let name = name else {
        print("Name is missing")
        return
    }

    print(name)
}
```

Використовуйте `guard`, коли:

- Відсутнє обов'язкове значення
- Не виконані передумови
- Ви хочете уникнути глибокої вкладеності

Він робить код пласким і легшим для читання.

</details>

<details>
<summary>24. У чому різниця між `if let` і `guard let`?</summary>

#### Swift

Обидва використовуються для optional binding, але застосовуються по-різному.

| Властивість | `if let` | `guard let` |
| --- | --- | --- |
| Основне призначення | Умовна гілка | Ранній вихід |
| Область видимості розгорнутого значення | Усередині блоку `if` | Після `guard` |
| Читабельність | Добре для коротких перевірок | Краще для обов'язкових умов |

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

Використовуйте `if let` для локальної гілки з optional.
Використовуйте `guard let`, коли значення потрібне для решти функції.

</details>

<details>
<summary>25. Що таке half-open range?</summary>

#### Swift

Half-open range включає нижню межу, але не включає верхню.

Для цього використовується `..<`

```swift
for i in 0..<5 {
    print(i)
}
```

Результат:

```swift
0
1
2
3
4
```

Half-open range корисні для:

- Циклів
- Індексації масивів
- Ситуацій, де кінцеве значення не повинно включатися

</details>

<details>
<summary>26. Що таке `where` clause?</summary>

#### Swift

`where` clause додає додаткову умову до pattern, циклу, generic constraint або
`catch` block.

#### У `switch`

```swift
let point = (2, 2)

switch point {
case let (x, y) where x == y:
    print("x equals y")
default:
    print("No match")
}
```

#### У циклах

```swift
for number in 1...10 where number.isMultiple(of: 2) {
    print(number)
}
```

Використовуйте `where`, коли хочете точніше налаштувати зіставлення або
фільтрацію.

</details>

<details>
<summary>27. Що робить `defer`?</summary>

#### Swift

`defer` планує виконання коду безпосередньо перед виходом з поточної області
видимості.

Він виконується незалежно від того, як саме відбувається вихід:

- Звичайний `return`
- Ранній `return`
- Кинута помилка

```swift
func performTask() {
    print("Start")

    defer {
        print("Cleanup")
    }

    print("Work")
}
```

Результат:

```swift
Start
Work
Cleanup
```

`defer` корисний для cleanup-задач, наприклад:

- Закриття файлів
- Розблокування ресурсів
- Скидання стану

</details>

<details>
<summary>28. Що таке `break` і `continue`?</summary>

#### Swift

`break` зупиняє поточний цикл або `switch`.
`continue` пропускає поточну ітерацію циклу і переходить до наступної.

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

Використовуйте `break`, щоб зупинити обробку.
Використовуйте `continue`, щоб пропустити одну ітерацію.

</details>

<details>
<summary>29. Для чого використовується `stride()`?</summary>

#### Swift

`stride()` використовується для створення послідовностей, які рухаються з
певним кроком.

Він корисний тоді, коли ви не хочете збільшувати значення на `1`.

#### Приклад з `through`

```swift
for number in stride(from: 0, through: 10, by: 2) {
    print(number)
}
```

#### Приклад з `to`

```swift
for number in stride(from: 0, to: 10, by: 2) {
    print(number)
}
```

Різниця:

- `through` включає кінцеве значення, якщо це можливо
- `to` не включає кінцеве значення

</details>

<details>
<summary>30. Що таке raw strings?</summary>

#### Swift

Raw strings дозволяють записувати string literals так, щоб зворотні слеші й
лапки не оброблялися як звичайні escape-символи.

Вони використовують `#` навколо рядка.

```swift
let path = #"C:\Users\Name\Documents"#
let text = #"He said "Hello""#
```

Якщо ви хочете interpolation всередині raw string, використовуйте `\#(...)`:

```swift
let name = "Alice"
let message = #"Hello, \#(name)"#
```

Raw strings корисні для:

- Регулярних виразів
- Шляхів до файлів
- JSON-фрагментів
- Рядків із великою кількістю зворотних слешів або лапок

</details>

<details>
<summary>31. Що таке closures у Swift?</summary>

#### Swift

Closures — це самодостатні блоки коду, які можна передавати далі та виконувати
пізніше.

Вони схожі на функції, але їх можна зберігати у змінних, і вони можуть
захоплювати значення з навколишньої області видимості.

```swift
let greet = { (name: String) in
    print("Hello, \(name)")
}

greet("Alice")
```

Closures часто використовуються для:

- Callbacks
- Completion handlers
- Сортування
- Функціональних операцій на кшталт `map` і `filter`

</details>

<details>
<summary>32. Escaping vs non-escaping closures?</summary>

#### Swift

Non-escaping closure виконується до повернення з функції.
Escaping closure може бути збережений і виконаний уже після повернення з
функції.

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

За замовчуванням використовуйте non-escaping closures.
Escaping closures використовуйте для асинхронної роботи, callbacks або
closures, які потрібно зберегти.

</details>

<details>
<summary>33. Що означає `@escaping`?</summary>

#### Swift

`@escaping` означає, що closure може жити довше, ніж функція, у яку його
передали.

Іншими словами, немає гарантії, що цей closure виконається до завершення
функції.

```swift
class Downloader {
    var completion: (() -> Void)?

    func fetch(completion: @escaping () -> Void) {
        self.completion = completion
    }
}
```

`@escaping` зазвичай потрібен, коли closure:

- Зберігається у властивості
- Виконується асинхронно
- Передається в іншу функцію, яка його зберігає

</details>

<details>
<summary>34. Що таке trailing closures?</summary>

#### Swift

Trailing closure — це closure, записаний після круглих дужок функції.

Такий синтаксис є чистішим, коли останній аргумент — це closure.

```swift
func perform(action: () -> Void) {
    action()
}

perform {
    print("Done")
}
```

Trailing closures часто використовуються в:

- Async API
- UIKit і SwiftUI callbacks
- Операціях над колекціями

</details>

<details>
<summary>35. Що таке value capturing у closures?</summary>

#### Swift

Closures можуть захоплювати значення з навколишньої області видимості й
продовжувати використовувати їх навіть після того, як ця область зазвичай уже
мала б зникнути.

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

Тут closure захоплює `count` і зберігає його живим.

Це корисно, але також може призводити до проблем з пам'яттю, якщо об'єкти
випадково захоплюються сильно.

</details>

<details>
<summary>36. Як Swift керує пам'яттю в closures?</summary>

#### Swift

Swift використовує ARC (Automatic Reference Counting).
Closures є reference types, тому вони можуть сильно захоплювати об'єкти.

Якщо closure сильно захоплює `self`, а `self` сильно утримує цей closure, може
виникнути retain cycle.

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

Щоб уникати витоків пам'яті, за потреби використовуйте capture lists:

- `[weak self]`, коли `self` може стати `nil`
- `[unowned self]`, коли `self` точно має існувати

</details>

<details>
<summary>37. Що таке higher-order functions (`map`, `filter`, `reduce`)?</summary>

#### Swift

Higher-order functions — це функції, які приймають інші функції або closures як
аргументи, або повертають їх.

У Swift поширені higher-order functions для колекцій:

- `map`
- `filter`
- `reduce`

#### `map`

Перетворює кожен елемент.

```swift
let numbers = [1, 2, 3]
let doubled = numbers.map { $0 * 2 }
```

#### `filter`

Залишає лише ті елементи, які підходять під умову.

```swift
let evenNumbers = numbers.filter { $0.isMultiple(of: 2) }
```

#### `reduce`

Об'єднує всі елементи в один результат.

```swift
let sum = numbers.reduce(0) { $0 + $1 }
```

Ці функції роблять код коротшим і виразнішим.

</details>

<details>
<summary>38. У чому різниця між `map` і `compactMap`?</summary>

#### Swift

`map` перетворює кожен елемент і залишає ту саму кількість елементів.
`compactMap` перетворює елементи та прибирає результати `nil`.

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

Використовуйте `map`, коли всі перетворені результати мають залишитися у
вихідному масиві.
Використовуйте `compactMap`, коли хочете ігнорувати невдалі перетворення або
значення `nil`.

</details>

<details>
<summary>39. Що таке currying (концептуально)?</summary>

#### Swift

Currying — це ідея перетворення функції, яка приймає кілька аргументів, на
послідовність функцій, кожна з яких приймає один аргумент.

Концептуально:

```swift
func add(_ a: Int) -> (Int) -> Int {
    return { b in
        a + b
    }
}

let addFive = add(5)
print(addFive(3)) // 8
```

Currying корисний для:

- Partial application
- Повторно використовуваних спеціалізованих функцій
- Концепцій функціонального програмування

Це радше концепція, ніж щось, що щодня активно використовується у типовому Swift
app code.

</details>

<details>
<summary>40. Що таке `@autoclosure`?</summary>

#### Swift

`@autoclosure` автоматично загортає вираз у closure.

Це дозволяє передавати вираз туди, де очікується closure, без явного запису
синтаксису closure.

```swift
func logIfTrue(_ condition: @autoclosure () -> Bool) {
    if condition() {
        print("True")
    }
}

logIfTrue(2 > 1)
```

Без `@autoclosure` довелося б писати так:

```swift
logIfTrue({ 2 > 1 })
```

Його часто використовують в API на кшталт `assert`.
Використовуйте його обережно, бо він може приховувати сам факт створення
closure.

</details>

<details>
<summary>41. Що таке generics і чому вони корисні?</summary>

#### Swift

Generics дозволяють писати гнучкий і повторно використовуваний код, який
працює з різними типами, зберігаючи type safety.

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

Тут `T` — це заповнювач для generic type.

Generics корисні, тому що вони:

- Зменшують дублювання коду
- Зберігають сильну type safety
- Роблять API більш повторно використовуваними

</details>

<details>
<summary>42. Що таке protocols?</summary>

#### Swift

Protocol визначає набір вимог, яких має дотримуватися тип.

Він може вимагати:

- Властивості
- Методи
- Ініціалізатори

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

Protocols використовуються для визначення спільної поведінки без примусу до
наслідування.

</details>

<details>
<summary>43. Що таке protocol-oriented programming (POP)?</summary>

#### Swift

Protocol-oriented programming — це підхід, за якого поведінка будується за
допомогою protocols і protocol extensions, а не переважно через class
inheritance.

У Swift це один із ключових стилів проєктування.

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

POP корисний, тому що він:

- Заохочує композицію замість наслідування
- Покращує повторне використання коду
- Добре працює з value types, такими як `struct`

</details>

<details>
<summary>44. Що таке associated types?</summary>

#### Swift

Associated type — це тип-заповнювач усередині protocol.

Він дозволяє типу, який відповідає protocol, самому визначити, який конкретний
тип буде використано.

```swift
protocol Container {
    associatedtype Item
    var items: [Item] { get set }
}

struct IntContainer: Container {
    var items: [Int]
}
```

Associated types корисні, коли protocol має працювати з різними типами даних,
але при цьому залишатися type-safe.

</details>

<details>
<summary>45. Що таке protocol composition?</summary>

#### Swift

Protocol composition означає поєднання кількох protocols в одну вимогу до типу.

Для цього використовується `&`.

```swift
protocol Readable {}
protocol Writable {}

func process(file: Readable & Writable) {
    print("Can read and write")
}
```

Використовуйте protocol composition, коли значення має одночасно відповідати
кільком видам поведінки.

</details>

<details>
<summary>46. Що таке protocol extensions?</summary>

#### Swift

Protocol extensions дозволяють додавати protocols реалізації за замовчуванням.

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

Це означає, що типи, які відповідають protocol, можуть автоматично отримати
спільну поведінку.

Protocol extensions — важлива частина protocol-oriented programming.

</details>

<details>
<summary>47. Що таке conditional conformance?</summary>

#### Swift

Conditional conformance означає, що generic type відповідає protocol лише тоді,
коли виконуються певні умови.

```swift
extension Array: Equatable where Element: Equatable {}
```

Це означає, що `Array` є `Equatable` лише тоді, коли його елементи також
`Equatable`.

Такий підхід корисний для побудови generic API, які залишаються точними та
type-safe.

</details>

<details>
<summary>48. Що таке type erasure?</summary>

#### Swift

Type erasure приховує конкретний тип за спільною обгорткою або абстрактним
інтерфейсом.

Він часто потрібний під час роботи з protocols, які мають:

- Associated types
- Вимоги `Self`

Наприклад, SwiftUI використовує `AnyView` як type-erased wrapper.

```swift
let views: [AnyView] = [
    AnyView(Text("Hello")),
    AnyView(Image(systemName: "star"))
]
```

Type erasure допомагає зберігати або передавати значення з різними конкретними
типами в єдиному форматі.

</details>

<details>
<summary>49. У чому різниця між `Self` і `self`?</summary>

#### Swift

`Self` і `self` — це різні речі.

- `Self` посилається на сам тип
- `self` посилається на поточний екземпляр

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

Використовуйте `self`, коли працюєте з поточним об'єктом або значенням.
Використовуйте `Self`, коли посилаєтеся на конкретний тип на рівні типів.

</details>

<details>
<summary>50. Як працює ARC у Swift?</summary>

#### Swift

ARC означає Automatic Reference Counting.

Це система керування пам'яттю у Swift для екземплярів class.
ARC автоматично відстежує, скільки strong references вказують на об'єкт.

- Коли лічильник посилань зростає, об'єкт залишається в пам'яті
- Коли лічильник посилань падає до нуля, об'єкт деалокується

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

ARC не керує value types на кшталт `struct` і `enum` у той самий спосіб,
оскільки вони не є reference types.

Головний ризик ARC — це retain cycle, який зазвичай розв'язується через `weak`
або `unowned` references.

</details>

<details>
<summary>51. Що таке retain cycle?</summary>

#### Swift

Retain cycle виникає тоді, коли два або більше reference-type об'єктів
утримують сильні посилання один на одного, тому жоден з них не може бути
деалокований.

Зазвичай це призводить до memory leak.

```swift
class Person {
    var apartment: Apartment?
}

class Apartment {
    var tenant: Person?
}
```

Якщо обидва посилання є strong, об'єкти не дадуть один одному звільнитися з
пам'яті.

Retain cycle часто трапляються з:

- Closures, які захоплюють `self`
- Батьківсько-дочірніми зв'язками між об'єктами
- Неправильно реалізованим delegation pattern

</details>

<details>
<summary>52. У чому різниця між `weak` і `unowned`?</summary>

#### Swift

І `weak`, і `unowned` використовуються для уникнення retain cycle, але вони
працюють по-різному.

| Властивість | `weak` | `unowned` |
| --- | --- | --- |
| Optional | Так | Ні |
| Може стати `nil` | Так | Ні |
| Безпечність | Безпечніше | Менш безпечно |
| Використання | Коли об'єкт може зникнути | Коли об'єкт точно має існувати |

#### Приклад

```swift
weak var delegate: SomeDelegate?
unowned var owner: Owner
```

Використовуйте `weak`, коли посилання може стати `nil`.
Використовуйте `unowned`, коли посилання завжди повинно вказувати на валідний
об'єкт.

</details>

<details>
<summary>53. Коли варто використовувати `unowned` замість `weak`?</summary>

#### Swift

`unowned` варто використовувати тоді, коли об'єкт, на який посилаються, має
точно існувати весь час, поки це посилання використовується.

Це поширено в ситуаціях, коли два об'єкти пов'язані, але один із них явно
визначає життєвий цикл іншого.

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

Використовуйте `unowned` лише тоді, коли ви впевнені, що до посилання ніколи не
звернуться після деалокації об'єкта.

В іншому разі використовуйте `weak`.

</details>

<details>
<summary>54. Що таке memory leak?</summary>

#### Swift

Memory leak виникає тоді, коли пам'ять більше не потрібна, але все одно не
звільняється.

У Swift це зазвичай трапляється тому, що об'єкти все ще мають strong
references, часто через retain cycle.

Ознаки memory leak:

- Об'єкти ніколи не деалокуються
- Використання пам'яті постійно зростає
- Екрани або view models залишаються в пам'яті після закриття

Memory leaks можуть призводити до:

- Більшого використання пам'яті
- Проблем із продуктивністю
- Завершення застосунку системою

</details>

<details>
<summary>55. Як ви дебажите проблеми з пам'яттю?</summary>

#### Swift

Поширені способи дебагу проблем із пам'яттю у Swift:

1. Xcode Memory Graph Debugger
2. Instruments із Leaks tool
3. Instruments із Allocations
4. Перевірка того, чи викликається `deinit`

#### Приклад

```swift
deinit {
    print("Deallocated")
}
```

Якщо `deinit` не викликається тоді, коли мав би, значить об'єкт усе ще хтось
утримує.

Типовий підхід такий:

- Відтворити сценарій екрана
- Закрити екран
- Перевірити Memory Graph
- Знайти retain cycle або неочікувані strong references

</details>

<details>
<summary>56. Як Swift працює з пам'яттю для value types і reference types?</summary>

#### Swift

Swift по-різному працює з пам'яттю для value types і reference types.

#### Value types

- `struct`
- `enum`
- `tuple`

Вони копіюються під час присвоєння або передачі у функції.
Вони не використовують ARC так само, як екземпляри class.

#### Reference types

- `class`

Вони передаються за посиланням.
Swift використовує ARC для керування їхнім життєвим циклом.

Отже, головна різниця така:

- Value types копіюють дані
- Reference types використовують спільний екземпляр

</details>

<details>
<summary>57. Що таке async/await у Swift?</summary>

#### Swift

`async/await` — це сучасний синтаксис Swift для асинхронного програмування.

Він робить async-код схожим на звичайний послідовний код.

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

Переваги:

- Чистіший async-код
- Краща читабельність
- Простішу обробку помилок через `try`

</details>

<details>
<summary>58. Що таке structured concurrency?</summary>

#### Swift

Structured concurrency означає, що асинхронна робота організована у зрозумілу
ієрархію батьківських і дочірніх tasks.

Це допомагає Swift керувати:

- Життєвим циклом tasks
- Скасуванням
- Поширенням помилок

У structured concurrency дочірні tasks зазвичай належать тій області
видимості, де вони були створені, і не залишаються працювати без контролю.

Поширені інструменти structured concurrency:

- `async let`
- `TaskGroup`

Це робить concurrent code безпечнішим і простішим для розуміння.

</details>

<details>
<summary>59. Що таке Task і Task groups?</summary>

#### Swift

`Task` — це одиниця асинхронної роботи.
`TaskGroup` дозволяє запускати кілька дочірніх tasks паралельно та збирати їхні
результати.

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

Використання:

- `Task` для однієї async-операції
- `TaskGroup` для кількох паралельних дочірніх tasks

</details>

<details>
<summary>60. Що таке `MainActor` і чому він важливий?</summary>

#### Swift

`MainActor` — це global actor, який гарантує, що код виконується на головному
потоці.

Це важливо, тому що оновлення UI повинні відбуватися на головному потоці.

```swift
@MainActor
class ViewModel {
    var title = ""

    func updateTitle() {
        title = "Updated"
    }
}
```

Також на нього можна переключитися явно:

```swift
await MainActor.run {
    print("Update UI")
}
```

`MainActor` допомагає уникати threading bugs і робить UI-код безпечнішим.

</details>

<details>
<summary>61. Що таке actors і як вони запобігають race conditions?</summary>

#### Swift

Actors — це reference types, які захищають свій змінний стан від небезпечного
одночасного доступу.

Вони допомагають запобігати race conditions завдяки ізоляції стану, тому лише
один task може звертатися до цього mutable state одночасно.

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

Щоб отримати доступ до actor-isolated state ззовні, зазвичай використовують
`await`.

Actors важливі в сучасній Swift concurrency, тому що часто дають безпечнішу
альтернативу ручному блокуванню.

</details>

<details>
<summary>62. Що таке data race і як Swift цьому запобігає?</summary>

#### Swift

Data race виникає тоді, коли кілька потоків або tasks одночасно звертаються до
одних і тих самих mutable data, і принаймні один із них виконує запис.

Це може спричинити непередбачувану поведінку та падіння.

Swift допомагає запобігати data races за допомогою:

- Actor isolation
- `Sendable`
- Structured concurrency
- Main actor isolation для UI-коду

У сучасному Swift concurrency-механізми спроєктовані так, щоб раніше виявляти
небезпечний спільний mutable state і спрощувати його уникнення.

</details>

<details>
<summary>63. У чому різниця між GCD і modern concurrency?</summary>

#### Swift

І GCD, і modern Swift concurrency працюють з асинхронною роботою, але
використовують різні моделі.

| Властивість | GCD | Modern concurrency |
| --- | --- | --- |
| Стиль | Callback-based | `async/await` |
| Читабельність | Більше вкладеності | Більш лінійний код |
| Скасування | Ручне | Вбудована підтримка |
| Безпечність | Нижчий рівень | Безпечніше та структурованіше |
| Інструменти | `DispatchQueue` | `Task`, actors, `TaskGroup`, `MainActor` |

#### Приклад GCD

```swift
DispatchQueue.global().async {
    print("Background work")
}
```

#### Приклад modern concurrency

```swift
Task {
    print("Async work")
}
```

Для нового Swift-коду modern concurrency зазвичай є кращим вибором.

</details>

<details>
<summary>64. Як синхронізувати доступ до shared state?</summary>

#### Swift

Синхронізація shared state означає, що concurrent code не повинен небезпечно
читати й змінювати одні й ті самі mutable data.

Поширені підходи:

- Actors
- Serial queues
- Locks
- `MainActor` для UI state

#### Бажаний сучасний підхід

```swift
actor Store {
    private var items: [String] = []

    func add(_ item: String) {
        items.append(item)
    }
}
```

У сучасному Swift actors зазвичай є найбезпечнішим варіантом за замовчуванням
для shared mutable state.

</details>

<details>
<summary>65. Що таке Sendable у Swift?</summary>

#### Swift

`Sendable` — це protocol, який позначає тип як безпечний для передачі між
concurrency domains.

Це важливо, коли значення передаються між tasks або actors.

```swift
struct User: Sendable {
    let id: Int
    let name: String
}
```

Value types з immutable stored properties часто природно є `Sendable`.

`Sendable` допомагає Swift виявляти небезпечне спільне використання mutable
state у concurrent code.

</details>

<details>
<summary>66. Як працює обробка помилок у Swift?</summary>

#### Swift

Swift використовує типізовану обробку помилок через `throw`, `throws`, `do`,
`try` і `catch`.

#### Приклад

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

Це робить обробку помилок явною і безпечнішою, ніж мовчазне ігнорування
помилок.

</details>

<details>
<summary>67. У чому різниця між `try`, `try?`, `try!`?</summary>

#### Swift

Усі три використовуються з throwing functions, але обробляють помилки
по-різному.

| Ключове слово | Поведінка |
| --- | --- |
| `try` | Звичайно передає або обробляє помилку |
| `try?` | Перетворює результат в optional і повертає `nil` у разі помилки |
| `try!` | Примусово припускає успіх і призводить до падіння, якщо буде помилка |

#### Приклад

```swift
let value1 = try someThrowingFunction()
let value2 = try? someThrowingFunction()
let value3 = try! someThrowingFunction()
```

Використання:

- `try` для нормальної обробки помилок
- `try?`, коли помилку можна представити як `nil`
- `try!` лише тоді, коли помилка неможлива

</details>

<details>
<summary>68. Що таке `throws` vs `rethrows`?</summary>

#### Swift

`throws` означає, що функція може кинути власну помилку.
`rethrows` означає, що функція кидає помилку лише тоді, коли її кидає один із
function arguments.

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

`rethrows` використовується для wrapper functions, які самі по собі не кидають
помилок, але викликають throwing closure.

</details>

<details>
<summary>69. Що таке тип Result?</summary>

#### Swift

`Result` — це enum, який представляє або:

- Успіх із певним значенням
- Помилку з error

```swift
let result: Result<String, Error> = .success("Done")
```

Приблизно він визначається так:

```swift
enum Result<Success, Failure: Error> {
    case success(Success)
    case failure(Failure)
}
```

`Result` корисний, коли потрібно явно передавати успіх або помилку, особливо в
callbacks чи асинхронних API.

</details>

<details>
<summary>70. Як ви поширюєте помилки?</summary>

#### Swift

Помилки поширюються через позначення функції як `throws` і використання `try`
під час виклику іншої throwing function.

```swift
func loadData() throws {
    throw NSError(domain: "Example", code: 1)
}

func processData() throws {
    try loadData()
}
```

Тут `processData()` не обробляє помилку самостійно.
Вона передає її вище до свого викликача.

Це корисно тоді, коли нижчий рівень має повідомити про помилку, а рішення про
обробку має приймати вищий рівень.

</details>

<details>
<summary>71. Що таке property wrappers?</summary>

#### Swift

Property wrappers — це можливість Swift, яка дозволяє додавати повторно
використовувану поведінку навколо stored properties.

Вони оголошуються через `@propertyWrapper`.

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

Property wrappers корисні для:

- Валідації
- Форматування
- Персистентності
- Dependency injection

</details>

<details>
<summary>72. Що таке opaque return types (`some`)?</summary>

#### Swift

Opaque return types дозволяють функції повертати значення певного типу, не
розкриваючи точний конкретний тип у API.

Для цього використовується ключове слово `some`.

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Той, хто викликає функцію, знає, що повернуте значення відповідає `View`, але
не зобов'язаний знати його конкретний тип.

Opaque types широко використовуються у SwiftUI.

</details>

<details>
<summary>73. У чому різниця між opaque types і generics?</summary>

#### Swift

І opaque types, і generics працюють з абстрактними типами, але вони розв'язують
різні задачі.

| Властивість | Generics | Opaque types |
| --- | --- | --- |
| Хто обирає конкретний тип? | Викликаючий код | Реалізація |
| Синтаксис | `<T>` | `some Protocol` |
| Основне призначення | Гнучкі повторно використовувані API | Приховування конкретних return types |

#### Приклад generic

```swift
func echo<T>(_ value: T) -> T {
    value
}
```

#### Приклад opaque type

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Використовуйте generics, коли тип задає викликаючий код.
Використовуйте opaque types, коли конкретний тип визначає реалізація, але
приховує його.

</details>

<details>
<summary>74. Що таке result builders?</summary>

#### Swift

Result builders — це можливість Swift, яка дозволяє будувати складні значення з
блоку декларативного коду.

Вони активно використовуються у SwiftUI.

```swift
@resultBuilder
struct StringBuilder {
    static func buildBlock(_ components: String...) -> String {
        components.joined(separator: " ")
    }
}
```

Result builder перетворює кілька виразів в один фінальний результат.

Це корисно для API у стилі DSL.

</details>

<details>
<summary>75. Що таке custom operators?</summary>

#### Swift

Custom operators дозволяють визначати власні оператори у Swift.

```swift
infix operator +++

func +++ (lhs: Int, rhs: Int) -> Int {
    lhs + rhs + 1
}
```

Можна створювати:

- Prefix operators
- Infix operators
- Postfix operators

Вони можуть бути потужним інструментом, але використовувати їх треба обережно.

Якщо їх забагато, код стає важчим для читання.

</details>

<details>
<summary>76. Що таке dynamic dispatch vs static dispatch?</summary>

#### Swift

Dispatch — це спосіб, у який Swift вирішує, яку саме реалізацію методу
викликати.

#### Static dispatch

Виклик методу визначається під час компіляції.
Зазвичай це швидше.

Це часто трапляється з:

- `struct`
- `enum`
- `final` methods

#### Dynamic dispatch

Виклик методу визначається під час виконання.
Це гнучкіше, але має більші накладні витрати.

Це часто трапляється з:

- Classes з наслідуванням
- `@objc dynamic`

Static dispatch орієнтується на продуктивність.
Dynamic dispatch орієнтується на runtime-гнучкість.

</details>

<details>
<summary>77. Що таке phantom type?</summary>

#### Swift

Phantom type — це generic type parameter, який використовується лише на етапі
компіляції і не зберігається під час виконання.

Він допомагає зробити API безпечнішими, кодувавши додаткову інформацію про тип
у type system.

```swift
struct ID<Tag> {
    let value: String
}

enum UserTag {}
enum OrderTag {}

let userID = ID<UserTag>(value: "123")
let orderID = ID<OrderTag>(value: "123")
```

Хоча обидва значення містять `String`, Swift розглядає їх як різні типи.

</details>

<details>
<summary>78. Що таке escape analysis?</summary>

#### Swift

Escape analysis — це концепція оптимізації компілятора, яка визначає, чи
значення або closure виходить за межі області, у якій воно було створене.

Якщо щось не виходить за межі області, Swift може ефективніше оптимізувати
використання пам'яті й поведінку викликів.

Ця концепція пов'язана з:

- Escaping vs non-escaping closures
- Рішеннями stack vs heap optimization

У повсякденних Swift-співбесідах зазвичай достатньо знати, що non-escaping
closures компілятору легше оптимізувати.

</details>

<details>
<summary>79. Що таке function builder (result builder)?</summary>

#### Swift

Function builder — це стара назва того, що Swift тепер називає result builder.

Це механізм, який перетворює блок виразів в один підсумковий результат, часто
для декларативних API.

SwiftUI активно використовує це у view-building syntax.

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

Отже, сьогодні:

- `function builder` — старіший термін
- `result builder` — поточний офіційний термін

</details>

<details>
<summary>80. Що таке SwiftUI і чим він відрізняється від UIKit?</summary>

#### Swift

SwiftUI — це декларативний UI-фреймворк Apple для побудови інтерфейсів на
платформах Apple.

UIKit — це старіший імперативний фреймворк для побудови iOS-інтерфейсів.

| Властивість | SwiftUI | UIKit |
| --- | --- | --- |
| Стиль | Декларативний | Імперативний |
| Оновлення UI | Керуються станом | Ручні оновлення |
| Синтаксис | Swift-based DSL | Classes і lifecycle APIs |
| Типове використання | Сучасна розробка UI для Apple | Зрілий фреймворк для iOS UI |

#### Приклад SwiftUI

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
    }
}
```

#### Приклад UIKit

```swift
let label = UILabel()
label.text = "Hello"
```

SwiftUI зазвичай дає швидшу розробку UI і кращу інтеграцію з сучасними
можливостями Swift.
UIKit дає нижчорівневий контроль і має більшу legacy-екосистему.

</details>

<details>
<summary>81. Що таке declarative UI?</summary>

#### Swift

Declarative UI означає, що ви описуєте, яким має бути інтерфейс для певного
стану, замість того щоб покроково вказувати, як саме його оновлювати.

У SwiftUI ви описуєте інтерфейс на основі даних, а фреймворк оновлює екран,
коли стан змінюється.

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

Це відрізняється від imperative UI, де ви вручну створюєте views і прямо
змінюєте їх.

</details>

<details>
<summary>82. Що таке @State?</summary>

#### Swift

`@State` — це property wrapper у SwiftUI, який використовується для зберігання
локального mutable state всередині view.

Коли значення `@State` змінюється, SwiftUI повторно рендерить view.

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

Використовуйте `@State` для простого стану, яким володіє саме view.

</details>

<details>
<summary>83. Що таке @StateObject vs @ObservedObject?</summary>

#### Swift

Обидва використовуються з observable reference types, але відрізняються
володінням.

| Wrapper | Володіння |
| --- | --- |
| `@StateObject` | View створює і володіє об'єктом |
| `@ObservedObject` | Об'єкт створений деінде і передається у view |

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

Використовуйте `@StateObject`, коли view має утримувати об'єкт живим.
Використовуйте `@ObservedObject`, коли view лише спостерігає за зовнішнім
об'єктом.

</details>

<details>
<summary>84. Що таке @EnvironmentObject?</summary>

#### Swift

`@EnvironmentObject` використовується для спільного доступу до observable object
через ієрархію SwiftUI views без ручної передачі його через кожне view.

```swift
class AppState: ObservableObject {
    @Published var isLoggedIn = false
}

struct ContentView: View {
    @EnvironmentObject var appState: AppState
}
```

Це корисно для спільного app-wide state, такого як:

- User session
- Theme
- Settings

Об'єкт має бути доданий в environment до того, як view почне його
використовувати.

</details>

<details>
<summary>85. Що таке @Published?</summary>

#### Swift

`@Published` — це property wrapper, який використовується всередині
`ObservableObject`.

Коли властивість змінюється, він повідомляє SwiftUI або інших підписників про
те, що об'єкт змінився.

```swift
class UserViewModel: ObservableObject {
    @Published var name = "Alice"
}
```

`@Published` часто використовується для стану view model, який має оновлювати
UI.

</details>

<details>
<summary>86. Як працює state management у SwiftUI?</summary>

#### Swift

State management у SwiftUI базується на тому, що UI керується даними.

Коли стан змінюється, SwiftUI перераховує affected views.

Поширені інструменти:

- `@State` для локального стану view
- `@StateObject` для observable objects, якими володіє view
- `@ObservedObject` для зовнішніх observable objects
- `@EnvironmentObject` для спільних app-wide objects
- `@Binding` для передачі mutable state між views

Ключова ідея проста:

- Стан змінюється
- SwiftUI оновлює ієрархію views

</details>

<details>
<summary>87. Що таке ViewModifier?</summary>

#### Swift

`ViewModifier` — це повторно використовуваний спосіб застосувати стилізацію або
поведінку до SwiftUI views.

```swift
struct TitleStyle: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.title)
            .foregroundColor(.blue)
    }
}
```

Використання:

```swift
Text("Hello").modifier(TitleStyle())
```

View modifiers допомагають не повторювати однакову логіку стилізації views.

</details>

<details>
<summary>88. Що таке SwiftUI environment?</summary>

#### Swift

SwiftUI environment — це система для неявної передачі значень вниз по ієрархії
views.

Вона надає спільний контекст, наприклад:

- Color scheme
- Locale
- Size category
- Custom environment values

Environment values читаються через `@Environment`.

```swift
struct ContentView: View {
    @Environment(\.colorScheme) var colorScheme
}
```

Environment допомагає уникати ручної передачі спільної конфігурації через
велику кількість шарів views.

</details>

<details>
<summary>89. Що таке GeometryReader?</summary>

#### Swift

`GeometryReader` — це SwiftUI container, який дає доступ до layout information
про доступний простір і геометрію view.

```swift
GeometryReader { geometry in
    Text("Width: \(geometry.size.width)")
}
```

Він корисний, коли вам потрібні:

- Динамічний layout залежно від доступного розміру
- Обчислення позицій
- Responsive UI behavior

Його слід використовувати обережно, бо надмірне використання може зробити
layout-код важчим для розуміння.

</details>

<details>
<summary>90. Як працює navigation у SwiftUI?</summary>

#### Swift

Navigation у SwiftUI зазвичай будується через `NavigationStack`.

Навігація відбувається шляхом додавання destination на стек.

```swift
NavigationStack {
    NavigationLink("Open Details") {
        DetailView()
    }
}
```

Також можна використовувати value-based navigation через
`navigationDestination`.

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

SwiftUI navigation керується станом і є більш декларативною, ніж navigation
controllers в UIKit.

</details>

<details>
<summary>91. Що таке lifecycle SwiftUI view?</summary>

#### Swift

SwiftUI views є value types, тому їхній lifecycle відрізняється від lifecycle
UIKit view controllers.

SwiftUI view часто створюється і перебудовується заново, коли змінюється стан.
Головна ідея тут не в житті самого `struct`, а в житті стану, який із ним
пов'язаний.

Поширені lifecycle hooks включають:

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

У SwiftUI стан і data flow важливіші за lifetime самого об'єкта.

</details>

<details>
<summary>92. Чому SwiftUI views є structs?</summary>

#### Swift

SwiftUI views є `struct`, тому що value types добре підходять для declarative
UI.

Переваги:

- Легковажність
- Простота повторного створення
- Безпечніший data flow
- Кращі можливості для оптимізації у SwiftUI

Оскільки це value types, SwiftUI може часто перебудовувати view values і
ефективно порівнювати їх під час зміни стану.

Справжні частини UI, що живуть довше, керуються самим фреймворком, а не
структурою view.

</details>

<details>
<summary>93. У чому різниця між UIKit і SwiftUI?</summary>

#### Swift

UIKit і SwiftUI — це обидва UI-фреймворки Apple, але вони використовують різні
підходи.

| Властивість | UIKit | SwiftUI |
| --- | --- | --- |
| Стиль | Імперативний | Декларативний |
| Основні будівельні блоки | `UIView`, `UIViewController` | `View` |
| Оновлення стану | Ручні | Керовані станом |
| Типове використання | Зрілий, нижчорівневий контроль UI | Сучасна декларативна розробка UI |

UIKit дає більше прямого контролю.
SwiftUI дає сучасніший і лаконічніший спосіб побудови UI.

</details>

<details>
<summary>94. Що таке Auto Layout?</summary>

#### Swift

Auto Layout — це система Apple для позиціонування та визначення розмірів
UI-елементів за допомогою constraints.

Замість того щоб вручну задавати frame для кожного розміру екрана, ви описуєте
правила того, як views пов'язані між собою.

Приклади:

- Label розташований на 16 points від лівого краю
- Button вирівняний по центру горизонтально
- Image має однакові ширину і висоту

Auto Layout допомагає будувати адаптивні інтерфейси для різних пристроїв і
розмірів екрана.

</details>

<details>
<summary>95. Що таке intrinsic content size?</summary>

#### Swift

Intrinsic content size — це природний розмір view, який воно віддає перевагу
на основі свого вмісту.

Наприклад:

- Label визначає свій розмір на основі тексту
- Image view визначає свій розмір на основі зображення

Це допомагає Auto Layout зрозуміти, яким має бути розмір view навіть без явно
заданих width і height constraints.

Views на кшталт `UILabel` і `UIButton` часто мають intrinsic content size.

</details>

<details>
<summary>96. Що таке constraints і anchors?</summary>

#### Swift

Constraints — це правила layout, які використовуються Auto Layout.
Anchors — це зручний для коду спосіб створювати ці constraints.

Поширені anchors:

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

Anchors роблять Auto Layout код безпечнішим і зрозумілішим, ніж старіші API
для роботи з constraints.

</details>

<details>
<summary>97. Що таке reusable cells?</summary>

#### Swift

Reusable cells — це cells для table view або collection view, які
перевикористовуються, а не створюються з нуля для кожного елемента.

Це покращує:

- Продуктивність
- Використання пам'яті
- Ефективність скролу

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
```

Reuse працює завдяки повторному використанню cells, які зникли з екрана, для
нового контенту.

</details>

<details>
<summary>98. У чому різниця між UITableView і UICollectionView?</summary>

#### Swift

Обидва відображають списки даних, але створені для різних layout-потреб.

| Властивість | `UITableView` | `UICollectionView` |
| --- | --- | --- |
| Стиль layout | Переважно вертикальний список | Гнучкі layouts |
| Складність | Простіший | Більш кастомізований |
| Типове використання | Прості списки, форми, settings | Сітки, кастомні layouts, складні списки |

Використовуйте `UITableView` для звичайних list-based UI.
Використовуйте `UICollectionView`, коли потрібні гнучкіші або кастомні layouts.

</details>

<details>
<summary>99. Що таке @IBOutlet vs @IBAction?</summary>

#### Swift

Обидва використовуються з Interface Builder у UIKit storyboards або XIB files.

- `@IBOutlet` з'єднує UI-елемент із кодом
- `@IBAction` з'єднує UI-подію з кодом

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

`@IBOutlet` використовується для посилань на UI-елементи.
`@IBAction` використовується для обробки дій користувача.

</details>

<details>
<summary>100. Що таке lifecycle UIViewController?</summary>

#### Swift

Lifecycle `UIViewController` — це послідовність методів, які викликаються,
коли view controller створюється, показується, проходить layout і зникає.

Поширені lifecycle methods:

1. `viewDidLoad`
2. `viewWillAppear`
3. `viewDidAppear`
4. `viewWillDisappear`
5. `viewDidDisappear`

#### Типові ролі

- `viewDidLoad`: початкове налаштування
- `viewWillAppear`: оновлення UI перед появою на екрані
- `viewDidAppear`: запуск анімацій або трекінгу
- `viewWillDisappear`: підготовка до виходу з екрана
- `viewDidDisappear`: cleanup-робота

Розуміння цього lifecycle є базово важливим для UIKit-розробки.

</details>

<details>
<summary>101. Що таке MVC?</summary>

#### Swift

MVC означає Model-View-Controller.

Це патерн проєктування, який розділяє застосунок на три частини:

- Model: дані та бізнес-логіка
- View: UI
- Controller: керує взаємодією між model і view

В iOS `UIViewController` часто виконує роль controller.

MVC є простим і поширеним, але в UIKit-застосунках легко може призвести до
"Massive View Controller", якщо в controller потрапляє забагато логіки.

</details>

<details>
<summary>102. Що таке MVVM?</summary>

#### Swift

MVVM означає Model-View-ViewModel.

Він розділяє відповідальність так:

- Model: дані та бізнес-правила
- View: UI
- ViewModel: presentation logic і стан для view

ViewModel готує дані для відображення і зменшує кількість логіки у view або
view controller.

MVVM популярний у SwiftUI і також часто використовується в UIKit-застосунках.

</details>

<details>
<summary>103. Що таке dependency injection?</summary>

#### Swift

Dependency injection означає передавати об'єкту залежності ззовні, замість того
щоб створювати їх усередині самого об'єкта.

Наприклад, замість того щоб view model створювала власний network service,
сервіс передається їй ззовні.

Переваги:

- Краща testability
- Нижча зв'язаність
- Простіша заміна реалізацій

</details>

<details>
<summary>104. Як реалізувати DI у Swift?</summary>

#### Swift

Найпоширеніший спосіб — constructor injection.

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

Інші поширені підходи:

- Property injection
- Method injection
- Dependency containers

Constructor injection зазвичай є кращим вибором, бо робить залежності явними.

</details>

<details>
<summary>105. Що таке delegation pattern?</summary>

#### Swift

Delegation — це патерн, у якому один об'єкт передає відповідальність за певну
роботу або події іншому об'єкту.

Зазвичай він реалізується через protocols.

```swift
protocol ButtonHandler: AnyObject {
    func didTapButton()
}
```

Delegation широко використовується в UIKit, наприклад з:

- `UITableViewDelegate`
- `UITextFieldDelegate`

Він допомагає тримати відповідальність розділеною, а взаємодію — гнучкою.

</details>

<details>
<summary>106. Коли варто використовувати singleton?</summary>

#### Swift

Singleton варто використовувати тоді, коли в застосунку має існувати рівно один
спільний екземпляр.

Типові приклади:

- App-wide configuration
- Logging service
- Cache manager

```swift
final class Logger {
    static let shared = Logger()

    private init() {}
}
```

Singleton слід використовувати обережно.
Надмірне використання створює приховані залежності та ускладнює тестування.

</details>

<details>
<summary>107. Що таке KVO?</summary>

#### Swift

KVO означає Key-Value Observing.

Це механізм для спостереження за змінами властивостей певних об'єктів, особливо
тих, що сумісні з Objective-C.

Він здебільшого пов'язаний із Cocoa та runtime-поведінкою Objective-C.

У сучасному Swift KVO використовується рідше, ніж:

- Combine
- `@Published`
- Інструменти стану у SwiftUI

Проте він усе ще трапляється в деяких UIKit і Foundation API.

</details>

<details>
<summary>108. Що таке NotificationCenter?</summary>

#### Swift

`NotificationCenter` — це система для широкомовної передачі повідомлень
кільком спостерігачам.

Один об'єкт публікує notification, а інші об'єкти можуть на неї підписатися.

```swift
NotificationCenter.default.post(name: .didLogout, object: nil)
```

Це корисно для слабко зв'язаної комунікації між частинами застосунку, особливо
коли прямі посилання небажані.

Використовуйте його обережно, бо надмірне використання ускладнює відстеження
data flow.

</details>

<details>
<summary>109. Як зробити network request у Swift?</summary>

#### Swift

Стандартний спосіб — використовувати `URLSession`.

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

У сучасному Swift також можна використовувати `async/await` разом із
`URLSession`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>110. Що таке Codable?</summary>

#### Swift

`Codable` — це type alias для:

- `Encodable`
- `Decodable`

Він дозволяє Swift-типам легко перетворюватися в формати на кшталт JSON і
назад.

```swift
struct User: Codable {
    let id: Int
    let name: String
}
```

Поширені варіанти використання:

- Парсинг API responses
- Збереження локальних даних
- Кодування request bodies

`Codable` значно зменшує кількість шаблонного коду для серіалізації.

</details>

<details>
<summary>111. Що таке decoding strategies?</summary>

#### Swift

Decoding strategies — це параметри, які використовує `JSONDecoder`, щоб
керувати тим, як декодуються вхідні дані.

Поширені strategies включають:

- `dateDecodingStrategy`
- `keyDecodingStrategy`
- `dataDecodingStrategy`

```swift
let decoder = JSONDecoder()
decoder.keyDecodingStrategy = .convertFromSnakeCase
decoder.dateDecodingStrategy = .iso8601
```

Вони корисні тоді, коли формат API напряму не збігається з форматом вашої Swift
model.

</details>

<details>
<summary>112. Що таке URLSession?</summary>

#### Swift

`URLSession` — це основний API Apple для виконання network requests.

Він використовується для:

- Завантаження даних
- Вивантаження даних
- Отримання файлів
- Керування network tasks

Він підтримує і completion-handler style, і `async/await`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>113. Що таке caching strategy?</summary>

#### Swift

Caching strategy — це план того, що саме кешувати, де це кешувати і коли
оновлювати або інвалідовувати кеш.

Поширені шари кешу в iOS-застосунках:

- In-memory cache
- Disk cache
- HTTP cache

Ключові рішення зазвичай включають:

- Час життя кешу
- Правила інвалідації
- Компроміси між пам'яттю і диском
- Компроміс між свіжістю даних і швидкістю

Хороша caching strategy покращує продуктивність, зменшує кількість мережевих
запитів і робить застосунок швидшим для користувача.

</details>

<details>
<summary>114. Як ви дебажите падіння застосунку?</summary>

#### Swift

Поширені способи дебагу crash включають:

1. Читання crash log
2. Перевірку stack trace
3. Локальне відтворення проблеми
4. Використання Xcode debugger і breakpoints
5. Використання crash reporting tools, наприклад Firebase Crashlytics

Важливо дивитися на:

- Потік, що впав
- Тип exception
- Останні викликані методи
- Версію пристрою й OS

Мета — відтворити crash, знайти root cause і підтвердити, що виправлення
спрацювало.

</details>

<details>
<summary>115. Як виявляти memory leaks?</summary>

#### Swift

Поширені способи виявлення memory leaks:

- Xcode Memory Graph Debugger
- Instruments Leaks tool
- Instruments Allocations
- Перевірка `deinit`

```swift
deinit {
    print("Object deallocated")
}
```

Якщо об'єкт мав би зникнути, але залишається в пам'яті, можливо, є retain cycle
або інше неочікуване strong reference.

</details>

<details>
<summary>116. Як покращити performance в iOS apps?</summary>

#### Swift

Поширені способи покращити performance:

- Зменшення роботи на main thread
- Оптимізація рендерингу і скролу
- Уникнення зайвих allocations
- Кешування дорогих результатів
- Використання background work для важких задач
- Профілювання через Instruments

Спочатку треба виміряти, а вже потім оптимізувати реальне вузьке місце.

Типові інструменти:

- Time Profiler
- Allocations
- Memory Graph
- Network instruments

</details>

<details>
<summary>117. Як оптимізувати використання батареї?</summary>

#### Swift

Щоб оптимізувати використання батареї, потрібно зменшувати зайву роботу і не
тримати апаратні ресурси або background tasks активними довше, ніж потрібно.

Поширені практики:

- Мінімізувати background activity
- Уникати надмірних оновлень локації
- Групувати network requests
- Зменшувати кількість частих таймерів і polling
- Уникати зайвих анімацій і перемальовувань

Головне правило просте:

- Робити менше роботи
- Робити її рідше

</details>

<details>
<summary>118. Що таке Keychain і коли його використовувати?</summary>

#### Swift

Keychain — це безпечне сховище Apple для невеликих чутливих фрагментів даних.

Використовуйте Keychain для таких даних, як:

- Tokens
- Passwords
- Credentials
- Чутливі секрети

Не використовуйте його як загальну базу даних.

Keychain безпечніший за `UserDefaults` для конфіденційних даних.

</details>

<details>
<summary>119. Що таке App Transport Security?</summary>

#### Swift

App Transport Security (ATS) — це security feature в iOS, яка за замовчуванням
вимагає безпечних мережевих з'єднань.

Зазвичай вона вимагає:

- HTTPS
- Strong TLS settings

Якщо застосунку потрібен небезпечний HTTP або слабші security settings,
потрібно явно додати винятки в конфігурацію застосунку.

ATS допомагає захищати мережевий трафік від перехоплення та небезпечного
транспорту.

</details>

<details>
<summary>120. Як безпечно зберігати дані?</summary>

#### Swift

Це залежить від чутливості даних.

Типові правила:

- Використовуйте Keychain для passwords, tokens і secrets
- Використовуйте file protection для чутливих файлів
- Не зберігайте secrets у plain text
- Не зберігайте конфіденційні дані в `UserDefaults`
- Шифруйте дані за потреби

Також важливо:

- Обмежувати обсяг того, що ви зберігаєте
- Зберігати дані лише стільки, скільки потрібно
- Захищати їх і в стані спокою, і під час передачі

</details>

<details>
<summary>121. Що таке XCTest?</summary>

#### Swift

`XCTest` — це testing framework від Apple для написання і запуску тестів у
Xcode.

Він використовується для:

- Unit tests
- UI tests
- Performance tests

```swift
func testAddition() {
    XCTAssertEqual(2 + 2, 4)
}
```

Це стандартний інструмент тестування для розробки під платформи Apple.

</details>

<details>
<summary>122. Що таке unit testing vs UI testing?</summary>

#### Swift

Unit testing перевіряє невеликі частини логіки ізольовано.
UI testing перевіряє застосунок через користувацький інтерфейс.

| Тип | Фокус |
| --- | --- |
| Unit test | Бізнес-логіка, функції, класи |
| UI test | Реальні користувацькі сценарії та взаємодії з екранами |

Unit tests зазвичай:

- Швидші
- Більш ізольовані
- Простіші для дебагу

UI tests корисні для перевірки наскрізної поведінки застосунку.

</details>

<details>
<summary>123. Що таке mocking?</summary>

#### Swift

Mocking означає заміну реальної залежності її тестовою фальшивою версією.

Це допомагає тестувати окрему одиницю коду ізольовано.

Наприклад, замість виклику реального API mock network service повертає
заздалегідь підготовлені дані.

Mocking корисний для:

- Швидших тестів
- Передбачуваних результатів
- Перевірки сценаріїв з помилками

</details>

<details>
<summary>124. Як ви залишаєтеся в курсі оновлень Swift?</summary>

#### Swift

Сильна відповідь тут — поєднувати офіційні джерела з практичним навчанням.

Поширені способи:

- Читати Swift Evolution proposals
- Дивитися сесії WWDC
- Читати документацію Apple
- Пробувати нові можливості мови у pet projects
- Стежити за поважними Swift та iOS engineers

Важливо не лише читати про оновлення, а й застосовувати їх у реальному коді.

</details>

<details>
<summary>125. Розкажіть про складну фічу, яку ви реалізували.</summary>

#### Swift

Хороша відповідь на співбесіді має будуватися так:

1. Коротко пояснити, що це була за фіча
2. Описати основні технічні виклики
3. Пояснити свої рішення і компроміси
4. Показати результат

#### Приклад структури відповіді

"Я реалізував offline-first синхронізацію для мобільного застосунку. Основними
викликами були розв'язання конфліктів, локальне зберігання даних, retry logic і
збереження чуйності UI під час синхронізації. Я поділив задачу на мережевий
шар, локальне сховище даних і шар orchestration для синхронізації. Також я
додав retry policies, обробку background sync і логування. У результаті
збільшилася відчутна швидкість роботи застосунку, покращилася надійність на
нестабільних мережах і зменшилася кількість звернень у підтримку."

Найкращі відповіді є конкретними і вимірюваними.

</details>

<details>
<summary>126. Як ви підходите до code review?</summary>

#### Swift

Сильний підхід до code review зосереджується спочатку на correctness, а потім
на maintainability.

Типові пріоритети:

- Bugs і edge cases
- Відповідність архітектурі та дизайну
- Читабельність
- Неймінг
- Покриття тестами
- Продуктивність і безпека, коли це релевантно

Хороший review має бути чітким, поважним і конкретним.

Мета не лише в тому, щоб знайти проблеми, а й у тому, щоб покращити якість
коду і поділитися знаннями.

</details>

<details>
<summary>127. Як ви проєктуєте scalable iOS architecture?</summary>

#### Swift

Scalable architecture — це про те, щоб фічі було легко розширювати, тестувати й
підтримувати в міру зростання застосунку.

Важливі принципи:

- Чітке розділення відповідальності
- Модульний дизайн
- Dependency injection
- Testable business logic
- Передбачуваний data flow

Scalable architecture має допомагати команді додавати нові фічі без постійного
переписування вже існуючого коду.

</details>

<details>
<summary>128. Які trade-offs ви враховуєте під час вибору архітектури?</summary>

#### Swift

Архітектура завжди пов'язана з trade-offs.

Поширені фактори:

- Розмір і досвід команди
- Складність застосунку
- Швидкість розробки
- Testability
- Maintainability
- Гнучкість для подальшого росту

Простому застосунку може не знадобитися важка архітектура.
Великий застосунок зазвичай виграє від кращого розділення, чіткіших меж і
кращого керування залежностями.

Найкращий вибір — це найпростіша архітектура, яка все ще добре відповідає
задачі.

</details>
