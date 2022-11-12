Еще одно использование ключевого слова `object` - это создавать вспомогательные объекты

```kotlin
class BigBoobaHandler{
	companion object
}
```

Companion - это  [[Синглтон]], который связан с классом, это похоже на [[static]] методы в [[Java]] 

---
## Объявление 
```kotlin
class BigBooba{
	var c:Int = 1
	companion object{
		fun doBoobaThings(){
			/*   */
		}
	}
}

fun main(){
	BigBooba.doBoobaThings()
}
```

Главное приемущество Companion - это доступ к [[private]] членам класса 

```kotlin
class BigBooba{
	private var c:Int = 1
	companion object{
		fun doBoobaThings(){
			print(c)
		}
	}
}

fun main(){
	BigBooba.doBoobaThings()
}

// output: 1
```

---
## Companion может иметь имя 
Иногда можно увидеть companion object с именем, к примеру:
```kotlin
class BigBooba{
	private var c:Int = 1
	companion object Booba{
		fun doBoobaThings(){
			print(c)
		}
	}
}

fun main(){
	BigBooba.doBoobaThings()
}
```

Разницы особо нет в использовании именованного объекта и обычного, отличия появляются если вы хотите вызвать этот объект из Java кода 