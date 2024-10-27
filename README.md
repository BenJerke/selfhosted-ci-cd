# Self-Hosted Local CI/CD via Docker Compose

## Setup Instructions
0. Install Docker.  
1. Open up a terminal and run `docker-compose up` in the project root. 
2. Set up the Gitea server: 
    - Head to `localhost:300` and create an admin user. 
3. Set up the Jenkins server: 
    - Head to `localhost:8066` 
    - Check the docker daemon logs in your terminal to find the initial Jenkins admin password. 
    - Use this password to create your admin user and unlock the server for usage.
4. Do Stuff
    - Use the Gitea container as an upstream for your projects. 
    - Set up pipelines on the Jenkins server that point to your Gitea repos. 
    - When defining branch sources on the Jenkins container, use the Gitea container's service name + internal port (e.g. 'http://gitea:3000/repo') This is somewhat annoying as it doesn't match the clone URL, but it works. 
    
This can run on your local Docker installation, and you can run it on a remote host without too much effort. The services will be exposed to hosts on the Docker host's network.


## Using the Services
Gitea documentation can be found here: https://docs.gitea.com/
Jenkins documentation can be found here: https://www.jenkins.io/doc/
Here's a cool repo with example Jenkins files: https://github.com/jenkinsci/pipeline-examples/tree/master

