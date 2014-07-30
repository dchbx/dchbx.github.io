---
layout: default
title: Information Model
---

# Information Model

The Information Model is a representation of HBX data resources and associations.

The Resources provide a logical grouping of the data types.  It is organized by logical HBX Resources.  The model illustrates the concepts and relationships for the data objects – the Resources – in the domain.

![ACApi Information Model](/assets/acapi_information_model.png)

| Resource	| Description |
| --------- | ----------- |
| Application Group	|  Application Group ties together the entities in an enrollment process – Employers, Households, Individuals, Policies, etc. | 
| Broker	| Qualifying Health Plan sellers representing Carrier provided plans.  Brokers package, bundle, and sell health and dental plans. | 
| Carrier	| Carriers provide the Qualifying Health Plans offered in the HBX to Individuals and Employers for their Employees. | 
| EDI Transaction	| Transactions with the Carriers. | 
| EDI Transmission	| Transmissions to and from the Carriers. | 
| Elected plan	| The Qualifying Health Plan ultimately selected. | 
| Eligibility	| Eligibility determines which Qualifying Health Plans and potential assistance for coverage an Individual or Employee is eligible for. | 
| Employer	| Employers are groups that contain Employees.  Employers offer open enrollment periods for Employees to be able to select Qualifying Health Plans through their Employer.  The Employer Resource encapsulates the Employer Resource as a subset. | 
| Enrollee | A Person enrolled with a Policy in the HBX. |
| HBX	| HBX is the identifying information for a specific Health Benefits Exchange. | 
| Household	|  Households are groups that contain Individuals.  Generally there is a primary Individual and Individuals associated in various relationships to the primary Individual. | 
| Individual (Person)	| An Individual is the discrete unit representing the insured within the HBX. | 
| Member	| A Member is a person which is part of an Application Group.  A Member can be an Individual or an Employee from the HBX perspective. | 
| Plan	| A Qualifying Health Plan. | 
| Premium Table	| Maps coverage dates and rates to plans. | 
| Premium Payments	| Premium payments for plans. | 
| Person Relationship	| Person Relationship associates or binds Application Group and Household. | 
| Policy	| Policy is a grouping that binds a set of Resources together under a session or key within the HBX. It represents a Person or Member covered under a Qualifying Health Plan with a start date and a stop date, in other words, for a specific period of time. | 
| SEP	| A Special Enrollment Period (SEP) triggered by a Qualifying Life Event. | 
