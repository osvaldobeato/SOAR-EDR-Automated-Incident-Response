# Project Overview

---

# Architecture

---

# Skills Learned

---

# Tools Used

---

# Investigation Walkthrough

## Phase 1 – Environment Deployment

<img width="1920" height="1080" alt="1  created a windows vm on Vultr" src="https://github.com/user-attachments/assets/9531f28e-1742-47cd-85b8-635a2e6d880b" />
Provisioned a Windows virtual machine on Vultr to serve as the endpoint for endpoint detection, response testing, and SOAR automation validation.

&nbsp;

<img width="1920" height="1080" alt="2  created a firewall rule that will allow my host IP to ms rdp into it" src="https://github.com/user-attachments/assets/78faae7a-5258-4eb8-af03-9644dbf6bb94" />
Configured a firewall rule permitting Remote Desktop Protocol (RDP) access only from the authorized host IP address, enabling secure administrative management of the endpoint.

&nbsp;

<img width="1920" height="1080" alt="3  Installed lima charlie agent into the windows vm" src="https://github.com/user-attachments/assets/cb14e08b-cdc9-4cb1-b95b-77a7c08665a8" />
Installed the LimaCharlie endpoint agent on the Windows virtual machine to begin collecting endpoint telemetry and enable EDR capabilities.

&nbsp;

<img width="1920" height="1080" alt="4  Confirmed that lima charlie is recieving connection from the agent thats intalled in the windows vm" src="https://github.com/user-attachments/assets/2af5059a-2de2-4062-8990-6def86e810fe" />
Verified that the Windows endpoint successfully connected to the LimaCharlie cloud platform and was actively reporting telemetry.


&nbsp;
&nbsp;

  
## Phase 2 – Detection Engineering

<img width="1920" height="1080" alt="5  Created a rule on lima charlie to alert me when Lazagne and password stealer is excuted on the windows vm, setting up the rule for the simulated attack" src="https://github.com/user-attachments/assets/1b37d03d-02cf-46a4-9314-139eab567067" />
Developed a custom LimaCharlie detection rule to identify execution of LaZagne, a credential-dumping utility commonly used during post-exploitation activities.

&nbsp;

<img width="1920" height="1080" alt="6  Downloaed Lazagne amd triggered it to test out the rule in Lima Charlie" src="https://github.com/user-attachments/assets/12f28148-de94-494e-9f66-6c643cc5f843" />
Executed LaZagne on the Windows endpoint to simulate credential theft and generate telemetry for validating the custom detection rule.

&nbsp;

<img width="1920" height="1080" alt="7  Confirmed it works and the event was regesiterd " src="https://github.com/user-attachments/assets/0f5a3eaf-019f-4de8-af71-a1c48e6465eb" />
Confirmed that the custom detection rule successfully detected LaZagne execution and generated the expected security event within LimaCharlie.

&nbsp;

<img width="1920" height="1080" alt="8  Added more to the rule and use the exsistencing detectioned of  lazagne to test the rule and confirm rule is true " src="https://github.com/user-attachments/assets/8959394f-bdea-419e-9232-1b157a738b9d" />
Enhanced and validated the custom detection rule by testing it against previously detected LaZagne activity to ensure reliable alert generation.

&nbsp;
&nbsp;

## Phase 3 – SOAR Workflow Development

<img width="1920" height="1080" alt="9  connected lima charlie output to tines  " src="https://github.com/user-attachments/assets/e0f425a2-dcc1-486b-9c5f-f1fb942ad517" />
Integrated LimaCharlie with Tines by configuring a webhook to automatically forward detection events into the SOAR workflow.

&nbsp;

<img width="1920" height="1080" alt="10  connected lima charlie to tines webhook to recieve lazagne alerts when triggered" src="https://github.com/user-attachments/assets/1dde4c55-d0d6-4edb-a9ed-869e1fc59504" />
Verified successful webhook integration by confirming LimaCharlie alerts were received within the Tines automation workflow.

&nbsp;

<img width="1920" height="1080" alt="11  Created a slack account, created a group and inside that group i created a channel called alerts for alerts and connected wih the webhook in tines to send a message about the lazagne alert " src="https://github.com/user-attachments/assets/4b69af66-2272-4632-8e12-386ab3570fe8" />
Configured Slack integration within Tines to automatically notify the SOC team whenever a LaZagne detection occurs.

&nbsp;

<img width="1920" height="1080" alt="12  confirming that message was recieved in the alert channel in slack " src="https://github.com/user-attachments/assets/f25da9ca-4f19-4397-b2f9-4b0c753fdcbb" />
Confirmed that detection alerts were successfully delivered to the designated Slack alert channel.

&nbsp;

<img width="1920" height="1080" alt="13  connected a email also as well in tines so a email is also sent to the soc assoicate when lazagne is triggered, shows it working in tines " src="https://github.com/user-attachments/assets/91e60f85-6e82-4103-b1b2-735185f71722" />
Added automated email notifications to ensure SOC analysts receive detection alerts through multiple communication channels.

&nbsp;

<img width="1920" height="1080" alt="14  confirming that email is getting the alert " src="https://github.com/user-attachments/assets/62b739e7-3316-451d-9cb8-34a64da69e2d" />
Verified successful email delivery following detection of simulated malicious activity.

&nbsp;
&nbsp;

## Phase 4 – Analyst Decision Workflow

<img width="1920" height="1080" alt="15  added a user input app in tines to give the option to isolate or not " src="https://github.com/user-attachments/assets/9098c4a4-eca3-4cf2-b777-de0adc89f584" />
Added a user approval step within Tines, allowing a SOC analyst to decide whether endpoint isolation should be performed before automated containment actions execute.

&nbsp;

<img width="1920" height="1080" alt="16  edited slack app in tines to send certain information from the alert into slack to give the soc analyst more context such as title, time, computer, source IP, Username, Filepath, commandline, sesnor Id,link " src="https://github.com/user-attachments/assets/5268b9fa-70cf-4dc3-8690-376a44f2f36f" />
Expanded Slack notifications to include investigation context such as hostname, username, source IP, file path, command line, sensor ID, timestamp, and alert details to support analyst decision-making.

&nbsp;

<img width="1920" height="1080" alt="17  Did the same edit for email give more context of the alert to the email " src="https://github.com/user-attachments/assets/b46611d7-db78-4f05-91ec-46815a3c659a" />
Added the same investigation context to automated email notifications, providing analysts with sufficient information to assess the alert.

&nbsp;

<img width="1920" height="1080" alt="18 edited the user input and added all the same context info that we put in slack alert  and email alert to give more context of what were isolating " src="https://github.com/user-attachments/assets/f0f008e0-d0c3-4b72-baa6-6a17fd626fee" />
Updated the analyst approval form to display detailed endpoint and detection information, enabling informed containment decisions directly from the approval request.

&nbsp;

<img width="1920" height="1080" alt="19  Added a no condition to the user prompt and connnected that back to slack and edited the slack message towards this no alert, shows its working in tines " src="https://github.com/user-attachments/assets/68cc51f2-62da-407d-a099-297895dad9ac" />
Configured the No response path within the analyst approval workflow to cancel automated isolation and notify the SOC team that additional investigation is required.

&nbsp;

<img width="1920" height="1080" alt="20  confirmed the user promt thats attached to the no condition that is attached to slack is working getting the message it was not isolate please investigate  " src="https://github.com/user-attachments/assets/3086f87b-00ea-415b-9b1c-5e51b90feab9" />
Validated the No workflow by confirming Slack received a notification indicating that endpoint isolation was not performed and that further investigation should continue.

&nbsp;
&nbsp;

## Phase 5 – Automated Endpoint Response

<img width="1920" height="1080" alt="21  Added the yes condition to the user prompt and connected it to lima charlie to isolate the machine, shows its working in tines " src="https://github.com/user-attachments/assets/9861e852-b998-41ed-901f-b856c71908e5" />
Configured the Yes response path within the analyst approval workflow to trigger LimaCharlie endpoint isolation, enabling analysts to approve automated containment directly from the Tines workflow.

&nbsp;

<img width="1920" height="1080" alt="22  Went to lima charlie to confirm the windows machine was isolated" src="https://github.com/user-attachments/assets/14e3fdb8-b386-415f-9f52-a2ac6e5daed9" />
Verified within LimaCharlie that the endpoint isolation request was successfully executed after analyst approval.

&nbsp;

<img width="1920" height="1080" alt="23  Went to the windows machine and another confirmation it has been isolated as I was kick out of the connection " src="https://github.com/user-attachments/assets/115e4189-5fe2-4b2d-9164-5b56cba56f4d" />
Confirmed successful network isolation by observing the Windows endpoint lose remote connectivity immediately after the containment action was performed.

&nbsp;


<img width="1920" height="1080" alt="24  added another lima charlie request to only get the status of the isolation, if was it successful or not and sent that status to slack alert, shows the workflow working in tines" src="https://github.com/user-attachments/assets/3f395b7b-0567-4c47-9938-f4214d7a5ec8" />
Added an additional LimaCharlie action to retrieve the endpoint isolation status and forward the result to Slack, providing analysts with confirmation that the containment action completed successfully.

&nbsp;

<img width="1920" height="1080" alt="25  showing lima charlie app is working in tines, recieving the lazagne alert" src="https://github.com/user-attachments/assets/6e8cb2d2-6592-4bc9-a2d7-0ec6873ffa25" />
Verified that Tines successfully communicated with LimaCharlie and executed the endpoint response action following analyst approval.

&nbsp;


<img width="1920" height="1080" alt="26  showing the request from lima charlie status of the isolation was successful or not is showing its working in lima charlie " src="https://github.com/user-attachments/assets/107d2285-46e6-4b85-b5a1-095b9a89082a" />
Confirmed that LimaCharlie returned a successful endpoint isolation status, validating completion of the containment action.

&nbsp;

<img width="1920" height="1080" alt="27  slack reciving the alert that the computer has been isolated and as you can see i edited the slack message to giv eslack the status, the computer and also that it has been isolated " src="https://github.com/user-attachments/assets/b085e2dd-66ab-46f0-a7e8-b052c3542e29" />
Enhanced Slack notifications to display the endpoint hostname, isolation status, and successful containment message, providing immediate confirmation to SOC analysts.

&nbsp;

<img width="1920" height="1080" alt="28  picture of the whole workflow " src="https://github.com/user-attachments/assets/7d915891-259d-4baa-8f69-2e4229d1d7c0" />
Final end-to-end SOAR workflow demonstrating automated detection, analyst notification, approval-based decision making, endpoint isolation, and post-containment verification within Tines.

---

Indicators of Compromise

MITRE ATT&CK Mapping

Automation Workflow Summary

Key Findings

Lessons Learned
