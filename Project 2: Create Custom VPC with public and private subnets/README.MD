<!-- PROJECT LOGO -->
<br />

<p align="center">
  <img src="./images/16.PNG" alt="Logo" width="700" height="700">
</p>


> AWS, VPC, Custom VPC, Public Subnet, Private Subnet

<!-- ABOUT THE PROJECT -->

# Create Custom VPC with public and private subnet

## Project Description

In this project I have created a custom VPC in AWS. The reference architecture diagram is provided as the project logo. I have created two subnets where one is a public subnet and the other is a private subnet. The public subnet could simulate as Web Server which is the Application Tier. For maintaining security concerns, the private subnet could simulate as Database Server which is the Database Tier.

## Follow Along:

#### Create VPC in the AWS Management Console
Head over to AWS VPC Services and then create a new VPC
![APT](./images/1.PNG)

Install Apache Web Server in the EC2 instance:

![APT](./images/2.PNG)

Print the instance id as the index.html page for the Apache web server

![APT](./images/3.PNG)

Start the Apache Web Server

![APT](./images/4.PNG)

Copy the Public IPv4 address and view it in browser

![APT](./images/5.PNG)

The Final Output for Part 1:

![APT](./images/6.PNG)


### Part 2: Bootstrap

Create another free tier eligible EC2 instance and in the "User Data" write like the following:

![APT](./images/7.PNG)

The Final Output for Part 2:

![APT](./images/8.PNG)
<!-- CONTACT -->

## Contact

Pritom Das Radheshyam - [Portfolio Website](https://pritom.uwu.ai/)
[![LinkedIn][linkedin-shield]][linkedin-url]  





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/you-found-pritom
[product-screenshot]: images/screenshot.jpg

