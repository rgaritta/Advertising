---
title: AdGroupPerformanceReportFilter Data Object - Reporting
ms.service: bing-ads
ms.subservice: reporting-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines the criteria to use to filter the ad group performance report data.
---
# AdGroupPerformanceReportFilter Data Object - Reporting
Defines the criteria to use to filter the ad group performance report data.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="AdGroupPerformanceReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountStatus" nillable="true" type="tns:AccountStatusReportFilter" />
    <xs:element minOccurs="0" name="AdDistribution" nillable="true" type="tns:AdDistributionReportFilter" />
    <xs:element minOccurs="0" name="CampaignStatus" nillable="true" type="tns:CampaignStatusReportFilter" />
    <xs:element minOccurs="0" name="DeviceOS" nillable="true" type="tns:DeviceOSReportFilter" />
    <xs:element minOccurs="0" name="DeviceType" nillable="true" type="tns:DeviceTypeReportFilter" />
    <xs:element minOccurs="0" name="Language" nillable="true" type="tns:LanguageReportFilter" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:AdGroupStatusReportFilter" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "AccountStatus": "ValueHere",
  "AdDistribution": "ValueHere",
  "CampaignStatus": "ValueHere",
  "DeviceOS": "ValueHere",
  "DeviceType": "ValueHere",
  "Language": "ValueHere",
  "Status": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [AdGroupPerformanceReportFilter](adgroupperformancereportfilter.md) object has the following elements: [AccountStatus](#accountstatus), [AdDistribution](#addistribution), [CampaignStatus](#campaignstatus), [DeviceOS](#deviceos), [DeviceType](#devicetype), [Language](#language), [Status](#status).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountstatus"></a>AccountStatus|The report will include data for only the account status. For example, you can use the filter to include data for only active accounts.<br/><br/>You can specify one or more account statuses.|[AccountStatusReportFilter](accountstatusreportfilter.md)|
|<a name="addistribution"></a>AdDistribution|The report will include data for only the specified distribution medium. For example, you can use the filter to include data for only search ads.<br/><br/>You can specify one or more distribution mediums.|[AdDistributionReportFilter](addistributionreportfilter.md)|
|<a name="campaignstatus"></a>CampaignStatus|The report will include data for only the campaign status. For example, you can use the filter to include data for only active campaigns.<br/><br/>You can specify one or more campaign statuses.|[CampaignStatusReportFilter](campaignstatusreportfilter.md)|
|<a name="deviceos"></a>DeviceOS|The report will include data where the ad is displayed on the specified device operating systems. For example, you may use the filter to include data for only ads displayed on Windows devices.|[DeviceOSReportFilter](deviceosreportfilter.md)|
|<a name="devicetype"></a>DeviceType|The report will include data where the ad is displayed on the specified device types. For example, you may use the filter to include data for only ads displayed on smartphones.<br/><br/>You may specify one or more device types.|[DeviceTypeReportFilter](devicetypereportfilter.md)|
|<a name="language"></a>Language|The report will include data for only websites that used the specified languages.<br/><br/>You can specify one or more languages.|[LanguageReportFilter](languagereportfilter.md)|
|<a name="status"></a>Status|The report will include data for only the specified ad group status values. For example, you can use the filter to include data for only active ad groups.<br/><br/>You can specify one or more status values.|[AdGroupStatusReportFilter](adgroupstatusreportfilter.md)|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[AdGroupPerformanceReportRequest](adgroupperformancereportrequest.md)  
