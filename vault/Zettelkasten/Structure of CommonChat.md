	День : 2025-01-09 
Время : 19-10

Status : #Programming  


# 👨‍💻Structure of CommonChat


```
lib/
├── main.dart
├── app.dart
├── config/
│   ├── theme.dart
│   └── localization.dart
├── models/
│   ├── user_model.dart
│   ├── chat_model.dart
│   ├── group_model.dart
│   └── message_model.dart
├── services/
│   ├── auth_service.dart
│   ├── chat_service.dart
│   ├── group_service.dart
│   ├── user_service.dart
│   └── notification_service.dart
├── screens/
│   ├── auth/
│   │   ├── login_page.dart
│   │   └── register_page.dart
│   ├── home/
│   │   ├── home_page.dart
│   │   ├── settings_page.dart
│   │   └── friends_list_page.dart
│   ├── chat/
│   │   ├── chat_page.dart
│   │   ├── group_chat_page.dart
│   │   └── chat_list_page.dart
├── widgets/
│   ├── app_drawer.dart
│   ├── custom_app_bar.dart
│   ├── chat_bubble.dart
│   └── friend_card.dart
├── utils/
│   ├── validators.dart
│   ├── constants.dart
│   ├── routes.dart
│   └── helpers.dart
└─── providers/
    ├── auth_provider.dart
    ├── chat_provider.dart
    └── theme_provider.dart


```


### 📂 **Описание папок и файлов**

#### 1. **`main.dart`**

Точка входа в приложение. Здесь происходит инициализация приложения и привязка темы/локализации.

#### 2. **`app.dart`**

Файл, где создаётся корневой виджет приложения с настройкой роутов, провайдеров и тем.

#### 3. **`config/`**

- `theme.dart` — определение светлой/тёмной темы для приложения.
- `localization.dart` — настройка языков (если поддерживается мультиязычность).

#### 4. **`models/`**

Модели данных:

- `user_model.dart` — данные пользователя (id, имя, email, друзья).
- `chat_model.dart` — данные чатов (id чата, участники, сообщения).
- `group_model.dart` — данные групповых чатов.
- `message_model.dart` — сообщения в чатах (id сообщения, отправитель, текст, время).

#### 5. **`services/`**

Сервисы для работы с данными:

- `auth_service.dart` — регистрация, логин, логика работы с токенами.
- `chat_service.dart` — отправка/получение сообщений.
- `group_service.dart` — создание групп, управление участниками.
- `user_service.dart` — поиск пользователей, добавление в друзья.
- `notification_service.dart` — уведомления о сообщениях и запросах.

#### 6. **`screens/`**

Разделение по страницам:

- `auth/` — логин и регистрация.
- `home/` — главная страница, настройки и список друзей.
- `chat/` — страницы чатов (одиночные и групповые).

#### 7. **`widgets/`**

Переиспользуемые виджеты:

- `app_drawer.dart` — боковое меню.
- `custom_app_bar.dart` — настраиваемая верхняя панель.
- `chat_bubble.dart` — пузырьки сообщений.
- `friend_card.dart` — карточка друга.

#### 8. **`utils/`**

- `validators.dart` — валидация данных (например, email/пароль).
- `constants.dart` — общие константы (цвета, размеры и т. д.).
- `routes.dart` — маршруты для перехода между страницами.
- `helpers.dart` — вспомогательные методы (форматирование дат и т. д.).

#### 9. **`providers/`**

Провайдеры для работы с состоянием:

- `auth_provider.dart` — управление состоянием авторизации.
- `chat_provider.dart` — управление состоянием чатов.
- `theme_provider.dart` — управление темой приложения.




---
# References

