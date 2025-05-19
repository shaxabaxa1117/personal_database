День : 2024-08-06 
Время : 12-41

Status : #Programming  


# 👨‍💻Bloc

 # [[Cubit]]
 # [[BLoC listener]]

---

<iframe width="620" height="315" src="https://www.youtube.com/embed/SDk_GldOtK8?si=L0sP-9ERPvi1yVRs&amp;start=1838" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
## What is BLoC?

- **Separation of Concerns:** Keeps business logic separate from the UI.
- **Streams:** Uses events and states to manage data flow.
- **Testability & Scalability:** Makes your app easier to test and maintain.

---

## Key Concepts

1. **Event:** User actions or external triggers.
2. **State:** Represents the current data or UI state.
3. **BLoC:** Processes events and emits new states.

---

- We create class that that responds to all events. We respond diffirently and change the state via `emit` just like a [[Cubit]]
![[Pasted image 20250205220050.png]]

- Here is the `sealed class CounterEvent`. BLoC can react to diffirent types of event we must create the genrerel class for all events.  
![[Pasted image 20250205220240.png]]
- And here we we add events to the BLoC and according to the Event the BLoC reacts diffirently and changes a state accordingly.

![[Pasted image 20250205220705.png]]

```ad-important

## **Why Use part and part of Instead of import?**

### **1. Single Compilation Unit**

When using `part` and `part of`, **all related files are compiled together as one unit**. This means:

- You **don’t need to import** the event and state files separately in your BLoC.
- You **avoid circular imports** that might happen when using `import`.

![[Pasted image 20250205221104.png]]

![[Pasted image 20250205221124.png]]


```







---
# References

[[Flutter]]