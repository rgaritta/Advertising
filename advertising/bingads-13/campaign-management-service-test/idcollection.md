---
title: IdCollection Data Object Test - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
description: Defines an object that contains a list of entity identifiers.(test)
---
# IdCollection Data Object Test - Campaign Management
Defines an object that contains a list of entity identifiers.

# [XML](#tab/xml)

```xml
<xs:complexType name="IdCollection" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element xmlns:q90="http://schemas.datacontract.org/2004/07/System" minOccurs="0" name="Ids" nillable="true" type="q90:ArrayOfNullableOflong" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "Ids": [
    "ValueHere"
  ]
}
```

-----

## <a name="elements"></a>Elements

The [IdCollection](idcollection.md) object has the following elements: [Ids](#ids).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ids"></a>Ids|A list of entity identifiers.|**long** array|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddNegativeKeywordsToEntities](addnegativekeywordstoentities.md)  
[GetCampaignIdsByBidStrategyIds](getcampaignidsbybidstrategyids.md)  
[GetCampaignIdsByBudgetIds](getcampaignidsbybudgetids.md)  