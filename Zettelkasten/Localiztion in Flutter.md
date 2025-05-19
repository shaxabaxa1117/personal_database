	День : 2025-01-22 
Время : 17-04

Status : #Programming  


# 👨‍💻Localiztion in Flutter



Flutter поддерживает локализацию через пакет **`flutter_localizations`**, а для удобной работы часто используют **`intl`**.

Если у вас уже есть код, можете скинуть его — я помогу адаптировать. А пока общий план действий:

### 1. **Добавьте зависимости в `pubspec.yaml`**

Вам понадобятся:

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations: # Для стандартных локализаций Flutter
    sdk: flutter
  intl: ^0.18.0 # Для управления переводами (можно обновить до последней версии)

dev_dependencies:
  flutter_test:
    sdk: flutter
  intl_utils: ^2.4.2 # Для генерации файлов переводов

```

### 2. **Настройте `MaterialApp` для локализации**

Откройте файл `main.dart` и настройте локализацию. Например:
```dart

import 'package:flutter/material.dart';
import 'package:flutter_localizations/flutter_localizations.dart';
import 'package:intl/intl.dart';
import 'generated/l10n.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My App',
      // Локализация приложения
      localizationsDelegates: const [
        S.delegate, // Генерированный класс для переводов
        GlobalMaterialLocalizations.delegate,
        GlobalWidgetsLocalizations.delegate,
        GlobalCupertinoLocalizations.delegate,
      ],
      supportedLocales: S.delegate.supportedLocales,
      locale: Locale('en'), // Задайте локаль по умолчанию (опционально)
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(S.of(context).helloWorld), // Используем перевод
      ),
      body: Center(
        child: Text(S.of(context).greeting('Flutter')), // С параметром
      ),
    );
  }
}

```

### 3. **Создайте файл конфигурации переводов**

Сгенерируйте файл для перевода:

1. Создайте папку `lib/l10n/`.
2. Добавьте файл `intl_en.arb` (или для нужного языка, например, `intl_ru.arb`) с содержимым:
```arb
{
  "helloWorld": "Hello, World!",
  "greeting": "Hello, {name}!"
}

```

- Аналогично создайте файл для русского: `intl_ru.arb`:
```arb
{
  "helloWorld": "Привет, мир!",
  "greeting": "Привет, {name}!"
}

```
### 4. **Сгенерируйте файл локализации**

Выполните команду для генерации переводов:
```terminal
flutter pub run intl_utils:generate
```

После этого создаётся файл `generated/l10n.dart`, где будет класс `S`. Этот класс используется для доступа к строкам перевода.


### 5. **Используйте переводы в коде**

Теперь вы можете использовать переводы через `S.of(context)`:
```dart
Text(S.of(context).helloWorld) // "Привет, мир!" или "Hello, World!"

```


### 6. **Тестирование локализации**

1. Чтобы поменять язык приложения, настройте `locale` в `MaterialApp`:
```dart
locale: Locale('ru'), // Принудительно русский
```
2. Для автоматического переключения языка используйте `LocaleProvider` на основе системы устройства.




---
# References

