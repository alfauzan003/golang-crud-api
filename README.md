# Simple CRUD API

This is a simple CRUD (Create, Read, Update, Delete) API built in Go for my learning purposes. The API allows you to manage a collection of movies. Instead of using a database, data is stored in memory using Go data structures.

## Features

- Get a list of all movies
- Get details of a specific movie by ID
- Create a new movie
- Update an existing movie
- Delete a movie by ID

## Project Structure

- `main.go`: The main entry point of the API that sets up the routes and starts the server.
- `mux` is used for routing.
- `Movie` and `Director` structs define the data model for movies and directors.
- The API uses in-memory storage (a slice) to store movie data.

## API Endpoints

- `GET /movies`: Get a list of all movies.
- `GET /movies/{id}`: Get details of a specific movie by ID.
- `POST /movies`: Create a new movie.
- `PUT /movies/{id}`: Update an existing movie by ID.
- `DELETE /movies/{id}`: Delete a movie by ID.

## Usage

1. Clone this repository to your local machine.
2. Run the API using the following command:

    ```bash
    go run main.go
    ```
3. The API will start on port 8000.
4. You can use tools like curl or Postman to interact with the API endpoints.

## Example Requests
- Get a list of all movies:
    ```
    curl http://localhost:8000/movies
    ```
- Get details of a specific movie by ID:
    ```
    curl http://localhost:8000/movies/1
    ```

- Create a new movie:
    ```
    curl -X POST -H "Content-Type: application/json" -d '{"isbn": "5678", "title": "New Movie", "director": {"firstname": "Jane", "lastname": "Doe"}}' http://localhost:8000/movies
    ```

- Update an existing movie by ID:
    ```
    curl -X PUT -H "Content-Type: application/json" -d '{"isbn": "5678", "title": "Updated Movie", "director": {"firstname": "Jane", "lastname": "Doe"}}' http://localhost:8000/movies/1
    ```

- Delete a movie by ID:
    ```
    curl -X DELETE http://localhost:8000/movies/1
    ```