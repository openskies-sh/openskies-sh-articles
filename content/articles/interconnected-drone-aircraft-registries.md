---
title: "What is a Registry Broker? First steps to enable inter-connected Drone + Aircraft registries"
date: 2020-09-10T13:17:56+01:00
draft: false
categories: [registry, identity, authentication]
tags: ["drone registration", "registry broker", "registry api", "registry sandbox"]
---

A registry broker is a piece of software that connects and exchanges data between different registries. Building upon the registration sandbox we take the next steps into connecting multiple registries to build a federation of registry servers.
<!--more-->

If you are reading this article without any background in drone registration, we recommend you read the [Building a Drone + Aircraft Registry]({{< ref "drone-aircraft-registry-sandbox.md" >}}) article. We are taking that conversation forward.

In this article you will learn:
     - How to connect different drone registries?
     - How to query data in multiple registries?

We anticipate that we will be in a world of multiple registries and these registries need to be able to talk to each other and securely exchange data. In this article you will be introduced to broker to interact with multiple registries. Don't worry if it seems complicated, it really isn't as long as you keep things separated.

{{< youtube x07L-KOBXGw >}}

### Registry Broker

To connect the different registries, we have created and developed a [registry broker](https://github.com/openskies-sh/aircraftregistry-broker). As you can see in the video above, it is a  application that manages the complexity of querying multiple registries. Of course the application has to be configured to point to the registry databases and also there has to be an agreement between different parties operating and running the registries to share and importantly _recognize_ credentials issued by each other.

The broker is modeled upon the EU VAT system where it is assumed that the data in each registry will be independent and stored at different locations, so there is no "central" database what the broker does is just sends queries all the registries in the broker and once one registry returns a reply, it will store that response. This is all done in real-time, once a user submits a query, they get a id of the job that queries these registries, they have to use that id to further query the status.

![brokerimage](https://i.imgur.com/A6b0IWO.jpg)

The main reason such a system works is because the registries in the network agree to use the same API and credential systems. This agreement is a social agreement (not a technical one) and things like contracts and other agreements are necessary. Perhaps this can also be done at a ICAO or other inter-governmental level but as a concept this enables a decentralized search across different registries.

You can access a working version of the broker at [Aircraft Registry Broker](https://aircraftregistry-broker.herokuapp.com/) and see the source code at [Github](https://github.com/openskies-sh/aircraftregistry-broker). We normally recommend that the registry be used in conjunction with the broker so a registry network can be formed.

### Final thoughts

A Registry broker enables you to connect to and query data from multiple registries seamlessly sharing credentials. If you want to enable interoperable registry data a broker is necessary or at the very least you need to be familiar with how to enable a standards conforming software. Need a more technical / in-depth review? Read the [Registry Broker Whitepaper](https://github.com/openskies-sh/aircraftregistry-broker/blob/master/documents/registration-brokerage-specification.md).

If you are ready to take on the challenge of registration and data inter-operability, we can help, reach out to use using the form at the "About Openskies" link.