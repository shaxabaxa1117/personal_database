День : 2024-03-26 
Время : 20-35

Status : #Programming 


# Static

Static allows us to use the methods of class without creating its object;

<mark style="background: #FFB8EBA6;">Example:</mark>
```dart
import 'dart:math';

  

void main{

    Random random = Random();// here is how we would use method nextInt();(of class - Random) 
int a = random.nextInt(25);//if it was not stat  
//But this class(or method) is static so we are able to use its methods without creating its object

int a = Random().nextInt(25); // here it is shown.



}
```



Below it is shown that we can not use the  `static` method in the object. The `static` method can be used only with the class.


```dart

class Animal {
int hp = 0;
String name = '';

Animal(this.hp, this.name);
void showName(){
print(name);
}

static String callAllAnimals(){
print('Evertyone, come here');
}

void main(){

String calling = Animal.callAllAnimal;

print(Animal.callAllAnimal);

Animal bird = Animal(10, 'BaBaY')

bird.callAllAnimal //ошибка

}


}
```


Static делает свойство общим для всех машин и позволяет не создавать в экземпляре класса новые значения.
Поэтому делают `static const`

<iframe width="560" height="315" src="https://www.youtube.com/embed/L0Cd3yCauGw?si=zAZZ5TiuVX0pfxMF&amp;start=870" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---
# References
[[Dart]]