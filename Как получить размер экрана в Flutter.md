```dart
class Body extends StatelessWidget {  
  
  
  @override  
  Widget build(BuildContext context) {  
    Size size = MediaQuery.of(context).size;  
    return Column(  
      children: [  
        Container(  
          height: size.height*0.2,  
          color: Colors.lightBlue,  
        )  
      ],  
    );  
  }  
}
```