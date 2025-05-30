---
title: Keyword Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a keyword.
---
# Keyword Data Object - Campaign Management
Defines a keyword.

Keywords are the words or phrases searched on when looking for a product or service. For example, keywords could be any of the following:

- Shoes
- Boats cruises vacation
- Tennis lessons in New York

As shown above, a keyword can be just a single word, several words, or even a phrase. In the context of search advertising, all of these are simply referred to as a keyword.

> [!IMPORTANT]
> As of April 2021, you cannot set any bid strategies for ad groups or keywords. If you attempt to set bid strategies for ad groups or keywords, the request will be ignored without error. Ad groups and keywords will inherit their campaign's bid strategy.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="Keyword" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Bid" nillable="true" type="tns:Bid" />
    <xs:element minOccurs="0" name="BiddingScheme" nillable="true" type="tns:BiddingScheme" />
    <xs:element minOccurs="0" name="DestinationUrl" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="EditorialStatus" nillable="true" type="tns:KeywordEditorialStatus" />
    <xs:element minOccurs="0" name="FinalAppUrls" nillable="true" type="tns:ArrayOfAppUrl" />
    <xs:element xmlns:q33="http://schemas.microsoft.com/2003/10/Serialization/Arrays" minOccurs="0" name="FinalMobileUrls" nillable="true" type="q33:ArrayOfstring" />
    <xs:element minOccurs="0" name="FinalUrlSuffix" nillable="true" type="xs:string" />
    <xs:element xmlns:q34="http://schemas.microsoft.com/2003/10/Serialization/Arrays" minOccurs="0" name="FinalUrls" nillable="true" type="q34:ArrayOfstring" />
    <xs:element xmlns:q35="http://schemas.datacontract.org/2004/07/System.Collections.Generic" minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q35:ArrayOfKeyValuePairOfstringstring" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="MatchType" nillable="true" type="tns:MatchType" />
    <xs:element minOccurs="0" name="Param1" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Param2" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Param3" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:KeywordStatus" />
    <xs:element minOccurs="0" name="Text" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TrackingUrlTemplate" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="UrlCustomParameters" nillable="true" type="tns:CustomParameters" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "Bid": {
    "Amount": DoubleValueHere
  },
  "BiddingScheme": {
    "Type": "CommissionBiddingScheme",
    "CommissionRate": DoubleValueHere
  },
  "DestinationUrl": "ValueHere",
  "EditorialStatus": "ValueHere",
  "FinalAppUrls": [
    {
      "OsType": "ValueHere",
      "Url": "ValueHere"
    }
  ],
  "FinalMobileUrls": [
    "ValueHere"
  ],
  "FinalUrls": [
    "ValueHere"
  ],
  "FinalUrlSuffix": "ValueHere",
  "ForwardCompatibilityMap": [
    {
      "key": "ValueHere",
      "value": "ValueHere"
    }
  ],
  "Id": "LongValueHere",
  "MatchType": "ValueHere",
  "Param1": "ValueHere",
  "Param2": "ValueHere",
  "Param3": "ValueHere",
  "Status": "ValueHere",
  "Text": "ValueHere",
  "TrackingUrlTemplate": "ValueHere",
  "UrlCustomParameters": {
    "Parameters": [
      {
        "Key": "ValueHere",
        "Value": "ValueHere"
      }
    ]
  }
}
```

-----

## <a name="elements"></a>Elements

The [Keyword](keyword.md) object has the following elements: [Bid](#bid), [BiddingScheme](#biddingscheme), [DestinationUrl](#destinationurl), [EditorialStatus](#editorialstatus), [FinalAppUrls](#finalappurls), [FinalMobileUrls](#finalmobileurls), [FinalUrls](#finalurls), [FinalUrlSuffix](#finalurlsuffix), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Id](#id), [MatchType](#matchtype), [Param1](#param1), [Param2](#param2), [Param3](#param3), [Status](#status), [Text](#text), [TrackingUrlTemplate](#trackingurltemplate), [UrlCustomParameters](#urlcustomparameters).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bid"></a>Bid|The maximum amount that you want to pay each time someone clicks your ad.<br/><br/>You bid against other advertisers using the same keyword, so in general, higher bids help get your ad to display in more desirable locations on the search results page.<br/><br/>Instead of using the default ad group level bid, you can set custom bids for each keyword. Custom bids for keywords override the ad group default bid for those specific keywords. With custom bids, you can focus your time and money on the most profitable keywords but will need to spend more time on managing the individual bids.<br/><br/>If the keyword level bid is not set, the Ad Group [CpcBid](adgroup.md#cpcbid) is used. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. To delete the keyword bid and use the [AdGroup](adgroup.md) default match type bid, set the [Amount](bid.md#amount) element of the [Bid](bid.md) object to null.|[Bid](bid.md)|
|<a name="biddingscheme"></a>BiddingScheme|The bid strategy type for how you want to manage your bids.<br/><br/>For details about supported bid strategies per campaign type, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).<br/><br/>**NOTE:** As of April 2021, you cannot set any bid strategies for ad groups or keywords. If you attempt to set bid strategies for ad groups or keywords, the request will be ignored without error. Ad groups and keywords will inherit their campaign's bid strategy.<br/><br/>**Add:** Optional. If you do not set this element, then [InheritFromParentBiddingScheme](inheritfromparentbiddingscheme.md) is used by default.<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|[BiddingScheme](biddingscheme.md)|
|<a name="destinationurl"></a>DestinationUrl|The URL of the webpage to take the user to when they click the ad. The keyword's destination URL is used if specified; otherwise, the ad's destination URL is used.<br/><br/>**Important:** As of November 2018 the keyword destination URL cannot be added or updated. You can use [Final URLs](#finalurls) instead. For more details see [Migrating your keyword destination URLs to final URLs](https://about.ads.microsoft.com/en-us/blog/post/august-2018/migrating-your-keyword-destination-urls-to-final-urls).<br/><br/>**Add:** Not allowed<br/>**Update:** Not allowed|**string**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the keyword, which indicates whether the keyword is pending review, has been approved, or has been disapproved.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeywordEditorialStatus](keywordeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|For future use.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL. The keyword's final mobile URL is used if specified; otherwise, the ad's final mobile URL is used.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL. The keyword's final URL is used if specified; otherwise, the ad's final URL is used.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile. Also note that if the [TrackingUrlTemplate](#trackingurltemplate) or [UrlCustomParameters](#urlcustomparameters) elements are set, then at least one final URL is required. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string** array|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. For more details and validation rules see [Final URL Suffix](../guides/url-tracking-upgraded-urls.md#finalurlsuffixvalidation) in the technical guides.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The system-generated identifier of the keyword.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="matchtype"></a>MatchType|The type of match to compare the keyword and the user's search term.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|[MatchType](matchtype.md)|
|<a name="param1"></a>Param1|The string to use as the substitution value in an ad if the ad's title, text, display URL, or destination URL contains the {Param1} dynamic substitution string.<br/><br/>Although you can use {Param1} to specify an ad's destination URL, you are encouraged not to. Instead, you should set the keyword's *DestinationUrl* element.<br/><br/>The string can contain a maximum of 1,022 characters. The actual limit depends on the length of the element that references the substitution string. For example, the length of a text ad's title can contain a maximum of 25 characters.<br/><br/>When implementing dynamic text in your ad copy you should provide a default string e.g. {Param1:default} that the system will use if Param1 for a keyword is null or empty, or if including the Param1 substitution value will cause the expanded string to exceed the element's limit; otherwise the ad will not serve with this keyword. For more information, see the Microsoft Advertising help article [Automatically customize your ads with dynamic text parameters](https://help.ads.microsoft.com/#apex/3/en/50811/1).<br/><br/>Also note that if the ad group only has one ad, and if that ad uses {Param1} but does not provide a default string e.g. {Param1:default}, then you must supply a valid *Param1* value for that substitution. Otherwise this keyword cannot be added or updated.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="param2"></a>Param2|The string to use as the substitution value in an ad if the title, text, display URL, or destination URL contains the {Param2} dynamic substitution string.<br/><br/>Typically, you use the {Param2} substitution string in the title or text (ad copy description) elements of an ad.<br/><br/>The string can contain a maximum of 70 characters. The actual limit depends on the length of the element that references the substitution string. For example, the length of a text ad's title can contain a maximum of 25 characters.<br/><br/>When implementing dynamic text in your ad copy you should provide a default string e.g. {Param2:default} that the system will use if Param2 for a keyword is null or empty, or if including the Param2 substitution value will cause the expanded string to exceed the element's limit; otherwise the ad will not serve with this keyword. For more information, see the Microsoft Advertising help article [Automatically customize your ads with dynamic text parameters](https://help.ads.microsoft.com/#apex/3/en/50811/1).<br/><br/>Also note that if the ad group only has one ad, and if that ad uses {Param2} but does not provide a default string e.g. {Param2:default}, then you must supply a valid *Param2* value for that substitution. Otherwise this keyword cannot be added or updated.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="param3"></a>Param3|The string to use as the substitution value in an ad if the title, text, display URL, or destination URL contains the {Param3} dynamic substitution string.<br/><br/>Typically, you use the {Param3} substitution string in the title or text (ad copy description) elements of an ad.<br/><br/>The string can contain a maximum of 70 characters. The actual limit depends on the length of the element that references the substitution string. For example, the length of a text ad's title can contain a maximum of 25 characters.<br/><br/>When implementing dynamic text in your ad copy you should provide a default string e.g. {Param3:default} that the system will use if Param3 for a keyword is null or empty, or if including the Param3 substitution value will cause the expanded string to exceed the element's limit; otherwise the ad will not serve with this keyword. For more information, see the Microsoft Advertising help article [Automatically customize your ads with dynamic text parameters](https://help.ads.microsoft.com/#apex/3/en/50811/1).<br/><br/>Also note that if the ad group only has one ad, and if that ad uses {Param3} but does not provide a default string e.g. {Param3:default}, then you must supply a valid *Param3* value for that substitution. Otherwise this keyword cannot be added or updated.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="status"></a>Status|The keyword's status. By default, the status is set to Active.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|[KeywordStatus](keywordstatus.md)|
|<a name="text"></a>Text|The keyword text. The text can contain a maximum of 100 characters. You should specify the keyword in the locale of the *Language* value that you specified for the ad group to which the keyword belongs.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**string**|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all *FinalUrls* and *FinalMobileUrls*.<br/><br/>The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Microsoft Advertising help article [What tracking or URL parameters can I use?](https://help.ads.microsoft.com/#apex/3/en/56799/2)<br/>- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Limits](../guides/entity-hierarchy-limits.md).<br/>- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.<br/>- Microsoft Advertising does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *`https://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}`* and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br/><br/>Microsoft Advertising will accept the first 8 [CustomParameter](customparameter.md) objects that you include within the [CustomParameters](customparameters.md) object, and if you include more than 8 custom parameters an error will be returned. Each [CustomParameter](customparameter.md) includes [Key](customparameter.md#key) and [Value](customparameter.md#value) elements.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. Set the *UrlCustomParameters* element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the [Parameters](customparameters.md#parameters) element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the [Parameters](customparameters.md#parameters) element of the [CustomParameters](customparameters.md) object.|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AddKeywords](addkeywords.md)  
[GetKeywordsByAdGroupId](getkeywordsbyadgroupid.md)  
[GetKeywordsByEditorialStatus](getkeywordsbyeditorialstatus.md)  
[GetKeywordsByIds](getkeywordsbyids.md)  
[UpdateKeywords](updatekeywords.md)  
