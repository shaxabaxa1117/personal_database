![[Stateless widgets 2024-04-15 18.13.51.excalidraw | 500]]День : 2024-04-12 
Время : 15-38

Status : #Programming   


# Stateless widgets



- Stateless widgets, as the name implies, are widgets that do not have internal state.
- They are immutable, meaning their properties cannot change once they are built.
- These widgets are ideal for displaying static content that doesn't change based on user interactions or other factors.
- Examples include [[Text]] ,  [[!Icon]],  [[Container]], etc.
```ad-note
So this kind of widget can be used only as kind of 'decoration'. Something that can be seen but not used.

```

--- 


```dart
void main() {

  runApp(const MyApp());

}

  

class MyApp extends StatelessWidget {

  const MyApp({super.key});

  

  @override

  Widget build(BuildContext context) { // function that have to return Widget

    return const Placeholder();

  }

}
```

RESULT
![[Pasted image 20240413172423.png | 200]]
---

```dart

тут можно увидеть применение 

import 'package:flutter/material.dart';

import 'package:flutter/widgets.dart';

  

void main() {

  runApp(const MyApp());

}

  

class MyApp extends StatelessWidget {

  const MyApp({super.key});

//используем stateless widget

  @override

  Widget build(BuildContext context) {

    return  MaterialApp(

      home: Scaffold(

        body:  Container(

          width: double.infinity,

          height: double.infinity,

          color: Colors.blueGrey,

          child: Column(

            children: [

              //appBar

              AppBarWidget(

                text: 'Wramggler is here',

                ), //вызов экземпляра класса

  

              //1-st block

  
  

              //2-nd block

            ],) ,),

        ),

    );

  }

}

  
  
  
  

class AppBarWidget extends StatelessWidget {

  const AppBarWidget({super.key,required this.text});

  

final String text;

  
  

  @override

  Widget build(BuildContext context) {

    return Container(

      padding: const EdgeInsets.all(15),

      color: Colors.white,

      margin: EdgeInsets.only(top: 50),

      child: Row(children: [

        Text(text)

  

      ],),

    );

  }

}
```



---
# References
[[4 types of widgets]]
[[Example of stateless and stateful usage]]