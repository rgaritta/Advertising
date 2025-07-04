---
title: GoogleImportOption Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines the Google import options that are available via API.
---
# GoogleImportOption Data Object - Campaign Management
Defines the Google import options that are available via API. 

> [!NOTE]
>
> * **Starting February 1, 2023, you'll no longer be able to import expanded text ads from Google Ads**. Any expanded text ads imported before then can be re-imported and we'll continue to import status changes (e.g., pause, unpause) from Google Ads.
> * [Learn more about this change](https://about.ads.microsoft.com/en-us/blog/post/august-2022/you-have-5-additional-months-to-migrate-to-responsive-search-ads-deadline-extended-to-february-1-2023).

> [!TIP]
> For an implementation overview, see the [Google Ads Import](../guides/google-ads-import.md) technical guide. 

> [!NOTE]
> Please note that the list below is not a comprehensive list of imported items. Microsoft Advertising imports all the data needed to manage your campaigns and aims to provide the best experience for you. 
> 
> There is no option to exclude future supported entities from scheduled imports. For example, you cannot choose to only import "these specific ad extension types, but no other current or future ad extension types". Let's say promotion ad extensions is not yet available in the [GoogleImportOption](googleimportoption.md#elements) object. Once Microsoft Advertising supports it generally e.g., via the UI, all current and future scheduled imports will include promotion ad extensions until users opt out. After "PromotionAdExtensions" is added to the list of import options, then you could explicitly set it false as needed.  

Microsoft Advertising will import most supported campaigns, ads, targets, ad extensions, and other settings by default. As needed you can exclude an entity or otherwise customize the import. Specifically for ```boolean``` properties, most options are set *true* by default. The following exceptions default to *false* if not otherwise set. 
- [AutoDeviceBidOptimization](#autodevicebidoptimization)
- [DeleteRemovedEntities](#deleteremovedentities)
- [EnableAutoCurrencyConversion](#enableautocurrencyconversion)
- [NewPausedAdsForExistingAdGroups](#newpausedadsforexistingadgroups)
- [NewPausedCampaignsAndChildEntities](#newpausedcampaignsandchildentities)
- [PauseCampaignsWithoutSupportedLocations](#pausecampaignswithoutsupportedlocations)
- [PauseNewCampaigns](#pausenewcampaigns)
- [SearchAndDsaMixedCampaignAsSearchCampaign](#searchanddsamixedcampaignassearchcampaign)

For more details about what does and doesn't get imported from Google Ads, see [What gets imported](https://help.ads.microsoft.com/#apex/3/en/50851/0). 

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="GoogleImportOption" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:ImportOption">
      <xs:sequence>
        <xs:element minOccurs="0" name="AccountUrlOptions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="AdScheduleUseSearcherTimezone" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="AdjustmentForBids" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="AdjustmentForCampaignBudgets" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="AssociatedStoreId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="AssociatedUetTagId" nillable="true" type="xs:long" />
        <xs:element minOccurs="0" name="AutoDeviceBidOptimization" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="DeleteRemovedEntities" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="EnableAutoCurrencyConversion" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="EnableParentLocationMapping" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewAccountNegativeKeywords" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewActiveAdsForExistingAdGroups" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewActiveCampaignsAndChildEntities" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewAdCustomizerFeeds" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewAdGroupsAndChildEntitiesForExistingCampaigns" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewAdSchedules" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewAppAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewAudienceTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewBrandSuitability" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewCallAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewCalloutAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewCarouselAd" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewConversionGoals" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewDemographicTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewDeviceTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewEntities" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewImageAdExtensions" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewKeywordUrls" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewKeywordsForExistingAdGroups" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewLabels" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewLeadFormAdExtensions" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewLocationAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewLocationTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewLogoAdExtensions" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="NewNegativeKeywordLists" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewNegativeKeywordsForExistingParents" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewNegativeSites" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewPageFeeds" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewPausedAdsForExistingAdGroups" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewPausedCampaignsAndChildEntities" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewPriceAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewProductFilters" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewPromotionAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewReviewAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewSitelinkAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewStructuredSnippetAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="NewUrlOptions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="PauseAIMAdGroupIfAllAudienceCriterionNotImported" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="PauseCampaignsWithoutSupportedLocations" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="PauseNewCampaigns" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="RaiseBidsToMinimum" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="RaiseCampaignBudgetsToMinimum" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="RaiseProductGroupBidsToMinimum" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="RenameCampaignNameWithSuffix" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="SearchAndDsaMixedCampaignAsSearchCampaign" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="SearchAndReplaceForCampaignNames" nillable="true" type="tns:ImportSearchAndReplaceForStringProperty" />
        <xs:element minOccurs="0" name="SearchAndReplaceForCustomParameters" nillable="true" type="tns:ImportSearchAndReplaceForStringProperty">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="SearchAndReplaceForFinalURLSuffix" nillable="true" type="tns:ImportSearchAndReplaceForStringProperty">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="SearchAndReplaceForTrackingTemplates" nillable="true" type="tns:ImportSearchAndReplaceForStringProperty" />
        <xs:element minOccurs="0" name="SearchAndReplaceForUrls" nillable="true" type="tns:ImportSearchAndReplaceForStringProperty" />
        <xs:element minOccurs="0" name="SuffixForCampaignNames" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="SuffixForTrackingTemplates" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="SuffixForUrls" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="UpdateAccountNegativeKeywords" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateAdCustomizerAttributes" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateAdCustomizerFeeds" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateAdGroupNetwork" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateAdSchedules" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateAdUrls" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateAppAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateAudienceTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateBiddingStrategies" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateBids" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateBrandSuitability" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateCallAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateCalloutAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateCampaignAdGroupLanguages" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateCampaignBudgets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateCampaignNames" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateConversionGoals" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateDemographicTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateDeviceTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateEntities" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateImageAdExtensions" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateKeywordUrls" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateLabels" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateLeadFormAdExtensions" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateLocationAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateLocationTargets" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateLogoAdExtensions" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateNegativeKeywordLists" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateNegativeSites" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdatePageFeeds" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdatePriceAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateProductFilters" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdatePromotionAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateReviewAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateSitelinkAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateSitelinkUrls" nillable="true" type="xs:boolean">
          <xs:annotation>
            <xs:appinfo>
              <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
            </xs:appinfo>
          </xs:annotation>
        </xs:element>
        <xs:element minOccurs="0" name="UpdateStatusForAdGroups" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateStatusForAds" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateStatusForCampaigns" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateStatusForKeywords" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateStructuredSnippetAdExtensions" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="UpdateUrlOptions" nillable="true" type="xs:boolean" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "ForwardCompatibilityMap": [
    {
      "key": "ValueHere",
      "value": "ValueHere"
    }
  ],
  "Type": "GoogleImportOption",
  "AccountUrlOptions": "ValueHere",
  "AdjustmentForBids": DoubleValueHere,
  "AdjustmentForCampaignBudgets": DoubleValueHere,
  "AdScheduleUseSearcherTimezone": "ValueHere",
  "AssociatedStoreId": "LongValueHere",
  "AssociatedUetTagId": "LongValueHere",
  "AutoDeviceBidOptimization": "ValueHere",
  "DeleteRemovedEntities": "ValueHere",
  "EnableAutoCurrencyConversion": "ValueHere",
  "EnableParentLocationMapping": "ValueHere",
  "NewAccountNegativeKeywords": "ValueHere",
  "NewActiveAdsForExistingAdGroups": "ValueHere",
  "NewActiveCampaignsAndChildEntities": "ValueHere",
  "NewAdCustomizerFeeds": "ValueHere",
  "NewAdGroupsAndChildEntitiesForExistingCampaigns": "ValueHere",
  "NewAdSchedules": "ValueHere",
  "NewAppAdExtensions": "ValueHere",
  "NewAudienceTargets": "ValueHere",
  "NewBrandSuitability": "ValueHere",
  "NewCallAdExtensions": "ValueHere",
  "NewCalloutAdExtensions": "ValueHere",
  "NewCarouselAd": "ValueHere",
  "NewConversionGoals": "ValueHere",
  "NewDemographicTargets": "ValueHere",
  "NewDeviceTargets": "ValueHere",
  "NewEntities": "ValueHere",
  "NewImageAdExtensions": "ValueHere",
  "NewKeywordsForExistingAdGroups": "ValueHere",
  "NewKeywordUrls": "ValueHere",
  "NewLabels": "ValueHere",
  "NewLeadFormAdExtensions": "ValueHere",
  "NewLocationAdExtensions": "ValueHere",
  "NewLocationTargets": "ValueHere",
  "NewLogoAdExtensions": "ValueHere",
  "NewNegativeKeywordLists": "ValueHere",
  "NewNegativeKeywordsForExistingParents": "ValueHere",
  "NewNegativeSites": "ValueHere",
  "NewPageFeeds": "ValueHere",
  "NewPausedAdsForExistingAdGroups": "ValueHere",
  "NewPausedCampaignsAndChildEntities": "ValueHere",
  "NewPriceAdExtensions": "ValueHere",
  "NewProductFilters": "ValueHere",
  "NewPromotionAdExtensions": "ValueHere",
  "NewReviewAdExtensions": "ValueHere",
  "NewSitelinkAdExtensions": "ValueHere",
  "NewStructuredSnippetAdExtensions": "ValueHere",
  "NewUrlOptions": "ValueHere",
  "PauseAIMAdGroupIfAllAudienceCriterionNotImported": "ValueHere",
  "PauseCampaignsWithoutSupportedLocations": "ValueHere",
  "PauseNewCampaigns": "ValueHere",
  "RaiseBidsToMinimum": "ValueHere",
  "RaiseCampaignBudgetsToMinimum": "ValueHere",
  "RaiseProductGroupBidsToMinimum": "ValueHere",
  "RenameCampaignNameWithSuffix": "ValueHere",
  "SearchAndDsaMixedCampaignAsSearchCampaign": "ValueHere",
  "SearchAndReplaceForCampaignNames": {
    "ReplaceString": "ValueHere",
    "SearchString": "ValueHere"
  },
  "SearchAndReplaceForCustomParameters": {
    "ReplaceString": "ValueHere",
    "SearchString": "ValueHere"
  },
  "SearchAndReplaceForFinalURLSuffix": {
    "ReplaceString": "ValueHere",
    "SearchString": "ValueHere"
  },
  "SearchAndReplaceForTrackingTemplates": {
    "ReplaceString": "ValueHere",
    "SearchString": "ValueHere"
  },
  "SearchAndReplaceForUrls": {
    "ReplaceString": "ValueHere",
    "SearchString": "ValueHere"
  },
  "SuffixForCampaignNames": "ValueHere",
  "SuffixForTrackingTemplates": "ValueHere",
  "SuffixForUrls": "ValueHere",
  "UpdateAccountNegativeKeywords": "ValueHere",
  "UpdateAdCustomizerAttributes": "ValueHere",
  "UpdateAdCustomizerFeeds": "ValueHere",
  "UpdateAdGroupNetwork": "ValueHere",
  "UpdateAdSchedules": "ValueHere",
  "UpdateAdUrls": "ValueHere",
  "UpdateAppAdExtensions": "ValueHere",
  "UpdateAudienceTargets": "ValueHere",
  "UpdateBiddingStrategies": "ValueHere",
  "UpdateBids": "ValueHere",
  "UpdateBrandSuitability": "ValueHere",
  "UpdateCallAdExtensions": "ValueHere",
  "UpdateCalloutAdExtensions": "ValueHere",
  "UpdateCampaignAdGroupLanguages": "ValueHere",
  "UpdateCampaignBudgets": "ValueHere",
  "UpdateCampaignNames": "ValueHere",
  "UpdateConversionGoals": "ValueHere",
  "UpdateDemographicTargets": "ValueHere",
  "UpdateDeviceTargets": "ValueHere",
  "UpdateEntities": "ValueHere",
  "UpdateImageAdExtensions": "ValueHere",
  "UpdateKeywordUrls": "ValueHere",
  "UpdateLabels": "ValueHere",
  "UpdateLeadFormAdExtensions": "ValueHere",
  "UpdateLocationAdExtensions": "ValueHere",
  "UpdateLocationTargets": "ValueHere",
  "UpdateLogoAdExtensions": "ValueHere",
  "UpdateNegativeKeywordLists": "ValueHere",
  "UpdateNegativeSites": "ValueHere",
  "UpdatePageFeeds": "ValueHere",
  "UpdatePriceAdExtensions": "ValueHere",
  "UpdateProductFilters": "ValueHere",
  "UpdatePromotionAdExtensions": "ValueHere",
  "UpdateReviewAdExtensions": "ValueHere",
  "UpdateSitelinkAdExtensions": "ValueHere",
  "UpdateSitelinkUrls": "ValueHere",
  "UpdateStatusForAdGroups": "ValueHere",
  "UpdateStatusForAds": "ValueHere",
  "UpdateStatusForCampaigns": "ValueHere",
  "UpdateStatusForKeywords": "ValueHere",
  "UpdateStructuredSnippetAdExtensions": "ValueHere",
  "UpdateUrlOptions": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [GoogleImportOption](googleimportoption.md) object has the following elements: [AccountUrlOptions](#accounturloptions), [AdjustmentForBids](#adjustmentforbids), [AdjustmentForCampaignBudgets](#adjustmentforcampaignbudgets), [AdScheduleUseSearcherTimezone](#adscheduleusesearchertimezone), [AssociatedStoreId](#associatedstoreid), [AssociatedUetTagId](#associateduettagid), [AutoDeviceBidOptimization](#autodevicebidoptimization), [DeleteRemovedEntities](#deleteremovedentities), [EnableAutoCurrencyConversion](#enableautocurrencyconversion), [EnableParentLocationMapping](#enableparentlocationmapping), [NewAccountNegativeKeywords](#newaccountnegativekeywords), [NewActiveAdsForExistingAdGroups](#newactiveadsforexistingadgroups), [NewActiveCampaignsAndChildEntities](#newactivecampaignsandchildentities), [NewAdCustomizerFeeds](#newadcustomizerfeeds), [NewAdGroupsAndChildEntitiesForExistingCampaigns](#newadgroupsandchildentitiesforexistingcampaigns), [NewAdSchedules](#newadschedules), [NewAppAdExtensions](#newappadextensions), [NewAudienceTargets](#newaudiencetargets), [NewBrandSuitability](#newbrandsuitability), [NewCallAdExtensions](#newcalladextensions), [NewCalloutAdExtensions](#newcalloutadextensions), [NewCarouselAd](#newcarouselad), [NewConversionGoals](#newconversiongoals), [NewDemographicTargets](#newdemographictargets), [NewDeviceTargets](#newdevicetargets), [NewEntities](#newentities), [NewImageAdExtensions](#newimageadextensions), [NewKeywordsForExistingAdGroups](#newkeywordsforexistingadgroups), [NewKeywordUrls](#newkeywordurls), [NewLabels](#newlabels), [NewLeadFormAdExtensions](#newleadformadextensions), [NewLocationAdExtensions](#newlocationadextensions), [NewLocationTargets](#newlocationtargets), [NewLogoAdExtensions](#newlogoadextensions), [NewNegativeKeywordLists](#newnegativekeywordlists), [NewNegativeKeywordsForExistingParents](#newnegativekeywordsforexistingparents), [NewNegativeSites](#newnegativesites), [NewPageFeeds](#newpagefeeds), [NewPausedAdsForExistingAdGroups](#newpausedadsforexistingadgroups), [NewPausedCampaignsAndChildEntities](#newpausedcampaignsandchildentities), [NewPriceAdExtensions](#newpriceadextensions), [NewProductFilters](#newproductfilters), [NewPromotionAdExtensions](#newpromotionadextensions), [NewReviewAdExtensions](#newreviewadextensions), [NewSitelinkAdExtensions](#newsitelinkadextensions), [NewStructuredSnippetAdExtensions](#newstructuredsnippetadextensions), [NewUrlOptions](#newurloptions), [PauseAIMAdGroupIfAllAudienceCriterionNotImported](#pauseaimadgroupifallaudiencecriterionnotimported), [PauseCampaignsWithoutSupportedLocations](#pausecampaignswithoutsupportedlocations), [PauseNewCampaigns](#pausenewcampaigns), [RaiseBidsToMinimum](#raisebidstominimum), [RaiseCampaignBudgetsToMinimum](#raisecampaignbudgetstominimum), [RaiseProductGroupBidsToMinimum](#raiseproductgroupbidstominimum), [RenameCampaignNameWithSuffix](#renamecampaignnamewithsuffix), [SearchAndDsaMixedCampaignAsSearchCampaign](#searchanddsamixedcampaignassearchcampaign), [SearchAndReplaceForCampaignNames](#searchandreplaceforcampaignnames), [SearchAndReplaceForCustomParameters](#searchandreplaceforcustomparameters), [SearchAndReplaceForFinalURLSuffix](#searchandreplaceforfinalurlsuffix), [SearchAndReplaceForTrackingTemplates](#searchandreplacefortrackingtemplates), [SearchAndReplaceForUrls](#searchandreplaceforurls), [SuffixForCampaignNames](#suffixforcampaignnames), [SuffixForTrackingTemplates](#suffixfortrackingtemplates), [SuffixForUrls](#suffixforurls), [UpdateAccountNegativeKeywords](#updateaccountnegativekeywords), [UpdateAdCustomizerAttributes](#updateadcustomizerattributes), [UpdateAdCustomizerFeeds](#updateadcustomizerfeeds), [UpdateAdGroupNetwork](#updateadgroupnetwork), [UpdateAdSchedules](#updateadschedules), [UpdateAdUrls](#updateadurls), [UpdateAppAdExtensions](#updateappadextensions), [UpdateAudienceTargets](#updateaudiencetargets), [UpdateBiddingStrategies](#updatebiddingstrategies), [UpdateBids](#updatebids), [UpdateBrandSuitability](#updatebrandsuitability), [UpdateCallAdExtensions](#updatecalladextensions), [UpdateCalloutAdExtensions](#updatecalloutadextensions), [UpdateCampaignAdGroupLanguages](#updatecampaignadgrouplanguages), [UpdateCampaignBudgets](#updatecampaignbudgets), [UpdateCampaignNames](#updatecampaignnames), [UpdateConversionGoals](#updateconversiongoals), [UpdateDemographicTargets](#updatedemographictargets), [UpdateDeviceTargets](#updatedevicetargets), [UpdateEntities](#updateentities), [UpdateImageAdExtensions](#updateimageadextensions), [UpdateKeywordUrls](#updatekeywordurls), [UpdateLabels](#updatelabels), [UpdateLeadFormAdExtensions](#updateleadformadextensions), [UpdateLocationAdExtensions](#updatelocationadextensions), [UpdateLocationTargets](#updatelocationtargets), [UpdateLogoAdExtensions](#updatelogoadextensions), [UpdateNegativeKeywordLists](#updatenegativekeywordlists), [UpdateNegativeSites](#updatenegativesites), [UpdatePageFeeds](#updatepagefeeds), [UpdatePriceAdExtensions](#updatepriceadextensions), [UpdateProductFilters](#updateproductfilters), [UpdatePromotionAdExtensions](#updatepromotionadextensions), [UpdateReviewAdExtensions](#updatereviewadextensions), [UpdateSitelinkAdExtensions](#updatesitelinkadextensions), [UpdateSitelinkUrls](#updatesitelinkurls), [UpdateStatusForAdGroups](#updatestatusforadgroups), [UpdateStatusForAds](#updatestatusforads), [UpdateStatusForCampaigns](#updatestatusforcampaigns), [UpdateStatusForKeywords](#updatestatusforkeywords), [UpdateStructuredSnippetAdExtensions](#updatestructuredsnippetadextensions), [UpdateUrlOptions](#updateurloptions).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accounturloptions"></a>AccountUrlOptions|Import the account level tracking template and final URL suffix.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Account-level URL options*.|**boolean**|
|<a name="adjustmentforbids"></a>AdjustmentForBids|The percentage amount that you want to increase or decrease the new or existing Microsoft Advertising bids relative to your Google Ads bids.<br/><br/>The valid bid multiplier range is -90 through 900.<br/><br/>For example, to increase the Microsoft Advertising bids 25 percent higher than your Google Ads bids, set this element to 25.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Customize bids for Microsoft Advertising*.|**double**|
|<a name="adjustmentforcampaignbudgets"></a>AdjustmentForCampaignBudgets|The percentage amount that you want to increase or decrease the new or existing Microsoft Advertising campaign budgets relative to your Google Ads campaign budgets.<br/><br/>The valid bid multiplier range is -90 through 900.<br/><br/>For example, to increase the Microsoft Advertising campaign budgets 25 percent higher than your Google Ads campaign budgets, set this element to 25.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Customize budgets for Microsoft Advertising*.|**double**|
|<a name="adscheduleusesearchertimezone"></a>AdScheduleUseSearcherTimezone|Reserved.|**boolean**|
|<a name="associatedstoreid"></a>AssociatedStoreId|*Note:* *AssociatedStoreId* is deprecated.<br/><br/>The identifier of the Microsoft Merchant Center store that you want to associate with imported product ads and product filters.<br/><br/>If this option is null or empty, your product ads and product filters will not be imported.<br/><br/>To learn more see the [Product Ads](../guides/product-ads.md) technical guide and the [Create product ads in a shopping campaign](https://help.ads.microsoft.com/#apex/3/en/51060/1) help article.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Microsoft Merchant Center > Associate Microsoft Merchant Center Store with imported shopping campaigns and ad extensions*.|**long**|
|<a name="associateduettagid"></a>AssociatedUetTagId|The identifier of the Universal Event Tracking tag ([UetTag](uettag.md)) that you want to associate with imported remarketing lists.<br/><br/>This option is only available for customers in the Remarketing Google Import feature pilot program ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 750).<br/><br/>To import audience lists, targets, and exclusions you must also enable the [NewAudienceTargets](#newaudiencetargets) option.<br/><br/>If this option is null or empty, your remarketing lists, targets, and exclusions will not be imported. This element is not required for in-market audience targets and exclusions, since they do not depend on a UET tag.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > UET tag > Asse the following UET tag with any remarketing list, audience, or converociatsion goal that has not previously imported into Microsoft Advertising*.|**long**|
|<a name="autodevicebidoptimization"></a>AutoDeviceBidOptimization|When enabled, we will not import negative bid modifiers for desktop targets except modifiers set to -100%.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Do not import negative bid modifier for desktop (except -100%)*.|**boolean**|
|<a name="deleteremovedentities"></a>DeleteRemovedEntities|Removed Google Ads items will be deleted along with their associated sub-items.<br/><br/>For example if you removed a Google Ads campaign since the previous import, then the campaign and its ad groups, ads, and keywords will be removed from Microsoft Advertising when the import runs next time. Likewise, if you removed your Google Ads account level tracking template or final URL suffix since the previous import, they will be deleted from Microsoft Advertising.<br/><br/>Ad extensions removed in Google Ads will not be deleted in Microsoft Advertising.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Delete items that have been removed from your Google Ads account*.|**boolean**|
|<a name="enableautocurrencyconversion"></a>EnableAutoCurrencyConversion|If the currency in your Google Ads account does not match the currency in your Microsoft Advertising ad account, the imported bids and budgets will be converted to their equivalent currency in Microsoft Advertising.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Choose your Google Ads account*. You will only see the UI option to convert or ignore if the currency varies between your Google Ads account and Microsoft Advertising ad account.|**boolean**|
|<a name="enableparentlocationmapping"></a>EnableParentLocationMapping|Google Ads location targets that are unsupported by Microsoft Advertising are expanded in scope and mapped to parent location targets that are supported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option. If you set this element *false* the unsupported location targets are not imported.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Targeting > Do not expand unsupported location targets*.|**boolean**|
|<a name="newaccountnegativekeywords"></a>NewAccountNegativeKeywords|Import account negative keywords that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to true. Set this element false to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Account negative keywords*.|**boolean**|
|<a name="newactiveadsforexistingadgroups"></a>NewActiveAdsForExistingAdGroups|Import new active ads within existing ad groups.<br/><br/>To also import paused ads, ensure that the [NewPausedAdsForExistingAdGroups](#newpausedadsforexistingadgroups) option is enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Ads for existing ad groups*.|**boolean**|
|<a name="newactivecampaignsandchildentities"></a>NewActiveCampaignsAndChildEntities|Import active campaigns that have not previously been imported.<br/><br/>The import will include all ad groups, active ads, and keywords that the new campaigns contain.<br/><br/>To also import paused campaigns, ensure that the [NewPausedCampaignsAndChildEntities](#newpausedcampaignsandchildentities) option is enabled. To also import paused ads, ensure that the [NewPausedAdsForExistingAdGroups](#newpausedadsforexistingadgroups) option is enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Campaigns*.|**boolean**|
|<a name="newadcustomizerfeeds"></a>NewAdCustomizerFeeds|Import ad customizer feeds that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Feeds > Ad customizer feeds*.|**boolean**|
|<a name="newadgroupsandchildentitiesforexistingcampaigns"></a>NewAdGroupsAndChildEntitiesForExistingCampaigns|Import new ad groups within existing campaigns.<br/><br/>The import will include all active ads and keywords that the new ad groups contain. To also import paused ads, ensure that the [NewPausedAdsForExistingAdGroups](#newpausedadsforexistingadgroups) option is enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Ad groups for existing campaigns*.|**boolean**|
|<a name="newadschedules"></a>NewAdSchedules|Import ad schedules that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Targeting > Ad schedules*.|**boolean**|
|<a name="newappadextensions"></a>NewAppAdExtensions|Import app extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > App Extensions*.|**boolean**|
|<a name="newaudiencetargets"></a>NewAudienceTargets|Import campaign and ad group targets and exclusions for in-market audiences. Targets and exclusions for remarketing lists and combined lists can be imported if a valid UET tag identifier is set via the [AssociatedUetTagId](#associateduettagid) element.<br/><br/>As support is added for import of additional audience types in the future, the corresponding lists, targets, and exclusions will also be imported if this option is enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Targeting > Audience targets*.|**boolean**|
|<a name="newbrandsuitability"></a>NewBrandSuitability|Import brand suitability that has not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Brand Suitability*|**boolean**|
|<a name="newcalladextensions"></a>NewCallAdExtensions|Import call extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Call Extensions*.|**boolean**|
|<a name="newcalloutadextensions"></a>NewCalloutAdExtensions|Import callout extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Callout Extensions*.|**boolean**|
|<a name="newcarouselad"></a>NewCarouselAd|Reserved.|**boolean**|
|<a name="newconversiongoals"></a>NewConversionGoals|Import conversion goals that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > UET tag > Conversion goals*.|**boolean**|
|<a name="newdemographictargets"></a>NewDemographicTargets|Import demographic targets that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Targeting > Demographic targets*.|**boolean**|
|<a name="newdevicetargets"></a>NewDeviceTargets|Import device targets that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Targeting > Device targets*.|**boolean**|
|<a name="newentities"></a>NewEntities|The prerequisite option for importing new entities and settings into Microsoft Advertising.<br/><br/>If this element is set *false*, the following options are ignored: [NewActiveAdsForExistingAdGroups](#newactiveadsforexistingadgroups), [NewActiveCampaignsAndChildEntities](#newactivecampaignsandchildentities), [NewAdCustomizerFeeds](#newadcustomizerfeeds), [NewAdGroupsAndChildEntitiesForExistingCampaigns](#newadgroupsandchildentitiesforexistingcampaigns), [NewAdSchedules](#newadschedules), [NewAppAdExtensions](#newappadextensions), [NewAudienceTargets](#newaudiencetargets), [NewCallAdExtensions](#newcalladextensions), [NewCalloutAdExtensions](#newcalloutadextensions), [NewDemographicTargets](#newdemographictargets), [NewDeviceTargets](#newdevicetargets), [NewKeywordsForExistingAdGroups](#newkeywordsforexistingadgroups), [NewKeywordUrls](#newkeywordurls), [NewLabels](#newlabels), [NewLocationAdExtensions](#newlocationadextensions), [NewLocationTargets](#newlocationtargets), [NewNegativeKeywordLists](#newnegativekeywordlists), [NewNegativeKeywordsForExistingParents](#newnegativekeywordsforexistingparents), [NewNegativeSites](#newnegativesites), [NewPageFeeds](#newpagefeeds), [NewPausedAdsForExistingAdGroups](#newpausedadsforexistingadgroups), [NewPausedCampaignsAndChildEntities](#newpausedcampaignsandchildentities), [NewPriceAdExtensions](#newpriceadextensions), [NewProductFilters](#newproductfilters), [NewReviewAdExtensions](#newreviewadextensions), [NewSitelinkAdExtensions](#newsitelinkadextensions), [NewStructuredSnippetAdExtensions](#newstructuredsnippetadextensions), [NewUrlOptions](#newurloptions).<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising*.|**boolean**|
|<a name="newimageadextensions"></a>NewImageAdExtensions|Reserved.|**boolean**|
|<a name="newkeywordsforexistingadgroups"></a>NewKeywordsForExistingAdGroups|Import new keywords within existing ad groups.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Keywords for existing ad groups*.|**boolean**|
|<a name="newkeywordurls"></a>NewKeywordUrls|Import new keyword landing page URLs.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Keyword landing page URLs*.|**boolean**|
|<a name="newlabels"></a>NewLabels|Import labels that have not previously been imported.<br/><br/>Label associations are only imported if you also import the corresponding new entities.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Labels*.|**boolean**|
|<a name="newleadformadextensions"></a>NewLeadFormAdExtensions|Reserved.|**boolean**|
|<a name="newlocationadextensions"></a>NewLocationAdExtensions|Import location extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Location Extensions*.|**boolean**|
|<a name="newlocationtargets"></a>NewLocationTargets|Import location targets that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Targeting > Location targets*.|**boolean**|
|<a name="newlogoadextensions"></a>NewLogoAdExtensions|Import logo ad extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Logo Ad Extensions*.|**boolean**|
|<a name="newnegativekeywordlists"></a>NewNegativeKeywordLists|Import negative keyword lists that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Negative keyword lists*.|**boolean**|
|<a name="newnegativekeywordsforexistingparents"></a>NewNegativeKeywordsForExistingParents|Import new negative keywords for existing campaigns or existing ad groups.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Negative keywords for existing campaigns and ad groups*.|**boolean**|
|<a name="newnegativesites"></a>NewNegativeSites|Import new negative sites for existing campaigns or existing ad groups.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Negative sites*.|**boolean**|
|<a name="newpagefeeds"></a>NewPageFeeds|Import page feeds that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Feeds > Page feeds*.|**boolean**|
|<a name="newpausedadsforexistingadgroups"></a>NewPausedAdsForExistingAdGroups|Import paused ads along with your active ads.<br/><br/>The [NewActiveAdsForExistingAdGroups](#newactiveadsforexistingadgroups) option must also be enabled, otherwise this option is effectively ignored.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Ad options > Include paused ads when importing new ads*.|**boolean**|
|<a name="newpausedcampaignsandchildentities"></a>NewPausedCampaignsAndChildEntities|Import paused campaigns along with your active campaigns.<br/><br/>The [NewActiveCampaignsAndChildEntities](#newactivecampaignsandchildentities) option must also be enabled, otherwise this option is effectively ignored.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Campaign options > Include paused campaigns when importing new items*.|**boolean**|
|<a name="newpriceadextensions"></a>NewPriceAdExtensions|Import price extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Price Extensions*.|**boolean**|
|<a name="newproductfilters"></a>NewProductFilters|Import new product filters from your shopping campaigns.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Product filters*.|**boolean**|
|<a name="newpromotionadextensions"></a>NewPromotionAdExtensions|Import promotion extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Promotion Extensions*.|**boolean**|
|<a name="newreviewadextensions"></a>NewReviewAdExtensions|Import review extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Review Extensions*.|**boolean**|
|<a name="newsitelinkadextensions"></a>NewSitelinkAdExtensions|Import sitelink extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Sitelink Extensions*.|**boolean**|
|<a name="newstructuredsnippetadextensions"></a>NewStructuredSnippetAdExtensions|Import structured snippet extensions that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Ad extensions > Structured Snippet Extensions*.|**boolean**|
|<a name="newurloptions"></a>NewUrlOptions|Import tracking templates, custom parameters, and final URL suffix URL options with entities that have not previously been imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Items not previously imported into Microsoft Advertising > Import items > Tracking templates, custom parameters, and final URL suffixes*.|**boolean**|
|<a name="pauseaimadgroupifallaudiencecriterionnotimported"></a>PauseAIMAdGroupIfAllAudienceCriterionNotImported|Reserved.|**boolean**|
|<a name="pausecampaignswithoutsupportedlocations"></a>PauseCampaignsWithoutSupportedLocations|When enabled this option will pause imported campaigns in case all of their location targets are unsupported by Microsoft Advertising.<br/><br/>If a campaign contains both supported and unsupported location targets the campaign will not be paused and will continue to serve for supported location targets.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Targeting > Pause campaigns when all imported location targets are unsupported*.|**boolean**|
|<a name="pausenewcampaigns"></a>PauseNewCampaigns|This option will pause newly imported campaigns allowing you to review your campaigns before you get your campaigns up and running.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Campaign options > Pause newly imported campaigns*.|**boolean**|
|<a name="raisebidstominimum"></a>RaiseBidsToMinimum|Due to differences in Microsoft Advertising and Google Ads minimum bid requirements any bids below the our minimum amount will automatically be raised during import. This means that the amount of money you spend overall may increase for the imported campaigns. If you decide to opt out of increasing the minimum bid during import any campaigns that don't meet the minimum amount will not get imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Increase keyword, ad group, and auto target bids to the minimum for Microsoft Advertising*.|**boolean**|
|<a name="raisecampaignbudgetstominimum"></a>RaiseCampaignBudgetsToMinimum|Due to differences in Microsoft Advertising and Google Ads minimum bid and budget requirements any budgets below our minimum amount will automatically be raised during import. This means that the amount of money you spend overall may increase for the imported campaigns. If you decide to opt out of increasing the minimum budget during import any campaigns that don't meet the minimum amount will not get imported.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Increase campaign budgets to the minimum for Microsoft Advertising*.|**boolean**|
|<a name="raiseproductgroupbidstominimum"></a>RaiseProductGroupBidsToMinimum|By enabling this option Microsoft Advertising will increase all product group bids to the minimum bid amount. Your campaigns will still be imported if you don't enable this option but any products groups that have a bid below the Microsoft Advertising minimum will not serve.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and Budgets > Increase product group bids to the minimum for Microsoft Advertising*.|**boolean**|
|<a name="renamecampaignnamewithsuffix"></a>RenameCampaignNameWithSuffix|Reserved.|**boolean**|
|<a name="searchanddsamixedcampaignassearchcampaign"></a>SearchAndDsaMixedCampaignAsSearchCampaign|If you enable this option, the service will only fetch search ads from mixed campaigns and import them as search campaigns. Otherwise the service will only fetch dynamic search ads from mixed campaigns and import them as dynamic search campaigns. Mixed campaigns contain both dynamic search ads and other ad types (e.g. Expanded Text Ads).<br/><br/>Mixed campaigns are available wherever Dynamic search ads are supported i.e., Australia (AU), Austria (AT), Belgium (BE), Canada (CA), France (FR), Germany (DE), Ireland (IE), Italy (IT), Netherlands (NL), New Zealand (NZ), Spain (ES), Sweden (SE), Switzerland (CH), United Kingdom (UK), and United States (US). In those countries/regions this option is ignored and will no longer be visible in the Microsoft Advertising UI. Then whether this option is set to *true* or *false* both search and DSA ad groups will be imported.<br/><br/>This option is turned off by default, or effectively set to *false*. Set this element *true* to enable this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Import search and DSA mixed campaigns as search campaigns*.|**boolean**|
|<a name="searchandreplaceforcampaignnames"></a>SearchAndReplaceForCampaignNames|Set this option to find and replace a string within each campaign name during import.<br/><br/>When you update import options via [UpdateImportJobs](updateimportjobs.md) you can remove, update, or leave in place the prior search and replace settings. For details please see the [remarks](#remarks) below.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Campaign options > Find and replace text in each campaign name*.|[ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md)|
|<a name="searchandreplaceforcustomparameters"></a>SearchAndReplaceForCustomParameters|Set this option to find and replace a string within each custom parameter during import.<br/><br/>When you update import options via [UpdateImportJobs](updateimportjobs.md) you can remove, update, or leave in place the prior search and replace settings. For details please see the [remarks](#remarks) below.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Tracking templates > Find and replace text in each custom parameter*.|[ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md)|
|<a name="searchandreplaceforfinalurlsuffix"></a>SearchAndReplaceForFinalURLSuffix|Reserved.|[ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md)|
|<a name="searchandreplacefortrackingtemplates"></a>SearchAndReplaceForTrackingTemplates|Set this option to find and replace a string within each tracking template during import.<br/><br/>When you update import options via [UpdateImportJobs](updateimportjobs.md) you can remove, update, or leave in place the prior search and replace settings. For details please see the [remarks](#remarks) below.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Tracking templates > Find and replace text in each tracking template*.|[ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md)|
|<a name="searchandreplaceforurls"></a>SearchAndReplaceForUrls|Set this option to find and replace a string within each final URL, mobile URL, and destination URL during import.<br/><br/>When you update import options via [UpdateImportJobs](updateimportjobs.md) you can remove, update, or leave in place the prior search and replace settings. For details please see the [remarks](#remarks) below.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Landing page URLs > Find and replace text in each final URL, mobile URL, and destination URL*.|[ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md)|
|<a name="suffixforcampaignnames"></a>SuffixForCampaignNames|Set this option to insert a string at the end of each campaign name during import.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Campaign options > Insert at the end of each campaign name*.|**string**|
|<a name="suffixfortrackingtemplates"></a>SuffixForTrackingTemplates|Set this option to insert a string at the end of each tracking template during import.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Tracking templates > Insert at the end of each tracking template*.|**string**|
|<a name="suffixforurls"></a>SuffixForUrls|Set this option to insert a string at the end of each final URL, mobile URL, and destination URL during import.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Landing page URLs > Insert at the end of each final URL, mobile URL, and destination URL*.|**string**|
|<a name="updateaccountnegativekeywords"></a>UpdateAccountNegativeKeywords|Import updates to existing account negative keywords.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to true. Set this element false to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Account negative keywords*.|**boolean**|
|<a name="updateadcustomizerattributes"></a>UpdateAdCustomizerAttributes|Import updates to existing ad customizer feeds.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Feeds > Ad customizer attributes*.|**boolean**|
|<a name="updateadcustomizerfeeds"></a>UpdateAdCustomizerFeeds|Import updates to existing ad customizer feeds.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Feeds > Ad customizer feeds*.|**boolean**|
|<a name="updateadgroupnetwork"></a>UpdateAdGroupNetwork|Import updates to the ad distribution of existing ad groups.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Ad distribution*.|**boolean**|
|<a name="updateadschedules"></a>UpdateAdSchedules|Import updates to existing ad schedules.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Targeting > Ad schedules*.|**boolean**|
|<a name="updateadurls"></a>UpdateAdUrls|Import updates to existing ad landing page URLs.<br /><br />This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br /><br />This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br /><br />This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Ad landing page URLs*.|**boolean**|
|<a name="updateappadextensions"></a>UpdateAppAdExtensions|Import updates to existing app extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > App Extensions*.|**boolean**|
|<a name="updateaudiencetargets"></a>UpdateAudienceTargets|Import updates to existing audience targets.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Targeting > Audience targets*.|**boolean**|
|<a name="updatebiddingstrategies"></a>UpdateBiddingStrategies|Update the existing campaign, ad group, and keyword bid strategies to match those currently in Google Ads.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Update bid strategies*.|**boolean**|
|<a name="updatebids"></a>UpdateBids|When enabled this option allows you to update the existing keywords, auto-targets, and product ads bid types to match those currently in Google Ads.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Update bids*.|**boolean**|
|<a name="updatebrandsuitability"></a>UpdateBrandSuitability|Import updates to brand suitablity.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Brand Suitability*.|**boolean**|
|<a name="updatecalladextensions"></a>UpdateCallAdExtensions|Import updates to existing call extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Call Extensions*.|**boolean**|
|<a name="updatecalloutadextensions"></a>UpdateCalloutAdExtensions|Import updates to existing callout extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Callout Extensions*.|**boolean**|
|<a name="updatecampaignadgrouplanguages"></a>UpdateCampaignAdGroupLanguages|Import updates to the language of existing campaigns and ad groups.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Campaign and ad group languages*.|**boolean**|
|<a name="updatecampaignbudgets"></a>UpdateCampaignBudgets|When enabled this option fetches updates to existing campaign budgets that are now in Microsoft Advertising.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Bids and budgets > Update existing campaign budgets*.|**boolean**|
|<a name="updatecampaignnames"></a>UpdateCampaignNames|By enabling this option Microsoft Advertising will update the names of previously imported campaigns if the name was updated in Google Ads. However, settings and items linked to those campaigns can still be updated.<br/><br/>Existing campaigns will be updated if the original items were created by an import after March 21, 2016. Otherwise, new campaign names will be created. This option is only applicable for existing campaigns and will not affect new campaigns.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > Other options > Campaign options > Do not update existing campaign names*.|**boolean**|
|<a name="updateconversiongoals"></a>UpdateConversionGoals|Import updates to existing conversion goals.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > UET tag > conversion goals*.|**boolean**|
|<a name="updatedemographictargets"></a>UpdateDemographicTargets|Import updates to existing demographic targets.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Targeting > Demographic targets*.|**boolean**|
|<a name="updatedevicetargets"></a>UpdateDeviceTargets|Import updates to existing device targets.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Targeting > Device targets*.|**boolean**|
|<a name="updateentities"></a>UpdateEntities|The prerequisite option for importing updated entities and settings into Microsoft Advertising. The service will import updates for previously imported items to match those currently in Google Ads.<br/><br/>If this element is set *false*, the following options are ignored: [UpdateAdCustomizerFeeds](#updateadcustomizerfeeds), [UpdateAdCustomizerFeeds](#updateadcustomizerfeeds), [UpdateAdGroupNetwork](#updateadgroupnetwork), [UpdateAdSchedules](#updateadschedules), [UpdateAppAdExtensions](#updateappadextensions), [UpdateAudienceTargets](#updateaudiencetargets), [UpdateCallAdExtensions](#updatecalladextensions), [UpdateCalloutAdExtensions](#updatecalloutadextensions), [UpdateDemographicTargets](#updatedemographictargets), [UpdateDeviceTargets](#updatedevicetargets), [UpdateKeywordUrls](#updatekeywordurls), [UpdateLabels](#updatelabels), [UpdateLocationAdExtensions](#updatelocationadextensions), [UpdateLocationTargets](#updatelocationtargets), [UpdateNegativeKeywordLists](#updatenegativekeywordlists), [UpdateNegativeSites](#updatenegativesites), [UpdatePageFeeds](#updatepagefeeds), [UpdatePriceAdExtensions](#updatepriceadextensions), [UpdateProductFilters](#updateproductfilters), [UpdateReviewAdExtensions](#updatereviewadextensions), [UpdateSitelinkAdExtensions](#updatesitelinkadextensions), [UpdateStructuredSnippetAdExtensions](#updatestructuredsnippetadextensions), [UpdateUrlOptions](#updateurloptions).<br/><br/>This option is equivalent to the "Updates to existing items" checkbox in the Microsoft Advertising UI.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items*.|**boolean**|
|<a name="updateimageadextensions"></a>UpdateImageAdExtensions|Reserved.|**boolean**|
|<a name="updatekeywordurls"></a>UpdateKeywordUrls|Import updates to existing keyword landing page URLs.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Keyword landing page URLs*.|**boolean**|
|<a name="updatelabels"></a>UpdateLabels|Import updates to existing labels.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Labels*.|**boolean**|
|<a name="updateleadformadextensions"></a>UpdateLeadFormAdExtensions|Reserved.|**boolean**|
|<a name="updatelocationadextensions"></a>UpdateLocationAdExtensions|Import updates to existing location extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Location Extensions*.|**boolean**|
|<a name="updatelocationtargets"></a>UpdateLocationTargets|Import updates to existing location targets.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Targeting > Location targets*.|**boolean**|
|<a name="updatelogoadextensions"></a>UpdateLogoAdExtensions|Import updates to existing logo ad extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Logo Ad Extensions*.|**boolean**|
|<a name="updatenegativekeywordlists"></a>UpdateNegativeKeywordLists|Import updates to existing negative keyword lists.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Negative keyword lists*.|**boolean**|
|<a name="updatenegativesites"></a>UpdateNegativeSites|Import updates to negative sites for existing campaigns and ad groups.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Negative sites*.|**boolean**|
|<a name="updatepagefeeds"></a>UpdatePageFeeds|Import updates to existing page feeds.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Feeds > Page feeds*.|**boolean**|
|<a name="updatepriceadextensions"></a>UpdatePriceAdExtensions|Import updates to existing price extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Price Extensions*.|**boolean**|
|<a name="updateproductfilters"></a>UpdateProductFilters|When enabled this option updates product filters in shopping campaigns to match those currently in Google Ads.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Product filters*.|**boolean**|
|<a name="updatepromotionadextensions"></a>UpdatePromotionAdExtensions|Import updates to existing promotion extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Promotion Extensions*.|**boolean**|
|<a name="updatereviewadextensions"></a>UpdateReviewAdExtensions|Import updates to existing review extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Review Extensions*.|**boolean**|
|<a name="updatesitelinkadextensions"></a>UpdateSitelinkAdExtensions|Import updates to existing sitelink extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Sitelink Extensions*.|**boolean**|
|<a name="updatesitelinkurls"></a>UpdateSitelinkUrls|Import updates to existing Sitelink Extension URLs.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Sitelink Extension URLs*.|**boolean**|
|<a name="updatestatusforadgroups"></a>UpdateStatusForAdGroups|Import updates to the status of existing ad groups.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Status > Ad group status*.|**boolean**|
|<a name="updatestatusforads"></a>UpdateStatusForAds|Import updates to the status of existing ads.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Status > Ad status*.|**boolean**|
|<a name="updatestatusforcampaigns"></a>UpdateStatusForCampaigns|Import updates to the status of existing campaigns.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Status > Campaign status*.|**boolean**|
|<a name="updatestatusforkeywords"></a>UpdateStatusForKeywords|Import updates to the status of existing keywords.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Status > Keyword status*.|**boolean**|
|<a name="updatestructuredsnippetadextensions"></a>UpdateStructuredSnippetAdExtensions|Import updates to existing structured snippet extensions.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Ad extensions > Structured Snippet Extensions*.|**boolean**|
|<a name="updateurloptions"></a>UpdateUrlOptions|Import updates to the tracking templates, custom parameters, and final URL suffix of existing entities.<br/><br/>This option is only honored if [UpdateEntities](#updateentities) is also enabled.<br/><br/>This option is enabled by default, or effectively set to *true*. Set this element *false* to turn off this option.<br/><br/>This option is available in the Microsoft Advertising UI via *Import from Google Ads > Choose import options > What to import > Updates to existing items > Campaign settings > Tracking templates, custom parameters, and final URL suffixes*.|**boolean**|

The [GoogleImportOption](googleimportoption.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsimportoption"></a>Inherited Elements from ImportOption
The [GoogleImportOption](googleimportoption.md) object derives from the [ImportOption](importoption.md) object, and inherits the following elements: [ForwardCompatibilityMap](#forwardcompatibilitymap), [Type](#type). The descriptions below are specific to [GoogleImportOption](googleimportoption.md), and might not apply to other objects that inherit the same elements from the [ImportOption](importoption.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="type"></a>Type|The type of the import option.<br/><br/>This value is *GoogleImportOption* when you retrieve a Google import option.<br/><br/>For more information about import option types, see the [ImportOption Data Object Remarks](importoption.md#remarks).|**string**|

## <a name="remarks"></a>Remarks
When you update import options via [UpdateImportJobs](updateimportjobs.md) you can remove, update, or leave in place the prior search and replace settings. Remove and update fully replace any previous settings. 
- **Remove:** Create an empty [ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md) object
- **Update:** Create a [ImportSearchAndReplaceForStringProperty](importsearchandreplaceforstringproperty.md) and set properties that you want to use going forward
- **Retain:** Set the element null

```csharp
// Remove
SearchAndReplaceForCampaignNames = new ImportSearchAndReplaceForStringProperty{},
// Update
SearchAndReplaceForTrackingTemplates = new ImportSearchAndReplaceForStringProperty{
    ReplaceString = "replace",
    SearchString = "search"
},
// Retain prior settings
SearchAndDsaMixedCampaignAsSearchCampaign = null
```

The code above generates the following SOAP request message.

```xml
<!--Retain prior settings-->
<SearchAndDsaMixedCampaignAsSearchCampaign i:nil="true" />
<!--Remove-->
<SearchAndReplaceForCampaignNames>
    <ReplaceString i:nil="true" />
    <SearchString i:nil="true" />
</SearchAndReplaceForCampaignNames>
<!--Update-->
<SearchAndReplaceForTrackingTemplates>
    <ReplaceString>replace</ReplaceString>
    <SearchString>search</SearchString>
</SearchAndReplaceForTrackingTemplates>
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

