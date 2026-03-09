# Production-ready WordPress Deployment with Docker on AWS EC2

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Docker](https://img.shields.io/badge/Docker-Compose-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue)
![WordPress](https://img.shields.io/badge/WordPress-Latest-21759B)

## Overview

This project demonstrates a production-style deployment of a WordPress application on AWS EC2 using Docker Compose and MySQL.

The environment includes:

- AWS EC2
- Ubuntu 22.04
- Docker Engine
- Docker Compose
- WordPress container
- MySQL 8.0 container
- Public HTTP access on port 80

## Architecture

Client → Internet → AWS EC2 → Docker Compose → WordPress Container + MySQL Container

## Deployment Process

1. Launch an EC2 instance on AWS
2. Configure the Security Group to allow:
   - Port 22 (SSH)
   - Port 80 (HTTP)
3. Connect to the instance via SSH
4. Install Docker and Docker Compose
5. Create the `docker-compose.yml` file
6. Start the containers with Docker Compose
7. Validate container health and public access

## Deployment Commands


sudo systemctl stop nginx
sudo docker compose up -d
sudo docker ps
curl localhost


## Security Configuration

- EC2 Security Group configured with:
- SSH (Port 22)
- HTTP (Port 80)
- Containers isolated inside Docker networking

## Why Docker?

- Docker was used to provide:
- environment consistency
- easier deployment management
- service isolation
- faster redeployment
- portability across environments

## Manual Deployment vs Docker Compose
Manual setup

- individual service installation
- harder maintenance
- more error-prone reconfiguration

## Docker Compose

- infrastructure as code
- easier service orchestration
- faster redeployment
- cleaner and more reproducible setup

## Troubleshooting

- During deployment, I solved the following issues:
- Port 80 conflict caused by Nginx running on the host
- Docker Compose YAML syntax errors
- ontainer naming conflicts from previous test runs
- Docker daemon startup issues
- Service exposure validation using curl localhost

## Result

The WordPress application was successfully deployed and made accessible through the EC2 public IP.

- Public URL
- http://54.236.210.172
- Admin URL
- http://54.236.210.172/wp-admin

## Screenshots

- WordPress Home
- WordPress Dashboard

## About the Author

AWS-focused Cloud/DevOps beginner with hands-on experience deploying containerized applications on EC2. 
This project demonstrates:

- Docker-based application deployment
- MySQL and WordPress container orchestration
- public web exposure through EC2
- troubleshooting of real infrastructure issues

Open to remote international opportunities.
