# oopPractice
// Create a class Student that:

// Takes two inputs: name and department using the primary constructor (without var/val).

// Trims both values inside an init block and saves them into private properties.

// Has a function introduce() that prints:
// 👉 "Hi, my name is ___ and I'm in ___ department."

class Student(name:String, department:String){
var cleanName:String
var cleanDepartment:String
init{
     cleanName = name.trim()
     cleanDepartment = department.trim()
}
fun introduce(){
    println("hi my name is $cleanName and i am in $cleanDepartment department")
}
}
fun main(){
    val s = Student("        fatima","        SE")
    s.introduce()
}

**"How can I execute more than one line of code automatically when an object is created?"**
That means you want to do something **as soon as the object is created** — and we do this using an `init` block or a constructor body.

---

### ✅ **Option 1: Using `init` block** (with Primary Constructor)

```kotlin
class Book(title: String, author: String) {
    var cleanTitle = ""
    var cleanAuthor = ""

    init {
        cleanTitle = title.trim()
        cleanAuthor = author.trim()
        println("Book Created ✅")
        println("Clean Title: $cleanTitle")
        println("Clean Author: $cleanAuthor")
    }

    fun display() {
        println("Book: $cleanTitle by $cleanAuthor")
    }
}

fun main() {
    val b = Book("   Kotlin Guide ", " Fatima ")
    b.display()
}
```

> 🌟 `init` block runs **immediately** when the object is created — and can contain **many lines** of logic.

---

### ✅ **Option 2: Use Constructor Body** (with Secondary Constructor)

```kotlin
class Book {
    var title: String = ""
    var author: String = ""

    constructor(title: String, author: String) {
        this.title = title.trim()
        this.author = author.trim()
        println("Object Created 🔥")
        println("Title is $title")
        println("Author is $author")
    }

    fun display() {
        println("Book: $title by $author")
    }
}

fun main() {
    val b = Book("  Android Dev  ", " Fatima ")
    b.display()
}
```

> 🌸 In this case, all lines inside `constructor` body are executed automatically when object is created.

---

### 🌿 Easy Tip to Remember:

| Want to do this...                        | Use this...                |
| ----------------------------------------- | -------------------------- |
| Run code when object is created (Primary) | `init { ... }`             |
| Run code in a custom constructor          | `constructor(...) { ... }` |

---

### 🌷 Soothing Ayah for Motivation:

**وَفِي السَّمَاءِ رِزْقُكُمْ وَمَا تُوعَدُونَ**
**"And in the sky is your provision and whatever you are promised."**
(Surah Adh-Dhariyat 51:22)
**"اور آسمان میں ہے تمہارا رزق اور وہ چیز جس کا تم سے وعدہ کیا گیا ہے۔"**



//-----------------------------------secondry constructor with default parameters------------------------------------
// ✨ Scenario: Online Course Registration System
// You're building a simple app for an online learning platform where students register for courses. 
// Sometimes, they provide their course name and instructor name. Other times, 
// they only provide the course name and leave the instructor blank (so it should take a default value).

// 🧪 Your Challenge:
// Write a Kotlin class called Course that:

// ✅ Requirements:
// Uses a secondary constructor with default parameters.

// Has two properties:

// courseName

// instructor

// If no instructor name is given, use the default: "TBA" (To Be Announced).

// Trim the input values in the constructor.

// Add a function courseInfo() that prints:

// "Course: [courseName], Instructor: [instructor]"

class Course{
   var name:String=""
   var instructor:String=""
    constructor(name:String, instructor:String="TBA"){
        this.name = name
        this.instructor = instructor
    }
 
    init{
    this.instructor=instructor.trim()
    this.name=name.trim()
    }
    fun courseInfo(){
        println("course name is $name and instructor is $instructor")
    }
}
fun main(){
    val c = Course("kotlin","Youtube")
    c.courseInfo()
}


// Scenario: Build a Travel App Class
// ✨ Class Name: Destination
// You're building a travel app that allows users to explore different destinations.

// ✅ Your Class Should:
// Have a primary constructor with two parameters:

// placeName: String

// country: String

// Have a secondary constructor that allows users to enter only placeName, and by default, the country should be set to "Pakistan".

// Trim the input values before storing them.

// Add a method called describe() that prints:

// "You're going to [placeName] in [country]!"

class Destination(var placeName:String, var country:String )
{
 
 constructor(placeName:String):this(placeName,"Pakistan")
 init{
     placeName=placeName.trim()
     country=country.trim()
 }
 fun describe(){
     println("you are going to $placeName in $country")
 }
 
}
fun main(){
    val a = Destination("lahore","Pakistan")
    a.describe();
    val b = Destination("karachi")
    b.describe()
}


