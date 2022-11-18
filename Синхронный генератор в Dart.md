Синхронный генератор :
```dart
Iterable<int> countTo(int max) sync*{
	int i = 0;
	while(i<max){
		yeld i++
	}
};

main(){
	Iterable it = countTo(5);
	Iterator i = it.iterator;
	while(i.moveNext()){
		print(i.current)
	}
}
```

Первое, и самое необычное - это оператор `sync*` перед телом функции.