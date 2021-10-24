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

