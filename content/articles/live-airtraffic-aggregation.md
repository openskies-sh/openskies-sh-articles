---
title: "High performance air-traffic data aggregation and normalization"
date: 2020-09-10T13:16:50+01:00
draft: false
categories: ["air traffic", "remote id",]
tags: ["remote id display application","flight tracking","aircraft surveillance"]
---

There are many methods for detecting and tracking flights and drones in the air. Most airspaces will have a combination of these sensors detecting air-traffic.
<!--more-->

It is important to understand how to store and normalize this data. Since the sensors are tracking the same things in the sky, the reason you will need to do this aggregation and normalization is to build a "single state of things" without duplicates and ensuring that the latest observation is kept. This way the "freshest" location / tracking information can be displayed.

### Multiple sensors and data streams

Aircraft tracking and surveillance is a huge topic and sort of out of scope for this article, to keep things simple, let us assume that we will be using different technologies and methods to sense traffic in the sky. It could be things like [ADS-B](https://en.wikipedia.org/wiki/Automatic_dependent_surveillance_%E2%80%93_broadcast), [FLARM](https://en.wikipedia.org/wiki/FLARM), Broadcast or Network Remote ID for drones or even from secondary data providers. The fundamental issue here is that these data streams are updating at different intervals depending on the technical capability of the processor.

![blender-image](https://i.imgur.com/pswQYsz.png)

The image above depicts this. To develop a real-time picture of the sky, these feeds need to be processed and normalized. Most sensors now a days can emit sensing data very fast even multiple times per second. Eventually data will have to be processed multiple times per second. When data is processed / displayed with lag greater than 100 milliseconds humans can perceive it anything sub 100 milliseconds is perceived as real-time or "live" by humans.

There are fundamental computing and network barriers to have this level of performance and as of 2020 is restricted to research labs, for our article and most drone detection and tracking a 1 sec update is considered acceptable and in some cases even too much.

How does one process multiple flight data feeds? You don't have to start from scratch to invent your own processing engine.

### Flight Blender: Flight data Aggregation and Normalization

To help in processing of raw flight tracking data and normalizing it, we have developed [Flight Blender](https://flightblender.com). The first thing to understand / configure here is how often you want to refresh / normalize the data. We recommend 1 second since as of 2020 it is considered good enough, although every 3 seconds might work as well. Once this is finalized you can set this in the application, run it on the internet or your private network / computer and point your flight data feeds to it. The streams will be processed and normalized and a "live" data stream would be submitted on the other side every X seconds for use in displays and other software. You can install this using the [installation instructions](https://github.com/openskies-sh/flight-blender#installation) or we can help with installation and customization as necessary.

### Final thoughts

Realtime data and handling it can be very tricky and offers a new opportunities to aviation in the context of UTM / U-Space. Data normalization can be quite complicated and the trick is not reinvent the wheel and use existing well proven techniques to your advantage. In the case of Flight Blender, we are using the high performance [Redis Streams](https://redis.io/topics/streams-intro) to do the heavy lifting. For the technically oriented, Redis backend can be switched to more robust offerings like [Apache Kafka](https://kafka.apache.org/) etc.
