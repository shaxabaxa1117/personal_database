Firstly, every widget consist of [[Widget properties]] 
#Programming 


```ad-note

In Flutter, properties of widgets can have other widgets or values assigned to them.
```

Container is a widget  which consist of [[Widget properties]]. [[Widget properties]] also can consist of widgets  or values.



# How learning and gaining information works?

So, first we should use the cursor to indicate information that Widget contains 
as an example i will use widget Text

```ad-note

 Text(  
**String** data, 

**{**  

**Key?** key,  
**TextStyle?** style,  
**StrutStyle?** strutStyle,  
**TextAlign?** textAlign,  
**TextDirection?** textDirection,  
**Locale?** locale,  
**bool?** softWrap,  
**TextOverflow?** overflow,  
**double?** textScaleFactor,  
**TextScaler?** textScaler,  
**int?** maxLines,
**String?** semanticsLabel,  
**TextWidthBasis?** textWidthBasis,  
**TextHeightBehavior?** textHeightBehavior,  
**Color?** selectionColor, 

**}**

)
```

So here is the property we have to use
It is **data**, and it have to be initialized with the **String** value
Why do only **data** have to be initialized ?
Because other properties are inside **curly braces** **{ }** .That means we don't have to  initialize them all.

Let's look at **locale** property
![[Pasted image 20240402162538.png]]

It asking for creating new object of <mark style="background: #FFB8EBA6;">Locale</mark>  

![[Pasted image 20240402163149.png]]

![[Pasted image 20240402163219.png]]
here we have to initialize String  **_ languageCode** , and  String? **_ countryCode**<mark style="background: #BBFABBA6;"> if you want to </mark>
![[Pasted image 20240402163810.png]]

Another instance :
![[Pasted image 20240402163558.png]]

![[Pasted image 20240402163622.png]]


Here we can see that TextStyle has a lot of properties, but the logic is the same

# Main widgets


[[BottomNavigationBar]]
[[Padding]]
[[Expanded]]
[[Drawer]]
[[MaterialApp]]
[[Navigator]]
[[Padding and Margin]]
[[ChangeNotifier]]
[[CircleAvatar]]




---


Everything starts from [[MaterialApp]] - one of the main widget in Flutter . 
# Reference 
[[Flutter]]

