# Netbox
![image](https://github.com/user-attachments/assets/3c94d408-2ffa-485c-a81f-d139b3a75ece)

In this repository, I'm documenting about **Netbox** tool and the steps to installation and setup using Docker.

## Introduction
Netbox is an open source network infrastructure management tool that allows network administrators to effectively monitor, manage and document their infrastructure. It was developed with the objective of providing a comprehensive solution for network design and maintenance.

## Key Features of NetBox:
1. **IP Address Management (IPAM)**: NetBox provides a centralized platform for IP address management, allowing organizations to efficiently allocate and monitor both IPv4 and IPv6 addresses, subnets, and VLANs.
   
2. **Device Inventory**: It enables detailed documentation of network devices, including their models, serial numbers, and specifications. This feature helps organizations maintain an up-to-date inventory of hardware assets.

3. **Cabling Management**: With NetBox, you can document physical and logical network connections, visualize inter-device links, and ensure accurate cabling documentation for troubleshooting and planning.
   
4. Rack Layouts: Organizations can create visual representations of racks and data center layouts, helping them track the physical location and mounting details of devices.
  
5. **Power Management**: NetBox allows for the management of power connections within racks, facilitating power usage monitoring and dependency tracking.
   
6. **Circuit Management**: It helps in the documentation of network circuits, including details about providers and link specifications.

7. **Custom Data**: NetBox’s high level of customization permits organizations to define custom fields and data types for storing specific information tailored to their network needs.

## Benefits to Organizations:

1. **Enhanced Documentation**: Accurate and up-to-date documentation reduces troubleshooting time, increases network reliability, and aids in compliance with industry standards.
   
2. **Efficient Resource Management**: Organizations can optimize resource allocation, such as IP address space and rack space, leading to cost savings and improved scalability.
   
3. **Improved Collaboration**: Centralized documentation fosters collaboration among IT teams, as everyone can access a single source of truth.
   
4. **Streamlined Capacity Planning**: NetBox’s comprehensive data helps organizations plan for future network expansion more effectively.

## Leveraging Automation for NetBox:
1. **Scripting and API Integration**: NetBox provides a RESTful API, enabling automation through scripts and integrations with other tools. You can use scripting languages like Python to automate tasks such as IP address allocation and device provisioning.
   
2. **Configuration Management**: Tools like Ansible or Puppet can be used to automate device configuration deployment based on the data stored in NetBox.
   
3. **Monitoring and Alerts**: Integrate NetBox with monitoring solutions like Grafana or Nagios to receive real-time alerts about changes or issues in the network.
   
4. **Scheduled Tasks**: Automate routine tasks, such as data backups or updates, by scheduling them through cron jobs or task schedulers.
   
--------------------------
## Installation
We'll install Netbox on Docker. So its prerequisite is Docker.

### Step-1 
* Update the existing list of packages:
```
sudo apt-get update
```
![netbox 1 sudo update](https://github.com/user-attachments/assets/0035ded9-a97f-43d0-9e44-8dfe6b37d442)

### Step-2
* Install the necessary packages to allow apt to use a repository over HTTPS:
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
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
![netbox 5](https://github.com/user-attachments/assets/5c8c837f-6e19-4fb2-a18a-f8b85273f1f1)

### Step-7
* Install Docker:
```
sudo apt install docker-ce
```
![netbox 7](https://github.com/user-attachments/assets/3bd15e13-fd4a-4140-a0ce-71f66d286828)


### Step-8
* Start and enable Docker:
```
sudo systemctl start docker
sudo systemctl enable docker
```
![netbox 8](https://github.com/user-attachments/assets/27df305e-0b50-44ab-84f1-59ea1d18b474)

* Check your docker version
```
docker --version
```
<img width="497" alt="image" src="https://github.com/user-attachments/assets/7e863d4a-bf00-4ee8-a575-dde6553152e9">



### Step-9
* Now install netbox
```
git clone https://github.com/netbox-community/netbox-docker
```
![image](https://github.com/user-attachments/assets/03650ced-adb0-4f6d-bc39-74c9b2d1e58c)

### Step-10
* Next, create a docker-compose.override.yml file. This step allows you to customize the Docker Compose setup without altering the original docker-compose.yml file. You might use a text editor like vim (or any editor you're comfortable with) to create and edit this file.
```
vim docker-compose.override.yml
```
![image](https://github.com/user-attachments/assets/db4510a2-4261-4188-a3f9-125874aa7951)

### Step-11
* Now hit the local IP ```127.0.0.1:8000``` adress on the web portal. You'll see the Netbx.
  <img width="925" alt="image" src="https://github.com/user-attachments/assets/5bb302a8-78c3-4059-a385-ba82b72a8f5f">







