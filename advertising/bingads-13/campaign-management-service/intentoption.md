---
title: IntentOption Value Set - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines the possible intent options for location criterion, for example to target people in, searching for, or viewing pages about your targeted location.
---
# IntentOption Value Set - Campaign Management
Defines the possible intent options for location criterion, for example to target people in, searching for, or viewing pages about your targeted location.

> [!NOTE]
> *PeopleSearchingForOrViewingPages* is deprecated as of April 2024. If you try to set *IntentOption* to *PeopleSearchingForOrViewingPages*, it will be set to *PeopleInOrSearchingForOrViewingPages* instead. We will automatically convert existing campaigns with this setting to *PeopleInOrSearchingForOrViewingPages*.

## Syntax
```xml
<xs:simpleType name="IntentOption" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <ActualType Name="short" Namespace="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
    </xs:appinfo>
  </xs:annotation>
  <xs:restriction base="xs:string">
    <xs:enumeration value="PeopleInOrSearchingForOrViewingPages" />
    <xs:enumeration value="PeopleIn" />
    <xs:enumeration value="PeopleSearchingForOrViewingPages" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [IntentOption](intentoption.md) value set has the following values: [PeopleIn](#peoplein), [PeopleInOrSearchingForOrViewingPages](#peopleinorsearchingfororviewingpages), [PeopleSearchingForOrViewingPages](#peoplesearchingfororviewingpages).

|Value|Description|
|-----------|---------------|
|<a name="peoplein"></a>PeopleIn|Show ads to people in your targeted location.|
|<a name="peopleinorsearchingfororviewingpages"></a>PeopleInOrSearchingForOrViewingPages|Show ads to people in, searching for, or viewing pages about your targeted location.|
|<a name="peoplesearchingfororviewingpages"></a>PeopleSearchingForOrViewingPages|*PeopleSearchingForOrViewingPages* is **deprecated** as of April 2024. If you try to set *IntentOption* to *PeopleSearchingForOrViewingPages*, it will be set to *PeopleInOrSearchingForOrViewingPages* instead. We will automatically convert existing campaigns with this setting to *PeopleInOrSearchingForOrViewingPages*.<br/><br/>Show ads to people searching for or viewing pages about your targeted location.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[LocationCondition](locationcondition.md)  
[LocationIntentCriterion](locationintentcriterion.md)  
