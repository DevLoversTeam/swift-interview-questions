**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Swift <img src="./assets/swift.svg" width="40" height="40" />
</h1>

<h2>Las preguntas y respuestas más populares de entrevistas sobre Swift</h2>

<details>
<summary>1. ¿Para qué se utiliza principalmente Swift en el desarrollo moderno?</summary>

#### Swift

Swift se utiliza principalmente para crear aplicaciones para las plataformas de Apple:

- iOS
- macOS
- watchOS
- tvOS
- visionOS

Se utiliza sobre todo para:

- Desarrollo de aplicaciones móviles
- Desarrollo nativo para plataformas Apple
- Desarrollo backend con frameworks como Vapor
- Herramientas de línea de comandos y scripts

Swift es valorado por su seguridad, rendimiento y sintaxis moderna.

</details>

<details>
<summary>2. ¿Cuál es la diferencia entre `let` y `var`?</summary>

#### Swift

`let` crea una constante y `var` crea una variable.

- Usa `let` cuando el valor no debe cambiar.
- Usa `var` cuando el valor puede cambiar más adelante.

```swift
let name = "Alice"
var age = 25

age = 26 // Permitido
// name = "Bob" // Error
```

Usar `let` por defecto hace que el código sea más seguro y más fácil de entender.

</details>

<details>
<summary>3. Explica la inferencia de tipos en Swift.</summary>

#### Swift

La inferencia de tipos significa que Swift puede determinar automáticamente el
tipo de un valor a partir de los datos asignados, por lo que no siempre es
necesario escribir el tipo de forma explícita.

```swift
let title = "Swift"      // String
let year = 2025          // Int
let isActive = true      // Bool
```

También puedes especificar el tipo manualmente cuando quieras expresar una intención más clara:

```swift
let score: Double = 99
```

La inferencia de tipos hace que el código sea más corto sin perder seguridad de tipos.

</details>

<details>
<summary>4. ¿Qué son los optionals y por qué son importantes?</summary>

#### Swift

Un optional es un tipo que puede contener:

- un valor
- `nil`

Los optionals son importantes porque hacen explícita la ausencia de un valor y
ayudan a evitar crashes en tiempo de ejecución causados por datos faltantes.

```swift
var nickname: String? = "Sam"
nickname = nil
```

Sin los optionals, Swift no podría representar de forma segura valores que
pueden no existir, como por ejemplo:

- Entrada del usuario
- Campos de respuestas de red
- Valores de base de datos
- URLs cuya inicialización puede fallar

</details>

<details>
<summary>5. ¿Cuál es la diferencia entre optional binding y force unwrapping?</summary>

#### Swift

El optional binding extrae de forma segura el valor de un optional.
El force unwrapping extrae el valor directamente y provoca un crash si el optional es `nil`.

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

Usa optional binding en la mayoría de los casos.
Usa force unwrapping solo cuando estés completamente seguro de que el valor no es `nil`.

</details>

<details>
<summary>6. ¿Qué es optional chaining y cuándo se usa?</summary>

#### Swift

Optional chaining es una forma de acceder de manera segura a propiedades,
métodos o subscripts sobre un valor optional.

Si el optional es `nil`, toda la expresión devuelve `nil` en lugar de provocar un crash.

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

Usa optional chaining cuando trabajes con valores optional anidados, especialmente en:

- Objetos de modelo
- Respuestas de API
- Referencias de UI que pueden no existir

</details>

<details>
<summary>7. ¿Qué es el operador nil coalescing?</summary>

#### Swift

El operador nil coalescing es `??`.
Proporciona un valor por defecto cuando un optional es `nil`.

```swift
let username: String? = nil
let displayName = username ?? "Guest"
```

En este ejemplo, `displayName` pasa a ser `"Guest"`.

Usa `??` cuando quieras un valor de respaldo para un optional.

</details>

<details>
<summary>8. ¿Qué son las tuplas y cuándo deberías usarlas?</summary>

#### Swift

Una tupla es un grupo de valores combinados en un único valor compuesto.

```swift
let person = ("Alice", 28)
```

También puedes nombrar los valores de la tupla:

```swift
let httpResponse = (statusCode: 200, message: "OK")
print(httpResponse.statusCode)
```

Usa tuplas para valores agrupados de corta duración, por ejemplo:

- Devolver varios valores desde una función
- Representar un pequeño conjunto de datos relacionados
- Datos locales temporales

Para datos más complejos o reutilizables, es mejor usar `struct` o `class`.

</details>

<details>
<summary>9. ¿Cuáles son los principales tipos de colecciones en Swift?</summary>

#### Swift

Los principales tipos de colecciones en Swift son:

1. `Array`
2. `Set`
3. `Dictionary`

#### Array

Almacena una lista ordenada de valores.

```swift
let numbers = [1, 2, 3]
```

#### Set

Almacena valores únicos y no ordenados.

```swift
let uniqueNumbers: Set = [1, 2, 3]
```

#### Dictionary

Almacena pares clave-valor.

```swift
let userAges = ["Alice": 25, "Bob": 30]
```

Estas colecciones se usan constantemente en el desarrollo con Swift.

</details>

<details>
<summary>10. ¿Cuál es la diferencia entre Array, Set y Dictionary?</summary>

#### Swift

La diferencia está en cómo almacenan y cómo permiten acceder a los datos.

| Type | Stores | Order | Uniqueness | Access |
| --- | --- | --- | --- | --- |
| `Array` | A list of values | Ordered | Duplicates allowed | By index |
| `Set` | Unique values | Unordered | Duplicates not allowed | By value lookup |
| `Dictionary` | Key-value pairs | Unordered | Keys must be unique | By key |

#### Ejemplo

```swift
let array = ["a", "b", "a"]
let set: Set = ["a", "b", "a"]
let dictionary = ["name": "Alice", "city": "Paris"]
```

- `Array` mantiene el orden y puede contener duplicados.
- `Set` elimina duplicados.
- `Dictionary` asocia claves con valores.

</details>

<details>
<summary>11. ¿Qué son los value types frente a los reference types?</summary>

#### Swift

Los value types se copian cuando se asignan o se pasan de un lugar a otro.
Los reference types comparten la misma instancia.

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

Usa value types por defecto, salvo que necesites estado mutable compartido.

</details>

<details>
<summary>12. ¿Cuál es la diferencia entre `struct` y `class`?</summary>

#### Swift

La diferencia principal es que `struct` es un value type y `class` es un reference type.

| Feature | `struct` | `class` |
| --- | --- | --- |
| Type | Value type | Reference type |
| Copy behavior | Copied on assignment | Shared by reference |
| Inheritance | Not supported | Supported |
| Deinitializer | Not supported | Supported |
| Identity check | No | Yes with `===` |

Usa `struct` en la mayoría de los casos.
Usa `class` cuando necesites:

- Estado mutable compartido
- Herencia
- Semántica de identidad

</details>

<details>
<summary>13. ¿Qué es copy-on-write?</summary>

#### Swift

Copy-on-write es una optimización en la que un valor no se copia de inmediato.
Swift solo crea una copia real cuando uno de los valores se modifica.

Esto se usa habitualmente en colecciones estándar como:

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

Esto ofrece la seguridad de los value types con un buen rendimiento.

</details>

<details>
<summary>14. ¿Qué es la inmutabilidad y por qué es importante?</summary>

#### Swift

La inmutabilidad significa que un valor no puede cambiar después de crearse.

En Swift, los valores declarados con `let` son inmutables.

```swift
let name = "Alice"
// name = "Bob" // Error
```

La inmutabilidad es importante porque:

- Hace el código más seguro
- Reduce errores
- Facilita seguir el estado
- Ayuda a razonar sobre la concurrencia

Usa valores inmutables por defecto y hazlos mutables solo cuando sea necesario.

</details>

<details>
<summary>15. ¿Qué son las computed properties?</summary>

#### Swift

Una computed property no almacena un valor directamente.
En su lugar, calcula el valor cada vez que se accede a ella.

```swift
struct Rectangle {
    var width: Double
    var height: Double

    var area: Double {
        width * height
    }
}
```

Las computed properties también pueden tener `get` y `set`:

```swift
struct Square {
    var side: Double

    var area: Double {
        get { side * side }
        set { side = sqrt(newValue) }
    }
}
```

Usa computed properties cuando un valor dependa de otros valores.

</details>

<details>
<summary>16. ¿Qué son los property observers (`willSet` / `didSet`)?</summary>

#### Swift

Los property observers te permiten reaccionar cuando cambia el valor de una stored property.

- `willSet` se ejecuta antes de almacenar el nuevo valor
- `didSet` se ejecuta después de almacenar el nuevo valor

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

Úsalos cuando necesites:

- Registrar cambios
- Actualizar la UI
- Disparar efectos secundarios después de que cambie un valor

</details>

<details>
<summary>17. ¿Qué son las lazy properties?</summary>

#### Swift

Una lazy property se inicializa solo cuando se usa por primera vez.

Se declara con la palabra clave `lazy` y debe ser una `var`.

```swift
class DataManager {
    lazy var formatter: DateFormatter = {
        let formatter = DateFormatter()
        formatter.dateStyle = .medium
        return formatter
    }()
}
```

Usa lazy properties cuando:

- La inicialización es costosa
- La propiedad puede no llegar a usarse nunca
- La propiedad depende de `self` después de la inicialización

</details>

<details>
<summary>18. ¿Qué son los key paths en Swift?</summary>

#### Swift

Los key paths son referencias type-safe a propiedades.
Permiten acceder a una propiedad de forma indirecta.

```swift
struct User {
    let name: String
}

let keyPath = \User.name
let user = User(name: "Alice")

print(user[keyPath: keyPath]) // Alice
```

Los key paths son útiles para:

- Ordenar
- Mapear
- APIs genéricas
- Observar o acceder a propiedades anidadas de forma type-safe

</details>

<details>
<summary>19. ¿Qué es el type casting (`is`, `as`, `as?`, `as!`)?</summary>

#### Swift

El type casting se usa para comprobar o convertir el tipo de un valor en tiempo de ejecución.

- `is` comprueba si un valor es de un tipo concreto
- `as` hace upcast a un supertipo
- `as?` hace downcast seguro y devuelve un optional
- `as!` hace downcast forzado y provoca un crash si falla

```swift
class Animal {}
class Dog: Animal {}

let animal: Animal = Dog()

print(animal is Dog) // true

let dog1 = animal as? Dog // Safe
let dog2 = animal as! Dog // Unsafe if wrong type
```

Usa `as?` en la mayoría de los casos.
Usa `as!` solo cuando el fallo sea imposible.

</details>

<details>
<summary>20. ¿Cuál es la diferencia entre `==` y `===`?</summary>

#### Swift

`==` comprueba la igualdad de valor.
`===` comprueba la identidad de referencia.

#### `==`

Se usa para comparar si dos valores son iguales.

```swift
let a = 5
let b = 5

print(a == b) // true
```

#### `===`

Se usa solo con clases para comprobar si dos referencias apuntan a la misma instancia.

```swift
class User {}

let user1 = User()
let user2 = user1
let user3 = User()

print(user1 === user2) // true
print(user1 === user3) // false
```

Por tanto:

- `==` significa "mismo valor"
- `===` significa "mismo objeto en memoria"

</details>

<details>
<summary>21. ¿Cómo funciona `switch` en Swift (pattern matching)?</summary>

#### Swift

`switch` en Swift es potente y admite pattern matching.
Puede hacer match con:

- Valores exactos
- Múltiples valores
- Rangos
- Tuplas
- Casos de enum
- Valores con condiciones

A diferencia de algunos lenguajes, `switch` en Swift debe ser exhaustivo.
Eso significa que todos los casos posibles deben manejarse.

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

`switch` en Swift se usa con frecuencia porque es más seguro y expresivo que
una cadena larga de sentencias `if`.

</details>

<details>
<summary>22. ¿Qué es `fallthrough` y cuándo debería evitarse?</summary>

#### Swift

`fallthrough` hace que la ejecución continúe desde un `case` al siguiente
`case` dentro de un `switch`.

Por defecto, Swift no hace fall through automáticamente.

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

Salida:

```swift
One
Two
```

Evita `fallthrough` en la mayoría de los casos porque:

- Hace la lógica menos clara
- Puede causar comportamientos inesperados
- Normalmente tiene alternativas más limpias

Úsalo solo cuando realmente quieras que también se ejecute el siguiente caso.

</details>

<details>
<summary>23. ¿Qué es una sentencia `guard` y cuándo se usa?</summary>

#### Swift

`guard` se usa para salir temprano.
Comprueba una condición y, si la condición falla, la ejecución debe abandonar
el scope actual.

```swift
func printName(_ name: String?) {
    guard let name = name else {
        print("Name is missing")
        return
    }

    print(name)
}
```

Usa `guard` cuando:

- Falta un valor necesario
- No se cumplen las precondiciones
- Quieres evitar un anidamiento profundo

Hace que el código sea más plano y más fácil de leer.

</details>

<details>
<summary>24. ¿Cuál es la diferencia entre `if let` y `guard let`?</summary>

#### Swift

Ambos se usan para optional binding, pero se utilizan de forma distinta.

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

Usa `if let` para trabajo opcional dentro de una rama local.
Usa `guard let` cuando el valor sea necesario para el resto de la función.

</details>

<details>
<summary>25. ¿Qué es un half-open range?</summary>

#### Swift

Un half-open range incluye el límite inferior pero excluye el límite superior.

Usa `..<`

```swift
for i in 0..<5 {
    print(i)
}
```

Salida:

```swift
0
1
2
3
4
```

Los half-open ranges son útiles para:

- Bucles
- Indexación de arrays
- Situaciones en las que no debe incluirse el valor final

</details>

<details>
<summary>26. ¿Qué es una cláusula `where`?</summary>

#### Swift

Una cláusula `where` añade una condición extra a un patrón, un bucle, una
restricción genérica o un bloque `catch`.

#### En `switch`

```swift
let point = (2, 2)

switch point {
case let (x, y) where x == y:
    print("x equals y")
default:
    print("No match")
}
```

#### En bucles

```swift
for number in 1...10 where number.isMultiple(of: 2) {
    print(number)
}
```

Usa `where` cuando quieras un matching o un filtrado más preciso.

</details>

<details>
<summary>27. ¿Qué hace `defer`?</summary>

#### Swift

`defer` programa código para ejecutarse justo antes de que el scope actual termine.

Se ejecuta sin importar cómo termine el scope:

- Retorno normal
- Retorno anticipado
- Error lanzado

```swift
func performTask() {
    print("Start")

    defer {
        print("Cleanup")
    }

    print("Work")
}
```

Salida:

```swift
Start
Work
Cleanup
```

`defer` es útil para tareas de limpieza como:

- Cerrar archivos
- Liberar recursos bloqueados
- Restablecer estado

</details>

<details>
<summary>28. ¿Qué son `break` y `continue`?</summary>

#### Swift

`break` detiene el bucle actual o el `switch`.
`continue` omite la iteración actual del bucle y pasa a la siguiente.

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

Usa `break` para detener el procesamiento.
Usa `continue` para omitir una iteración.

</details>

<details>
<summary>29. ¿Para qué se usa `stride()`?</summary>

#### Swift

`stride()` se usa para crear secuencias que avanzan por pasos.

Es útil cuando no quieres incrementar de `1` en `1`.

#### Ejemplo con `through`

```swift
for number in stride(from: 0, through: 10, by: 2) {
    print(number)
}
```

#### Ejemplo con `to`

```swift
for number in stride(from: 0, to: 10, by: 2) {
    print(number)
}
```

Diferencia:

- `through` incluye el valor final si es posible
- `to` excluye el valor final

</details>

<details>
<summary>30. ¿Qué son los raw strings?</summary>

#### Swift

Los raw strings te permiten escribir literales de cadena sin tratar las barras
invertidas y las comillas como caracteres de escape normales.

Usan `#` alrededor de la cadena.

```swift
let path = #"C:\Users\Name\Documents"#
let text = #"He said "Hello""#
```

Si quieres interpolación dentro de un raw string, usa `\#(...)`:

```swift
let name = "Alice"
let message = #"Hello, \#(name)"#
```

Los raw strings son útiles para:

- Expresiones regulares
- Rutas de archivos
- Fragmentos JSON
- Cadenas con muchas barras invertidas o comillas

</details>

<details>
<summary>31. ¿Qué son los closures en Swift?</summary>

#### Swift

Los closures son bloques de código autocontenidos que pueden pasarse de un
lugar a otro y ejecutarse más tarde.

Son similares a las funciones, pero pueden almacenarse en variables y capturar
valores del scope que los rodea.

```swift
let greet = { (name: String) in
    print("Hello, \(name)")
}

greet("Alice")
```

Los closures se usan habitualmente para:

- Callbacks
- Completion handlers
- Ordenación
- Operaciones funcionales como `map` y `filter`

</details>

<details>
<summary>32. ¿Escaping vs non-escaping closures?</summary>

#### Swift

Un non-escaping closure se ejecuta antes de que la función retorne.
Un escaping closure puede almacenarse y ejecutarse después de que la función retorne.

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

Usa non-escaping closures por defecto.
Usa escaping closures para trabajo asíncrono, callbacks o closures almacenados.

</details>

<details>
<summary>33. ¿Qué significa `@escaping`?</summary>

#### Swift

`@escaping` significa que el closure puede sobrevivir a la función en la que fue pasado.

En otras palabras, no se garantiza que el closure se ejecute antes de que la
función retorne.

```swift
class Downloader {
    var completion: (() -> Void)?

    func fetch(completion: @escaping () -> Void) {
        self.completion = completion
    }
}
```

`@escaping` suele ser necesario cuando el closure:

- Se almacena en una propiedad
- Se ejecuta de forma asíncrona
- Se pasa a otra función que lo almacena

</details>

<details>
<summary>34. ¿Qué son los trailing closures?</summary>

#### Swift

Un trailing closure es un closure escrito después de los paréntesis de la función.

Esta sintaxis es más limpia cuando el último argumento es un closure.

```swift
func perform(action: () -> Void) {
    action()
}

perform {
    print("Done")
}
```

Los trailing closures son comunes en:

- APIs asíncronas
- Callbacks de UIKit y SwiftUI
- Operaciones sobre colecciones

</details>

<details>
<summary>35. ¿Qué es value capturing en closures?</summary>

#### Swift

Los closures pueden capturar valores del scope que los rodea y seguir usándolos
incluso después de que ese scope normalmente ya no exista.

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

Aquí, el closure captura `count` y lo mantiene vivo.

Esto es útil, pero también puede provocar problemas de memoria si se capturan
objetos fuertemente por error.

</details>

<details>
<summary>36. ¿Cómo gestiona Swift la memoria en los closures?</summary>

#### Swift

Swift usa ARC (Automatic Reference Counting).
Los closures son reference types, por lo que pueden capturar objetos con una referencia fuerte.

Si un closure captura fuertemente a `self`, y `self` mantiene fuertemente al closure,
puede producirse un retain cycle.

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

Para evitar memory leaks, usa capture lists cuando sea necesario:

- `[weak self]` cuando `self` pueda pasar a ser `nil`
- `[unowned self]` cuando `self` deba seguir existiendo

</details>

<details>
<summary>37. ¿Qué son las higher-order functions (`map`, `filter`, `reduce`)?</summary>

#### Swift

Las higher-order functions son funciones que reciben otras funciones o closures
como argumentos, o los devuelven.

En Swift, las higher-order functions más comunes sobre colecciones son:

- `map`
- `filter`
- `reduce`

#### `map`

Transforma cada elemento.

```swift
let numbers = [1, 2, 3]
let doubled = numbers.map { $0 * 2 }
```

#### `filter`

Mantiene solo los elementos que cumplen la condición.

```swift
let evenNumbers = numbers.filter { $0.isMultiple(of: 2) }
```

#### `reduce`

Combina todos los elementos en un solo resultado.

```swift
let sum = numbers.reduce(0) { $0 + $1 }
```

Estas funciones hacen que el código sea más corto y expresivo.

</details>

<details>
<summary>38. ¿Cuál es la diferencia entre `map` y `compactMap`?</summary>

#### Swift

`map` transforma cada elemento y mantiene el mismo número de elementos.
`compactMap` transforma elementos y elimina los resultados `nil`.

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

Usa `map` cuando todos los resultados transformados deban mantenerse en la salida.
Usa `compactMap` cuando quieras ignorar conversiones fallidas o valores `nil`.

</details>

<details>
<summary>39. ¿Qué es currying (conceptualmente)?</summary>

#### Swift

Currying es la idea de convertir una función que recibe varios argumentos en
una secuencia de funciones que reciben un argumento cada una.

Conceptualmente:

```swift
func add(_ a: Int) -> (Int) -> Int {
    return { b in
        a + b
    }
}

let addFive = add(5)
print(addFive(3)) // 8
```

Currying es útil para:

- Aplicación parcial
- Funciones especializadas reutilizables
- Conceptos de programación funcional

Es más un concepto que algo que se use todos los días en el código típico de aplicaciones Swift.

</details>

<details>
<summary>40. ¿Qué es `@autoclosure`?</summary>

#### Swift

`@autoclosure` envuelve automáticamente una expresión dentro de un closure.

Esto te permite pasar una expresión donde se espera un closure, sin escribir
manualmente la sintaxis del closure.

```swift
func logIfTrue(_ condition: @autoclosure () -> Bool) {
    if condition() {
        print("True")
    }
}

logIfTrue(2 > 1)
```

Sin `@autoclosure`, escribirías:

```swift
logIfTrue({ 2 > 1 })
```

Se usa con frecuencia en APIs como `assert`.
Úsalo con cuidado, porque puede ocultar el hecho de que se está creando un closure.

</details>

<details>
<summary>41. ¿Qué son los genéricos y por qué son útiles?</summary>

#### Swift

Los genéricos te permiten escribir código flexible y reutilizable que funciona
con distintos tipos manteniendo la seguridad de tipos.

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    let temp = a
    a = b
    b = temp
}
```

Aquí, `T` es un marcador de posición para un tipo genérico.

Los genéricos son útiles porque:

- Reducen la duplicación de código
- Mantienen una fuerte seguridad de tipos
- Hacen que las APIs sean más reutilizables

</details>

<details>
<summary>42. ¿Qué son los protocolos?</summary>

#### Swift

Un protocolo define un conjunto de requisitos que un tipo debe cumplir.

Puede requerir:

- Propiedades
- Métodos
- Inicializadores

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

Los protocolos se usan para definir comportamiento compartido sin forzar herencia.

</details>

<details>
<summary>43. ¿Qué es protocol-oriented programming (POP)?</summary>

#### Swift

Protocol-oriented programming es un enfoque en el que el comportamiento se
construye usando protocolos y extensiones de protocolos en lugar de depender
principalmente de la herencia de clases.

En Swift, este es un estilo de diseño central.

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

POP es útil porque:

- Fomenta la composición sobre la herencia
- Mejora la reutilización de código
- Funciona bien con value types como `struct`

</details>

<details>
<summary>44. ¿Qué son los associated types?</summary>

#### Swift

Un associated type es un tipo marcador de posición dentro de un protocolo.

Permite que el tipo que adopta el protocolo decida qué tipo concreto se usará.

```swift
protocol Container {
    associatedtype Item
    var items: [Item] { get set }
}

struct IntContainer: Container {
    var items: [Int]
}
```

Los associated types son útiles cuando un protocolo debe trabajar con distintos
tipos de datos, pero seguir siendo type-safe.

</details>

<details>
<summary>45. ¿Qué es protocol composition?</summary>

#### Swift

Protocol composition significa combinar varios protocolos en un único requisito de tipo.

Usa `&`.

```swift
protocol Readable {}
protocol Writable {}

func process(file: Readable & Writable) {
    print("Can read and write")
}
```

Usa protocol composition cuando un valor deba cumplir varios comportamientos al mismo tiempo.

</details>

<details>
<summary>46. ¿Qué son las protocol extensions?</summary>

#### Swift

Las protocol extensions te permiten añadir implementaciones por defecto a los protocolos.

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

Esto significa que los tipos conformes pueden obtener comportamiento compartido automáticamente.

Las protocol extensions son una parte clave de protocol-oriented programming.

</details>

<details>
<summary>47. ¿Qué es conditional conformance?</summary>

#### Swift

Conditional conformance significa que un tipo genérico conforma a un protocolo
solo cuando se cumplen ciertas condiciones.

```swift
extension Array: Equatable where Element: Equatable {}
```

Esto significa que `Array` es `Equatable` solo si sus elementos son `Equatable`.

Es útil para construir APIs genéricas que sigan siendo precisas y type-safe.

</details>

<details>
<summary>48. ¿Qué es type erasure?</summary>

#### Swift

Type erasure oculta un tipo concreto específico detrás de un wrapper común o
de una interfaz abstracta.

A menudo es necesario al trabajar con protocolos que tienen:

- Associated types
- Requisitos de `Self`

Por ejemplo, SwiftUI usa `AnyView` como un wrapper con type erasure.

```swift
let views: [AnyView] = [
    AnyView(Text("Hello")),
    AnyView(Image(systemName: "star"))
]
```

Type erasure ayuda a almacenar o pasar valores con distintos tipos concretos de una forma uniforme.

</details>

<details>
<summary>49. ¿Cuál es la diferencia entre `Self` y `self`?</summary>

#### Swift

`Self` y `self` son diferentes.

- `Self` se refiere al propio tipo
- `self` se refiere a la instancia actual

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

Usa `self` cuando trabajes con el objeto o valor actual.
Usa `Self` cuando te refieras al tipo concreto a nivel de tipo.

</details>

<details>
<summary>50. ¿Cómo funciona ARC en Swift?</summary>

#### Swift

ARC significa Automatic Reference Counting.

Es el sistema de gestión de memoria de Swift para instancias de clases.
ARC realiza un seguimiento automático de cuántas referencias fuertes apuntan a un objeto.

- Cuando el recuento de referencias aumenta, el objeto permanece en memoria
- Cuando el recuento de referencias baja a cero, el objeto se libera

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

ARC no gestiona value types como `struct` y `enum` de la misma manera,
porque no son reference types.

El principal riesgo de ARC es un retain cycle, que normalmente se resuelve con
referencias `weak` o `unowned`.

</details>

<details>
<summary>51. ¿Qué es un retain cycle?</summary>

#### Swift

Un retain cycle ocurre cuando dos o más objetos de tipo referencia mantienen
referencias fuertes entre sí, de modo que ninguno puede liberarse.

Esto normalmente causa un memory leak.

```swift
class Person {
    var apartment: Apartment?
}

class Apartment {
    var tenant: Person?
}
```

Si ambas referencias son fuertes, los objetos se mantienen vivos mutuamente.

Los retain cycles son comunes con:

- Closures que capturan `self`
- Relaciones padre-hijo entre objetos
- Delegate patterns implementados incorrectamente

</details>

<details>
<summary>52. ¿Cuál es la diferencia entre `weak` y `unowned`?</summary>

#### Swift

Tanto `weak` como `unowned` se usan para evitar retain cycles, pero se
comportan de forma distinta.

| Feature | `weak` | `unowned` |
| --- | --- | --- |
| Optional | Yes | No |
| Can become `nil` | Yes | No |
| Safety | Safer | Less safe |
| Use when | Referenced object may disappear | Referenced object must exist |

#### Ejemplo

```swift
weak var delegate: SomeDelegate?
unowned var owner: Owner
```

Usa `weak` cuando la referencia pueda convertirse en `nil`.
Usa `unowned` cuando la referencia siempre deba apuntar a un objeto válido.

</details>

<details>
<summary>53. ¿Cuándo usarías `unowned` en lugar de `weak`?</summary>

#### Swift

Usa `unowned` cuando el objeto referenciado deba existir siempre mientras se use esta referencia.

Esto es común cuando dos objetos están vinculados, pero uno posee claramente
el ciclo de vida del otro.

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

Usa `unowned` solo cuando estés seguro de que nunca se accederá a la referencia
después de que el objeto se haya liberado.

En caso contrario, usa `weak`.

</details>

<details>
<summary>54. ¿Qué es un memory leak?</summary>

#### Swift

Un memory leak ocurre cuando la memoria ya no es necesaria, pero aun así no se libera.

En Swift, esto suele ocurrir porque los objetos siguen teniendo referencias fuertes,
a menudo debido a retain cycles.

Señales de un memory leak:

- Los objetos nunca se liberan
- El uso de memoria sigue creciendo
- Pantallas o view models permanecen en memoria después de cerrarse

Los memory leaks pueden provocar:

- Mayor uso de memoria
- Problemas de rendimiento
- Terminación de la app por parte del sistema

</details>

<details>
<summary>55. ¿Cómo depuras problemas de memoria?</summary>

#### Swift

Las formas más comunes de depurar problemas de memoria en Swift son:

1. Xcode Memory Graph Debugger
2. Instruments con la herramienta Leaks
3. Instruments con Allocations
4. Comprobar si se llama a `deinit`

#### Ejemplo

```swift
deinit {
    print("Deallocated")
}
```

Si `deinit` no se llama cuando debería, algo sigue reteniendo el objeto.

Un flujo de trabajo habitual es:

- Reproducir el flujo de la pantalla
- Cerrar la pantalla
- Revisar Memory Graph
- Buscar retain cycles o referencias fuertes inesperadas

</details>

<details>
<summary>56. ¿Cómo gestiona Swift la memoria para value types frente a reference types?</summary>

#### Swift

Swift gestiona la memoria de forma diferente para value types y reference types.

#### Value types

- `struct`
- `enum`
- `tuple`

Se copian al asignarse o al pasarse a funciones.
No usan ARC de la misma manera que las instancias de clases.

#### Reference types

- `class`

Se comparten por referencia.
Swift usa ARC para gestionar su ciclo de vida.

Así que la diferencia principal es:

- Los value types copian datos
- Los reference types comparten la misma instancia

</details>

<details>
<summary>57. ¿Qué es async/await en Swift?</summary>

#### Swift

`async/await` es la sintaxis moderna de Swift para programación asíncrona.

Hace que el código asíncrono se parezca más a código secuencial normal.

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

Beneficios:

- Código asíncrono más limpio
- Mejor legibilidad
- Manejo de errores más sencillo con `try`

</details>

<details>
<summary>58. ¿Qué es structured concurrency?</summary>

#### Swift

Structured concurrency significa que el trabajo asíncrono se organiza en una
jerarquía clara de tareas padre e hijas.

Esto ayuda a Swift a gestionar:

- El ciclo de vida de las tareas
- La cancelación
- La propagación de errores

Con structured concurrency, las tareas hijas normalmente pertenecen al scope
donde se crearon y no quedan ejecutándose sin control.

Las herramientas comunes de structured concurrency son:

- `async let`
- `TaskGroup`

Hace que el código concurrente sea más seguro y más fácil de razonar.

</details>

<details>
<summary>59. ¿Qué son Tasks y Task groups?</summary>

#### Swift

Una `Task` es una unidad de trabajo asíncrono.
Un `TaskGroup` te permite ejecutar varias tareas hijas en paralelo y recoger sus resultados.

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

Usa:

- `Task` para una operación asíncrona
- `TaskGroup` para varias tareas hijas en paralelo

</details>

<details>
<summary>60. ¿Qué es `MainActor` y por qué es importante?</summary>

#### Swift

`MainActor` es un actor global que garantiza que el código se ejecute en el hilo principal.

Es importante porque las actualizaciones de UI deben hacerse en el hilo principal.

```swift
@MainActor
class ViewModel {
    var title = ""

    func updateTitle() {
        title = "Updated"
    }
}
```

También puedes cambiar a él explícitamente:

```swift
await MainActor.run {
    print("Update UI")
}
```

`MainActor` ayuda a evitar errores de threading y hace más seguro el código relacionado con la UI.

</details>

<details>
<summary>61. ¿Qué son los actors y cómo previenen race conditions?</summary>

#### Swift

Los actors son reference types que protegen su estado mutable frente a accesos
concurrentes inseguros.

Ayudan a prevenir race conditions aislando el estado, de modo que solo una
tarea puede acceder a ese estado mutable a la vez.

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

Para acceder al estado aislado por un actor desde fuera, normalmente se usa `await`.

Los actors son importantes en la concurrencia moderna de Swift porque ofrecen
una alternativa más segura que los locks manuales en muchos casos.

</details>

<details>
<summary>62. ¿Qué es un data race y cómo lo previene Swift?</summary>

#### Swift

Un data race ocurre cuando varios hilos o tareas acceden al mismo dato mutable
al mismo tiempo y al menos uno de ellos lo escribe.

Esto puede causar comportamiento impredecible y crashes.

Swift ayuda a prevenir data races con:

- Aislamiento por actors
- `Sendable`
- Structured concurrency
- Aislamiento del main actor para código de UI

En Swift moderno, las características de concurrencia están diseñadas para
detectar antes el estado mutable compartido inseguro y facilitar su prevención.

</details>

<details>
<summary>63. ¿Cuál es la diferencia entre GCD y la concurrencia moderna?</summary>

#### Swift

Tanto GCD como la concurrencia moderna de Swift manejan trabajo asíncrono,
pero usan modelos diferentes.

| Feature | GCD | Modern concurrency |
| --- | --- | --- |
| Style | Callback-based | `async/await` |
| Readability | More nested | More linear |
| Cancellation | Manual | Built-in support |
| Safety | Lower-level | Safer and more structured |
| Tools | `DispatchQueue` | `Task`, actors, `TaskGroup`, `MainActor` |

#### Ejemplo con GCD

```swift
DispatchQueue.global().async {
    print("Background work")
}
```

#### Ejemplo con concurrencia moderna

```swift
Task {
    print("Async work")
}
```

La concurrencia moderna suele ser la opción preferida para nuevo código Swift.

</details>

<details>
<summary>64. ¿Cómo sincronizas el acceso al estado compartido?</summary>

#### Swift

Sincronizas el estado compartido asegurándote de que el código concurrente no
lea y escriba los mismos datos mutables de forma insegura.

Enfoques comunes:

- Actors
- Colas seriales
- Locks
- `MainActor` para estado de UI

#### Enfoque moderno preferido

```swift
actor Store {
    private var items: [String] = []

    func add(_ item: String) {
        items.append(item)
    }
}
```

En Swift moderno, los actors suelen ser la opción más segura por defecto para
estado mutable compartido.

</details>

<details>
<summary>65. ¿Qué es Sendable en Swift?</summary>

#### Swift

`Sendable` es un protocolo que marca un tipo como seguro para transferirse
entre dominios de concurrencia.

Esto importa cuando se pasan valores entre tareas o actors.

```swift
struct User: Sendable {
    let id: Int
    let name: String
}
```

Los value types con propiedades almacenadas inmutables suelen ser
naturalmente `Sendable`.

`Sendable` ayuda a Swift a detectar el intercambio inseguro de estado mutable
en código concurrente.

</details>

<details>
<summary>66. ¿Cómo funciona el manejo de errores en Swift?</summary>

#### Swift

Swift usa manejo de errores tipado con `throw`, `throws`, `do`, `try` y `catch`.

#### Ejemplo

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

Esto hace que el manejo de errores sea explícito y más seguro que ignorar
fallos silenciosamente.

</details>

<details>
<summary>67. ¿Cuál es la diferencia entre `try`, `try?` y `try!`?</summary>

#### Swift

Los tres se usan con funciones que pueden lanzar errores, pero los manejan de forma distinta.

| Keyword | Behavior |
| --- | --- |
| `try` | Propagates or handles the error normally |
| `try?` | Converts the result to an optional and returns `nil` on error |
| `try!` | Forces success and crashes if an error is thrown |

#### Ejemplo

```swift
let value1 = try someThrowingFunction()
let value2 = try? someThrowingFunction()
let value3 = try! someThrowingFunction()
```

Usa:

- `try` para el manejo normal de errores
- `try?` cuando el fallo pueda ignorarse como `nil`
- `try!` solo cuando el fallo sea imposible

</details>

<details>
<summary>68. ¿Qué es `throws` frente a `rethrows`?</summary>

#### Swift

`throws` significa que una función puede lanzar su propio error.
`rethrows` significa que una función solo lanza si uno de sus argumentos
función lanza un error.

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

Usa `rethrows` para funciones wrapper que no lanzan por sí mismas, pero llaman
a un closure que sí puede lanzar.

</details>

<details>
<summary>69. ¿Qué es el tipo Result?</summary>

#### Swift

`Result` es un enum que representa:

- Éxito con un valor
- Fallo con un error

```swift
let result: Result<String, Error> = .success("Done")
```

Está definido aproximadamente así:

```swift
enum Result<Success, Failure: Error> {
    case success(Success)
    case failure(Failure)
}
```

`Result` es útil cuando quieres pasar explícitamente éxito o fallo,
especialmente en callbacks o APIs asíncronas.

</details>

<details>
<summary>70. ¿Cómo propagas errores?</summary>

#### Swift

Propagas errores marcando una función con `throws` y usando `try` al llamar a otra función que lanza errores.

```swift
func loadData() throws {
    throw NSError(domain: "Example", code: 1)
}

func processData() throws {
    try loadData()
}
```

Aquí, `processData()` no maneja el error por sí misma.
Pasa el error a quien la llama.

Esto es útil cuando una función de nivel inferior debe informar del fallo y
dejar que una capa de nivel superior decida cómo manejarlo.

</details>

<details>
<summary>71. ¿Qué son los property wrappers?</summary>

#### Swift

Los property wrappers son una característica de Swift que te permite añadir
comportamiento reutilizable alrededor de stored properties.

Se declaran con `@propertyWrapper`.

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

Los property wrappers son útiles para:

- Validación
- Formateo
- Persistencia
- Inyección de dependencias

</details>

<details>
<summary>72. ¿Qué son los opaque return types (`some`)?</summary>

#### Swift

Los opaque return types permiten que una función devuelva un valor de algún
tipo específico sin exponer ese tipo exacto en la API.

Usan la palabra clave `some`.

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Quien llama a la función sabe que el valor devuelto conforma a `View`, pero no
necesita conocer el tipo concreto.

Los opaque types se usan mucho en SwiftUI.

</details>

<details>
<summary>73. ¿Cuál es la diferencia entre opaque types y genéricos?</summary>

#### Swift

Tanto los opaque types como los genéricos trabajan con tipos abstractos, pero
resuelven problemas diferentes.

| Feature | Generics | Opaque types |
| --- | --- | --- |
| Who chooses the concrete type? | Caller | Implementation |
| Syntax | `<T>` | `some Protocol` |
| Main use | Flexible reusable APIs | Hiding concrete return types |

#### Ejemplo genérico

```swift
func echo<T>(_ value: T) -> T {
    value
}
```

#### Ejemplo de opaque type

```swift
func makeView() -> some View {
    Text("Hello")
}
```

Usa genéricos cuando el tipo lo proporcione quien llama.
Usa opaque types cuando el tipo lo proporcione la implementación, pero lo oculte.

</details>

<details>
<summary>74. ¿Qué son los result builders?</summary>

#### Swift

Los result builders son una característica que permite a Swift construir
valores complejos a partir de un bloque de código declarativo.

Se usan mucho en SwiftUI.

```swift
@resultBuilder
struct StringBuilder {
    static func buildBlock(_ components: String...) -> String {
        components.joined(separator: " ")
    }
}
```

Un result builder transforma varias expresiones en un único resultado final.

Esto es útil para APIs de estilo DSL.

</details>

<details>
<summary>75. ¿Qué son los custom operators?</summary>

#### Swift

Los custom operators te permiten definir tus propios operadores en Swift.

```swift
infix operator +++

func +++ (lhs: Int, rhs: Int) -> Int {
    lhs + rhs + 1
}
```

Puedes crear:

- Operadores prefix
- Operadores infix
- Operadores postfix

Pueden ser potentes, pero deben usarse con cuidado.

Si se abusa de ellos, el código se vuelve más difícil de leer.

</details>

<details>
<summary>76. ¿Qué es dynamic dispatch frente a static dispatch?</summary>

#### Swift

Dispatch es la forma en que Swift decide qué implementación de método llamar.

#### Static dispatch

La llamada al método se resuelve en tiempo de compilación.
Normalmente es más rápido.

Esto es común con:

- `struct`
- `enum`
- Métodos `final`

#### Dynamic dispatch

La llamada al método se resuelve en tiempo de ejecución.
Es más flexible, pero tiene más overhead.

Esto es común con:

- Clases con herencia
- `@objc dynamic`

Static dispatch se centra en el rendimiento.
Dynamic dispatch se centra en la flexibilidad en tiempo de ejecución.

</details>

<details>
<summary>77. ¿Qué es un phantom type?</summary>

#### Swift

Un phantom type es un parámetro de tipo genérico que se usa solo en tiempo de
compilación y no se almacena en tiempo de ejecución.

Ayuda a hacer las APIs más seguras codificando información extra en el sistema de tipos.

```swift
struct ID<Tag> {
    let value: String
}

enum UserTag {}
enum OrderTag {}

let userID = ID<UserTag>(value: "123")
let orderID = ID<OrderTag>(value: "123")
```

Aunque ambos valores contienen un `String`, Swift los trata como tipos diferentes.

</details>

<details>
<summary>78. ¿Qué es escape analysis?</summary>

#### Swift

Escape analysis es un concepto de optimización del compilador que se usa para
determinar si un valor o closure escapa del scope donde fue creado.

Si algo no escapa, Swift puede optimizar el uso de memoria y el comportamiento
de llamada de forma más eficiente.

Este concepto está relacionado con:

- Escaping vs non-escaping closures
- Decisiones de optimización entre stack y heap

En entrevistas habituales de Swift, normalmente basta con saber que los
non-escaping closures son más fáciles de optimizar para el compilador.

</details>

<details>
<summary>79. ¿Qué es function builder (result builder)?</summary>

#### Swift

Function builder es el nombre antiguo de lo que Swift ahora llama result builder.

Es una característica que transforma un bloque de expresiones en un único resultado,
a menudo para APIs declarativas.

SwiftUI usa esto intensamente con su sintaxis de construcción de vistas.

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

Así que hoy:

- `function builder` es el término antiguo
- `result builder` es el término oficial actual

</details>

<details>
<summary>80. ¿Qué es SwiftUI y en qué se diferencia de UIKit?</summary>

#### Swift

SwiftUI es el framework declarativo de Apple para construir interfaces en las
plataformas Apple.

UIKit es el framework imperativo más antiguo para construir interfaces en iOS.

| Feature | SwiftUI | UIKit |
| --- | --- | --- |
| Style | Declarative | Imperative |
| UI updates | State-driven | Manual updates |
| Syntax | Swift-based DSL | Classes and lifecycle APIs |
| Typical usage | Modern Apple UI development | Mature iOS UI framework |

#### Ejemplo de SwiftUI

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello")
    }
}
```

#### Ejemplo de UIKit

```swift
let label = UILabel()
label.text = "Hello"
```

SwiftUI suele ofrecer un desarrollo de UI más rápido y una mejor integración
con las características modernas de Swift.
UIKit ofrece un control de más bajo nivel y tiene un ecosistema legacy más grande.

</details>

<details>
<summary>81. ¿Qué es la UI declarativa?</summary>

#### Swift

La UI declarativa significa que describes cómo debe verse la interfaz para un
estado determinado, en lugar de escribir instrucciones paso a paso para actualizarla.

En SwiftUI, declaras la interfaz basándote en los datos, y el framework
actualiza la pantalla cuando cambia el estado.

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

Esto es diferente de la UI imperativa, donde creas vistas manualmente y las
modificas directamente.

</details>

<details>
<summary>82. ¿Qué es `@State`?</summary>

#### Swift

`@State` es un property wrapper usado en SwiftUI para almacenar estado mutable local dentro de una vista.

Cuando un valor `@State` cambia, SwiftUI vuelve a renderizar la vista.

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

Usa `@State` para estado simple que pertenece a la propia vista.

</details>

<details>
<summary>83. ¿Qué es `@StateObject` frente a `@ObservedObject`?</summary>

#### Swift

Ambos se usan con tipos referencia observables, pero se diferencian en la propiedad del objeto.

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

Usa `@StateObject` cuando la vista deba mantener vivo el objeto.
Usa `@ObservedObject` cuando la vista solo observe un objeto externo.

</details>

<details>
<summary>84. ¿Qué es `@EnvironmentObject`?</summary>

#### Swift

`@EnvironmentObject` se usa para compartir un objeto observable a través de la
jerarquía de vistas de SwiftUI sin pasarlo manualmente por cada vista.

```swift
class AppState: ObservableObject {
    @Published var isLoggedIn = false
}

struct ContentView: View {
    @EnvironmentObject var appState: AppState
}
```

Es útil para estado compartido a nivel de app, como:

- Sesión de usuario
- Tema
- Ajustes

El objeto debe inyectarse en el environment antes de que la vista lo use.

</details>

<details>
<summary>85. ¿Qué es `@Published`?</summary>

#### Swift

`@Published` es un property wrapper usado dentro de un `ObservableObject`.

Cuando la propiedad cambia, notifica a SwiftUI u otros suscriptores que el
objeto ha cambiado.

```swift
class UserViewModel: ObservableObject {
    @Published var name = "Alice"
}
```

`@Published` se usa habitualmente para estado de view model que debe actualizar la UI.

</details>

<details>
<summary>86. ¿Cómo funciona la gestión de estado en SwiftUI?</summary>

#### Swift

La gestión de estado en SwiftUI se basa en que los datos impulsan la UI.

Cuando el estado cambia, SwiftUI recalcula las vistas afectadas.

Herramientas comunes:

- `@State` para estado local de la vista
- `@StateObject` para objetos observables propios
- `@ObservedObject` para objetos observables externos
- `@EnvironmentObject` para objetos compartidos a nivel de app
- `@Binding` para pasar estado mutable entre vistas

La idea central es simple:

- El estado cambia
- SwiftUI actualiza la jerarquía de vistas

</details>

<details>
<summary>87. ¿Qué es un `ViewModifier`?</summary>

#### Swift

Un `ViewModifier` es una forma reutilizable de aplicar estilo o comportamiento
a vistas de SwiftUI.

```swift
struct TitleStyle: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.title)
            .foregroundColor(.blue)
    }
}
```

Uso:

```swift
Text("Hello").modifier(TitleStyle())
```

Los view modifiers ayudan a evitar repetir la misma lógica de estilo de vistas.

</details>

<details>
<summary>88. ¿Qué es el environment de SwiftUI?</summary>

#### Swift

El environment de SwiftUI es un sistema para pasar valores por la jerarquía de
vistas de forma implícita.

Proporciona contexto compartido como:

- Esquema de color
- Locale
- Categoría de tamaño
- Valores personalizados de environment

Lees valores del environment con `@Environment`.

```swift
struct ContentView: View {
    @Environment(\.colorScheme) var colorScheme
}
```

El environment ayuda a evitar pasar manualmente configuración común por muchas capas de vistas.

</details>

<details>
<summary>89. ¿Qué es `GeometryReader`?</summary>

#### Swift

`GeometryReader` es un contenedor de SwiftUI que da acceso a información de
layout sobre el espacio disponible y la geometría de la vista.

```swift
GeometryReader { geometry in
    Text("Width: \(geometry.size.width)")
}
```

Es útil cuando necesitas:

- Layout dinámico según el tamaño disponible
- Cálculos de posición
- Comportamiento responsive de la UI

Debe usarse con cuidado, porque un uso excesivo puede hacer más difícil razonar sobre el layout.

</details>

<details>
<summary>90. ¿Cómo funciona la navegación en SwiftUI?</summary>

#### Swift

La navegación en SwiftUI normalmente se construye con `NavigationStack`.

Navegas haciendo push de destinos sobre una pila.

```swift
NavigationStack {
    NavigationLink("Open Details") {
        DetailView()
    }
}
```

También puedes usar navegación basada en valores con `navigationDestination`.

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

La navegación en SwiftUI está impulsada por estado y es más declarativa que
los navigation controllers de UIKit.

</details>

<details>
<summary>91. ¿Cuál es el lifecycle de una vista SwiftUI?</summary>

#### Swift

Las vistas de SwiftUI son value types, así que su lifecycle es diferente al de
los view controllers de UIKit.

Una vista SwiftUI se crea y recrea con frecuencia a medida que cambia el estado.
La idea importante no es la vida del struct en sí, sino la vida del estado conectado a él.

Los hooks de lifecycle más comunes incluyen:

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

En SwiftUI, el estado y el flujo de datos importan más que la vida del objeto.

</details>

<details>
<summary>92. ¿Por qué las vistas de SwiftUI son structs?</summary>

#### Swift

Las vistas de SwiftUI son structs porque los value types funcionan bien con una UI declarativa.

Beneficios:

- Ligeras
- Fáciles de recrear
- Flujo de datos más seguro
- Mejores oportunidades de rendimiento para SwiftUI

Como son value types, SwiftUI puede reconstruir los valores de vista con
frecuencia y compararlos eficientemente cuando cambia el estado.

Las partes persistentes reales de la UI las gestiona el framework, no el propio struct de la vista.

</details>

<details>
<summary>93. ¿Cuál es la diferencia entre UIKit y SwiftUI?</summary>

#### Swift

UIKit y SwiftUI son frameworks de UI de Apple, pero usan enfoques diferentes.

| Feature | UIKit | SwiftUI |
| --- | --- | --- |
| Style | Imperative | Declarative |
| Main building blocks | `UIView`, `UIViewController` | `View` |
| State updates | Manual | State-driven |
| Typical usage | Mature, lower-level UI control | Modern declarative UI development |

UIKit te da un control más directo.
SwiftUI te ofrece una forma más moderna y concisa de construir UI.

</details>

<details>
<summary>94. ¿Qué es Auto Layout?</summary>

#### Swift

Auto Layout es el sistema de Apple para posicionar y dimensionar elementos de
UI usando constraints.

En lugar de establecer frames manualmente para cada tamaño de pantalla,
defines reglas sobre cómo se relacionan las vistas entre sí.

Ejemplos:

- Un label está a 16 puntos del borde izquierdo
- Un botón está centrado horizontalmente
- Una imagen mantiene el mismo ancho y alto

Auto Layout ayuda a construir interfaces adaptativas para diferentes
dispositivos y tamaños de pantalla.

</details>

<details>
<summary>95. ¿Qué es intrinsic content size?</summary>

#### Swift

Intrinsic content size es el tamaño natural que una vista prefiere según su contenido.

Por ejemplo:

- Un label dimensiona su tamaño según su texto
- Un image view dimensiona su tamaño según la imagen

Esto ayuda a Auto Layout a saber qué tamaño debe tener una vista incluso sin
constraints explícitas de ancho y alto.

Vistas como `UILabel` y `UIButton` suelen tener intrinsic content size.

</details>

<details>
<summary>96. ¿Qué son constraints y anchors?</summary>

#### Swift

Las constraints son reglas de layout usadas por Auto Layout.
Los anchors son una forma más cómoda en código de crear esas constraints.

Anchors comunes:

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

Los anchors hacen que el código de Auto Layout sea más seguro y más fácil de
leer que las APIs de constraints más antiguas.

</details>

<details>
<summary>97. ¿Qué son las reusable cells?</summary>

#### Swift

Las reusable cells son celdas de table view o collection view que se reutilizan
en lugar de crearse desde cero para cada elemento.

Esto mejora:

- El rendimiento
- El uso de memoria
- La eficiencia del scroll

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
```

La reutilización funciona reciclando celdas fuera de pantalla para nuevo contenido.

</details>

<details>
<summary>98. ¿Cuál es la diferencia entre UITableView y UICollectionView?</summary>

#### Swift

Ambos muestran listas de datos, pero están diseñados para distintas necesidades de layout.

| Feature | `UITableView` | `UICollectionView` |
| --- | --- | --- |
| Layout style | Mostly vertical list | Flexible layouts |
| Complexity | Simpler | More customizable |
| Typical use | Simple lists, forms, settings | Grids, custom layouts, complex lists |

Usa `UITableView` para una UI sencilla basada en listas.
Usa `UICollectionView` cuando necesites layouts más flexibles o personalizados.

</details>

<details>
<summary>99. ¿Qué es `@IBOutlet` frente a `@IBAction`?</summary>

#### Swift

Ambos se usan con Interface Builder en storyboards UIKit o archivos XIB.

- `@IBOutlet` conecta un elemento de UI con el código
- `@IBAction` conecta un evento de UI con el código

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

`@IBOutlet` sirve para referencias a elementos de UI.
`@IBAction` sirve para manejar acciones del usuario.

</details>

<details>
<summary>100. ¿Qué es el lifecycle de `UIViewController`?</summary>

#### Swift

El lifecycle de `UIViewController` es la secuencia de métodos que se llaman
cuando un view controller se crea, se muestra, se layouta y se retira.

Métodos de lifecycle comunes:

1. `viewDidLoad`
2. `viewWillAppear`
3. `viewDidAppear`
4. `viewWillDisappear`
5. `viewDidDisappear`

#### Ejemplos de funciones

- `viewDidLoad`: configuración inicial
- `viewWillAppear`: actualizar la UI antes de que se vuelva visible
- `viewDidAppear`: iniciar animaciones o tracking
- `viewWillDisappear`: prepararse para salir de la pantalla
- `viewDidDisappear`: trabajo de limpieza

Comprender este lifecycle es esencial en el desarrollo de apps UIKit.

</details>

<details>
<summary>101. ¿Qué es MVC?</summary>

#### Swift

MVC significa Model-View-Controller.

Es un patrón de diseño que separa una app en tres partes:

- Model: datos y lógica de negocio
- View: UI
- Controller: gestiona la interacción entre el modelo y la vista

En iOS, `UIViewController` suele desempeñar el papel de controller.

MVC es simple y común, pero en apps UIKit puede llevar fácilmente a un "Massive View Controller"
si se coloca demasiada lógica en el controller.

</details>

<details>
<summary>102. ¿Qué es MVVM?</summary>

#### Swift

MVVM significa Model-View-ViewModel.

Separa las responsabilidades así:

- Model: datos y reglas de negocio
- View: UI
- ViewModel: lógica de presentación y estado para la vista

El ViewModel prepara los datos para mostrarlos y reduce la lógica dentro de la vista
o del view controller.

MVVM es popular en SwiftUI y también se usa con frecuencia en apps UIKit.

</details>

<details>
<summary>103. ¿Qué es dependency injection?</summary>

#### Swift

Dependency injection significa proporcionar a un objeto las dependencias que necesita
desde fuera, en lugar de crearlas dentro del propio objeto.

Por ejemplo, en vez de que un view model cree su propio servicio de red,
el servicio se le pasa desde fuera.

Beneficios:

- Mejor testabilidad
- Menor acoplamiento
- Sustitución más fácil de implementaciones

</details>

<details>
<summary>104. ¿Cómo implementas DI en Swift?</summary>

#### Swift

La forma más común es la inyección por constructor.

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

Otros enfoques comunes:

- Inyección por propiedad
- Inyección por método
- Contenedores de dependencias

La inyección por constructor suele preferirse porque hace explícitas las dependencias.

</details>

<details>
<summary>105. ¿Qué es el delegation pattern?</summary>

#### Swift

La delegación es un patrón en el que un objeto pasa la responsabilidad de cierto trabajo
o eventos a otro objeto.

Normalmente se implementa con protocolos.

```swift
protocol ButtonHandler: AnyObject {
    func didTapButton()
}
```

La delegación se usa mucho en UIKit, por ejemplo con:

- `UITableViewDelegate`
- `UITextFieldDelegate`

Ayuda a mantener separadas las responsabilidades y a que la comunicación sea flexible.

</details>

<details>
<summary>106. ¿Cuándo deberías usar un singleton?</summary>

#### Swift

Un singleton debería usarse cuando debe existir exactamente una única instancia compartida
en la app.

Ejemplos típicos:

- Configuración global de la app
- Servicio de logging
- Gestor de caché

```swift
final class Logger {
    static let shared = Logger()

    private init() {}
}
```

Usa singletons con cuidado.
Abusar de ellos puede crear dependencias ocultas y dificultar las pruebas.

</details>

<details>
<summary>107. ¿Qué es KVO?</summary>

#### Swift

KVO significa Key-Value Observing.

Es un mecanismo para observar cambios en propiedades de ciertos objetos,
especialmente aquellos compatibles con Objective-C.

Está principalmente asociado con Cocoa y con el comportamiento del runtime de Objective-C.

KVO se usa menos en código Swift moderno en comparación con:

- Combine
- `@Published`
- Herramientas de estado de SwiftUI

Pero todavía aparece en algunas APIs de UIKit y Foundation.

</details>

<details>
<summary>108. ¿Qué es NotificationCenter?</summary>

#### Swift

`NotificationCenter` es un sistema para difundir mensajes a múltiples observadores.

Un objeto publica una notificación y otros objetos pueden escucharla.

```swift
NotificationCenter.default.post(name: .didLogout, object: nil)
```

Es útil para una comunicación flexible entre partes de la app, especialmente
cuando las referencias directas no son ideales.

Úsalo con cuidado, porque un uso excesivo puede hacer más difícil seguir el flujo de datos.

</details>

<details>
<summary>109. ¿Cómo haces una petición de red en Swift?</summary>

#### Swift

La forma estándar es usar `URLSession`.

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

En Swift moderno, también puedes usar `async/await` con `URLSession`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>110. ¿Qué es Codable?</summary>

#### Swift

`Codable` es un type alias para:

- `Encodable`
- `Decodable`

Permite convertir tipos Swift fácilmente hacia y desde formatos como JSON.

```swift
struct User: Codable {
    let id: Int
    let name: String
}
```

Casos de uso comunes:

- Parsear respuestas de API
- Guardar datos locales
- Codificar cuerpos de petición

`Codable` reduce mucho el boilerplate de serialización.

</details>

<details>
<summary>111. ¿Qué son las decoding strategies?</summary>

#### Swift

Las decoding strategies son opciones usadas por `JSONDecoder` para controlar
cómo se decodifican los datos entrantes.

Las estrategias comunes incluyen:

- `dateDecodingStrategy`
- `keyDecodingStrategy`
- `dataDecodingStrategy`

```swift
let decoder = JSONDecoder()
decoder.keyDecodingStrategy = .convertFromSnakeCase
decoder.dateDecodingStrategy = .iso8601
```

Son útiles cuando el formato de la API no coincide directamente con el formato
de tu modelo Swift.

</details>

<details>
<summary>112. ¿Qué es URLSession?</summary>

#### Swift

`URLSession` es la API principal de Apple para realizar peticiones de red.

Se usa para:

- Descargar datos
- Subir datos
- Obtener archivos
- Gestionar tareas de red

Soporta tanto el estilo completion-handler como `async/await`.

```swift
let (data, response) = try await URLSession.shared.data(from: url)
```

</details>

<details>
<summary>113. ¿Qué es una estrategia de caché?</summary>

#### Swift

Una estrategia de caché es el plan para decidir qué datos almacenar en caché,
dónde almacenarlos y cuándo actualizarlos o invalidarlos.

Capas de caché comunes en apps iOS:

- Caché en memoria
- Caché en disco
- Caché HTTP

Las decisiones clave suelen incluir:

- Vida útil de la caché
- Reglas de invalidación
- Trade-offs entre memoria y disco
- Frescura frente a velocidad

Una buena estrategia de caché mejora el rendimiento, reduce el uso de red y hace
que la app se sienta más rápida.

</details>

<details>
<summary>114. ¿Cómo depuras crashes?</summary>

#### Swift

Las formas comunes de depurar crashes incluyen:

1. Leer el crash log
2. Revisar el stack trace
3. Reproducir el problema localmente
4. Usar el debugger de Xcode y breakpoints
5. Usar herramientas de crash reporting como Firebase Crashlytics

Cosas importantes a revisar:

- El hilo que falló
- El tipo de excepción
- Los últimos métodos llamados
- El dispositivo y la versión del sistema operativo

El objetivo es reproducir el crash, identificar la causa raíz y confirmar el fix.

</details>

<details>
<summary>115. ¿Cómo detectas memory leaks?</summary>

#### Swift

Las formas comunes de detectar memory leaks son:

- Xcode Memory Graph Debugger
- Herramienta Leaks de Instruments
- Allocations de Instruments
- Comprobar `deinit`

```swift
deinit {
    print("Object deallocated")
}
```

Si un objeto debería desaparecer pero permanece en memoria, puede haber un
retain cycle u otra referencia fuerte inesperada.

</details>

<details>
<summary>116. ¿Cómo mejoras el rendimiento en apps iOS?</summary>

#### Swift

Las formas comunes de mejorar el rendimiento incluyen:

- Reducir el trabajo en el main thread
- Optimizar el renderizado y el scroll
- Evitar asignaciones innecesarias
- Poner en caché resultados costosos
- Usar trabajo en background para tareas pesadas
- Perfilar con Instruments

Primero debes medir y después optimizar el verdadero cuello de botella.

Herramientas típicas:

- Time Profiler
- Allocations
- Memory Graph
- Instrumentos de red

</details>

<details>
<summary>117. ¿Cómo optimizas el uso de batería?</summary>

#### Swift

Para optimizar el uso de batería, reduce el trabajo innecesario y evita mantener
el hardware o las tareas en background activos más tiempo del necesario.

Prácticas comunes:

- Minimizar la actividad en background
- Evitar actualizaciones de ubicación excesivas
- Agrupar peticiones de red
- Reducir timers frecuentes y polling
- Evitar animaciones y redraws innecesarios

La regla principal es simple:

- Hacer menos trabajo
- Hacerlo con menos frecuencia

</details>

<details>
<summary>118. ¿Qué es Keychain y cuándo usarlo?</summary>

#### Swift

Keychain es el sistema de almacenamiento seguro de Apple para pequeñas piezas de datos sensibles.

Usa Keychain para cosas como:

- Tokens
- Contraseñas
- Credenciales
- Secretos sensibles

No lo uses como base de datos general.

Keychain es más seguro que `UserDefaults` para datos confidenciales.

</details>

<details>
<summary>119. ¿Qué es App Transport Security?</summary>

#### Swift

App Transport Security (ATS) es una función de seguridad de iOS que fomenta
por defecto el uso de conexiones de red seguras.

En general exige:

- HTTPS
- Configuraciones TLS fuertes

Si una app necesita HTTP inseguro o configuraciones de seguridad más débiles,
deben añadirse excepciones explícitas en la configuración de la app.

ATS ayuda a proteger el tráfico de red frente a intercepciones y transporte inseguro.

</details>

<details>
<summary>120. ¿Cómo almacenas datos de forma segura?</summary>

#### Swift

Depende de la sensibilidad de los datos.

Reglas típicas:

- Usa Keychain para contraseñas, tokens y secretos
- Usa protección de archivos para archivos sensibles
- Evita almacenar secretos en texto plano
- No almacenes datos confidenciales en `UserDefaults`
- Cifra los datos cuando sea necesario

También es importante:

- Limitar lo que almacenas
- Guardarlo solo el tiempo necesario
- Protegerlo tanto en reposo como en tránsito

</details>

<details>
<summary>121. ¿Qué es XCTest?</summary>

#### Swift

`XCTest` es el framework de Apple para escribir y ejecutar tests en Xcode.

Se usa para:

- Unit tests
- UI tests
- Tests de rendimiento

```swift
func testAddition() {
    XCTAssertEqual(2 + 2, 4)
}
```

Es la herramienta estándar de testing para el desarrollo en plataformas Apple.

</details>

<details>
<summary>122. ¿Qué es unit testing frente a UI testing?</summary>

#### Swift

Unit testing comprueba pequeñas piezas de lógica de forma aislada.
UI testing comprueba la app a través de la interfaz de usuario.

| Type | Focus |
| --- | --- |
| Unit test | Lógica de negocio, funciones, clases |
| UI test | Flujos reales de usuario e interacciones con pantallas |

Los unit tests suelen ser:

- Más rápidos
- Más aislados
- Más fáciles de depurar

Los UI tests son útiles para validar el comportamiento end-to-end.

</details>

<details>
<summary>123. ¿Qué es mocking?</summary>

#### Swift

Mocking significa reemplazar una dependencia real por una versión falsa para tests.

Esto ayuda a probar una unidad de forma aislada.

Por ejemplo, en vez de llamar a una API real, un mock network service devuelve
datos predefinidos.

Mocking es útil para:

- Tests más rápidos
- Resultados predecibles
- Probar escenarios de fallo

</details>

<details>
<summary>124. ¿Cómo te mantienes al día con Swift?</summary>

#### Swift

Una buena respuesta consiste en combinar fuentes oficiales con aprendizaje práctico.

Formas comunes:

- Leer propuestas de Swift Evolution
- Seguir sesiones de WWDC
- Leer documentación de Apple
- Probar nuevas funciones del lenguaje en side projects
- Seguir a ingenieros reconocidos de Swift e iOS

La parte importante no es solo leer actualizaciones, sino aplicarlas en código real.

</details>

<details>
<summary>125. Háblame de una feature compleja que hayas desarrollado.</summary>

#### Swift

Una buena respuesta de entrevista debería estructurarse así:

1. Explicar brevemente la feature
2. Describir los principales retos técnicos
3. Explicar tus decisiones y trade-offs
4. Mostrar el resultado

#### Ejemplo de estructura de respuesta

"Desarrollé una feature de sincronización offline-first para una app móvil. Los
principales retos fueron la resolución de conflictos, la persistencia local, la
lógica de retry y mantener la UI responsiva durante la sincronización. Dividí
el problema en capas de networking, almacenamiento local de datos y
orquestación de sincronización. También añadí políticas de retry, gestión de
sincronización en background y logging. El resultado fue un mejor rendimiento
percibido, mayor fiabilidad en redes inestables y menos problemas de soporte."

Las mejores respuestas son concretas y medibles.

</details>

<details>
<summary>126. ¿Cómo enfocas una code review?</summary>

#### Swift

Un enfoque sólido de code review se centra primero en la corrección y después en la mantenibilidad.

Prioridades típicas:

- Bugs y edge cases
- Adecuación de la arquitectura y el diseño
- Legibilidad
- Naming
- Cobertura de tests
- Rendimiento y seguridad cuando sea relevante

Una buena review debe ser clara, respetuosa y específica.

El objetivo no es solo encontrar problemas, sino también mejorar la calidad del código
y compartir conocimiento.

</details>

<details>
<summary>127. ¿Cómo diseñas una arquitectura iOS escalable?</summary>

#### Swift

Una arquitectura escalable consiste en mantener las features fáciles de ampliar,
testear y mantener a medida que la app crece.

Principios importantes:

- Separación clara de responsabilidades
- Diseño modular
- Inyección de dependencias
- Lógica de negocio testeable
- Flujo de datos predecible

Una arquitectura escalable debe ayudar a los equipos a añadir features sin
reescribir constantemente el código existente.

</details>

<details>
<summary>128. ¿Qué trade-offs consideras al elegir una arquitectura?</summary>

#### Swift

La arquitectura siempre trata de trade-offs.

Factores comunes:

- Tamaño y experiencia del equipo
- Complejidad de la app
- Velocidad de desarrollo
- Testabilidad
- Mantenibilidad
- Flexibilidad para el crecimiento futuro

Una app simple puede no necesitar una arquitectura pesada.
Una app grande suele beneficiarse de una separación más fuerte, límites más claros
y una mejor gestión de dependencias.

La mejor elección es la arquitectura más simple que siga encajando bien con el problema.

</details>
