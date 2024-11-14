
# Deploying 2048 Game in Kubernetes Cluster with CI/CD Pipeline
## Description
This project demonstrates the deployment of the 2048 game as a containerized application within a Kubernetes cluster. Entire deployment is automated with Jenkins CI/CD pipeline. In this project tools like GitHub, Jenkins, Ansible, Docker and Kubernetes are used. 
## Project Architecture
1. Docker : For building the image and pushing the image to the DockerHub.
2. Ansible : Manages configuration and deployment of Kubernetes resources.
3. Jenkins : Automates build and deployment processes.
4. Kubernetes : For hosting the 2048 application.

## Software Installation

### 1. Docker Installation

```bash
sudo apt update
sudo apt install docker.io -y 
```
After installation use this command for adding the user in to docker group.
```bash
sudo usermod -aG docker $USER
```
Check the status of the docker service.
```bash
sudo systemctl status docker  
```

### 2. Ansible Installation
```bash
sudo apt update
sudo apt install ansible2 -y
```
Create the inventory and ansible.cfg file in the location.
```bash
sudo touch /etc/ansible/hosts
sudo touch /etc/ansible/ansible.cfg
```
 ### 3. Jenkins Installation
```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
Start the jenkins and Check the status.
```bash
sudo systemctl start jenkins 
sudo systemctl status jenkins
```

Plugins to install in Jenkins.
```
1. Docker
2. Ansible
3. Stageview
```

### 4. Kubernetes Installation
Install Kubernetes for the file "kubernetes_installation.txt".
