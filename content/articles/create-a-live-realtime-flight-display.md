---
title: "Beginners guide to building a live drone / aircraft traffic dashboard"
date: 2020-09-10T13:16:35+01:00
draft: false
categories: ["air traffic", "remote id","applications"]
tags: ["remote id display application","flight tracking","aircraft surveillance"]
---

If you want to track drones or other flights in the sky, then you must be able to connect to the airspace and show flights on a map / display. This can be challenging but don't let that put out off, it is not that complicated.
<!--more-->

Here is everything that you will learn in this guide:

- Understanding basics of live flight traffic / air traffic data
- Basics of 3D mapping and showing other geo-data e.g. geo-fence, flight declarations
- Deploy / Run a docker based application
- Understand how live data is streamed

### See it in action

{{< youtube rXAMIGzZCDA >}}

### Basics of streaming live air traffic data

Drones / aircraft flying can be detected either by using technologies such as [radars](https://en.wikipedia.org/wiki/Radar), [ADS-B](https://en.wikipedia.org/wiki/Automatic_dependent_surveillance_%E2%80%93_broadcast), however drones are normally tracked using these technologies, in Europe and US there are upcoming regulations for drones to broadcast their position __from the drone__ and / or it can be queried using a network, commonly called as Network / Broadcast Remote ID. Since the airspace is shared and with flights and drones that have different capabilities a combination of the techniques mentioned above need to be deployed. The Broadcast and Network Remote ID constitute the most recent developments for tracking drones and there are mature systems for the older techniques such as radars / ADS-B etc. There are free and paid services that you can connect to get flight data, e.g. you can take a look at [Opensky Network](https://opensky-network.org/), a free service that provides live air-traffic information. For drone traffic, you will have to use newer technologies, more on that below.

### Basics of 3D mapping / geo-data / geo-fencing

Any flying objects including drones fly in a 3D space so we must use a 3D display / technology for mapping and displaying the flight paths, normally software like Google Earth can be used. There are other alternatives as well that are open source for e.g. [Cesium](https://cesiumjs.org). Cesium provides a 3D globe and more importantly enables us to display objects in 3D, not just latitude and longitude but in altitude as well. This means that specific zones in the airspace can be defined and displayed, see for example EuroCAE's [ED 269](https://eshop.eurocae.net/eurocae-documents-and-reports/ed-269/) specification which details how certain zones can be displayed.

### Flight Spotlight

At Openskies, we have a developed a software that enables you to deploy this "globe" and see flight data **live**: [Flight Spotlight](https://github.com/openskies-sh/flight-spotlight). You can deploy the globe and connect to any flight traffic feed. I will talk about how to feed flight data in a later post. In drone standards lingo, this software can be termed as a "Remote ID Display Application" and can be deployed using Docker to any public or private cloud.

We will now setup all of this in an single server and application. You can choose if you want to put this securely on internet or have it just for internal use. Deploying this requires basic programming / server orchestration background but this means that you can setup a instance and see live flight data.

For a more detailed introduction  you can review the [Installation Guide](https://github.com/openskies-sh/flight-spotlight/blob/master/documents/installation-instructions.md). If you do not have the resources to install this, we can do this for you on your infrastructure if you have it or we can provision it on popular cloud services as well. 

![Flight Spotlight](https://i.imgur.com/6kfx13d.png)

### How is data streamed into Flight Spotlight

Once the application is deployed, you can now set the area of interest as in the video, and start sending flight data. There is a small customization work required, if you have a air-traffic feed, you can link to that or you can also use modern drone telemetry to feed  this information.

As you can see, once the flight data is submitted, you can see it live on the application. In addition to the live flight streaming data, you can submit two other kinds of data about the airspace:
    - You can submit a 3D geo-fence to see special zones in the airspace. A geofence can be  used to see what is flying in the air in real-time,
    - Additionally you can submit future flights to see what has been declared.

### Installation and Security

There is a detailed [installation guide](https://github.com/openskies-sh/flight-spotlight/blob/master/documents/installation-instructions.md) that details how you can install it on your server, as mentioned earlier, we can install it for you as well. The whole application is secured using standard OAUTH technology, that we have developed that is also opensource: [Flight Passport](https://www.github.com/openskies-sh/flight-passport). You can choose to integrate it with your preferred security, identity technology as well.

### Final thoughts

We now have a working display of flights that can be streamed by using a few docker commands. The next question is how is data going to be aggregated and fed in to the system? We will touch upon this in another article, we use [Flight Blender](https://www.github.com/openskies-sh/flight-blender). This way you can securely connect to the airspace by self hosting a Flight Spotlight instance and display flight data.