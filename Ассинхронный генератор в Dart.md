```dart
Stream<int> countTo(int max) async*{
	int = 0;
	while(i<max){
		yeld i++;
	}
}

main() async{
	Stream s = countTo(5);
	await for(int i in s){
		print(i);
	}
}
```

Первое, и самое необычное - это оператор `async*` перед телом функции.
Она говорит, что это функция генератора, а не просто какая-то хуйня

Второй момент - это использование ключевого слова `yeld` - оно выталкивает значение к [[Stream в Dart]] в цикл for, которое создается за кулисами.

