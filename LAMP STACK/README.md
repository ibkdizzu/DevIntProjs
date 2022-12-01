# LAMP WEBSTACK IMPLEMETATION IN AWS
LAMP - stands for Linux, Apache, MySQL, PHP/Python/Perl

Webstacks are a stack of technologies that make different solutions possible. In this implementation, we will be installing these technologies on a cloud server (AWS), and our P is PHP.

The aim of this excercise is a

### Tasks to be completed
1. Provision Ubuntu Server on AWS
2. Install/Configure Apache
3. Install/Configure MySQL
4. Install/Configure PHP
5. Create Virtual host for website using Apache
6. Enable PHP on created website


## Tasks Workthrough
### Provision Ubuntu Server on AWS
**Requirements**
1. AWS account. Sign up for free tier account [here](https://aws.amazon.com/) if you do not already have one
2. Ubuntu EC2 server
3. A keypair. You can use an existing one or create a new one
4. Remote connection via ssh (ubuntu), putty (windows). we'll be connecting with ssh via Vscode in this excercise but your ubuntu, wsl, windows etc will also suffice


- To start login to your AWS account, select EC2 on the navigation menu and under Instance select Launch Instances
- Fill the the installation details like Server name, select OS - we will be working with Ubuntu Server 22.04 LTS for this project

![Installation in progress](C:/Users/Home/und/PBL/0.PNG)

- Select or create a new key pair. This will later be used to establish remote access

![Select or create key pair](C:\Users\Home\und\PBL\0.zuri.PNG)

- For the purpose of this project, it will suffice to allow all other options use default values

- Click on Launch Instance to complete installation

- Voila! If all steps are followed correctly a new server just gpt provisioned. Go to EC2 dashboard to access new created server

![PBLab Server is provisioned and running](C:\Users\Home\und\PBL\1.EC2.PNG)

- One more step that can be taken here is open TCP port 80 to receive traffic. To do this go to security tab under the server, select the security group, then edit inbound rules and add http rule as show below and save

![Click on security tab](C:\Users\Home\und\PBL\1.Security.PNG)

![Add http rule](C:\Users\Home\und\PBL\3.EnableTCP.PNG)


### Install/Configure Apache
**Requirements**
- Provisioned server
- Account with sudo access

- To start, update the list of packages with the command below
`sudo apt update`

- Next, run the apache2 package installation
`sudo apt install apache2`

- After completion, verify that the apache2 service is running
`sudo systemctl status apache2 `


![Apache installed and running](C:\Users\Home\und\PBL\4.Apache.PNG)

- if all goes well without error, the result will show a running apache service - We have launced our first Web Server in the cloud!! :sunglasses:

- Now that our server is is running we can access it locally and via the internet

- Run the following commands via bash and the browser
` curl http://localhost:80` and   `curl http://127.0.0.1:80`

![access web browser from shell](C:\Users\Home\und\PBL\6.Editor.PNG)

![access web browser from browser](C:\Users\Home\und\PBL\5.Localhost.PNG)


### Install/Configure MySQL
**Requirements**
- Provisioned server
- Account with sudo access

- To start, run the command below in the terminal
`$ sudo apt install mysql-server`

- Accept the prompt to allow installation

- On completion, log in to MySQl console with the command
`sudo mysql`

![MySQL Console](C:\Users\Home\und\PBL\7.Mysql.PNG)

