# How to Create and Push Docker Images to Docker Hub: A Step-by-Step Guide

In this guide, you will:

    1. Create a Docker Hub account.
    2. Sign in with your Docker ID in Docker Desktop.
    3. Log in to Docker Hub using the Docker CLI.
    4. Run a base Nginx Docker image.
    5. Create a custom Dockerfile and index.html.
    6. Build a Docker image from the Dockerfile.
    7. Tag and push the Docker image to Docker Hub.
    8. Search and explore Docker images on Docker Hub.

# Step 1: Create Docker Hub Account
   * Visit [Docker Hub](https://hub.docker.com/) and sign up for a new account.

# Step 2: Sign In to Docker Desktop
   * Open Docker Desktop.
   * Click on Sign In and log in with your Docker ID.

# Step 3: Verify Docker Version and Log In via Command Line

    # Check Docker version
    docker version

    # Log in to Docker Hub
    docker login

    # To Logout from Docker Hub
    docker logout

# Step 4: Run the Base Nginx Container

    # Run the default Nginx Docker Image
    docker run --name <CONTAINER-NAME> -p <HOST_PORT>:<CONTAINER_PORT> -d <IMAGE_NAME>:<TAG>

    # Example:
    docker run --name myapp1 -p 8090:80 -d nginx

    # List running Docker containers
    docker ps

    # Access the application in your browser
    http://localhost:8090

    # Stop and remove the Docker container
    docker stop myapp1
    docker rm myapp1

    # Or force remove the container
    docker rm -f myapp1

# Step 5: Create Dockerfile and Customized index.html
   * Directory: Dockerfiles

Create a Dockerfile:
    
    FROM nginx
    COPY index.html /usr/share/nginx/html

Create a simple index.html:

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StackSimplify</title>
    <style>
        body { 
            font-family: Arial, sans-serif; 
            text-align: center; 
            padding: 50px; 
            background-color: rgb(197, 144, 144);
        }
        h1 { font-size: 50px; }
        h2 { font-size: 40px; }
        h3 { font-size: 30px; }
        p { font-size: 20px; }
    </style>
    </head>
    <body>
    <h1>Welcome to My Website</h1>
    <h2>Docker Image BUILD, RUN, TAG and PUSH to Docker Hub</h2>
    <p>Learn technology through practical, real-world demos.</p>
    <p>Application Version: v1</p>
    </body>
    </html>

# Step 6: Build Docker Image and Run It

    # Change to the directory containing your Dockerfile
    cd Dockerfiles

    # Build the Docker image
    docker build -t <IMAGE_NAME>:<TAG> .

    # Example:
    docker build -t mynginx-custom:v1 .

    # List Docker images
    docker images

    # Run the Docker container and verify
    docker run --name <CONTAINER-NAME> -p <HOST_PORT>:<CONTAINER_PORT> -d <IMAGE_NAME>:<TAG>

    # Example:
    docker run --name mynginx1 -p 8090:80 -d mynginx-custom:v1

    # Access the application in your browser
    http://localhost:8090





