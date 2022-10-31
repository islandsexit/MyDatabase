
Enum-[[Основы классов в Kotlin|классы]] - это перечисления
В [Котлин](Котлин.md) они записываются так:
```kotlin
enum class Downloading{
	STARTED, LOADING, DONE, FAILED
}
```

Каждая enum-константа является объектом, разделяются запятыми

---
Крч enum - пиздатая тема, с помощью нее можно хранить состояния, это как булевое значение, но только имеет не два состояния

---
### Конструктор классов enum

Классы перечислений могут иметь конструктор 
```kotlin
enum class color Day(val value:Int){
	MONDAY(1), TUESDAY(2), WEDNESDAY(3); //точка с запятой, так нужно делать, чтоб компилятор понл, что дальше идут уже другие члены
	
	fun getDuration(day:Day){
		return value-day.value //value, без this т.к и так понятно
	}
}
```

---

### [[Анонимные классы]]

Enum-константы могут объявлять свои анонимные классы, также  могут перегружать методы базового класса
```kotlin
enum class State{
	WAITING{
		override fun signal() = TALKING
	},
	TALKING{
		override fun signal() = WAITING
	};

	abstract fun signal():State
}
```

---

#### [[Наследование в Kotlin|Рeализация интерфейсов в классах enum]]

Enum-класс может реализовыватьь интерфейс, но не наследоваться от класса.
Чтобы реализовать интерфейс нужно реализовать его либо для всех элементов enum, либо один на всех.
```kotlin
interface Do{
	fun doNow()
	fun doLater()
}

enum class EUMM:Do{
	FIRST{
		override fun doNow() = /* === */
	},
	SECOND{
		override fun doNow() = /* === */
	};
	
	override fun doLater() = /* === */
}
```



