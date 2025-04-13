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
## Step 2: Install Dependencies and Backend Setup:
   
   ![image](https://github.com/user-attachments/assets/894f1d76-a357-4400-80e6-ea08bbd06f26)
   ![image](https://github.com/user-attachments/assets/f35ce82f-843b-4f3b-b914-926791c8e6ed)

 - Start backend:

   ![image](https://github.com/user-attachments/assets/633e9ffb-714b-447a-86c2-1a6f7f1e8126)

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


