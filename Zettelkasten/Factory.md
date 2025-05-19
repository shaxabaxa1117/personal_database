День : 2024-06-03 
Время : 14-46

Status : #Programming  


# 👨‍💻Factory
```ad-note

Ключевое слово `factory` в Dart на самом деле является синтаксическим <mark style="background: #FF5582A6;">сахаром</mark> для выражения чего-то. Это базовый паттерн, который называется **фабричным методом** или **шаблоном фабричного метода**.
```

```dart

class` Person{

    String name;

    int age;    

    factor` Person(String name, int age)

    {

        if(name.length <2)

        {

            name = "Undefined";

        }

        if(age <1 || age > 110)

        {

            age = 18;

        }

        return Person._create(name, age);

    }

    Person._create(this.name,this.age);

    void display() => print("Name: $name \tAge: $age");

}

void main() {

    Person tom = Person("Tom", 38);

    tom.display();     // Name: Tom    Age: 38

    Person li = Person("L", 100500);

    li.display();    // Name: Undefined    Age: 18

}
```


---
# References

