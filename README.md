## Creating mongoDb queries 

## Question-1 ( Approach ) :
    # Task : To list down the movies and the comments associated with it.
    ```bash
    $lookup : Utilized this to join the two collections on the "_id" field in the movie and "movie_id" in the comments collection.

    $project : To decide what entries are expected in the output.

    $map : To retrieve only a few fields that are required as per the task.