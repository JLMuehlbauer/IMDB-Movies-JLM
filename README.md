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
 
 **title_basics contains:**
 - tconst : ID for a movie
 - primaryTitle : Primary movie title
 - startYear : Year released
 - runtimeMinutes : Runtime in minutes

**genres contains:**
- genre_id : integer ID for genre
- genre_name : genre name

**title_genres** is a joiner table that joins the many-to-many relationship between titles (or movies) and genres. It contains:
- tconst : ID for a movie
- genreID : ID for genre

**title_ratings contains:**
- averageRating : average movie rating
- numVotes : # of votes in the rating

**tmdb_data contains:**
- imdb_id : equivalent to tconst
- revenue : money that movie made
- budget : money used to make the movie
- certification : G, PG, PG-13, R, UR rating

 
 <img width="363" alt="tables" src="https://user-images.githubusercontent.com/115378901/225484509-f08c0209-f076-46b0-bcae-fbe358e64738.png">



 ## Methods:
 - TMDB API calls were used to fetch financial information and certification ratings for movies released between 2000 and 2009 (2000s). 
 - Hypothesis tests were utilized to understand what made movies produced in this time period successful
   - One-way ANOVA
   - Independent T-test
 
 ## EDA:
 The data was explored to understand what makes a movie successful. The bar plots below show that the certification rating appears to be correlated to the amount of revenue the movie generates and the budget used to make the movie. *Note: These plots only show data from movies released in 2000 and 2001
 
![revenue_certification](https://user-images.githubusercontent.com/115378901/225486560-128d0c23-6041-4c87-8510-b4d51b2e7586.png)
![budget_certification](https://user-images.githubusercontent.com/115378901/225486565-4725aaa7-3f7e-40e1-81e4-dc67f3440c61.png)
 
 ## Hypothesis Testing:
 
 ### Q1: Does the MPAA rating of a movie (G/PG/PG-13/R) affect how much revenue the movie generates?
 
 **Visual**
 ![rev_cert](https://user-images.githubusercontent.com/115378901/225804164-33417b27-d263-4320-8ab7-83b251eb1e61.png)

 **Tests Used**
 - Kruskal-Wallis, result: p-value < 0.05, There is a statistical difference between revenue of each MPAA rating.
 - Tukey, result: R-rated movies have lower revenue than the other ratings. The other ratings (G/PG/PG-13) did not have a significant difference in their revenues.
 
 ### Q2: Does having an above average budget affect how much revenue the movie generates?
 
 **Visual**
 ![rev_budget](https://user-images.githubusercontent.com/115378901/225804187-3d65b3d9-545e-4462-ae1b-97f16492e905.png)

 **Tests Used**
 - Independent t-test, result: p-value << 0.05, the null hypothesis that there is not significant differnce between the means was rejected. Movies with with above average budgets generate higher revenue than those that have lower than average revenue.
 
 ### Q3: Do some movie genres earn more revenue than others?
 
 **Visual**
 ![rev_genre](https://user-images.githubusercontent.com/115378901/225804202-b9bc38f7-8d1f-4580-b109-100fbac1922f.png)
 
 **Tests Used**
 - Kruskal-Wallis, result: p-value < 0.05, There is a statistical difference between revenue of each genre.
 - Tukey, result: Many comparisions... Adventure and Animation generate statistically more revenue than all other genres sans Family and Fantasy.
 
 
 ## Recommendations:
 
 To increase movie revenue, studios should follow the following guidelines:
 - Do not make R-rated movies
 - Produce movies with higher than industry average budgets (~$17,000,000)
 - Produce Adventure or Animation movies
 
 ## Next Steps:
 
 Develop a linear regression model to understand all the interations between the available features and revenue. 
 
