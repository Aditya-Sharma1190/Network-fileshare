<h2>Network File Shares and Permissions</h2>

Network File Share >> A folder on a computer that is shared over the network

Practical uses <br />
Individual departments can have their own folders shared on the Company Intranet <br />
Training material can be shared to a large number of employees<br />

<h2>Steps</h2>

Connect to DC VM using RDP<br />
username : mydomain.com\adiadmin<br />
password : Cyberuser1234<br />

Connect to Client VM using RDP<br />
username - mydomain.com\bax.divu<br />
password - Password1<br />

In DC VM , create 4 folders on C Drive<br />
<b>Accounting</b> <br />
Properties >> Sharing >> Share >> Domain Users >> Add <br />

![image](https://github.com/user-attachments/assets/95f65dab-5809-430b-97d4-cf86840156f1)


<b>IT</b> <br />
Properties >> Sharing >> Share >> Domain Users >> Add <br />

![image](https://github.com/user-attachments/assets/441b5421-a8ac-4688-81a9-b8c5ad582b0b)


<b>Management</b> <br />
Properties >> Sharing >> Share >> Domain Admins >> Add <br />

![image](https://github.com/user-attachments/assets/e3d4a15a-a0ea-4b26-a2a4-a3984c2ee074)

<b>Admins</b> <br />

Skip for now 

![image](https://github.com/user-attachments/assets/8a45ba31-41ad-41f4-93c3-234abc1b5abe)

From Clinet VM as User : bax.divu <br />
In run >> \\dc<br />

You will notice that you have access to Accounting and IT folder , but you don't have permission to write anything in these folders .<br />

![image](https://github.com/user-attachments/assets/3b271382-e9b6-47b4-ba81-43b04070e75d)

You will notice that you don't see Admins folder , as it is not shared yet on the network <br />

You will notice you don't have access to Management folder<br />

![image](https://github.com/user-attachments/assets/5b1b2904-2a25-4540-ac0b-1e1fba73927d)

From DC VM , we can give User : bax.divu permission to read/write in the Accounting folder
![image](https://github.com/user-attachments/assets/ba4ad9c7-0a50-4998-b090-afcfe4445d85)

From Client VM as User : bax.divu , we can now create a new folder in Accounting folder 

![image](https://github.com/user-attachments/assets/a9b3a9e9-bd15-40b8-8304-e2ad20a013a9)

From DC VM , we can give User : bax.divu permission to read/write in the Management folder by adding  User : bax.divu to Domain Admins security group

![image](https://github.com/user-attachments/assets/7f857d9d-9d60-4127-a57c-c5fe96c39014)

![image](https://github.com/user-attachments/assets/e87ce16a-ee0f-4189-96e6-4eefde782c55)

![image](https://github.com/user-attachments/assets/eaaca40b-d68f-4c46-a260-7ea2d6edfeb2)


From Client VM as User : bax.divu , we can now have access and create a new folder in Management folder after logging out and log back in as User : bax.divu to enforce the changes 

![image](https://github.com/user-attachments/assets/d3164d98-4f6c-4f2b-b6d2-89cdbde5e364)












