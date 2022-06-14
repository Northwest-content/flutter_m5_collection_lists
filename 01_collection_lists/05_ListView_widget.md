**ListView** is a scrollable list of widgets arranged linearly. It displays its children one after another in the scroll direction i.e, vertical or horizontal.
There are many different types of **ListView**:

- ListView
- ListView.builder.
- ListView.separated
- ListView.custom.

In this project, we will go with **ListView.builder**.

13. Cut the whole `Card` widget and replace it with the **ListView.builder** widget.

```dart
    // a
    body: ListView.builder(
      // b
      itemCount: movies.length,
      // c
      itemBuilder: (BuildContext context, int index) {
        return Text('$index');
      },
    ),
```

> > a. We added a **ListView.builder** widget in the `Scaffold`'s `body`.
>
> > **Note**: The **ListView** widget requires two named arguments: The first named argument is `itemCount`, which refers to the length of the list that will be displayed, and helps the **ListView** widget to estimate the maximum scroll extent. The other named argument is **itemBuilder**, which requires a function that takes the **context** and the **index** number, and returns the widget each time it gets invoked. This function will be recalled several times based on the number of **itemCount**. Each time this function will increase the index number by one.
>
> > b. We passed the movies length to the **itemCount** named argument in the **ListView.builder**.
>
> > c. The **itemBuilder** named argument will return the index only several times for now.

![screenshot](https://lh6.googleusercontent.com/7pKfusFSZ1_YtuxZFfRyzxspxovO7WKAQ6Ideke9LGXPT8yP_PqvGypBTEkTr0-LZIZ_Wea6LAlDD3XU0QyxVWI0mFQDAoj0cAKHjXjTGCD_R3QxRXYYEgItBWvecOafUQv37tP8)

As you see in the screenshot above, we got a list of numbers that start from zero to nine. We got this result because the **itemBuilder** named argument inside the **ListView** widget returns a **Text** widget. This **Text** widget takes an index that keeps increasing by one until it reaches the **itemCount** which is 9.

14. Replace the returned widget inside the **itemBuilder** function with the **Card** widget that we cut in **step 13**.

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

> Nice! Now we have ten tiles that show the Toy Story movie.

![screenshot](https://lh6.googleusercontent.com/jyE1hSZxCuGuxe2t4KkPx83wS4JLw9fbNrhZSKkwSlMdEdwjI7zzv95Q6XjzqXt9NIh6fot6pm2PhYreJIAfRcAfyBVNkLNO79uRtuVqifbXoWVnyB0zgozFheRn3KeE1FzzbmX5)

We got this result because we did not change the index of the list variables inside the **Card** widget.

15. Change the zero index to the index argument that is passed from the **itemBuilder** function.

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

> We changed the zero index of both `imgPaths` and `movies` list to the index variable that passed from the **itemBuilder** function.

Finally,

![screenshot](https://lh3.googleusercontent.com/_6stenCzXIGkbzoECN3_BM4GY7uYlc2eG4kgg8S8xQ58gP-0jifHDKi6LNAzYpLkYOPfvgc74cnHo5oLuhf5oi30Pz8KxhHf4Z2nJqLeRwZ6NabupK1TWIJRF0A2Kdgls_oX9jME)

**![screenshot](https://lh5.googleusercontent.com/F20HQmtLu9HtT_hoYOq8oPuUh2c78fVCnrAY2gyRlIepYhxbdIlrlLehCUO9UcvC1BDqPgUD4A_dM8ve8oYWwkgqAUgPYxzGcMA76SEO7a0B9LlgW08I9SkMzLceVzYYcpnJB7nK)**
