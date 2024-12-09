# Question-1 ( Approach ) :
## Task : To list down the movies and the comments associated with it.
    $lookup : Utilized this to join the two collections on the "_id" field in the movie and "movie_id" in the comments collection.

    $project : To decide what entries are expected in the output.

    $map : To retrieve only a few fields that are required as per the task.

# Question-2 ( Approach ) :
## Task : To count the number of comments for each movie
    $group : To group the entire collection based on the title of the movie, so that multiple instances can be considered together.

    $sum : To calculate the total sum of the number of comments after the grouping is done on a title, This gives the total number of comments on a movie with a given Title.

    $project : To decide what to expect in the output.

# Question-3 ( Approach ) :
## Task : To list down the top 5 movies, that have the highest average IMDB rating

    $group : To group the entire collection based on the title of the movie, so that multiple instances can be considered together.

    $avg : To calculate the average imdb rating

    $sum : To calculate the total sum of the number of comments after the grouping is done on a title, This gives the total number of comments on a movie with a given Title.

    $sort : To sort the data in descending order of the average imdbRating.

    $limit : To set the limit of number of documents to be retrieved.

    $project : To decide what to expect in the output.

# Question-4 ( Approach ) :
## Task : To get the list of all unique cast members across all the movies and to count how many movies each cast member has appeared in

    $unwind : To break the array of cast into individual cast member, so they can be grouped together.

    $group : To group the data on each cast member, to know the frequency of his/her appearance.

    $project : To decide what to expect in the output, moviecount, castmember etc.

# Question-5 ( Approach ) :
## Task : To get the list of all movies released before 1950 and have average imdb rating >= 7 along with the top two comments for each movie.

    $match : To make a match where the year is < 1950.

    $lookup : To join the data to get the comments associated with the movie.

    $addFields : Adds the average IMDb rating using $avg on the imdb.rating field.

    $match : To make a match where the average imdb rating is >= 7

    $project : To decide what to expect in the output, moviecount, castmember etc.

    $map : For each comment, we want to display certain data only, name and text.
    Using map, we define only these two entries to come as output.
