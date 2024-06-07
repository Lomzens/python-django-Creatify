Creatify
如果你的项目有一个特定的名称，可以在这里写上项目名称。

Django REST API with JWT Authentication
This project is a Django application that provides a RESTful API with JWT authentication. It includes endpoints for user signup, signin, and user profile retrieval.

Features
User signup (/signup/): Allows users to register by providing an email and password.
User signin (/signin/): Authenticates users and provides JWT tokens for accessing protected endpoints.
User profile (/me/): Retrieves the current user's profile information using JWT authentication.
Requirements
Docker
Docker Compose
Installation and Setup
Clone the repository


git clone https://github.com/your_username/your_repository.git
cd your_repository
Environment Variables

Create a .env file in the project root and add the following variables:


SECRET_KEY=your_django_secret_key
DEBUG=1
Replace your_django_secret_key with a secure random string for Django's secret key.

Run Docker Compose

Start the Docker containers using Docker Compose:


docker-compose up
This will build the Docker images and start the Django application along with the required services (e.g., database).

Apply Migrations

Open another terminal or stop the running Docker Compose process (Ctrl+C) and apply Django migrations:


docker-compose exec web python manage.py migrate
Accessing the API

Once the Docker containers are running, the API should be accessible at http://localhost:8000.

API Endpoints
Signup: POST /signup/


curl --location --request POST 'http://localhost:8000/signup/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "test@example.com",
    "password": "your_password"
}'
Signin: POST /signin/


curl --location --request POST 'http://localhost:8000/signin/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "test@example.com",
    "password": "your_password"
}'
User Profile: GET /me/


curl --location --request GET 'http://localhost:8000/me/' \
--header 'Authorization: Bearer <your_access_token>'
Replace <your_access_token> with the token obtained from the /signin/ endpoint.

Contributing
Fork the repository
Create a new branch (git checkout -b feature/new-feature)
Make your changes
Commit your changes (git commit -am 'Add new feature')
Push to the branch (git push origin feature/new-feature)
Create a new Pull Request
License
null
