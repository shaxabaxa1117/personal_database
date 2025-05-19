День : 2024-06-03 
Время : 14-43

Status : #Programming  


# 👨‍💻HTTP

[[Using JSON data in app]]










---

```dart

import 'package:http/http.dart' as http;
import 'dart:convert';

```

# Get access to the website
```ad-important
```dart
Future<void> fetchData() async {
  final response = await http.get(Uri.parse('https://jsonplaceholder.typicode.com/posts'));

  if (response.statusCode == 200) {
    List<dynamic> data = json.decode(response.body);
    // Теперь 'data' содержит полученные данные
    print(data);
  } else {
    throw Exception('Не удалось загрузить данные');
  }
}

```


```dart

@override
void initState() {
  super.initState();
  fetchData();
}

```

---
# References

