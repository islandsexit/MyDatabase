Чтобы использовать библиотеку, в игру вступает ключевое слово `import`
```dart
import 'dart:html'
```


Некоторые библиотеки представляются вашим собственным кодом, а некоторые всроены в Dart по умолчанию.
Для встроенных библиотек есть специальные [[URI]], они начиаются со слова `dart:`, еоторое является частью схемы URI.

Если библиотека берется из какого-либо пакета (см. [[Package в Dart]]), то вам стоит использовать `package:` схему:
```dart
import "package:lib.dart"
```

Если библиотека представлена вашей кодовой базой, тогда нужно использовать относительный путь:
```dart
import "../libs/myLibrary.dart"
```

