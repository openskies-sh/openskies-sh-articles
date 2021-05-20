---
title: "Aerobridge: A open-source manufacturers management server for India"
date: 2020-12-11
draft: False
categories: ["aerobridge", "India","digital sky"]
tags: ["Management Server","Digital Sky"]
---

There has been a flurry of activity around standardization of drone operations to support innovation, performance and safety. In this article we will focus on the specific topic of Remote-ID for drones.

The Civil Aviation Authority of India, DGCA, released the RPAS Guidance Manual, which makes it mandatory for the drone to be interfaced with the Digital Sky Infrastructure for flight authorizations. The Digital Sky infrastructure works on concepts of Public Key Infrastructure (PKI) to authorize, identify and validate the identity of the different stakeholders and also of flight operations.
<!--more-->


In reality, the Digital Sky and No Permission No Takeoff (NPNT) architecture means that not only the manufacturer but also the operator (who may or may not be the same entity) needs to be involved in acquiring and transferring sensitive data from Digital Sky to the drone and vice versa.

This puts a heavy burden on the drone manufacturers and operators who now have to understand the workings of PKI and additionally to store and manage and share sensitive data. In the absence of digital infrastructure, these operations are time-consuming and problematic in the long term and most importantly do not scale. The RPAS guidance manual recognizes this and proposes the concept of a “manufacturer’s management server” to help with this.

### Introduction

Aerobridge is an open-source implementation of this Management Server that addresses these key issues: it helps with data storage, integration with Digital Sky, compatibility GCS and the Registered Flight Module. In India, recently, there have been developments in the UAS ecosystem and the first draft of the [National Unmanned Aircraft Traffic Management Policy](https://www.civilaviation.gov.in/sites/default/files/National-UTM-Policy-Discussion-Draft-30-Nov-2020-updated.pdf) transitions the current monolithic Digital Sky infrastructure to a federation of traffic management and other services interacting with Digital Sky via a Digital Sky UTM Service Provider. As the regulatory environment changes, Aerobridge will continue to evolve.

### Aerobridge now and future

![RID Flow image](/images/aerobridge-diagram-full.png)

The Aerobridge server interfaces with different aspects of the current and proposed components of the regulatory ecosystem:

1. Digital Sky / Digital Sky UTMSP - As the Digital Sky ecosystem evolves and the regulators bring in changes to policy and add additional supplemental data and service requirements, Aerobridge will maintain compatibility with these changes.

2. The management server - It interacts with Digital Sky APIs, stores keys of the drone flight module, and also grants secure access to 3rd Party applications. These are done via a set of standardized, well-documented APIs that have been tested.

3. Ground Control station, Firmware and Bootloader -  The Ground Control software or management client is that bridges the gap between the management server and the drone.

A permission artefact downloaded from Digital Sky has to be transferred to the drone and the flight controller is required to arm the drone once the validity has been verified. In addition, flight logs have to be signed by the flight controller and sent back to Digital Sky. We anticipate that we will be building integrations with QGC and a PX4/Ardupilot to cryptographically check the permission artefacts and sign flight logs.  

### Blazing the trail in India

The Digital Sky is a unique architecture that satisfies the important considerations of security, data integrity and auditability of drone operations. The reliance on PKI and other open technologies to sign data ensures that well known and robust security mechanisms and interfaces are utilized. However, this technologically intensive workflow imposes a huge burden of compliance understanding on the manufacturers and operators. 
This is especially pronounced for small companies (SMEs) in the Indian ecosystem where the resources are limited and there is sometimes no capacity to invest in understanding and implementing this infrastructure. Manufacturers are focused on certification and other hardware / manufacturing aspects of their company and operators are focused on the operations and pilots side. This affects both local manufacturers and operators stunting the ecosystem and limits hardware and operational innovation.

Aerobridge project, therefore, serves two important purposes for the Indian Drone Ecosystem and potentially for projects like PX4 and Ardupilot:

- Providing reference / best in class implementations for compliance thereby enabling any operator / manufacturer large or small a clear ramp to compliance and speeds up their ability to join the ecosystem.
 
- Build capacity in the ecosystem for world class open solutions to drone security, operation auditability as the ecosystem evolves. Aerobridge has built a small but thriving community of engineers innovating on open technologies around Digital Sky and drone operations in India.
  
### Aerobridge Community 

The community and its engineering focus on the project provides a blueprint for the organization of drone communities in India’s neighborhood or jurisdictions where a Digital Sky like infrastructure might be of interest. We have been able to get together a group of technical engineers who understand drone operations and provide technical solutions to regulatory challenges. Communities like Aerobridge work symbiotically with the broader drone open-source community working at a different level of the ecosystem.

The ideas that encapsulate Digital Sky: utilizing PKI to authorize and approve drone flights have some ideas that are relevant to the entire drone community beyond India. It effectively addresses the concerns that many regulators and government agencies have around security, safety and operational intent. It also provides room for a decentralized market-based approach to drone operations and promotes local manufacturing. What was missing till now is an open, world-class reference implementation and the Aerobridge project completes the ecosystem in India. There is a long way ahead and the community in India is just getting started.

### Join Aerobridge

You can join the community by filling out the form on [www.aerobridge.in](https://www.aerobridge.in)

### Authors

- Dr. Hrishikesh Ballal is the Lead Developer at Aerobridge. Aerobridge is part of a portfolio of open-source projects built and operated by Openskies Aerial Technology Ltd. a company he founded.
- Vibhu Tripathi is the founder of Vizzbee Robotics Solutions Pvt. Ltd. and the community lead at Aerobridge in addition to being Ambassador at PX4, he has been instrumental in organizing and connecting the community to the broader ecosystem.