#Programming 
# Basics of dart



# [[Factory]] 

Dart is programming language which is use in the<mark style="background: #FF5582A6;"> Flutter.</mark>  

1. Type of veriable: Symbol  
    usage: _Symbel name_of_veriable = # char_  
    2)the type of data in _var_ can  be changed, while in dynamic it is possible.
    
2. method _.runtimeType_ can show the type of value( Int, Boolean, String and so on)
    

типы данных

---

|Примитивные|Продвинутые|
|:-:|---|
|int|const|
|double|final|
|bool|dynamic|
|String|var|

Late variables

[https://dart.dev/language/variables#late-variables](https://dart.dev/language/variables#late-variables)

The `late` modifier has two use cases:

- Declaring a non-nullable variable that's initialized after its declaration.
- Lazily initializing a variable.

Often Dart's control flow analysis can detect when a non-nullable variable is set to a non-null value before it's used, but sometimes analysis fails. Two common cases are top-level variables and instance variables: Dart often can't determine whether they're set, so it doesn't try.

If you're sure that a variable is set before it's used, but Dart disagrees, you can fix the error by marking the variable as `late`:

dart

```dart
late String description;

void main() {
  description = 'Feijoada!';
  print(description);
}
```

content_copy

_warning_Notice

If you fail to initialize a `late` variable, a runtime error occurs when the variable is used.

4. _&&_ - means *and
    
5. _||_ - means _or_
    
6. |`value1 ?? value2`|
    
    Если значение `value1` (значение слева от оператора ??) не равно `null`, то оператор возвращает именно это значение value1. Если же это значение равно `null`, то оператор ?? возвращает значение value2 (справа от оператора).
    

|||
|---|---|
|`void` `main() {`  <br>  <br>    `int? num1 = 23;`  <br>  <br>    `int num2 = num1 ?? 0;`  <br>  <br>    `print(num2);`        `// 23`  <br>  <br>    `num1 =` `null``;`  <br>  <br>    `num2 = num1 ?? 0;`  <br>  <br>    `print(num2);`        `// 0`  <br>  <br>`}`||

7. `++ (префиксный инкремент) ++a`
    
    Предполагает увеличение переменной на единицу, например, `z=++y` (вначале значение переменной y увеличивается на 1, а затем ее значение присваивается переменной z)
    

|`int a = 8;`  
  
`int b = ++a;`  
  
`print(a);`   `// 9`  
  
`print(b);`   `// 9`

- `++ (постфиксный инкремент) a++` Также представляет увеличение переменной на единицу, например, `z=y++` (вначале значение переменной y присваивается переменной z, а потом значение переменной y увеличивается на 1) |`int a = 8;`  
      
    `int b = a++;`  
      
    `print(a);`   `// 9`  
      
    `print(b);`   `// 8`|  
    
- `-- (префиксный декремент) --a` уменьшение переменной на единицу, например, `z=--y` (вначале значение переменной y уменьшается на 1, а потом ее значение присваивается переменной z) |`int a = 8;`  
      
    `int b = --a;`  
      
    `print(a);`   `// 7`  
      
    `print(b);`   `// 7`|  
    
- `-- (постфиксный декремент) a--` `z=y--` (сначала значение переменной y присваивается переменной z, а затем значение переменной y уменьшается на 1) `int a = 8;`  
      
    `int b = a--;`  
      
    `print(a);`   `// 7`  
      
    `print(b);`   `// 8`|

8. import "dart:io" - is for interaction with other information console
    
9.  `String feeling = stdin.readLineSync()!` ; Here `!` shows that value won't be null, if so there will be error.  
     `String? feeling = stdin.readLineSync();` ; Here `?` shows that value can be null and non-
    
    nullable;
    
10. `var x = int.parse(stdin.readLineSync() ?? '0');`
    
    `stdin.readLineSync()`: Этот вызов считывает строку введенную пользователем из консоли (стандартного ввода).
    
    `?? '0'`: Это называется оператором null-aware (`??`). Если результат `stdin.readLineSync()` равен null, то вместо null будет использована строка `'0'`.
    
    `int.parse(...)`: Этот вызов конвертирует строку в целое число.
    
11. `isPrime` - функция, которая принимает число и возвращает `true`, если оно простое, и `false` в противном случае.  
    if (`isPrime(userInput)`) {
    

    print('$userInput - простое число.');

  } else {

   print('$userInput - не простое число.');

  }  

  [[Function]]
12)
```dart

|`value1 ?? value2`|

```
Если значение `value1` (значение слева от оператора ??) не равно `null`, то оператор возвращает именно это значение value1. Если же это значение равно `null`, то оператор ?? возвращает значение value2 (справа от оператора).