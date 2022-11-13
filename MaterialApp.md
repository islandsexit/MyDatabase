При создании экземпляра класса **MaterialApp** можно указать параметр **debugShowCheckedModeBanner** со значеним **false** – это скроет надпись “debug”.

```dart
import 'package:flutter/material.dart';
void main() {
  runApp(
      new MaterialApp(
          debugShowCheckedModeBanner: false,// скрываем надпись debug
          home: new Scaffold(
              appBar: new AppBar(title: new Text('Flutter.su')),
              body: new Text('Hello World!')
          )
      )
  );
}
```