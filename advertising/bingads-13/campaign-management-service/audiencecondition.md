---
title: AudienceCondition Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a condition to use conversion value rules for specified audiences.
---
# AudienceCondition Data Object - Campaign Management
Defines a condition to use conversion value rules for specified audiences.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="AudienceCondition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Audiences" nillable="true" type="tns:ArrayOfAudienceConditionItem" />
    <xs:element minOccurs="0" name="IsPrimary" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "Audiences": [
    {
      "Id": "LongValueHere",
      "Name": "ValueHere",
      "Type": "ValueHere"
    }
  ],
  "IsPrimary": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [AudienceCondition](audiencecondition.md) object has the following elements: [Audiences](#audiences), [IsPrimary](#isprimary).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|The audiences included in the condition.|[AudienceConditionItem](audienceconditionitem.md) array|
|<a name="isprimary"></a>IsPrimary|Indicates if this is the primary condition. Only 1 primary condition is allowed in a conversion value rule.|**boolean**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[ConversionValueRule](conversionvaluerule.md)  
