# TravelMemory MERN Stack Deployment 
## Introduction

TravelMemory is a full-stack MERN (MongoDB, Express, React, Node.js) application designed to capture and share travel memories. This documentation details the process of deploying the TravelMemory app on an AWS EC2 instance, configuring reverse proxy with NGINX, setting up load balancing, and attaching a custom domain via Cloudflare.

GitHub Repository: https://github.com/Mahi130594/Travelmemory
## Step 1: Launch EC2 Instance
1. Log in to AWS Management Console.
2. Go to EC2 Dashboard > Launch Instance.
3. Choose Ubuntu 22.04 LTS or latest version as AMI.
4. Select an instance type (t2.micro for testing).
5. Add a key pair and security group allowing:
   - TCP: 22 (SSH)
   - TCP: 80 (HTTP)
   - TCP: 443 (HTTPS, optional)
   - TCP: 3000 (backend, optional internal)

 6. Launch instance
    ![image](https://github.com/user-attachments/assets/f2a7580c-bd82-461f-94f6-965398dc73bb)

# 1. Backend Configuration
## Step 2: Install Dependencies and Backend Setup:
   
   ![image](https://github.com/user-attachments/assets/894f1d76-a357-4400-80e6-ea08bbd06f26)
   ![image](https://github.com/user-attachments/assets/f35ce82f-843b-4f3b-b914-926791c8e6ed)

 - Start backend:

   ![image](https://github.com/user-attachments/assets/633e9ffb-714b-447a-86c2-1a6f7f1e8126)

# 2. Frontend and Backend Connection
## step 3: Setup Frontend
  - Update Frontend API URL

    ![image](https://github.com/user-attachments/assets/04ad3643-a917-462c-96ec-b100cb9bb1dc)
  - Build the frontend:
    
    ![image](https://github.com/user-attachments/assets/6f7190f6-220a-4526-bb6c-809625e0bd9a)

   ## Step 4: Install and Configure NGINX
   ![image](https://github.com/user-attachments/assets/239d046b-a3a9-45a9-baf6-3999d4a7e75f)

  - Update NGINX Config:
   
   ![image](https://github.com/user-attachments/assets/9a3f6a30-f2f8-4a4a-92ab-3d4fa3cb69b8)

   - Connection Test and Restart NGINX

     ![image](https://github.com/user-attachments/assets/7ac999ff-882b-40b9-bb19-18f603ea1046)

   # 3. Scaling the Application:
   ### Create Target Groups
   - Since frontend and backend are on the same instance, but listening on different ports
   - Front-End - Protocol: HTTP, Port: 80, Health Check Path: /
   - Back-End - Port: 5000 (or your backend port), Health Check Path: /api/health
      
   ![image](https://github.com/user-attachments/assets/de817702-3c3b-4f56-811e-45509a82f84f)

   - Created Application Load Balancer with 2 availability zones

   ![image](https://github.com/user-attachments/assets/d9533de6-e407-4a20-8e49-d75356c7b9bf)
### Create Auto Scaling Group
   -  Name: Mahi-MERN-APP-ASG
   -  Attached the both target groups

![image](https://github.com/user-attachments/assets/5324ab93-548a-4a50-a66f-3b772deb2302)



   - Output:
     
     ![image](https://github.com/user-attachments/assets/2c4bf273-d1ab-4393-bd84-e34e09cf1daf)
     ![image](https://github.com/user-attachments/assets/172b057f-cc52-4f11-919c-7a440d9a9633)
     ![image](https://github.com/user-attachments/assets/df561744-1876-4d32-9d74-d6bda458e75b)

     
   ## 4. Domain Setup with Cloudflare:

   ![image](https://github.com/user-attachments/assets/905b9e6d-cb14-434d-aac0-4eadf8e5ed6d)


   ##  architecture diagram 
   ![ArchitectDiagram](https://github.com/user-attachments/assets/6028a99a-679e-40ba-bb27-5b98dd99ad9d)






