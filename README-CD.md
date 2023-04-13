part1: 

CD Project Overview:
 - For part 1, I will use semantic versioning to create a tag for my commit. Then,I will update my GitHub Action workflow to automatically generate Docker image tags based on my tag version and push them to DockerHub. The purpose of this is to process of building and pushing Docker images when a new tag is pushed to the repository. The tools like GitHub Actions, DockerHub, and the “docker/metadata-action” to accomplish this.

How to generate a tag in git / GitHub:
 - Open up Ubuntu
 - cd to the working directory "/3120-cicd-vietnamese64/.github/workflows"
 - "git commit -a -m "21"" to commit all the modified files in the current working directory
 - "git tag -a v1.10.0" to creates a new tag in git
 - "git push origin v1.10.0" to push the Git tag with the name "v1.10.0" to the remote reposity 	"origin"
 - Lastly, "git push" to push all changes from local branch to remote branch

Behavior of GitHub workflow:
 - GitHub Workflow automates software development tasks triggered by events like code pushes or pull request merges. I can create steps in a YAML file, and GitHub Workflow will execute it automatically. It can perform tasks like building and testing code, deploying applications. This helps make software development faster, more efficient, and less prone to errors.

-https://hub.docker.com/repository/docker/vietnamese64/springcat/general

Part2: 

To install Docker on your instance:
 - Open up Ubuntu and connect to the instance SSH
 - Update the package list by running the command: $ sudo apt-get update
 - Install Docker by running the command: $ sudo apt-get install docker.io

Container restart script:
 - $ sudo docker stop container: This command stops a running container 
 - $ sudo docker rm khacontainer: This command removes the stopped container 
 - $ sudo docker pull vietnamese64/springcat:latest: This command pulls the latest image from the DockerHub repository 
 - $ sudo docker run -d --name container -p 88:80 vietnamese64/springcat:latest: This command runs a container on port 88 and names it container using the image that was pulled in the previous step.
 - The script is named deploy.sh and needs to have its permission changed to be executable.
  The script can be saved in either the main directory or the default directory when connecting to the instance.
  After saving the script, you can try it out by running the command "./deploy.sh". This will execute the script, allowing   you to see the outcome by accessing the container.
