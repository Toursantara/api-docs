## Register User

-   **URL**

    `/register`

-   **Method**

    `POST`

-   **Request Body**

    | Parameter  | Type   | Description          |
    | ---------- | ------ | -------------------- |
    | `username` | string | User's username      |
    | `email`    | string | User's email address |
    | `password` | string | User's password      |

-   **Success Response**

    -   **Code:** 201 Created
        **Content:**
        ```json
        {
            "status": "success",
            "message": "User registered successfully"
        }
        ```
        <br>

-   **Error Responses**

    -   **Code:** 409 Conflict <br />

        **Content:**

        ```json
        {
            "status": "fail",
            "message": "Email is already in use"
        }
        ```

    -   **Code:** 400 Bad Request
        **Content:**

        ```json
        {
            "status": "fail",
            "message": "Invalid request body"
        }
        ```

    -   **Code:** 500 Internal Server Error
        **Content:**
        ```json
        {
            "status": "error",
            "message": "Internal server error"
        }
        ```

-   **Sample Request**

    ```json
    {
        "username": "exampleuser",
        "email": "example@example.com",
        "password": "examplepassword"
    }
    ```
<br>

## Login

-   **URL**

    `/login`

-   **Method**

    `POST`

-   **Request Body**

    | Parameter  | Type   | Description          |
    | ---------- | ------ | -------------------- |
    | `email`    | string | User's email address |
    | `password` | string | User's password      |

-   **Success Response**

    -   **Code:** 201 Created
        **Content:**
        ```json
        {
            "status": "success",
            "message": "Logged in successfully"
        }
        ```
        <br>

-   **Error Responses**

    -   **Code:** 401 Unauthorized <br />

        **Content:**

        ```json
        {
            "status": "fail",
            "message": "Invalid email or password"
        }
        ```

    -   **Code:** 400 Bad Request
        **Content:**

        ```json
        {
            "status": "fail",
            "message": "Invalid request body"
        }
        ```

    -   **Code:** 500 Internal Server Error
        **Content:**
        ```json
        {
            "status": "error",
            "message": "Internal server error"
        }
        ```

-   **Sample Request**

    ```json
    {
        "email": "example@example.com",
        "password": "examplepassword"
    }
    ```

## Load Places

-   **URL**

    `/load-places`

    >Route for loading all places into Firestore (just for initialization) - Don't consume this endpoint since the place is already in database

-   **Method**

    `GET`

-   **Request Body**
    | Parameter  | Type   | Description          |
    | ---------- | ------ | -------------------- |
    |            |        | Empty the body       |

-   **Success Response**

    -   **Code:** 200 Ok
        **Content:**
        ```json
        {
          "message": "All places loaded into Firestore successfully"
        }

        ```
        <br>

## Get Place

-   **URL**

    `/place/<place_id>`

-   **Method**

    `GET`
    
-   **Request Body**
    | Parameter  | Type   | Description          |
    | ---------- | ------ | -------------------- |
    |            |        | Empty the body       |

-   **Success Response**

    -   **Code:** 200 OK
        **Content:**
        ```json
        {
            "status": "success",
            "place": {
                        "category": "Budaya" 
                        "city": "Yogyakarta"
                        "description": "Taman Budaya Yogyakarta (TBY)..."
                        "place_id": "100"
                        "place_name": "Taman Budaya Yogyakarta"
                        "price": 0
                        "rating": 4.5
                    }
        }
        ```
        
-   **Error Responses**

    -   **Code:** 404 Not Found <br />

        **Content:**

        ```json
        {
            "status": "fail",
            "message": "Place not found"
        }
        ```

-   **Sample Request**

    ```bash
    GET /place/100
    ```
    <br>

    
