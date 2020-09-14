---
title: "Building a digital Drone + Aircraft registration sandbox / Bringing your registration data online"
date: 2020-09-10T13:17:48+01:00
draft: false
categories: [registry, identity, authentication]
tags: ["drone registration", "registry API", "registry sandbox"]
---

Over the past few years, we have done a large amount of work the topic of registration of drones. Registration of drones is a fundamental pillar of UTM / U-Space. In this article, you will be introduced to a registry sandbox that you can deploy for your projects. Registration of drones is a vast topic and in this article you will be introduced to a digital sandbox and practical tools to enable the registration function for your software stack.

<!--more-->
If you are new to registration, you are at the right place, here is everything that you will be introduced to in this article:

- What elements need to be registered?
- Backend and Front end of the registry system
- Registry API
- Securing the registration system

The system introduced here comes with a frontend, a backend a API that can be individually deployed depending on your needs and enables you to securely store and query information about aircraft, operators and people.

Registering drones is similar to registering aircrafts or other vehicles e.g. cars in many ways, however it is significantly different in that given the digital airspace the data has to be "live" and brought online to be queried in real time. Registration as a topic has been tackled at various levels including at ICAO and also at national level as well. However, most of the efforts are not public and / or are not easily accessible in a way that enables testing, integration etc. This work which started at GUTMA, was undertaken to build digital interoperable registry sandbox that can be deployed easily and evolve as the needs evolve. The code referenced here is a fork from the GUTMA code and the original authors continue to maintain and support.

{{< youtube 6tjoeOzJ8EY >}}

### What should be registered?

In most cases, managing registration is the domain of the national civil aviation agency or other authorities or sometime delegated to local authorities. For a comprehensive introduction, you can review the [Registration White Paper](https://github.com/openskies-sh/aircraftregistry/blob/master/documents/registration-white-paper.md). What is important to understand is that we will live in a world with multiple registries at a national or sub-national level that need to interconnect / share data securely. In many cases there is a need to stand a drone registry in case of a emergency or special operations around rescue, fire etc. Conceptually, in a registry, there are only three things need to be registered:

- _Operator_: Operators are generally entities or companies that own drones / aircraft and also have associated legal contacts and pilots. One operator can own number of drones, have number of pilots but normally have a distinct identifier such as a company ID etc.  

- _Equipment_: These are normally aircrafts or drones. One operator may have number of drones associated with them. There are numerous drones of different make and model. In addition there may be a need to register fixed wing aircraft as well.

- _People_: Finally any registration system should be able to register data about people and identity. In many jurisdictions it is covered under GDPR and requires additional precautions. What is important to understand is that all registries necessarily will have personal information in them, including things like ID number, training history etc.

Registration data is not "static" it is a living database that needs to be updated and maintained, to develop a conceptual understanding of this, review the landscape document above. One point to note here is that normally getting data into a registry has to be a function of "competent authorities" and processes need to be developed for controlling how this data will be entered. The next section details how data in the registries can be "brought online" securely.

### Registry API

Once data is entered in to a registry, in the context of drones (especially), the ability to "bring it online" and make it queryable is critical to be able to develop a API specification so that data in the registry can be queried in a standardized fashion. Most of the time though when building these type of public facing systems, you want "read-only" access to the registration data since you really don't want to enable writing into the registry from outside networks. You can see the [API Specification](https://aircraftregistry.herokuapp.com/api/v1) that has been developed. Just by looking at it you can understand the data structures: Getting operator, equipment and personal data using GET endpoints.

### Security and levels of privilege

Of course not all data in the registry should be available to everyone, the amount and kind of data access should depend on the person / entity accessing it. E.g. law enforcement etc. should have special, un-throttled access to the data. For this a detailed Information Security Assessment needs to be performed and appropriate credentials and scopes have to be developed. For a comprehensive understanding of this aspect and how the API endpoints are protected you can review the [Identity and Authentication](https://github.com/openskies-sh/aircraftregistry/blob/master/documents/registration-identity-authentication.md) for registry white paper.

### Backend and Frontend and Testing

![Registry flow](https://i.imgur.com/noCPlUf.png)

The registration sandbox comes with a front end and a backend system, they are independent, the front can be customized or new ones can be developed. At the moment, [Frontend](https://airegister.herokuapp.com) is a ReactJS based app that is also [open source](github.com/openskies-sh/aircraft-registry-spa). The video above shows how to login to the frontend and then query the backend for the data. All of this can be customized as necessary and also a series of tests around load have also been developed to simulate [real-world load](https://github.com/openskies-sh/aircraftregistry/blob/master/documents/comprehensive-registry-testing.md). 

### Final words

The registration sandbox shown above has been developed and deployed over a number of years of work. The goal is to provide a blueprint / reference implementation that is compatible with ICAO work and the needs of the drone eco system. As experts in registration can help you in deploying a instance and getting started with true integration. Registration is a vast and complex topic but these tools help you in deploying a secure local instance of the registry customized for your needs. I hope that this gives a good understanding of the open source registry system.