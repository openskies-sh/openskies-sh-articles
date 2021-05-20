---
title: "Flight Blender + Spotlight: A standards-compliant Remote-ID Display Provider and Application"
date: 2020-11-12T13:16:50+01:00
draft: False
categories: ["air traffic", "remote id",]
tags: ["remote id display application","remote id display provider"]
---

There has been a flurry of activity around standardization of drone operations to support innovation, performance and safety. In this article we will focus on the specific topic of Remote-ID for drones.

<!--more-->

If you already know about Remote-ID, and just want to install a Display Provider and Application just jump to [installation instructions](#deploy-flight-blender).

ASTM's committee on Unmanned Aircraft Systems [F38](https://www.astm.org/industry/unmanned-aircraft-overview.html) has worked on a wide range of un-manned aviation systems (UAS) standardization and has recently released a standard for [Remote ID](https://www.astm.org/Standards/F3411.htm).

UAS Remote Identification (Remote-ID) allows Government and private entities to identify UAS for safety, security and compliance purposes. Remote ID is undertaken securely, preserving privacy and through a series of protocols utilizing different techniques and technologies. Broadly, Remote-ID (RID) is of two types:

- Broadcast RID
- Network RID (Net-RID)

Broadcast RID is emitted directly from the drone via public WiFi Channels, Bluetooth 4.0 and 5.0 and received via widely available equipment including antennas common within most smartphones. Network RID is shared via a TCP/IP network, normally through the operator's software. Since there may be many proximate operators, the orchestration of this network RID is accomplished via a software called [Discovery and Synchronization (DSS)](https://github.com/interuss/dss). The DSS enables communication between operators, authorities and stakeholders. There are provisions for exchanging dynamic restrictions and supplemental data (e.g., weather) etc. within the DSS. Broadcast and Network RIDs have pros and cons but Network RID considered a robust scalable way to identify drones.

### How do you identify drones?

This article we will focuses on the Network RID and how the RID standard addresses displaying Network RID from a end-user point of view. See the image below depicting how a "[Network Remote ID flow](https://github.com/interuss/dss/blob/master/assets/generated/rid_display.png)" works.

![RID Flow image](/images/rid_display.png)

### Display Provider and Display Applications

These are a complicated set of operations, focusing on left hand side of the chart: "Display Application" and "Display Provider". These are the two software applications with which end-users and stakeholders interact. The "Display Provider" is effectively a server that interacts with the DSS and the drone operators or service providers. This "Display Provider" queries the network, picks up the flight feeds, and directs it to a "Display Application". A "Display Application" could be a website or a App for a phone or a tablet installed on the users phone or computer. The standard makes a distinction between "Display Provider" and "Display Application". We have have built a open source resources for both. When used in conjunction, they can be used for RID queries to the network. They are:

- [Flight Spotlight](https://flightspotlight.com) (Display Application)
- [Flight Blender](https://flightblender.com) (Display Provider)

### See it in action

{{< youtube 21YbsUhaDZ0 >}}


### Flight Blender: ASTM-standards compatible Remote ID Display Provider

We already offer a flight feed aggregator called Flight Blender, see the [article](https://www.openskies.sh/articles/live-airtraffic-aggregation/) introducing it. We have recently introduced a "Network Remote-ID module" inside Flight Blender for communication with the DSS and the service providers. These include querying and downloading the data to show it on a "Display Applications" e.g. [Flight Spotlight](https://flightspotlight.com). Consider the system image below.

![Flight Blender Flow](/images/openskies-stack.png)

The current Remote-ID module is compatible with the ASTM standard for network RID and will be updated as the standard progresses. Consequently you need not understand the standard to enable Remote-ID operations, it is simply done for you. Of course as other network based Remote-ID standards appear, we will build support for them as well within Flight Blender as additional modules.

### Deploy Flight Blender

If you have the capability, you can install using the straight forward [installation instructions](https://github.com/openskies-sh/flight-blender#installation) using Docker. You have the choice to host it on your own infrastructure or we can host a instance for you to enable network RID capability. We can help with installation and customization as necessary, taking into account the security and other specific requirements your organization may have.