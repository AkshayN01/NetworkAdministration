# NetworkAdministration
This repository contains all the ansible scripts required to run Apache server as a docker container on Linux. Apache container is installed without using a Dockerfile. Although, the project contains a Dockerfile as a secondary option which is not used currently.


### Pre-requisites:
- Ubuntu or any Linux distribution
- Git
- Ansible

### Steps to follow:
1. Git clone/download this project.
    - git clone https://github.com/AkshayN01/NetworkAdministration.git
2. Open the terminal and navigate to the project folder 'CA-1'.
3. Run the 'docker-deploy.yaml' ansible script.
    - sudo ansible-playbook docker-deploy.yaml
