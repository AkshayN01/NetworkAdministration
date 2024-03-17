# NetworkAdministration
This repository contains all the ansible scripts required to deploy Apache server as a docker container on Linux. Apache container is installed using ansible docker modules. Although, the project contains a Dockerfile as a secondary option which is not used currently.


### Pre-requisites:
- Ubuntu or any Linux distribution
- Git
- Ansible
- SSH connnection between client and host

### SSH connection between Client and Host
#### Client:
- Generate public and private keys
    - ssh-keygen -t rsa
- Configure ssh to use the key
    - nano ~/.ssh/config
    - copy and edit the below contents into the config:
        Host {serverName}
		Hostname {server ip address}
		User {username}
		PubKeyAuthentication yes
		IdentityFile {key location}
- Copy the public key of the Client:
    - cat ~/.ssh/id_rsa.pub

#### Server:
- Paste the public key of the Client into authorized keys file:
    - nano ~/.ssh/authorized_keys

### Steps to follow to install Apache container on Server:
#### Client:
1. Install Ansible in the machine from where you will be running the playbook:
    - sudo apt install ansible
2. Git clone/download this project.
    - git clone https://github.com/AkshayN01/NetworkAdministration.git
3. Open the terminal and navigate to the project folder 'CA-1'.
4. Add Server ip to the inventory file
    - replace the value of 'ansible_host' with the ip-address of the HOST machine.
    - replace the value of 'ansible_ssh_user' with the username of the HOST machine.
5. Run the 'docker-deploy.yaml' ansible script.
    - ansible-playbook -i inventory docker-deploy.yaml
