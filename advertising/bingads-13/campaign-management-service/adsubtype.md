---
title: AdSubType Value Set - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines the possible ad sub types.
---
# AdSubType Value Set - Campaign Management
Defines the possible ad sub types.

## Syntax
```xml
<xs:simpleType name="AdSubType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Video" />
        <xs:enumeration value="Display" />
        <xs:enumeration value="HTML5">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

The [AdSubType](adsubtype.md) value set has the following values: [Display](#display), [HTML5](#html5), [Video](#video).

|Value|Description|
|-----------|---------------|
|<a name="display"></a>Display|The ad is a display ad.|
|<a name="html5"></a>HTML5|The ad is an HTML5 ad.|
|<a name="video"></a>Video|The ad is a video ad.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[CreateResponsiveAdRecommendation](createresponsiveadrecommendation.md)  
[GetSupportedFonts](getsupportedfonts.md)  
[ResponsiveAd](responsivead.md)  
