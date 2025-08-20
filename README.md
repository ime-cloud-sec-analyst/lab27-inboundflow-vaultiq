# lab27-inboundflow-vaultiq
Amazon Connect inbound contact flow for VaultIQ Solutions with IVR menu, routing, and BasicQueue setup.
Lab 27 – Inbound Contact Flow with Amazon Connect (VaultIQ Solutions)
📌 Overview

This lab demonstrates the setup of an Amazon Connect inbound contact flow for VaultIQ Solutions.
The flow is designed to greet callers, present them with IVR options, and route them to the correct department using BasicQueue.
It also integrates user management, error handling, and contact control to simulate a real-world enterprise call center solution.

🎯 Objectives

Configure an inbound contact flow with a professional IVR.

Route customers to the appropriate queue based on their input.

Assign agents and routing profiles using User Management.

Validate the working flow through test calls.

Document implementation for cloud security and operations portfolios.

🏗️ Architecture
Caller → Amazon Connect Entry Point → IVR Menu (Get Customer Input)
   → Finance Queue (1)
   → Customer Services Queue (2)
   → HR Queue (3)
   → Technical Support Queue (4)
   → Developer Queue (5)
   → Transport Queue (6)
   → Error Handling (Invalid Input / Timeout)


Queues: All departments route to BasicQueue by default.

Agents: Managed in Amazon Connect user settings.

Routing Profiles: Agents are assigned to Basic Routing Profile.

📞 IVR Script

When a caller dials in, the following menu is played:

Welcome to VaultIQ Solutions.  
For Finance, press 1.  
For Customer Services, press 2.  
For Human Resources, press 3.  
For Technical Support, press 4.  
For Developers, press 5.  
For Transport, press 6.  
To repeat these options, press the star key.  


Invalid input → “We are experiencing technical issues, please call again later.”

Timeout → Call ends gracefully.

⚙️ Implementation Steps
1. Amazon Connect Setup

Launched Amazon Connect Instance.

Configured inbound phone number.

Assigned contact flow to entry point.

2. Contact Flow Design

Block Play Prompt → Welcome message.

Block Get Customer Input → Collect keypad input.

Blocks Check Contact Attributes → Route input to queue.

Block Transfer to Queue → Sends call to BasicQueue.

Block Error Handling → Default prompt on invalid input.

3. Queues and Routing

All calls routed to BasicQueue.

Routing profile set as Basic Routing Profile.

Agents mapped to queues through User Management.

4. User Management

User created: imeben (Agent + Admin).

Security Profiles: Agent, Admin.

Phone Type: Softphone.

Routing Profile: Basic Routing Profile.

5. Testing

Placed test calls to verify:

Menu prompts play correctly.

Inputs route to BasicQueue.

Invalid inputs play error message.

Calls terminate gracefully when no input is provided.

🛠️ Tools & Services Used

Amazon Connect (Contact Flow, Queues, User Management)

Amazon Connect CCP (Contact Control Panel) for agent interface

AWS IAM for identity and access management

Softphone for call testing

✅ Outcomes

Successfully built a working IVR system with department routing.

Enabled user roles and routing profiles for call handling.

Completed Lab 27 as part of VaultIQ AWS Cloud Security & Contact Center portfolio.

📂 Repository Contents

screenshots/ – Screenshots of flow design, queues, and user setup

contact-flow-diagram.png – Visual of IVR flow

README.md – Documentation

🚀 Significance

This lab demonstrates practical cloud security engineering and operations setup for enterprise call center solutions.
It showcases:

IVR and inbound call flow design.

Secure queue-based routing.

Integration with agent management.

Such solutions are critical for customer experience, automation, and operational efficiency in modern enterprises.

🔗 Author

👤 Ime Ben

AWS Cloud Security Engineer | DevSecOps | Cloud Architect

GitHub: ime-cloud-sec-analyst

Company: VaultIQ Global Solutions Ltd
