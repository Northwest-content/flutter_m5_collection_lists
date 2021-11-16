# Showing the values inside the List





8. To access these values inside the movies list, we can use the **index**. Replace the Frozen **Text** widget with 

   ```dart
   Text(
                     movies[0], // <- here
                     style: TextStyle(
                       fontWeight: FontWeight.bold,
                       fontSize: 18,
                     ),
                   )
   ```

   

We replaced the *‘Frozen’* string with the name of our list which is **movies**. Also, note that we used **square brackets** to access the values inside the **movies**. Here, we used zero index, to access the first value inside the **movies** list which is ‘Toy Story’. 

> If you change the index from zero to one, you will see the second value inside the **movies** list variable which is the ‘Spider Man’.





9. We will create another list for the image paths, so replace `// TODO: #4 Create image paths list` with 

```dart
  List imgPaths = [
    'assets/toy_story.jpeg',
    'assets/spider_man.jpeg',
    'assets/inside_out.jpeg',
    'assets/lego.jpeg',
    'assets/lion_king.jpeg',
    'assets/frozen.jpeg',
    'assets/shrek.jpeg',
    'assets/big_hero.jpeg',
    'assets/ice_age.jpeg',
    'assets/brave.jpeg',
  ];
```

> Here, we also have a **list** of type **String**, and it holds the image paths.





10. After we added the image paths list, we will show one value of this list inside the image widget. Replace **Image.asset** with 

    ```dart
    Image.asset(
                    imgPaths[0], // <- Here
                    width: 125,
                    height: 125,
                  )
    ```

    > **Note:** the reason why we got the right image for the **Toy Story** movie is that we ordered the group of strings inside the **imgPaths** same as the **movies** list order. So, here we used zero index, and we got the correct image for the **Toy Story** movie.



Now, we have just one **Movie** tile, we want to add more tiles. To do that, we will use the **Column** widget, and inside add more **Movie** tiles.

Hover the **Card** widget, then click,

​	- Windows: **Ctrl + .**

​	- MacOS: **CMD + .**

Then click **Wrap with widget...**

<img src="https://lh4.googleusercontent.com/U6EfiNcBJV0lNQqePZOgfxAygj8tYuDqijz9lxFIs_dcVBQT1JIce7lfRpKfew3YmwPRdE47il6Zg-7jyMrdYtoH0AGx-8ycU5-d5vmNSwVd07SZab--8gy6c1q4CEU5xalG2fFe" alt="img" width="450" />

Click **Wrap with Column**





After that copy the Card widget tree, then paste it down the first **Card** widget three times.

<img src="https://lh6.googleusercontent.com/cHmiFr7JkV-z8a_mYcpIro7kUwaiBDY7MDNAYB9I0JtM7cldeMjH1biROHqLNeM8vgrcTvQ7Kz5Opg9vx15RPv0zOVwBm4VId8vBNRDXr0b8lUEqLV23ymeqSlzQr_0_FMPlex0q" alt="img" width="450" />



After you save the **main.dart** file, you will see on the emulator there will be three Movie tile widgets.

Now, change the **index** for both the second and third movie tiles. 

>  Don’t forget to change the **title** index & **imgPath** index.

<img src="https://lh5.googleusercontent.com/KY_WlLIpgdVDparErMhqxjmLULuaf9PYChr2nY2wdS89b4v6dGVU10CitI-zvqmzyOt56osxa6V1dxeS_-uPMa21WMY1FDGaL5lVJyLYZDsgrXRhPR7DAolrmtiBnL2agWxhdQtH" alt="img" width="450" />





**The final result** </br>
<img src="https://lh3.googleusercontent.com/7b-G8ORUH5Pu0iueRBybrtF5l5u4MY9vzwLdpVp-WiA-972SW5jsHKLYURqKGpI8zNm7zS5iIoKrIvtUliZU0DfvMAoKQxsNt98yRuJ9Xrc_87LYESSGZEVwHbuw42MUtLP1Sh8E" alt="img" width="350" />




Now, try to add more **Movie** tiles inside the **Column** widget.



After adding more Movie tiles inside the **Column** widget, you will see an error down on the screen. 

<img src="https://lh6.googleusercontent.com/OBoQu64xE98yY4uHDnjzVU6ff9P7oewwM7LFr-UTgL3MfrSdVLC3rSqO0ijcODb4ZfpOIv4KhDRiSWWf7MP9T_BHHbMMGtv4R84301VQeiksGf0JXHKyV_7GhkjgNdHXRFrs-2JP" alt="img" width="350" />


Also, if you see the **DEBUG CONSOLE**, you will see an **Exception**. We got this error because the **Column** widget will take the entire screen, the **widgets** inside the **children** named argument; It took up more space than the height of the screen so we got this error.

<img src="https://lh6.googleusercontent.com/3LE8Mf32ULbTDhUwV8On7ff1kX2ovvyno4p5XdaSRvg3afYcsdY5oJAmhQr3RItH9tr7v7zwzXefaxPlYSudKiJDMr6ZWOkAZK1odNJ5sTkmVWQSzSSPxiVq-YIqXEYwVLpxXD7m" alt="img" width="350" />




To solve this error we will use **ListView** widget























































































