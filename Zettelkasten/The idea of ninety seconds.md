### Разработка приложения на Flutter для изучения английских слов с использованием метода "90 секунд"

#### 1. **Описание функционала приложения**

**Главные функции:**

- Добавление новых слов и фраз в словарь.
- Ежедневные напоминания о повторении слов.
- Автоматизированное расписание повторений.
- Аудио воспроизведение фраз для лучшего запоминания.
- Прогресс трекинг.

#### 2. **Дизайн приложения**

##### **Главные экраны:**

1. **Экран "Главная"**:
    
    - Приветственное сообщение.
    - Кнопки навигации: "Мой словарь", "Добавить слово", "Прогресс".
    - Список слов/фраз для повторения на сегодня.
2. **Экран "Мой словарь"**:
    
    - Список всех добавленных слов/фраз.
    - Возможность поиска и фильтрации.
3. **Экран "Добавить слово"**:
    
    - Поле для ввода нового слова.
    - Поле для ввода контекстного предложения.
    - Кнопка "Сохранить".
4. **Экран "Прогресс"**:
    
    - График или статистика повторений.
    - Уровень запоминания слов.

##### **UI элементы:**

- **Карточки** для отображения фраз и прогресса.
- **Диалоговые окна** для добавления новых слов.
- **Графики и диаграммы** для визуализации прогресса.
- **Звуковые и анимационные эффекты** для улучшения пользовательского опыта.

#### 3. **Архитектура проекта**

##### **Общие принципы:**

- Использование архитектуры MVVM (Model-View-ViewModel) для отделения логики приложения от UI.
- Использование пакета `provider` для управления состоянием.

##### **Структура директорий:**

less

```dart


lib/
|- models/       // Модели данных (слова, фразы)
|- views/        // UI компоненты (экран Главная, Мой словарь и т.д.)
|- viewmodels/   // Логика и управление состоянием
|- services/     // Сервисы (работа с базой данных, напоминания)
|- utils/        // Утилиты и вспомогательные функции
|- main.dart     // Точка входа в приложение
```


##### **Модели данных:**


```dart
class Phrase {
  String word;
  String sentence;
  DateTime addedDate;
  DateTime nextReviewDate;

  Phrase({required this.word, required this.sentence, required this.addedDate, required this.nextReviewDate});
}
```

##### **ViewModels:**

- **PhraseViewModel**: Логика для добавления и управления словами.
- **ReviewViewModel**: Логика для управления повторениями и напоминаниями.

##### **Сервисы:**

- **DatabaseService**: Для хранения слов и фраз.
- **NotificationService**: Для управления напоминаниями.
- **AudioService**: Для воспроизведения звуков.

#### 4. **Интеграция и технологии**

- **Firebase** для хранения данных (Firestore) и управления напоминаниями (Firebase Cloud Messaging).
- **SQLite** для локального хранения данных.
- **Flutter Local Notifications** для локальных напоминаний.
- **Text-to-Speech (TTS)** API для воспроизведения звуков.

#### 5. **Пошаговая реализация**

1. **Настройка проекта**: Создать новый проект на Flutter и настроить зависимости.
2. **Создание моделей данных**: Определить модель для слов и фраз.
3. **Разработка UI**: Создать основные экраны и элементы интерфейса.
4. **Реализация ViewModels**: Написать логику для управления состоянием.
5. **Подключение баз данных и сервисов**: Настроить Firebase и SQLite для хранения данных.
6. **Настройка уведомлений**: Использовать Flutter Local Notifications для напоминаний.
7. **Интеграция TTS**: Добавить функциональность Text-to-Speech для озвучивания фраз.
8. **Тестирование и отладка**: Провести тестирование приложения и исправить ошибки.
9. **Развертывание**: Подготовка и выпуск приложения в App Store и Google Play.

#### Пример кода:

**models/phrase.dart**

```dart
class Phrase {
  final String id;
  final String word;
  final String sentence;
  final DateTime addedDate;
  final DateTime nextReviewDate;

  Phrase({
    required this.id,
    required this.word,
    required this.sentence,
    required this.addedDate,
    required this.nextReviewDate,
  });

  factory Phrase.fromMap(Map<String, dynamic> data, String documentId) {
    final Timestamp addedDate = data['addedDate'];
    final Timestamp nextReviewDate = data['nextReviewDate'];

    return Phrase(
      id: documentId,
      word: data['word'],
      sentence: data['sentence'],
      addedDate: addedDate.toDate(),
      nextReviewDate: nextReviewDate.toDate(),
    );
  }

  Map<String, dynamic> toMap() {
    return {
      'word': word,
      'sentence': sentence,
      'addedDate': addedDate,
      'nextReviewDate': nextReviewDate,
    };
  }
}
```


**viewmodels/phrase_viewmodel.dart**


```dart
import 'package:flutter/material.dart';
import 'package:cloud_firestore/cloud_firestore.dart';
import '../models/phrase.dart';

class PhraseViewModel extends ChangeNotifier {
  final FirebaseFirestore _db = FirebaseFirestore.instance;

  Future<void> addPhrase(Phrase phrase) async {
    await _db.collection('phrases').add(phrase.toMap());
    notifyListeners();
  }

  Stream<List<Phrase>> getPhrases() {
    return _db.collection('phrases').snapshots().map((snapshot) {
      return snapshot.docs.map((doc) => Phrase.fromMap(doc.data(), doc.id)).toList();
    });
  }
}
```
**main.dart**

```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'viewmodels/phrase_viewmodel.dart';
import 'views/home_view.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MultiProvider(
      providers: [
        ChangeNotifierProvider(create: (_) => PhraseViewModel()),
      ],
      child: MaterialApp(
        title: '90 Seconds Method App',
        theme: ThemeData(
          primarySwatch: Colors.blue,
        ),
        home: HomeView(),
      ),
    );
  }
}
```

Эти основные шаги и примеры кода помогут в реализации приложения на Flutter