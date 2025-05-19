День : 2024-04-01 
Время : 16-05

Status : #Programming 


# Flutter layout

```ad-note
Widget restrictions are declared in the parents. The dimensions (desired) are set in the widget itself. The position of the widget on the screen is set by the parent Widget restrictions are declared in the parents. Dimensions (desired)

```
1. Firstly, the widget creates restrictions for its childish widgets
2. Secondly, according to the parent restrictions, childish widgets change its size.

There is great [[Layout example]] 

```ad-note
Child widget can not have any size. Everything depends on its parent.


```


SO IF YOU PUT `CONTAINER` TO THE `SCAFFOLD` IT WILL COVER WHOLE SCREEN(WHOLE `SCAFFOLD`). <mark style="background: #FFB8EBA6;">BUT</mark> IF YOU COVER `CONTAINER` WITH `CENTER` WIDGET. CENTER WILL SAY : '''OKEY ,`CONTAINER` BE AS BIG AS YOU WANT TO. HOWEVER NOT BIGGER THAN `SCAFFOL`'
``


`Container(width: 100, height: 100, color: Colors.red)`




---
# References

## [[Flutter]]
## [link oh the channel](https://habr.com/ru/articles/500210/)  