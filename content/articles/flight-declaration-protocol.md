---
title: "Developing current and future flight schedule by standardized declaration"
date: 2020-09-11T13:18:20+01:00
draft: false
categories: ["operations", "protocol"]
tags: ["remote id display application","flight tracking","aircraft surveillance"]
---

As the airspace gets busier, flight schedules and the associated geographic information must be shared and transmitted in a standard fashion. At the moment the flight plans are built on customized software or other opensource software. Most of these software have a the functionality to export flight plans as "standard" geo-referenced file e.g. see KML export in [QGroundcontrol](https://docs.qgroundcontrol.com/master/en/PlanView/PlanView.html#file).

Just like KML there are other formats to share geographical information, take a look at some proprietary and open [data formats](https://gisgeography.com/gis-formats/) that can be used to share geographic information. Do they work? Yes, perfectly.. but only if you know some of the specifics and depending on what you are trying to some work better than others.

<!--more-->

When it comes to flight declarations, you are necessarily sharing data about future flights "to interested parties", fortunately the Global Unmanned Traffic Management Association (GUTMA) has developed a [flight declaration protocol](https://github.com/gutma-org/flight-declaration-protocol). In our involvement with GUTMA, we developed backwards-compatible update to the declaration protocol or the "[development version](https://github.com/openskies-sh/flight-declaration-protocol-development)", in this article you will learn the importance of standardizing flight declarations / plans and how the development version of the protocol enables you to build services.  

In this article you will learn about:
    - Importance of standardizing flight declaration data and a analysis of the GUTMA flight declaration protocol
    - Key differences between the agreed protocol and the development version

### Analysis of the GUTMA flight declaration protocol

While the published GUTMA protocol is a great step forward, there are certain deficiencies that we can discuss here. At this time, we would recommend you take a look at sample declarations [here](https://github.com/gutma-org/flight-declaration-protocol/blob/master/FlightDeclarationProtocol.md#772-examples). There are two fundamental issues with this format:

- The `sequence number` is a numeric field that is incremented and software is expected to read the "highest" sequence number as  the current declaration overriding any other previous ones. This puts the onus on the declaring party and also causes issues around deletion e.g. should deleted flights be declared as a new sequence number?
- The `parts` field has a numeric `id` starting with 0 that shows the flight parts and the associated parameters for that part a part can only be `LineString` or `Polygon`
- GeoJSON does not specifically allow volumetric information which is critical for flight path declarations.
  
The `sequence number` and `parts` are the two main things that are different in the development version of the protocol The `parts` field is now a GeoJSON `FeatureCollection` and every feature has a associated property that holds flight information about that part of the fight and the `sequence number` is a UNIX timestamp now which is still a number but this enables temporal processing of flight declarations.

### Integration with Live air-traffic

Using GeoJSON feature collection is a minor change / update over the existing one it enables us to interoperate with KML directly and use other standard tools. Finally using timestamp over numeric sequence numbers enables us to parse the declarations using standard date / time libraries. We use flight declarations in [Flight Spotlight]({{< ref "create-a-live-flight-display.md" >}}). Flight Spotlight is meant for __live__ air-traffic and we show declared flights as a overlay as well. By integrating declared flights with live traffic data, we can build capabilities for authorizations.

### Open issues

A critical open issue is how volumetric information is shared in declarations. If you have ideas / formats about how this can be shared, please reach out!