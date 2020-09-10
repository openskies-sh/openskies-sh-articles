---
title: "Beginners guide to building a live air traffic dashboard"
date: 2020-09-10T13:16:35+01:00
draft: false
categories: ["air traffic", "remote id","applications"]
tags: ["remote id display application","flight tracking","aircraft surveillance"]
---

If you want to track drone and other flights in the sky, then you must be able to connect to the airspace and show flights on a map / display. This can be challenging but dont let that put out off, it is not that complicated.
<!--more-->

Here is everything that you will learn in this guide: 
- Understanding basics of live flight traffic / air traffic data
- Basics of 3D mapping and showing other geo-data e.g. geo-fence, flight declarations
- Deploy / Run a docker based application 
- Understand how live data is streamed

## See it in action     

{{< youtube rXAMIGzZCDA >}}

## Basics of streaming live air traffic data

Drones / aircraft flying can be deteced either by using technologies such as [radars](https://en.wikipedia.org/wiki/Radar), [ADS-B](https://en.wikipedia.org/wiki/Automatic_dependent_surveillance_%E2%80%93_broadcast), however drones are normally tracked using these technologies, in Europe and US there are upcoming regulations for drones to broadcast their position __from the drone__ and / or it can be queried using a network, commonly called as Network / Broadcast Remote ID. Since the airspace is shared and with flights and drones that have different capabilities a combination of the techniques mentioned above need to be deployed. The Broadcast and Network Remote ID constitute the most recent developments for tracking drones and there are mature systems for the older techniques such as radars / ADS-B etc. 

## Basics of 3D mapping / geo-data / geo-fencing

Any flying objects including drones fly in 3D space so we must use a 3D display / technology for mapping and displaying the airspace, in this case we will use the well known open source [Cesium](https://cesiumjs.org) technology. Cesium provides a 3D globe and more importantly enables us to display objects in 3D, not just latitude and longitude but in altitude as well. 

This means that specific zones in the airspace can be defined and depicted as well, see for example EuroCAE's [ED 269](https://eshop.eurocae.net/eurocae-documents-and-reports/ed-269/) specifications. Any volume in the airspace can be depicted in this fashion. And since the traffic and all data is "live" we will have to stream this data. 

## Flight Spotlight and deploying it using Docker 

[Flight Spotlight](https://github.com/openskies-sh/flight-spotlight) is an software application that orchestrates all of these functions. It can be termed as a "Remote ID Display provider" and can be deployed using Docker to any public or private cloud. We will now setup all of this in an single application. This requires some basic programming / server orchestration background but bascially it is delivered using Docker. For a more detailed introduction  you can review the [Installation Guide](https://github.com/openskies-sh/flight-spotlight/blob/master/documents/installation-instructions.md). However since this application is deployed using Docker, all you need to do is install docker and clone the repository using `git clone https://github.com/openskies-sh/flight-spotlight.git` and then `docker-compose up`. This will download all the files and run the application. 

![Flight Spotlight](https://i.imgur.com/6kfx13d.png)

## Understand how data is streamed / API end points 

Once the application is deployed, you can now set the area of interest as in the video, and start sending flight data as a JSON file to the `/set_air_traffic` endpoint. The flight data will be streamed to the front end and in 3D. You can submit a geo-fence using the `/set_geo_fence` endpoint and a flight declaration using the `/set_flight_declaration` endpoint. This can be used to see what is flying in the air in realtime, what has been declared if geo-fences are being crossed. 

## Final thoughts

We now have a working display of flights that can be streamed by using a few docker commands. The next question is how is data going to be aggregated and fed in to the system? We will touch upon this in another article. We have also not touch the security and authentication / identity aspect of this. For the moment the application is protected using standard OAUTH 2.0 technology provided by a OAUTH 2.0 provider like [Flight Passport](https://github.com/openskies-sh/flight-passport/) but this can be customized to any provider of your choice, we help with the customization. This way you can securely connect to the airspace by self hosting a Flight Spotlight instance and display flight data. 