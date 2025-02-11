# VPC-Peering-Across-AWS-Regions

### Overview:
This project demonstrates the setup of VPC Peering across different AWS regions to establish communication between web servers, app servers, and a database server. The objective is to connect EC2 instances located in different VPCs and regions securely via VPC peering.

### Architecture Diagram
The architecture consists of:

* App Server (North Virginia Region)
* Web Server (North Virginia Region)
* Database Server (Ohio Region)

VPC Peering is configured to enable communication between these servers

![alt text](image.png)

## Steps to Set Up VPC Peering

### Step 1: Create Web, App, and Database Servers
Launch three EC2 instances:

*	App Server

*	Web Server

*	DB Server (Located in a different region)

![alt text](image-1.png)

![alt text](image-2.png)

![alt text](image-3.png)

![alt text](image-4.png)

### Step 2: Configure Security Groups

Navigate to AWS Console > Security > Security Groups.

Edit inbound rules for both App Server and Web Server
Add the VPC IDs of both instances to allow communication.

Allow all traffic (for testing purposes only, not recommended for production)

### Step 3: Launch and Connect EC2 Instances

* Launch Web Server and App Server
* Connect to instances using PuTTY
* Color-coded PuTTY terminals:

* Yellow → App Server
* Green → Web Server
* Red → DB Server

![alt text](image-5.png)

![alt text](image-6.png)

### Step 4: Configure Route Tables

* Set up the required route tables for App Server and Web Server
* Establish the routes to allow communication between them

![alt text](image-7.png)

![alt text](image-8.png)

Now the connection is successful as shown below. Here app server is able to ping the webserver.

![alt text](image-9.png)

Similarly web server is able to ping app-server as shown below.

![alt text](image-10.png)

In the same way to establish connection with db server which is located in ohio region from web server and app server which are located in north virginia. This is achieved using the routetables and establish suitable connections. 

![alt text](image-11.png)

![alt text](image-12.png)

The below image shows how db server is able to ping app server. 

![alt text](image-13.png)

> [!NOTE]
> Please do not forget to delete all the resourcs like VPC when done.
> ALL this can be achieved in AWS free tier account



