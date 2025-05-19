	День : 2025-01-12 
Время : 15-52

Status : #Programming  


# 👨‍💻Firekeys

![[Pasted image 20250112155224.png]]

![[Pasted image 20250112155538.png]]
![[Pasted image 20250112155610.png]]

---

## **Работа с собственными классами**

Чтобы работать с Firestore, удобно использовать Dart-классы для представления данных. Вот шаги :

### Создание модели

![[Pasted image 20250112155714.png]]

### Добавление данных через модель

![[Pasted image 20250112155841.png]]

### Чтение данных и преобразование в модель

```dart
DocumentSnapshot doc = await FirebaseFirestore.instance.collection('users').doc('userId123').get();

if (doc.exists) {
  final user = UserModel.fromMap(doc.data() as Map<String, dynamic>, doc.id);
  print(user.name); // John Doe
}
```

### Получение списка моделей

![[Pasted image 20250112160017.png]]


---
# References

