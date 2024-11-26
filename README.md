

# Todo List API

This project provides a simple API for managing a todo list, including user authentication and CRUD operations for todos. It is an implementation of the [Todo List API project](https://roadmap.sh/projects/todo-list-api) from [roadmap.sh](https://roadmap.sh).

## Features

- User authentication (register and login)
- JWT-based authentication
- CRUD operations for todos
- Pagination support
- Secure headers with Helmet
- Protection against XSS attacks with xss-clean


## Running the project

1. Clone the repository.
2. Install dependencies:

   ```bash
   npm install 
   ```
3. Create a `.env` file and add the environment variables:

   ```env
   PORT=3000
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   JWT_EXPIRATION=30d
   ```

4. Start the server:

   ```bash
   npm start
   ```

## API Endpoints

### Authentication

- `POST /api/v1/auth/register` - Register a new user
  - **Body parameters:**
    - `name`: String
    - `email`: String
    - `password`: String
- `POST /api/v1/auth/login` - Log in with existing user credentials
  - **Body parameters:**
    - `email`: String
    - `password`: String

### Todos

- `GET /api/v1/todos` - Get a list of todos (requires authentication)
  - **Query parameters:**
    - `p`: Page number (default: 1)
- `POST /api/v1/todos` - Create a new todo (requires authentication)
  - **Body parameters:**
    - `title`: String
    - `description`: String
- `GET /api/v1/todos/:id` - Get a single todo by ID (requires authentication)
- `PUT /api/v1/todos/:id` - Update a todo by ID (requires authentication)
  - **Body parameters:**
    - `title`: String
    - `description`: String
- `DELETE /api/v1/todos/:id` - Delete a todo by ID (requires authentication)

