---
title: "Open-UTM with Flight Spotlight and Flight Blender"
date: 2022-06-20
draft: False
categories: ["open utm", "remote id","flight authorization", "air traffic"]
tags: ["utm", "remote id display application","flight tracking","aircraft surveillance"]
---

Openskies provides in the open source foundational elements of UTM services and also a roadmap for jurisdictions to graudally enable additional services in a international standards compatible fashion.
<!--more-->

## Introduction
The "Open-UTM" stack provided by Openskies implement published and developing international standards on UTM in a fully open source fashion. These components are described below. These can be extended and incorporated within private companies and stand up UTM services or participate in the UTM eco-system securely. The best part of this system is that these are plug and play modules that can be deployed together or independently as you see fit for the use case. 

![Open UTM roadmap](/images/open-utm.roadmap.png)

### Permissioning and User roles
To access this system, you will need to get an account in the system. You will need to contact your administrators to get an account. Normally you cannot sign up for an account by yourself but will have to be nominated by your administrators. There are broadly three types of access to this system, in many cases there are additional special roles that are: 

1. **Authority**: A person who is a part of Civil Aviation Authority, Police, Military, Air Navigation Service Provider etc. As you would expect these users will have additional authorization features for the system. 
2. **Operator**: A person who is associated with the flight operations and can share flight plans and logs etc. 
3. **Public**: A person who is neither an Authority or Operator but has a general interest in the airspace. 

### Flight Spotlight
Flight Spotlight is the front-end to this system. Flight Spotlight has mainly three entities: 

1. Live Flights: This is a display to see live flights in an area, when configured, live manned air-traffic and / or ASTM compared Network Remote-ID etc. can be provided. Here you can also see geo-fences etc. 

2. Launchpad: Using this form operators can submit flight declarations as GeoJSON into the system. In the background, this is compatible with ASTM standards on USS <-> USS interoperability standards. The GeoJSON once submitted is stored as an ASTM operational intent (Volume4D etc.) and the raw GeoJSON as well. This data is submitted to the Blender backend securely. 

3. Noticeboard: Fight Declarations submitted via the Launchpad interface is seen here, operations can be seen on a table and / or on a map. If you have the appropriate privileges you can authorize operations. At the moment, there is no deconfliction or any other support but these can be added in the future. 

You can see some screenshots and photos, you can navigate [this directory](https://github.com/openskies-sh/flight-spotlight/tree/master/images/screenshots) on Github.

### Flight Blender
Flight Blender is the backend data storage and processing engine for this system. Flight Spotlight communicates with Blender via an <a href="http://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/openskies-sh/flight-blender/master/api/flight-blender-1.0.0-resolved.yaml">elaborate API</a> and in most cases you do will not have to interact with this part. You can check the Blender Connectivity with Spotlight from within Spotlight. 

## Support and Contact 
If you want to get in touch please reach out to your administrators / local contact or contact via the form at [Openskies website](https://about.openskies.sh/#contact), it may take one or two days to get back to you.