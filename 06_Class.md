# Class



16. Let’s add ratings for our movies, to do that we will create a new list for our rating as we learned, but there is another best approach to achieve this which is creating a new **class** for our movie; a **Class** consists of a set of variables called **properties**.



17.  Inside the **lib** folder, create a new file called **movie.dart**



18. After that create a new **Movie** class by calling the **class** keyword.

```dart
class Movie {
  
}
```



19.  Then, add three properties; **name**, **imgPath**, and **rating**

```dart
 String name;
 String imgPath;
 double rating;
```

> Here we are creating three variables, two of them are String, and one is a double number. Also, note here we didn’t type any initial value for these variables. 





20.  After that go to the last line and click 
    - Mac: **Command** + **.**
    - Windows: **Ctrl + .**



21.  Click **Generate constructor** 

<img src="https://lh4.googleusercontent.com/xN0Q-0WvMZt_ABMcaSViz1E0JqVeAAmSTuPf2tBiWkr2bl-hCORllBPv6qPNfK7OCap-qEn1HOxhI-y1PteWYSbf_p_u-RNoLHNXQFNR0NJ4S-MoFx7JYAnV9FMQo1RSI5eE-gAD" alt="img" style="zoom: 50%;" />



22. You will see that VS Code, will create a constructor for our **Movie** class

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



23. Remove **movies** and **imgPaths** list.



24. Create a new list called **movies**

    ```dart
     List movies = [
        
      ];
    ```



25. Import **movie.dart** file above the **main.dart** file

```dart
import 'package:flutter_movie_app_starter/movie.dart';
```

> **Note:** you can use auto import that comes with VS Code, by calling Movie class then click the first Movie class, then the VS Code will import the **movie.dart** file automatically.



26. Inside this movies list, we will create a new Movie object for each movie we have by using the **Movie** class that we created inside the **movie.dart** file; right now let’s just create one movie object for the first movie we have.

    ```dart
     List movies = [
        Movie(name: 'Toy Story', imgPath: 'assets/toy_story.jpeg', rating: 8),
      ];
    ```

    > Here we created one object for the **Toy Story** movie, and we passed the value for each **name**, **imgPath**, and the **rating** inside the constructor.

    >  Note that this approach is cleaner than the first approach



27. We will repeat this approach, and create other objects for the other movies.

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

    

28. After we create our objects for the movies, we need to use them inside the widgets, and to do that we will use period (.) to access the properties that we have inside the Movie object. Go to the **Text** widget, and change its value.

    ```dart
    Text(
                          movies[index].name, // <- Here
                          style: TextStyle(
                            fontWeight: FontWeight.bold,
                            fontSize: 18,
                          ),
                        )
    ```

    > **Note:** here we got the object by calling the movies list with an index value, and to access its properties we used period (.), then we type the name of the property that we want to use; in our case, we used **name** property inside the **Text** widget to display the name of the movie.





29. Also, we need to change the image path, and use the **imgPath** property.

    ```dart
    Image.asset(
                        movies[index].imgPath, // <- Here
                        width: 125,
                        height: 125,
                      )
    ```

    

30. Run the app again, we will see the same result that we had before, but with a good approach, and rating value ^_^.

<img src="https://lh4.googleusercontent.com/Lo8LJJy3r27BNM6GALQRjex7fRO7_szfCsB8fWukhG-abOafUWtrdA4tmpvagjsc-5xG_Kbd8sYxTdZ4I6ZFU57BhjWcNA0wpmz9rhuild1w_Sr1IWLwITEj127TFgtKIzqHnfh5" alt="img" style="zoom:50%;" />



31. To display the **rating** for each movie, we will add a new **Text** widget. Also, we will wrap the **Text** widget that we had with the **Column** widget, and we will insert the other **rating** **Text** widget.

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

**<img src="https://lh3.googleusercontent.com/MfOiYBotK_S_aObhR4TygpVNQucCMepGpF8hr_QSQozy6k04763pq75F8Jod95qmXt1bTfBSfOkkMC8c4actEr_uIkYAMqs-8zgx9njH3nRJroL1eSprc-2e-MP6Tc4nnn7c3f3n" alt="img" style="zoom:50%;" />**

![img](https://lh3.googleusercontent.com/sWB_R-NssSz1SChYdsLQbcXNj6NuPquFLLMzOnv8iDtc73uqAJNiofOc8B0-QPYbtlVLPWGVSj3S1v9LV54D2HZd-ra0bi_TbHjLGgPLFl-vqa5oy22r60hvIdVEF-BQTcCICx4r)























































































































