В Dart обработка исключений схожа с языками [[Котлин]] и другими C подобными языками

Отличие от других языков в том, что все исключения в Dart не проверяются.

---
## ![[Как бросить исключение в Dart]]
---
## Блок try-catch-finally

Чтобы поймать исключение нужно использовать всеми знакомый блок:
```dart
try{
	smthCanException();
} on FormatException catch (fe){
	print(fe)
} on Exception catch (e){
	print("SomeOtherException"+e)
} catch (u){
	print("UnknownException")
} finally {
	print("All Done")
}
```

Есть пара вещей,  о которых ты должен помнить - **Обрабатывай только те исключения, которые ты ожидаешь**