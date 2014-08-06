---
layout: default
title: Resources/Individual Request Individual
---
## Request Name
Individual Request

## Purpose
Provide request methods to retrieve Individual information from the HBX

## Request URN
```
	urn:openhbx:requests:v1:people/<primary_key>, or
	urn:openhbx:requests:v1:people?hbx_id=<hbx_id>
```

## Message Composition

### Header (*ServiceHeaderType*)
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

### Request (*IndividualRequestType*)
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| request_name | EmployerRequestNameType | 1..1 | Request type for Individual |
| parameters   | xs:anyURI | 0..1 |  Request parameters |
| metadata     | ServiceMetadataType | 0..1 | Metadata associated with the request
| body         | ServiceBodyType | 0..1 | Optional - IndividualType restriction

### Response (*IndividualResponseType*)
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| metadata     | ServiceMetadataType | 0..1 | Metadata associated with the response
| body         | ServiceBodyType | 0..1 | Optional - IndividualType restriction


## Request
```
By Primary Key:

	urn:openhbx:requests:v1:people/<primary_key>

By HBX ID:

	urn:openhbx:requests:v1:people?hbx_id=123456
```

## Response Payload
```
<?xml version="1.0"?>
<n1:individuals xsi:schemaLocation="http://openhbx.org/api/terms/1.0 individual.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:n1="http://openhbx.org/api/terms/1.0">
  <n1:individual>
    <n1:authority_hbx_member_uri/>
    <n1:authority_hbx_member_id>175141</n1:authority_hbx_member_id>
    <n1:person>
      <n1:name>
        <n1:name_prefix/>
        <n1:name_first>Jane</n1:name_first>
        <n1:name_middle/>
        <n1:name_last>Doe</n1:name_last>
        <n1:name_suffix/>
        <n1:name_full>Jane Doe</n1:name_full>
      </n1:name>
      <n1:job_title/>
      <n1:department/>
      <n1:addresses>
        <n1:address>
          <n1:address_type>home</n1:address_type>
          <n1:address_1>123 Any Street</n1:address_1>
          <n1:address_2/>
          <n1:city>Washington</n1:city>
          <n1:state>DC</n1:state>
          <n1:postal_code>20020</n1:postal_code>
          <n1:country_code>US</n1:country_code>
        </n1:address>
      </n1:addresses>
    </n1:person>
    <n1:member_roles>
       <n1:member_role>
         <n1:gender>urn:dc0:terms:gender#female</n1:gender>
         <n1:dob>YYYYMMDD</n1:dob>
         <n1:ssn>123456789</n1:ssn>
         <n1:tobacco_user>unknown</n1:tobacco_user>
         <n1:language/>
         <n1:hbx_uri/>
         <n1:hbx_id>123456</n1:hbx_id>
         <n1:person>
           <n1:name>
             <n1:name_prefix/>
             <n1:name_first>Jane</n1:name_first>
             <n1:name_middle/>
             <n1:name_last>Doe</n1:name_last>
             <n1:name_suffix/>
             <n1:name_full>Jane Doe</n1:name_full>
           </n1:name>
           <n1:job_title/>
           <n1:department/>
           <n1:addresses>
             <n1:address>
               <n1:address_type>home</n1:address_type>
               <n1:address_1>123 Any Street</n1:address_1>
               <n1:address_2/>
               <n1:city>Washington</n1:city>
               <n1:state>DC</n1:state>
               <n1:postal_code>20020</n1:postal_code>
               <n1:country_code>US</n1:country_code>
             </n1:address>
           </n1:addresses>
         </n1:person>
         <n1:relationship/>
       </n1:member_role>
     </n1:member_roles>
   </n1:individual>
 </n1:individuals>
```

