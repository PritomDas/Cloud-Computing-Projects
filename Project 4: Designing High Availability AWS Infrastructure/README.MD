<!-- PROJECT LOGO -->
<br />

<p align="center">
  <img src="./images/1.PNG" alt="Logo" width="900" height="800">
</p>


> AWS, ELB, ASG, Launch Configuration
<!-- ABOUT THE PROJECT -->

# Designing High Availability AWS Infrastructure

## Project Description
This is a medium difficulty level project. Based on the reference architecture diagram, we will design high available system. We will create AMI for our desired EC2 Instances which will be bootstrapped for starting an Apache Webserver. We will create load balancers, launch configurations and auto scaling groups. We will run 2 EC2 instances in different public subnets and it gets auto provisioned when old EC2 Instances are down.

## Follow Along:

### Part 1: Create AMI from an EC2 Instance

Head over to EC2 in services from AWS Management Console. Then "Launch Instance" :

![APT](./images/2.PNG)

We will create free tier eligible instance :

![APT](./images/3.PNG)

Keep everything default, we will provide the Bootstrap Script in the "User Data" from the "Advanced Settings" :

![APT](./images/4.PNG)

Here is the Bootstrap Script for better view:

![APT](./images/5.PNG)

In the security group we will open another rule for "HTTP" connection:

![APT](./images/6.PNG)

Now let's check if our webserver is serving the desired content properly or not. Grab the Public IPv4 address:

![APT](./images/7.PNG)

If the webserver is working correctly, then it should view this in a new browser :

![APT](./images/8.PNG)

Now, we will create an AMI from this EC2 instance that we have just deployed. Follow the picture given below to create an image:

![APT](./images/9.PNG)

Keep veryhting default and give a name to this image:

![APT](./images/10.PNG)

Now go to "Images" section and click "AMIs". Our new image should show "available" in status:

![APT](./images/11.PNG)

Now we can terminate the EC2 instance that we have created, the main purpose was to create a custom AMI which we have completed:

![APT](./images/12.PNG)


### Part 2: Creating Application Load Balancer

Go to Load Balancer, create a new load balancer and choose Application Load Balancer :

![APT](./images/13.PNG)

Give a name to the Load Balancer and choose two availability zones. Make sure these availability zones are part of public subnet and not private subnet :

![APT](./images/14.PNG)

We will create a new security group and keep the default rule :

![APT](./images/15.PNG)

After successfully creating the load balancer:

![APT](./images/16.PNG)



### Delete the RDS Instance
Don't forget to delete all the RDS Instance as one can be billed after the free tier quota is over.

<!-- CONTACT -->

## Contact

Pritom Das Radheshyam - [Portfolio Website](https://pritom.uwu.ai/)
[![LinkedIn][linkedin-shield]][linkedin-url]  





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/you-found-pritom
[product-screenshot]: images/screenshot.jpg

