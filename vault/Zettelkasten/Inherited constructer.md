День : 2024-05-16 
Время : 19-07

Status : #Programming  


# 👨‍💻Inherited constructer

![[Pasted image 20240516191651.png]]
Before we use data in our class from other class( even if it abstract like here), we must create [[Constructer]] <mark style="background: #FFB86CA6;">in both classes</mark>. But the thing is that if we want to take data from our parent class we must use `super.`
in child class when we are creating constructor. But the data from its own class should still be declared with word `this.` 

In the example: we extend data `_hp` and `_name` to the Lion, but `isHungry` we get from this class(`Lion`)

The data from `Animal` is already extended to `Lion`but constructer of `Animal` is not.  


---
# References

[[Constructer]]
[[Inheritance]]