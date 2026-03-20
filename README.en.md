**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Swift <img src="./assets/swift.svg" width="40" height="40" />
</h1>

<h2>Most Popular Swift Interview Questions and Answers</h2>

<details>
<summary>1. What is Swift primarily used for in modern development?</summary>

#### Swift

Swift is primarily used to build applications for Apple's platforms:

- iOS
- macOS
- watchOS
- tvOS
- visionOS

It is mainly used for:

- Mobile app development
- Native Apple platform development
- Backend development with frameworks such as Vapor
- Command-line tools and scripts

Swift is valued for its safety, performance, and modern syntax.

</details>

<details>
<summary>2. What is the difference between `let` and `var`?</summary>

#### Swift

`let` creates a constant, and `var` creates a variable.

- Use `let` when the value should not change.
- Use `var` when the value may change later.

```swift
let name = "Alice"
var age = 25

age = 26 // Allowed
// name = "Bob" // Error
```

Using `let` by default makes code safer and easier to reason about.

</details>

<details>
<summary>3. Explain type inference in Swift.</summary>

#### Swift

Type inference means Swift can automatically determine the type of a value from
the assigned data, so you do not always need to write the type explicitly.

```swift
let title = "Swift"      // String
let year = 2025          // Int
let isActive = true      // Bool
```

You can still specify the type manually when you want clearer intent:

```swift
let score: Double = 99
```

Type inference makes code shorter while keeping it type-safe.

</details>

<details>
<summary>4. What are optionals and why are they important?</summary>

#### Swift

An optional is a type that can hold either:

- a value
- `nil`

Optionals are important because they make the absence of a value explicit and
help prevent runtime crashes caused by using missing data.

```swift
var nickname: String? = "Sam"
nickname = nil
```

Without optionals, Swift would not safely represent values that may be missing,
such as:

- User input
- Network response fields
- Database values
- URLs that may fail to initialize

</details>

<details>
<summary>5. Difference between optional binding and force unwrapping?</summary>

#### Swift

Optional binding safely extracts the value from an optional.
Force unwrapping extracts the value directly and crashes if the optional is
`nil`.

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

Use optional binding in most cases.
Use force unwrapping only when you are completely sure the value is not `nil`.

</details>

<details>
<summary>6. What is optional chaining and when to use it?</summary>

#### Swift

Optional chaining is a way to access properties, methods, or subscripts on an
optional value safely.

If the optional is `nil`, the whole expression returns `nil` instead of
crashing.

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

Use optional chaining when working with nested optional values, especially in:

- Model objects
- API responses
- UI references that may not exist

</details>

<details>
<summary>7. What is the nil coalescing operator?</summary>

#### Swift

The nil coalescing operator is `??`.
It provides a default value when an optional is `nil`.

```swift
let username: String? = nil
let displayName = username ?? "Guest"
```

In this example, `displayName` becomes `"Guest"`.

Use `??` when you want a fallback value for an optional.

</details>

<details>
<summary>8. What are tuples and when should you use them?</summary>

#### Swift

A tuple is a group of values combined into a single compound value.

```swift
let person = ("Alice", 28)
```

You can also name tuple values:

```swift
let httpResponse = (statusCode: 200, message: "OK")
print(httpResponse.statusCode)
```

Use tuples for short-lived grouped values, for example:

- Returning multiple values from a function
- Representing a small related data set
- Temporary local data

For more complex or reusable data, prefer `struct` or `class`.

</details>

<details>
<summary>9. What are the main collection types in Swift?</summary>

#### Swift

The main collection types in Swift are:

1. `Array`
2. `Set`
3. `Dictionary`

#### Array

Stores an ordered list of values.

```swift
let numbers = [1, 2, 3]
```

#### Set

Stores unique unordered values.

```swift
let uniqueNumbers: Set = [1, 2, 3]
```

#### Dictionary

Stores key-value pairs.

```swift
let userAges = ["Alice": 25, "Bob": 30]
```

These collections are used constantly in Swift development.

</details>

<details>
<summary>10. Difference between Array, Set, and Dictionary?</summary>

#### Swift

The difference is in how they store and access data.

| Type | Stores | Order | Uniqueness | Access |
| --- | --- | --- | --- | --- |
| `Array` | A list of values | Ordered | Duplicates allowed | By index |
| `Set` | Unique values | Unordered | Duplicates not allowed | By value lookup |
| `Dictionary` | Key-value pairs | Unordered | Keys must be unique | By key |

#### Example

```swift
let array = ["a", "b", "a"]
let set: Set = ["a", "b", "a"]
let dictionary = ["name": "Alice", "city": "Paris"]
```

- `Array` keeps order and can contain duplicates.
- `Set` removes duplicates.
- `Dictionary` maps keys to values.

</details>

<details>
<summary>11. What are value types vs reference types?</summary>

#### Swift

Value types are copied when assigned or passed around.
Reference types share the same instance.

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

Use value types by default unless shared mutable state is required.

</details>

<details>
<summary>12. Difference between struct and class?</summary>

#### Swift

The main difference is that `struct` is a value type and `class` is a reference
type.

| Feature | `struct` | `class` |
| --- | --- | --- |
| Type | Value type | Reference type |
| Copy behavior | Copied on assignment | Shared by reference |
| Inheritance | Not supported | Supported |
| Deinitializer | Not supported | Supported |
| Identity check | No | Yes with `===` |

Use `struct` in most cases.
Use `class` when you need:

- Shared mutable state
- Inheritance
- Identity semantics

</details>

<details>
<summary>13. What is copy-on-write?</summary>

#### Swift

Copy-on-write is an optimization where a value is not copied immediately.
Swift only creates a real copy when one of the values is modified.

This is commonly used by standard collections such as:

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

This gives value-type safety with good performance.

</details>

<details>
<summary>14. What is immutability and why is it important?</summary>

#### Swift

Immutability means a value cannot be changed after it is created.

In Swift, values declared with `let` are immutable.

```swift
let name = "Alice"
// name = "Bob" // Error
```

Immutability is important because it:

- Makes code safer
- Reduces bugs
- Makes state easier to track
- Helps reasoning about concurrency

Use immutable values by default, and make things mutable only when needed.

</details>

<details>
<summary>15. What are computed properties?</summary>

#### Swift

A computed property does not store a value directly.
Instead, it calculates the value every time it is accessed.

```swift
struct Rectangle {
    var width: Double
    var height: Double

    var area: Double {
        width * height
    }
}
```

Computed properties can also have `get` and `set`:

```swift
struct Square {
    var side: Double

    var area: Double {
        get { side * side }
        set { side = sqrt(newValue) }
    }
}
```

Use computed properties when a value depends on other values.

</details>

<details>
<summary>16. What are property observers (`willSet` / `didSet`)?</summary>

#### Swift

Property observers let you react when a stored property's value changes.

- `willSet` runs before the new value is stored
- `didSet` runs after the new value is stored

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

Use them when you need to:

- Log changes
- Update UI
- Trigger side effects after a value changes

</details>

<details>
<summary>17. What are lazy properties?</summary>

#### Swift

A lazy property is initialized only when it is used for the first time.

It is declared with the `lazy` keyword and must be a `var`.

```swift
class DataManager {
    lazy var formatter: DateFormatter = {
        let formatter = DateFormatter()
        formatter.dateStyle = .medium
        return formatter
    }()
}
```

Use lazy properties when:

- Initialization is expensive
- The property may never be used
- The property depends on `self` after initialization

</details>

<details>
<summary>18. What are key paths in Swift?</summary>

#### Swift

Key paths are type-safe references to properties.
They let you access a property indirectly.

```swift
struct User {
    let name: String
}

let keyPath = \User.name
let user = User(name: "Alice")

print(user[keyPath: keyPath]) // Alice
```

Key paths are useful for:

- Sorting
- Mapping
- Generic APIs
- Observing or accessing nested properties in a type-safe way

</details>

<details>
<summary>19. What is type casting (`is`, `as`, `as?`, `as!`)?</summary>

#### Swift

Type casting is used to check or convert a value's type at runtime.

- `is` checks whether a value is of a specific type
- `as` upcasts to a supertype
- `as?` safely downcasts and returns an optional
- `as!` force downcasts and crashes if it fails

```swift
class Animal {}
class Dog: Animal {}

let animal: Animal = Dog()

print(animal is Dog) // true

let dog1 = animal as? Dog // Safe
let dog2 = animal as! Dog // Unsafe if wrong type
```

Use `as?` in most cases.
Use `as!` only when failure is impossible.

</details>

<details>
<summary>20. Difference between `==` and `===`?</summary>

#### Swift

`==` checks value equality.
`===` checks reference identity.

#### `==`

Used to compare whether two values are equal.

```swift
let a = 5
let b = 5

print(a == b) // true
```

#### `===`

Used only with classes to check whether two references point to the same
instance.

```swift
class User {}

let user1 = User()
let user2 = user1
let user3 = User()

print(user1 === user2) // true
print(user1 === user3) // false
```

So:

- `==` means "same value"
- `===` means "same object in memory"

</details>

<details>
<summary>21. How does `switch` work in Swift (pattern matching)?</summary>

#### Swift

`switch` in Swift is powerful and supports pattern matching.
It can match:

- Exact values
- Multiple values
- Ranges
- Tuples
- Enum cases
- Values with conditions

Unlike some languages, `switch` in Swift must be exhaustive.
That means every possible case must be handled.

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

Swift `switch` is often used because it is safer and more expressive than a
long chain of `if` statements.

</details>

<details>
<summary>22. What is `fallthrough` and when should it be avoided?</summary>

#### Swift

`fallthrough` makes execution continue from one `case` to the next case in a
`switch`.

By default, Swift does not fall through automatically.

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

Output:

```swift
One
Two
```

Avoid `fallthrough` in most cases because it:

- Makes logic less clear
- Can cause unexpected behavior
- Usually has cleaner alternatives

Use it only when you intentionally want the next case to run as well.

</details>

<details>
<summary>23. What is a `guard` statement and when to use it?</summary>

#### Swift

`guard` is used for early exit.
It checks a condition, and if the condition fails, execution must leave the
current scope.

```swift
func printName(_ name: String?) {
    guard let name = name else {
        print("Name is missing")
        return
    }

    print(name)
}
```

Use `guard` when:

- A required value is missing
- Preconditions are not met
- You want to avoid deep nesting

It makes code flatter and easier to read.

</details>

<details>
<summary>24. Difference between `if let` and `guard let`?</summary>

#### Swift

Both are used for optional binding, but they are used differently.

| Feature | `if let` | `guard let` |
| --- | --- | --- |
| Main use | Conditional branch | Early exit |
| Scope of unwrapped value | Inside the `if` block | After the `guard` statement |
| Readability | Good for short checks | Better for required conditions |

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

Use `if let` for optional work inside a local branch.
Use `guard let` when the value is required for the rest of the function.

</details>

<details>
<summary>25. What is a half-open range?</summary>

#### Swift

A half-open range includes the lower bound but excludes the upper bound.

It uses `..<`

```swift
for i in 0..<5 {
    print(i)
}
```

Output:

```swift
0
1
2
3
4
```

Half-open ranges are useful for:

- Loops
- Array indexing
- Situations where the end value should not be included

</details>

<details>
<summary>26. What is a `where` clause?</summary>

#### Swift

A `where` clause adds an extra condition to a pattern, loop, generic
constraint, or `catch` block.

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

#### In loops

```swift
for number in 1...10 where number.isMultiple(of: 2) {
    print(number)
}
```

Use `where` when you want more precise matching or filtering.

</details>

<details>
<summary>27. What does `defer` do?</summary>

#### Swift

`defer` schedules code to run just before the current scope exits.

It runs no matter how the scope exits:

- Normal return
- Early return
- Error thrown

```swift
func performTask() {
    print("Start")

    defer {
        print("Cleanup")
    }

    print("Work")
}
```

Output:

```swift
Start
Work
Cleanup
```

`defer` is useful for cleanup tasks such as:

- Closing files
- Unlocking resources
- Resetting state

</details>

<details>
<summary>28. What are `break` and `continue`?</summary>

#### Swift

`break` stops the current loop or `switch`.
`continue` skips the current loop iteration and moves to the next one.

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

Use `break` to stop processing.
Use `continue` to skip one iteration.

</details>

<details>
<summary>29. What is `stride()` used for?</summary>

#### Swift

`stride()` is used to create sequences that move in steps.

It is useful when you do not want to increment by `1`.

#### Example with `through`

```swift
for number in stride(from: 0, through: 10, by: 2) {
    print(number)
}
```

#### Example with `to`

```swift
for number in stride(from: 0, to: 10, by: 2) {
    print(number)
}
```

Difference:

- `through` includes the end value if possible
- `to` excludes the end value

</details>

<details>
<summary>30. What are raw strings?</summary>

#### Swift

Raw strings let you write string literals without treating backslashes and
quotes as normal escape characters.

They use `#` around the string.

```swift
let path = #"C:\Users\Name\Documents"#
let text = #"He said "Hello""#
```

If you want interpolation inside a raw string, use `\#(...)`:

```swift
let name = "Alice"
let message = #"Hello, \#(name)"#
```

Raw strings are useful for:

- Regular expressions
- File paths
- JSON snippets
- Strings with many backslashes or quotes

</details>

<details>
<summary>31. What are closures in Swift?</summary>

#### Swift

Closures are self-contained blocks of code that can be passed around and
executed later.

They are similar to functions, but they can be stored in variables and capture
values from the surrounding scope.

```swift
let greet = { (name: String) in
    print("Hello, \(name)")
}

greet("Alice")
```

Closures are commonly used for:

- Callbacks
- Completion handlers
- Sorting
- Functional operations like `map` and `filter`

</details>

<details>
<summary>32. Escaping vs non-escaping closures?</summary>

#### Swift

A non-escaping closure is executed before the function returns.
An escaping closure can be stored and executed after the function returns.

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

Use non-escaping closures by default.
Use escaping closures for asynchronous work, callbacks, or stored closures.

</details>

<details>
<summary>33. What does `@escaping` mean?</summary>

#### Swift

`@escaping` means the closure may outlive the function it was passed into.

In other words, the closure is not guaranteed to execute before the function
returns.

```swift
class Downloader {
    var completion: (() -> Void)?

    func fetch(completion: @escaping () -> Void) {
        self.completion = completion
    }
}
```

`@escaping` is usually needed when the closure is:

- Stored in a property
- Executed asynchronously
- Passed to another function that stores it

</details>

<details>
<summary>34. What are trailing closures?</summary>

#### Swift

A trailing closure is a closure written after the function's parentheses.

This syntax is cleaner when the last argument is a closure.

```swift
func perform(action: () -> Void) {
    action()
}

perform {
    print("Done")
}
```

Trailing closures are common in:

- Async APIs
- UIKit and SwiftUI callbacks
- Collection operations

</details>

<details>
<summary>35. What is value capturing in closures?</summary>

#### Swift

Closures can capture values from the surrounding scope and keep using them even
after that scope would normally be gone.

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

Here, the closure captures `count` and keeps it alive.

This is useful, but it can also lead to memory issues if objects are captured
strongly by mistake.

</details>

<details>
<summary>36. How does Swift manage memory in closures?</summary>

#### Swift

Swift uses ARC (Automatic Reference Counting).
Closures are reference types, so they can capture objects strongly.

If a closure strongly captures `self`, and `self` strongly holds the closure, a
retain cycle can happen.

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

To avoid memory leaks, use capture lists when needed:

- `[weak self]` when `self` may become `nil`
- `[unowned self]` when `self` must still exist

</details>

<details>
<summary>37. What are higher-order functions (`map`, `filter`, `reduce`)?</summary>

#### Swift

Higher-order functions are functions that take other functions or closures as
arguments, or return them.

In Swift, common higher-order functions on collections are:

- `map`
- `filter`
- `reduce`

#### `map`

Transforms each element.

```swift
let numbers = [1, 2, 3]
let doubled = numbers.map { $0 * 2 }
```

#### `filter`

Keeps only matching elements.

```swift
let evenNumbers = numbers.filter { $0.isMultiple(of: 2) }
```

#### `reduce`

Combines all elements into one result.

```swift
let sum = numbers.reduce(0) { $0 + $1 }
```

These functions make code shorter and more expressive.

</details>

<details>
<summary>38. Difference between `map` and `compactMap`?</summary>

#### Swift

`map` transforms every element and keeps the same number of elements.
`compactMap` transforms elements and removes `nil` results.

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

Use `map` when all transformed results should stay in the output.
Use `compactMap` when you want to ignore failed conversions or `nil` values.

</details>

<details>
<summary>39. What is currying (conceptually)?</summary>

#### Swift

Currying is the idea of turning a function that takes multiple arguments into a
sequence of functions that each take one argument.

Conceptually:

```swift
func add(_ a: Int) -> (Int) -> Int {
    return { b in
        a + b
    }
}

let addFive = add(5)
print(addFive(3)) // 8
```

Currying is useful for:

- Partial application
- Reusable specialized functions
- Functional programming concepts

It is more of a concept than something used every day in typical Swift app
code.

</details>

<details>
<summary>40. What is `@autoclosure`?</summary>

#### Swift

`@autoclosure` automatically wraps an expression in a closure.

This lets you pass an expression where a closure is expected, without writing
the closure syntax manually.

```swift
func logIfTrue(_ condition: @autoclosure () -> Bool) {
    if condition() {
        print("True")
    }
}

logIfTrue(2 > 1)
```

Without `@autoclosure`, you would write:

```swift
logIfTrue({ 2 > 1 })
```

It is often used in APIs like `assert`.
Use it carefully, because it can hide the fact that a closure is being created.

</details>

<details>
<summary>41. What are generics and why are they useful?</summary>

#### Swift

Generics let you write flexible, reusable code that works with different types
while keeping type safety.

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

Here, `T` is a generic type placeholder.

Generics are useful because they:

- Reduce code duplication
- Keep strong type safety
- Make APIs more reusable

</details>

<details>
<summary>42. What are protocols?</summary>

#### Swift

A protocol defines a set of requirements that a type must follow.

It can require:

- Properties
- Methods
- Initializers

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

Protocols are used to define shared behavior without forcing inheritance.

</details>

<details>
<summary>43. What is protocol-oriented programming (POP)?</summary>

#### Swift

Protocol-oriented programming is an approach where behavior is built using
protocols and protocol extensions instead of relying mainly on class
inheritance.

In Swift, this is a core design style.

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

POP is useful because it:

- Encourages composition over inheritance
- Improves code reuse
- Works well with value types like `struct`

</details>

<details>
<summary>44. What are associated types?</summary>

#### Swift

An associated type is a placeholder type inside a protocol.

It lets the conforming type decide what concrete type will be used.

```swift
protocol Container {
    associatedtype Item
    var items: [Item] { get set }
}

struct IntContainer: Container {
    var items: [Int]
}
```

Associated types are useful when a protocol should work with different data
types, but still stay type-safe.

</details>

<details>
<summary>45. What is protocol composition?</summary>

#### Swift

Protocol composition means combining multiple protocols into a single type
requirement.

It uses `&`.

```swift
protocol Readable {}
protocol Writable {}

func process(file: Readable & Writable) {
    print("Can read and write")
}
```

Use protocol composition when a value must satisfy multiple behaviors at the
same time.

</details>

<details>
<summary>46. What are protocol extensions?</summary>

#### Swift

Protocol extensions let you add default implementations to protocols.

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

This means conforming types can get shared behavior automatically.

Protocol extensions are a key part of protocol-oriented programming.

</details>

<details>
<summary>47. What is conditional conformance?</summary>

#### Swift

Conditional conformance means a generic type conforms to a protocol only when
certain conditions are met.

```swift
extension Array: Equatable where Element: Equatable {}
```

This means `Array` is `Equatable` only if its elements are `Equatable`.

It is useful for building generic APIs that stay precise and type-safe.

</details>

<details>
<summary>48. What is type erasure?</summary>

#### Swift

Type erasure hides a specific concrete type behind a common wrapper or abstract
interface.

It is often needed when working with protocols that have:

- Associated types
- `Self` requirements

For example, SwiftUI uses `AnyView` as a type-erased wrapper.

```swift
let views: [AnyView] = [
    AnyView(Text("Hello")),
    AnyView(Image(systemName: "star"))
]
```

Type erasure helps store or pass values with different concrete types in a
uniform way.

</details>

<details>
<summary>49. What is the difference between `Self` and `self`?</summary>

#### Swift

`Self` and `self` are different.

- `Self` refers to the type itself
- `self` refers to the current instance

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

Use `self` when working with the current object or value.
Use `Self` when referring to the concrete type in a type-level way.

</details>

<details>
<summary>50. How does ARC work in Swift?</summary>

#### Swift

ARC stands for Automatic Reference Counting.

It is Swift's memory management system for class instances.
ARC automatically keeps track of how many strong references point to an object.

- When the reference count increases, the object stays in memory
- When the reference count drops to zero, the object is deallocated

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

ARC does not manage value types like `struct` and `enum` in the same way,
because they are not reference types.

The main ARC risk is a retain cycle, which is usually solved with `weak` or
`unowned` references.

</details>

<details>
<summary>51. What is a retain cycle?</summary>

#### Swift

A retain cycle happens when two or more reference-type objects hold strong
references to each other, so none of them can be deallocated.

This usually causes a memory leak.

```swift
class Person {
    var apartment: Apartment?
}

class Apartment {
    var tenant: Person?
}
```

If both references are strong, the objects keep each other alive.

Retain cycles are common with:

- Closures capturing `self`
- Parent-child object relationships
- Delegate patterns implemented incorrectly

</details>

<details>
<summary>52. Difference between `weak` and `unowned`?</summary>

#### Swift

Both `weak` and `unowned` are used to avoid retain cycles, but they behave
differently.

| Feature | `weak` | `unowned` |
| --- | --- | --- |
| Optional | Yes | No |
| Can become `nil` | Yes | No |
| Safety | Safer | Less safe |
| Use when | Referenced object may disappear | Referenced object must exist |

#### Example

```swift
weak var delegate: SomeDelegate?
unowned var owner: Owner
```

Use `weak` when the reference can become `nil`.
Use `unowned` when the reference should always point to a valid object.

</details>

<details>
<summary>53. When would you use `unowned` instead of `weak`?</summary>

#### Swift

Use `unowned` when the referenced object must always exist for as long as this
reference is used.

This is common when two objects are linked, but one clearly owns the lifetime
of the other.

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

Use `unowned` only when you are sure the reference will never be accessed after
the object is deallocated.

Otherwise, use `weak`.

</details>

<details>
<summary>54. What is a memory leak?</summary>

#### Swift

A memory leak happens when memory is no longer needed, but it is still not
released.

In Swift, this usually happens because objects are still strongly referenced,
often due to retain cycles.

Signs of a memory leak:

- Objects are never deallocated
- Memory usage keeps growing
- Screens or view models stay in memory after dismissal

Memory leaks can lead to:

- Higher memory usage
- Performance problems
- App termination by the system

</details>

<details>
<summary>55. How do you debug memory issues?</summary>

#### Swift

Common ways to debug memory issues in Swift are:

1. Xcode Memory Graph Debugger
2. Instruments with the Leaks tool
3. Instruments with Allocations
4. Checking whether `deinit` is called

#### Example

```swift
deinit {
    print("Deallocated")
}
```

If `deinit` is not called when expected, something is still retaining the
object.

A common workflow is:

- Reproduce the screen flow
- Dismiss the screen
- Check Memory Graph
- Look for retain cycles or unexpected strong references

</details>

<details>
<summary>56. How does Swift handle memory for value vs reference types?</summary>

#### Swift

Swift handles memory differently for value types and reference types.

#### Value types

- `struct`
- `enum`
- `tuple`

They are copied on assignment or when passed to functions.
They do not use ARC in the same way as class instances.

#### Reference types

- `class`

They are shared by reference.
Swift uses ARC to manage their lifetime.

So the main difference is:

- Value types copy data
- Reference types share the same instance

</details>

<details>
<summary>57. What is async/await in Swift?</summary>

#### Swift

`async/await` is Swift's modern syntax for asynchronous programming.

It makes async code look more like regular sequential code.

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

Benefits:

- Cleaner async code
- Better readability
- Easier error handling with `try`

</details>

<details>
<summary>58. What is structured concurrency?</summary>

#### Swift

Structured concurrency means asynchronous work is organized in a clear parent
and child task hierarchy.

This helps Swift manage:

- Lifetime of tasks
- Cancellation
- Error propagation

With structured concurrency, child tasks usually belong to the scope where they
were created and are not left running without control.

Common structured concurrency tools are:

- `async let`
- `TaskGroup`

It makes concurrent code safer and easier to reason about.

</details>

<details>
<summary>59. What are Tasks and Task groups?</summary>

#### Swift

A `Task` is a unit of asynchronous work.
A `TaskGroup` lets you run multiple child tasks in parallel and collect their
results.

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

Use:

- `Task` for one async operation
- `TaskGroup` for multiple parallel child tasks

</details>

<details>
<summary>60. What is `MainActor` and why is it important?</summary>

#### Swift

`MainActor` is a global actor that ensures code runs on the main thread.

It is important because UI updates must happen on the main thread.

```swift
@MainActor
class ViewModel {
    var title = ""

    func updateTitle() {
        title = "Updated"
    }
}
```

You can also switch to it explicitly:

```swift
await MainActor.run {
    print("Update UI")
}
```

`MainActor` helps prevent threading bugs and makes UI-related code safer.

</details>

<details>
<summary>61. What are actors and how do they prevent race conditions?</summary>

#### Swift

Actors are reference types that protect their mutable state from unsafe
concurrent access.

They help prevent race conditions by isolating state, so only one task can
access that mutable state at a time.

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

To access actor-isolated state from outside, you usually use `await`.

Actors are important in modern Swift concurrency because they provide a safer
alternative to manual locking for many cases.

</details>

<details>
<summary>62. What is data race and how does Swift prevent it?</summary>

#### Swift

A data race happens when multiple threads or tasks access the same mutable data
at the same time, and at least one of them writes to it.

This can cause unpredictable behavior and crashes.

Swift helps prevent data races with:

- Actor isolation
- `Sendable`
- Structured concurrency
- Main actor isolation for UI code

In modern Swift, concurrency features are designed to catch unsafe shared
mutable state earlier and make it easier to avoid.

</details>

<details>
<summary>63. Difference between GCD and modern concurrency?</summary>

#### Swift

GCD and modern Swift concurrency both handle asynchronous work, but they use
different models.

| Feature | GCD | Modern concurrency |
| --- | --- | --- |
| Style | Callback-based | `async/await` |
| Readability | More nested | More linear |
| Cancellation | Manual | Built-in support |
| Safety | Lower-level | Safer and more structured |
| Tools | `DispatchQueue` | `Task`, actors, `TaskGroup`, `MainActor` |

#### GCD example

```swift
DispatchQueue.global().async {
    print("Background work")
}
```

#### Modern concurrency example

```swift
Task {
    print("Async work")
}
```

Modern concurrency is usually preferred for new Swift code.

</details>

<details>
<summary>64. How do you synchronize access to shared state?</summary>

#### Swift

You synchronize shared state by making sure concurrent code does not read and
write the same mutable data unsafely.

Common approaches:

- Actors
- Serial queues
- Locks
- `MainActor` for UI state

#### Preferred modern approach

```swift
actor Store {
    private var items: [String] = []

    func add(_ item: String) {
        items.append(item)
    }
}
```

In modern Swift, actors are usually the safest default for shared mutable
state.

</details>

<details>
<summary>65. What is Sendable in Swift?</summary>

#### Swift

`Sendable` is a protocol that marks a type as safe to transfer across
concurrency domains.

This matters when values are passed between tasks or actors.

```swift
struct User: Sendable {
    let id: Int
    let name: String
}
```

Value types with immutable stored properties are often naturally `Sendable`.

`Sendable` helps Swift detect unsafe sharing of mutable state in concurrent
code.

</details>

<details>
<summary>66. How does error handling work in Swift?</summary>

#### Swift

Swift uses typed error handling with `throw`, `throws`, `do`, `try`, and
`catch`.

#### Example

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

This makes error handling explicit and safer than silently ignoring failures.

</details>

<details>
<summary>67. Difference between `try`, `try?`, `try!`?</summary>

#### Swift

All three are used with throwing functions, but they handle errors differently.

| Keyword | Behavior |
| --- | --- |
| `try` | Propagates or handles the error normally |
| `try?` | Converts the result to an optional and returns `nil` on error |
| `try!` | Forces success and crashes if an error is thrown |

#### Example

```swift
let value1 = try someThrowingFunction()
let value2 = try? someThrowingFunction()
let value3 = try! someThrowingFunction()
```

Use:

- `try` in normal error handling
- `try?` when failure can be ignored as `nil`
- `try!` only when failure is impossible

</details>

<details>
<summary>68. What is `throws` vs `rethrows`?</summary>

#### Swift

`throws` means a function can throw its own error.
`rethrows` means a function only throws if one of its function arguments throws.

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

Use `rethrows` for wrapper functions that do not throw by themselves, but call
a throwing closure.

</details>

<details>
<summary>69. What is the Result type?</summary>

#### Swift

`Result` is an enum that represents either:

- Success with a value
- Failure with an error

```swift
let result: Result<String, Error> = .success("Done")
```

It is defined roughly like this:

```swift
enum Result<Success, Failure: Error> {
    case success(Success)
    case failure(Failure)
}
```

`Result` is useful when you want to pass success or failure explicitly,
especially in callbacks or asynchronous APIs.

</details>

<details>
<summary>70. How do you propagate errors?</summary>

#### Swift

You propagate errors by marking a function with `throws` and using `try` when
calling another throwing function.

```swift
func loadData() throws {
    throw NSError(domain: "Example", code: 1)
}

func processData() throws {
    try loadData()
}
```

Here, `processData()` does not handle the error itself.
It passes the error up to its caller.

This is useful when a lower-level function should report failure and let a
higher-level layer decide how to handle it.

</details>

<details>
<summary>71. What are property wrappers?</summary>

#### Swift

Property wrappers are a Swift feature that lets you add reusable behavior around
stored properties.

They are declared with `@propertyWrapper`.

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

Property wrappers are useful for:

- Validation
- Formatting
- Persistence
- Dependency injection

</details>

<details>
<summary>72. What are opaque return types (`some`)?</summary>

#### Swift

Opaque return types let a function return a value of some specific type without
exposing that exact type in the API.

They use the `some` keyword.

```swift
func makeView() -> some View {
    Text("Hello")
}
```

The caller knows the returned value conforms to `View`, but does not need to
know the concrete type.

Opaque types are widely used in SwiftUI.

</details>

<details>
<summary>73. Difference between opaque types and generics?</summary>

#### Swift

Both opaque types and generics work with abstract types, but they solve
different problems.

| Feature | Generics | Opaque types |
| --- | --- | --- |
| Who chooses the concrete type? | Caller | Implementation |
| Syntax | `<T>` | `some Protocol` |
| Main use | Flexible reusable APIs | Hiding concrete return types |

#### Generic example

```swift
func echo<T>(_ value: T) -> T {
    value
}
```

#### Opaque type example

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Use generics when the caller provides the type.
Use opaque types when the implementation provides the type but hides it.

</details>

<details>
<summary>74. What are result builders?</summary>

#### Swift

Result builders are a feature that lets Swift build complex values from a block
of declarative code.

They are heavily used in SwiftUI.

```swift
@resultBuilder
struct StringBuilder {
    static func buildBlock(_ components: String...) -> String {
        components.joined(separator: " ")
    }
}
```

A result builder transforms multiple expressions into one final result.

This is useful for DSL-style APIs.

</details>

<details>
<summary>75. What are custom operators?</summary>

#### Swift

Custom operators let you define your own operators in Swift.

```swift
infix operator +++

func +++ (lhs: Int, rhs: Int) -> Int {
    lhs + rhs + 1
}
```

You can create:

- Prefix operators
- Infix operators
- Postfix operators

They can be powerful, but should be used carefully.

If overused, they make code harder to read.

</details>

<details>
<summary>76. What is dynamic dispatch vs static dispatch?</summary>

#### Swift

Dispatch is how Swift decides which method implementation to call.

#### Static dispatch

The method call is resolved at compile time.
It is usually faster.

This is common with:

- `struct`
- `enum`
- `final` methods

#### Dynamic dispatch

The method call is resolved at runtime.
It is more flexible, but has more overhead.

This is common with:

- Classes with inheritance
- `@objc dynamic`

Static dispatch focuses on performance.
Dynamic dispatch focuses on runtime flexibility.

</details>

<details>
<summary>77. What is phantom type?</summary>

#### Swift

A phantom type is a generic type parameter that is used only at compile time
and not stored at runtime.

It helps make APIs safer by encoding extra type information in the type system.

```swift
struct ID<Tag> {
    let value: String
}

enum UserTag {}
enum OrderTag {}

let userID = ID<UserTag>(value: "123")
let orderID = ID<OrderTag>(value: "123")
```

Even though both values contain a `String`, Swift treats them as different
types.

</details>

<details>
<summary>78. What is escape analysis?</summary>

#### Swift

Escape analysis is a compiler optimization concept used to determine whether a
value or closure escapes the scope where it was created.

If something does not escape, Swift may optimize memory usage and calling
behavior more efficiently.

This concept is related to:

- Escaping vs non-escaping closures
- Stack vs heap optimization decisions

In everyday Swift interviews, it is usually enough to know that non-escaping
closures are easier for the compiler to optimize.

</details>

<details>
<summary>79. What is function builder (result builder)?</summary>

#### Swift

A function builder is the old name for what Swift now calls a result builder.

It is a feature that transforms a block of expressions into a single result,
often for declarative APIs.

SwiftUI uses this heavily with view-building syntax.

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

So today:

- `function builder` is the older term
- `result builder` is the current official term

</details>

<details>
<summary>80. What is SwiftUI and how is it different from UIKit?</summary>

#### Swift

SwiftUI is Apple's declarative UI framework for building interfaces across
Apple platforms.

UIKit is the older imperative framework for building iOS interfaces.

| Feature | SwiftUI | UIKit |
| --- | --- | --- |
| Style | Declarative | Imperative |
| UI updates | State-driven | Manual updates |
| Syntax | Swift-based DSL | Classes and lifecycle APIs |
| Typical usage | Modern Apple UI development | Mature iOS UI framework |

#### SwiftUI example

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
    }
}
```

#### UIKit example

```swift
let label = UILabel()
label.text = "Hello"
```

SwiftUI usually gives faster UI development and better integration with modern
Swift features.
UIKit gives lower-level control and has a larger legacy ecosystem.

</details>

<details>
<summary>81. What is declarative UI?</summary>

#### Swift

Declarative UI means you describe what the UI should look like for a given
state, instead of writing step-by-step instructions for updating it.

In SwiftUI, you declare the interface based on data, and the framework updates
the screen when the state changes.

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

This is different from imperative UI, where you manually create views and
change them directly.

</details>

<details>
<summary>82. What is @State?</summary>

#### Swift

`@State` is a property wrapper used in SwiftUI to store local mutable state
inside a view.

When a `@State` value changes, SwiftUI re-renders the view.

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

Use `@State` for simple state owned by the view itself.

</details>

<details>
<summary>83. What is @StateObject vs @ObservedObject?</summary>

#### Swift

Both are used with observable reference types, but they differ in ownership.

| Wrapper | Ownership |
| --- | --- |
| `@StateObject` | The view creates and owns the object |
| `@ObservedObject` | The object is created elsewhere and passed into the view |

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

Use `@StateObject` when the view should keep the object alive.
Use `@ObservedObject` when the view just observes an external object.

</details>

<details>
<summary>84. What is @EnvironmentObject?</summary>

#### Swift

`@EnvironmentObject` is used to share an observable object through the SwiftUI
view hierarchy without passing it manually through each view.

```swift
class AppState: ObservableObject {
    @Published var isLoggedIn = false
}

struct ContentView: View {
    @EnvironmentObject var appState: AppState
}
```

It is useful for shared app-wide state such as:

- User session
- Theme
- Settings

The object must be injected into the environment before the view uses it.

</details>

<details>
<summary>85. What is @Published?</summary>

#### Swift

`@Published` is a property wrapper used inside an `ObservableObject`.

When the property changes, it notifies SwiftUI or other subscribers that the
object has changed.

```swift
class UserViewModel: ObservableObject {
    @Published var name = "Alice"
}
```

`@Published` is commonly used for view model state that should update the UI.

</details>

<details>
<summary>86. How does state management work in SwiftUI?</summary>

#### Swift

State management in SwiftUI is based on data driving the UI.

When state changes, SwiftUI recalculates the affected views.

Common tools:

- `@State` for local view state
- `@StateObject` for owned observable objects
- `@ObservedObject` for external observable objects
- `@EnvironmentObject` for shared app-wide objects
- `@Binding` for passing mutable state between views

The core idea is simple:

- State changes
- SwiftUI updates the view hierarchy

</details>

<details>
<summary>87. What is a ViewModifier?</summary>

#### Swift

A `ViewModifier` is a reusable way to apply styling or behavior to SwiftUI
views.

```swift
struct TitleStyle: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.title)
            .foregroundColor(.blue)
    }
}
```

Usage:

```swift
Text("Hello").modifier(TitleStyle())
```

View modifiers help avoid repeating the same view styling logic.

</details>

<details>
<summary>88. What is SwiftUI environment?</summary>

#### Swift

The SwiftUI environment is a system for passing values down the view hierarchy
implicitly.

It provides shared context such as:

- Color scheme
- Locale
- Size category
- Custom environment values

You read environment values with `@Environment`.

```swift
struct ContentView: View {
    @Environment(\.colorScheme) var colorScheme
}
```

The environment helps avoid manually passing common configuration through many
layers of views.

</details>

<details>
<summary>89. What is GeometryReader?</summary>

#### Swift

`GeometryReader` is a SwiftUI container that gives access to layout information
about the available space and view geometry.

```swift
GeometryReader { geometry in
    Text("Width: \(geometry.size.width)")
}
```

It is useful when you need:

- Dynamic layout based on available size
- Position calculations
- Responsive UI behavior

It should be used carefully, because excessive use can make layout code harder
to reason about.

</details>

<details>
<summary>90. How does navigation work in SwiftUI?</summary>

#### Swift

Navigation in SwiftUI is typically built with `NavigationStack`.

You navigate by pushing destinations onto a stack.

```swift
NavigationStack {
    NavigationLink("Open Details") {
        DetailView()
    }
}
```

You can also use value-based navigation with `navigationDestination`.

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

SwiftUI navigation is state-driven and more declarative than UIKit navigation
controllers.

</details>

<details>
<summary>91. What is lifecycle of a SwiftUI view?</summary>

#### Swift

SwiftUI views are value types, so their lifecycle is different from UIKit view
controllers.

A SwiftUI view is frequently created and recreated as state changes.
The important idea is not the lifetime of the struct itself, but the lifetime
of the state connected to it.

Common lifecycle hooks include:

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

In SwiftUI, state and data flow matter more than object lifetime.

</details>

<details>
<summary>92. Why are SwiftUI views structs?</summary>

#### Swift

SwiftUI views are structs because value types work well with declarative UI.

Benefits:

- Lightweight
- Easy to recreate
- Safer data flow
- Better performance opportunities for SwiftUI

Because they are value types, SwiftUI can rebuild view values often and compare
them efficiently as state changes.

The actual persistent parts of the UI are managed by the framework, not by the
view struct itself.

</details>

<details>
<summary>93. Difference between UIKit and SwiftUI?</summary>

#### Swift

UIKit and SwiftUI are both Apple UI frameworks, but they use different
approaches.

| Feature | UIKit | SwiftUI |
| --- | --- | --- |
| Style | Imperative | Declarative |
| Main building blocks | `UIView`, `UIViewController` | `View` |
| State updates | Manual | State-driven |
| Typical usage | Mature, lower-level UI control | Modern declarative UI development |

UIKit gives you more direct control.
SwiftUI gives you a more modern and concise way to build UI.

</details>

<details>
<summary>94. What is Auto Layout?</summary>

#### Swift

Auto Layout is Apple's system for positioning and sizing UI elements using
constraints.

Instead of manually setting frames for every screen size, you define rules about
how views relate to each other.

Examples:

- A label is 16 points from the left edge
- A button is centered horizontally
- An image keeps equal width and height

Auto Layout helps build adaptive interfaces for different devices and screen
sizes.

</details>

<details>
<summary>95. What is intrinsic content size?</summary>

#### Swift

Intrinsic content size is the natural size a view prefers based on its content.

For example:

- A label sizes itself based on its text
- An image view sizes itself based on the image

This helps Auto Layout know how large a view should be even without explicit
width and height constraints.

Views like `UILabel` and `UIButton` often have intrinsic content size.

</details>

<details>
<summary>96. What are constraints and anchors?</summary>

#### Swift

Constraints are layout rules used by Auto Layout.
Anchors are a code-friendly way to create those constraints.

Common anchors:

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

Anchors make Auto Layout code safer and easier to read than older constraint
APIs.

</details>

<details>
<summary>97. What are reusable cells?</summary>

#### Swift

Reusable cells are table view or collection view cells that are reused instead
of created from scratch for every item.

This improves:

- Performance
- Memory usage
- Scrolling efficiency

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
```

Reuse works by recycling off-screen cells for new content.

</details>

<details>
<summary>98. Difference between UITableView and UICollectionView?</summary>

#### Swift

Both display lists of data, but they are designed for different layout needs.

| Feature | `UITableView` | `UICollectionView` |
| --- | --- | --- |
| Layout style | Mostly vertical list | Flexible layouts |
| Complexity | Simpler | More customizable |
| Typical use | Simple lists, forms, settings | Grids, custom layouts, complex lists |

Use `UITableView` for straightforward list-based UI.
Use `UICollectionView` when you need more flexible or custom layouts.

</details>

<details>
<summary>99. What is @IBOutlet vs @IBAction?</summary>

#### Swift

Both are used with Interface Builder in UIKit storyboards or XIB files.

- `@IBOutlet` connects a UI element to code
- `@IBAction` connects a UI event to code

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

`@IBOutlet` is for references to UI elements.
`@IBAction` is for handling user actions.

</details>

<details>
<summary>100. What is UIViewController lifecycle?</summary>

#### Swift

`UIViewController` lifecycle is the sequence of methods called as a view
controller is created, shown, laid out, and removed.

Common lifecycle methods:

1. `viewDidLoad`
2. `viewWillAppear`
3. `viewDidAppear`
4. `viewWillDisappear`
5. `viewDidDisappear`

#### Example roles

- `viewDidLoad`: initial setup
- `viewWillAppear`: update UI before it becomes visible
- `viewDidAppear`: start animations or tracking
- `viewWillDisappear`: prepare to leave screen
- `viewDidDisappear`: cleanup work

Understanding this lifecycle is essential in UIKit app development.

</details>

<details>
<summary>101. What is MVC?</summary>

#### Swift

MVC stands for Model-View-Controller.

It is a design pattern that separates an app into three parts:

- Model: data and business logic
- View: UI
- Controller: handles interaction between model and view

In iOS, `UIViewController` often plays the controller role.

MVC is simple and common, but in UIKit apps it can easily lead to "Massive View
Controller" if too much logic is placed in the controller.

</details>

<details>
<summary>102. What is MVVM?</summary>

#### Swift

MVVM stands for Model-View-ViewModel.

It separates responsibilities like this:

- Model: data and business rules
- View: UI
- ViewModel: presentation logic and state for the view

The ViewModel prepares data for display and reduces logic inside the view or
view controller.

MVVM is popular in SwiftUI and also commonly used in UIKit apps.

</details>

<details>
<summary>103. What is dependency injection?</summary>

#### Swift

Dependency injection means giving an object the dependencies it needs from the
outside, instead of creating them inside the object.

For example, instead of a view model creating its own network service, the
service is passed into it.

Benefits:

- Better testability
- Lower coupling
- Easier replacement of implementations

</details>

<details>
<summary>104. How do you implement DI in Swift?</summary>

#### Swift

The most common way is constructor injection.

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

Other common approaches:

- Property injection
- Method injection
- Dependency containers

Constructor injection is usually preferred because it makes dependencies
explicit.

</details>

<details>
<summary>105. What is delegation pattern?</summary>

#### Swift

Delegation is a pattern where one object passes responsibility for some work or
events to another object.

It is commonly implemented with protocols.

```swift
protocol ButtonHandler: AnyObject {
    func didTapButton()
}
```

Delegation is widely used in UIKit, for example with:

- `UITableViewDelegate`
- `UITextFieldDelegate`

It helps keep responsibilities separated and communication flexible.

</details>

<details>
<summary>106. When should you use singleton?</summary>

#### Swift

A singleton should be used when there must be exactly one shared instance in
the app.

Typical examples:

- App-wide configuration
- Logging service
- Cache manager

```swift
final class Logger {
    static let shared = Logger()

    private init() {}
}
```

Use singletons carefully.
Overusing them can create hidden dependencies and make testing harder.

</details>

<details>
<summary>107. What is KVO?</summary>

#### Swift

KVO stands for Key-Value Observing.

It is a mechanism for observing changes to properties of certain objects,
especially Objective-C compatible ones.

It is mostly associated with Cocoa and Objective-C runtime behavior.

KVO is less commonly used in modern Swift code compared to:

- Combine
- `@Published`
- SwiftUI state tools

But it still appears in some UIKit and Foundation APIs.

</details>

<details>
<summary>108. What is NotificationCenter?</summary>

#### Swift

`NotificationCenter` is a system for broadcasting messages to multiple
observers.

One object posts a notification, and other objects can listen for it.

```swift
NotificationCenter.default.post(name: .didLogout, object: nil)
```

It is useful for loose communication between parts of the app, especially when
direct references are not ideal.

Use it carefully, because excessive use can make data flow harder to trace.

</details>

<details>
<summary>109. How do you make a network request in Swift?</summary>

#### Swift

The standard way is to use `URLSession`.

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

In modern Swift, you can also use `async/await` with `URLSession`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>110. What is Codable?</summary>

#### Swift

`Codable` is a type alias for:

- `Encodable`
- `Decodable`

It lets Swift types be easily converted to and from formats such as JSON.

```swift
struct User: Codable {
    let id: Int
    let name: String
}
```

Common use cases:

- Parsing API responses
- Saving local data
- Encoding request bodies

`Codable` greatly reduces boilerplate for serialization.

</details>

<details>
<summary>111. What are decoding strategies?</summary>

#### Swift

Decoding strategies are options used by `JSONDecoder` to control how incoming
data is decoded.

Common strategies include:

- `dateDecodingStrategy`
- `keyDecodingStrategy`
- `dataDecodingStrategy`

```swift
let decoder = JSONDecoder()
decoder.keyDecodingStrategy = .convertFromSnakeCase
decoder.dateDecodingStrategy = .iso8601
```

They are useful when the API format does not match your Swift model format
directly.

</details>

<details>
<summary>112. What is URLSession?</summary>

#### Swift

`URLSession` is Apple's main API for performing network requests.

It is used for:

- Downloading data
- Uploading data
- Fetching files
- Managing network tasks

It supports both completion-handler style and `async/await`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>113. What is caching strategy?</summary>

#### Swift

A caching strategy is the plan for what data to cache, where to cache it, and
when to refresh or invalidate it.

Common cache layers in iOS apps:

- In-memory cache
- Disk cache
- HTTP cache

Key decisions usually include:

- Cache lifetime
- Invalidation rules
- Memory vs disk trade-offs
- Freshness vs speed

A good caching strategy improves performance, reduces network usage, and makes
the app feel faster.

</details>

<details>
<summary>114. How do you debug crashes?</summary>

#### Swift

Common ways to debug crashes include:

1. Reading the crash log
2. Checking the stack trace
3. Reproducing the issue locally
4. Using Xcode debugger and breakpoints
5. Using crash reporting tools such as Firebase Crashlytics

Important things to look at:

- Crashed thread
- Exception type
- Last called methods
- Device and OS version

The goal is to reproduce the crash, identify the root cause, and confirm the
fix.

</details>

<details>
<summary>115. How do you detect memory leaks?</summary>

#### Swift

Common ways to detect memory leaks are:

- Xcode Memory Graph Debugger
- Instruments Leaks tool
- Instruments Allocations
- Checking `deinit`

```swift
deinit {
    print("Object deallocated")
}
```

If an object should disappear but stays in memory, there may be a retain cycle
or another unexpected strong reference.

</details>

<details>
<summary>116. How do you improve performance in iOS apps?</summary>

#### Swift

Common ways to improve performance include:

- Reducing main-thread work
- Optimizing rendering and scrolling
- Avoiding unnecessary allocations
- Caching expensive results
- Using background work for heavy tasks
- Profiling with Instruments

You should measure first, then optimize the real bottleneck.

Typical tools:

- Time Profiler
- Allocations
- Memory Graph
- Network instruments

</details>

<details>
<summary>117. How do you optimize battery usage?</summary>

#### Swift

To optimize battery usage, reduce unnecessary work and avoid keeping hardware
or background tasks active longer than needed.

Common practices:

- Minimize background activity
- Avoid excessive location updates
- Batch network requests
- Reduce frequent timers and polling
- Avoid unnecessary animations and redraws

The main rule is simple:

- Do less work
- Do it less often

</details>

<details>
<summary>118. What is Keychain and when to use it?</summary>

#### Swift

Keychain is Apple's secure storage system for sensitive small pieces of data.

Use Keychain for things like:

- Tokens
- Passwords
- Credentials
- Sensitive secrets

Do not use it as a general database.

Keychain is more secure than `UserDefaults` for confidential data.

</details>

<details>
<summary>119. What is App Transport Security?</summary>

#### Swift

App Transport Security (ATS) is an iOS security feature that encourages secure
network connections by default.

It generally requires:

- HTTPS
- Strong TLS settings

If an app needs insecure HTTP or weaker security settings, explicit exceptions
must be added in the app configuration.

ATS helps protect network traffic from interception and insecure transport.

</details>

<details>
<summary>120. How do you securely store data?</summary>

#### Swift

It depends on the sensitivity of the data.

Typical rules:

- Use Keychain for passwords, tokens, and secrets
- Use file protection for sensitive files
- Avoid storing secrets in plain text
- Do not store confidential data in `UserDefaults`
- Encrypt data when needed

Also important:

- Limit what you store
- Store it only as long as necessary
- Protect it both at rest and in transit

</details>

<details>
<summary>121. What is XCTest?</summary>

#### Swift

`XCTest` is Apple's testing framework for writing and running tests in Xcode.

It is used for:

- Unit tests
- UI tests
- Performance tests

```swift
func testAddition() {
    XCTAssertEqual(2 + 2, 4)
}
```

It is the standard testing tool for Apple platform development.

</details>

<details>
<summary>122. What is unit testing vs UI testing?</summary>

#### Swift

Unit testing checks small pieces of logic in isolation.
UI testing checks the app through the user interface.

| Type | Focus |
| --- | --- |
| Unit test | Business logic, functions, classes |
| UI test | Real user flows and screen interactions |

Unit tests are usually:

- Faster
- More isolated
- Easier to debug

UI tests are useful for validating end-to-end behavior.

</details>

<details>
<summary>123. What is mocking?</summary>

#### Swift

Mocking means replacing a real dependency with a fake test version.

This helps test a unit in isolation.

For example, instead of calling a real API, a mock network service returns
predefined data.

Mocking is useful for:

- Faster tests
- Predictable results
- Testing failure scenarios

</details>

<details>
<summary>124. How do you stay up to date with Swift?</summary>

#### Swift

A strong answer is to combine official sources with practical learning.

Common ways:

- Reading Swift Evolution proposals
- Following WWDC sessions
- Reading Apple documentation
- Trying new language features in side projects
- Following respected Swift and iOS engineers

The important part is not just reading updates, but applying them in real code.

</details>

<details>
<summary>125. Tell me about a complex feature you built.</summary>

#### Swift

A good interview answer should be structured like this:

1. Briefly explain the feature
2. Describe the main technical challenges
3. Explain your decisions and trade-offs
4. Show the outcome

#### Example answer structure

"I built an offline-first synchronization feature for a mobile app. The main
challenges were conflict resolution, local persistence, retry logic, and keeping
the UI responsive during sync. I split the problem into networking, local data
storage, and sync orchestration layers. I also added retry policies, background
sync handling, and logging. The result was faster perceived performance, better
reliability on unstable networks, and fewer support issues."

The best answers are concrete and measurable.

</details>

<details>
<summary>126. How do you approach code review?</summary>

#### Swift

A strong code review approach focuses on correctness first, then maintainability.

Typical priorities:

- Bugs and edge cases
- Architecture and design fit
- Readability
- Naming
- Test coverage
- Performance and security when relevant

A good review should be clear, respectful, and specific.

The goal is not only to find problems, but also to improve code quality and
share knowledge.

</details>

<details>
<summary>127. How do you design scalable iOS architecture?</summary>

#### Swift

Scalable architecture is about keeping features easy to extend, test, and
maintain as the app grows.

Important principles:

- Clear separation of concerns
- Modular design
- Dependency injection
- Testable business logic
- Predictable data flow

A scalable architecture should help teams add features without constantly
rewriting existing code.

</details>

<details>
<summary>128. What trade-offs do you consider when choosing architecture?</summary>

#### Swift

Architecture is always about trade-offs.

Common factors:

- Team size and experience
- App complexity
- Speed of development
- Testability
- Maintainability
- Flexibility for future growth

A simple app may not need a heavy architecture.
A large app usually benefits from stronger separation, clearer boundaries, and
better dependency management.

The best choice is the simplest architecture that still fits the problem well.

</details>
