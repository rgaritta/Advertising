---
title: DataExclusion Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
description: Defines a data object for DataExclusion.
---
# DataExclusion Data Object - Campaign Management
Defines a data object for DataExclusion.

## Syntax
```xml
<xs:complexType name="DataExclusion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CampaignAssociations" nillable="true" type="tns:ArrayOfCampaignAssociation" />
    <xs:element minOccurs="0" name="CampaignTypeFilter" nillable="true" type="tns:CampaignType" />
    <xs:element minOccurs="0" name="Description" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="DeviceTypeFilter" nillable="true" type="tns:DeviceType" />
    <xs:element minOccurs="0" name="EndDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="xs:dateTime" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [DataExclusion](dataexclusion.md) object has the following elements: [CampaignAssociations](#campaignassociations), [CampaignTypeFilter](#campaigntypefilter), [Description](#description), [DeviceTypeFilter](#devicetypefilter), [EndDate](#enddate), [Id](#id), [Name](#name), [StartDate](#startdate).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaignassociations"></a>CampaignAssociations|Which campaigns to include for the data exclusion.|[CampaignAssociation](campaignassociation.md) array|
|<a name="campaigntypefilter"></a>CampaignTypeFilter|Which campaign types to include for the data exclusion.|[CampaignType](campaigntype.md)|
|<a name="description"></a>Description|A description for the data exclusion.|**string**|
|<a name="devicetypefilter"></a>DeviceTypeFilter|Which devices types to include for the data exclusion.|[DeviceType](devicetype.md)|
|<a name="enddate"></a>EndDate|The end date.|**dateTime**|
|<a name="id"></a>Id|The data exclusion ID.|**long**|
|<a name="name"></a>Name|The data exclusion name.|**string**|
|<a name="startdate"></a>StartDate|The start date.|**dateTime**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddDataExclusions](adddataexclusions.md)  
[GetDataExclusionsByAccountId](getdataexclusionsbyaccountid.md)  
[GetDataExclusionsByIds](getdataexclusionsbyids.md)  
[UpdateDataExclusions](updatedataexclusions.md)  