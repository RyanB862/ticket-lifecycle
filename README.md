<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# Ticket-Lifecycle-Intake-Through-Resolution
In this lab, I worked through the complete incident management lifecycle using osTicket. I created and managed tickets, assigned priorities and SLAs, routed incidents to appropriate departments, observed role-based access controls, escalated critical issues, communicated through ticket updates, and resolved tickets from creation through closure, simulating real-world helpdesk operations.
This outlines the lifecycle of a ticket from intake to resolution within the open-source help desk ticketing system osTicket.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Ticket Lifecycle Stages</h2>

- Intake
- Assignment and Communication
- Working the Issue
- Resolution



</p>
<p>An Azure region is the location of the datacenter where my VM runs. 
Here I set up the VM in Azure. I added it to a resource group and gave the VM a name. I also used US East 2 region. Choosing the right region helps with speed, cost, and keeping services available if a problem happens.
</p>
<br />
<p>

<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/f2f2178f-57ea-4fc9-9cd3-a178430c5546" />
Here is where I gave the VM a username and password. These are very important as they allow me to successfully login to the VM using port 3389 RDP (Remote Desktop Protocol). Remote Desktop Protocol is important because it allows the helpdesk to remotely access an endpoint without being in person.


<img width="1920" height="1032" alt="Screenshot 2026-06-01 151909" src="https://github.com/user-attachments/assets/2d55fe10-f9d0-424f-86c7-ff83d78ce0c6" />
Here I select the operation system (os) disk size and image. The disk image is important in Azure VM deployment because it acts as the template (operating system + setup) used to quickly create a new virtual machine. A standard HDD is important because it provides a low-cost storage option for the VM’s disk when high performance isn’t required. I then select to delete when VM is deleted. This is to help avoid extra storage charges and 
keeps the environment clean. I delete the disk with the VM so I don’t pay for something I'm no longer using.


<img width="1920" height="1032" alt="Screenshot 2026-06-01 151930" src="https://github.com/user-attachments/assets/18310723-385c-4637-b955-c76831f528ec" />
Here I select the VNet and subnet so the VM can communicate on the network, assign a public IP for remote access, and choose to delete the public IP and NIC with the VM to avoid leaving unused resources and extra costs. Virtual Network (VNet) is the VM's network. It allows the VM to communicate with other Azure resources and systems, similar to how a home Wi-Fi network connects devices.
Subnet: This is a smaller section inside the VNet that helps organize and control traffic between resources.
Public IP Address: This gives the VM an address that can be reached from the internet, allowing remote access such as RDP port 3389.
Delete Public IP and NIC when VM is deleted: The NIC (Network Interface Card) is the VM's network adapter. Selecting these options ensures that when the VM is deleted, its public IP and network adapter are also removed, preventing unused resources from remaining in Azure and generating unnecessary costs.


<img width="1920" height="1032" alt="Screenshot 2026-06-01 152136" src="https://github.com/user-attachments/assets/b6782bba-1995-4e4f-ab3c-d25979f8f698" />
The Review + Create step is important because it lets me verify all VM settings before deployment, helping prevent configuration mistakes that could affect performance, security, or cost. It also shows the estimated pricing so I can confirm the VM meets the project's requirements and budget before creating it.


<h2>Connecting to Windows VM:</h2> 
<img width="403" height="239" alt="RDP" src="https://github.com/user-attachments/assets/9e983087-37bc-44f0-968c-553baa04b0c4" />

This makes accessing a computer easy by using remote desktop protocol (RDP) port 3389. 
To gain access the public IP address is used along with the VM Admin username and password. 

<h2>Lifecycle Stages</h2>

<p>
<img width="850" height="407" alt="image" src="https://github.com/user-attachments/assets/ef272aee-24ae-4355-bee2-0ead7844e901" />
 
  I start by logging into osticket with admin username and password.
<img width="883" height="322" alt="Screenshot 2026-06-04 200856" src="https://github.com/user-attachments/assets/f9069129-6162-4349-8eec-dffe9ca70753" />
<img width="877" height="327" alt="Screenshot 2026-06-04 201613" src="https://github.com/user-attachments/assets/89ad3cdb-8b10-4fd0-b854-0f8bf7f2c20a" />

Once inside I click admin portal then I click the agents tab then departments

<img width="835" height="305" alt="image" src="https://github.com/user-attachments/assets/b9d0f467-ef7b-40b8-8397-c6dbc9ee6512" />

I then click maintn=enance and then click delete. Deleting the Maintenance Department reduces unnecessary departments, making ticket assignment and escalation easier to manage. This helps demonstrate how tickets move between active departments Support and SysAdmins. Removing unused departments keeps the ticketing environment organized and reduces routing confusion.

<img width="731" height="428" alt="image" src="https://github.com/user-attachments/assets/ed642960-7e18-4bc6-8f7b-d4b5abc50256" />

I then open a new browser http://localhost/osTicket. I then click open new ticket tab in blue

<img width="683" height="828" alt="image" src="https://github.com/user-attachments/assets/709fe4d3-c6c4-432c-8362-965405a92cec" />
<img width="735" height="421" alt="image" src="https://github.com/user-attachments/assets/9868b120-b01b-40e5-9af1-b6b23516d978" />

Inside the new ticket Karen's email and help topic along with the issue summary and description is provided. 
Then I click create ticket in red at the bottom. Then an auto response is created to show the helpdesk is actively accepting the issue. 

<img width="366" height="253" alt="image" src="https://github.com/user-attachments/assets/a73bc885-0d31-4658-8498-184d56560647" />
<img width="838" height="319" alt="image" src="https://github.com/user-attachments/assets/0a152755-11c0-4f17-888d-037685d39768" />

I then login as John (helpdesk) to work Karen's ticket. I then click on Karen's ticket.

<img width="829" height="695" alt="image" src="https://github.com/user-attachments/assets/5c28d46d-b728-4a8c-ba05-a3df578140df" />

John is only is able to make notes due to his "Read Only" permission. Once the note is taken John logs out.
This demonstrates how department-based permissions restrict access and protect ticket ownership.

<img width="840" height="333" alt="image" src="https://github.com/user-attachments/assets/e5e3db7d-47b8-4547-9f9d-5d531f1d4f08" />
<img width="841" height="364" alt="image" src="https://github.com/user-attachments/assets/6bad8945-488a-4610-9074-3370b46653e0" />
<img width="842" height="489" alt="image" src="https://github.com/user-attachments/assets/efa7b429-370d-4930-bb72-0693f52a6c8e" />

I log in with Admin username and password then click admin panel. 
I then click John Doe. 

Then I click Agents then access. I then grant John "full access".  
This allows John full permission to work the ticket. Then click save changes then log out.
These properties determine how quickly the issue is handled and who is responsible for resolution.

<img width="826" height="441" alt="image" src="https://github.com/user-attachments/assets/8f933c51-eaa6-4a6d-91b5-7bf25f57b035" />
<img width="824" height="480" alt="image" src="https://github.com/user-attachments/assets/21b133c6-2d82-4beb-b48d-e39aa0e19b77" />
<img width="825" height="427" alt="image" src="https://github.com/user-attachments/assets/bb61af90-7edd-496b-84be-d7c4cba7e270" />

John now logs back in and clicks "Priority Level". With new permissions granted John is able to update the ticket's priority level and SLA plan.
John then changes ticket priority level to "emergency" and SLA plan to Sev-A business critical then clicks update.
A Severity A SLA ensures immediate response for business-critical outages requiring urgent attention.

<img width="765" height="621" alt="image" src="https://github.com/user-attachments/assets/ffd3e8a9-a0bd-4c84-89fb-0ace02457707" />
<img width="820" height="568" alt="image" src="https://github.com/user-attachments/assets/dd615df7-7065-47b0-98ed-46ac0122a58b" />

John then updates ticket by triaging ticket to Sysadmin.

<img width="784" height="331" alt="image" src="https://github.com/user-attachments/assets/88a7a8eb-b082-4395-9f5f-c325fde55e66" />
<img width="569" height="242" alt="image" src="https://github.com/user-attachments/assets/ea2f8fd9-ee9c-4150-b936-5fd3438ea9ed" />

I then click and change "Assigned To" Jane Doe. 
Then I click "Department" and assign to SysAdmins then click transfer.
Resolving the ticket verifies that escalated issues can be managed by authorized personnel.

<img width="842" height="338" alt="image" src="https://github.com/user-attachments/assets/8947051e-f5d8-49a8-aded-230c410891e5" />

This shows now that John no longer has the access to work the ticket after the transfer. John now logs out.

<img width="378" height="252" alt="image" src="https://github.com/user-attachments/assets/50ce3986-d381-4c49-a62e-e151c4d9151e" />
<img width="844" height="316" alt="image" src="https://github.com/user-attachments/assets/b74d5361-7950-47cb-a096-adeb9f931e03" />

Jane logs in. And sees the ticket from Karen thats now assigned to her.

<img width="778" height="750" alt="image" src="https://github.com/user-attachments/assets/c72b1cb1-6222-431b-ad3f-6a622157741a" />

Jane now repsonds with the cause of the issue. Then she clicks post reply.

<img width="728" height="638" alt="image" src="https://github.com/user-attachments/assets/1d6156f2-48ae-4824-b810-01cef9e1cb95" />

Here Jane contacts Karen and confirms the issue is resolved. Jane now repost her reply on the issue and the ticket is now closed.

<img width="555" height="192" alt="image" src="https://github.com/user-attachments/assets/35261fca-411b-421f-87de-cf985ff40eb7" />

Jane then clicks the ticket's status and clcks resolved


<h2>Ticket number 2</h2>

<img width="601" height="824" alt="image" src="https://github.com/user-attachments/assets/5c9e1458-d975-49e4-b50a-a4d7d041b74c" />

Ken creates a ticket. The ticket is now sent to John.
This simulates a standard service request commonly handled by IT support teams.

<img width="844" height="342" alt="image" src="https://github.com/user-attachments/assets/ba8cf3de-b603-48d0-83d5-b5dbbe3f9eea" />

John logs in and see Ken's ticket.

<img width="631" height="664" alt="image" src="https://github.com/user-attachments/assets/9c999add-4c3c-4895-a2bf-4d2532a0421e" />

John contacts Ken to understand and gain more details on ticket issue. John then clicks post reply. 

<img width="820" height="420" alt="image" src="https://github.com/user-attachments/assets/8a59ccdb-6d55-4b3e-8535-b09d52a07289" />

John then clicks "priority level" to high then update.

<img width="556" height="215" alt="image" src="https://github.com/user-attachments/assets/d81e8e7a-5fa4-4d9e-96b8-af95e9564b45" />

John then cliks SLA Plan. John then changes from default to "Sev-B" then upadte.
A Severity B SLA prioritizes the issue appropriately without treating it as a critical outage.

<img width="779" height="683" alt="image" src="https://github.com/user-attachments/assets/a8a17878-aa83-48df-b795-827668f30e20" />

John then upadtes the ticket and provides that he contaced Josh from the Desktop Admin Group. John the post his reply in osticket.

<img width="719" height="514" alt="image" src="https://github.com/user-attachments/assets/3e0f9383-17e7-4452-a0ad-fd9470e3e2d8" />

John then post the install is working and everyone is fully up and running.

<img width="565" height="189" alt="image" src="https://github.com/user-attachments/assets/826b82a2-41bd-4a0e-9cc3-46976e97aad3" />

John then click "Status" and changes the ticket status to closed



