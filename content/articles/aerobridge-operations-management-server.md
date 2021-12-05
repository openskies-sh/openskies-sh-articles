---
title: "Aerobridge Guardian: Secure your drone operations"
date: 2020-12-11
draft: False
categories: ["aerobridge", "India","cyber security"]
tags: ["Management Server","Operations"]
---

Aerobridge is a management server that helps operators and manufacturers secure their equipment and operations using the mature and well-tested Public Key Infrastructure and commonly available identity and authentication standards.
<!--more-->

Security of drone operations is an important consideration as drone flights scale up. Cyber security for drone operations is a crucial component of running a safe, secure operation. For small companies, ensuring operational security means large investments in software and systems. Operational security from a very practical point of view means solving some basic problems for operators. e.g. How does a company ensure that the flight path for which the permission was granted is the one that is actually flown by the pilots? If pilot has left the company, how does it ensure that they dont have access to the company's hardware and software? If a drone is marked as stolen in the company's systems, it should not be able to fly operations for the company. This kind of system is fairly common for private companies in IT. For e.g. once a company issues you a laptop they can specify what apps can and cannot be installed on it. In the same way, a employee who is no longer associated with the company should not be able to fly or operate company equipment

To run a world-class drones operation, a operator needs to build a digital storage, security, auditing system and be compliant with regulations. All of this puts a heavy burden on the drone manufacturers and operators who now have to understand the workings of PKI and additionally to store and manage and share sensitive data. In the absence of accessible digital infrastructure, these operations are time-consuming and problematic in the long term and most importantly do not scale. Therefore we have built a entire system of storage, security and identity for operators and secure their operations.

### Introduction

Aerobridge is an open-source implementation a Management Server that addresses these key issues: it helps with data storage, integration with Identity and Authentication technologies, compatibility GCS and the Registered Flight Module e.g. ArduPilot. The project does in the open source by following commonly available and popular technologies that are used on the internet e.g. OAUTH and JSON Web Signatures and Tokens. These are also used in the current and upgoing standards in the drone ecosystem therefore this will be compatible with any upcoming regulations.

### Aerobridge + Aerobridge Guardian

![Aerobridge Guardian](/images/aerobridge-guardian-system.png)

The Aerobridge management server Aerobridge Guardian (the GCS integration) interfaces with different aspects of this system via well-defined APIS, following are the key components:

1. An Authorization server (Flight Passport) - This is a OAUTH server that issues and signs JSON web tokens and JSON web signatures. OAUTH is a industry standard and in this case we use a server specifically developed for drones [Flight Passport](https://github.com/openskies-sh/flight_passport), you can see more information about OAUTH, the need for a server to focus on drones on the repository. 

2. The management server (Aerobridge)- It interacts with Authorization server, acts as a data storage for keys, and also grants secure access to 3rd Party applications. These are done via a set of standardized, well-documented APIs that have been tested. You can see the [Aerobrige API](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/openskies-sh/aerobridge/master/api/aerobridge-1.0.0.resolved.yaml) or explore the [front end](https://aerobridgetestflight.herokuapp.com/launchpad/)

3. Ground Control station, Firmware and Bootloader (Aerobridge Guardian) -  The Ground Control software or management client is that bridges the gap between the management server and the drone. You can see the current implementation based on [QGroundcontrol](https://github.com/openskies-sh/qgroundcontrol)

A permission object as a JSON web signature is downloaded from the authorization server has to be transferred to the drone and the flight controller is required to arm the drone once the validity has been verified. In addition, flight logs have to be signed by the flight controller and sent back to Aerobridge, closing the loop. A full workflow is below: 

![Aerobridge Guardian Workflow](/images/aerobridge-guardian.png)

### Blazing the trail in India

The Aerobridge Guardian is a unique architecture that satisfies the important considerations of security, data integrity and auditability of drone operations. The reliance on PKI and other open technologies to sign data ensures that well known and robust security mechanisms and interfaces are utilized. However, this technologically intensive workflow imposes a huge burden of compliance understanding on the manufacturers and operators.
This is especially pronounced for small companies (SMEs) in the Indian ecosystem where the resources are limited and there is sometimes no capacity to invest in understanding and implementing this infrastructure. Manufacturers are focused on certification and other hardware / manufacturing aspects of their company and operators are focused on the operations and pilots side. This affects both local manufacturers and operators stunting the ecosystem and limits hardware and operational innovation.

Aerobridge project, therefore, serves two important purposes for the Indian Drone Ecosystem and potentially for projects like PX4 and Ardupilot:

- Providing reference / best in class implementations for compliance thereby enabling any operator / manufacturer large or small a clear ramp to compliance and speeds up their ability to join the ecosystem.
- Build capacity in the ecosystem for world class open solutions to drone security, operation auditability as the ecosystem evolves. Aerobridge has built a small but thriving community of engineers innovating on open technologies around Digital Sky and drone operations in India.
  
### Aerobridge Community

The community and its engineering focus on the project provides a blueprint for the organization of drone communities in India’s neighborhood or jurisdictions where a digital security of operations might be of interest. We have been able to get together a group of technical engineers who understand drone operations and provide technical solutions to regulatory challenges. Communities like Aerobridge work symbiotically with the broader drone open-source community working at a different level of the ecosystem.

The ideas that encapsulate Aerobridge Guardian: utilizing PKI to authorize and approve drone flights have some ideas that are relevant to the entire drone community beyond India. It effectively addresses the concerns that many regulators and government agencies have around security, safety and operational intent. It also provides room for a decentralized market-based approach to drone operations and promotes local manufacturing. What was missing till now is an open, world-class reference implementation and the Aerobridge project completes the ecosystem in India. There is a long way ahead and the community in India is just getting started.

### Join Aerobridge

You can join the community by filling out the form on [www.aerobridge.in](https://www.aerobridge.in)

### Authors

- Dr. Hrishikesh Ballal is the Lead Developer at Aerobridge. Aerobridge is part of a portfolio of open-source projects built and operated by Openskies Aerial Technology Ltd. a company he founded.
- Vibhu Tripathi is the founder of Vizzbee Robotics Solutions Pvt. Ltd. and the community lead at Aerobridge in addition to being Ambassador at PX4, he has been instrumental in organizing and connecting the community to the broader ecosystem.