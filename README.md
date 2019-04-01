# MovieChatbot

#### School project about a simple chatbot that tells you information of movies using the omdbapi API and Node JS.

As a small project, try to finish your movie bot by implementing the following steps or adding your proper ideas to make your chatbot as user friendly as possible!

The api results are detailed information on each movie including its exact Title Year omdbID poster. At first we chosed TMDB api. This api can pick out matching movies based on type, actor, year, director, etc. It has more choices. But it needs project url information. So finally we chosed simple api omdb.

You can ask like : 
- Movie <Moviename>
- i want to know information about <MovieName>
  
 For the recommandation system, we use langage R et collaborative filtering. 
 Our recommendation system is based on collaborative filtering and the details can be referred as follow:

We use statistic environment R to build our recommendation system.

Before we import our dataset we change separator “::” into “~” because R didn’t support double separator.

Then we import following packages and use these packages to deal with our data:
```
library(readr) for reading .dat document (from .dat to data frame)
e.g. ratings <- read_delim("ratings.dat", "~", 
                      escape_double = FALSE, trim_ws = TRUE)
```

after some steps of data selection we only preserve 3 column: UserID, MovieID and Rating 
library(data.table) and library(reshape) for data transformation (from data frame to matrix)
We change our data from this kind of format to a matrix
    user item rating
    5    u1   i2      2
    7    u1   i3      3
    9    u1   i4      5
    10   u1   i6      5
    13   u1   i8      4
    1    u2   i1      2

        item
 user i1 i2 i3 i4 i5 i6 i7 i8 i9 i10
   u1 NA  2  3  5 NA  5 NA  4 NA  NA
   u2  2 NA NA NA NA NA NA NA  2   3
   u3  2 NA NA NA NA  1 NA NA NA  NA
   u4  2  2  1 NA NA  5 NA  0  2  NA
   u5  5 NA NA NA NA NA NA  5 NA   4

```library ( "recommenderlab" )``` for collaborative filtering algorithm

We use Item based collaborative filtering (IBCF) to train our data and then use 

Predict function to make prediction e.g. use 1-800 user to train and predict user 801-803’s preference.



