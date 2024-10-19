# laravel-docker-setup
A Complete Guide to containerize Laravel Application using Docker And Docker Compose


# Steps to Dockerize a Laravel Application Using Docker Compose

Step 1: Create a Laravel Project
If you already have a Laravel project, you can skip this step. Otherwise, create a new Laravel project using Composer:

	composer create-project --prefer-dist laravel/laravel laravel-app

Navigate into the Laravel project directory:
	
 	cd laravel-app

Step 2: Create a Dockerfile
In the root of your Laravel application, create a Dockerfile to define the environment for Laravel:

Step 3: Create docker-compose.yml File
In the root directory of your Laravel application, create a docker-compose.yml file. This file will define the multi-container setup for PHP-FPM, MySQL, Nginx (or Apache), and phpMyAdmin.

Step 4: Create Nginx Configuration File
Create the nginx.conf file in a new nginx directory at the root of your Laravel project:

Step 5: Build and Run the Docker Containers

	docker-compose up --build

This will:

	•	Build the Laravel app using the Dockerfile.
	•	Start MySQL, Nginx, and phpMyAdmin services.

 Step 6: Access Your Application

Once the containers are running, you can access:

	•	Laravel App: Visit http://localhost:8080 in your browser.
	•	phpMyAdmin: Visit http://localhost:8081 to manage the MySQL database.
Use the following credentials to log in to phpMyAdmin:
	•	Server: db
	•	Username: root
	•	Password: rootpassword

Step 7: Run Laravel Migrations

After starting the containers, run the Laravel migrations to create the necessary database tables:

	docker-compose exec app php artisan migrate

Step 8: Stop the Containers

	docker-compose down

This will stop and remove all containers, networks, and volumes.

Summary

You’ve successfully dockerized a Laravel application using Docker Compose with the following services:

	•	PHP-FPM to run the Laravel app.
	•	Nginx as the web server.
	•	MySQL for the database.
	•	phpMyAdmin for managing the database.

This setup can easily be scaled and adapted for development and production environments. Let me know if you need any further clarification!

LinkedIn: https://www.linkedin.com/in/noman-nayyar


