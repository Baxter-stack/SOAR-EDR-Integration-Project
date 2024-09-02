<div align="center">
  <h2>SOAR EDR Integration & Automation</h2>
</div>
<div align="center">
  <img src="https://github.com/user-attachments/assets/866274d9-7249-4ea0-9acd-1b93921c6d60" alt="Description" width="500">
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
- [Vmware](https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
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
# ![LimaCharlie](https://images.ctfassets.net/8ypp714zy4gs/56gQDOjtMywHI4R70K8WdJ/162b909916246fd2cb77fd95c0f74100/LimaCharlie_LogoMarkOnly_WHITE.png?w=64&q=100) EDR Installation on Virtual Machine

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

Navigate to <b>Automation</b> > <b>D&R Rules</b> > <b>New Rule</b>. 

<img src="https://github.com/user-attachments/assets/50a138cc-9e8c-4865-b6e7-7863e1280298" width="500" />
<img src="https://github.com/user-attachments/assets/61ec5e92-04ca-4ce7-91eb-0a2e80de44a9" width="500" />

#### - *We will use a template to help create the detection rule.*
Navigate to <b>Automation</b> > <b>D&R Rules</b> > <b>windows_process_creation/proc_creation_win_lolbin_device_credential_deployment</b>

<img src="https://github.com/user-attachments/assets/3440779a-44b8-4425-a371-cd1bb6fdc1de" width="500" />

Under the D&R rule, click on the GitHub repository.

<img src="https://github.com/user-attachments/assets/aa02e367-9c30-4e95-b204-3243e9f08ebe" width="500" />

Select <b>Raw</b> and copy the rule content. 

<img src="https://github.com/user-attachments/assets/9b6aeddf-861d-4511-b02d-90e859820254" width="500" />

*<b>Modify the rule content.*</b>

Detect Rule:

<img src="https://github.com/user-attachments/assets/1c230812-6122-459f-b8cf-405e7a04ab58" width="500" />

Respond Rule:

<img src="https://github.com/user-attachments/assets/4c8fe891-9f70-4b9e-9de7-a51ad6b5f283" width="500" />

Name the New Rule and hit save:

<img src="https://github.com/user-attachments/assets/1088234d-6d19-4348-8816-7182ebeddbd6" width="500" />

To test the new rule, copy the event from the timeline, paste it into the event section, and hit <b>Test Event</b>.
  
<img src="https://github.com/user-attachments/assets/7b1b72f6-08fa-47e4-94cc-a31b87795e9c" width="500" />

*<b>Can confirm that the new rule is working.</b>*

<img src="https://github.com/user-attachments/assets/47d78879-d4b6-43a8-88fe-51e0ccee07b5" width="500" />

*After running a command in the Windows Server, a detection will pop up under the <b>Detections</b> tab.*

-----
# ![Slack](https://a.slack-edge.com/3d92b39/marketing/img/nav/slack-salesforce-logo-nav-white.png)

Create [Slack](https://slack.com/get-started#/createnew) account. 

Create A New Workspace. 

<img src="https://github.com/user-attachments/assets/158a9c60-ab81-4e58-949a-553e81cbcc74" width="500" />

Choose the free plan.

Create a new channel and name it <b>alerts</b>.

<img src="https://github.com/user-attachments/assets/82e458ff-113d-4a39-92ff-78ad5d111388" width="500" />

---- 

<img src="https://firebasestorage.googleapis.com/v0/b/standards-site-beta.appspot.com/o/documents%2Fjycsjx9ypwh%2F02csbs2azqv%2FTinesLogoWhite.svg?alt=media&token=f31af318-7b96-463b-8048-9835598142ae" alt="Tines Logo" width="150" />

Create a free [tines](https://www.tines.com/) account.

Tines dashboard. 

<img src="https://github.com/user-attachments/assets/85b4c16f-4d7d-4677-973a-6d8033a0aa86" width="500" />

*<b>The goal is to link LimaCharlie and tines.*</b>

Grab the <b>Webhook</b> icon from the tools section and drag it to the story. 

Name the Webhook <b>Retrieves Detections</b> and Description <b>Retrieves Detections from LimaCharlie</b>. 

Copy the <b>Webhook URL</b> and go to LimaCharlie. 

<img src="https://github.com/user-attachments/assets/faa2366f-e908-4e25-a5db-6f899e7465bd" width="500" />

In LimaCharlie, navigate to <b>Outputs > Add Output > Detections > Tines.

<img src="https://github.com/user-attachments/assets/9722355a-207e-4db2-b528-bfbbd22f2a7c" width="500" />
<img src="https://github.com/user-attachments/assets/83d0f0a4-d3c1-4e81-a6d5-33c7c525611e" width="500" />
<img src="https://github.com/user-attachments/assets/6997900f-f5e5-4289-96c9-711b1e8ff1b2" width="500" />
<img src="https://github.com/user-attachments/assets/830badc7-fb4b-4dd8-ae81-e2e65d6e5cb9" width="500" />

Name the Output and paste the Webhook URL.

<img src="https://github.com/user-attachments/assets/01691493-479b-46ec-9afc-2a5fec65cded" width="500" />

*<b>After saving the output, you will not see a detection. Run a command in the virtual machine, Refresh Samples, and a sample detection will appear.</b>*

<img src="https://github.com/user-attachments/assets/8f8cb381-09ec-421d-bbf8-b99f0b63757c" width="500" />
<img src="https://github.com/user-attachments/assets/d21c0ed8-68c2-4a1b-b11d-7ce16e8f5da3" width="500" />

Under <b>Retrieve Detections</b>, select <b>Events</b> and take a look at the most recent event. 

<img src="https://github.com/user-attachments/assets/1e7f6478-a7bd-48d0-830e-551781a7d357" width="500" />

*<b>Next, we will link tines to slack.</b>

On slack, select <b> More > Automations > search for tines > Add > Add to Slack.</b>

<img src="https://github.com/user-attachments/assets/c84cd47e-d729-49d9-9c0e-c941b8004168" width="300" />

Follow the steps for installing the app. 

<img src="https://github.com/user-attachments/assets/9696c5d1-1012-4bc7-b4d7-e657e9aa3205" width="500" />

In the tines dashboard, navigate to <b>Your teams > Credentials > New Credentials > Slack > Use Tine's app for Slack </b>

<img src="https://github.com/user-attachments/assets/f924649b-3ac7-4602-a3b1-039fbc497160" width="500" />

<img src="https://github.com/user-attachments/assets/c7e7b120-b322-459f-b482-98c61c1b5df2" width="500" />

<img src="https://github.com/user-attachments/assets/5c44bb84-a085-4085-a9f9-2575f51e388f" width="500" />

New Slack Credential.

<img src="https://github.com/user-attachments/assets/2625a7fe-3c34-496a-b9d2-d683881882e6" width="500" />

Under templates in tines, select <b> Slack > Send a message template.</b>

On slack, right-click on alerts, select view channel details, and copy channel ID.

<img src="https://github.com/user-attachments/assets/212763bb-cf8e-4c29-98ca-71e423139a4f" width="500" />
<img src="https://github.com/user-attachments/assets/029e2a8b-a318-4493-9cbe-c0ff6399b617" width="500" />

Paste the channel ID on tines.

<img src="https://github.com/user-attachments/assets/ed0ec5ff-b0c8-4158-b340-57ebf41bf9ee" width="500" />

Now we will create the detection message with important fields. (These can be obtained under Retrieve Detections). 

<img src="https://github.com/user-attachments/assets/0d92ec72-01e3-4aaa-a18b-a05fd30589de" width="500" />

Hit <b>run</b> on slack and verify the message. 

<img src="https://github.com/user-attachments/assets/d6b89b5d-6a71-45cd-8107-71a7ac478111" width="500" />
<img src="https://github.com/user-attachments/assets/f08bdef2-c5e2-4c7c-8ccb-0496e323125e" width="500" />

----
<b> - Next we'll create a Send Email Action.</b>

Drag the Send Email Action onto the story and connect it to Webhook. 

Name the <b>Description, Sender name, and Subject</b>. 
Copy the message from the slack body and paste it into the Email Action.

<img src="https://github.com/user-attachments/assets/081672a7-e4bb-4341-b12f-5ad0ed7f1713" width="500" />

Select Run > Retrieve Detections > Test. 

<img src="https://github.com/user-attachments/assets/a1b98f57-7d16-44b8-91af-ad4e59fc972c" width="500" />

Confirmed email!

<img src="https://github.com/user-attachments/assets/d64fca7e-60f6-4aa6-8618-71211c3a2cf3" width="500" />

---
<b> - For User Prompt, hit tools and add a new page. </b>

Provide a <b> Name, Description, and Success message </b>. 

<img src="https://github.com/user-attachments/assets/8b490173-b1a2-4988-bb2b-db350aaded79" width="500" />

Select Edit on the User Prompt and input the Detection Fields. 

<img src="https://github.com/user-attachments/assets/5d50c5c6-2022-47bd-8877-09e9e5ce5be5" width="500" />

Cool!!

<img src="https://github.com/user-attachments/assets/6bcd07b6-80a2-4939-ba22-e30145618f56" width="500" />

<b> - We will now build out the Y/N responses for the User Prompt.</b> 

<img src="https://github.com/user-attachments/assets/83578fd1-e2ce-47af-acc0-e04694c4678a" width="500" />

Select the <b>Trigger</b> tool and drag it to the story. 
Name it <b>Yes</b> and input the rules.

<img src="https://github.com/user-attachments/assets/19633cb6-83d7-4bb7-ac5a-037ee6652e68" width="500" />
<img src="https://github.com/user-attachments/assets/ed50ad47-a1af-4407-80bd-3210ec308524" width="500" />

Under templates, select <b>LimaCharlie</b> and search for <b>Isolate Sensor</b>.

Provide a <b> Name and Description</b>.

Under <b>URL</b>, add the value, <b>retrieve_detections.body.routing.sid</b>.   

<img src="https://github.com/user-attachments/assets/bfbd9700-177f-4436-9968-2595afa86f9d" width="500" />
<img src="https://github.com/user-attachments/assets/b87da941-3f52-4b96-ad1b-ffef8c69c34e" width="500" />
<img src="https://github.com/user-attachments/assets/fe138534-a30f-48fd-90ba-414e38981c41" width="500" />



