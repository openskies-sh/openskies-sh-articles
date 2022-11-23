---
title: "UTM Service Provider Software verification"
date: 2022-10-20
draft: False
categories: ["open utm", "software verification","certification"]
tags: ["utm", "utmsp","ussp", "ussp certification"]
---

In this article, we will discuss tools for independent, third-party verification of software systems that claim to be conforming to published UTM standards. Specifically, we will see how the opensource automated verification tooling can help with your software certification efforts. TLDR; For practical way to get started, take a look at the [course](https://ussp-verification.openskies.sh) that provides a hands on technical introduction. You can contact us to get started with compliance and verification support via the [OpenUTM](https://utm.openskies.sh) stack.

<!--more-->

## Background
In the EU, starting in January 2023, there is a new law regarding drones and flying drones for e.g. BVLOS in certain airspaces. The Commission Implementing Regulation (EU) [2021/664](https://www.easa.europa.eu/en/regulations/U-space) of 22 April 2021 introduces a regulatory framework for "U-space" airspace. What it means is that EU member states will have to allocate new air-space structures as "U-Space" to enable drone flights within this air-space. In addition, to ensure safety of operations and safe integration of drones in this eco-system, some UTM software services will have to be provided by companies to operate safely. In addition to enabling safe integration of drones, this regulation introduces a number of requirements for Member States around certification of these services. 

## Regulations and U-Space Service Providers (USSPs)
We will discuss some key ideas in the regulation. The Member States will be responsible for designating the geographical zones where the drone operations will be allowed to take place with the support of U-space services. The ‘U-space service providers’ (USSP) are referred to as newly created organisations that are to be certified to provide U-space services, which may be in one or more Member States. Article 14, 15 and 18 of the regulation introduces requirements for certification of USSPs and the responsiblities for the member states. Article 18 specifically mentions the requirement on Member States to establish audit and oversight processes around the services provided by U-Space providers and also mandates that Member States carry out audits, assessments, investigations and inspecations of the Service Providers. 

Drone operators should have non-discriminatory access to all U-space service providers in the Union. They will have to establish a contract with one certified USSP of their choice and request their flight authorisation at least 5 minutes prior to estimated take-off time. 

Air Navigation Service Providers (ANSPs) will continue to remain responsible for the provision of air traffic management (ATM) services to manned aircraft. They will have to establish arrangements with USSP’s to ensure adequate coordination and exchange of information.

### Mandatory amd Optional Services in U-Space
USSPs will have to provide - at least - four mandatory U-space services and below are some of the standards associated with them as well: 
- Geo-Awareness service, see e.g. [ED 269 standard](https://eurocae.net/news/posts/2020/june/ed-269-minimum-operational-performance-standard-for-uas-geo-fencing/)
- Flight Authorization service, see e.g. [ASTM F3548-21](https://www.astm.org/f3548-21.html)
- Network e-Identification service, see eg. [ASTM F3411-22](https://www.astm.org/f3411-22a.html)
- Traffic Information service, there are no standards yet ad integrations must be done with Air Navigation Service Providers (ANSPs) around integrating Traffic in to USSP software
- Weather Information service (optional)
- Conformance Monitoring service (optional)

A company desiring to be a certified USSP must demonstrate that the company's internal systems are compliant against these and other e.g. ISO and Cybersecurity standards. 

### Self-certification of USSPs
As a pre-requisite to formal certification, some Member States might require the USSPs to verify and demonstrate software compliance to the technical standards prior to engaging with the Civil Aviation Authority for certification. This is the first step called as "self-certification" by the USSP. The self-certification will be undertaken by a verification process that can be developed by the USSP and demonstrate software complaince with the standards. Standards around drones are relatively new and they cover data exchange and interoperability between different USSP systems. We have built and developed a fully-opensource "[Open-UTM](https://utm.openskies.sh)" stack that complies with these UTM standards and you use it to deploy services or you can use it to test your systems against a production deployment. All of these should help you with your certification efforts. 

### Opensource Software Verification toolkit
There have been efforts to develop this software verification framework via [InterUSS](https://interuss.org) in the open-source. The InterUSS verification toolkit offers a opensource and peer reviewed way to get UTM systems verified. USSPs, instead of developing / inventing a new self-verification process can adopt a already developed verification process that is fully open-source. In addition, USSPs can utilize fully-opensource tools to "adopt and extend" and develop verification processes for their circumstances. 

### OpenUTM Stack
The [OpenUTM](https://utm.openskies.sh) stack is meant for organizations intending to stand up standards-compatible UTM capability, specifically it is for: 

- For **UTM Program managers** in Government organizations / authorities who want to participate in, verify and understand standards compatible UTM operations of outside companies
- For **software developers** within organizations who want to test and verify data interoperability and standards complaince of their internal systems.

To get a more detailed introduction to the UTM stack, see the [related article]({{< relref "open-utm-with-blender-spotlight.md" >}}).

### Verification by third party
In many cases, in addition to the self-certification, third party verification might be required to ensure ongoing compliance. Openskies via the OpenUTM stack can help your Company with it. As experts in building UTM systems that pass the InterUSS based verification tests, we can help you with compliance and additionally standing UTM services within your company. 

### Conclusion
As opposed to the classic "Build or Buy" decisions that companies have to make the OpenUTM stack presents a innovative strategy of "embrace and extend" where open-source tools can be utilized to achieve the objectives of verification and certification, resulting in savings of cost and time.