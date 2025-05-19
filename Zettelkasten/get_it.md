	День : 2025-02-24 
Время : 10-03

Status : #Programming  


# 👨‍💻get_it

# [Основной ресурс](https://grok.com/chat/d561857e-51c3-44c7-b0fb-96f1ce7c8d6b?referrer=website)

GetIt — это библиотека для управления зависимостями (dependency injection) во Flutter. Её основная задача — помочь организовать код так, чтобы разные части приложения могли легко получать доступ к общим объектам (например, сервисам, контроллерам, репозиториям) без необходимости передавать их вручную через конструкторы или создавать каждый раз заново.

  

Представь, что у тебя есть приложение, где много экранов, и все они используют один и тот же сервис для работы с API. Без GetIt тебе пришлось бы либо создавать этот сервис заново на каждом экране (что неэффективно), либо передавать его через параметры (что может запутать код). GetIt решает эту проблему: ты регистрируешь сервис один раз, а потом просто "берёшь" его там, где он нужен.

  

Преимущества:

  

1. **Удобство**: Не нужно передавать объекты через цепочку классов.
  
2. **Одиночные экземпляры (singleton)**: Можно настроить так, чтобы один объект создавался и использовался повсюду.
  
4. **Тестирование**: Легко подменять зависимости для тестов.
  
6. **Чистый код**: Меньше boilerplate-кода (лишних повторений).
  

### Что будет, если не использовать GetIt?

  

Если не использовать GetIt или другой способ управления зависимостями, то:

  

- Ты можешь столкнуться с дублированием кода: каждый раз создаёшь новый экземпляр сервиса, даже если он должен быть общим.
  
- Код станет сложнее поддерживать: если зависимости передаются через конструкторы, цепочка вызовов может стать громоздкой.
  
- Производительность может пострадать: создание новых объектов вместо повторного использования существующих тратит ресурсы.
  
- Тестировать будет сложнее: без централизованного управления зависимостями трудно подменять реальные объекты на заглушки (mocks).
  

### Пример

  

Давай разберём простой случай с использованием GetIt и без него.

  

#### 1. Без GetIt

  

Допустим, у нас есть сервис ApiService, который получает данные из интернета, и два виджета, которые его используют.
```dart

class ApiService {
  Future<String> fetchData() async {
    return "Данные с сервера";
  }
}

class Screen1 extends StatelessWidget {
  final ApiService apiService = ApiService(); // Новый экземпляр

  @override
  Widget build(BuildContext context) {
    return FutureBuilder(
      future: apiService.fetchData(),
      builder: (context, snapshot) => Text(snapshot.data ?? "Загрузка..."),
    );
  }
}

class Screen2 extends StatelessWidget {
  final ApiService apiService = ApiService(); // Ещё один новый экземпляр

  @override
  Widget build(BuildContext context) {
    return FutureBuilder(
      future: apiService.fetchData(),
      builder: (context, snapshot) => Text(snapshot.data ?? "Загрузка..."),
    );
  }
}
```


**Проблема**: Каждый экран создаёт свой собственный ApiService. Если сервис должен быть один (например, с настройками подключения или кэшем), это не работает. Приходится либо передавать сервис через конструкторы, либо дублировать код.

  

#### 2. С GetIt

  
Теперь используем GetIt, чтобы сделать ApiService единым экземпляром.

Сначала устанавливаем библиотеку:

```dart
import 'package:get_it/get_it.dart';

// Создаём глобальный экземпляр GetIt
final getIt = GetIt.instance;

void setupDependencies() {
  getIt.registerSingleton<ApiService>(ApiService()); // Регистрируем сервис как singleton
}

class ApiService {
  Future<String> fetchData() async {
    return "Данные с сервера";
  }
}

class Screen1 extends StatelessWidget {
  final ApiService apiService = getIt<ApiService>(); // Берём готовый экземпляр

  @override
  Widget build(BuildContext context) {
    return FutureBuilder(
      future: apiService.fetchData(),
      builder: (context, snapshot) => Text(snapshot.data ?? "Загрузка..."),
    );
  }
}

class Screen2 extends StatelessWidget {
  final ApiService apiService = getIt<ApiService>(); // Тот же экземпляр

  @override
  Widget build(BuildContext context) {
    return FutureBuilder(
      future: apiService.fetchData(),
      builder: (context, snapshot) => Text(snapshot.data ?? "Загрузка..."),
    );
  }
}

void main() {
  setupDependencies(); // Настраиваем зависимости перед запуском
  runApp(MyApp());
}
```




### Итог

**GetIt** нужен для удобного и эффективного управления зависимостями. Без него можно обойтись в маленьких проектах, но в больших приложениях отсутствие такого инструмента приведёт к беспорядку в коде и проблемам с масштабированием. Попробуй использовать его в своём проекте — это сильно упрощает жизнь! 


---
# References
[[Main packages]]
