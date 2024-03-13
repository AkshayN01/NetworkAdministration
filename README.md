# NetworkAdministration
This repository contains all the ansible scripts required to run Apache server as a docker container on Linux. Apache container is installed without using a Dockerfile. Although, the project contains a Dockerfile as a secondary option which is not used currently.


### Pre-requisites:
- Ubuntu or any Linux distribution
- Ansible

### Steps to follow:
1. Git clone/download this project.
2. Open terminal and navigate to the project folder 'CA-1'.
3. Run the 'deploy-apache.yaml' ansible script.
    - ansible-playbook deploy-apache.yaml

### Deploy-Apache.YAML Description:
- The deploy-apache.yaml script checks if docker is installed in the system by using the following command:
    - docker --version
- The value of this command is stored in a custom variable 'docker_valid'.
- Docker will be installed based on the value of 'docker_valid.failed' which returns a boolean value.
- The scripts to install docker is mentioned inside the 'docker-install.yaml' ansible script.
- The main command to run the apache container is:
    - sudo docker run -d --name my-apache-server -p 80:80 -v ./website/:/usr/local/apache2/htdocs/ httpd:2.4
        - '-d' runs the container in a detached mode as a background process.
        - '-p 80:80' maps the port 80 of the host to port 80 of the container. This will make all the public requests made on port 80 to be redirected to the port 80 of the container.
            - This is done by mapping './website/' to '/usr/local/apache2/htdocs/'. The './website' folder acts a root folder here.
            
