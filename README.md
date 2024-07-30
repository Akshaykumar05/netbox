# Netbox

In this repository, I'm summarising the steps to install and setup the Netbox tool using Docker.

## Introduction
Netbox is an open source network infrastructure management tool that allows network administrators to effectively monitor, manage and document their infrastructure. It was developed with the objective of providing a comprehensive solution for network design and maintenance.

## Installation
We'll install Netbox on Docker. So its prerequisite is Docker.

### Step-1 
* Update the existing list of packages:
```
sudo apt get update
```
![netbox 1 sudo update](https://github.com/user-attachments/assets/0035ded9-a97f-43d0-9e44-8dfe6b37d442)

### Step-2
* Install the necessary packages to allow apt to use a repository over HTTPS:
![netbox 2](https://github.com/user-attachments/assets/e39905ff-8c92-4b1a-a4f8-fed6a52ede93)

### Step-3
* Add the Docker GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
![netbox 4](https://github.com/user-attachments/assets/dc866fe3-0303-4f24-980c-4d97da920438)

### Step-4
* Add the Docker repository to APT sources:
```
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
### Step-5
* Update the package database with Docker packages from the newly added repo:
```
sudo apt update
```

### Step-6
* Ensure you are installing from the Docker repo instead of the default Ubuntu repo:
```
apt-cache policy docker-ce
```

### Step-7





