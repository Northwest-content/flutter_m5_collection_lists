1. Fork and clone the starter point of the project from [GitHub](https://github.com/Northwest-content/flutter_movie_app_starter), open it in the **VS Code**, and get the packages.

2. The images that will be used inside the app were already added in the assets folder, and their paths were placed inside **pubspec.yaml** file.

3. Replace `// TODO: #1 Create movie tile` with the code below to create a tile widget that holds the movie information such as the name and the image of the movie.

```dart
   // a
      body: Card(
        // b
        child: Row(
          children: [
            // c
            Container(
              padding: EdgeInsets.all(20),
              //d
              child: Text(
                'Frozen',
                style: TextStyle(
                  fontWeight: FontWeight.bold,
                  fontSize: 18,
                ),
              ),
            ),
            // TODO: #3 Add image widget
          ],
        ),
      ),
```

> > a. We created the tile widget that shows the name of the movie, and we used a **Card** widget to style it.
> > b. We used the **Row** widget to display the widgets horizontally on the screen.
> > c. We used the **Container** widget to add some padding to the **Text**.
> > d. We used the **Text** widget to show the name of the movie, in addition to some text styles such as `font-weight` and `font-size`.

![screenshot](https://lh5.googleusercontent.com/BOMWNAolE4vzRFtWYKSiEDLs4NCQpuX8TDkksoa4HBtCDrDk-i4Cxmx3iWboS7tryYqnIUGwMs5MtgZHH0xufr5ElIpOLIfHcVwVvW803L4AwOie4dcRDAhQNVTmIy3EFmQ2RTX_)

4. Replace `// TODO: #3 Add image widget ` with the code below to add the movie poster:

```dart
  // a
    Container(
        padding: EdgeInsets.all(10),
        // b
        child: Image.asset(
          'assets/frozen.jpeg',
          // c
          width: 125,
          height: 125,
        ),
      ),
```

> > a. We wrapped the image widget with a **Container** to add some padding.
> > b. We used the **Image.asset** widget to show the frozen image inside the assets folder.
> > c. We added a width and height for the image.

<!-- The screenshots are too big, it would be better if we decrease their sizes -->

![screenshot](https://lh5.googleusercontent.com/P8xSDlW_ZF7KOK2JgsP-iNaCHXHonnOQW1hUEdECl75DleHBblRztdXRxelVFPoK_ajMTbzhWv-Sl9YcEFedkD5f1I5ajC7hZAgaTQGn5JEI79vCs6-EX50mMXPxAdv9RXwdGpS7)

We added the name of the movie with its poster, but the style of the tile widget looks ugly, so we are going to fix it a bit:

5. Wrap the **Container** that holds the **Text** with the **Expanded** widget to take the remaining space inside the **Row** widget.

```dart
     Expanded(
          child: Container(
            padding: EdgeInsets.all(20),
            child: Text(
              'Frozen',
              style: TextStyle(
                fontWeight: FontWeight.bold,
                fontSize: 18,
              ),
            ),
          ),
        ),
```

![screenshot](https://lh4.googleusercontent.com/eJE5kyRRGbG2FSHvrVUTLSgOc3Mz-INqpyncWRZL_0Vc8H2fGqlgMj7Mk0cYePgBgg_zJi-GAp7pMw1GT-UoHPipOXyMVWxWP0kw2j8Bp5t6PGLSYzr_JkNz8MeLbpUkDHK5GuRl)

Now, we have an excellent tile widget for each movie.

![screenshot](https://lh6.googleusercontent.com/9hdCbAoPSajX4-feFKEMCaem4qXJr41tqlGfwOvu2f8-au8r9M3d64AGr7F0ysK2PjoDgvSM7kavZNKba2j5XsJgCKaVThDECQvtHqtis_VNIhFRNU8ia3rdQoqwevmt45XsUGNN)
