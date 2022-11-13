runApp - запускает "Окна" приложения 
Функция принимает в себя объект типа [[Widget]] 
```dart 
import 'package:flutter/material.dart';// подключаем библиотеку material
void main() {
  runApp(
      new MaterialApp(
          home: new Text('Hello World!')
          )
  );
}
```

В качестве параметра мы передали объект [[MaterialApp]] в параметре [[home]] мы передали виджет [[Text Widget]]


