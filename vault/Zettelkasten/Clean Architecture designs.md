День : 2024-05-23 
Время : 18-57

Status : #Programming  


# 👨‍💻Architecture designs


## LINKS

- [[Pattern of data state]]
---


My Architecture designs for [[Working with restfulAPI]]  

Я разделил код на **четыре уровня**:  
1️⃣ `ITMDBApi` (интерфейс API)  
2️⃣ `Repository` (работает с API, возвращает `List<Any_Model>`)  
3️⃣ `Service` (обрабатывает данные с Repostory например фильтр, обработка нужных данных)  
4️⃣ `Provider` / `State Manager` (работает с UI)


---

- [[Architecture of folders]]





![[Pasted image 20250123211739.png | 550]]

![[Pasted image 20250131184529.png]]
## [Link to the article ](https://medium.com/@yamen.abd98/clean-architecture-in-flutter-mvvm-bloc-dio-79b1615530e1) that helped me to understand [[MVVM]].



---
# References

