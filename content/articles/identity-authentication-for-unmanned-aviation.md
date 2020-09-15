---
title: "First steps in Identity and Authentication for Unmanned Aviation"
date: 2020-09-10T13:17:14+01:00
draft: false
categories: [identity, authentication]
tags: ["token", "oauth", "cybersecurity"]
---

Drones and unmanned vehicles present new challenges to identity, authentication and most importantly cyber-security. Given the dynamic nature of the industry, the space continuously evolves so it can be hard to keep up. In this article you will be introduced to some basic things regarding authentication and also around options that you have to enable authentication technologies that are compatible with ASTM standards.

Identity and Authentication is a critical component of the drone / unmanned aviation ecosystem. You need to understand the basics of enabling this, once you do you will be able to automate to a large extent the orchestration of identity among the different stakeholders in the ecosystem: law enforcement, USS Service providers, remote id display providers etc.

<!--more-->

In this article you will learn about:

- The current consensus in one or two standard bodies on the method of Identity and Authentication
- The problems with "commercial" and "opensource" systems since they are not purpose built for UTM / U-Space
- About Flight Passport, a open source Identity and Authentication provider specifically built for UTM / U-Space
- Some concerns on using OAUTH and JWT tokens in drones / unmanned aviation

### Internet standards for unmanned aviation: OAUTH

Currently there are many standardization efforts ongoing around the world, most notably in ASTM, EuroCAE. The [remote ID standard](https://www.astm.org/Standards/F3411.htm) that has been developed and released advocates the use of OAUTH and JWT Tokens for sharing identity and authentication information. OAuth is a open standard for access delegation used in the Internet as way to authenticate users, grant permission on websites without giving password, it is commonly used in many commercial service providers like Google, Facebook etc.

The fundamental concept that you need to understand is that OAUTH provides "secure delegated access" (source: [Wikipedia](https://en.wikipedia.org/wiki/OAuth#OAuth_2.0)) to resources on behalf of the resource owner. What does secure delegated access mean? Quite simply you are developing a system to accept identity and other information issued by a different service and based on the data allow access to resources on your server. This is how "Login with Facebook" works: You let the user login using Facebook and you accept that once they login successfully, you accept the credentials and other details provided by Facebook, although you never access the user's email or password etc. This is of course a simplistic way to put it but the concept is the same.

Technically, OAUTH can be difficult to understand, if you really want to get a good introduction, it is a bit more detailed and technical I would recommend that you watch this video [OAUTH 2.0 and OpenID Connect (in plain English)](https://www.youtube.com/watch?v=996OiexHze0).

This technique of "secure delegated access" has been proposed in the standards developed by ASTM, we will not get into if it is the most appropriate one, it is the one that there is a consensus that it can be useful to solve the issues we face today. For a more detail / in-depth understanding of JWTs you can review the [Hard parts of JWT](https://www.pingidentity.com/en/company/blog/posts/2019/jwt-security-nobody-talks-about.html).

In the ASTM context, with you use a software like [InterUSS](https://www.interuss.org), you must use A JWT or JSON Web Token. If you look at the [standard API](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/uastech/standards/astm_rid_1.0/remoteid/canonical.yaml) looks like the following:

``` json
{
  "exp": 1575944837,
  "nbf": 1575926837,
  "iat": 1575926837,
  "iss": "https://example.com",
  "aud": "intended-recipient.example.com",
  "sub": "example-uss",
  "typ": "Bearer",
  "scope": "dss.read.identification_service_areas"
}
```

By using a Token with the information above, you can access resources in the eco-system. The question is how do you issue tokens? How do you identify who gets to make the requests for tokens.

### Problems with existing providers

The good news is that OAUTH 2.0 and the associated OpenID standard are open standards and there a number of commercial and open source solutions available. Broadly I would classify them as:

- Big Cloud: e.g. Amazon AWS Cognito, Microsoft Azure Active Directory, Google Cloud Identity etc.
- Large Players: e.g. Auth0, OKTA etc. 
- Opensource / self-host: e.g. Key Cloak, ORY Hydra, Gluu Server etc. You can look at a more comprehensive list on the [OAUTH website](https://oauth.net/code/)

The are a number of issues with these solutions:

- National Entities may or may not be interested in using private commercial companies for authentication and identity. Since this can be / is a national function, they would prefer to host the platform locally.
- OAuth / OpenID / Open ID Connect stack are a “general purpose” authentication and identity standard and the commercial solutions available price it very differently. Some charge by number of users, some charge by number of tokens / clients etc. All of this is not really suitable for UTM / U-Space operations.
- The Remote ID standard and demos use the `sub` and `aud` claim in a specific way that a number of commercial solutions do not support out-of-the-box. e.g. Azure does not support “scope” in Client Credentials grant, this is required per the Remote ID standard.
- On the open source side, a number of them are not totally ready or have very complex installation procedures or have too many features that make it bulky: e.g. user management. These make them unsuitable / overkill for the specific use-cases.

### Final thoughts / id.openskies.sh

To overcome all of this, we have developed a open source, easy to use / install OAUTH server. It is designed the address the issues above and specifically developed / customized for UTM / U-Space, it is built on existing Open source projects and maintained and developed by us. You can see a production instance on [https://id.openskies.sh](https://id.openskies.sh). This can be deployed on your infrastructure and is called [Flight Passport](https://www.github.com/openskies-sh/flight_passport), using Flight Passport you can issue tokens, credentials, link to existing identity providers and also your organization's and issue tokens securely and flexibly without limitations mentioned above. We can of course help in installing and securing your own instance as necessary.
