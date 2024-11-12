## Kotlin基础

### 规范

1. kotlin必须要有主函数作为入口

2. 风格

   1. 驼峰命名函数
   2. 函数括号后空一格

   ```kotlin
   fun bakeChocolateCake(){
       println("ChocolateCakeBaked!")
   }
   
   fun main() {
       val discount: Double = 12.00
       println("hello world")
   }
   ```

### 变量

1. 数据类型和规范

   | **类型**  |                     **可包含的数据类型**                     |                **示例**                |
   | :-------: | :----------------------------------------------------------: | :------------------------------------: |
   | `String`  |                             文本                             | `"Add contact"` `"Search"` `"Sign in"` |
   |   `Int`   |                             整数                             |        `32` `1293490` `-59281`         |
   | `Double`  |                             小数                             |    `2.0` `501.0292` `-31723.99999`     |
   |  `Float`  |    小数（不如 `Double` 精确），数字末尾带有 `f` 或 `F`。     |    `5.0f` `-1630.209f` `1.2940278F`    |
   | `Boolean` | `true` 或 `false`。当只有两个可能的值时，可使用此数据类型。请注意，`true` 和 `false` 是 Kotlin 中的关键字。 |             `true` `false`             |

2. 声明习惯

   ```kotlin
   val count: Int = 2
   ```

3. 字符串模板

   ```kotlin
   fun main() {
       val count: Int = 2
       println("You have $count unread messages")
   }
   ```

   结合大括号输出更复杂的表达式

   ```kotlin
   fun main() {
       val unreadCount = 2
       val readCount = 300
       println("You have ${unreadCount + readCount} messages")
   }
   ```

   ```bash
   You have 302 messages
   ```

4. 类型推断

   编译器可以推断数据类型时，可以省略类型

   ```kotlin
   val count: Int = 2
   val count = 2
   ```

5. 更新变量

   注意 `val` 和 `var` 的区别，val是常量，var是变量，kotlin建议尽量多使用val关键字

6. 反斜杠最为转义字符

   ```kotlin
   println(say \"hello\"")
   ```

7. 字符串可以连接其他类型的字符

   ```kotlin
   fun main() {
   	var notificationsEnabled: Boolean = false
       notificationsEnabled = true
       println("Are notifications Enabled? " + notificationsEnabled)
   }
   ```

### 函数

函数签名：函数名称和其输入统称为函数签名，包含返回值之前的全部内容

1. 定义和调用

   ```kotlin
   fun birthdayGreeting() {
       print("Happy Birthday, Rover!\n")
       print("You are now 5 years old!\n")
   }
   
   fun main() {
       birthdayGreeting()
   }
   ```

2. 声明带有返回值的函数

   默认类型是 `Unit` ， 常用的还有 `String` `Int` 等

   ```kotlin 
   fun birthdayGreeting() : Unit {
       println("Happy Birthday, Rover!");
       println("You are now 5 years old!");
   }
   
   fun main() {
       birthdayGreeting()
   }
   ```

   ```kotlin
   fun birthdayGreeting() : String {
       val nameGreeting = "Happy Birthday, Rover!"
       val ageGreeting = "You are now 5 years old!"
       return "$nameGreeting\n$ageGreeting"
   }
   
   fun main() {
       println(birthdayGreeting())
   }
   ```

3. 添加形参（多个形参）

   ```kotlin
   fun birthdayGreeting(name: String, age: Int) : String {
       val nameGreeting = "Happy Birthday, $name!"
       val ageGreeting = "You are now $age years old!"
       return "$nameGreeting\n$ageGreeting"
   }
   
   fun main() {
       println(birthdayGreeting("Rover", 5))
       println(birthdayGreeting("Bob", 6))
       println(birthdayGreeting("Alice", 7))
   }
   ```

4. 具名实参

   使用具名实参可以更改传参的顺序

   ```kotlin
   println(birthdayGreeting(age = 5, name = "Rex"))
   ```

5. 默认实参

   可以为函数形参指定默认实参，传参时可以只传部分，或者省略

### 练习题

```kotlin
fun moreThanYesterday(timeSpendToday : Int = 0, timeSpendYesterday : Int = 0) : Boolean {
    return timespendToday > timeSpendYesterday
}

fun main() {
    println("today 300, yesterday 400, more than yesterday? "+moreThanYesterday(500 ,400))
}
```

## Kotlin进阶

### 条件语句

if/else 语句

when 语句（类似Switch）

```kotlin
fun main(){
	val trafficLightColor = "Amber"
    
    when(trafficLightColor) {
        "Red" -> println("Stop") 
        "Yellow", "Amber" -> println("Slow") 
        "Green" -> println("Go") 
        else -> println("Invalid traffic-light color")
    }
}
```

### null性

### 类和对象

### 函数