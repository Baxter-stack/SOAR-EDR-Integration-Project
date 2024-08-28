<div align="center">
  <h2>SOAR EDR Integration</h2>
</div>
<div align="center">
  <img src="https://i.ibb.co/HxX3wh7/HVb4hnk-Imgur.png)](https://i.ibb.co/HxX3wh7/HVb4hnk-Imgur.png" alt="Description" width="500">
</div>

# Project Objective
This project demonstrates the integration of Security Orchestration, Automation, and Response (SOAR) with Endpoint Detection and Response (EDR) tools to automate security workflows and enhance cybersecurity posture. By leveraging LimaCharlie for the EDR agent and Tines for SOAR, the project provides real-time security insights and automated responses to detected threats. A key feature of this integration is the ability to empower users with a prompt to decide whether to isolate the affected machine, allowing for informed decision-making and flexibility in response actions. Additionally, the project highlights the seamless communication between various platforms, such as Slack and email, ensuring that critical detection alerts and actions are efficiently communicated to relevant stakeholders. This integration streamlines the incident response process and provides a robust framework for dynamic and adaptable security operations.

# Tools Used
- <b>Windows Machine</b>: Target machine LimaCharlie will detect for isolation decision, where users can choose to isolate it based on the threat severity.
- <b> LimaCharlie (EDR)</b>: Used to detect and respond to security threats.
- <b>Tines (SOAR)</b>: Automates the security workflows and orchestrates the response actions.
- <b>Slack</b>: Serves as the communication platform to receive alert detections.
- <b>SquareX (Email)</b>: Used to receive detection alert emails.
- <b>Vultr</b>: Cloud provider for hosting the virtual machine used in the project. (You can use other cloud providers or use Vmware/VirtualBox, just make sure they are connected to the internet)

# Skills Gained 
- Integration of SOAR and EDR Tools: Developed the ability to integrate SOAR tools with EDR platforms, enhancing automated incident response capabilities.
- Automation of Security Workflows: Learned to design and implement automated security workflows, enabling real-time detection, response, and notification processes that streamline incident handling.
- Threat Detection and Response: Gained experience in configuring and using LimaCharlie to detect threats on compromised endpoints, including decision-making on whether to isolate affected machines based on detected threats.
- Communication and Alerting Systems: Enhanced skills in setting up and managing communication and alerting systems using Slack and email, ensuring timely and effective dissemination of critical security information.
- User Prompt Configuration: Acquired the ability to create and configure user prompts within the SOAR workflow, allowing for interactive decision-making during the incident response process.
- Incident Response Management: Improved overall incident response management skills, including the ability to coordinate responses across multiple tools and platforms, ensuring a cohesive and efficient approach to handling security incidents.


#### <b> *Please note: You can use any cloud provider or hosted hypervisor for this project.* </b>
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
<b> - Next, we’ll set up the firewall.</b>.

Under products, select <b>Network</b> > <b>Firewall</b> > <b>Firewall Group</b>.

<img src="https://github.com/user-attachments/assets/0f61ace7-35d9-4804-9b14-d2eb623fb928" width="500" />

Give a Description Name and select <b>Add Firewall Group</b>

For Protocol, select <b>MS RDP</b>. <b>Source</b>, select <b>MY IP</b> and hit the + button. 

<img src="https://github.com/user-attachments/assets/c6865313-a24c-4629-b848-90cd6dcc119b" width="500" />

To add the firewall, go back to your machine and select <b>Settings</b> > <b>Firewall</b> > Click the dropdown and select the firewall you created > <b>Update Firewall Group</b>.

<img src="https://github.com/user-attachments/assets/bb014ad2-4820-42f0-bc9e-263646562044" width="500" />

<img src="https://github.com/user-attachments/assets/6a80d47c-8b29-47f1-aa32-c230daa9ac91" width="500" />

-----
# LimaCharlie (EDR) Installation on Virtual Machine

Navigate to [LimaCharlie](https://limacharlie.io/) and create an account.

Create a New Organization, select your name and desired residency region.

<img src="https://github.com/user-attachments/assets/e08d9529-8592-4bc3-980e-4620e480aa57" width="500" />

<img src="https://github.com/user-attachments/assets/f3fd3849-2358-466b-a35f-e5b3721968d2" width="500" />

For the installation key, remove the default keys and create a new key.

<img src="https://github.com/user-attachments/assets/824cc7ee-9ad8-4f45-af6e-159df3dd7772" width="500" />

Next, under <b>Sensor Downloads</b>, copy the link address for the <b>Windows 64 bit</b> EDR agent and paste into server MS Edge page.

<img src="https://github.com/user-attachments/assets/fa0dfd54-ad6f-40c7-aea6-d7c8aed3787c" width="500" />
<img src="https://github.com/user-attachments/assets/6e98b131-fbcf-4e60-aa73-01abc0d1c505" width="500" />

Copy sensor key which is the installation key

<img src="https://github.com/user-attachments/assets/96af6c87-2190-4953-9584-4530efb7d6a6" width="500" />

Open Powershell on the Server as <b>Administrator</b>.

Navigate to the downloads directory.

Type in the hcp.exe downloaded, insert <b> -i </b>, the sensor key (installation key) and hit enter.

 <img src="https://github.com/user-attachments/assets/ddfa5bd2-73e3-4cfa-8595-80240e1df32f" width="500" />

 <img src="https://github.com/user-attachments/assets/fe512496-c6c2-411e-8332-42dafde3ec88" width="500" />

<b>Sweet! The Agent was installed successfully!</b>

We can confirm that the sensor is active! 

<img src="https://github.com/user-attachments/assets/fcd6352a-4c7c-4685-9bd6-64999b0b5fc1" width="500" />

Sensor Details:

<img src="https://github.com/user-attachments/assets/fa36081b-7b6f-43f7-8864-7eca502927c9" width="500" />

---
<b> - Next, we will download LaZagne (Password Recovery Tool) on the Windows Server to generate telemetry in LimaCharlie </b>

Click on the [LaZagne](https://github.com/AlessandroZ/LaZagne) Repo by Alessandro and select <b>Release v2.4.6 > LaZagne.exe</b>

#### <b> *Please note: You will have to disable Real-time protection under Windows Security for LaZagne.exe to download successfully.* </b>

From the downloads folder, hold shift and right-click on <b>LaZagne</b> and <b>Open Powershell window here</b>.

<img src="https://github.com/user-attachments/assets/cef7b445-21ea-4c0c-85fa-088ef4815458" width="500" />

Can confirm LaZagne is working. 

<img src="https://github.com/user-attachments/assets/4e293a18-2073-46ff-a320-1e338d96c34a" width="500" />

After running the command, LimaCharlie will generate a <b>NEW_PROCESS event</b>.

<img src="https://github.com/user-attachments/assets/ff96c3bf-6c75-415b-934e-7413d4b9e94a" width="500" />

Event Information:

<img src="https://github.com/user-attachments/assets/40588b49-5854-4769-9125-aeec38eaf9b7" width="500" />


<b> - Detection & Response Rule Creation </b>
