# SOAR EDR Integration  
<img src="https://i.ibb.co/HxX3wh7/HVb4hnk-Imgur.png)](https://i.ibb.co/HxX3wh7/HVb4hnk-Imgur.png" width="500" />

# Project Objective
This project demonstrates the integration of Security Orchestration, Automation, and Response (SOAR) with Endpoint Detection and Response (EDR) tools to automate security workflows and enhance cybersecurity posture. By leveraging LimaCharlie for the EDR agent and Tines for SOAR, the project provides real-time security insights and automated responses to detected threats. A key feature of this integration is the ability to empower users with a prompt to decide whether to isolate the affected machine, allowing for informed decision-making and flexibility in response actions. Additionally, the project highlights the seamless communication between various platforms, such as Slack and email, ensuring that critical detection alerts and actions are efficiently communicated to relevant stakeholders. This integration streamlines the incident response process and provides a robust framework for dynamic and adaptable security operations.

# Tools Used
- Windows Machine: Target machine LimaCharlie will detect for isolation decision, where users can choose to     isolate it based on the threat severity.
- LimaCharlie (EDR): Used to detect and respond to security threats.
- Tines (SOAR): Automates the security workflows and orchestrates the response actions.
- Slack: Serves as the communication platform to receive alert detections.
- SquareX (Email): Used to receive detection alert emails.
- Vultr: Cloud provider for hosting the virtual machine used in the project. (You can use other cloud providers or use Vmware/VirtualBox, just make sure they are connected to the internet)

*Please note, you can use any cloud provider or hosted hypervisor for this project.*

# Skills Gained 
- Integration of SOAR and EDR Tools: Developed the ability to integrate SOAR tools with EDR platforms, enhancing automated incident response capabilities.
- Automation of Security Workflows: Learned to design and implement automated security workflows, enabling real-time detection, response, and notification processes that streamline incident handling.
- Threat Detection and Response: Gained experience in configuring and using LimaCharlie to detect threats on compromised endpoints, including decision-making on whether to isolate affected machines based on detected threats.
- Communication and Alerting Systems: Enhanced skills in setting up and managing communication and alerting systems using Slack and email, ensuring timely and effective dissemination of critical security information.
- User Prompt Configuration: Acquired the ability to create and configure user prompts within the SOAR workflow, allowing for interactive decision-making during the incident response process.
- Incident Response Management: Improved overall incident response management skills, including the ability to coordinate responses across multiple tools and platforms, ensuring a cohesive and efficient approach to handling security incidents.


### *Please note, you can use any cloud provider or hosted hypervisor for this project.*
----
# Windows Server Virtual Machine Setup in Vultr 

Navigate to [Vultr](https://www.vultr.com/) and create an account. (You get a free $100 credit using the hyperlink provided!)

<b> - Select Deploy + or Depploy New Server.</b>

<img src="https://github.com/user-attachments/assets/f6037365-ad39-4328-8cce-7ec1151ec2cd" width="500" />

Select “Optimized Cloud Compute - Dedicated CPU” as your New Instance and select your desired location.

<img src="https://github.com/user-attachments/assets/ef1717fd-b58b-4f73-a2ce-8c9c67e3cf46" width="500" />

For Image, select Windows Standard 2022.

<img src="https://github.com/user-attachments/assets/63217f3f-c000-4d6f-90ef-c534bfb72caa" width="500" />

Select the lowest plan. In this case, it will be $54/month.

<img src="https://github.com/user-attachments/assets/4dcedcff-4182-4886-a6f6-0180bd620671" width="500" />

Name your Hostname & Label 

<img src="https://github.com/user-attachments/assets/76dcea11-f6b4-4f9b-ae16-1bc397988857" width="500" />

After you deploy the server, you will get the “Running” status

<img src="https://github.com/user-attachments/assets/bbae925f-6152-456c-bb3c-33ee8786dbbb" width="500" />


Once the installation is completed and you get “Running” status, select “View Server Details” to obtain the machine’s password and “View Console” to access the VM.

<img src="https://github.com/user-attachments/assets/be8e5010-1eba-4bcb-8458-72ee6758a293" width="500" />

<img src="https://github.com/user-attachments/assets/a906243b-6927-46a7-82a8-fdacfc3e5137" width="500" />

-----
<b> - Next, we’ll set up our firewall.</b>.

Under products, select <b>Network</b> > <b>Firewall</b> > <b>Firewall Group</b>.

<img src="https://github.com/user-attachments/assets/0f61ace7-35d9-4804-9b14-d2eb623fb928" width="500" />

Give a Description Name and select <b>Add Firewall Group</b>

For Protocol, select <b>MS RDP</b>. <b>Source</b>, select <b>MY IP</b> and hit the + button. 

<img src="https://github.com/user-attachments/assets/c6865313-a24c-4629-b848-90cd6dcc119b" width="500" />

To add the firewall, go back to your machine and select <b>Settings</b> > <b>Firewall</b> > Click the dropdown and select the firewall you created > <b>Update Firewall Group</b>.

<img src="https://github.com/user-attachments/assets/bb014ad2-4820-42f0-bc9e-263646562044" width="500" />

<img src="https://github.com/user-attachments/assets/6a80d47c-8b29-47f1-aa32-c230daa9ac91" width="500" />

-----
# LimaCharlie (EDR) Installation

Navigate to [LimaCharlie](https://limacharlie.io/) and create an account.

<img src="https://github.com/user-attachments/assets/e08d9529-8592-4bc3-980e-4620e480aa57" width="500" />

