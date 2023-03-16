# IMDB-Movies-JLM
 
 ## Sources:
 
 TMDB:
 ![blue_long_2-9665a76b1ae401a510ec1e0ca40ddcb3b0cfe45f1d51b77a308fea0845885648](https://user-images.githubusercontent.com/115378901/222606437-9bd0ed89-0366-4a9b-8c12-59e310a575c2.svg)

 IMDB:
 
 ![IMDB_Logo_2016 svg](https://user-images.githubusercontent.com/115378901/222606914-51cdda13-3b87-45eb-8450-2f7073413a92.png)

 
  ## Desciption of Project:
 This project involves retrieving data from IMDB and TMDB to create a SQL database. The data from IMDB was simply downloaded as compressed CSV files, while data from TMDB was extracted using the TMDB API. 
 
 The data from these sources were combined and explored. After exploring the data, hypothesis testing was performed to understand, with statistical significance, what makes a movie successful.
 
 ## Description of Data:
 The title_basics, title_genres, genres, and title_ratings all came from the IMDB files. The tmdb_data table came from the TMDB API calls. 
 
 title_basics contains:
 - tconst : ID for a movie
 - primaryTitle : Primary movie title
 - startYear : Year released
 - runtimeMinutes : Runtime in minutes

genres contains:
- genre_id : integer ID for genre
- genre_name : genre name

title_genres is a joiner table that joins the many-to-many relationship between titles (or movies) and genres. It contains:
- tconst : ID for a movie
- genreID : ID for genre

title_ratings contains:
- averageRating : average movie rating
- numVotes : # of votes in the rating

tmdb_data contains:
- imdb_id : equivalent to tconst
- revenue : money that movie made
- budget : money used to make the movie
- certification : G, PG, PG-13, R, UR rating

 
 <img width="363" alt="tables" src="https://user-images.githubusercontent.com/115378901/225484509-f08c0209-f076-46b0-bcae-fbe358e64738.png">



 ## Methods:
 TMDB API calls were used to fetch financial information and certification ratings.
 
 ## EDA:
 The data was explored to understand what makes a movie successful. The bar plots below show that the certification rating appears to be correlated to the amount of revenue the movie generates and the budget used to make the movie. *Note: These plots only show data from movies released in 2000 and 2001
 
![revenue_certification](https://user-images.githubusercontent.com/115378901/225486560-128d0c23-6041-4c87-8510-b4d51b2e7586.png)
![budget_certification](https://user-images.githubusercontent.com/115378901/225486565-4725aaa7-3f7e-40e1-81e4-dc67f3440c61.png)
 
 ## Hypothesis Testing:
 ## Modeling:
 ## Recommendations:
 ## Next Steps:
 
 
