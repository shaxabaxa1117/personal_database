
	День : 2025-02-09 
Время : 23-08

Status : #Programming  


# 👨‍💻How BLoC works with Streams

### Как BLoC обрабатывает события?

1. **Добавление события в BLoC:**  
    Когда вы добавляете событие в BLoC с помощью метода `add`, например:
    
```dart
    context.read<AuthBloc>().add(LoginEvent(email: "user@example.com", password: "password"));
```
    

    Это событие попадает в специальный `Stream` событий, который находится внутри BLoC.
    
2. **Подписка на события:**  
    BLoC автоматически подписывается на этот `Stream` событий. Каждый раз, когда новое событие добавляется в BLoC, оно передается в метод `mapEventToState` (или в обработчики on</Event> в новых версиях библиотеки).
    
3. **Обработка события:**  
    Внутри метода `mapEventToState` BLoC обрабатывает событие и генерирует новые состояния (`AuthState`), которые добавляются в `Stream` состояний с помощью `yield`.
    
4. **Обновление UI:**  
    UI-слой (например, `BlocBuilder` или `BlocConsumer`) подписывается на `Stream` состояний BLoC. Когда BLoC генерирует новое состояние, UI автоматически обновляется.
    


---

### Почему событие срабатывает?

Когда вы добавляете событие в BLoC с помощью `add`, происходит следующее:

1. **Событие добавляется в `Stream` событий:**  
    BLoC внутри себя использует `StreamController` для управления потоком событий. Когда вы вызываете `add`, событие добавляется в этот `StreamController`.
    
2. **BLoC подписан на `Stream` событий:**  
    BLoC автоматически подписывается на `Stream` событий, который он сам же и создает. Это происходит внутри библиотеки `flutter_bloc`.
    
3. **Событие передается в `mapEventToState`:**  
    Каждое новое событие из `Stream` событий передается в метод `mapEventToState`, где оно обрабатывается.
    
4. **Генерация состояний:**  
    Внутри `mapEventToState` вы обрабатываете событие и генерируете новые состояния с помощью `yield`. Эти состояния добавляются в `Stream` состояний, на который подписан UI.
    

---

### Как это работает внутри BLoC?

Вот упрощенная схема того, как BLoC работает внутри:

1. **`StreamController` для событий:**  
    BLoC создает `StreamController`, который управляет потоком событий (`AuthEvent`).
    
2. **`StreamController` для состояний:**  
    BLoC также создает `StreamController`, который управляет потоком состояний (`AuthState`).
    
3. **Подписка на события:**  
    BLoC подписывается на `Stream` событий и передает каждое событие в метод `mapEventToState`.
    
4. **Генерация состояний:**  
    Внутри `mapEventToState` вы обрабатываете событие и генерируете состояния, которые добавляются в `Stream` состояний.
    
5. **Подписка UI на состояния:**  
    UI-слой (например, `BlocBuilder`) подписывается на `Stream` состояний и обновляется, когда BLoC генерирует новое состояние.


---

 ## Пример работы BLoC
 
  1. **Добавление события:**
```dart	
context.read<AuthBloc>().add(LoginEvent(email: "user@example.com", password:"password"));
```
  2. **Обработка события в BLoC:**
  ```dart
  @override
Stream<AuthState> mapEventToState(AuthEvent event) async* {
  if (event is LoginEvent) {
    yield AuthLoading(); // Генерация состояния загрузки
    await Future.delayed(Duration(seconds: 2)); // Имитация задержки
    if (event.email == "user@example.com" && event.password == "password") {
      yield AuthAuthenticated(user: User(email: event.email, token: "dummy_token")); // Успешная аутентификация
    } else {
      yield AuthError(message: "Invalid credentials"); // Ошибка аутентификации
    }
  }
}
```
 3. **Обновление UI:**

```dart
BlocBuilder<AuthBloc, AuthState>(
  builder: (context, state) {
    if (state is AuthLoading) {
      return CircularProgressIndicator();
    } else if (state is AuthAuthenticated) {
      return Text("Welcome, ${state.user.email}!");
    } else if (state is AuthError) {
      return Text("Error: ${state.message}");
    } else {
      return LoginForm();
    }
  },
)
```

---
# References

