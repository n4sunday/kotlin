# Kotlin


### 🚀 ประโยชน์ของ Kotlin

- ชัดเจนและรัดกุม (Expressive and concise)
- โค้ดมีความปลอดภัยกว่า (Safer code)
- ทำงานร่วมกับ Java ได้ (Interoperable)
- สร้างมาเพื่อให้ทำงานพร้อมกัน (Structured Concurrency)

https://kotlinlang.org/docs/home.html
https://kotlinlang.org/docs/kotlin-pdf.html

### 🚀 Get Started
#### Hello World
```kotlin
fun main(){
    println("Hello World")
}
```
#### Data Type
**Integer types**
- `Long` (64 Bit)
- `Int` (32 Bit)
- `Short` (16 Bit)
- `Byte` (8 Bit)

**Floting Point types**
- `Double` (64 bit)
- `Float` (32 bit)

**Unsigned Integer types**
- `UByte` (8 bit) : 0 - 255
- `UShort` (16 bit) : 0 - 65,535
- `UInt` (32 bit) : 0 - (2³² - 1)
- `ULong` (64 bit) : 0 - (2⁶⁴ - 1)


**Other types**
- `Char` (16 bit)
- `Boolean` (8 bit)

#### Variables
```kotlin
// Colon Notation
var width: Int = 77
var length: Double = 176.5
```
``เมื่อ Compile จะไม่สามารถเปลี่ยนแปลง Type ได้``

##### Mutable and Immutable
**Mutable (สามารถเปลี่ยนได้)**
```kotlin
var name = "Sunday"
```
**Immutable (ไม่สามารถเปลี่ยนได้)**
```kotlin
val pi = 3.14
```

##### Other Variable
```kotlin
 val hex = 0x0F
 val binary = 0b00001011
```

``use _``
```kotlin
val oneMillion = 1_000_000
val creditCardNumber = 1234_5678_9012_3456L
val socialSecurityNumber = 999_99_9999L
val hexBytes = 0xFF_EC_DE_5E
val bytes = 0b11010010_01101001_10010100_10010010
```

``String``
```kotlin
val str = "abcd"
 println(str.uppercase()) 
 // "ABCD"
 println(str) 
 // "abcd"

val s = "abc"
println("s has ${s.length} characters")
```

#### Conditionals
##### Ranges
```kotlin
val numberOfStudent = 50
if(numberOfStudent in 1..100) {
    println(numberOfStudent)
}
// 50
```
##### When
```kotlin
when (results) {
    0 -> println("No result")
    in 1..39 -> println("Got results!")
    else -> println("That's a lot of results!")
}
// Thai's a lot of results!
```
##### For Loops
```kotlin
var pets = arrayOf("Dog","Cat", "Rabbit")
for (item in pets) {
    println(item + " ")
}
// Dog Cat Rabbit

// Elements and Indexes
for((index, item) in pets.withIndex()) {
    println("Item at $index is $element\n")
}
// Item at 0 is Dog
// Item at 1 is Cat
// Item at 2 is Rabbit

// Step sizes and ranges
for (i in 1..5) {
    print(i)
}
// 12345

for (i in 5 downTo 1) {
    print(i)
}
// 54321

for (i in 3..6 step 2) {
    print(i)
}
// 35

for (i in 'd'..'g') {
    print(i)
}
// defg
```

##### Repeat Loops
```kotlin
repeat(2) {
    print("Hello!")
}
//Hello!;Hello!
```

#### Null Safety
Safe call operator
```kotlin
var numberOfBook: Int? = null
```
Test value null
```kotlin
var numberOfBooks = 10
if (numberOfBooks != null) {
    numberOfBooks = numberOfBooks.dec()
}
// Kotlin use safe call
var numberOfBook = 10
numberOfBooks = numberOfBook?.dec()

// Noll Pointer Exception
val len = s!!.length
```

##### Elvis
```kotlin
// default value
numberOfBooks = numberOfBooks?.dec() ?: 0
```

#### List and Array
##### List
`Immutable List` (List ที่ไม่สามารถเปลี่ยนแปลงค่าได้)
```kotlin
val instruments = listOf("trumpet","piano","violin")
println(instruments)
// "trumpet","piano","violin"
```
`Mutable List` (List ที่สามารถเปลี่ยนแปลงค่าได้)
```kotlin
val myList = mutableListOf("trumpet","piano","violin")
myList.remove("violin")
```

##### Array
- for sorting or search
- fix size (Immutable)

```kotlin
import java.util.*val pets = arrayOf("Dog","Cat", "Rabbit")
println(java.util.Arrays.toString(pets))
// ["Dog","Cat", "Rabbit"]

// Create array muti tyle
val mix = arrayOf("Solidity",2)

// Create array fix type
val mix = intArrayOf(1,2,3)

// Combine array
val number1 = intArrayOf(1,2,3)
val number2 = intArrayOf(4,5,6)
val combined = number1 + number2
println(Arrays.toString(combined))
```


### 🚀 Functions

- Default parameters(ค่าตั้งต้น)
- Required parameters(บังัคับให้ใส่ค่า)
- Named arguments(ตั้งชื่อตัวแปรได้)

#### Default parameters
```kotlin
fun drive(speed: String = "fast") {
    println("driving $speed")
}

drive()
// driving fast
```

#### Required parameter
```kotlin
fun tempToday(day: String, temp: Int) {
    println("Today is $day and it's $temp degrees.")
}
```

#### Default and Required oaraneters
```kotlin

fun mobile(color: String="black", model: String) {
    // ...
}
```

#### Named arguments 
```kotlin
car(str, model="Honda", color="red")
```

#### Compact Functions
Compact Functions เป็นรูปแบบอย่างหนึ่งในการเขียนโค้ดสำหรับ Function ที่จะช่วยทำให้คำสั่งที่อยู่ใน Function นั้น ๆ อยู่ในรูปแบบที่สั้นกระชับมากขึ้น เหมาะกับ Function ที่มี Return Type และมีคำสั่งข้างในไม่เยอะเพื่อลดจำนวนโค้ดที่ไม่จำเป็นให้น้อยลง

`EX Nomal Function`
```kotlin
fun calculateArea(width: Int, height: Int): Int {
    return width * height
}

fun createSampleUser(): Person {
    return Person.Builder()
        .name("John")
        .age(28)
        .job("Software Engineer")
        .create()
}
```
เมื่อเขียนในรูปแบบของ Compact Function จะไม่ต้องใส่เครื่องหมาย `{` กับ `}` และใช้เครื่องหมาย `=` ต่อท้าย Function ได้เลย
`EX Compact Function`
```kotlin
fun calculateArea(width: Int, height: Int) = width * height

fun createSampleUser(): Person = 
    Person.Builder()
        .name("John")
        .age(28)
        .job("Software Engineer")
        .create()
        .create()
```
จะเห็นว่า Compact Function จะใส่ Return Type หรือไม่ก็ได้ โดยการใส่ Return Type จะช่วยให้อ่านและเข้าใจได้ง่ายเท่านั้น ไม่มีผลต่อการทำงานใด ๆ ของ Compact Function

#### Lambdas and higher-order function
##### Lambdas
```kotlin
val waterFilter: (Int) -> Int = {level -> level / 2 }
```

```kotlin
val enc1: (String) -> String = { input -> input.toUpperCase() }
println(encodeMsg("abc, enc1"))
```

```kotlin
fun enc2(input:String): String = input.reversed()
encodeMessage("abc", ::enc2)
```

`Ex Nomal Function`
```kotlin
fun compare(a: String, b: String) {
    return a.length < b.length
}
```

`Ex Lambda Expression`
```kotlin
// Function type variable
val compare: (String, String) -> Boolean = { a, b -> a.length < b.length
}

// Anonymous function
fun max(string: String, compare:(String, String) -> Boolean)

max("1234", { a, b -> a.length < b.length})
```

`Lambda Expression จะมี Syntax แบบเต็มดังนี้`
```kotlin
val sum: (Int, Int) -> Int = { x: Int, y: Int -> 
   x + y 
}
```
- โค้ดทั้งหมดของ Lambda Expression จะอยู่ในเครื่องหมายปีกกาเสมอ
- Parameter จะขึ้นอยู่กับ Function Type ที่ประกาศไว้ โดยข้างใน Lambda Expression จะกำหนดเป็นชื่อตัวแปรใด ๆ ก็ได้ (ในตัวอย่างกำหนดชื่อเป็น x และ y)
- คำสั่งที่จะทำงานใน Lambda Expression จะอยู่ต่อท้ายเครื่องหมาย > เสมอ
- ผลลัพธ์ที่ได้จากคำสั่งในบรรทัดสุดท้าย จะกลายเป็นผลลัพธ์ของ Lambda Expression เสมอ จึงไม่จำเป็นต้องใส่ Keyword ว่า return ไว้ที่บรรทัดสุดท้าย

เขียน Lambda Expression ให้อยู่ในรูปแบบย่อ
```kotlin
val sum: (Int, Int) -> Int = { x, y -> x + y }
val sum = { x: Int, y: Int -> x + y }
```
กรณีที่ Lambda Expression มี Parameter แค่เพียงตัวเดียว สามารถใช้ `it`
```kotlin
val filter: (String) -> Boolean = { it.length == 5 }
```
มี Parameter บางตัวที่ไม่ใช้งานก็สามารถใช้เครื่องหมาย `_`
```kotlin
val filterWithIndex: (Int, String) -> Boolean = { _, value ->    
     value.length == 5
}
```

##### Higher-order Functions
Higher-order Functions คือ Function ใด ๆ ก็ตามที่รับ Function เป็น Parameter หรือมี Return Type เป็น Function
```kotlin
fun find(date: Array<String>, predicate: (String) -> Boolean): String? {
    for (element in data) {
        if(predicate(element)) {
          return element  
        }
    }
    return null
}
```

```kotlin
val items = arrayOf("Apple", "Banana", "Coconut")
val result1: String? = find(items) { it.contains("A") } // Result: "Apple"
val result1: String? = find(items) { it.length == 6 } // Result: "Banana"
```

#### List Filter

`Ex one parameter`
```kotlin
val ints = listOf(1,2,3)
ints.filter { it > 0 }
```
##### Eager and Lazy Filters
- `Eager`: ถูกประมวลผลทุกครั้ง แม้ข้อมูลไม่ได้ถูกวนำมาใช้งาน
- `Lazy`: ถูกประมวลผลเมื่อถูกเรียกใช้งานระหว่าง runtime 

##### Convert List
- map() : convert all item in function and return list
```kotlin
val numbers = setOf(1,2,3)
println(numbers.map {it * 3})
// [3, 6 ,9]
```

- flatten() : combine list and return one list  
```kotlin
val numberSets = listOf(setOf(1,2,3), setOf(4,5), setOf(1,2))
println(numberSets.flatten())
// [1, 2 ,3 ,4 ,1 ,2]
```