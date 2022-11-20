```dart
class Body extends StatelessWidget {  
  
  
  @override  
  Widget build(BuildContext context) {  
  // дает нам размер экрана
    Size size = MediaQuery.of(context).size;  
    return Column(  
      children: [  
        Container(  
        // и тут можем получить 20% экрана на контейнер
          height: size.height*0.2,  
          color: Colors.lightBlue,  
        )  
      ],  
    );  
  }  
}
```