---
layout: default
title: "Policy Request by Identifiers"
description: "Retrieve Policy Details by Specified Identifiers"
iteratortitle: "by id"
---
### Request Name
Policy Request

### Purpose
Provide request methods to retrieve Policy information from the HBX

### Request URN
```
	urn:openhbx:requests:v1:policies/<primary_key>, or
	urn:openhbx:requests:v1:policies?enrollment_group_id=<enrollment_group_id>
```

### Message Composition

#### Header (*ServiceHeaderType*)
Header elements are common to requests and responses

| Element | Type | Min..Max | Description |
| ------- | ---- | -------- | ----------- |
| hbx_id              | xs:string   | 1..1 | CMS-assigned Health Benefit Exchange identifier |
| submitted_timestamp | xs:dateTime | 1..1 | UTC date and time when event occurred |
| status              | ServiceStatusType | 1..1 | Service call return status |
| authorization       | xs:string   | 1..1 | Authentication/authorization credentials |
| message_id          | xs:string   | 0..1 | Value that uniquely identifies this message |
| originating_service | xs:anyURI   | 1..1 | The URN of service that posted event |
| reply_to            | xs:anyURI   | 0..1 | Designated the consumer service urn endpoint where to transmit response |
| correlation_id      | xs:string   | 0..1 | Attribute to associate the current message with previous message ID or application-specific message |

#### Request (*PolicyRequestType*)
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| request_name | PolicyRequestNameType | 1..1 | Request type for Policy |
| parameters   | xs:anyURI | 0..1 |  Request parameters |
| metadata     | ServiceMetadataType | 0..1 | Metadata associated with the request
| body         | ServiceBodyType | 0..1 | Optional - PolicyType restriction

### Response (*PolicyResponseType*)
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| metadata     | ServiceMetadataType | 0..1 | Metadata associated with the response
| body         | ServiceBodyType | 0..1 | Optional - PolicyType restriction


### Request
```
By Primary Key:

	urn:openhbx:requests:v1:policies/<primary_key>

By Group Enrollment Id:

	urn:openhbx:requests:v1:policies?enrollment_group_id=<enrollment_group_id>
```

### Response Payload
```
<?xml version="1.0"?>
<n1:policy xsi:schemaLocation="http://openhbx.org/api/terms/1.0 policy.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:n1="http://openhbx.org/api/terms/1.0">
  <n1:broker>
    <n1:npn_id>10419079</n1:npn_id>
    <n1:name>John Doe Broker</n1:name>
    <n1:address>
      <n1:address_type>work</n1:address_type>
      <n1:address_1>123 Any Street</n1:address_1>
      <n1:address_2/>
      <n1:city>Washington</n1:city>
      <n1:state>DC</n1:state>
      <n1:postal_code>22042</n1:postal_code>
      <n1:country_code>US</n1:country_code>
    </n1:address>
    <n1:phone>
      <n1:phone_type>work</n1:phone_type>
      <n1:phone_number>1234567890</n1:phone_number>
      <n1:extension/>
    </n1:phone>
    <n1:email>
      <n1:email_type>work</n1:email_type>
      <n1:email_address>john.doe.broker@xyzcompany.com</n1:email_address>
    </n1:email>
  </n1:broker>
  <n1:website/>
  <n1:hbx_uri/>
  <n1:hbx_id/>
  <n1:enrollees>
    <n1:enrollee>
      <n1:premium_amount>999.99/n1:premium_amount>
      <n1:disabled>false</n1:disabled>
      <n1:benefit_status>active</n1:benefit_status>
      <n1:employment_status>active</n1:employment_status>
      <n1:relationship>self</n1:relationship>
      <n1:carrier_assigned_member_id/>
      <n1:carrier_assigned_policy_id/>
      <n1:coverage_start_date>2014-01-01</n1:coverage_start_date>
      <n1:coverage_end_date/>
      <n1:coverage_status>active</n1:coverage_status>
      <n1:member>
        <n1:gender>urn:dc0:terms:gender#male</n1:gender>
        <n1:dob>YYYYMMDD</n1:dob>
        <n1:ssn>123345678</n1:ssn>
        <n1:tobacco_user>unknown</n1:tobacco_user>
        <n1:language/>
        <n1:hbx_uri/>
        <n1:hbx_id>123456</n1:hbx_id>
        <n1:person>
          <n1:name>
            <n1:name_prefix/>
            <n1:name_first>John</n1:name_first>
            <n1:name_middle/>
            <n1:name_last>Doe</n1:name_last>
            <n1:name_suffix/>
            <n1:name_full>John Doe</n1:name_full>
          </n1:name>
          <n1:job_title/>
          <n1:department/>
          <n1:addresses>
            <n1:address>
              <n1:address_type>home</n1:address_type>
              <n1:address_1>321 Any Street</n1:address_1>
              <n1:address_2/>
              <n1:city>Washington</n1:city>
              <n1:state>DC</n1:state>
              <n1:postal_code>20003</n1:postal_code>
              <n1:country_code>US</n1:country_code>
            </n1:address>
          </n1:addresses>
          <n1:emails>
            <n1:email>
              <n1:email_type>home</n1:email_type>
              <n1:email_address>john.doe@xyz.com</n1:email_address>
            </n1:email>
          </n1:emails>
          <n1:phones>
            <n1:phone>
              <n1:phone_type>home</n1:phone_type>
              <n1:phone_number>1234567890</n1:phone_number>
              <n1:extension/>
            </n1:phone>
          </n1:phones>
        </n1:person>
        <n1:relationship/>
      </n1:member>
    </n1:enrollee>
  </n1:enrollees>
  <n1:premium_amount_total>999.99</n1:premium_amount_total>
  <n1:total_responsible_amount>999.99</n1:total_responsible_amount>
  <n1:total_employer_responsible_amount>0.0</n1:total_employer_responsible_amount>
  <n1:carrier_to_bill>false</n1:carrier_to_bill>
  <n1:plan>
    <n1:hios_plan_id>12345DC1234567-01</n1:hios_plan_id>
    <n1:coverage_type>health</n1:coverage_type>
    <n1:hbx_uri_to_plan/>
    <n1:hbx_id/>
    <n1:csr_policy_amt/>
    <n1:ehb>0.0</n1:ehb>
    <n1:carrier>
      <n1:carrier_name>CarrierNameText</n1:carrier_name>
      <n1:hbx_uri_to_carrier/>
      <n1:hbx_id>123456</n1:hbx_id>
    </n1:carrier>
  </n1:plan>
  <n1:allocated_aptc>0.0</n1:allocated_aptc>
  <n1:elected_aptc_percent>0.0</n1:elected_aptc_percent>
  <n1:applied_aptc>0.0</n1:applied_aptc>
</n1:policy>
```

