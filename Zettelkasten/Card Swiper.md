День : 2024-05-17 
Время : 21-25

Status : #Programming  


# 👨‍💻Card Swiper

it is exceptional package that allows us to swipe objects

```dart
Swiper(
itemBuilder: (BuildContext context, int index), // creates the widgets index times

autoplay: true, // enables autoplay
autoplayDelay: 5050, // frequency of animation (time between animations) (in milliseconds)
duration: 450 // duration of the animation

)
```

## Layout options

```dart
1) viewportFraction: 0.8,
   scale: 0.9,
```

```dart
2) itemWidth: 300.0,
   layout: SwiperLayout.STACK,
```

```dart
3) layout: SwiperLayout.CUSTOM,
  customLayoutOption: CustomLayoutOption(
    startIndex: -1,
    stateCount: 3
  )..addRotate([
    -45.0/180,
    0.0,
    45.0/180
  ])..addTranslate([
    Offset(-370.0, -40.0),
    Offset(0.0, 0.0),
    Offset(370.0, -40.0)
  ]),
  itemWidth: 300.0,
  itemHeight: 200.0,
```





---
# References

[[Main packages]]
https://pub.dev/packages/card_swiper
