
# Creatify

## Django REST API with JWT Authentication

This project is a Django application that provides a RESTful API with JWT authentication. It includes endpoints for user signup, signin, and user profile retrieval.

### Features

- **User Signup** (`/signup/`):
  Allows users to register by providing an email and password.

- **User Signin** (`/signin/`):
  Authenticates users and provides JWT tokens for accessing protected endpoints.

- **User Profile** (`/me/`):
  Retrieves the current user's profile information using JWT authentication.

### Installation and Setup

1. **Clone the repository**

   ```
   git clone https://github.com/your_username/your_repository.git
   cd your_repository
   ```

2. **Environment Variables**

   Create a `.env` file in the project root and add the following variables:

   ```
   SECRET_KEY=your_django_secret_key
   DEBUG=1
   ```

   Replace `your_django_secret_key` with a secure random string for Django's secret key.

3. **Run Docker Compose**

   Start the Docker containers using Docker Compose:

   ```
   docker-compose up
   ```

   This will build the Docker images and start the Django application along with the required services (e.g., database).

4. **Apply Migrations**

   Open another terminal or stop the running Docker Compose process (Ctrl+C) and apply Django migrations:

   ```
   docker-compose exec web python manage.py migrate
   ```

5. **Accessing the API**

   Once the Docker containers are running, the API should be accessible at `http://localhost:8000`.

### API Endpoints

- **Signup**: `POST /signup/`

  ```
  curl --location --request POST 'http://localhost:8000/signup/' \
  --header 'Content-Type: application/json' \
  --data-raw '{
      "email": "test@example.com",
      "password": "your_password"
  }'
  ```

- **Signin**: `POST /signin/`

  ```
  curl --location --request POST 'http://localhost:8000/signin/' \
  --header 'Content-Type: application/json' \
  --data-raw '{
      "email": "test@example.com",
      "password": "your_password"
  }'
  ```

- **User Profile**: `GET /me/`

  ```
  curl --location --request GET 'http://localhost:8000/me/' \
  --header 'Authorization: Bearer <your_access_token>'
  ```

  Replace `<your_access_token>` with the token obtained from the `/signin/` endpoint.

### Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/new-feature`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add new feature'`)
5. Push to the branch (`git push origin feature/new-feature`)
6. Create a new Pull Request

### License
free.
