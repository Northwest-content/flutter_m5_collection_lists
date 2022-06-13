7. Replace the Frozen **Text** widget with the code below:

```dart
Text(
     movies[0], // <- here
     style: TextStyle(
       fontWeight: FontWeight.bold,
       fontSize: 18,
     ),
   )
```

> **Note**: we place the index of a specific element inside square brackets to access that element.

We replaced the _‘Frozen’_ string with the name of the list which is **movies**. We used zero index to access the first value of the **movies** list which is ‘Toy Story’.

> If you change the index from zero to one, you will get the second value of the **movies** list which is the ‘Spider Man’.

8. Replace `// TODO: #4 Create image paths list` with the code below to create another list for the images paths:

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

> Here, we have a **list** of type **String**, and it holds the images paths.

9. Replace **Image.asset** with the code below to show the image of one of the elements inside the list.

   ```dart
   Image.asset(
               imgPaths[0], // <- Here
               width: 125,
               height: 125,
             )
   ```

> **Note:** We got the right image for the **Toy Story** movie because we ordered the group of strings inside the **imgPaths** in the same order as the **movies** list.

For now, we have one **Movie** tile only, what if we want to add more tiles?

10. To do that, you can use the **Column** widget, and add the other **Movie** tiles to it.

Hover over the **Card** widget, click:

​ - Windows: **Ctrl + .**

​ - MacOS: **CMD + .**

Then choose **Wrap with widget...**

![screenshot](https://lh4.googleusercontent.com/U6EfiNcBJV0lNQqePZOgfxAygj8tYuDqijz9lxFIs_dcVBQT1JIce7lfRpKfew3YmwPRdE47il6Zg-7jyMrdYtoH0AGx-8ycU5-d5vmNSwVd07SZab--8gy6c1q4CEU5xalG2fFe)

11. Duplicate the **Card** widget three times inside the **Column**.

![screenshot](https://lh6.googleusercontent.com/cHmiFr7JkV-z8a_mYcpIro7kUwaiBDY7MDNAYB9I0JtM7cldeMjH1biROHqLNeM8vgrcTvQ7Kz5Opg9vx15RPv0zOVwBm4VId8vBNRDXr0b8lUEqLV23ymeqSlzQr_0_FMPlex0q)

Once you save the **main.dart** file, three Movie tile widgets will be displayed on the screen.

12. Change the **index** of both the second and third movie tiles.

> Do not forget to change the index of both **title** & **imgPath** .

![screenshot](https://lh5.googleusercontent.com/KY_WlLIpgdVDparErMhqxjmLULuaf9PYChr2nY2wdS89b4v6dGVU10CitI-zvqmzyOt56osxa6V1dxeS_-uPMa21WMY1FDGaL5lVJyLYZDsgrXRhPR7DAolrmtiBnL2agWxhdQtH)

**The final result**

![screenshot](https://lh3.googleusercontent.com/7b-G8ORUH5Pu0iueRBybrtF5l5u4MY9vzwLdpVp-WiA-972SW5jsHKLYURqKGpI8zNm7zS5iIoKrIvtUliZU0DfvMAoKQxsNt98yRuJ9Xrc_87LYESSGZEVwHbuw42MUtLP1Sh8E)

Try to add more **Movie** tiles inside the **Column** widget, you will notice an error appears at the bottom of the screen.

![screenshot](https://lh6.googleusercontent.com/OBoQu64xE98yY4uHDnjzVU6ff9P7oewwM7LFr-UTgL3MfrSdVLC3rSqO0ijcODb4ZfpOIv4KhDRiSWWf7MP9T_BHHbMMGtv4R84301VQeiksGf0JXHKyV_7GhkjgNdHXRFrs-2JP)

And if you check the **DEBUG CONSOLE**, you will see an **Exception**.

You got this error because the **Column** widget got bigger and does not fit the screen anymore. It took up more space than the default height of the screen.

![screenshot](https://lh6.googleusercontent.com/3LE8Mf32ULbTDhUwV8On7ff1kX2ovvyno4p5XdaSRvg3afYcsdY5oJAmhQr3RItH9tr7v7zwzXefaxPlYSudKiJDMr6ZWOkAZK1odNJ5sTkmVWQSzSSPxiVq-YIqXEYwVLpxXD7m)

This is where our hero **ListView** widget comes to save us.
