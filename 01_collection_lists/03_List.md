The most common collection in nearly every programming language is the array or ordered group of objects, which in our current lovely language is known as `List`. [1] [dart.dev](https://dart.dev/).

**List** can hold a collection of objects inside it, and these objects should be the same type.

In the movie app, we need two lists: one for holding the movie's names, and the other for images paths inside the **assets** folder.
Right now, we will create a `List` of movies that holds the movie's names; Later, we will create the other `List` for the images.

6. Replace `// TODO: #2 Create movies list` with the code below:

```dart
 List movies = [
    'Toy Story',
    'Spider Man',
    'Inside out',
    'The LEGO Movie',
    'The Lion King',
    'Frozen',
    'Shrek',
    'BIG HERO',
    'ICE AGE',
    'BRAVE',
  ];
```

> We created a `List` variable that holds the names of the movies, and the type of these names is **String**. Thus, the **movies** `List` variable only holds a String type value.

![screenshot](https://lh6.googleusercontent.com/MYiSn2YclSUQoo50fMAusvSzrFZYBQj0ohUIui01RX84ZgnSwszZVlO_1aI0_oqIhOn0wsMoBeQ9a4BB7Uvd9l99Io2KFmG_9R65iFG4Fo9M3lHU41XTNYbD04-TLUAxuG8IsWtf)

> **Note:** Remember that in programming, if we have a list with the length `n`, we always count from 0 to `n-1`, whereas 0 refers to the first element of the list and `n-1` to the last element.
