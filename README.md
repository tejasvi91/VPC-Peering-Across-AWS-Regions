# VPC-Peering-Across-AWS-Regions

### Overview:
This project demonstrates the setup of VPC Peering across different AWS regions to establish communication between web servers, app servers, and a database server. The objective is to connect EC2 instances located in different VPCs and regions securely via VPC peering.

### Architecture Diagram
The architecture consists of:

* App Server (North Virginia Region)
* Web Server (North Virginia Region)
* Database Server (Ohio Region)

VPC Peering is configured to enable communication between these servers

![image](https://github.com/user-attachments/assets/8426fab7-5416-40e1-8718-bca3e6551b17)


## Steps to Set Up VPC Peering

### Step 1: Create Web, App, and Database Servers
Launch three EC2 instances:

*	App Server

*	Web Server

*	DB Server (Located in a different region)

![image](https://github.com/user-attachments/assets/84c99dfa-9146-4e40-99e1-c2f813925ca2)


![image](https://github.com/user-attachments/assets/ba6f347f-360e-49bc-b7a1-ee654fbd77f3)


![image](https://github.com/user-attachments/assets/a7f7216c-93a7-4a89-856a-1d64661b2efa)


![image](https://github.com/user-attachments/assets/665abd95-ca52-4b27-aa29-68f510ffd333)


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

![image](https://github.com/user-attachments/assets/4bd6abd9-b098-4fd2-9d75-44837b96a697)


![image](https://github.com/user-attachments/assets/ecb0393e-e107-4d0a-ba89-d708d4a482b5)


### Step 4: Configure Route Tables

* Set up the required route tables for App Server and Web Server
* Establish the routes to allow communication between them

![image](https://github.com/user-attachments/assets/7936e8d4-417b-4050-a635-6d71ecb84ffa)


![image](https://github.com/user-attachments/assets/5b062812-57e6-421f-b865-1acc98e3f53c)


Now the connection is successful as shown below. Here app server is able to ping the webserver.

![image](https://github.com/user-attachments/assets/203e7acf-2f94-4716-a2ae-3cb1bb99de5b)



Similarly web server is able to ping app-server as shown below.

![image](https://github.com/user-attachments/assets/b7a82ddf-b160-4780-b263-baff3b4988ef)


In the same way to establish connection with db server which is located in ohio region from web server and app server which are located in north virginia. This is achieved using the routetables and establish suitable connections. 

![image](https://github.com/user-attachments/assets/2cc5efeb-04f6-4ca1-9ecf-1b523cab8631)


![image](https://github.com/user-attachments/assets/732f0522-bfae-4f02-bf08-20a9197412b8)


The below image shows how db server is able to ping app server. 

![image](https://github.com/user-attachments/assets/90f784b0-470c-4051-ab33-68591b0ed230)


> [!NOTE]
> Please do not forget to delete all the resourcs like VPC when done.
> ALL this can be achieved in AWS free tier account

### Conclusion
This project successfully demonstrates the establishment of VPC Peering across AWS regions to connect web and database servers in different locations. The final setup allows seamless communication between all instances using proper routing and security configurations.

