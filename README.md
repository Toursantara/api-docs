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
            "message": "User data stored successfully"
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
