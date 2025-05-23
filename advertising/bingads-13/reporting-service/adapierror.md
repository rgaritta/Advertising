---
title: AdApiError Data Object - Reporting
ms.service: bing-ads
ms.subservice: reporting-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a Reporting Ad API error object that contains the details that explain why the service operation failed.
---
# AdApiError Data Object - Reporting
Defines a Reporting Ad API error object that contains the details that explain why the service operation failed.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="AdApiError" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Code" type="xs:int" />
    <xs:element minOccurs="0" name="Detail" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ErrorCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Message" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "Code": IntValueHere,
  "Detail": "ValueHere",
  "ErrorCode": "ValueHere",
  "Message": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [AdApiError](adapierror.md) object has the following elements: [Code](#code), [Detail](#detail), [ErrorCode](#errorcode), [Message](#message).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="code"></a>Code|A numeric error code that identifies the error.|**int**|
|<a name="detail"></a>Detail|A message that contains additional details about the error. This string can be empty.|**string**|
|<a name="errorcode"></a>ErrorCode|A symbolic string constant that identifies the error. For example, *UserIsNotAuthorized*.|**string**|
|<a name="message"></a>Message|A message that describes the error.<br/><br/>For more information about troubleshooting and error handling, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md) and [Operation Error Codes](../guides/operation-error-codes.md).|**string**|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://adapi.microsoft.com  

## Used By
[AdApiFaultDetail](adapifaultdetail.md)  
