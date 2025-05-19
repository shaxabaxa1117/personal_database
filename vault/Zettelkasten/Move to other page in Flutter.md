День : 2024-04-26 
Время : 20-42

Status : #Programming  


# 👨‍💻Move to other page in Flutter

```dart
          GestureDetector(

            // moving to other page

            onTap: () => Navigator.pushReplacement( //moving to other page

              context,

              MaterialPageRoute( // here it starts

                builder: ((context) {

                  return HomePage();

                }),

              ),

            ),

            child: Container(

                decoration: BoxDecoration(

                    borderRadius: BorderRadius.circular(12),

                    color: Colors.deepPurple),

                padding: EdgeInsets.all(24),

                child: Text(

                  'Get Started',

                  style: TextStyle(color: Colors.white),

                )),

          ),
```


---
# References
[[Interesting Func in Flutter]]
[
