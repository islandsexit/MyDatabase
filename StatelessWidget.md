StatelessWidget - рекомендуется при неизменяемых виджетах, которые не имеют внутреннего состояния

Вот примеры виджетов, которые наследуются от StatelessWidget (см. [[Наследование в Dart]]):
-   class Text()
-   class FlatButton()
-   class Container()
---
## Объявление своего Виджета

```dart
class MyWidget extends StatelessWidget{
	@override
	Widget build(BuildContext context){
		return /*------------*/
	}
}
```

---
### Пример 

