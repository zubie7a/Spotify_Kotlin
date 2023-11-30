## Santiago Zubieta
#### 2023

## Spotify Wrapped with Kotlin (?)
A quick attempt at gathering music listening insights similar to Spotify Wrapped

### What's this about?
Yesterday the **Spotify Wrapped** came out and I was very excited to check it!

However I wanted to have a few extra insights, so I requested my data export.

This export can take many days, or even weeks, and I was impatient, so I looked for data somwehere else in the meantime.

I have Spotify connected with **LastFM**, so every song I listen to is logged there. With [this website](https://mainstream.ghan.nl/export.html) I can export my LastFM data in JSON or CSV, so I just did that!

Python and Pandas sound like a better candidate for analysing this data, but I wanted to give a try to Kotlin dataframes and their Jupyter notebook integration.

So I created this [notebook](https://github.com/zubie7a/Spotify_Kotlin/blob/main/ZWrapped.ipynb), which has just some basic aggregations on the music data for curiosity.

Then I manually made some poorly designed graphics mimicking the actual Wrapped.
  
**Sorry to any designers looking at these!**

Afterwards I compared the insights from the Spotify Wrapped with the LastFM data, but there's a few discrepancies, I suspect sometimes the Spotify-LastFM integration stops working and it skips some scrobbles, and also the cutoff date for the Spotify Wrapped is unknown so the best I can do is an estimate.

**I suspect Spotify doesn't include December in the Wrapped because it'd be full of christmas music!**

The data from LastFM is very limited, just names of songs, albums, artists, and timestamps, so only basic data aggregations can be performed.

With this data I tried extracting the following stuff for **2022** and **2023** to compare:

* A chart with the count of songs played every day the whole year
* A chart with the count of songs played every hour
* Songs, albums, and artists most listened to in 2023, and their change in ranking compared to 2022
* Songs, albums, and artists most listened to in a same day
* Songs, albums, and artists most listened to in 2023 which I hadn't listened to in 2022
* Songs, albums, and artists most listened to in 2022 which I didn't listen again in 2023
* The amount of unique songs I've listened to
* The amount of unique artists I've listened to
* The total amount of songs (including repeats) I've listened to

With the full Spotify export I hope I'm also able to get data like:
* My playlists' content, to join it with streaming data to see how often, how long, and at what time I listen to my almost 200 playlists
* The amount time from each song actually listened to, to compute total listening time for songs, albums, artists, and playlists

I wish there was more data to play with but this should be enough for now!

### How to run
This initial version expects that you have a LastFM account where you have scrobbled your songs' data. A future revision will include these operations with the Spotify exported data.
1. Get your LastFM data export from https://mainstream.ghan.nl/export.html 
2. Make sure you either have Kotlin Notebook plugin for IDEA Ultimate or install Kotlin support for Jupyter
   - IDEA Ultimate [Kotlin Notebook plugin](https://plugins.jetbrains.com/plugin/16340-kotlin-notebook)
   - If you have Conda use: `$ conda install -c jetbrains kotlin-jupyter-kernel`
3. Open notebook and make sure the filename matches your export.

### Interesting Resources
* LetsPlot Kotlin https://lets-plot.org/kotlin/
* Kotlin DataFrame documentation https://kotlin.github.io/dataframe/gettingstarted.html
* Kotlin libraries for Data Science https://kotlinlang.org/docs/data-science-overview.html
* Kotlin Data Frame Overview by Anatoly Nitikin https://www.youtube.com/watch?v=qGou8F2asNw
* Replacing SQL with Kotlin's 'dataframe' on the Las Vegas Strip by Andrew Goldberg https://www.youtube.com/watch?v=sDZWiu9nnuU

### Wrapped Images
I hope this doesn't hurt the eyes of people who actually designs these things:
  
![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_1_Charts.png?raw=true)

![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_8_Time_Of_Day.png?raw=true)

![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_2_Totals_Unique.png?raw=true)
  
![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_3_Albums.png?raw=true)
  
![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_4_Songs.png?raw=true)
  
![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_5_Artists.png?raw=true)

![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_6_Top_Only_2022.png?raw=true)

![](https://github.com/zubie7a/Spotify_Wrapped_Kotlin/blob/main/Wrapped_7_Top_Only_2023.png?raw=true)