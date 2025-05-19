	День : 2024-12-22 
Время : 19-00

Status : #Programming  


# 👨‍💻Project Movie_db



---
# References


	2024-12-22

_Creating  auth_widget( authentication )
- creating a links in words is not good practice

	2024-12-24
_Creating the logic of the cheking the passowrd_
- Creating a error text only when tere is an error
```dart
Column(

      crossAxisAlignment: CrossAxisAlignment.start,

      children: [

        if (errorText != null) ...[ //? creates column of widgets if errorText is not null

          Text(

            errorText!,

            style: const TextStyle(color: Colors.red, fontSize: 18),

          ),

          SizedBox(

            height: 15,

          )

        ], //! if errorText is not null, then show the errorText

        const Text(

          'Username',

          style: styleText,

        ),

        TextField(

          controller: _loginTextrController,

          decoration: textfieldDecoratiton,

        ),
```

- We can create a function and add `setState` inside. Everything changes correctly 
```dart
  void _auth() {

    final login = _loginTextrController.text;

    final password = _passwordTextController.text;

  

    if (login == 'admin' && password == 'admin') {

      print('Empty fields');

      errorText = null;

    } else {

      errorText = 'Invalid login or password';

      print('Login: $login, Password: $password');

    }

    setState(() {});

  }

  

  void _resetPassword() {

    print('Reset password');

  }
```

