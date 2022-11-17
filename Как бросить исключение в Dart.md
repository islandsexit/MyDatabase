```dart
throw FormatException("This value is badass!!");
```

Интересно, что в Dart необязательно бросать ошибку в каком-то формате `exception`, тут можно бросить даже строку, как ошибку
```dart
throw "This value is badass!!"
```

Однако лучше не бросать все. что выходит за пределы классов [[Error в Dart]] и [[Exception в Dart]], ведь это пиздец какой дурной тон))



