<!-- PROJECT LOGO -->
<br />

<p align="center">
  <img src="./images/RDS.png" alt="Logo" width="600" height="600">
</p>


> AWS, RDS, MySQL, MySQL Workbench
<!-- ABOUT THE PROJECT -->

# Connecting AWS RDS with local SQL Client

## Project Description
This is a very simple project where we will work with AWS RDS. We will create a free tier eligible MySQL RDS Database Instance. We will then install a local SQL client in our local environment. We will connect the the local SQL client with the AWS RDS Database instance that we have just created. After successful creation, we will delete all the created resources.

## Follow Along:

### Part 1
Create any Free Tier eligible EC2 instance. Use "Putty" and "PuttyGen" to convert the key-pair pem file to a ppk file. After successfully login to the EC2 instance from putty, it should like something like this:
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

