День : 2024-06-03 
Время : 15-38

Status : #Programming  


# 👨‍💻Using JSON data in app

First and foremost :

We must find JSON data from the web and we must create classes that for the type of data we are going to take. So, if JSON file consists of name, age, occupation we probably are going to create class `Person` or `Emploee` and so on. 

![[Pasted image 20240603154931.png]]

So here we have data type of `Office`

we create list for for each  `Office` in clas `Offices`

![[Pasted image 20240603155045.png]]

---

we create class office with variables that we need. Then we create `factory method`
<mark style="background: #FF5582A6;">fromJson</mark> is going to take Json file.



the `name` of `Office` will have value of `Map<String, dynamic> json`.
- `Map<String, dynamic> json`.
  1) First value: String is the name of key -it is always `String` as long as the key in JSON start with `String`
  2) Second value: `dynamic` is the value that each key has and it can be any type of value
name : `json['name']`
address : `json['address']`
image : `json['image']`

so we put the value json's 'name' key value to new objects name; 

![[Pasted image 20240603155223.png]]

---

![[Pasted image 20240603161246.png]]

As we have collection in the beginning we write 
and with method `Offices.fromJson()` we add all `Office` typed data to the list `officesList`
- ` factory Offices.fromJson(Map<String, dynamic> json)`
- The map() method **creates a new iterable object that contains all elements of the iterable that pass a test**.
```dart
class Offices {

  List<Office>? offices;

  

  Offices({this.offices});

  

  factory Offices.fromJson(Map<String, dynamic> json) {

    final officesJson = json['offices'] as List; 
 //! по ключю 'offices' мы обращемся к значеню offices(Это работа Map)
//!  и так как значение по ключю 'offices' равно листу то пишем для страховки as List
    List<Office> officesList = officesJson.map((e) => Office.fromJson(e)).toList();

    return Offices(offices: officesList);

  }

}
```

---
we also may not have collection in the beginning like here

![[Pasted image 20240603162212.png]]
we just change to the `List` as long as we don't need collection in the beginning 
![[Pasted image 20240603162330.png]]
---
# After all

![[Pasted image 20240603163010.png]]
 
1) We [[HTTP#Get access to the website]] and its `Future` typed method that must have every file that uses json from web

2) `snapshot` is almost everything . It provides us information of <mark style="background: #FF5582A6;">access</mark>,  <mark style="background: #FF5582A6;">data</mark> and so on.   
  

3) Here it is checking the state of connection and shows `CircularProgressIndicator` if it is waiting for data

4) If there is error in connection we build text in the Centre and alarm that there is poor internet connection.

5) [[ListView]] builder to create box where we display info from json

6) Using `snapshot` we get access to <mark style="background: #FF5582A6;">data</mark>(class `Offices`) which has access to <mark style="background: #FF5582A6;">offices</mark>(`List<Office>`) and via <mark style="background: #FF5582A6;">index</mark> we move to the next data.
and we get data by properties of each class `Office`(name ,address ,image ) (<mark style="background: #FF5582A6;">offices?.address</mark>)




---
# References

