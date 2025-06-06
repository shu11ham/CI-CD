<h1>﻿Hosting a Static Website on AWS Cloud</h1>﻿
<h2>Hosted My First Website on AWS Cloud!</h2>
<p>I'm excited to share that I’ve successfully hosted a basic HTML/CSS/JS website on AWS Cloud — and this is my first post documenting the process!</p>
<p>Here’s a step-by-step guide I followed to deploy the site on an AWS EC2 instance:</p>
<div>🔧 Steps to Host a Website on AWS EC2</div>
Create an EC2 Instance
Select your preferred OS (I used Ubuntu). Generate and download the key-pair file (.pem) for SSH access.
Launch the Instance
Once launched, connect using the terminal:
ssh -i your-key.pem ubuntu@<your-public-ip>
Update and Install Nginx
sudo apt update
sudo apt install nginx
Deploy Your HTML Files
Navigate to the web directory:
cd /usr/share/nginx/html
Check file contents using ls, then:
sudo vim index.html
Paste your basic HTML code or use wget to pull from a GitHub repo or remote source.
Check Nginx Status
sudo systemctl status nginx
If inactive:
sudo systemctl start nginx
sudo systemctl enable nginx
Test in Browser
Open your browser and enter:
http://<your-public-ip>
Fix: If Site Can’t Be Reached
This often happens due to security group settings.
Modify Security Group (Firewall)
Go to your EC2 instance > Security tab > Edit Inbound Rules.
Add a rule:
Type: HTTP (or Custom TCP)
Port Range: 80
Source: Anywhere (0.0.0.0/0, ::/0)
✅ And that’s it! Your static website is now live on the cloud.
This hands-on experience taught me a lot about EC2, server setup, Nginx, and networking rules in AWS. Looking forward to exploring more cloud-native services!
#AWS #CloudComputing #WebHosting #DevOps #EC2 #Nginx #LinkedInLearning #100DaysOfCloud #BeginnerToPro

