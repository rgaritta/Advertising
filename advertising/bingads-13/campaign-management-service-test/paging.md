---
title: Paging Data Object Test - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
description: Defines a paging object to request Campaign Management objects in batches.(test)
---
# Paging Data Object Test - Campaign Management
Defines a paging object to request Campaign Management objects in batches.

# [XML](#tab/xml)

```xml
<xs:complexType name="Paging" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="Index" type="xs:int" />
    <xs:element name="Size" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "Index": "ValueHere",
  "Size": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [Paging](paging.md) object has the following elements: [Index](#index), [Size](#size).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="index"></a>Index|The zero-based results page index.<br/><br/>For example to request the first page of results, set this value to 0 (zero).|**int**|
|<a name="size"></a>Size|The page size and the number of results to return in the specified page.<br/><br/>The maximum size is 1,000. If you do not set this element the default size is 0 (zero).|**int**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetExperimentsByIds](getexperimentsbyids.md)  
[GetImportResults](getimportresults.md)  
[GetLabelAssociationsByLabelIds](getlabelassociationsbylabelids.md)  
[GetLabelsByIds](getlabelsbyids.md)  
[GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md)  
[GetVideosByIds](getvideosbyids.md)  