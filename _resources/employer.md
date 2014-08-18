---
layout: default
title: "Employer Resource"
description: "Employers are groups that contain Employees and is specific to the HBX domain SHOP or Business marketplace.  Employers offer open enrollment periods for Employees to be able to select Qualifying Health Plans provided through Carriers and Brokers associated with the Employer.  The Employer Resource accounts for Resource Requests and Events associated with the Employee."
iteratortitle: "Employer"
---

The Employer Resource supports service requests, responses and events associated with both Employers and Employees.  Employers include business entities who qualify for and participate in the HBX Small Business Health Options Program (SHOP) marketplace. Employers include an Employee roster,  elected set of available Qualifying Health Plans (QHPs), and premium payment history, amoung other resources.  

An Employee is an Individual in the HBX, however they are a special type or class of Individual who is associated with an Employer.  An Employee can review, select, and purchase specific, Qualified Health Plans which are offered by their Employer.  Generally, an Employee will select a Qualifying Health Plan offered by their Employer because the Employer can opt to cover any portion of the Employee health plan.  However, an Employee associated with an Employer can, at their discretion, shop for Individual Qualifying Health Plans and chooses one independent of the Employer.  This Resource description focuses on the Events and Operations specific to the Employer-Employee relationship and the elements associated with Employers, Employees, and Qualifying Health Plans.

### Employer Requests and Events

#### Employer Requests
This table enumerates the Employer Resource Requests:

| Request	 | Description / Provides |
| --------- | ----------- |{% for q in site.resourceemployerreq %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}
| create	| Creates or registers an Employer.  | 
| update	| Updates an Employer.  | 
| delete	| Deletes an Employer.  | 
| terminate	| Terminates an Employee.   | 
| reinstate	| Reinstates an Employee.   | 
| add_broker	| Add a broker associated with the Employer. | 
| remove_broker	| Remove a broker associated with the Employer. | 
| enrollment 	| Provides a list of actively enrolled Employees.   | 
| assign_carrier_group	| Sets the carrier-assigned group id for this Employer. | 
| open_enrollment	| Transition the Employer enrollment status to open. | 
| close_enrollment	| Transition the Employer enrollment status to closed. | 
| initiate_premium_payment	| Start a premium payment transaction. | 
| advance_premium_payment	| Advance coverage period. | 
| reverse_premium_payment	| Debit premium paid balance due to refund, Non-Sufficient Funds (NSF) or other reversal.  | 
| remit_payment	| Remit Employer contribution payment.   | 
| binder_premium_payment_amount_due	| Provide total premium amount due for Employer current payment. | 
| premium_amount_due	| Retrieve Employer premium amount due.   | 
| nfp_employer_premium_payment	| NFP Operation – Retrieve Employer premium payment. | 
| nfp_get_dashboard_data	| NFP Operation – Get Employer dashboard data. | 
| nfp_get_customer_statements	| NFP Operation – Get Employer customer (employee) statements. |

#### Employer Events

This table enumerates the Employer Resource Events:

| Event	| Description /Trigger Mechanism |
| --------------------  | ----------- |
| created	 | Employer registers or is added to the HBX. |
| updated	| Employer updates information to the HBX. |
| deleted	| Employer is deleted from the HBX. |
| terminated	| Employee was terminated by the Employer. |
| reinstated	| Employee was reinstated by the Employer. |
| broker_added	| Employer adds a broker to be associated with them in the HBX. |
| broker_removed	| Employer removes a broker associated with them in the HBX. |
| enrollment_opened	| Employer enrollment opens. |
| enrollment_closed	| Employer enrollment closes. |
| carrier_group_assigned	| Employer assigns a group to a carrier. |
| payment_initiated	| Employer payment contribution is initiated. |
| payment_advanced	| Employer payment is allocated. |
| payment_reversed	| Employer payment contribution is remitted. |

### Employer Employee Requests and Events

#### Employer Employee Requests
This table enumerates the Employer Employee Resource Operations:

| Request	 | Description / Provides |
| ---------  | ---------------------- |
| Base Operation	| Employees – retrieves the list of employees associated with this employer in the HBX.	|
id	| Retrieves Employee details for the Employee specified by the id.	|
create	| Creates or registers an Employee	|
update	| Updates an Employee.	|
delete	| Deletes an Employee.	|
terminate_employment	| Terminates an Employee.	|
effectuate	| Effectuate the plan for the Employee.  Completes and finalizes the plan purchase with the Carrier.	|
start_sep	| Start the special enrollment period for the Employee.	|
end_sep	| End the special enrollment period for the Employee.	|
withdraw_qhp	| Withdraw a QHP from an Employee.	|
select_qhp	| Employee selects a QHP.	|
change_qhp	| Employee changes a QHP.	|
terminate_qhp	| Terminate a QHP for an Employee.	|
cancel_qhp	| Cancel a QHP for an Employee. 	|
reinstate	| Reinstate 	|

#### Employer Employee Events

This table enumerates the Employer Employee Events.

| Event	| Description /Trigger Mechanism |
| --------------------  | ----------- |
| created	| Employee registers or is added to the HBX. | 
| updated	| Employee updates information to the HBX. | 
| deleted	| Employee is deleted from the HBX. | 
| qhp_selected	| Employee has selected a QHP. | 
| qhp_withdrawn	| Employee had a QHP withdrawn. | 
| qhp_effectuated	| Employee has finalized their selected QHP with the Carrier. | 
| qhp_canceled	| Employee had their QHP canceled by their Employer. | 
| qhp_terminated	| Employee QHP terminated – could be several reasons. | 
| sep_started	| Employee Special Enrollment Period started. | 
| sep_ended	| Employee Special Enrollment Period ended. | 
| employment_terminated	| Employee was terminated by the Employer. | 
