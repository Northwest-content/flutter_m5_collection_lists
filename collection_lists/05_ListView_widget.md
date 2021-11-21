# ListView widget



11. Now, we will use a new widget that will help us to show all values inside the Lists which is the **ListView** widget. Also, it is a scrollable list of widgets arranged linearly. In our example, we will use it to show all movies that we have. 

To do that copy the whole **Card** widget, then remove it

```dart
Card(
        child: Row(
          children: [
            Expanded(
              child: Container(
                padding: EdgeInsets.all(20),
                child: Text(
                  movies[0],
                  style: TextStyle(
                    fontWeight: FontWeight.bold,
                    fontSize: 18,
                  ),
                ),
              ),
            ),
            Container(
              padding: EdgeInsets.all(10),
              child: Image.asset(
                imgPaths[0],
                width: 125,
                height: 125,
              ),
            ),
          ],
        ),
      )
```





12. Now, we have an empty body, replace it with **ListView.builder** widget.

    ```dart
        // 1
          body: ListView.builder(
            // 2
            itemCount: movies.length,
            // 3
            itemBuilder: (BuildContext context, int index) {
              return Text('$index');
            },
          ),
    ```

1. First, we added a **ListView** widget which will take the entire Scaffold widget body.
2. Because we use **ListView builder**, we need to provide the **ListView** widget with the item count that this **ListView** will show, and this named argument will help the **ListView** widget to estimate the maximum scroll extent. So, here because we want to show all the values of movies, we used **movies.length** property which will give us the number of objects in this list; in our case this property will return 10.
3. We used the **itemBuilder** named argument, which will take one function that returns the **context**, and the **index** number, and return the widget each time this method is invoked. This function will be recalled several times, and the number of recalled items will be equal to the **itemCount**, and each time this function will increase the index number by one. 





13. After we replaced the scaffold body, you will see this result. 

![screenshot](https://lh6.googleusercontent.com/7pKfusFSZ1_YtuxZFfRyzxspxovO7WKAQ6Ideke9LGXPT8yP_PqvGypBTEkTr0-LZIZ_Wea6LAlDD3XU0QyxVWI0mFQDAoj0cAKHjXjTGCD_R3QxRXYYEgItBWvecOafUQv37tP8)

As you see in the above screenshot, we will have a list of numbers that start from zero to 9. The reason why we got this result; because our **itemBuilder** named argument inside the **ListView** widget returns a **Text** widget, and this **Text** widget takes the index, and as we know that the list starts from zero, where 0 is the index of the first value that why we got zero on the first value, and this index will increase by one until the end of the List. We got 9 because we have ten items inside the **movies** list.







14. Now, replace the returned widget inside the **itemBuilder** function with the widget that we copied in the **step 11**. 

```dart
 return Card(
            child: Row(
              children: [
                Expanded(
                  child: Container(
                    padding: EdgeInsets.all(20),
                    child: Text(
                      movies[0],
                      style: TextStyle(
                        fontWeight: FontWeight.bold,
                        fontSize: 18,
                      ),
                    ),
                  ),
                ),
                Container(
                  padding: EdgeInsets.all(10),
                  child: Image.asset(
                    imgPaths[0],
                    width: 125,
                    height: 125,
                  ),
                ),
              ],
            ),
          );
```

>  After we paste the widget inside the return **itermBuilder** function, we will have ten tiles that show the Toy Story movie.

![screenshot](https://lh6.googleusercontent.com/jyE1hSZxCuGuxe2t4KkPx83wS4JLw9fbNrhZSKkwSlMdEdwjI7zzv95Q6XjzqXt9NIh6fot6pm2PhYreJIAfRcAfyBVNkLNO79uRtuVqifbXoWVnyB0zgozFheRn3KeE1FzzbmX5)



15. We got this result because we didn’t change the index of the list variables inside the **Card** widgets. In other words, to show the other values of the movies, we need to change the zero index to take the index argument that passed from **itemBuilder** function.

    ```dart
    Card(
                child: Row(
                  children: [
                    Expanded(
                      child: Container(
                        padding: EdgeInsets.all(20),
                        child: Text(
                          movies[index], // <- Here
                          style: TextStyle(
                            fontWeight: FontWeight.bold,
                            fontSize: 18,
                          ),
                        ),
                      ),
                    ),
                    Container(
                      padding: EdgeInsets.all(10),
                      child: Image.asset(
                        imgPaths[index], // <- Here
                        width: 125,
                        height: 125,
                      ),
                    ),
                  ],
                ),
              );
    ```

> Here, we changed the zero index with the index variable that passed from the **itemBuilder** function. After we pass index variables inside both the **Text** widget and **Image** widget we will see all the values inside the **movies** list and **imgPaths** list. This is because the **index** variable will start from zero and increase by one until the end of the **movies** list. 



Finally,   

![screenshot](https://lh3.googleusercontent.com/_6stenCzXIGkbzoECN3_BM4GY7uYlc2eG4kgg8S8xQ58gP-0jifHDKi6LNAzYpLkYOPfvgc74cnHo5oLuhf5oi30Pz8KxhHf4Z2nJqLeRwZ6NabupK1TWIJRF0A2Kdgls_oX9jME)


**![screenshot](https://lh5.googleusercontent.com/F20HQmtLu9HtT_hoYOq8oPuUh2c78fVCnrAY2gyRlIepYhxbdIlrlLehCUO9UcvC1BDqPgUD4A_dM8ve8oYWwkgqAUgPYxzGcMA76SEO7a0B9LlgW08I9SkMzLceVzYYcpnJB7nK)**































































































