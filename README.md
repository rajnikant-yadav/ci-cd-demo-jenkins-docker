# CI/CD Demo with Jenkins and Docker

This repository contains a simple Django project intended for CI/CD demonstration using Jenkins and Docker.

## Getting Started

Follow the steps below to set up and run the project locally:

1. Clone the repository:

    ```bash
    git clone https://github.com/rajnikant-yadav/ci-cd-demo-jenkins-docker.git
    ```

2. Update package information and install Python3-pip:

    ```bash
    sudo apt update
    sudo apt install python3-pip
    ```

3. Check the installed pip version:

    ```bash
    pip3 --version
    ```

4. Install Django:

    ```bash
    sudo pip3 install django
    ```

5. Navigate to the project directory:

    ```bash
    cd ci-cd-demo-jenkins-docker
    ```

6. Apply database migrations:

    ```bash
    python3 manage.py migrate
    ```

7. Run the Django development server:

    ```bash
    python3 manage.py runserver 0.0.0.0:8000
    ```

## Docker Instructions

### Build Docker Image

Build the Docker image in the project directory:

```bash
sudo docker build . -t ci_cd_demo_jenkins_docker
```

### Run Docker Container
Run the Docker container, mapping port 8000:
```bash
docker run -p 8000:8000 -d ci_cd_demo_jenkins_docker
```

### View Container Logs
View the logs of the running container:

```bash
docker logs -f <container_id>
```
### Docker Hub
Log in to Docker Hub
```
docker login
```
### Tag and Push Docker Image
```bash
docker tag ci_cd_demo_jenkins_docker your-username/my-image
docker push your-username/my-image
```

### Pull Docker Image
```bash
docker pull your-username/my-image
```
### Cleanup
Remove local Docker images and containers:
```bash
docker rmi ci_cd_demo_jenkins_docker
docker rm <container_id>
```