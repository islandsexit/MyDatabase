Сама асинхронная функция должа быть помечена, перед определением ёё тела, ключевым словом [[async в Dart]] и возвращать объект [[Future в Dart]]:
```dart
Future someLongOperation() async{
	/*_____*/
}
```

*Важно*: Функция, которая вызывает `someLongOperation` должна тоже быть помечена [[async в Dart]]
```dart
void invokeSomeLongOperation() async{
	await someLongOperation()
}
```