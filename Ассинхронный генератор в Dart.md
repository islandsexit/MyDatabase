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