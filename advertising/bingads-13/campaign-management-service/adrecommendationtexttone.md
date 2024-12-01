---
title: AdRecommendationTextTone Value Set - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a value set for ad recommendation text tone.
---
# AdRecommendationTextTone Value Set - Campaign Management
Defines a value set for ad recommendation text tone.

## Syntax
```xml
<xs:simpleType name="AdRecommendationTextTone" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Friendly" />
    <xs:enumeration value="Persuasive" />
    <xs:enumeration value="Cute" />
    <xs:enumeration value="Inspiring" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [AdRecommendationTextTone](adrecommendationtexttone.md) value set has the following values: [Cute](#cute), [Friendly](#friendly), [Inspiring](#inspiring), [Persuasive](#persuasive).

|Value|Description|
|-----------|---------------|
|<a name="cute"></a>Cute|Reserved.|
|<a name="friendly"></a>Friendly|Reserved.|
|<a name="inspiring"></a>Inspiring|Reserved.|
|<a name="persuasive"></a>Persuasive|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AdRecommendationTextRefineOperation](adrecommendationtextrefineoperation.md)  
[CreateAssetGroupRecommendation](createassetgrouprecommendation.md)  
[CreateResponsiveAdRecommendation](createresponsiveadrecommendation.md)  
[CreateResponsiveSearchAdRecommendation](createresponsivesearchadrecommendation.md)  
