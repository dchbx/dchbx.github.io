---
layout: default
title: ACApi Home
---

## Welcome to the Affordable Care Act API ##
Health care exchanges provide an online marketplace where consumers can shop, compare and purchase plans.  Exchanges must orchestrate numerous processes that communicate digital information among internal system components and between external partners, including: consumers, issuers, goverment agencies, financial institutions, developers and others.

The health care industry has long used Electronic Data Interchange (EDI) to transmit information and conduct electronic transactions with partners.  Passage of the Affordable Care Act (ACA) -- accompanied by arrival of public Health Benefit Exchanges (HBXs) -- both realigned and extended these electronic data communication requirements.  The HBXs now function as the system-of-record, collecting and distributing enrollment, plan selection and (sometimes) premium payment information.

In order to meet the business complexity, HBX implementation patterns integration 

 in ways that existing standards were neither scoped nor designed to accomodate.  

The Affordable Care Act Application Programming Interface (ACApi) provides a communication framework and vocabulary standard for operating online health care marketplaces.  


The ACApi's scope includes traditional benefit enrollment and premium billing functions, with ACA healthcare reform-introduced extensions. It covers Individual unassisted Qualified Health Plan (QHP) and Small Business Health Options Program (SHOP) Markets. 

The ACApi:

* Enables a distributed system of record for critical enrollment and premium billing information
* Replaces point-to-point integration of Exchange subsystems with REST data API
* Reduces long-term reliance on specific vendor solutions and reduces switching impact/costs
* Creates benefits of functionality, data synchronization, transformation, auditability and composite UI capability


The ACApi serves as an abstraction layer that allows any component to query any part of the Exchange data model without needing to know the system of record

defined terms and associations -- the Canonical Vocabulary -- provide a model for representing and passing information between 



system components to access and exchange information.  The ACApi is a key element of an event-driven Service-oriented Architecture (SOA) design that enables agencies to rapidly establish and extend cost-effective, online health insurance marketplaces for individuals and small businesses.


## Purpose



Exchange is the system of record.


Avoids 'accidental architecture', an outcome where a system's architecture outcome where rather than a deliberate design, s defined by a series of 

The ACApi 

DCHBX is developing the ACApi to improve the District of Columbia's DCHealthLink system operation and efficiency.  The ACApi organizes knowledge gained and lessons learned during HBX development into a useful form for the benefit and reuse of others. 

## Associated Projects
The ACApi part of a set of reusable components that support core functions, promote interoperability, improve performance and help reduce cost of implementing and operating an online health exchange.  ACApi scope includes both Individual and SHOP (Business) exchange marketplaces.  Its components include:

* Canonical Vocabulary
* Interface specifications
* Resource service definitions

## Associated Projects
The ACApi and related projects offer a flexible framework upon which to build health insurance marketplace technology.  The design encourages reuse and extension by applying modern, proven, system development principles:

* Convention over configuration
* Open source tools and systems
* Test-first development
* RESTful Web services

Related projects:

* [GlueDB](https://github.com/dchbx/gluedb): a portal for HBX EDI enrollment operations
* [QHP enrollment](#): a Web application for Individual and SHOP market enrollment
* [ACApi](#): this project
* [HBX transport](https://github.com/dchbx/hbx_transport): transport layer for passing ACApi messages between HBX services

## Contributors
The ACApi is sponsored by the District of Columbia Health Benefit Exchange (DCHBX).  Collaboration and contributions from other HBX agencies are welcome.

