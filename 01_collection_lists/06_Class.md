16. Let’s add ratings for our movies. To do that, we will create a new list for our rating. However, there is a better approach to do that: creating a new **class** for our movie, which consists of a set of variables called **properties**.

17. Create a new file called **movie.dart** inside the **lib** folder.

18. Create a new **Movie** class by calling the **class** keyword.

```dart
class Movie {

}
```

19. Add three properties; **name**, **imgPath**, and **rating**

```dart
 String name;
 String imgPath;
 double rating;
```

> Here we are creating three variables, two of them are String, and one is a double number. Note that we did not type any initial value for these variables.

20. Go to the last line of the class and click:

    - Mac: **Command** + **.**
    - Windows: **Ctrl + .**

Then, Click **Generate constructor**.

![screenshot](https://lh4.googleusercontent.com/xN0Q-0WvMZt_ABMcaSViz1E0JqVeAAmSTuPf2tBiWkr2bl-hCORllBPv6qPNfK7OCap-qEn1HOxhI-y1PteWYSbf_p_u-RNoLHNXQFNR0NJ4S-MoFx7JYAnV9FMQo1RSI5eE-gAD)

You will see that VS Code will create a constructor for the **Movie** class.

```dart
class Movie {
  String name;
  String imgPath;
  double rating;
  Movie({
    required this.name,
    required this.imgPath,
    required this.rating,
  });

}
```

21. Remove **movies** and **imgPaths** list.

22. Create a new list called **movies**

    ```dart
     List movies = [

      ];
    ```

23. Import the **movie.dart** file inside the **main.dart** file

```dart
import 'package:flutter_movie_app_starter/movie.dart';
```

> **Note:** You can use `auto import` that comes with the VS Code by calling Movie class and clicking the first Movie class, then the VS Code will import the **movie.dart** file automatically.

24. Inside this movies list, we will create a new Movie object for each movie we have by using the **Movie** class that we created inside the **movie.dart** file. Right now, let’s just create one movie object for the first movie we have.

    ```dart
     List movies = [
        Movie(name: 'Toy Story', imgPath: 'assets/toy_story.jpeg', rating: 8),
      ];
    ```

    > Here, we created one object for the **Toy Story** movie, and we passed the value of each **name**, **imgPath**, and the **rating** inside the constructor.

    > Note that this approach is cleaner than the first approach

25. We will repeat this approach, and create other objects for the other movies.

    ```dart
    List movies = [
        Movie(name: 'Toy Story', imgPath: 'assets/toy_story.jpeg', rating: 8),
        Movie(name: 'Spider Man', imgPath: 'assets/spider_man.jpeg', rating: 5),
        Movie(name: 'Inside out', imgPath: 'assets/inside_out.jpeg', rating: 7),
        Movie(name: 'The LEGO Movie', imgPath: 'assets/lego.jpeg', rating: 5.5),
        Movie(name: 'The Lion King', imgPath: 'assets/lion_king.jpeg', rating: 9),
        Movie(name: 'Frozen', imgPath: 'assets/frozen.jpeg', rating: 4.5),
        Movie(name: 'Shrek', imgPath: 'assets/shrek.jpeg', rating: 8.5),
        Movie(name: 'BIG HERO', imgPath: 'assets/big_hero.jpeg', rating: 8),
        Movie(name: 'ICE AGE', imgPath: 'assets/ice_age.jpeg', rating: 7.5),
        Movie(name: 'BRAVE', imgPath: 'assets/brave.jpeg', rating: 7),
      ];
    ```

26. After we create our objects for the movies, we need to use them inside the widgets. To do that, we will use period (.) to access the properties that we have inside the Movie object.
27. Change the value of the Text widget.

    ```dart
      Text(
          movies[index].name, // <- Here
          style: TextStyle(
            fontWeight: FontWeight.bold,
            fontSize: 18,
          ),
        )
    ```

28. Use the **imgPath** property.

    ```dart
    Image.asset(
                movies[index].imgPath, // <- Here
                width: 125,
                height: 125,
              )
    ```

29. Run the app again. You will see the same result. However, this approach, this time is better and you added a rating value.

![screenshot](https://lh4.googleusercontent.com/Lo8LJJy3r27BNM6GALQRjex7fRO7_szfCsB8fWukhG-abOafUWtrdA4tmpvagjsc-5xG_Kbd8sYxTdZ4I6ZFU57BhjWcNA0wpmz9rhuild1w_Sr1IWLwITEj127TFgtKIzqHnfh5)

30. To display the **rating** of each movie, add a new **Text** widget, wrap the **Text** widget that we had with the **Column** widget, and insert the other **rating** **Text** widget.

    ```dart
    Expanded(
            child: Container(
              padding: EdgeInsets.all(10),
              child: Column(
                children: [
                  Text(
                    '${movies[index].name}',
                    style: TextStyle(
                      fontWeight: FontWeight.bold,
                      fontSize: 18,
                    ),
                  ),
                  Container(height: 10),
                  Text(
                    'Rating: ${movies[index].rating}/10',
                    style: TextStyle(
                      fontWeight: FontWeight.bold,
                      color: Colors.grey[700],
                      fontSize: 14,
                    ),
                  ),
                ],
              ),
            ),
          ),
    ```

**The final result**

**![screenshot](https://lh3.googleusercontent.com/MfOiYBotK_S_aObhR4TygpVNQucCMepGpF8hr_QSQozy6k04763pq75F8Jod95qmXt1bTfBSfOkkMC8c4actEr_uIkYAMqs-8zgx9njH3nRJroL1eSprc-2e-MP6Tc4nnn7c3f3n)**

![screenshot](https://lh3.googleusercontent.com/sWB_R-NssSz1SChYdsLQbcXNj6NuPquFLLMzOnv8iDtc73uqAJNiofOc8B0-QPYbtlVLPWGVSj3S1v9LV54D2HZd-ra0bi_TbHjLGgPLFl-vqa5oy22r60hvIdVEF-BQTcCICx4r)
