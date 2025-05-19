День : 2024-08-20 
Время : 15-25

Status : #Programming  


# 👨‍💻Methods of PyLoops

### **Методы циклов**

#### 1. **`range(start, stop, step)`**

- Генерирует последовательность чисел от `start` до `stop` (не включая `stop`) с шагом `step`.
- Примеры:
    
    python
    
    Copy code
    
    `range(5)         # [0, 1, 2, 3, 4] range(1, 10, 2)  # [1, 3, 5, 7, 9] range(10, 0, -2) # [10, 8, 6, 4, 2]`
    

#### 2. **`enumerate(iterable, start=0)`**

- Возвращает итератор, который генерирует пары (индекс, значение) для каждого элемента в `iterable`.
- Пример:
    
    python
    
    Copy code
    
    `items = ['a', 'b', 'c'] for index, item in enumerate(items):     print(index, item) # Вывод: # 0 a # 1 b # 2 c`
    

#### 3. **`zip(*iterables)`**

- Объединяет несколько итерируемых объектов (например, списки) в кортежи, где каждый кортеж содержит элементы из всех итерируемых объектов на соответствующей позиции.
- Пример:
    
    python
    
    Copy code
    
 ```python
	names = ['Alice', 'Bob', 'Charlie'] scores = [85, 90, 88] 
for name, score in zip(names, scores):    
print(f"{name} scored {score}") # Вывод: # Alice scored 85 # Bob scored 90 # Charlie scored 88
	
	```
    

#### 4. **`reversed(sequence)`**

- Возвращает итератор для последовательности в обратном порядке.
- Пример:
    
    python
    
    Copy code
    
    ```python
for i in reversed(range(5)):     print(i) # Вывод: # 4 # 3 # 2 # 1 # 0
```
    

#### 5. **`sorted(iterable, key=None, reverse=False)`**

- Возвращает новый отсортированный список из элементов итерируемого объекта.
- Пример:
    
    python
    
    Copy code
    
    `numbers = [4, 2, 5, 1, 3] for i in sorted(numbers):     print(i) # Вывод: # 1 # 2 # 3 # 4 # 5`

---
# References

