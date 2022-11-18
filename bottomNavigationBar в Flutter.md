





-----
# Пример использования 

1. Тест
```dart
import "package:flutter/material.dart";  
  
  
class BottomApp extends StatefulWidget{  
  @override  
  State<StatefulWidget> createState() {  
    return _BottomApp();  
  }  
  
}  
  
class _BottomApp extends State{  
  var _currentPage = 0;  
  
  final _pages = [  
    const Text("Page 1"),  
    const Text("Page 2"),  
    const Text("PAge 3")  
  ];  
  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      title: "Flutter Playground",  
      home: Scaffold(  
        body: Center(  
          child: _pages.elementAt(_currentPage),  
        ),  
        bottomNavigationBar: BottomNavigationBar(  
          items: const [  
            BottomNavigationBarItem(  
                icon: Icon(Icons.accessibility_new),  
                label: "Page 1",  
                backgroundColor: Colors.amber),  
            BottomNavigationBarItem(  
                icon: Icon(Icons.accessibility_new),  
                label: "Page 2",  
                backgroundColor: Colors.lightBlueAccent),  
            BottomNavigationBarItem(  
                icon: Icon(Icons.accessibility_new),  
                label: "Page 3",  
                backgroundColor: Colors.pinkAccent),  
          ],  
          currentIndex: _currentPage,  
          onTap: (int inIndex){  
            setState(() {  
              _currentPage = inIndex;  
            });  
          },  
        ),  
  
      )  
    );  
  }  
  
  
}

```