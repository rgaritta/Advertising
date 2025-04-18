---
title: AssetGroup Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines an asset group in an advertising campaign.
---
# AssetGroup Data Object - Campaign Management
Defines an asset group in an advertising campaign.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="AssetGroup" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AssetGroupSearchThemes" nillable="true" type="tns:ArrayOfAssetGroupSearchTheme">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
    <xs:element minOccurs="0" name="AssetGroupUrlTargets" nillable="true" type="tns:ArrayOfAssetGroupUrlTarget">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
    <xs:element minOccurs="0" name="BusinessName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="CallToAction" nillable="true" type="tns:CallToAction" />
    <xs:element minOccurs="0" name="Descriptions" nillable="true" type="tns:ArrayOfAssetLink" />
    <xs:element minOccurs="0" name="EditorialStatus" nillable="true" type="tns:AssetGroupEditorialStatus" />
    <xs:element minOccurs="0" name="EndDate" nillable="true" type="tns:Date" />
    <xs:element xmlns:q115="http://schemas.microsoft.com/2003/10/Serialization/Arrays" minOccurs="0" name="FinalMobileUrls" nillable="true" type="q115:ArrayOfstring" />
    <xs:element xmlns:q116="http://schemas.microsoft.com/2003/10/Serialization/Arrays" minOccurs="0" name="FinalUrls" nillable="true" type="q116:ArrayOfstring" />
    <xs:element xmlns:q117="http://schemas.datacontract.org/2004/07/System.Collections.Generic" minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q117:ArrayOfKeyValuePairOfstringstring" />
    <xs:element minOccurs="0" name="Headlines" nillable="true" type="tns:ArrayOfAssetLink" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Images" nillable="true" type="tns:ArrayOfAssetLink" />
    <xs:element minOccurs="0" name="LongHeadlines" nillable="true" type="tns:ArrayOfAssetLink" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Path1" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Path2" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:AssetGroupStatus" />
    <xs:element minOccurs="0" name="Videos" nillable="true" type="tns:ArrayOfAssetLink">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "AssetGroupSearchThemes": [
    {
      "Id": "LongValueHere",
      "SearchTheme": "ValueHere",
      "Status": "ValueHere"
    }
  ],
  "AssetGroupUrlTargets": [
    {
      "Id": "LongValueHere",
      "Status": "ValueHere",
      "TargetCondition1": "ValueHere",
      "TargetCondition2": "ValueHere",
      "TargetCondition3": "ValueHere",
      "TargetConditionOperator1": "ValueHere",
      "TargetConditionOperator2": "ValueHere",
      "TargetConditionOperator3": "ValueHere",
      "TargetValue1": "ValueHere",
      "TargetValue2": "ValueHere",
      "TargetValue3": "ValueHere"
    }
  ],
  "BusinessName": "ValueHere",
  "CallToAction": "ValueHere",
  "Descriptions": [
    {
      "Asset": {
        "Id": "LongValueHere",
        "Name": "ValueHere",
        "Type": "ImageAsset",
        "CropHeight": IntValueHere,
        "CropWidth": IntValueHere,
        "CropX": IntValueHere,
        "CropY": IntValueHere,
        "SubType": "ValueHere",
        "TargetHeight": IntValueHere,
        "TargetWidth": IntValueHere
      },
      "AssetPerformanceLabel": "ValueHere",
      "EditorialStatus": "ValueHere",
      "PinnedField": "ValueHere"
    }
  ],
  "EditorialStatus": "ValueHere",
  "EndDate": {
    "Day": IntValueHere,
    "Month": IntValueHere,
    "Year": IntValueHere
  },
  "FinalMobileUrls": [
    "ValueHere"
  ],
  "FinalUrls": [
    "ValueHere"
  ],
  "ForwardCompatibilityMap": [
    {
      "key": "ValueHere",
      "value": "ValueHere"
    }
  ],
  "Headlines": [
    {
      "Asset": {
        "Id": "LongValueHere",
        "Name": "ValueHere",
        "Type": "ImageAsset",
        "CropHeight": IntValueHere,
        "CropWidth": IntValueHere,
        "CropX": IntValueHere,
        "CropY": IntValueHere,
        "SubType": "ValueHere",
        "TargetHeight": IntValueHere,
        "TargetWidth": IntValueHere
      },
      "AssetPerformanceLabel": "ValueHere",
      "EditorialStatus": "ValueHere",
      "PinnedField": "ValueHere"
    }
  ],
  "Id": "LongValueHere",
  "Images": [
    {
      "Asset": {
        "Id": "LongValueHere",
        "Name": "ValueHere",
        "Type": "ImageAsset",
        "CropHeight": IntValueHere,
        "CropWidth": IntValueHere,
        "CropX": IntValueHere,
        "CropY": IntValueHere,
        "SubType": "ValueHere",
        "TargetHeight": IntValueHere,
        "TargetWidth": IntValueHere
      },
      "AssetPerformanceLabel": "ValueHere",
      "EditorialStatus": "ValueHere",
      "PinnedField": "ValueHere"
    }
  ],
  "LongHeadlines": [
    {
      "Asset": {
        "Id": "LongValueHere",
        "Name": "ValueHere",
        "Type": "ImageAsset",
        "CropHeight": IntValueHere,
        "CropWidth": IntValueHere,
        "CropX": IntValueHere,
        "CropY": IntValueHere,
        "SubType": "ValueHere",
        "TargetHeight": IntValueHere,
        "TargetWidth": IntValueHere
      },
      "AssetPerformanceLabel": "ValueHere",
      "EditorialStatus": "ValueHere",
      "PinnedField": "ValueHere"
    }
  ],
  "Name": "ValueHere",
  "Path1": "ValueHere",
  "Path2": "ValueHere",
  "StartDate": {
    "Day": IntValueHere,
    "Month": IntValueHere,
    "Year": IntValueHere
  },
  "Status": "ValueHere",
  "Videos": [
    {
      "Asset": {
        "Id": "LongValueHere",
        "Name": "ValueHere",
        "Type": "ImageAsset",
        "CropHeight": IntValueHere,
        "CropWidth": IntValueHere,
        "CropX": IntValueHere,
        "CropY": IntValueHere,
        "SubType": "ValueHere",
        "TargetHeight": IntValueHere,
        "TargetWidth": IntValueHere
      },
      "AssetPerformanceLabel": "ValueHere",
      "EditorialStatus": "ValueHere",
      "PinnedField": "ValueHere"
    }
  ]
}
```

-----

## <a name="elements"></a>Elements

The [AssetGroup](assetgroup.md) object has the following elements: [AssetGroupSearchThemes](#assetgroupsearchthemes), [AssetGroupUrlTargets](#assetgroupurltargets), [BusinessName](#businessname), [CallToAction](#calltoaction), [Descriptions](#descriptions), [EditorialStatus](#editorialstatus), [EndDate](#enddate), [FinalMobileUrls](#finalmobileurls), [FinalUrls](#finalurls), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Headlines](#headlines), [Id](#id), [Images](#images), [LongHeadlines](#longheadlines), [Name](#name), [Path1](#path1), [Path2](#path2), [StartDate](#startdate), [Status](#status), [Videos](#videos).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="assetgroupsearchthemes"></a>AssetGroupSearchThemes|A list of asset group search themes.|[AssetGroupSearchTheme](assetgroupsearchtheme.md) array|
|<a name="assetgroupurltargets"></a>AssetGroupUrlTargets|Reserved.|[AssetGroupUrlTarget](assetgroupurltarget.md) array|
|<a name="businessname"></a>BusinessName|The name of the business.<br/><br/>Your business's name may appear in your ad, depending on the ad placement.<br/><br/>The length of the string is limited to 25 characters.<br/><br/>**Add:** Required. If not provided and parent campaign associates to a store, the store name will be used as the business name.<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="calltoaction"></a>CallToAction|A brief, punchy reason for customers to click your ad right now.<br/><br/>This is displayed on your call to action button.<br/><br/>**Add:** Required. If not provided and parent campaign associates to a store, it will default to *LearnMore*.<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|[CallToAction](calltoaction.md)|
|<a name="descriptions"></a>Descriptions|The descriptions that are shown below the path in your ad.<br /><br />You must set between 2-5 descriptions. Each description's Text must contain at least one word. The Text cannot contain the newline (\n) character.<br /><br />If the parent campaign associates to a store and you specify Descriptions, you must also specify Headlines, LongHeadlines, and Images. <br /><br />**Add**: Optional if the parent campaign associates to a store, required if its parent campaign does not associate to a store.<br />**Update**: Optional. To retain all of the existing asset links, set or leave this element nil. If you set a value for this element, any descriptions that were previously linked to this asset group will be replaced. If the parent campaign associates to a store and you set this element to an empty list, the previous setting will be deleted. |[AssetLink](assetlink.md) array|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the asset group, which indicates whether the asset group is pending review, has been approved, or has been disapproved.<br /><br />**Add**: Read-only<br />**Update**: Read-only |[AssetGroupEditorialStatus](assetgroupeditorialstatus.md)|
|<a name="enddate"></a>EndDate|The date that the asset group will expire.<br /><br />If you do not specify an end date, the asset group will not expire. The end date can be extended to make an asset group eligible for delivery, even after the asset group expires. <br /><br />The end date is inclusive. For example, if you set EndDate to 12/31/2020, the ads in the ad group will expire at 11:59 PM on 12/31/2020. The time is based on the time zone that you specify at the campaign level. <br /><br />**Add**: Optional. To set no end date when adding an asset group, set this element to null. <br />**Update**: Optional. If no value is set for the update, this setting is not changed. To delete the existing end date setting, and effectively set no end date when updating an asset group, set the end date equal to or later than January 2, 2050. When you retrieve the asset group next time, this element will be nil i.e. it will not be set to January 2, 2050. |[Date](date.md)|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.<br />- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br />- You may specifiy up to 10 items for both FinalUrls and FinalMobileUrls; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br />- Usage of '{' and '}' is only allowed to delineate tags, for example {lpurl}.<br />- Final URLs must each be a well-formed URL starting with either http:// or https://.<br />- If you specify FinalMobileUrls, you must also specify FinalUrls.<br /><br />**Add**: Optional <br />**Update**: Optional |**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br /><br />The domain portion of the URL in combination with the path 1 and path 2 strings cannot exceed 67 characters.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.<br />- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br />- You may specify up to 10 items for both FinalUrls and FinalMobileUrls; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br />- Usage of '{' and '}' is only allowed to delineate tags, for example {lpurl}.<br />- Final URLs must each be a well-formed URL starting with either http:// or https://.<br />- If you specify FinalMobileUrls, you must also specify FinalUrls.<br /><br />For retail campaigns, the final url must match the domain from the store associated with the campaign.<br /><br />**Add**: Required. If not provided and parent campaign associates to a store, the store URL will be used as the final URL.<br />**Update**: Optional |**string** array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object. |[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="headlines"></a>Headlines|Headlines are the most prominent text that appears in your ad, so you should make the most out of the available characters. We require multiple headlines so the ad can flexibly display across a variety of publishers and placements.<br /><br />From a data model perspective the descriptions and headlines are each stored as text assets i.e., one [TextAsset](../campaign-management-service/textasset.md) per [AssetLink](../campaign-management-service/assetlink.md). The same asset can be used by multiple ads. For example if "Seamless Integration" is a text asset, it will have the same asset identifier across all ads in the same Microsoft Advertising account.<br /><br />You must set between 3-15 headlines. Each headline's Text must contain at least one word.<br /><br />The Text cannot contain the newline (\n) character.<br /><br />If the parent campaign associates to a store and you specify Headlines, you must also specify LongHeadlines, Descriptions, and Images.<br /><br />**Add**: Optional if its parent campaign associates to a store, required if its parent campaign does not associate to a store. <br />**Update**: Optional. To retain all of the existing asset links, set or leave this element nil. If you set a value for this element, any headlines that were previously linked to this asset group will be replaced. If the parent campaign associates to a store and you set this element to an empty list, the previous setting will be deleted. |[AssetLink](assetlink.md) array|
|<a name="id"></a>Id|The system generated asset group ID.<br /><br />**Add**: Read-only<br />**Update**: Read-only |**long**|
|<a name="images"></a>Images|Image assets with different sizes and aspect ratios so they can flexibly display across a variety of publishers and placements. <br /><br />Include one or more [AssetLink](../campaign-management-service/assetlink.md) objects that each contain an [ImageAsset](../campaign-management-service/imageasset.md) with [SubType](../campaign-management-service/imageasset.md#subtype) and crop settings that match the desired aspect ratio.<br /><br />The ImageAsset contains the CropHeight, CropWidth, CropX, CropY and SubType fields.<br /><br />The possible sub type values include LandscapeImageMedia, SquareImageMedia, LandscapeLogoMedia, SquareLogoMedia, ImageMedia15X10, ImageMedia133X100, ImageMedia178X100, ImageMedia1X2, and ImageMedia4X1.<br /><br />You must provide at least 1 LandscapeImageMedia and 1 SquareImageMedia. A total of up to 20 images and a total of up to 5 logos can be saved. <br /><br />If the parent campaign associates to a store and you specify Images, you must also specify Headlines, LongHeadlines, and Descriptions.<br /><br />**Add**: Optional if the parent campaign associates to a store, required if its parent campaign does not associate to a store. <br />**Update**: Optional. If no value is set for the update, this setting is not changed. If you include images during update, any previously set images will be replaced. If the parent campaign associates to a store and you set this element to an empty list, the previous setting will be deleted. |[AssetLink](assetlink.md) array|
|<a name="longheadlines"></a>LongHeadlines|You must set between 1-5 long headlines. Each headline's Text must contain at least one word. The Text cannot contain the newline (\n) character. <br /><br />If the parent campaign associates to a store and you specify LongHeadlines, you must also specify Headlines, Descriptions, and Images. <br /><br />**Add**: Optional if the parent campaign associates to a store, required if its parent campaign does not associate to a store. <br />**Update**: Optional. To retain all of the existing asset links, set or leave this element nil. If you set a value for this element, any headlines that were previously linked to this asset group will be replaced. If the parent campaign associates to a store and you set this element to an empty list, the previous setting will be deleted. |[AssetLink](assetlink.md) array|
|<a name="name"></a>Name|The name of the asset group. Names should be unique in a campaign and are case sensitive. The length cannot exceed 256 characters. <br /><br />**Add**: Required <br />**Update**: Optional |**string**|
|<a name="path1"></a>Path1|The first part of the optional path that will be appended to the domain portion of your display URL. The domain portion of your display URL e.g. https://www.contoso.com will be generated from the domain of your Final URL (FinalUrls element). Then if you have specified a value for Path1 it will be appended to the display URL. If you have also specified a value for Path2, then it will also be appended to the display URL after Path1. For example if your FinalUrls contains https://www.contoso.com, Path1 is set to subdirectory1, and Path2 is set to subdirectory2, then the URL displayed will be https://www.contoso.com/subdirectory1/subdirectory2. <br /><br />No more than 15 characters can be input. The ad will fail to display if the length of the final URL domain and the paths combined exceed 67 characters. <br /><br />For languages with double-width characters e.g. Traditional Chinese no more than 7 final characters can be input. The ad will fail to display if the length of the final URL domain and the paths combined exceed 33 characters. The double-width characters are determined by the characters you use instead of the character set of the campaign language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. <br /><br />The path cannot contain the forward slash (/) or newline (\n) characters. <br /><br />If the path includes a space, it will be replaced with an underscore (_) when the ad is shown. <br /><br />**Add**: Optional <br />**Update**: Optional |**string**|
|<a name="path2"></a>Path2|The second part of the optional path that will be appended to the domain portion of your display URL. The domain portion of your display URL e.g. https://www.contoso.com will be generated from the domain of your Final URL (FinalUrls element). Then if you have specified a value for Path1 it will be appended to the display URL. If you have also specified a value for Path2, then it will also be appended to the display URL after Path1. For example if your FinalUrls contains https://www.contoso.com, Path1 is set to subdirectory1, and Path2 is set to subdirectory2, then the URL displayed will be https://www.contoso.com/subdirectory1/subdirectory2.<br /><br />You can only specify Path2 if Path1 is also set. <br /><br />No more than 15 characters can be input. The ad will fail to display if the length of the final URL domain and the paths combined exceed 67 characters. <br /><br />For languages with double-width characters e.g. Traditional Chinese no more than 7 final characters can be input. The ad will fail to display if the length of the final URL domain and the paths combined exceed 33 characters. The double-width characters are determined by the characters you use instead of the character set of the campaign language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. <br /><br />The path cannot contain the forward slash (/) or newline (\n) characters. <br /><br />If the path includes a space, it will be replaced with an underscore (_) when the ad is shown. <br /><br />**Add**: Optional <br />**Update**: Optional |**string**|
|<a name="startdate"></a>StartDate|The date that the asset group can begin serving; otherwise, the service can begin serving ads the day that the asset group becomes active. <br /><br />The start date is inclusive. For example, if you set the start date to 5/5/2021, the ads created from the asset group will start at 12:00 AM on 5/5/2021. The time is based on the time zone that you specify at the campaign level. <br /><br />**Add**: Optional. If you do not set the start date, then it will default to today's date and the service can begin serving ads as soon as the asset group status is active.<br />**Update**: Optional. If no value is set for the update, this setting is not changed. The start date cannot be updated after the asset group is submitted i.e., once the start date has arrived. |[Date](date.md)|
|<a name="status"></a>Status|The status of the Asset group. Possible values are *Active*, *Expired* and *Paused*. The *Expired* status is read-only.<br /><br />**Add**: Optional. Default is *Paused*. <br />**Update**: Optional |[AssetGroupStatus](assetgroupstatus.md)|
|<a name="videos"></a>Videos|Reserved.|[AssetLink](assetlink.md) array|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddAssetGroups](addassetgroups.md)  
[CreateAssetGroupRecommendation](createassetgrouprecommendation.md)  
[GetAssetGroupsByCampaignId](getassetgroupsbycampaignid.md)  
[GetAssetGroupsByIds](getassetgroupsbyids.md)  
[RefineAssetGroupRecommendation](refineassetgrouprecommendation.md)  
[UpdateAssetGroups](updateassetgroups.md)  
