День : 2024-04-12 
Время : 22-18

Status : #Programming  


# 👨‍💻BottomNavigationBar

![[BottomNavigationBar 2024-05-10 20.47.37.excalidraw]]

[link to the file](file:///d%3A/Programming/Projects/Flutter%20projects/Main%20Projects/jap_in_pan/lib/pages/navigator_page.dart)
I created special file where the description of `BottomNavigationBar`'logic is written. 
I used [convex package](https://pub.dev/packages/convex_bottom_bar) as it is more convenient.

convex has `onTap(int index){ }` property 
index here is the button from `items: TabItem` list. So if the first button is tapped than the index is 0. (As long as list starts with 0)

- In stateful widget we create variable `selectedPage`. 
- We create list of the content(other pages that we want to move on) `_pageList`.
- And we also create state function `changeIndex`.
![[Pasted image 20240510211458.png]]

## The logic

Whenever we click on the buttons of `BottomNavigationBar`  the `index` parameter of `onTap` property is always changed
![[Pasted image 20240510212117.png]]
we have got  `changeIndex` function which changes our `selectedPage` to the `index` whenever we type on the buttons. in the body we use `_pageList[selectedPage]` to finally change the content.

Example : we click on the second button : the `index` changes to 1 : function `changeIndex` changes value `selectedPage` to the `index` : so now `selectedPage` is 1: in the body the page of `_pageList[selectedPage]`  will be declared

![[Pasted image 20240510211752.png]]

---
<mark style="background: #BBFABBA6;">HOWEVER  !!!</mark>
2024-05-10 
22:51
We must change our code as I understood that the first page is not going to react with previous code 

But the code below solves the problem!!!
Here we see that `curentPage` get the page from `_pageList` and then it is shown in `body:`

![[Pasted image 20240510225809.png]]

```ad-important

Change the initialPage to the one we want to 
```

---
- ![[Pasted image 20240513192128.png]]

---

---
# References

[link to the file](file:///d%3A/Programming/Projects/Flutter%20projects/Main%20Projects/jap_in_pan/lib/pages/navigator_page.dart) 