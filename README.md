# AWS WordPress Deployment with Docker
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Docker](https://img.shields.io/badge/Docker-Container-blue)
![WordPress](https://img.shields.io/badge/WordPress-Deployment-21759B)

## Overview
This project demonstrates the deployment of a WordPress application using Docker containers on an AWS EC2 instance running Ubuntu 22.04.

## Architecture
Client → Internet → AWS EC2 → Docker Network → WordPress Container → MySQL Container

## Technologies Used
- AWS EC2
- Ubuntu 22.04
- Docker
- MySQL 5.7
- WordPress Latest

## 🛠 Deployment Step by Step

1. Launch an AWS EC2 Ubuntu 22.04 instance  
2. Install Docker on the instance  
3. Create Docker network
4. Deployed MySQL container
5. Deployed WordPress container
6. Configured port 80 access

## Deployment Commands Used

```bash
sudo docker network create wp_network

sudo docker run -d --name wp_db --network wp_network \
  -e MYSQL_DATABASE=wordpress \
  -e MYSQL_USER=wp_user \
  -e MYSQL_PASSWORD=wp_password \
  -e MYSQL_ROOT_PASSWORD=root_password \
  mysql:5.7

sudo docker run -d --name wp_app --network wp_network \
  -p 80:80 \
  -e WORDPRESS_DB_HOST=wp_db:3306 \
  -e WORDPRESS_DB_USER=wp_user \
  -e WORDPRESS_DB_PASSWORD=wp_password \
  -e WORDPRESS_DB_NAME=wordpress \
  wordpress

## Live   
## 🔗 Demo
Application deployed at:  
http://IP34.227.75.202

## Security Configuration
- Configured Security Group to allow HTTP (Port 80)
- Isolated containers using Docker network

## Why Docker? 

Docker was used to ensure application portability, environment consistency,
and easier deployment management.

## Challenges Faced

- Port conflict on port 80
- Docker container naming issues
- Network connectivity troubleshooting

## Lessons Learned
- How to manage port conflicts
- How to connect containers using Docker networks
- Basic troubleshooting in cloud environments

## About the Author

Cloud enthusiast focused on AWS and Docker deployments.
This project demonstrates hands-on experience deploying containerized applications on AWS EC2.


    
    
  
