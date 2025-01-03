---
title: ConversionValueRuleStatus Value Set - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines the conversion value rule status value set.
---
# ConversionValueRuleStatus Value Set - Campaign Management
Defines the conversion value rule status value set.

## Syntax
```xml
<xs:simpleType name="ConversionValueRuleStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Paused">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Deleted">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Invalid">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [ConversionValueRuleStatus](conversionvaluerulestatus.md) value set has the following values: [Active](#active), [Deleted](#deleted), [Invalid](#invalid), [Paused](#paused).

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The rule is active.|
|<a name="deleted"></a>Deleted|The rule is deleted.|
|<a name="invalid"></a>Invalid|The rule is invalid.|
|<a name="paused"></a>Paused|The rule is paused.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[ConversionValueRule](conversionvaluerule.md)  
[UpdateConversionValueRulesStatus](updateconversionvaluerulesstatus.md)  
