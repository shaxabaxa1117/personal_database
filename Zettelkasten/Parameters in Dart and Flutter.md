День : 2024-04-16 
Время : 16-13

Status : #Programming  


# 👨‍💻Parameters in [[Dart]] and [[Flutter]] 

So parameter are really used in Flutter so it is essential understand what it is.

## Casual parameters
```dart
void main(){
sayHi('Shakhzod')
}

void sayHi(String name){          // this is required parameter
print('$name. How are you doing?')


}
```
## Not required parameters
```dart
void main(){
sayHi('Shakhzod'/nothing)
}

void sayHi([String name]){    //[]      // this is NOT required parameter
print('$name. How are you doing?')


}
```

## Named parameters (the most used one in [[Flutter]])
```dart
void main(){
sayHi('Shakhzod'/nothing)
}

void sayHi({String name}){   //{}       // this is NAMED NOT required parameter
print('$name. How are you doing?')


}
```
## Required Named parameters (the most used one in [[Flutter]])
```dart
void main(){
sayHi('Shakhzod')
}

void sayHi({ required String name}){   //{required ...}       // this is NAMED REQUIRED parameter
print('$name. How are you doing?')


}
```
---
# References

https://dart.dev/language/functions#parameters
[[Basics of dart]]
[[Flutter]] 