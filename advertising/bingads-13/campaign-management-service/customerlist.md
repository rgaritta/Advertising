---
title: CustomerList Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a CustomerList data object.
---
# CustomerList Data Object - Campaign Management
Defines a CustomerList data object.

> [!IMPORTANT]
> Before you create customer list data via Campaign Management API, you must first create one customer list audience and accept the terms and conditions in the Microsoft Advertising UI. The initial customer list doesn't need to contain any customer data, but you must select I ACCEPT. By selecting "I accept" you (1) agree that you are able to lawfully disclose audience details, which is personal data, to Microsoft and (2) accept the Customer Match Terms, the Microsoft Advertising Agreement, and the Microsoft Advertising policies. Microsoft will use the data that you upload in accordance with the [Customer Match Terms](https://go.microsoft.com/fwlink/?linkid=2106709).

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="CustomerList" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Audience">
      <xs:sequence />
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "AudienceNetworkSize": "LongValueHere",
  "CustomerShare": {
    "CustomerAccountShares": [
      {
        "AccountId": "LongValueHere",
        "Associations": [
          {
            "AssociationCount": "LongValueHere",
            "UsageType": "ValueHere"
          }
        ],
        "CustomerId": "LongValueHere"
      }
    ],
    "OwnerCustomerId": "LongValueHere"
  },
  "Description": "ValueHere",
  "ForwardCompatibilityMap": [
    {
      "key": "ValueHere",
      "value": "ValueHere"
    }
  ],
  "Id": "LongValueHere",
  "MembershipDuration": IntValueHere,
  "Name": "ValueHere",
  "ParentId": "LongValueHere",
  "Scope": "ValueHere",
  "SearchSize": "LongValueHere",
  "SupportedCampaignTypes": [
    "ValueHere"
  ],
  "Type": "CustomerList"
}
```

-----

## <a name="elements"></a>Elements

The [CustomerList](customerlist.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsaudience"></a>Inherited Elements from Audience
The [CustomerList](customerlist.md) object derives from the [Audience](audience.md) object, and inherits the following elements: [AudienceNetworkSize](#audiencenetworksize), [CustomerShare](#customershare), [Description](#description), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Id](#id), [MembershipDuration](#membershipduration), [Name](#name), [ParentId](#parentid), [Scope](#scope), [SearchSize](#searchsize), [SupportedCampaignTypes](#supportedcampaigntypes), [Type](#type). The descriptions below are specific to [CustomerList](customerlist.md), and might not apply to other objects that inherit the same elements from the [Audience](audience.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiencenetworksize"></a>AudienceNetworkSize|The total number of people who are active members of this audience in the Audience network. This gives you an idea of how many Audience network users you can target.<br/><br/>The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="customershare"></a>CustomerShare|Determines the list of customers and accounts that share the audience. Details include audience association counts.<br/><br/>Shared UET tags and audiences are only available for pilot customers. For an overview of sharing audiences and UET tags in a customer hierarchy, see the [Share Audiences and UET Tags](../guides/universal-event-tracking.md#hierarchy-share) technical guide.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. Set this element to null or empty to retain any existing customer account shares. To remove all customer account shares, set the [CustomerAccountShares](customershare.md#customeraccountshares) element of the [CustomerShare](customershare.md) object to null or empty. To remove a subset of customer account shares, specify the customer account shares that you want to keep in the [CustomerAccountShares](customershare.md#customeraccountshares) element of the [CustomerShare](customershare.md) object.|[CustomerShare](customershare.md)|
|<a name="description"></a>Description|The description of the audience. Use a description to help you remember what audience you are targeting.<br/><br/>The description can contain a maximum of 1,024 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *Audience* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Microsoft Advertising identifier of the audience.<br/><br/>**Add:** Read-only<br/>**Update:** Required and read-only|**long**|
|<a name="membershipduration"></a>MembershipDuration|When you create an audience, you can specify how far back in time Microsoft Advertising should look for actions that match your audience definition.<br/><br/>The minimum duration is 1 day and the maximum duration allowed is 390 days. You can also set the duration to -1 for no expiration.<br/><br/>**Add:** Optional. If not specified, the membership duration will be set to 30 by default.<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**int**|
|<a name="name"></a>Name|The name of the audience. The name can contain a maximum of 128 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="parentid"></a>ParentId|The Microsoft Advertising identifier of the account or customer. <br/><br/>If the *Scope* is set to *Account*, this is the account ID, and otherwise it is the customer ID.<br/><br/>**Add:** Required<br/>**Update:** Read-only. You cannot change the parent ID.|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/>If scope is set to *Account*, the audience can only be associated with campaigns and ad groups in one account i.e., via the [ParentId](#parentid). If scope is set to *Customer*, the audience can be associated with campaigns and ad groups in all of the customer's accounts.<br/><br/>**Add:** Required<br/>**Update:** Optional. You can change the scope from Account to Customer, but you cannot change the scope from Customer to Account.|[EntityScope](entityscope.md)|
|<a name="searchsize"></a>SearchSize|The total number of people who are active members of this audience in the Search network. This gives you an idea of how many search users you can target.<br/><br/>The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.<br/><br/>This property will be nil or empty for up to 48 hours while the audience is being built, for example if you add or update the customer list membership duration.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="supportedcampaigntypes"></a>SupportedCampaignTypes|The list of campaign types that support this audience.<br/><br/>Supported values are Audience, DynamicSearchAds, Search, and Shopping. New campaign types might be added in the future, so you should not take any dependency on a fixed set of values.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string** array|
|<a name="type"></a>Type|The type of the audience. This value is *CustomerList* when you retrieve a customer list audience. For more information about audience types, see the [Audience Data Object Remarks](audience.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AudienceType](audiencetype.md)|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[ApplyCustomerListItems](applycustomerlistitems.md)  
