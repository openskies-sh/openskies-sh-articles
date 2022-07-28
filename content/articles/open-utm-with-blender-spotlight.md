---
title: "Open-UTM with Flight Spotlight and Flight Blender"
date: 2022-06-20
draft: False
categories: ["open utm", "remote id","flight authorization", "air traffic"]
tags: ["utm", "remote id service provider","flight tracking","aircraft surveillance","interuss"]
---

Openskies provides foundational elements of a federated UTM services and also a roadmap for jurisdictions to graudally enable additional services and service providers in a international standards compatible fashion.
<!--more-->

## Introduction
The "Open-UTM" stack provided is by Openskies via products such as [Flight Blender](https://flightblender.com) (backend) and [Flight Spotlight](https://flightspotlight.com) (frontend). These tools implement the published and developing international standards on UTM in code. These robust and well-tested products can be extended and customized to your particular needs as necessary and enable setting up of UTM services by government entities or private companies securely and enable these to participate in a standards-compliant federated UTM eco-system. The best part of this stack is that these are plug and play components that can be deployed together or independently as you see fit for the use case. UTM is a complex piece of software and it is recommended that UTM capability be gradually developed and integrated. A roadmap for the gradual deployment of this capacity for a private company or a national authority is detailed below. 

![Open UTM roadmap](/images/open-utm.roadmap.png)

The roadmap provides for a phased approach to ramp up UTM capabilities eventually participating a federated UTM network where multiple providers can inter-operate in a standards compliant software. This system is therefore compliant with the ASTM standards and the [InterUSS](https://interuss.org) software. 

### Permissioning and User roles
The Blender and Spotlight stack implements a modern authorization and authentication stack. To access this system, you will need to get an account in the system in an OIDC compliant software, in this case we use the [Flight Passport](https://id.openskies.sh) software. Once the system is configured, you will need to contact your administrators to get an account. Normally you cannot sign up for an account by yourself but will have to be nominated by your administrators to get setup. In addition to an account you will also get access to a credentials site where other credentials for automatic API access etc. are provided for machine-to-machine transactions. For people / individuals, there are broadly three types of access to this system, in many cases there are additional special roles that are: 

1. **Authority**: A person who is a part of Civil Aviation Authority, Police, Military, Air Navigation Service Provider etc. As you would expect these users will have additional authorization features for the system. 
2. **Operator**: A person who is associated with the flight operations and can share flight plans and logs etc. 
3. **Public**: A person who is neither an Authority or Operator but has a general interest in the airspace. 

### Flight Spotlight
[Flight Spotlight](https://flightspotlight.com) is the front-end to this system. Flight Spotlight has mainly three pages to use: 

1. Live Flights: This is a display to see live flights in an area, when configured, live manned air-traffic and / or ASTM compared Network Remote-ID etc. can be provided. Here you can also see geo-fences etc. 

2. Launchpad: Using this form operators can submit flight declarations as GeoJSON into the system. In the background, this is compatible with ASTM standards on USS <-> USS interoperability standards. The GeoJSON once submitted is stored as an ASTM operational intent (Volume4D etc.) and the raw GeoJSON as well. This data is submitted to the Blender backend securely. 

3. Noticeboard: Fight Declarations submitted via the Launchpad interface is seen here, operations can be seen on a table and / or on a map. If you have the appropriate privileges you can authorize operations. At the moment, there is no deconfliction or any other support but these can be added in the future. 

You can see some screenshots and photos, you can navigate [this directory](https://github.com/openskies-sh/flight-spotlight/tree/master/images/screenshots) on Github.

### Flight Blender
[Flight Blender](https://flightblender.com) is the backend data storage and processing engine for this Open-UTM system. Flight Spotlight communicates with Blender via an extensive and <a href="http://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/openskies-sh/flight-blender/master/api/flight-blender-1.0.0-resolved.yaml">elaborate API</a>. You can review the API to understand the kind of data that is processed and utilized in the software. In most cases you do will not have to interact with Flight Blender but technical teams within your organization can use the API to build extensions and addons on top of Blender. Iin some cases, you might encounter slowness in Blender and the interaction from Spotlight. This can be for a number of reasons but conceptually these are two different software talking to you each other in a private network. You can check the Blender Connectivity with Spotlight from within Spotlight user interface as well.. 

## Support and Contact 
If you want to get in touch or have queries regarding the software and how you can deploy it in your company, please reach out to your administrators / local contact or contact via the form at [Openskies website](https://about.openskies.sh/#contact), it may take one or two days to get back to you.

## Frequently Asked Questions (FAQ)
A list of frequently asked questions are below, these are updated from time to time. 

**Q: I use this system on the phone, are there apps that I can install to draw a GeoJSON (and declare my flights)?**

A: The Open-UTM system works as expected on a phone / mobile device. The website should open and launch just as you would on a desktop. Flight plans are entered as GeoJSON and there are free and paid apps that are available to help you draw GeoJSON on a mobile device. You can draw your flight path with using these apps. Both have a "Export" function that is free which will allow you to save the file as GeoJSON. The 

__iOS__

- [Maps To-Do](https://apps.apple.com/ie/app/maps-to-do/id1553502403)
- [QPad Geo Collector](https://apps.apple.com/ie/app/qpad-geo-collector/id1533262307)

__Android__
- TBC

Know of an app that can be added to the list? Tell your administrators or us via our [support form](https://about.openskies.sh/#contact)