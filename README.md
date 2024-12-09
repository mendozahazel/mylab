# Library Management API
## Overview

This API provides endpoints for managing a library system. It includes functionalities for user registration, authentication, managing books, authors, and their associations.

### Authentication

The API uses JSON Web Tokens (JWT) for authentication. Include the token in the Authorization header as a Bearer token in requests requiring authentication.

### Header Example

#### Payload
```bash
Authorization: Bearer <JWT_TOKEN>
```

### Endpoints

### 1. User Management

### Register User
#### Description: Registers a new user.
#### URL: /user/register
#### Method: POST

#### Payload
```json
{
  "username": "username",
  "password": "password"
}
```
### Response
#### Success
```json
{
    "status": "success",
    "data": null
}
```
#### Failure
```json
{
    "status": "fail",
    "data": {
        "title": "Username or password already exists"
    }
}
```

### Login User
#### Description: Authenticates a user and returns a JWT token.
#### URL: /user/login
#### Method: POST

#### Payload
```json
{
  "username": "username",
  "password": "password"
}
```
### Response
#### Success
```json
{
    "status": "success",
    "token": "JWT_TOKEN",
    "data": null
}
```
#### Failure
```json
{
    "status": "fail",
    "data": {
        "title": "Authentication failed"
    }
}
```

### 2. Author Management

### Add Author
#### Description: Adds a new author. Requires token validation.
#### URL: /user/register
#### Method: POST

#### Payload
```json
{
    "name": "author_name"
}
```
### Response
#### Success
```json
{
    "status": "success",
    "message": "Author added successfully",
    "authorid": "integer"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

### Update Author
#### Description: Updates an author's details. Requires token validation.
#### URL: /authors/update/{id}
#### URL Parameters: id: Author ID (integer)
#### Method: PUT

#### Payload
```json
{
    "name": "author_name"
}
```
### Response
#### Success
```json
{
    "status": "success",
    "message": "Author updated successfully"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

### Delete Author
#### Description: Deletes an author. Requires token validation.
#### URL: /authors/delete/{id}
#### URL Parameters: id: Author ID (integer)
#### Method: DELETE

### Response
#### Success
```json
{
    "status": "success",
    "message": "Author deleted successfully"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```


### 3. Book Management

### Add Book
#### Description:  Adds a new book. Requires token validation.
#### URL: /books/add
#### Method: POST

#### Payload
```json
{
    "title": "book_title"
}
```
### Response
#### Success
```json
{
    "status": "success",
    "message": "Book added successfully",
    "bookid": "integer"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

### Update Book
#### Description: Updates a book's details. Requires token validation.
#### URL: /books/update/{id}
#### URL Parameters: id: Book ID (integer)
#### Method: PUT

#### Payload
```json
{
    "title": "book_title"
}
```
### Response
#### Success
```json
{
    "status": "success",
    "message": "Book updated successfully"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

### Delete Book
#### Description: Deletes an author. Deletes a book. Requires token validation.
#### URL: /books/delete/{id}
#### URL Parameters: id:  Book ID (integer)
#### Method: DELETE

### Response
#### Success
```json
{
    "status": "success",
    "message": "Book deleted successfully"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

### 4. Book-Author Management

### Associate Book with Author
#### Description:  Associates a book with an author. Requires token validation.
#### URL: /books_author/add
#### Method: POST

#### Payload
```json
{
    "bookid": "integer",
    "authorid": "integer"
}
```

### Response
#### Success
```json
{
    "status": "success",
    "message": "Book-Author entry added successfully",
    "collectionid": "integer"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

### Delete Book-Author Association
#### Description: Deletes an author. Deletes a book. Requires token validation.
#### URL: /books_author/delete/{collectionid}
#### URL Parameters: id: Collection ID (integer)
#### Method: DELETE

### Response
#### Success
```json
{
    "status": "success",
    "message": "Book-Author entry deleted successfully"
}
```
#### Failure
```json
{
    "status": "fail",
    "message": "error_message"
}
```

