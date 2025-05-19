День : 2024-04-27 
Время : 22-22

Status : #Programming  


# 👨‍💻GridView.builder()

<iframe width="420" height="255" src="https://www.youtube.com/embed/nUBMK7UEQ1Q?si=qWSjGud2ln9Xmy-P" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

it has 2 **required** properties 
1) `gridDeligate :`
- **SliverGridDelegate<mark style="background: #FF5582A6;">WithFixed</mark>CrossAxisCount()**
   - `required crossAxisCount: double(1,2,3,4)`
- **SliverGridDelegate<mark style="background: #FFB86CA6;">WithMax</mark>CrossAxisCount()**
  - - `required maxCrossAxisExtent: double(1,2,3,4)`
2) `itemBuilder :`
 [[WidgetBuilder | Widget Function(BuildContext, int)]] - this <mark style="background: #BBFABBA6;">type</mark> of widget it requires

3) 
```ad-important
DO NOT FORGET ABOUT `itemCount`  which show how many widget(which are going to be built) will be in your GridView(<mark style="background: #FFB86CA6;">Grid</mark>)

```


---
# References
[[GridView]]

