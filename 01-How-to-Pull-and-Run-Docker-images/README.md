In this guide, you will:

    1. Pull Docker images from Docker Hub.
    2. Run Docker containers using the pulled images.
    3. Start and stop Docker containers.
    4. Remove Docker images.
    5. Important Note: Docker Hub sign-in is not needed for downloading public images. In this case, the   Docker image stacksimplify/mynginx is public and does not require authentication.


# Step 1: Pull Docker Image from Docker Hub

    # List Docker images (should be empty if none are pulled yet)
    docker images

    # Pull Docker image from Docker Hub
    docker pull stacksimplify/mynginx:v1

    # Alternatively, pull from GitHub Packages (no download limits)
    docker pull ghcr.io/stacksimplify/mynginx:v1

    # List Docker images to confirm the image is pulled
    docker images

Important Notes:

    1. Docker Image Pull Limits: Docker Hub imposes pull rate limits for anonymous and free users.
    2. Alternative Registry: To avoid hitting Docker Hub pull limits, you can pull the same Docker image from GitHub Packages.
    3. Consistency: Both images are the same; choose either Docker Hub or GitHub Packages based on your needs.

# Step 2: Run the Downloaded Docker Image
   * Copy the Docker image name from Docker Hub or GitHub Packages.
   * HOST_PORT: The port number on your host machine where you want to receive traffic (e.g., 8080).
   * CONTAINER_PORT: The port number within the container that's listening for connections (e.g., 80).

    # Run Docker Container
    docker run --name <CONTAINER-NAME> -p <HOST_PORT>:<CONTAINER_PORT> -d <IMAGE_NAME>:<TAG>

    # Example using Docker Hub image:
    docker run --name myapp1 -p 8080:80 -d stacksimplify/mynginx:v1

    # Or using GitHub Packages image:
    docker run --name myapp1 -p 8080:80 -d ghcr.io/stacksimplify/mynginx:v1
