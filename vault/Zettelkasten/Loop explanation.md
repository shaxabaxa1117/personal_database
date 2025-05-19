День : 2024-05-03 
Время : 15-19

Status : #Programming  


# 👨‍💻Loop explanation


```dart

  

var num1 =int.parse(stdin.readLineSync() ?? '0');

  

int answer = 1;

for (var i = 1; i <= num1; i++) {

   answer = answer * i;

  

}

print('фактариал числа $num1 = $answer');

  
  

}
```

```ad-info

i увеличивается на 1 после каждой итерации  
А не перед  
while(i<10)  
{  
something  
i++  
}  
Типа такого  
Сначала код выполняется  
Потом i увеличивается
```


---
# References
[[Basics of dart]]

