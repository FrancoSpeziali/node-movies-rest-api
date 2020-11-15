# Node Movies Rest API

In this assignment you will be expected to write an API for connecting to a movie database

## Assignments

For the backend part of this assignment, you are expected to write your code in the file `server.js`

## Assignment 1 - Sample data

Before we can begin, we will load a sample dataset to work with.

MongoDB provides multiple sample datasets, with sample data for us.

1. Log into your MongoDB account

2. In your main control panel, click on `Clusters`

3. Click on the 3 dots (...) and click on `Load Sample Dataset`

4. Follow the on screen instructions

> Note: It may take up to 15 minutes for the dataset to completely load

After this, you should have some new databases / collections:

> sample_airbnb
> sample_analytics
> sample_geospatial
> sample_mflix
> sample_restaurants
> sample_supplies
> sample_training
> sample_weatherdata

We will be using the `sample_mflix` database.

## Assignment 2 - Connect to your database

1. Use the dotenv package to load the process.env variables from your .env file

> Note: Connect to the `sample_mflix` database

2. In the file `server.js`, connect to your server

3. Check the connection

## Assignment 3 - Comments Schema & Model

Unfortunately the sample datasets do not come with Models or Schemas, so we must build our own to interact with these databases / collections.

1. Using the MongoDB viewing tool (or another similar tool), examine the data in the `comments` collection. What MongoDB data types are being used?

2. Create a `CommentSchema` schema for the collection `comments`

3. Create a `CommentModel` model for the collection `comments`

> Hint: You may use `String`, `Date`, `Number`, `Boolean` as your data types

## Assignment 4 - Movies Schema & Model

Unfortunately the sample datasets do not come with Models or Schemas, so we must build our own to interact with these databases / collections.

1. Using the MongoDB viewing tool (or another similar tool), examine the data in the `movies` collection. What MongoDB data types are being used?

2. Create a `MovieSchema` schema for the collection `movies`

3. Create a `MovieModel` model for the collection `movies`

> Hint: You may use `String`, `Date`, `Number`, `Boolean` as your data types

## Assignment 5 - 'Movies' by id endpoint

We will create an endpoint to load specific movie data, based on the movie id

1. Create an endpoint `/movieById`. This will be a `get` endpoint. The endpoint should expect a parameter, the movie id.

> Hint: In your endpoint callback you will need to use `request.params` to get the request parameters

2. Use your `MoviesModel` to find the movie by id, then:
    - If found, return a status of `200` and the resulting movie
    - If not found, return a status of `404` and an appropriate message
    
## Assignment 6 - 'Movies' search endpoint

We will create an endpoint to search for movie data

1. Create an endpoint `/movieSearch`. This will be a `get` endpoint
    - The endpoint should expect a parameter, the movie `title` to search by
    - The endpoint should expect a second parameter, the number of results to limit to search to

> Hint: In your endpoint callback you will need to use `request.params` to get the request parameters

2. Use your `MoviesModel` to find the movie by searching in the `title` field. It should:
    - Limit the results using the `limit()` method. If no value is supplied, default to `10`
    - If found, return a status of `200` and the resulting movies
    - If not found, return a status of `404` and an appropriate message

## Assignment 7 - 'Comments' endpoint

We will create an endpoint to load the comments data

1. Create an endpoint `/comments`. This will be a `get` endpoint. The endpoint should expect a parameter, the comment id.

> Hint: In your endpoint callback you will need to use `request.params` to get the request parameters

2. Use your `CommentModel` to find the comment by id, then:
    - If found, return a status of `200` and the resulting comment
    - If not found, return a status of `404` and an appropriate message
    
## Assignment 8 - Populating our comments

We will update our comments endpoint to return the populated movie data

1. Update the `/comments` endpoint to use the `populate()` method on the `movie_id` field.

2. Test that your endpoint gives you the correct result.