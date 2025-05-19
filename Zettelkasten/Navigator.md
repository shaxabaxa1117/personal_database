День : 2024-05-06 
Время : 18-51

Status : #Programming  


# 👨‍💻Navigator


## Navigator.push

![[Pasted image 20240506203308.png]]
 
Via <mark style="background: #FF5582A6;">Navigator.push</mark> we we can move to other page which is mentioned in <mark style="background: #BBFABBA6;">MaterialPageRoute    </mark>

```ad-important
It is essential that we can not use the <mark style="background: #FFB86CA6;">Navigator.push()</mark> in the main file.

So it works between non-main pages

(It is how I understood it)

```

## Navigator.pushNamed

We create the names for paths in advance 
![[Pasted image 20240506205022.png]]

Here we name the route to the <mark style="background: #FF5582A6;">HomePage() </mark>in main file;
Then, in <mark style="background: #BBFABBA6;">IntroPage()</mark> we declare the movement to the next page via <mark style="background: #FFB86CA6;">Navigator.pushNamed(context,'/homepage')</mark>

![[Pasted image 20240506205407.png]]


 
---
# References

[[List of widgets]]

https://api.flutter.dev/flutter/widgets/Navigator-class.html