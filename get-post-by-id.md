# Get Post by ID

## Overview

Retrieves a single post from the posts collection using its unique
identifier.

------------------------------------------------------------------------

## Endpoint

GET https://jsonplaceholder.typicode.com/posts/1

------------------------------------------------------------------------

## Description

This endpoint returns a single post object in JSON format. It is
typically used to fetch the details of a specific post by its ID.

------------------------------------------------------------------------

## HTTP Method

GET

Used to retrieve data without modifying the server.

------------------------------------------------------------------------

## Request

### Headers

No authentication or special headers are required.

### Parameters

This endpoint does not require query or body parameters.

The post ID is included directly in the URL path.

Example: /posts/{id}

------------------------------------------------------------------------

## Example Request

### cURL

curl -X GET https://jsonplaceholder.typicode.com/posts/1

### JavaScript (Fetch)

fetch("https://jsonplaceholder.typicode.com/posts/1") .then(response =\>
response.json()) .then(data =\> console.log(data));

------------------------------------------------------------------------

## Response

### Status Code

200 OK --- The request was successful and the post was found.

### Response Format

application/json

### Example Response

{ "userId": 1, "id": 1, "title": "sunt aut facere repellat provident
occaecati", "body": "quia et suscipit suscipit recusandae consequuntur
expedita et cum" }

------------------------------------------------------------------------

## Response Fields

  Field    Type      Description
  -------- --------- -------------------------------------
  userId   integer   ID of the user who created the post
  id       integer   Unique identifier of the post
  title    string    Title of the post
  body     string    Main content of the post

------------------------------------------------------------------------

## Possible Errors

  Status Code                 Meaning
  --------------------------- ---------------------------------------
  404 Not Found               The post does not exist
  500 Internal Server Error   Server error while processing request

------------------------------------------------------------------------

## Usage Notes

-   This is a read-only endpoint.
-   No authentication is required.
-   Useful for testing API integrations and prototyping.
