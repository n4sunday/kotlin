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
<<<<<<< HEAD

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
=======
>>>>>>> 45bbdb4843ecc6d865c94f517124cea4114f260b
