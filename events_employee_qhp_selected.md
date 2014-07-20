---
layout: default
title: Events/Employee QHP Selected
---# Resource: Employer: Event: Employee Qualifying Health Plan (QHP) Selected

## Event Name
employee_qhp_plan_selected

## Purpose
The event notifies subscribers and listeners that an employee has selected a QHP in the HBX.

## Trigger
Event is published by the HBX client (to the HBX) and subsequently by the HBX when an employee has selected a QHP in the HBX.

## Request Elements
The event request must contain at least the following request elements:

| Request Element	| Description |
| ----------------- | ----------- |
| employer_id	| Employer id associated with the employee who selected the QHP. |
| employer_uri	| The URI to access the specific employer associated with this employee QHP selection. |
| employee_id	| Employee id associated with the employee who selected the QHP. |
| employee_uri	| The URI to access the employee who selected the QHP. |
| plan_id	| The QHP plan id of the plan the employee selected. |
| plan_uri	| The URI to access the specific QHP selected. |

## Transport Elements

| Protocol	 | Elements as |
| ---------- | ----------- |
| HTTP	     | GET Parameters, POST Parameters | 
| JMS	     | Message Properties | 
| AMQP	     | Message Headers | 

## Request Payload

    Request Payload

## Response Payload
	
	Response Payload

