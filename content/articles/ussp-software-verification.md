---
title: "UTM Service Provider (USSP) Software verification"
date: 2022-10-20
draft: False
categories: ["open utm", "software verification","certification"]
tags: ["utm", "utmsp","ussp", "ussp certification"]
---

In this article I will talk about UTM Service providers, the associated regulations in the EU and the toolset available to verify compliance with the UTM standards. TLDR; take a look at the [course](https://ussp-verification.openskies.sh) to get started in your journey or contact us to get started with compliance and verification via the [OpenUTM](https://utm.openskies.sh).
<!--more-->

## Introduction
In the EU, starting in January 2023 there is a new law regarding drones and flying drones e.g. BVLOS in the EU. The Commission Implementing Regulation (EU) [2021/664](https://www.easa.europa.eu/en/regulations/U-space) of 22 April 2021 introduces a regulatory framework for "U-space". What it means is that member states (MS) will have to allocate new air-space structures as "U-Space" to enable drone flights within this air-space. In addition, to ensure safety of operations and safe integrations, some software services will have to be provided by companies to operate safely in the air-space. In addition to enabling safe integration of drones, this regulation introduces a number of requirements for Member States around certification of different entities. 

## U-Space Service Providers
The Member States will be responsible for designating the geographical zones where the drone operations will be allowed to take place with the support of U-space services. The ‘U-space service providers’ (USSP) are referred to as newly created organisations that are to be certified to provide U-space service, which may be in one or more Member States. Article 14, 15 and 18 of the regulation introduces requirements for certification of USSPs and the responsiblities for the member states. Article 18 specifically mentions the requirement on Member States to establish audit and oversight processes around the services provided by U-Space providers and also mandates that Member States carry out audits, assessments, investigations and inspecations of the Service Providers. 

Drone operators should have non-discriminatory access to all U-space service providers in the Union. They will have to establish a contract with one certified USSP of their choice and request their flight authorisation at least 5 minutes prior to estimated take-off time. 

Air Navigation Service Providers (ANSPs) will continue to remain responsible for the provision of air traffic management (ATM) services to manned aircraft. They will have to establish arrangements with USSP’s to ensure adequate coordination and exchange of information.

### Mandatory amd Optional Services
The Member States will be responsible for designating the geographical zones where the drone operations will be allowed to take place with the support of U-space services. The ‘U-space service providers’ (USSP) are referred to as newly created organisations that are to be certified to provide U-space service, which may be in one or more Member States. They will have to provide - at least - four mandatory U-space services, I am linking some relevant services necessary as well: 
- Geo-Awareness, see e.g. [ED 269 standard](https://eurocae.net/news/posts/2020/june/ed-269-minimum-operational-performance-standard-for-uas-geo-fencing/)
- Flight Authorization, see e.g. [ASTM F3548-21](https://www.astm.org/f3548-21.html)
- Network e-Identification, see eg. [ASTM F3411-22](https://www.astm.org/f3411-22a.html)
- Traffic Information, there are no standards yet ad integrations must be done with Air Navigation Service Providers (ANSPs) around integrating Traffic in to USSP software
- Weather Information (optional)
- Conformance Monitoring (optional)

### Self-certification 
As a pre-requisite to formal certification, some Member States might require the USSPs to verify and demonstrate software compliance to the technical standards prior to engaging with the Authorities. This is the first step in "self-certification" by the USSP. The "self-certification" will be undertaken by a verification process that can be developed by the USSP and demonstrate software complaince with the standards. 

### Software Verification
There have been efforts to develop this software verification framework via larger projects such as [InterUSS](https://interuss.org). USSPs instead of developing / inventing a new self-verification process can adopt the verification process that is fully open-source. In addition, USSPs can utilize fully-opensource tools to "adopt and extend" and develop verification processes. 

### Verification by third party
In many cases, in addition to the self-certification, third party verification might be required to ensure ongoing compliance. Openskies via the OpenUTM stack can help your Company with it. As experts in building UTM systems that pass the InterUSS based verification tests, we can help you with compliance and additionally standing UTM services within your company. 

### How can Openskies help? 
The OpenUTM stack and the software verification requirements present opportunities for companies to develop safe and robust software practices. As opposed to the classic "Build or Buy" decisions that companies have to make the OpenUTM stack presents a additional option of "embract and extend" where open-source tools can be utilized to achieve the objectives. 