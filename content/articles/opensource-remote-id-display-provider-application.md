---
title: "An open-source standards compliant Remote-ID Display Provider and Application"
date: 2020-11-12T13:16:50+01:00
draft: False
categories: ["air traffic", "remote id",]
tags: ["remote id display application","remote id display provider"]
---

There has been a flurry of activity around standardization of drone operations to support innovation, performance and safety. In this article we will focus on the specific topic of Remote ID for drones. 

<!--more-->

ASTM has taken a lead in some of the standard making activities as a part of [The Committee on Unmanned Aircraft Systems (F38)](https://www.astm.org/industry/unmanned-aircraft-overview.html). While the committee is broadly focused on a wide range of aspects of un-manned aviation, from a UTM / U-Space point of view they have recently released a standard for [Remote ID](https://www.astm.org/Standards/F3411.htm).

There are a lot of details about Remote ID but to put it in a concise way, Remote Identification (Remote ID) of unmanned aircrafts allows Government and Civil bodies to identify UAS for safety, security and compliance purposes. This identification is done securely, preserving privacy and through a series of steps utilizing different technologies. Broadly Remote ID is of two types:

- Broadcast Remote ID
- Network Remote ID (Net-RID)

Broadcast remote is emitted directly from the drone via public WiFi Channels, Bluetooth 4.0 and 5.0 and received using a range of equipment including specialized antennas common smartphones. Network Remote ID is shared via a TCP/IP network, normally via the operator of the drone. Since there may be many operators in a airspace, the orchestration of this network Remote ID done by a piece of software called Discovery and Synchronization [DSS](https://github.com/interuss/dss). The DSS enables communication between different operators, authorities and stakeholders. There are provisions for exchanging dynamic restrictions, supplemental data (e.g. weather) etc. as well. Broadcast and Network remote IDs have their pros and cons but network Remote-ID considered a robust scalable way to identify drones.

### How do you identify drones?

Remote ID is a deep topic but in this article we will focus on the Network Remote ID and the how the standard deals with displaying Network Remote ID. See the sample flow of how a "[Network Remote ID flow](https://github.com/interuss/dss/blob/master/assets/generated/rid_display.png)" works.

![RID Flow image](/images/rid_display.png)

### Display Provider and Display Applications

These are a complicated set of operations, we will focus on left hand side of the chart: "Display Application" and "Display Provider", these are the two software that users will interact with. The "Display Provider" is basically a server that interacts with the DSS and the operators or the service provider. This display provider actually queries the network and picks up the flight feeds and direct it to a "Display Application" which could be a website or a App or any screen really. The standard makes a distinction between "Display Provider" and "Display Application" and we have now built a open source provider that can be used to Remote ID queries to the network.

### Flight Blender: ASTM-standards compatible Remote ID operations

We already have a flight feed aggregator called Flight Blender, you can read the related [article](https://www.openskies.sh/articles/live-airtraffic-aggregation/) introducing it. We have now developed a "DSS module" inside Flight Blender. This module does the communication with the DSS and processes the queries to show it on Display Applications e.g. [Flight Spotlight](https://flightspotlight.com). Take a look at the system image below.

![Flight Blender Flow](/images/blender-public.png)

The Remote-ID module at the moment is compatible with the released ASTM standard for network Remote ID, so that you don't have to understand the standard to enable Remote-ID operations, it is done for you. 

### Get Remote-ID capability

You can install this using the [installation instructions](https://github.com/openskies-sh/flight-blender#installation) and host it on your own infrastructure or we can host a instance for you to enable network Remote-ID capability. We can help with installation and customization as necessary, taking into account the security considerations and other specific needs that your organization may have. 