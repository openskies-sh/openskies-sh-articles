---
title: "Aerobridge Server: Fleet Management and Trusted Flight"
date: 2021-01-07
draft: false
categories: ["aerobridge","supply chain", "drone assembly"]
tags: ["Management Server","Operations"]
---

Aerobridge is a advanced management server for drone assemblers and service providers. Deploying this server in your company will help you with tracking and documenting parts / component assemblies and different flight events. For advanced users, it provides a security layer via Trusted Flight infrastructure, we explore the assembly tools in this article.
<!--more-->

### Introduction

Now-a-days, building a basic drone is not that difficult or complicated, in addition, commercial-off-the-shelf drones are also readily avaialble and relatively easy to procure. While this is great and desirable, this ease of assembly and procurement brings about a new set of challenges around managing the fleet, maintaining parts and understanding the flight operations. This is because a vast majority of flight operations and assembly are either carried out by hand / papers or are never recorded systematically. 

### Fleet Management

Aerobridge is a state-of-the art drone operations Management Server that is ideally suited for companies operating / manufacturing or assembly of drones. What makes Aerobridge interesting as a management server is that it can be flexibly configured depending on the entity using it: as a manufacturer, assembler or an operator of drones. 

The management server helps the comapny maintain a list of equipment, people and companies operating the drones and connect to external systems e.g. UTM, regulators etc. There are two main aspects of Aerobridge: 
- Fleet and Components management and 
- Trusted Flight

Trusted Flight adds a security layer for your fleet, in this article we will talk about the components and fleet management features, for more details about this, please read the [Aerobridge Trusted Flight]({{< ref "aerobridge-trusted-flight.md" >}}) article. 

### Event Management Module
Aerobridge is meant for drone operators and drone service providers and with the goal of enabling digital support for flight operations management. Drone Operators and Service providers can setup their fleet regardless of if they are building drones or buying commercially off-the-shelf ones. Additionally, Aerobridge has the ability to understand your suppliers and supply chain. Once your fleet is setup via our setup wizard, you can then develop deep insights on how your fleet is performing as you conduct new operations. Aerbridge understands your drone assembly and can link to 3D models of your aircraft if avaialble.

|![Events Management](/images/supply_chain/assembly_details.jpg)|
|:--:|
|<b>Figure 1: Aircraft Assembly in 3D</b>|

Aerobridge is compatible with your fleet and models, it understands your Bill of Materials and you can use Aerobridge to track any kind of components or events. You can add any number of models and you can decide what kind of events you want to track across your fleet. Some example events can be: 
 - Reporting Damaged Parts,
 - Battery Status
 - Insurance Claimed
 - Dysfunctional part

|![Assembly Visualization](/images/supply_chain/events_calendar.jpg)|
|:--:|
|<b>Figure 2: Aircraft Events Calendar</b>|
As these events happen, Aerobridge will allow you log and record them and in turn generate deep insights into your operations via the Calendar view (above) and analytics. 

### Supply Chain Transparency

For a small company, running a world class assembly / production is hard. In the drone context, it is even harder because the components are small and relatively cheaper to procure or build. In most cases, if a part is broken or needs to be replaced the manufacturer or the operator just buys a new one and attaches it to the drone. This makes tracking of parts in the company difficult especially in day-to-day operations.

Consumers and regulators want to know more about the products and the sourcing of the products that they are using. This is a very difficult challenge to address and delivery a solution. In recent years, a lot of work has been done in the agriculture sector around introduction of modern technologies for storing parts and ensuring external parties can authenticate ownership and traceability. Ensuring traceability bring numerous benefits to the manufacturer / assembler of the drone:

1. It builds trust in the brand
2. It provides a way to build operational performance
3. It provides a way to have external parties including customers to be part of the process of manufacturing

__Traceability vs Transparency__: A common distinction that needs to be made between transparency and tracking of parts. Tracking / traceability is a much more difficult problem to solve given the complications of tracking parts and spares as they move through the custody chain. Transparency is simpler to achieve in a modern software context therefore we begin with Transparency first while we tackle the harder issue of traceability later.

|![Authentic Component Network](/images/supply_chain/component_history.png)|
|:--:|
|<b>Figure 3: Aircraft Component History in Aerobridge</b>|

### Authentic components network

By building a public queryable ledger, we can build a network of components that can be verified via modern tracking technologies such as RFID etc. 

|![Supplier Proucrement](/images/supply_chain/procurement_origin.jpg)|
|:--:|
|<b>Figure 4: Where was the component procured from?</b>|

By enabling a datastructures for verified components and a system of verification of the origin, we are budiling a network of verified suppliers and components with radical transparency utilizing modern technologies. 

|![Authentic Component Network](/images/supply_chain/authentic_component_network.png)|
|:--:|
|<b>Figure 5: Verify Component for authenticity</b>|

### Conclusion

We are buliding a modern supply chain for drone manufacturers and assemblers where trust is baked in to the network utilizing modern de-centralized technologies. When you decide to use Aerobridge, you will automatically join the network and get access to the community.

### Join Aerobridge

You can join the community by filling out the form on [www.aerobridge.io](https://www.aerobridge.io)