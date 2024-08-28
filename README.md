# SOAR-EDR-Integration-Project 
<img src="https://github.com/user-attachments/assets/d56e2f15-344c-460a-8467-cc0542b516ba" width="500" />

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

# Windows Server Virtual Machine Setup in Vultr 

Navigate to the [Vultr](https://www.vultr.com/) and create an account. (You get a free $100 credit using the hyperlink provided!)



<img src="https://github.com/user-attachments/assets/474105bc-a6b0-4384-8452-0bd3122660e1" width="500" />

Navigate to the Vultr and create an account. (You get a free $100 credit using the hyperlink provided!)
Select Deploy + or Depploy New Server 
Select “Optimized Cloud Compute - Dedicated CPU” as your New Instance
Choose your Location 
For Image, select “Windows Standard” 2022
Select the lowest plan. In this case, it will be $54/month
Name your Hostname & Label 
After you deploy the server, you will get the “Running” status
Once the installation is completed and you get “Running” status, select “View Server Details” to obtain the machine’s password and “View Console” to access the VM
