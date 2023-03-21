CI Project overview: 

In this project, we are using Docker to create a container that hosts a website and runs a web server. This simplifies deployment and improves scalability. We are using Docker, WSL2 or EC2, and web servers like Apache2 or Nginx.

Run Project Locally: 

- To install docker + dependencies for WSL2 use the following command "sudo apt install docker.oi" and also download the Docker desktop 
- To build an image from the Dockerfile first need to a Dockerfile file and a index.html file on ubuntu. After having those 2 files with all the codes that need to create a image, then run the following code to build "docker build -t long-day ."
- To run the container use the following code "docker run -d -p 80:80 long-day"

- to view or see if the container is working open the brower and type in "localhost" which is for port 80"
