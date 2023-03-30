Part-1 CI Project overview: 

In this project, we are using Docker to create a container that hosts a website and runs a web server. This simplifies deployment and improves scalability. We are using Docker, WSL2 or EC2, and web servers like Apache2 or Nginx.

Run Project Locally: 

- To install docker + dependencies for WSL2 use the following command "sudo apt install docker.oi" and also download the Docker desktop 
- To build an image from the Dockerfile first need to a Dockerfile file and a index.html file on ubuntu. After having those 2 files with all the codes that need to create a image, then run the following code to build "docker build -t long-day ."
- To run the container use the following code "docker run -d -p 80:80 long-day"

- to view or see if the container is working open the brower and type in "localhost" which is for port 80"


part-2: 

Process to create public repo in DockerHub: 
- On DockerHub, go to Repositories page 
- On the Repositories page, click "create repository"
- After click  "create repository", this is the page that you can edit for the name and description
- For visibility make it public and click on create after everything filled out

How to authenticate with DockerHub via CLI using Dockerhub credentials:
- Open up Ubuntu 
- Enter the following command " docker login -u vietnamese64" and it should ask for your password 
- If you have turned on two-factor authentication, you might need to use an authentication token instead of your password. You can create this token on the DockerHub website by going to your account settings.

How to push container image to Dockerhub (without GitHub Actions):
- Step1: open Ubuntu
- Step2: login to your docker using the following command "docker login -u vietnamese64"
- Step3: use command "docker images" to see all the available images
- Step4: pick the one image that you want to push
- Step5: tag it with the following example command "docker tag long-firstime:latest vietnamese/springcats:1.0"
- Step6: "docker images" again to see if the image that you created from tag long-firstime now available
- Step7: Now push it using the following command "docker push vietnamese64/springcats:1.0"

Configuring GitHub Secrets:
- Step1: Go to GitHub and into the cicd repo
- Step2: on the repo go to settings and under settings go to "secrets and variables"
- Step3: Click on "New repository secret" to create a new secret
- Step4: Name the 1st secret as DOCKER_USERNAME and 2nd secret as DOCKER_PASSWORD. Add your secrets in the textbox for both

Behavior of GitHub workflow:
- A GitHub workflow is a tool that can help you automate things like building, testing, and deploying code in your GitHub repository. You can create custom workflows that run when certain events happen, like when someone pushes or pulls code, and then they can do a series of tasks or jobs on different operating systems.
- The variables in workflow that someone may use and need to change is the "IMAGE_NAME: ",  Tag image to Dockerhub repo, Push Docker image to Dockerhub, and for "evn" change the DOCKER_USERNAME: and DOCKER_PASSWORD: to your right repo name on dockerhub 

