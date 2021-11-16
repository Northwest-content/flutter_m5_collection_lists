# Creating the movie app UI



1. Download the starter project from GitHub, then open the project by using the **VS Code**, and get the packages.

> https://github.com/Northwest-content/flutter_movie_app_starter



2. In this starter project, we already added the movie images that we will use inside the app. Also, we added these images inside **pubspec.yaml** file.



3. The first step for the movie app UI is the tile, we will create a tile widget that holds our movie information such as the name of the movie & image.



4. To create a tile widget, replace `// TODO: #1 Create movie tile` with 

```dart
   // 1
      body: Card(
        // 2
        child: Row(
          children: [
            // 3
            Container(
              padding: EdgeInsets.all(20),
              //4
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

1. Here, we create the tile widget that will show the name of the movie, so we used a **Card** widget to style this widget.
2. We used a **Row** widget to add widgets together from left to right.
3. Using **Container** widget to add some padding for our **Text** widget.
4. Using **Text** widget to show the name of the movie; for example, here we used Frozen movie as an example. Also, we added some text styles such as font-weight and font size.

<img src="https://lh5.googleusercontent.com/BOMWNAolE4vzRFtWYKSiEDLs4NCQpuX8TDkksoa4HBtCDrDk-i4Cxmx3iWboS7tryYqnIUGwMs5MtgZHH0xufr5ElIpOLIfHcVwVvW803L4AwOie4dcRDAhQNVTmIy3EFmQ2RTX_" alt="img" width="350" />



5. Next, we will add the movie poster image; to do that replace `// TODO: #3 Add image widget ` with 

```dart
		// 1
         Container(
              padding: EdgeInsets.all(10),
              // 2
              child: Image.asset(
                'assets/frozen.jpeg',
                // 3
                width: 125,
                height: 125,
              ),
            ),
```

1.  First, we wrapped the image widget with **Container** to add some padding.
2. Here, we used **Image.asset** widget to show the frozen image inside the assets folder.
3. Changing the width and height for the image.

<img src="https://lh5.googleusercontent.com/P8xSDlW_ZF7KOK2JgsP-iNaCHXHonnOQW1hUEdECl75DleHBblRztdXRxelVFPoK_ajMTbzhWv-Sl9YcEFedkD5f1I5ajC7hZAgaTQGn5JEI79vCs6-EX50mMXPxAdv9RXwdGpS7" alt="img" width="350" />

Here, we add the name of the movie with its poster, but we don’t like the style of the tile widget.



6. Wrap the **Container** widget that holds the **Text** widget with **Expanded** widget, to take the remaining space inside the **Row** widget.

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

<img src="https://lh4.googleusercontent.com/eJE5kyRRGbG2FSHvrVUTLSgOc3Mz-INqpyncWRZL_0Vc8H2fGqlgMj7Mk0cYePgBgg_zJi-GAp7pMw1GT-UoHPipOXyMVWxWP0kw2j8Bp5t6PGLSYzr_JkNz8MeLbpUkDHK5GuRl" alt="img" width="350" />



Now we have a good tile widget for our movies.

<img src="https://lh6.googleusercontent.com/9hdCbAoPSajX4-feFKEMCaem4qXJr41tqlGfwOvu2f8-au8r9M3d64AGr7F0ysK2PjoDgvSM7kavZNKba2j5XsJgCKaVThDECQvtHqtis_VNIhFRNU8ia3rdQoqwevmt45XsUGNN" alt="img" width="350" />































































































































