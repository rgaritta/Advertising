---
title: ApiFault Data Object - Customer Management
ms.service: bing-ads
ms.subservice: customer-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a Customer Management API fault detail object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.
---
# ApiFault Data Object - Customer Management
Defines a Customer Management API fault detail object that operations return when web service-specific errors occur, such as when the request message contains incomplete or invalid data.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="ApiFault" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension xmlns:q1="https://adapi.microsoft.com" base="q1:ApplicationFault">
      <xs:sequence>
        <xs:element minOccurs="0" name="OperationErrors" nillable="true" type="tns:ArrayOfOperationError" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "TrackingId": "ValueHere",
  "Type": "ApiFault",
  "OperationErrors": [
    {
      "Code": IntValueHere,
      "Details": "ValueHere",
      "Message": "ValueHere"
    }
  ]
}
```

-----

## <a name="elements"></a>Elements

The [ApiFault](apifault.md) object has the following elements: [OperationErrors](#operationerrors).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="operationerrors"></a>OperationErrors|An array of OperationError objects that contains the reasons that explain why the service operation failed when the error is not related to a specific item in the batch of items.|[OperationError](operationerror.md) array|

The [ApiFault](apifault.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsapplicationfault"></a>Inherited Elements from ApplicationFault
The [ApiFault](apifault.md) object derives from the [ApplicationFault](applicationfault.md) object, and inherits the following elements: [TrackingId](#trackingid). The descriptions below are specific to [ApiFault](apifault.md), and might not apply to other objects that inherit the same elements from the [ApplicationFault](applicationfault.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="trackingid"></a>TrackingId|The identifier of the log entry that contains the details of the API call.|**string**|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13/Exception  

