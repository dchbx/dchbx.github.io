---
layout: default
title: Service Resources
---

The ACApi exposes the following HBX Service Resources.  Each Resource has an associated set of Requests and Events.  Requests are functions or operations that can be called to perform actions on the Resource or to retrieve information about the Resource.  Events are notifications triggered by specific occurrences in the HBX.

Each specific Resource page describes Requests, Events, the basics of crafting a request, and expected response objects.  Resource pages will become accessible as they are defined and made available in the ACApi.

| Resource	| Description |
| --------- | ----------- |
| [Employer](/docs/resources_employer) | Employers are groups that contain Employees and is specific to the HBX domain SHOP or Business marketplace.  Employers offer open enrollment periods for Employees to be able to select Qualifying Health Plans provided through Carriers and Brokers associated with the Employer.  The Employer Resource accounts for Resource Requests and Events associated with the Employee. | 
| [Individual](/docs/resources_individual) | An Individual represents the discrete unit of insured in the HBX.  Individuals enroll, determine eligibility, and select plans outside of the Employer/Employee relationship.  The Individual marketplace is distinct from the SHOP/Business marketplace. | 
| [Policy](/docs/resources_policy) | Policy is a grouping that binds a set of Resources together under a session or key within the HBX. |
| Broker	| Qualifying Health Plan sellers representing Carrier provided plans.  Brokers package, bundle, and sell health and dental plans. | 
| Carrier	| Carriers provide the Qualifying Health Plans offered. | 
| Application Group	|  Application Group ties together the entities in an enrollment process – Employers, Households, Individuals, Policies, etc. | 
| Household	|  Households are groups that contain Individuals.  Generally there is a primary Individual and Individuals associated in various relationships to the primary Individual. | 