	День : 2025-02-05 
Время : 20-33

Status : #Programming  


# 👨‍💻Cubit


<iframe width="660" height="315" src="https://www.youtube.com/embed/SDk_GldOtK8?si=xTIP2z-hx_m8OBav&amp;controls=0&amp;start=220" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In Flutter, a **Cubit** is a simplified version of a **Bloc** (Business Logic Component) that is part of the `flutter_bloc` state management library. It is used to manage and emit state changes in your application. Unlike Bloc, Cubit does not rely on events to trigger state changes. Instead, it exposes methods that can be called directly to emit new states.

### Key Features of Cubit:

1. **Simplicity**: Easier to use than Bloc because it doesn't require events.
    
2. **State Management**: Manages the state of your application.
    
3. **Emit States**: Uses the `emit` method to update the state.
    
4. **Lightweight**: Less boilerplate compared to Bloc.
    

### How Cubit Works:

- A Cubit holds a state and exposes methods to change that state.
    
- When a method is called, it performs some logic and emits a new state using `emit`.
    
- Widgets can listen to the Cubit and rebuild when the state changes.



---

### Example: Counter App with Cubit

1. **Define the Cubit**:  
    Create a Cubit that manages a counter state.


![[Pasted image 20250205203604.png]]
- When we give in generics of the parent class the type of data this tells us what type of data is used as main type. The intial data type must be the generics' type too.
2. **Use the Cubit in a Widget**:  
	Use `BlocProvider` to provide the Cubit to the widget tree and `BlocBuilder` to listen to state changes.

```dart

import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: BlocProvider(
        create: (context) => CounterCubit(),
        child: CounterScreen(),
      ),
    );
  }
}

class CounterScreen extends StatelessWidget {
final counterCubit = BlocProvider.of<CounterCubit>(context);
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Counter with Cubit')),
      body: Center(
        child: BlocBuilder<CounterCubit, int>( // specifing the type of data of cubita and the type of its data.
		bloc: counterCubit,
          builder: (context, count) {
            return Text('Count: $count', style: TextStyle(fontSize: 24));
          },
        ),
      ),
      floatingActionButton: Column(
        mainAxisAlignment: MainAxisAlignment.end,
        children: [
          FloatingActionButton(
            onPressed: () => counterCubit.increment(),
            child: Icon(Icons.add),
          ),
          SizedBox(height: 10),
          FloatingActionButton(
            onPressed: () => counterCubit.decrement();
            child: Icon(Icons.remove),
          ),
        ],
      ),
    );
  }
}
```

---
# References

