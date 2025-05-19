День : 2024-05-24 
Время : 16-50

Status : #Programming  


# 👨‍💻Future

![[Pasted image 20240524175744.png]]
![[Pasted image 20240524175510.png]]
В данном случаи Future обеспечивает функцию после основного действия в main.

что бы получить результат мы обращаемся к `then`
у класса `File` есть метод `readAsSting` который является типом `Future`
`Future` не может просто так взять и скинуть результат, на то он и `Future` что ждет чего то а потом отправляет через `then`. Даже если нечего ждать, он будет ждать и по сути сразу выводит результат `value`.  
`then` - ждет пока main закончиться.
Здесь он ждет пока main() закончит свою работу и после этого выполниться Future

Через then мы можем получить значение в который возвращает Future<`generic`>
![[Pasted image 20240524182712.png]]

## async/await

![[Pasted image 20240524183530.png]]
![[Pasted image 20240524183429.png]]
First of all- `async/awit` is sugar code
It does exactly same thing what is written in comments.

`then` - waits the code in main to be executed and then it return the result of Future typed function.

But we can write less code if we make `main()` `async` and add `await` to each Future functions

![[Pasted image 20240524185339.png]]

<mark style="background: #BBFABBA6;">Result :</mark>

![[Pasted image 20240524185354.png]]


<mark style="background: #FF5582A6;">link to that part</mark>
<iframe width="560" height="315" src="https://www.youtube.com/embed/12KsifmXcGc?si=dYYliqlPH9inssFM&amp;start=1955" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


```ad-hint
Самое простое объяснение зачем нужен async/await это привести пример получения данных с сервера, а потом их обработать, мы же не можем их обработать не получив, а для получения нужно обождать.

```

---
# References

