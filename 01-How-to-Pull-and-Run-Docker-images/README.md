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