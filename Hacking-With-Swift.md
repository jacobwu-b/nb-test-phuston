---
Title: Hacking With Swift
---

# Day 1 Variables, simple data types, and string interpolation

Var vs. Let

`"String"` and """Multiline

String"

Int, double, bool

String Interpolation

```swift
var score = 89
var output = "Your score was \(score)"
```

Type Inference

# Day 2 Arrays, dictionaries, sets, and enums

## Arrays

```swift
let john = "John Lennon"
let paul = "Paul McCartney"
let george = "George Harrison"
let ringo = "Ringo Starr"

let beatles = [john, paul, george, ringo]
```

## Sets

Like array, but unordered and cannot have repeats

```swift
let colors = Set(["red", "green", "blue"])
```

## Tuples

Can't add or remove; Can't change type; Can have str as index

```swift
var name = (first: "Taylor", last: "Swift")
```

## Dictionaries

Custom index type

```swift
let heights = [
    "Taylor Swift": 1.78,
    "Ed Sheeran": 1.73
]
```

### Dictionary default value

```swift
favoriteIceCream["Charlotte", default: "Unknown"]
```

### Empty Collections

```swift
var teams = [String: String]()
```

```swift
var results = [Int]()
```

```swift
var words = Set<String>()
```

```swift
var scores = Dictionary<String, Int>()
var results = Array<Int>()
```

## Enums

```swift
enum Result {
    case success
    case failure
}

let result4 = Result.failure
```

### Enum associated values

```swift
enum Activity {
    case bored
    case running(destination: String)
    case talking(topic: String)
    case singing(volume: Int)
}
```

### Enum raw values

```swift
enum Planet: Int {
    case mercury
    case venus
    case earth
    case mars
}
```

```swift
let earth = Planet(rawValue: 2)
```

```swift
enum Planet: Int {
    case mercury = 1
    case venus
    case earth
    case mars
}
```

# Day 3 Operators and conditions

## Arithmetic operators

`+ - * /`

`%` Remainder

## Operator overloading

```swift
let meaningOfLife = 42
let doubleMeaning = 42 + 42
```

```swift
let fakers = "Fakers gonna "
let action = fakers + "fake"
```

```swift
let firstHalf = ["John", "Paul"]
let secondHalf = ["George", "Ringo"]
let beatles = firstHalf + secondHalf
```

## Compound assignment 

```swift
var score = 95
score -= 5
```

```swift
var quote = "The rain in Spain falls mainly on the "
quote += "Spaniards"
```

## Comparison Operators

```swift
let firstScore = 6
let secondScore = 4
```

```swift
firstScore == secondScore
firstScore != secondScore
```

```swift
firstScore < secondScore
firstScore >= secondScore
```

```swift
"Taylor" <= "Swift"
```

## Conditions

```swift
let firstCard = 11
let secondCard = 10

if firstCard + secondCard == 21 {
    print("Blackjack!")
}
```

```swift
if firstCard + secondCard == 21 {
    print("Blackjack!")
} else {
    print("Regular cards")
}
```

```swift
if firstCard + secondCard == 2 {
    print("Aces – lucky!")
} else if firstCard + secondCard == 21 {
    print("Blackjack!")
} else {
    print("Regular cards")
}
```

## Combining conditions

```swift
let age1 = 12
let age2 = 21

if age1 > 18 && age2 > 18 {
    print("Both are over 18")
}
```

```swift
if age1 > 18 || age2 > 18 {
    print("At least one is over 18")
}
```

## Ternary operator

`If expression ? ifTrue : else`

```swift
let firstCard = 11
let secondCard = 10
print(firstCard == secondCard ? "Cards are the same" : "Cards are different")
```

## Switch Case

```swift
switch weather {
case "rain":
    print("Bring an umbrella")
case "snow":
    print("Wrap up warm")
case "sunny":
    print("Wear sunscreen")
default:
    print("Enjoy your day!")
}
```

```swift
switch weather {
case "rain":
    print("Bring an umbrella")
case "snow":
    print("Wrap up warm")
case "sunny":
    print("Wear sunscreen")
    fallthrough // Execution continues to next case
default:
    print("Enjoy your day!")
}
```

## Range Operator

```swift
let score = 85

switch score {
case 0..<50:
    print("You failed badly.")
case 50..<85:
    print("You did OK.")
default:
    print("You did great!")
}
```

# Day 4 Loops, loops, and more loops

## For loops

```swift
let count = 1...10
for number in count {
    print("Number is \(number)")
}
```

```swift
let albums = ["Red", "1989", "Reputation"]

for album in albums {
    print("\(album) is on Apple Music")
}
```

```swift
print("Players gonna ")

for _ in 1...5 {
    print("play")
}
```

## While loops

```swift
var number = 1

while number <= 20 {
    print(number)
    number += 1
}

print("Ready or not, here I come!")
```

## Repeat loops

Like while, except condition checked at end (thus always run at least once)

```swift
var number = 1

repeat {
    print(number)
    number += 1
} while number <= 20

print("Ready or not, here I come!")
```

## Exiting loops

`break` exits loop

```swift
while countDown >= 0 {
    print(countDown)

    if countDown == 4 {
        print("I'm bored. Let's go now!")
        break
    }

    countDown -= 1
}
```

# Exiting multiple (nested) loops

```swift
for i in 1...10 {
    for j in 1...10 {
        let product = i * j
        print ("\(i) * \(j) is \(product)")
    }
}
```

```swift
outerLoop: for i in 1...10 {
    for j in 1...10 {
        let product = i * j
        print ("\(i) * \(j) is \(product)")

        if product == 50 {
            print("It's a bullseye!")
            break outerLoop
        }
    }
}
```

## Skipping items

`continue` skips current iteration

```swift
for i in 1...10 {
    if i % 2 == 1 {
        continue
    }

    print(i)
}
```

## Infinite loops

```swift
var counter = 0

while true {
    print(" ")
    counter += 1

    if counter == 273 {
        break
    }
}
```

# Day 5 Functions, parameters, and errors

## Writing functions

```swift
func printHelp() {
    let message = """
Welcome to MyApp!

Run this app inside a directory of images and
MyApp will resize them all into thumbnails
"""

    print(message)
}

printHelp()
```

## Accepting parameters

```swift
func square(number: Int) {
    print(number * number)
}
```

## Returning values

```swift
func square(number: Int) -> Int {
    return number * number
}
```

## Parameter labels

```swift
func sayHello(to name: String) {
    print("Hello, \(name)!")
}
```

## Omitting parameter labels

```swift
func greet(_ person: String) {
    print("Hello, \(person)!")
}
```

## Default parameters

```swift
func greet(_ person: String, nicely: Bool = true) {
    if nicely == true {
        print("Hello, \(person)!")
    } else {
        print("Oh no, it's \(person) again...")
    }
}
```

## Variadic functions

```swift
func square(numbers: Int...) {
    for number in numbers {
        print("\(number) squared is \(number * number)")
    }
}
```

## Writing throwing functions

```swift
enum PasswordError: Error {
    case obvious
}

func checkPassword(_ password: String) throws -> Bool {
    if password == "password" {
        throw PasswordError.obvious
    }

    return true
}
```

## Running throwing functions

```swift
do {
    try checkPassword("password")
    print("That password is good!")
} catch {
    print("You can't use that password.")
}
```

## inout parameters

```swift
func doubleInPlace(number: inout Int) {
    number *= 2
}

var myNum = 10 
doubleInPlace(number: &myNum)
```

# Day 6 Closures part one

## Creating basic closures

```swift
let driving = {
    print("I'm driving in my car")
}
```

## Accepting parameters in a closure

```swift
let driving = { (place: String) in
    print("I'm going to \(place) in my car")
}
```

## Returning values from a closure

```swift
let driving = { (place: String) in
    print("I'm going to \(place) in my car")
}
```

```swift
let drivingWithReturn = { (place: String) -> String in
    return "I'm going to \(place) in my car"
}
```

## Closures as parameters

```swift
let driving = {
    print("I'm driving in my car")
}
```

```swift
func travel(action: () -> Void) {
    print("I'm getting ready to go.")
    action()
    print("I arrived!")
}
```

```swift
travel(action: driving)
```

## Trailing closure syntax

```swift
func travel(action: () -> Void) {
    print("I'm getting ready to go.")
    action()
    print("I arrived!")
}
```

```swift
travel() {
    print("I'm driving in my car")
}
```

```swift
travel {
    print("I'm driving in my car")
}
```

# Day 7 Closures part two

## Using closures as parameters when they accept parameters

```swift
func travel(action: (String) -> Void) {
    print("I'm getting ready to go.")
    action("London")
    print("I arrived!")
}
```

```swift
travel { (place: String) in
    print("I'm going to \(place) in my car")
}
```

## Using closures as parameters when they return values

```swift
func travel(action: (String) -> String) {
    print("I'm getting ready to go.")
    let description = action("London")
    print(description)
    print("I arrived!")
}
```

```swift
travel { (place: String) -> String in
    return "I'm going to \(place) in my car"
}
```

## Shorthand parameter names

```swift
func travel(action: (String) -> String) {
    print("I'm getting ready to go.")
    let description = action("London")
    print(description)
    print("I arrived!")
}

travel {
    "I'm going to \($0) in my car"
}
```

## Closures with multiple parameters

```swift
func travel(action: (String, Int) -> String) {
    print("I'm getting ready to go.")
    let description = action("London", 60)
    print(description)
    print("I arrived!")
}

travel {
    "I'm going to \($0) at \($1) miles per hour."
}
```

## Returning closures from functions

```swift
func travel() -> (String) -> Void { // First function return, then closure return
    return {
        print("I'm going to \($0)")
    }
}

let result = travel()
result("London")

let result2 = travel()("London")
```

## Capturing values

```swift
func travel() -> (String) -> Void {
    return {
        print("I'm going to \($0)")
    }
}

let result = travel()
result("London")
```

```swift
func travel() -> (String) -> Void {
    var counter = 1 // External values are captured

    return {
        print("\(counter). I'm going to \($0)")
        counter += 1
    }
}

let result = travel()
result("London") // Each time result() is called, counter += 1
result("London")
result("London")
```

# Day 8 Structs, properties, and methods

## Creating your own structs

```swift
struct Sport {
    var name: String
}

var tennis = Sport(name: "Tennis")
print(tennis.name)

tennis.name = "Lawn tennis"
```

## Computed properties

```swift
struct Sport {
    var name: String
    var isOlympicSport: Bool

    var olympicStatus: String {
        if isOlympicSport {
            return "\(name) is an Olympic sport"
        } else {
            return "\(name) is not an Olympic sport"
        }
    }
}
```

## Property observers

```swift
struct Progress {
    var task: String
    var amount: Int
}
```

```swift
var progress = Progress(task: "Loading data", amount: 0)
progress.amount = 30
progress.amount = 80
progress.amount = 100
```

```swift
struct Progress {
    var task: String
    var amount: Int {
        didSet { // Any time variable changes
            print("\(task) is now \(amount)% complete")
        }
    }
}
```

## Methods

```swift
struct City {
    var population: Int

    func collectTaxes() -> Int {
        return population * 1000
    }
}
```

``` swift
let london = City(population: 9_000_000)
london.collectTaxes()
```

## Mutating methods

```swift
struct Person {
    var name: String

    mutating func makeAnonymous() { // mutating allows function to change struct properties
        name = "Anonymous"
    }
}
```

```swift
var person = Person(name: "Ed")
person.makeAnonymous()
```

## Properties and methods of strings

Strings are structs, with methods

```swift
let string = "Do or do not, there is no try."

print(string.count)
print(string.hasPrefix("Do"))
print(string.uppercased())
print(string.sorted())
```

## Properties and methods of arrays

```swift
var toys = ["Woody"]

print(toys.count)
toys.append("Buzz")
toys.firstIndex(of: "Buzz")
print(toys.sorted())
toys.remove(at: 0)
```

# Day 9

## Initializers

```swift
struct User {
    var username: String
}
```

```swift
var user = User(username: "twostraws")
```

Alternatively:

```swift
struct User {
    var username: String

    init() {
        username = "Anonymous"
        print("Creating a new user!")
    }
}
```

```swift
var user = User()
user.username = "twostraws"
```

## Referring to the current instance

```swift
struct Person {
    var name: String

    init(name: String) {
        print("\(name) was born!")
        self.name = name // self.name refers to the property, name refers to the parameter
    }
}
```

## Lazy properties

```swift
struct Person {
    var name: String
    lazy var familyTree = FamilyTree() // Delay creation of struct until it's needed / accessed

    init(name: String) {
        self.name = name
    }
}

var ed = Person(name: "Ed")
```

## Static properties and methods

```swift
struct Student {
    var name: String

    init(name: String) {
        self.name = name
    }
}

let ed = Student(name: "Ed")
let taylor = Student(name: "Taylor")
```

```swift
struct Student {
    static var classSize = 0 // classSize property belongs to the struct itself rather than instances of the struct
    var name: String

    init(name: String) {
        self.name = name
        Student.classSize += 1
    }
}
```

## Access control

```swift
struct Person {
    private var id: String // can't be accessed from outside struct

    init(id: String) {
        self.id = id
    }
}
```

# Day 10

## Creating your own classes

Class - must intialize every property

```swift
class Dog {
    var name: String
    var breed: String

    init(name: String, breed: String) {
        self.name = name
        self.breed = breed
    }
}
```

## Class inheritance

```swift
class Poodle: Dog { // From Dog superclass, create child class
    init(name: String) {
        super.init(name: name, breed: "Poodle")
    }
}
```

## Overriding methods

```swift
class Dog {
    func makeNoise() {
        print("Woof!")
    }
}
```

```swift
class Poodle: Dog {
    override func makeNoise() {
        print("Yip!")
    }
}
```

## Final classes

No class can inherit from it

```swift
final class Dog {
    var name: String
    var breed: String

    init(name: String, breed: String) {
        self.name = name
        self.breed = breed
    }
}
```

## Copying objects

Structs copy as deuplicate; Objects copy as pointers/references

```swift
class Singer {
    var name = "Taylor Swift"
}

var singer = Singer()

var singerCopy = singer
singerCopy.name = "Justin Bieber" // Now singer.name is also Justin Bieber
```

## Deinitializers

Classes can run code when class is destroyed

```swift
class Person {
    var name = "John Doe"

    init() {
        print("\(name) is alive!")
    }

    func printGreeting() {
        print("Hello, I'm \(name)")
    }
  
  	deinit {
    		print("\(name) is no more!")
		}
}
```

## Mutability

Variable property in constant struct can't be changed

Variable property in constant class can be changed

```swift
class Singer {
    var name = "Taylor Swift"
}

let taylor = Singer()
taylor.name = "Ed Sheeran"
print(taylor.name)
```

# Day 11 Protocols, extensions, and protocol extensions

## Protocols

Outline required properties and methods

​	→ Adopting / conforming to a protocol

```swift
protocol Identifiable {
    var id: String { get set } // can be read (“get”) or written (“set”)
}
```

```swift
struct User: Identifiable {
    var id: String
}
```

## Protocol Inheritance

```swift
protocol Payable {
    func calculateWages() -> Int
}

protocol NeedsTraining {
    func study()
}

protocol HasVacation {
    func takeVacation(days: Int)
}
```

```swift
protocol Employee: Payable, NeedsTraining, HasVacation { }
```

## Extensions

Add methods to existing types

​	Can't store properties -- must use computed properties

```swift
extension Int {
    func squared() -> Int {
        return self * self
    }
}
```

## Protocol extensions

```swift
let pythons = ["Eric", "Graham", "John", "Michael", "Terry", "Terry"]
let beatles = Set(["John", "Paul", "George", "Ringo"])
```

```swift
extension Collection { // Applicable to both arrays and sets
    func summarize() {
        print("There are \(count) of us:")

        for name in self {
            print(name)
        }
    }
}
```

## Protocol-oriented programming

```swift
protocol Identifiable {
    var id: String { get set }
    func identify()
}
```

```swift
extension Identifiable {
    func identify() {
        print("My ID is \(id).")
    }
}
```

```swift
struct User: Identifiable {
    var id: String
}

let twostraws = User(id: "twostraws")
twostraws.identify()
```

# Day 12 Optionals, unwrapping, and typecasting

## Handling missing data

```swift
var age: Int? = nil
```

## Unwrapping optionals

```swift
var name: String? = nil
```

```swift
if let unwrapped = name { // Safe unwrapping
    print("\(unwrapped.count) letters")
} else {
    print("Missing name.")
}
```

## Unwrapping with guard

```swift
func greet(_ name: String?) {
    guard let unwrapped = name else {
        print("You didn't provide a name!")
        return
    }

    print("Hello, \(unwrapped)!")
}
```

## Force unwrapping

```swift
let str = "5"
let num = Int(str) // Optional Int
let num = Int(str)! // Regular Int, but error -> Crash
```

## Implicitly unwrapped optionals

Useful when var start as nil but you're sure they will have a value when it is used

```swift
let age: Int! = nil
```

## Nil coalescing

```swift
func username(for id: Int) -> String? {
    if id == 1 {
        return "Taylor Swift"
    } else {
        return nil
    }
}
```

```swift
let user = username(for: 15) ?? "Anonymous"
```

## Optional chaining

```swift
let names = ["John", "Paul", "George", "Ringo"]
```

```swift
let beatle = names.first?.uppercased() // If valid, then continue; else return nil
```

## Optional try

```swift
enum PasswordError: Error {
    case obvious
}

func checkPassword(_ password: String) throws -> Bool {
    if password == "password" {
        throw PasswordError.obvious
    }

    return true
}

do {
    try checkPassword("password")
    print("That password is good!")
} catch {
    print("You can't use that password.")
}
```

```swift
if let result = try? checkPassword("password") {
    print("Result was \(result)")
} else {
    print("D'oh.")
}
```

```swift
try! checkPassword("sekrit")
print("OK!")
```

## Failable initializers

```swift
struct Person {
    var id: String

    init?(id: String) {
        if id.count == 9 {
            self.id = id
        } else {
            return nil
        }
    }
}
```

## Typecasting

```swift
class Animal { }

class Fish: Animal { }

class Dog: Animal {
    func makeNoise() {
        print("Woof!")
    }
}

let pets = [Fish(), Dog(), Fish(), Dog()]

for pet in pets {
    if let dog = pet as? Dog { // Safely try to typecast
        dog.makeNoise()
    }
}
```

# Day 13 Swift review, day one

## Enums with additional values

```swift
enum WeatherType {
    case sun
    case cloud
    case rain
    case wind(speed: Int)
    case snow
}
```

```swift
func getHaterStatus(weather: WeatherType) -> String? {
    switch weather {
    case .sun:
        return nil
    case .wind(let speed) where speed < 10:
        return "meh"
    case .cloud, .wind:
        return "dislike"
    case .rain, .snow:
        return "hate"
    }
}

getHaterStatus(weather: WeatherType.wind(speed: 5))
```

# Day 14 Swift review, day two

## Property Observers

```swift
struct Person {
    var clothes: String {
        willSet {
            updateUI(msg: "I'm changing from \(clothes) to \(newValue)")
        }

        didSet {
            updateUI(msg: "I just changed from \(oldValue) to \(clothes)")
        }
    }
}

func updateUI(msg: String) {
    print(msg)
}

var taylor = Person(clothes: "T-shirts")
taylor.clothes = "short skirts"
```

## Computed Properties

```swift
struct Person {
    var age: Int

    var ageInDogYears: Int {
        get {
            return age * 7
        }
    }
}

var fan = Person(age: 25)
print(fan.ageInDogYears)
```

# Day 15 Swift review, day three

```swift
class Album {
    var name: String

    init(name: String) {
        self.name = name
    }
}

class StudioAlbum: Album {
    var studio: String

    init(name: String, studio: String) {
        self.studio = studio
        super.init(name: name)
    }
}

class LiveAlbum: Album {
    var location: String

    init(name: String, location: String) {
        self.location = location
        super.init(name: name)
    }
}
```

```swift
var taylorSwift = StudioAlbum(name: "Taylor Swift", studio: "The Castles Studios")
var fearless = StudioAlbum(name: "Speak Now", studio: "Aimeeland Studio")
var iTunesLive = LiveAlbum(name: "iTunes Live from SoHo", location: "New York")

var allAlbums: [Album] = [taylorSwift, fearless, iTunesLive]
```

```swift
class Album {
    var name: String

    init(name: String) {
        self.name = name
    }

    func getPerformance() -> String {
        return "The album \(name) sold lots"
    }
}

class StudioAlbum: Album {
    var studio: String

    init(name: String, studio: String) {
        self.studio = studio
        super.init(name: name)
    }

    override func getPerformance() -> String { // StudioAlbum will use override version
        return "The studio album \(name) sold lots"
    }
}

class LiveAlbum: Album {
    var location: String

    init(name: String, location: String) {
        self.location = location
        super.init(name: name)
    }

    override func getPerformance() -> String { // LiveAlbum will use override version
        return "The live album \(name) sold lots"
    }
}
```

```swift
for album in allAlbums {
    print(album.getPerformance())

    if let studioAlbum = album as? StudioAlbum {
        print(studioAlbum.studio)
    } else if let liveAlbum = album as? LiveAlbum {
        print(liveAlbum.location)
    }
}
```

## Trailing Closure

```swift
let vw = UIView()

UIView.animate(withDuration: 0.5, animations: {
    vw.alpha = 0
})
```

```swift
let vw = UIView()

UIView.animate(withDuration: 0.5) { // Functionally equivalent, because last parameter is a closure
    vw.alpha = 0
}
```

# Day 16-19 Project 1 WeSplit

# Day 20-22 Project 2



# Day 23-25 Project 3

## View as Properties

```swift
struct ContentView: View {
    let motto1 = Text("Draco dormiens")
    let motto2 = Text("nunquam titillandus")

    var body: some View {
        VStack {
    				motto1
        				.foregroundColor(.red)
    				motto2
        				.foregroundColor(.blue)
        }
    }
}
```

```swift
var motto1: some View { Text("Draco dormiens") }  // Computed property
```

## View Composition

```swift
struct CapsuleText: View {
    var text: String

    var body: some View {
        Text(text)
            .font(.largeTitle)
            .padding()
            .foregroundColor(.white)
            .background(Color.blue)
            .clipShape(Capsule())
    }
}
```

```swift
struct ContentView: View {
    var body: some View {
        VStack(spacing: 10) {
            CapsuleText(text: "First")
            CapsuleText(text: "Second")
        }
    }
}
```

## Custom Modifier

```swift
struct Title: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.largeTitle)
            .foregroundColor(.white)
            .padding()
            .background(Color.blue)
            .clipShape(RoundedRectangle(cornerRadius: 10))
    }
}
```

```swift
Text("Hello World")
    .modifier(Title())
```

```swift
extension View {
    func titleStyle() -> some View {
        self.modifier(Title())
    }
}
```

```swift
Text("Hello World")
    .titleStyle()
```

```swift
struct Watermark: ViewModifier {
    var text: String

    func body(content: Content) -> some View {
        ZStack(alignment: .bottomTrailing) {
            content
            Text(text)
                .font(.caption)
                .foregroundColor(.white)
                .padding(5)
                .background(Color.black)
        }
    }
}

extension View {
    func watermarked(with text: String) -> some View {
        self.modifier(Watermark(text: text))
    }
}
```

# Day 26-28 Project 4

# Day 29-31 Project 5

## List and ForEach

`List` provides scrolling table of data, but present data rather than collecting date like `Form`

```swift
List {
    Section(header: Text("Section 1")) {
        Text("Static row 1")
        Text("Static row 2")
    }

    Section(header: Text("Section 2")) {
        ForEach(0..<5) {
            Text("Dynamic row \($0)")
        }
    }

    Section(header: Text("Section 3")) {
        Text("Static row 3")
        Text("Static row 4")
    }
}
```

```swift
struct ContentView: View {
    let people = ["Finn", "Leia", "Luke", "Rey"]

    var body: some View {
        List(people, id: \.self) {
            Text($0)
        }
    }
}
```

## Accessing stored files

```swift
if let fileURL = Bundle.main.url(forResource: "some-file", withExtension: "txt") {
    // we found the file in our bundle!
  if let fileContents = try? String(contentsOf: fileURL) {
    // we loaded the file into a string!
	}
}
```

## String operations

```swift
let input = "apple banana congo"
let words = input.components(separatedBy: " ")
let word = letters.randomElement()
let checker = UITextChecker()
let range = NSRange(location: 0, length: word.utf16.count)
let misspelledRange = checker.rangeOfMisspelledWord(in: word, range: range, startingAt: 0, wrap: false, language: "en")
let allGood = misspelledRange.location == NSNotFound // No errors found
```



# Day 32-35 Project 6

## Animation: Introduction

```swift
struct ContentView: View {
    @State var size: CGFloat = 1
    @State var shouldIncrement = true
    
    var body: some View {
        Button(shouldIncrement ? "Hello, World!" : "Bye World") {
            self.size += self.shouldIncrement ? 0.1 : -0.1
            if self.size > 3 {
                self.shouldIncrement = false
            } else if self.size < 1 {
                self.shouldIncrement = true
            }
        }
        .padding(50)
        .background(Color.red)
        .foregroundColor(.white)
        .clipShape(Circle())
        .scaleEffect(size)
        .animation(.default) // Implicit animation -- let Swift figure it out!
    }
}
```

```swift
.animation(
    Animation.easeInOut(duration: 1)
        .delay(1)
        .repeatCount(3, autoreverses: true)
)
```

```swift
.animation(
    Animation.easeInOut(duration: 1)
        .repeatForever(autoreverses: true)
)
```

```swift
.overlay(
    Circle()
        .stroke(Color.red)
        .scaleEffect(animationAmount)
        .opacity(Double(2 - animationAmount))
) // Animate circle only
```

```swift
.overlay(
    Circle()
        .stroke(Color.red)
        .scaleEffect()
        .opacity(Double(2 - animationAmount))
        .animation(
            Animation.easeOut(duration: 1)
                .repeatForever(autoreverses: false)
        )
)
```

```swift
var body: some View {
    print(animationAmount)

    return VStack { // You can issue commands like print as long as you tell Swift what to return
```

```swift
.rotation3DEffect(.degrees(animationAmount), axis: (x: 0, y: 1, z: 0)) // Explicit animation
```

```swift
withAnimation {
    self.animationAmount += 360
} // This closure tells Swift to animate while changing the variable
```

Only changes preceding the `.animation()` will be animated

​	Possible to nest `.animation()` so that each one is activated when anything before it changes

```swift
Button("Tap Me") {
    self.enabled.toggle()
}
.frame(width: 200, height: 200)
.background(enabled ? Color.blue : Color.red)
.animation(nil)
.foregroundColor(.white)
.clipShape(RoundedRectangle(cornerRadius: enabled ? 60 : 0))
.animation(.interpolatingSpring(stiffness: 10, damping: 1))
```

## Custom Animations

```swift
struct CornerRotateModifier: ViewModifier {
    let amount: Double
    let anchor: UnitPoint

    func body(content: Content) -> some View {
        content.rotationEffect(.degrees(amount), anchor: anchor).clipped()
    }
}
```

```swift
extension AnyTransition {
    static var pivot: AnyTransition {
        .modifier(
            active: CornerRotateModifier(amount: -90, anchor: .topLeading),
            identity: CornerRotateModifier(amount: 0, anchor: .topLeading)
        )
    }
}
```

```swift
.transition(.pivot)
```

# Day 36-38 Project 7

## Sheets

Struct must re-create every time a value is changed (`@State`), classes can just modify it (`@ObservedObject`)

Class should be used to share data across views

​	Use `@Published`

```swift
struct SecondView: View {
    var body: some View {
        Text("Second View")
    }
}

struct ContentView: View {
    @State private var showingSheet = false

    var body: some View {
        Button("Show Sheet") {
            self.showingSheet.toggle()
        }
        .sheet(isPresented: $showingSheet) {
            SecondView()
        }
    }
}
```

Environment contains information provided to us externally

```swift
@Environment(\.presentationMode) var presentationMode

Button("Dismiss") {
    self.presentationMode.wrappedValue.dismiss()
}
```

## Deleting From Array

```swift
struct ContentView: View {
    @State private var numbers = [Int]()
    @State private var currentNumber = 1

    var body: some View {
        VStack {
            List {
                ForEach(numbers, id: \.self) {
                    Text("\($0)")
                }
								.onDelete(perform: removeRows)
            }

            Button("Add Number") {
                self.numbers.append(self.currentNumber)
                self.currentNumber += 1
            }
        }
    }

  	func removeRows(at offsets: IndexSet) {
    		numbers.remove(atOffsets: offsets)
		}
}
```

## Storing User Data

```swift
struct ContentView: View {
    @State private var tapCount = UserDefaults.standard.integer(forKey: "Tap")

    var body: some View {
        Button("Tap count: \(tapCount)") {
            self.tapCount += 1
          	UserDefaults.standard.set(self.tapCount, forKey: "Tap")
        }
    }
}
```

Complex User Data

`Codable` Archiving & unarchiving data

```swift
struct User: Codable {
    var firstName: String
    var lastName: String
}

Button("Save User") {
    let encoder = JSONEncoder()

    if let data = try? encoder.encode(self.user) {
        UserDefaults.standard.set(data, forKey: "UserData")
    }
}
```

# Day 39-42 Project 8

## Images

```swift
Image("Example")
    .frame(width: 300, height: 300)
    .clipped() // Confines image content to image frame
```

```swift
Image("Example")
    .resizable()
    .aspectRatio(contentMode: .fit) // Fit maintains aspect ratio; fill stretches image to fill
    .frame(width: 300, height: 300)
```

```swift
VStack {
    GeometryReader { geo in
        Image("Example")
            .resizable()
            .aspectRatio(contentMode: .fit)
            .frame(width: geo.size.width)
    }
}
```

## ScrollView

`ScrollView(.vertical)` or `.horizontal`

`ScrollView(.horizontal, showsIndicators: false) {`

## NavigationLink

```swift
NavigationView {
    VStack {
        NavigationLink(destination: Text("Detail View")) {
            Text("Hello World")
        }
    }
    .navigationBarTitle("SwiftUI")
}
```

## Decoding Hierarchical Codable JSON

```swift
Button("Decode JSON") {
    let input = """
    {
        "name": "Taylor Swift",
        "address": {
            "street": "555, Taylor Swift Avenue",
            "city": "Nashville"
        }
    }
    """

    // more code to come
}
```

```swift
struct User: Codable {
    var name: String
    var address: Address
}

struct Address: Codable {
    var street: String
    var city: String
}
```

```swift
let data = Data(input.utf8)
let decoder = JSONDecoder()
if let user = try? decoder.decode(User.self, from: data) {
    print(user.address.street)
}
```

## Making Methods Generic

`<>` Placeholders

`<T>` for "type" to be used everywhere we want our custom, generalizable struct





# Day 43-48 Project 9

## Paths

Core Animation = most animation, textfield, and drawing

Metal = low-level framework for complex animations

Path is a type that allows us to represent lines & shapes

CG = core graphics, an old method to refer to positions

```swift
var body: some View {
    Path { path in
        path.move(to: CGPoint(x: 200, y: 100))
        path.addLine(to: CGPoint(x: 100, y: 300))
        path.addLine(to: CGPoint(x: 300, y: 300))
        path.addLine(to: CGPoint(x: 200, y: 100))
    }
		.fill(Color.blue).stroke(Color.purple, lineWidth: 10)
}
```

```swift
Path { path in
    path.move(to: CGPoint(x: 200, y: 100))
    path.addLine(to: CGPoint(x: 100, y: 300))
    path.addLine(to: CGPoint(x: 300, y: 300))
    path.addLine(to: CGPoint(x: 200, y: 100))
    path.addLine(to: CGPoint(x: 100, y: 300)) // Connect the first and last line
}
.stroke(Color.blue, lineWidth: 10)
```

```swift
.stroke(Color.blue, style: StrokeStyle(lineWidth: 10, lineCap: .round, lineJoin: .round))
```

## Shapes

Structs that contains lines

```swift
struct Triangle: Shape {
    func path(in rect: CGRect) -> Path {
        var path = Path()

        path.move(to: CGPoint(x: rect.midX, y: rect.minY))
        path.addLine(to: CGPoint(x: rect.minX, y: rect.maxY))
        path.addLine(to: CGPoint(x: rect.maxX, y: rect.maxY))
        path.addLine(to: CGPoint(x: rect.midX, y: rect.minY))

        return path
    }
}

Triangle()
    .stroke(Color.red, style: StrokeStyle(lineWidth: 10, lineCap: .round, lineJoin: .round))
    .frame(width: 300, height: 300)
```

```swift
struct Arc: Shape {
    var startAngle: Angle
    var endAngle: Angle
    var clockwise: Bool

    func path(in rect: CGRect) -> Path {
        var path = Path()
        path.addArc(center: CGPoint(x: rect.midX, y: rect.midY), radius: rect.width / 2, startAngle: startAngle, endAngle: endAngle, clockwise: clockwise)

        return path
    }
}

Arc(startAngle: .degrees(0), endAngle: .degrees(110), clockwise: true)
    .stroke(Color.blue, lineWidth: 10)
    .frame(width: 300, height: 300)
```

```swift
func path(in rect: CGRect) -> Path { // Rectifies iOS's weird drawing behavior
    let rotationAdjustment = Angle.degrees(90)
    let modifiedStart = startAngle - rotationAdjustment
    let modifiedEnd = endAngle - rotationAdjustment

    var path = Path()
    path.addArc(center: CGPoint(x: rect.midX, y: rect.midY), radius: rect.width / 2, startAngle: modifiedStart, endAngle: modifiedEnd, clockwise: !clockwise)

    return path
}
```

```swift
Circle()
		.stroke(Color.blue, lineWidth: 40) // Takes middle of stroke, i.e. 20
```

```swift
Circle()
    .strokeBorder(Color.blue, lineWidth: 40) // Takes outer of stroke, i.e. 40
```

```swift
var insetAmount: CGFloat = 0

func inset(by amount: CGFloat) -> some InsettableShape {
    var arc = self
    arc.insetAmount += amount
    return arc
} // Allows arc to fill all available space by making it InsettableShape

path.addArc(center: CGPoint(x: rect.midX, y: rect.midY), radius: rect.width / 2 - insetAmount, startAngle: modifiedStart, endAngle: modifiedEnd, clockwise: !clockwise)
```

## Transforming Shapes

**CGAffineTransform**

```swift
struct Flower: Shape {
    // How much to move this petal away from the center
    var petalOffset: Double = -20

    // How wide to make each petal
    var petalWidth: Double = 100

    func path(in rect: CGRect) -> Path {
        // The path that will hold all petals
        var path = Path()

        // Count from 0 up to pi * 2, moving up pi / 8 each time
        for number in stride(from: 0, to: CGFloat.pi * 2, by: CGFloat.pi / 8) {
            // rotate the petal by the current value of our loop
            let rotation = CGAffineTransform(rotationAngle: number)

            // move the petal to be at the center of our view 
            let position = rotation.concatenating(CGAffineTransform(translationX: rect.width / 2, y: rect.height / 2))

            // create a path for this petal using our properties plus a fixed Y and height
            let originalPetal = Path(ellipseIn: CGRect(x: CGFloat(petalOffset), y: 0, width: CGFloat(petalWidth), height: rect.width / 2))

            // apply our rotation/position transformation to the petal
            let rotatedPetal = originalPetal.applying(position)

            // add it to our main path
            path.addPath(rotatedPetal)
        }

        // now send the main path back
        return path
    }
}
```

```swift
struct ContentView: View {
    @State private var petalOffset = -20.0
    @State private var petalWidth = 100.0

    var body: some View {
        VStack {
            Flower(petalOffset: petalOffset, petalWidth: petalWidth)
                .stroke(Color.red, lineWidth: 1)

            Text("Offset")
            Slider(value: $petalOffset, in: -40...40)
                .padding([.horizontal, .bottom])

            Text("Width")
            Slider(value: $petalWidth, in: 0...100)
                .padding(.horizontal)
        }
    }
}
```

Can't use an image as border stroke? Use this:

```swift
Capsule()
    .strokeBorder(ImagePaint(image: Image("Example"), scale: 0.1), lineWidth: 20)
    .frame(width: 300, height: 200)
```

## Rendering Shapes

```swift
struct ColorCyclingCircle: View {
    var amount = 0.0
    var steps = 100

    var body: some View {
        ZStack {
            ForEach(0..<steps) { value in
                Circle()
                    .inset(by: CGFloat(value))
                    .strokeBorder(self.color(for: value, brightness: 1), lineWidth: 2)
            }
        }
    }

    func color(for value: Int, brightness: Double) -> Color {
        var targetHue = Double(value) / Double(self.steps) + self.amount

        if targetHue > 1 {
            targetHue -= 1
        }

        return Color(hue: targetHue, saturation: 1, brightness: brightness)
    }
}

struct ContentView: View {
    @State private var colorCycle = 0.0

    var body: some View {
        VStack {
            ColorCyclingCircle(amount: self.colorCycle)
                .frame(width: 300, height: 300)

            Slider(value: $colorCycle)
        }
    }
}
```

Use Metal for faster rendering -- `drawingGroup()`

## Special Effects

```swift
ZStack {
    Image("PaulHudson")

    Rectangle() // Red filter on top of the image
        .fill(Color.red)
        .blendMode(.multiply)
}
.frame(width: 400, height: 500)
.clipped()
```

Alternatively:

```swift
var body: some View {
    Image("PaulHudson")
        .colorMultiply(.red)
}
```

## animatableData

```swift
AnimatablePair<CGFloat, AnimatablePair<CGFloat, AnimatablePair<CGFloat, CGFloat>>>
```

Animates complex, multiple objects

# Day 49-52 Project 10

## Processing and Transferring Data

Compliance w/ Codable in a class requires (a) every proproperty is codable, or (b) CodingKeys

```swift
enum CodingKeys: CodingKey {
    case name
}

required init(from decoder: Decoder) throws {
    let container = try decoder.container(keyedBy: CodingKeys.self)
    name = try container.decode(String.self, forKey: .name)
}
```

```swift
func loadData() {
  	guard let url = URL(string: "https://itunes.apple.com/search?term=taylor+swift&entity=song") else {
    		print("Invalid URL")
    		return
		}
  
  	let request = URLRequest(url: url)
  
  			URLSession.shared.dataTask(with: request) { data, response, error in
						if let data = data {
            		if let decodedResponse = try? JSONDecoder().decode(Response.self, from: data) {
                    // we have good data – go back to the main thread
                    DispatchQueue.main.async {
                        // update our UI
                        self.results = decodedResponse.results
                    }

                    // everything is good, so we can exit
                    return
                }
            }

            // if we're still here it means there was a problem
            print("Fetch failed: \(error?.localizedDescription ?? "Unknown error")")
				}.resume()
		}
}
```

```swift
Section {
    Button("Create account") {
        print("Creating account…")
    }
}
.disabled(username.isEmpty || email.isEmpty)
```

# Day 53-56 Project 11

## @Binding

If a boolean is passed to a struct (object), then that object keeps track of the value, rather than content view

To solve this and unify, use @Binding instead of @State in the object

```swift
struct PushButton: View {
    let title: String
    @Binding var isOn: Bool // Use @Binding to indicate subsidiary view

    var onColors = [Color.red, Color.yellow]
    var offColors = [Color(white: 0.6), Color(white: 0.4)]

    var body: some View {
        Button(title) {
            self.isOn.toggle()
        }
        .padding()
        .background(LinearGradient(gradient: Gradient(colors: isOn ? onColors : offColors), startPoint: .top, endPoint: .bottom))
        .foregroundColor(.white)
        .clipShape(Capsule())
        .shadow(radius: isOn ? 0 : 5)
    }
}

struct ContentView: View {
    @State private var rememberMe = false // Keep @State in ContentView

    var body: some View {
        VStack {
            PushButton(title: "Remember Me", isOn: $rememberMe) // Use $ sign here
            Text(rememberMe ? "On" : "Off")
        }
    }
}
```

## Size Classes

Swift returns vague size information -- regular or compact

```swift
if sizeClass == .compact {
    return AnyView(VStack { // Since VStack and HStack aren't considered the same type of view, they need to be embedded in AnyView
        Text("Active size class:")
        Text("COMPACT")
    }
    .font(.largeTitle))
} else {
    return AnyView(HStack {
        Text("Active size class:")
        Text("REGULAR")
    }
    .font(.largeTitle))
}
```

## Core Data

Lets us design, store, and retrive custom data

​	Allows more data storage and processing options than `Codable` and `UserDefaults`

Add Entity > Add Properties > Integrate

```swift

    @Environment(\.managedObjectContext) var moc
    @FetchRequest(entity: Student.entity(), sortDescriptors: []) var students: FetchedResults<Student>

        List(students, id: \.self) { student in
        		Text(student.name ?? "Unknown")
        }
        Button("Add") {
          	let first = ["a", "b", "c"]
          	let last = ["1", "2", "3"]

          	let f = first.randomElement()
          	let l = last.randomElement()

          	let student = Student(context: self.moc)
          	student.id = UUID()
          	student.name = "\(f) \(l)"

          	try? self.moc.save()
        }
```

















































# 

# Day 57-61 Project 12

## Core Data

CoreData > Entities > Inspectors > Show Data Model Inspectors

Codegen: Manual/None gives more custom options

**Editor > Create NSManagedObectClass** Generates swift files that explicates the data model

CoreDataProperties

```swift
if self.moc.hasChanges {
    try? self.moc.save()
} // Avoids unnecessary saves when nothing changed
```

## Writing to CoreData

Add this to Scene Delegate, so that SwiftUI will automatically remove older duplicates

```swift
import CoreData // Manual Add
```

```swift
context.mergePolicy = NSMergeByPropertyObjectTrumpMergePolicy // Below let context =
```

## NSPredicate

Allows selectively displaying objects

```swift
import CoreData
import SwiftUI

struct ContentView: View {
    @Environment(\.managedObjectContext) var moc
    @FetchRequest(entity: Ship.entity(), sortDescriptors: [], predicate: nil) var ships: FetchedResults<Ship>

    var body: some View {
        VStack {
            List(ships, id: \.self) { ship in
                Text(ship.name ?? "Unknown name")
            }

            Button("Add Examples") {
                let ship1 = Ship(context: self.moc)
                ship1.name = "Enterprise"
                ship1.universe = "Star Trek"

                let ship2 = Ship(context: self.moc)
                ship2.name = "Defiant"
                ship2.universe = "Star Trek"

                let ship3 = Ship(context: self.moc)
                ship3.name = "Millennium Falcon"
                ship3.universe = "Star Wars"

                let ship4 = Ship(context: self.moc)
                ship4.name = "Executor"
                ship4.universe = "Star Wars"

                try? self.moc.save()
            }
        }
    }
}
```

```swift
@FetchRequest(entity: Ship.entity(), sortDescriptors: [], predicate: NSPredicate(format: "universe == 'Star Wars'")) var ships: FetchedResults<Ship>
```

```swift
NSPredicate(format: "universe == %@", "Star Wars")) // Conditional
```

```swift
NSPredicate(format: "name < %@", "F")) var ships: FetchedResults<Ship> // Any word before F
```

```swift
NSPredicate(format: "universe IN %@", ["Aliens", "Firefly", "Star Trek"]) // Option is one of three
```

```swift
NSPredicate(format: "name BEGINSWITH %@", "E")) // String conditional
```

``` swift
NSPredicate(format: "name BEGINSWITH[c] %@", "e")) // [c] indicates any location
```

```swift
NSPredicate(format: "NOT name BEGINSWITH[c] %@", "e")) // NOT as logical operator
```

## Dynamic Filtering

```swift
var wrappedFirstName: String {
    firstName ?? "Unknown"
}

var wrappedLastName: String {
    lastName ?? "Unknown"
}
```

```swift
@Environment(\.managedObjectContext) var moc
@State private var lastNameFilter = "A"
```

```swift
VStack {
    // list of matching singers

    Button("Add Examples") {
        let taylor = Singer(context: self.moc)
        taylor.firstName = "Taylor"
        taylor.lastName = "Swift"

        let ed = Singer(context: self.moc)
        ed.firstName = "Ed"
        ed.lastName = "Sheeran"

        let adele = Singer(context: self.moc)
        adele.firstName = "Adele"
        adele.lastName = "Adkins"

        try? self.moc.save()
    }

    Button("Show A") {
        self.lastNameFilter = "A"
    }

    Button("Show S") {
        self.lastNameFilter = "S"
    }
}
```

```swift
var fetchRequest: FetchRequest<Singer>
```

```swift
init(filter: String) {
    fetchRequest = FetchRequest<Singer>(entity: Singer.entity(), sortDescriptors: [], predicate: NSPredicate(format: "lastName BEGINSWITH %@", filter))
}
```

```swift
var body: some View {
    List(fetchRequest.wrappedValue, id: \.self) { singer in
        Text("\(singer.wrappedFirstName) \(singer.wrappedLastName)")
    }
}
```

```swift
var singers: FetchedResults<Singer> { fetchRequest.wrappedValue }
```

```swift
FilteredList(filter: lastNameFilter)
```

```swift
NSPredicate(format: "%K BEGINSWITH %@", filterKey, filterValue)
```







































# Code Dump



## Project 1

```swift
//
//  ContentView.swift
//  WeSplit
//
//  Created by Academia on 5/12/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct ContentView: View {
    @State var mealCost = 1
    @State var mealCent = 1
    @State var numPeople = 1
    @State var tip = 1
    var tipMult: Double {
        return 1 + Double(tip) / 20.0
    }
    var orderAmount: Double {
        return Double(self.mealCost) + Double(self.mealCent) / 100.0
    }
    var grandTotal: Double {
        return orderAmount * tipMult
    }
    var totalPerPerson: Double {        
        return grandTotal / Double(numPeople)
    }
    
    var body: some View {
        GeometryReader { geometry in
            NavigationView {
                VStack {
                    Spacer()
                    Text("How much does the meal cost?").font(.caption)
                    HStack(spacing: 0) {
                        HStack {
                            Spacer()
                            Picker(selection: self.$mealCost, label: Text("Dollar amount")) {
                                ForEach(0 ..< 1000) {
                                    Text("$\($0)")
                                }
                            }.frame(width: 50)
                                .clipped()
                        }
                        HStack {
                            Picker(selection: self.$mealCent, label: Text("Cent amount")) {
                                ForEach(0 ..< 100) {
                                    Text($0 < 10 ? ".0\($0)" : ".\($0)")
                                }
                            }.frame(width: 50)
                                .clipped()
                            Spacer()
                        }
                    }
                    
                    Form {
                        Section {
                            Stepper(value: self.$numPeople, in: 1...20) {
                                Text("Number of People: \(self.numPeople)")
                            }
                        }
                        
                        Section(header: Text("How much tip do you want to leave?")) {
                            Picker("Tip percentage", selection: self.$tip) {
                                ForEach(0 ..< 5) {
                                    Text("\($0 * 5)%")
                                }
                            }
                            .pickerStyle(SegmentedPickerStyle())
                        }
                        
                        Section(header: Text("Cost Summary")) {
                            Text("Meal Cost: $\(self.orderAmount, specifier: "%.2f")")
                            Text("Grand Total: $\(self.grandTotal, specifier: "%.2f")")
                            Text("Per Person: $\(self.totalPerPerson, specifier: "%.2f")")
                        }
                    }
                }.navigationBarTitle(Text("🤷‍♂️ WeSplit"))
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

## Project 2

```swift
//
//  ContentView.swift
//  Guess the Flag
//
//  Created by Academia on 5/12/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct ContentView: View {
    @State var countries = ["Estonia", "France", "Germany", "Ireland", "Italy", "Nigeria", "Poland", "Russia", "Spain", "UK", "US"].shuffled()
    @State var correctAnswer = Int.random(in: 0 ..< 3)
    @State var displayText = ""
    @State var score = 0
    var displayColor: Color {
        if displayText == "Correct" {
            return .green
        } else {
            return .red
        }
    }
    
    func flagTapped(_ number: Int) {
        if number == correctAnswer {
            displayText = "Correct"
            score += 1
        } else {
            displayText = "Wrong"
        }
        countries.shuffle()
        correctAnswer = Int.random(in: 0...2)
    }
    var body: some View {
        NavigationView {
        ZStack {
            LinearGradient(gradient: Gradient(colors: [.purple, .blue]), startPoint: .top, endPoint: .bottom)
            VStack {
                Text("Tap the flag of").font(.caption).foregroundColor(.white)
                Text(countries[correctAnswer]).font(.headline).bold().foregroundColor(.white)
                ForEach(0 ..< 3) { i in
                    Button(action: {
                        self.flagTapped(i)
                    }) {
                        Image(self.countries[i])
                            .renderingMode(.original)
                            .clipShape(Capsule())
                            .overlay(Capsule().stroke(Color.white, lineWidth: 5))
                            .padding(5)
                    }
                }
                Text(displayText)
                    .font(.largeTitle)
                    .foregroundColor(displayColor)
                    .bold()
            }
        }.edgesIgnoringSafeArea(.all).navigationBarTitle(Text("🚩 Guess the Flag"))
            .navigationBarItems(trailing:
                Text("Score: \(score)").foregroundColor(.white)
            )
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

## Project 3

```swift
//
//  ContentView.swift
//  Composing Views Demo
//
//  Created by Academia on 5/13/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct MottoView: View {
    let motto1 = Text("Draco dormiens")
    let motto2 = Text("nunquam titillandus")

    var body: some View {
        VStack {
            VStack {
                motto1
                    .foregroundColor(.red)
                motto2
                    .foregroundColor(.purple)
            }
        }
    }
}

struct CapsuleText: View {
    var text: String

    var body: some View {
        Text(text)
            .font(.largeTitle)
            .padding()
            .foregroundColor(.white)
            .background(Color.blue)
            .clipShape(Capsule())
    }
}

struct Title: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.largeTitle)
            .foregroundColor(.white)
            .padding()
            .background(Color.blue)
            .clipShape(RoundedRectangle(cornerRadius: 10))
    }
}

extension View {
    func titleStyle() -> some View {
        self.modifier(Title())
    }
}

struct Watermark: ViewModifier {
    var text: String

    func body(content: Content) -> some View {
        ZStack(alignment: .bottomTrailing) {
            content
            Text(text)
                .font(.caption)
                .foregroundColor(.white)
                .padding(5)
                .background(Color.black)
        }
    }
}

extension View {
    func watermarked(with text: String) -> some View {
        self.modifier(Watermark(text: text))
    }
}

struct GridStack<Content: View>: View {
    let rows: Int
    let columns: Int
    let content: (Int, Int) -> Content

    init(rows: Int, columns: Int, @ViewBuilder content: @escaping (Int, Int) -> Content) {
        self.rows = rows
        self.columns = columns
        self.content = content
    }

    var body: some View {
        VStack {
            ForEach(0..<rows, id: \.self) { row in
                HStack {
                    ForEach(0..<self.columns, id: \.self) { column in
                        self.content(row, column)
                    }
                }
            }
        }
    }
}

struct ContentView: View {
    var body: some View {
        NavigationView {
        VStack {
            Text("Hello World")
                .padding()
                .background(Color.red)
                .padding()
                .background(Color.blue)
                .padding()
                .background(Color.green)
                .padding()
                .background(Color.yellow)
            
            MottoView().titleStyle()

            Button("Hello World") {
                print(type(of: self.body))
            }
            .frame(width: 100, height: 100)
            .background(Color.red)

            VStack(spacing: 10) {
                CapsuleText(text: "First")
                    .foregroundColor(.white)
                CapsuleText(text: "Second")
                    .foregroundColor(.yellow)
            }

            GridStack(rows: 4, columns: 4) { row, col in
                Image(systemName: "\(row * 4 + col).circle")
                Text("R\(row) C\(col)")
            }
            }.navigationBarTitle(Text("🔨 Composing Views"))
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

## Project 4

```swift
//
//  ContentView.swift
//  Better Rest
//
//  Created by Academia on 5/13/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct ContentView: View {
    @State var desiredWakeTime = defaultWakeTime
    @State var sleepAmount = 8.0
    @State var coffeeAmount = 1
    
    @State var alertTitle = ""
    @State var alertMessage = ""
    @State var showingAlert = false
    
    @State var displayBedtime = ""

    let model = SleepCalculator()
    
    static var defaultWakeTime: Date {
        var components = DateComponents()
        components.hour = 7
        components.minute = 0
        return Calendar.current.date(from: components) ?? Date()
    }
    
    var calculateBedTime : String {
        let components = Calendar.current.dateComponents([.hour, .minute], from: desiredWakeTime)
        
        let hour = (components.hour ?? 0) * 60 * 60
        let minute = (components.minute ?? 0) * 60
        do {
            let prediction = try model.prediction(wake: Double(hour + minute), estimatedSleep: sleepAmount, coffee: Double(coffeeAmount))
            
            let sleepTime = desiredWakeTime - prediction.actualSleep
            
            let formatter = DateFormatter()
            formatter.timeStyle = .short
            
            return formatter.string(from: sleepTime)
        } catch {
            alertTitle = "Error"
            alertMessage = "Sorry, calculating bedtime encountered an issue. Please try again later."
            showingAlert = true
        }
        return ""
    }
    
    var body: some View {
        NavigationView {
            Form {
                Section(header: Text("When do you want to wake up?")) {
                    DatePicker("Please enter a time", selection: $desiredWakeTime, displayedComponents: .hourAndMinute)
                        .labelsHidden()
                        .datePickerStyle(WheelDatePickerStyle())
                }
                Section(header: Text("Desired amount of sleep")) {
                    Stepper(value: $sleepAmount, in: 4...12, step: 0.25) {
                        Text("\(sleepAmount, specifier: "%g") hours")
                    }
                }
                Section(header: Text("Daily coffee intake")) {
                    Stepper(value: $coffeeAmount, in: 1...20) {
                        if coffeeAmount == 1 {
                            Text("1 cup")
                        } else {
                            Text("\(coffeeAmount) cups")
                        }
                    }
                }
                Section() {
                    VStack(alignment: .leading) {
                        Text("Your ideal bedtime is")
                        Text(calculateBedTime)
                    }
                }
            }.navigationBarTitle(Text("🛌 Better Rest"))
                .navigationBarItems(trailing:
                    Button(action: {
                        self.alertTitle = "You should wake up at"
                        self.alertMessage = self.calculateBedTime
                        self.showingAlert = true
                    }) {
                        Text("Calculate")
                })
                .alert(isPresented: $showingAlert) {
                    Alert(title: Text(alertTitle), message: Text(alertMessage), dismissButton: .default(Text("OK")))
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```



## Project 5

```swift
//
//  ContentView.swift
//  Word Scramble
//
//  Created by Academia on 5/13/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

extension Array { // Produces possible combinations of elements in an array
    var combinationsWithoutRepetition: [[Element]] {
        guard !isEmpty else { return [[]] }
        return Array(self[1...]).combinationsWithoutRepetition.flatMap { [$0, [self[0]] + $0] }
    }
}

struct ContentView: View {
    @State var usedWords = [String]()
    @State var rootWord = "Hello"
    @State var newWord = ""
    
    @State var errorTitle = ""
    @State var errorMessage = ""
    @State var showingError = false
    
    @State var checkWord = ""
    @State var checkOutcome = ""
    @State var checkedWords = [String]()
    
    @State var generateUsing = ""
    @State var generatedPossibilities = [String]()
    
    func startGame() {
        // 1. Find the URL for start.txt in our app bundle
        if let startWordsURL = Bundle.main.url(forResource: "start", withExtension: "txt") {
            // 2. Load start.txt into a string
            if let startWords = try? String(contentsOf: startWordsURL) {
                // 3. Split the string up into an array of strings, splitting on line breaks
                let allWords = startWords.components(separatedBy: "\n")
                // 4. Pick one random word, or use "silkworm" as a sensible default
                rootWord = allWords.randomElement() ?? "silkworm"
                return // If we are here everything has worked, so we can exit
            }
        }
        // Otherwise there was a problem – trigger a crash and report the error
        fatalError("Could not load start.txt from bundle.")
    }
    
    func addNewWord() {
        let answer = newWord.lowercased().replacingOccurrences(of: " ", with: "")
        guard answer.count > 0 else {
            return
        }
        
        guard isOriginal(word: answer) else {
            wordError(title: "Word used already", message: "Be more original")
            return
        }
        
        guard isPossible(word: answer) else {
            wordError(title: "Word not recognized", message: "You can't just make them up, you know!")
            return
        }
        
        guard isReal(word: answer) else {
            wordError(title: "Word not possible", message: "That isn't a real word.")
            return
        }
        
        usedWords.insert(answer, at: 0)
        newWord = ""
    }
    
    func wordError(title: String, message: String) {
        errorTitle = title
        errorMessage = message
        showingError = true
    }
    
    func isOriginal(word: String) -> Bool {
        !usedWords.contains(word)
    }
    
    func isPossible(word: String) -> Bool {
        var tempWord = rootWord
        
        for letter in word {
            if let pos = tempWord.firstIndex(of: letter) {
                tempWord.remove(at: pos)
            } else {
                return false
            }
        }
        
        return true
    }
    
    func isReal(word: String) -> Bool {
        let checker = UITextChecker()
        let range = NSRange(location: 0, length: word.utf16.count)
        let misspelledRange = checker.rangeOfMisspelledWord(in: word, range: range, startingAt: 0, wrap: false, language: "en")
        
        return misspelledRange.location == NSNotFound
    }
    
    func check() {
        if isReal(word: checkWord) {
            checkOutcome = "\(checkWord) is valid"
        } else {
            checkOutcome = "\(checkWord) is not valid"
        }
        checkedWords.insert(checkOutcome, at: 0)
        checkWord = ""
    }
    
    func generate() {
        generatedPossibilities = []
        let letters = generateUsing.lowercased().replacingOccurrences(of: " ", with: "").map(String.init)
        for possibility in letters.combinationsWithoutRepetition {
            if isReal(word: possibility.joined()) && possibility != [] {
                generatedPossibilities.insert(possibility.joined(), at: 0)
            }
        }
        generatedPossibilities = Array(Set(generatedPossibilities)).sorted { // Sort by longest first
            $0.count > $1.count
        }
    }
    
    var body: some View {
        TabView {
            NavigationView {
                VStack {
                    TextField("Enter word to check", text: $checkWord, onCommit: check)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .autocapitalization(.none)
                        .padding()
                    List(checkedWords, id: \.self) {
                        Image(systemName: $0.suffix(8) == "is valid" ? "checkmark.circle.fill" : "xmark.circle.fill")
                        Text($0)
                            .foregroundColor($0.suffix(8) == "is valid" ? .green : .red)
                    }
                }.navigationBarTitle(Text("👾 Word Scramble"))
            }.tabItem {
                Image(systemName: "checkmark.seal.fill")
                Text("Validate")
            }
            .tag(0)
            
            
            NavigationView {
                VStack {
                    TextField("Enter letters to generate words", text: $generateUsing, onCommit: generate)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .autocapitalization(.none)
                        .padding()
                    List(generatedPossibilities, id: \.self) {
                        Image(systemName: "\($0.count).circle")
                        Text($0)
                    }
                }.navigationBarTitle(Text("👾 Word Scramble"))
            }.tabItem {
                Image(systemName: "lightbulb.fill")
                Text("Enumerate")
            }
            .tag(1)
            
            NavigationView {
                VStack {
                    HStack {
                        Text("Root word:").font(.largeTitle)
                        Text(rootWord).font(.largeTitle).bold()
                    }
                    TextField("Make words with letters in \(rootWord)", text: $newWord, onCommit: addNewWord)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .autocapitalization(.none)
                        .padding()
                    List(usedWords, id: \.self) {
                        Image(systemName: "\($0.count).circle")
                        Text($0)
                    }
                }.navigationBarTitle(Text("👾 Word Scramble"))
                    .navigationBarItems(trailing: Button(action: {
                        self.startGame()
                    }) {
                        Text("New Challenge")
                    })
                    .onAppear(perform: startGame)
                    .alert(isPresented: $showingError) {
                        Alert(title: Text(errorTitle), message: Text(errorMessage), dismissButton: .default(Text("OK")))
                }
            }.tabItem {
                Image(systemName: "rosette")
                Text("Practice")
            }
            .tag(2)
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

## Project 6

```swift
//
//  ContentView.swift
//  Animations
//
//  Created by Academia on 5/15/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct ContentView: View {
    @State var size: CGFloat = 1
    @State var shouldIncrement = true
    @State var rotationAmount = 0.0
    
    @State var dragAmount = CGSize.zero
    
    let letters = Array("Hello SwiftUI")
    @State var enabled = false
    
    @State var isShowingRed = false
    var body: some View {
        NavigationView {
            TabView {
                VStack {
                    Spacer()
                    Button(shouldIncrement ? "Hello, World!" : "Bye World") {
                        self.size += self.shouldIncrement ? 0.1 : -0.1
                        if self.size > 2 {
                            self.shouldIncrement = false
                        } else if self.size < 1 {
                            self.shouldIncrement = true
                        }
                    }
                    .padding(50)
                    .background(Color.red)
                    .foregroundColor(.white)
                    .clipShape(Capsule())
                    .scaleEffect(size)
                    .animation(.default)
                    
                    Spacer()
                    
                    Button("Flip me") {
                        withAnimation {
                            self.rotationAmount += 360
                        }
                    }
                    .padding(50)
                    .background(Color.purple)
                    .foregroundColor(.white)
                    .clipShape(Circle())
                        .rotation3DEffect(.degrees(rotationAmount), axis: (x: 0, y: 1, z: 0)) // Explicit animation
                    Spacer()
                }.tabItem {
                    Image(systemName: "1.square.fill")
                    Text("First")
                }
                
                VStack {
                    LinearGradient(gradient: Gradient(colors: [.blue, .yellow]), startPoint: .topLeading, endPoint: .bottomTrailing)
                        .frame(width: 300, height: 200)
                        .clipShape(RoundedRectangle(cornerRadius: 10))
                        .offset(dragAmount)
                        .gesture(
                            DragGesture()
                                .onChanged { self.dragAmount = $0.translation }
                                .onEnded { _ in
                                    withAnimation(.spring()) {
                                        self.dragAmount = .zero
                                    }
                            }
                    )
                }.tabItem {
                    Image(systemName: "2.square.fill")
                    Text("Second")
                }
                
                HStack(spacing: 0) {
                    ForEach(0..<letters.count) { num in
                        Text(String(self.letters[num]))
                            .padding(5)
                            .font(.title)
                            .background(self.enabled ? Color.blue : Color.red)
                            .offset(self.dragAmount)
                            .animation(Animation.default.delay(Double(num) / 20))
                    }
                }
                .gesture(
                    DragGesture()
                        .onChanged { self.dragAmount = $0.translation }
                        .onEnded { _ in
                            self.dragAmount = .zero
                            self.enabled.toggle()
                    }
                ).tabItem {
                    Image(systemName: "3.square.fill")
                    Text("Third")
                }
                
                VStack {
                    Button("Tap Me") {
                        withAnimation {
                            self.isShowingRed.toggle()
                        }
                    }
                    
                    if isShowingRed {
                        Rectangle()
                            .fill(Color.red)
                            .frame(width: 200, height: 200)
                            .transition(.asymmetric(insertion: .scale, removal: .opacity))
                    }
                }.tabItem {
                    Image(systemName: "4.square.fill")
                    Text("Fourth")
                }
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

## Project 7

### ContentView

```swift
//
//  ContentView.swift
//  iExpense
//
//  Created by Academia on 5/17/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct ExpenseItem: Identifiable, Codable {
    let id = UUID() // Universally unique identifier
    let name: String
    let type: String
    let amount: Int
}

class Expenses: ObservableObject {
    @Published var items = [ExpenseItem]()
    
    init() {
        if let items = UserDefaults.standard.data(forKey: "Items") {
            if let decoded = try? JSONDecoder().decode([ExpenseItem].self, from: items) {
                self.items = decoded
                return
            }
        }
        
        self.items = []
    }
}

struct ContentView: View {
    @State private var showingAddExpense = false
    
    @ObservedObject var expenses = Expenses()
    
    var body: some View {
        NavigationView {
            VStack {
                List {
                    ForEach(expenses.items) { item in
                        HStack {
                            VStack(alignment: .leading) {
                                Text("\(item.name)").font(.title)
                                Text("\(item.type)").font(.caption)
                            }
                            Spacer()
                            Text("\(item.amount)")
                        }.padding(.horizontal)
                    }
                    .onDelete(perform: removeItem)
                }
            }.navigationBarTitle("iExpense")
                .navigationBarItems(leading: EditButton(), trailing: Button(action: {
                    self.showingAddExpense = true
                }) {
                    Image(systemName: "plus.circle")
                })
                .sheet(isPresented: $showingAddExpense) {
                    AddView(expenses: self.expenses)
            }
        }
    }
    
    func removeItem(at offsets: IndexSet) {
        expenses.items.remove(atOffsets: offsets)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

### AddView

```swift
//
//  AddView.swift
//  iExpense
//
//  Created by Academia on 5/20/20.
//  Copyright © 2020 JW. All rights reserved.
//

import SwiftUI

struct AddView: View {
    @State private var name = ""
    @State private var type = "Personal"
    @State private var amount = ""
    static let types = ["Business", "Personal"]
    
    @ObservedObject var expenses: Expenses
    
    @Environment(\.presentationMode) var presentationMode
    
    var body: some View {
        NavigationView {
            Form {
                TextField("Name", text: $name)
                
                Picker("Type", selection: $type) {
                    ForEach(Self.types, id: \.self) {
                        Text($0)
                    }
                }
                
                TextField("Amount", text: $amount)
                    .keyboardType(.numberPad)
            }.navigationBarTitle("Add new expense")
                .navigationBarItems(trailing: Button("Save") {
                    if let actualAmount = Int(self.amount) {
                        let item = ExpenseItem(name: self.name, type: self.type, amount: actualAmount)
                        self.expenses.items.append(item)
                        
                        if let encoded = try? JSONEncoder().encode(self.expenses.items) {
                            UserDefaults.standard.set(encoded, forKey: "Items")
                        }
                        
                        self.presentationMode.wrappedValue.dismiss()
                    }
                })
        }
    }
}

struct AddView_Previews: PreviewProvider {
    static var previews: some View {
        AddView(expenses: Expenses())
    }
}
```

