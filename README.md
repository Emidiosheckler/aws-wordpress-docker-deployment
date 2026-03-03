# AWS WordPress Deployment with Docker

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

## Live   
## 🔗 Demo
Application deployed at:  
http://<IP34.227.75.202>

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

flowchart TD
    Internet((Internet))

    subgraph AWS [AWS Cloud]
        subgraph EC2 [EC2 Instance]
            subgraph Docker [Docker Network]
                WP[WordPress Container]
                DB[(MySQL Container)]
            end
        end
    end

    Internet -->|HTTP/HTTPS| EC2
    EC2 --> WP
    WP -->|Port 3306| DB
    
    style WP fill:#21759b,stroke:#fff,stroke-width:2px,color:#fff
    style DB fill:#e48e00,stroke:#fff,stroke-width:2px,color:#fff
    
  
