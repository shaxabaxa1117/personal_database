День : 2024-04-26 
Время : 21-17

Status : #Programming  

There is Provider(our model) and it own Consumer(widgets that uses data from model)
# 👨‍💻ChangeNotifier

## How it works 
 1. **ChangeNotifier**:
    
    - `ChangeNotifier` - это класс, реализующий паттерн наблюдателя (Observer pattern). Он содержит данные и уведомляет своих слушателей (например, виджеты), когда эти данные изменяются.
    - Когда вызывается метод `notifyListeners()` у объекта `ChangeNotifier`, он оповещает всех своих слушателей о том, что данные изменились.
2. **Provider**:
    
    - `Provider` - это механизм управления состоянием, предоставляемый пакетом `provider`. Он используется для предоставления объектов вверх по иерархии виджетов и их доступа вниз по этой иерархии.
    - Когда объект `ChangeNotifier` предоставляется через `Provider`, он становится доступным для всех виджетов в иерархии, которые имеют доступ к этому `Provider`.
3. **Как это работает вместе**:
    
    - Когда данные в объекте `ChangeNotifier` изменяются и вызывается метод `notifyListeners()`, `Provider` обнаруживает это изменение.
    - `Provider` автоматически перестраивает все виджеты в иерархии, которые зависят от этого объекта `ChangeNotifier`.
    - Таким образом, виджеты, которые используют данные из объекта `ChangeNotifier` через `Provider`, автоматически обновляются, чтобы отобразить актуальные данные.


	

---

## Usage

1) So the first thing is to extract the<mark style="background: #FF5582A6;"> Model</mark> class as long as we must separate the logic and UI
here the model is `CounterModel`
![[Pasted image 20240429184240.png]]
2) Then we make sure that the `ChangeNotifyProvider` concerns our widget MainApp
but it's not really good. We had better use Provider for each pages
<mark style="background: #BBFABBA6;">It is better to link Provider for each specific place, page, etc.</mark> where it is necessary to change the state 


So here it is badly managed ⛔
![[Pasted image 20240429184714.png]]
but this one is good 👍
![[Pasted image 20240429193800.png]]
По скольку я наследую мой ConuterModel от ChangeNotifier, я могу возвращать CounterModel (в обязательный (create:)  параметр ChangeNotifierProvider) как экземпляр класс ChangeNotifier
![[Pasted image 20240429191459.png]]


3) So now we make our Widget( in this case it is Scaffold) Consumer of the provider , and we can see that

- via context we create the object of the class which is essential
- via value we can take the 
The type of the Consumer is  `<CounterModel>` -  so we take the data from the class ``<CounterModel>``

![[Pasted image 20240429185925.png]]
<mark style="background: #FF5582A6;">BUT!!!</mark>
We can just  inticialize variable(let say 'model') with context.watch<ProviderClass(model name)>;
```dart
final model = context.watch<CounterProvider>();
```

![[Pasted image 20240501204923.png]]

4) So now we can use the values of the provider `<CounterModel>` if this provider has getter
(Left Consumer, Right Provider)

![[Pasted image 20240429194512.png]]

5) Here is how we get method of the class in the consumer 
![[Pasted image 20240429204320.png]]

```dart
final model = context.read<CounterProvider>();
```

<mark style="background: #FFB8EBA6;"></mark>

---
# References

[[List of widgets]]
[[Provider]]