День : 2024-04-12 
Время : 15-25

Status : #Programming   


# Stateful widgets

```ad-important
setState() rebuild the widget (the class)

```


- Stateful widgets can maintain state that can change over time, causing the widget to rebuild with the updated state.
- They are mutable, allowing for dynamic interactions and updates in the UI.
- Stateful widgets are used when the UI needs to react to user input, network responses, animations, etc
```ad-note
This kind of widgets are more 'practcal'. <mark style="background: #FFB86CA6;">They can be used, moved, changed and so on.</mark>

SO HERE EACH WIDGET HAS ITS OWN STATE. It chaned after certain interaction with it 

```

<mark style="background: #FFB86CA6;">we should take into account where we should create  variables to change </mark>

![[Pasted image 20240423183201.png]]

---
![[Pasted image 20240423185156.png]]
![[Pasted image 20240423185246.png]]

So here setState(){} looks at the whole widget and tries to find whether something is going to change. If it finds it, <mark style="background: #FF5582A6;">it rebuilds the whole widget</mark>.


Examples include [[TextField]] , [[Checkbox]] , [[ Slider]], etc.


---
# Reference 
[[Example of stateless and stateful usage]] 