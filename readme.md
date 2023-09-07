![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Web Scraping Single Page (GNOD part 1)

#### Business goal:

- Check the `case_study_gnod.md` file.
- Make sure you've understood the big picture of your project:

  - the goal of the company (`Gnod`),
  - their current product (`Gnoosic`),
  - their strategy, and
  - how your project fits into this context.

  Re-read the business case and the e-mail from the CTO.

#### Instructions - Scraping popular songs

Your product will take a song as an input from the user and will output another song (the recommendation). In most cases, the recommended song will have to be similar to the inputted song, but the CTO thinks that if the song is on the top charts at the moment, the user will also enjoy a recommendation of another song that is popular at the moment.

You have to find data on the internet about currently popular songs. Popvortex maintains a weekly Top 100 of "hot" songs here: [http://www.popvortex.com/music/charts/top-100-songs.php](http://www.popvortex.com/music/charts/top-100-songs.php).

It's a good place to start! Scrape the current top 100 songs and their respective artists, and put the information into a pandas dataframe.

# Lab | Web Scraping Multiple Pages

#### Business goal:

- Check the `case_study_gnod.md` file.
- Make sure you've understood the big picture of your project:

  - the goal of the company (`Gnod`),
  - their current product (`Gnoosic`),
  - their strategy, and
  - how your project fits into this context.

  Re-read the business case and the e-mail from the CTO, take a look at the flowchart and create an initial Trello board with the tasks you think you'll have to accomplish.

##  Instructions Part 1 

#### Prioritize the MVP (Minimum Viable Product)

In the previous lab, you had to scrape data about "hot songs". It's critical to be on track with that part, as it was part of the request from the CTO.

If you couldn't finish the first lab, use this time to go back there.

#### Expand the project

If you're done, you can try to expand the project on your own. Here are a few suggestions:

- Find other lists of hot songs on the internet and scrape them too: having a bigger pool of songs will be awesome!
- Apply the same logic to other "groups" of songs: the best songs from a decade or from a country / culture / language / genre.
- Wikipedia maintains a large collection of lists of songs: https://en.wikipedia.org/wiki/Lists_of_songs

## Instructions Part 2 
#### Practice web scraping. **This is not involved with the GNOD project of the week**

As you've seen, scraping the internet is a skill that can get you all sorts of information. Here are some little challenges that you can try to gain more experience in the field. Open a new Jupyter notebook and scrape at least 3 of these sites.

- Retrieve an arbitrary Wikipedia page of "Python" and create a list of links on that page: `url ='https://en.wikipedia.org/wiki/Python'`
- Find the number of titles that have changed in the United States Code since its last release point: `url = 'http://uscode.house.gov/download/download.shtml'`
- Create a Python list with the top ten FBI's Most Wanted names: `url = 'https://www.fbi.gov/wanted/topten'`
- Display the 20 latest earthquakes info (date, time, latitude, longitude and region name) by the EMSC as a pandas dataframe: `url = 'https://www.emsc-csem.org/Earthquake/'`
- List all language names and number of related articles in the order they appear in [wikipedia.org](wikipedia.org): `url = 'https://www.wikipedia.org/'`
- A list with the different kind of datasets available in [data.gov.uk](data.gov.uk): `url = 'https://data.gov.uk/'`
- Display the top 10 languages by number of native speakers stored in a pandas dataframe: `url = 'https://en.wikipedia.org/wiki/List_of_languages_by_number_of_native_speakers'`

# Lab | API wrappers - Create your collection of songs & audio features


#### Instructions 


To move forward with the project, you need to create a collection of songs with their audio features - as large as possible! 

These are the songs that we will cluster. And, later, when the user inputs a song, we will find the cluster to which the song belongs and recommend a song from the same cluster.
The more songs you have, the more accurate and diverse recommendations you'll be able to give. Although... you might want to make sure the collected songs are "curated" in a certain way. Try to find playlists of songs that are diverse, but also that meet certain standards.

The process of sending hundreds or thousands of requests can take some time - it's normal if you have to wait a few minutes (or, if you're ambitious, even hours) to get all the data you need.

An idea for collecting as many songs as possible is to start with all the songs of a big, diverse playlist and then go to every artist present in the playlist and grab every song of every album of that artist. The amount of songs you'll be collecting per playlist will grow exponentially!


# Lab | Unsupervised learning intro (GNOD - part 4)

#### Instructions 


It's the moment to perform clustering on the songs you collected. Remember that the ultimate goal of this little project is to improve the recommendations of songs in the hope that the user will enjoy the new song.. Clustering the songs will allow the recommendation system to limit the scope of the recommendations to only songs that belong to the same cluster - songs with similar audio features.

The activities you did with the `Spotify` API and the PopVortex web scraping will allow you to create a pipeline such that when the user enters a song, you:

1. Check whether or not the input song is in the PopVortex Hot 100.
2. Recommend another Hot 100 song
3. If it is NOT in the hot 100, then collect the audio features from the `Spotify` API for the input song.
4. You want to send the `Spotify` audio features of the submitted song to the clustering model, which should return a cluster number.  
5. Then you recommend a song from the same cluster number.

Your model will be even more accurate the more songs you use to create your clusters in your model, so you want to have as many songs as possible to create the clustering model. You can find some larger datasets on Kaggle containing more songs with audio features that have already been scraped and saved as a .csv file. You can add these to your own scraped data.   Here are some links to try:
- [Datasets 1960 - 2019](https://www.kaggle.com/datasets/theoverman/the-spotify-hit-predictor-dataset?select=README.txt)
- [Datasets 1921 - 2020](https://www.kaggle.com/datasets/yamaerenay/spotify-dataset-19212020-600k-tracks?select=tracks.csv)
- [General Song Datasets](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)
