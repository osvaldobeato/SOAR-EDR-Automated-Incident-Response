<img width="1920" height="1080" alt="1  created a windows vm on Vultr" src="https://github.com/user-attachments/assets/aca1b042-8bd8-460a-a6e9-c2bed7bc4bd2" />

<img width="1920" height="1080" alt="2  created a firewall rule that will allow my host IP to ms rdp into it" src="https://github.com/user-attachments/assets/7bb425fe-fef2-4120-b988-d325ef4dc882" />

<img width="1920" height="1080" alt="3  Installed lima charlie agent into the windows vm" src="https://github.com/user-attachments/assets/434c206a-38b6-43cb-bd6c-4e0c9b3f81e3" />

<img width="1920" height="1080" alt="4  Confirmed that lima charlie is recieving connection from the agent thats intalled in the windows vm" src="https://github.com/user-attachments/assets/22f41ea7-39d8-4ad2-88b6-92058dec849b" />

<img width="1920" height="1080" alt="5  Created a rule on lima charlie to alert me when Lazagne and password stealer is excuted on the windows vm, setting up the rule for the simulated attack" src="https://github.com/user-attachments/assets/7a6faf93-d3be-4e9b-858f-d7eb155341ad" />

<img width="1920" height="1080" alt="6  Downloaed Lazagne amd triggered it to test out the rule in Lima Charlie" src="https://github.com/user-attachments/assets/eb5e3876-4283-48b2-afb5-8d0670168a5e" />

<img width="1920" height="1080" alt="7  Confirmed it works and the event was regesiterd " src="https://github.com/user-attachments/assets/0e4a53b2-dc62-4087-9fd1-ada0221234f2" />

<img width="1920" height="1080" alt="8  Added more to the rule and use the exsistencing detectioned of  lazagne to test the rule and confirm rule is true " src="https://github.com/user-attachments/assets/23d1498d-928f-4b3d-a549-be8ee9980e1f" />

<img width="1920" height="1080" alt="9  connected lima charlie output to tines  " src="https://github.com/user-attachments/assets/d6d1978d-2966-4cf5-9d60-de95235963b8" />

<img width="1920" height="1080" alt="10  connected lima charlie to tines webhook to recieve lazagne alerts when triggered" src="https://github.com/user-attachments/assets/91afb682-fdc8-4931-8d49-96cf400f3c9a" />

<img width="1920" height="1080" alt="11  Created a slack account, created a group and inside that group i created a channel called alerts for alerts and connected wih the webhook in tines to send a message about the lazagne alert " src="https://github.com/user-attachments/assets/cd6b2d8e-1b20-4415-8350-292fabb05d3c" />

<img width="1920" height="1080" alt="12  confirming that message was recieved in the alert channel in slack " src="https://github.com/user-attachments/assets/a490b0d5-456a-4381-9405-25d64a517d5e" />

<img width="1920" height="1080" alt="13  connected a email also as well in tines so a email is also sent to the soc assoicate when lazagne is triggered, shows it working in tines " src="https://github.com/user-attachments/assets/a708ba20-8d1e-4295-8242-3626f20794a4" />

<img width="1920" height="1080" alt="14  confirming that email is getting the alert " src="https://github.com/user-attachments/assets/a269069e-5d0a-4a19-9da1-71d5aa58083c" />

<img width="1920" height="1080" alt="15  added a user input app in tines to give the option to isolate or not " src="https://github.com/user-attachments/assets/3366e3f9-deb2-4b7c-a598-6678d4a27bdd" />

<img width="1920" height="1080" alt="16  edited slack app in tines to send certain information from the alert into slack to give the soc analyst more context such as title, time, computer, source IP, Username, Filepath, commandline, sesnor Id,link " src="https://github.com/user-attachments/assets/58d5e327-1e97-4e5b-a802-36700c0001c4" />

<img width="1920" height="1080" alt="17  Did the same edit for email give more context of the alert to the email " src="https://github.com/user-attachments/assets/2e905df9-95b8-4ce7-8b78-e9e7181d9966" />

<img width="1920" height="1080" alt="18 edited the user input and added all the same context info that we put in slack alert  and email alert to give more context of what were isolating " src="https://github.com/user-attachments/assets/79d5ebd4-a17e-4156-9e1c-f9a75eccf5dd" />

<img width="1920" height="1080" alt="19  Added a no condition to the user prompt and connnected that back to slack and edited the slack message towards this no alert, shows its working in tines " src="https://github.com/user-attachments/assets/8b467e53-11b7-49ec-a162-1cc70b1c29d4" />

<img width="1920" height="1080" alt="20  confirmed the user promt thats attached to the no condition that is attached to slack is working getting the message it was not isolate please investigate  " src="https://github.com/user-attachments/assets/2a15c388-1a59-4751-b4a0-0d5fb9fa515e" />

<img width="1920" height="1080" alt="21  Added the yes condition to the user prompt and connected it to lima charlie to isolate the machine, shows its working in tines " src="https://github.com/user-attachments/assets/714e4ad6-d991-4d68-8c9a-54d8ea860ba1" />

<img width="1920" height="1080" alt="22  Went to lima charlie to confirm the windows machine was isolated" src="https://github.com/user-attachments/assets/6d437921-b372-43d1-9a91-ff0f2515e76e" />

<img width="1920" height="1080" alt="23  Went to the windows machine and another confirmation it has been isolated as I was kick out of the connection " src="https://github.com/user-attachments/assets/103eeed4-430a-43c0-acdb-518454c59cc7" />

<img width="1920" height="1080" alt="24  added another lima charlie request to only get the status of the isolation, if was it successful or not and sent that status to slack alert, shows the workflow working in tines" src="https://github.com/user-attachments/assets/36e7b6d7-084e-48ce-89ea-8246bc2d131f" />

<img width="1920" height="1080" alt="25  showing lima charlie app is working in tines, recieving the lazagne alert" src="https://github.com/user-attachments/assets/786557a5-35a8-4157-ab71-e20a96841a97" />

<img width="1920" height="1080" alt="26  showing the request from lima charlie status of the isolation was successful or not is showing its working in lima charlie " src="https://github.com/user-attachments/assets/39ac407a-adf7-4968-b1be-1bb07a0f8d14" />

<img width="1920" height="1080" alt="27  slack reciving the alert that the computer has been isolated and as you can see i edited the slack message to giv eslack the status, the computer and also that it has been isolated " src="https://github.com/user-attachments/assets/20059aee-8fde-42db-982c-22f1873693ce" />

<img width="1920" height="1080" alt="28  picture of the whole workflow " src="https://github.com/user-attachments/assets/899ac6fd-5459-44f9-af12-30ad623bffa1" />

<img width="954" height="782" alt="29  Diagram" src="https://github.com/user-attachments/assets/466da8b4-3aa3-41e5-9d58-1c46065ea648" />
