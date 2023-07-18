# PulseLive Proxy

## AAC Solutions 

## Table of Contents
- [PulseLive.cloud](#project-title)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Features](#features)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Contributing](#contributing)
  - [License](#license)
  - [Acknowledgements](#acknowledgements)

## Introduction
PulseLive Proxy is an optional add on service to PulseLive which allows a venue manager to connect to their venue remotely, anywhere in the world (so long as you have an internet conneciton). 
This is all done without a VPN or changing your network settings. All of the remote access is handled by AAC Solutions' cloud server. 

## Features
1. HTTPS Secure connection
- Your venue data outside of the network is encrypted and safe from anyone listening in. 
3. User Management
- Request us to set up more users at your discretion
- Only you can access your venue 
5. Multi venue connection
- If you are a manager of multiple venues you can connect to multiple servers with our front dashboard.

## Prerequisites
- As a user you are only required to have a web browser which supports SSL2 and 3
- (Any modern browser such as a recently updated Chrome, Firefox, Safari, Brave, TOR, and Opera should work fine) 

## Installation
- All installation is carried out by AAC Solutions
- Technicians to auto deploy with docker and SSH in using their private keys in order to add configurations
- If you have a pre-existing PulseLive server dont worry, all we need to do is add a small PC on your network and create an open port to that PC only.

### Technician notes 
- Configuration DBMS managed via python configurator to SQL

## Usage
- Simply go to the address which we specify in our setup documentation and login with your one time password.
- Note that when you connect to your chosen venue site you will have to log into that site again using your credentials for that site. 

## Contributing
- Contact AAC Solutions if you wish to conrtibute to this project.
- Requrements:
- DBMS, Python, JS, LAMP, Nginx, LinuxSysadmin or Cyber Security experience 

### Software: 

**OVERVIEW**

As seen in the below diagram, the software can be described as a system which connects managers to their designated venues. 
A manager logs in, a dashboard is displayed with their related venues (internet facing nginx proxy servers) and they can connect to their venue. 
The system should be modular and scalable to allow the rapid integration of >100 clients. 

![pulselive](https://github.com/aacsolutions-anthony/pulseliveproxy/assets/131961269/259ddf28-8eb1-4edc-b062-a2decec2dd51)

As seen below is the user specific authentication, authorisation, and access to the related servers: 


![userflow](https://github.com/aacsolutions-anthony/pulseliveproxy/assets/131961269/dc274459-dea2-4cd7-a742-11785f61e380)

**0.0 SOFTWARE STACK:**

**1. FLASK**

User logic, DBMS, Installation scripting, Configuration scripting. 

![image](https://github.com/aacsolutions-anthony/pulselivecloud/assets/131961269/54f3cd9a-8db1-45f4-82c2-d1260443b128)

**2. NGINX**

Reverse proxy connections at the venues 

![image](https://github.com/aacsolutions-anthony/pulselivecloud/assets/131961269/f0ed763f-42b5-468d-8988-467910cc9f82)

**3. PULSELIVE**

Executable web server running at the venues 

![image](https://github.com/aacsolutions-anthony/pulselivecloud/assets/131961269/fa40bdca-1c5b-400b-abc6-0940dcdb056e)

**4. AKAMI / VULTR** *Sydney Locations*

Cloud service for hosting the proxy access point

![image](https://github.com/aacsolutions-anthony/pulselivecloud/assets/131961269/e7410c9a-39ad-4354-ae07-1ad43b8ddd2d)

**OTHERS:**

**5. React.JS**

SPA (Single Page Application) logic and control 
Crucial for correct control of what the user sees and controlling where the user connects to via the cloud proxy. 



## Legal Parameters 
This project is privatised and currently closed source as it is application specific. 
PulseLive and PulseLive Proxy Copyright 2023 All rights reserved 

## Warranty 

This project comes with absolutely no warranty 

## Acknowledgement and credits 

Systems Administration - Anthony Grace 
Network Architecture - Anthony Grace
Test network authority - Daniel Solah
Team management - Daniel Solah
Idea Plan - Andy Martin
Configuraitons - Matthew Chambers
Cyber Security - Anthony Grace 
Proxy testing - Matthew Chambers
Project sponsor - Daniel Solah 


