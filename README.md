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

## Setting Up Jenkins with Docker

## Pull the Jenkins Image from Docker Hub

```bash
docker pull jenkins/jenkins
docker run -p 8080:8080 -d 441f36761835
docker logs -f 441f36761835

Copy the generated password from the logs.

Access Jenkins Web Interface
Visit http://35.154.152.42:8080/ in your web browser.

Paste the copied password to unlock Jenkins.
Continue with the basic Jenkins setup, creating a user and configuring the instance.
Jenkins is now ready!
```

## Configure Jenkins with GitHub
Follow these steps to configure Jenkins to work with GitHub:

### Go to Jenkins Configuration:

1. Open Jenkins in your web browser.

2. Navigate to "Manage Jenkins" > "Configure System."

## Add GitHub Server:

3. Scroll down to the "GitHub" section.

4. Click on "Add GitHub Server."

5. Enter the following details:
   - **Name:** (Provide a name for the GitHub server configuration.)
   - **API Token:** (Enter the GitHub API token. This is typically a personal access token generated from your GitHub account.)

6. Click "Add" and then "Save."

Now, Jenkins is configured to work seamlessly with GitHub. This integration allows Jenkins to interact with your GitHub repositories, triggering builds and providing continuous integration and continuous delivery (CI/CD) capabilities.

**Note:** Ensure you replace the placeholder token (`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`) with the actual GitHub API token that you've generated from your GitHub account.

Feel free to explore additional Jenkins and GitHub integration features based on your project requirements.

---

### Additional Notes:

- Always keep your GitHub API token secure and avoid sharing it in public repositories or insecure locations.

- Jenkins provides various plugins for GitHub integration, offering features like webhooks, pull request building, and more. Explore the Jenkins plugin ecosystem for additional functionalities.

- Refer to the Jenkins and GitHub documentation for more detailed configurations and best practices.

