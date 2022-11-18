TabBar (Эквивалент CupertinoTabBar) - это стек экранов, где виден только один, а пользователь может перемещаться из одного в другой, как и [[bottomNavigationBar в Flutter]]. 

Виджет TabController будет сам отвечать за отображение текущей вкладки.
Я могу сам его создать, но это потребует дополнительной работы, так что проще всего использовать [[DefaultTabController Flutter]] в качестве значения свойства `home` в виджете [[MaterialApp]] 

Однако сделав это, нужно будет указать в `TabController` сколько будет всего вкладок 


---
## Пример использования
1. Test
```dart
import "package:flutter/material.dart";  
import 'package:mvc_pattern/mvc_pattern.dart';  
  
class MyTabBar extends StatelessWidget{  
  @override  
  Widget build(BuildContext context) {  
      return MaterialApp(  
        home: DefaultTabController(  
          length: 3,  
          child: Scaffold(  
            appBar: AppBar(title: Text("Flutter Demo"),  
            bottom: const TabBar(  
              tabs: [  
                Tab(icon: Icon(Icons.new_label)),  
                Tab(icon: Icon(Icons.new_label)),  
                Tab(icon: Icon(Icons.new_label)),  
              ],  
            ),  
            ),  
            body: const TabBarView(  
              children: [  
                Center(child:Text("fuck")),  
                Center(child:Text("me")),  
                Center(child:Text("please")),  
              ],  
            ),  
          ),  
        ),  
      );  
  }  
  
}
```