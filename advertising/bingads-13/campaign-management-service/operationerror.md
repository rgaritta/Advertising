---
title: OperationError Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a Campaign Management operation error that contains the details that explain why the service operation failed.
---
# OperationError Data Object - Campaign Management
Defines a Campaign Management operation error that contains the details that explain why the service operation failed.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="OperationError" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Code" type="xs:int" />
    <xs:element minOccurs="0" name="Details" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ErrorCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Message" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "Code": IntValueHere,
  "Details": "ValueHere",
  "ErrorCode": "ValueHere",
  "Message": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [OperationError](operationerror.md) object has the following elements: [Code](#code), [Details](#details), [ErrorCode](#errorcode), [Message](#message).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="code"></a>Code|A numeric error code that identifies the error.|**int**|
|<a name="details"></a>Details|A message that provides additional details about the error. This string can be empty.|**string**|
|<a name="errorcode"></a>ErrorCode|A symbolic string constant that identifies the error. For example, UserIsNotAuthorized.|**string**|
|<a name="message"></a>Message|A message that describes the error.<br/><br/>For more information about troubleshooting and error handling, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md) and [Operation Error Codes](../guides/operation-error-codes.md).|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AdRecommendationMediaRefineResult](adrecommendationmediarefineresult.md)  
[AdRecommendationTextRefineResult](adrecommendationtextrefineresult.md)  
[ApiFaultDetail](apifaultdetail.md)  
[EditorialApiFaultDetail](editorialapifaultdetail.md)  
[HealthCheckError](healthcheckerror.md)  
