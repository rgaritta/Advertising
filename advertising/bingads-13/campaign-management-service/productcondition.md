---
title: ProductCondition Data Object - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a condition that determines whether a product is selected from a customer's Microsoft Merchant Center catalog file.
---
# ProductCondition Data Object - Campaign Management
Defines a condition that determines whether a product is selected from a customer's Microsoft Merchant Center catalog file.

You can use campaign level production conditions with Shopping campaigns, feed-based Audience campaigns, and Search campaigns with multimedia ads i.e., those campaigns that leverage a Microsoft Merchant Center [store ID](shoppingsetting.md#storeid). (Note: Not everyone has Search campaigns with multimedia ads yet. If you don't, don't worry - it's coming soon!) Ad group level product conditions can only be used with Shopping campaigns. Asset group level product conditions can only be used with Performance Max campaigns. The product scope allows you to choose which items from your catalog to include in the campaign e.g., filter by  brand or condition.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="ProductCondition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Attribute" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Operand" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Operator" nillable="true" type="xs:string">
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
  "Attribute": "ValueHere",
  "Operand": "ValueHere",
  "Operator": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [ProductCondition](productcondition.md) object has the following elements: [Attribute](#attribute), [Operand](#operand), [Operator](#operator).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="attribute"></a>Attribute|The condition's attribute value.<br/><br/>An attribute's value must exactly match the value specified in the customer's Microsoft Merchant Center catalog file.<br/><br/>The available *Attribute* and *Operand* values vary depending on the campaign type. For supported attribute and operand values, see [Remarks](#remarks) below.<br/><br/>**Add or Apply:** Required<br/>**Update:** Optional|**string**|
|<a name="operand"></a>Operand|The condition's operand. The operands implicitly include the equal operator. For example, read Brand as Brand=.<br/><br/>**Add or Apply:** Required<br/>**Update:** Optional|**string**|
|<a name="operator"></a>Operator|The rule item operator.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|

## <a name="remarks"></a>Remarks
For supported Product Condition (operand) and Product Value (attribute) per campaign type, see the tables below.

### <a name="productconditions-audience"></a>Product Conditions for Feed-Based Audience Campaigns
Multiple product conditions can be specified for each feed-based Audience campaign. Each condition is met if the product's attribute value equals the operand's attribute value. For example, if the operand is set to Brand and the attribute is set to Contoso, the condition is met if the value of the product catalog's Brand attribute is equal to Contoso.

|Product Condition (Operand)|Product Value (Attribute) Description|Business Rules|
|----------------|-------------------------|----------------------|
|Brand|The product's manufacturer, brand, or publisher.<br/><br/>A maximum of 1,000 characters.|The *Brand* operand may only be specified once per campaign product scope filter.|
|Condition|The condition of the product.<br/><br/>If operand is set to Condition, the supported attribute values that you can specify are *New*, *Used*, and *Refurbished*.|The *Condition* operand may only be specified once per campaign product scope filter.|
|ProductType1-5<br/><br/>Five product type operand values are available i.e. ProductType1, ProductType2, ProductType3, ProductType4, and ProductType5.|A product type or category defined by the merchant.<br/><br/>ProductType1 is the highest level product type, and ProductType5 is the lowest level or most granular product type.<br/><br/>A maximum of 100 characters.|Each of the product type operands may be used once per campaign product scope filter.<br/><br/>If you set the operand to a product type from 1 through 5, they must be specified in ascending order. For example, the operand can be set to "ProductType2" with attribute "Pet Supplies", if a higher level product partition has operand "ProductType1" with attribute "Animals & Pet Supplies".|
|CustomLabel0-4<br/><br/>Five custom label operand values are available i.e. CustomLabel0, CustomLabel1, CustomLabel2, CustomLabel3, and CustomLabel4.|A custom label defined by the merchant.<br/><br/>Custom labels e.g. CustomLabel0 and CustomLabel4 are not validated based on any hierarchy.<br/><br/>A maximum of 100 characters.|Each of the *CustomLabel* operands may be used once per campaign product scope filter.|

### <a name="productconditions-shopping"></a>Product Conditions for Shopping Campaigns
Multiple product conditions can be specified for each Microsoft Shopping campaign and ad group. Each condition is met if the product's attribute value equals the operand's attribute value. For example, if operand is set to Brand and attribute is set to Contoso, the condition is met if the value of the product catalog's Brand attribute is equal to Contoso.

In Shopping campaigns the product conditions can be set at campaign and ad group level. The following table describes Product Condition (operand) and Product Value (attribute) business rules for campaign [ProductScope](productscope.md) and ad group [ProductPartition](productpartition.md) objects.

|Product Condition (Operand)|Product Value (Attribute) Description|Campaign Product Scope Rules|Ad Group Product Partition Rules|
|----------------|-------------------------|----------------------|--------------------------|
|All|Must be null.|Not applicable.|For an ad group's product partitions, the root node must have operand set to "All" and attribute set to null or empty.|
|Brand|The product's manufacturer, brand, or publisher.<br/><br/>A maximum of 1,000 characters.|The *Brand* operand may only be specified once per campaign product scope filter.|The *Brand* operand may be used in multiple branches, but may only be specified once per branch.|
|CategoryL1-5<br/><br/>Five category operand values are available i.e. CategoryL1, CategoryL2, CategoryL3, CategoryL4, and CategoryL5.|A product category defined by the Microsoft Merchant Center store. Please see [Bing Category Taxonomy](https://go.microsoft.com/fwlink?LinkId=507666) for valid category values and taxonomy.<br/><br/>CategoryL0 is the highest level category, and CategoryL4 is the lowest level or most granular category.<br/><br/>A maximum of 100 characters.|Each of the *CategoryL* operands may be used once per campaign product scope filter.<br/><br/>If you specify a product condition with operand set to a product category from 1 through 5,<br/>they must be specified in ascending order. For example, you can set the operand to "CategoryL2" with attribute "Pet Supplies", if a preceding product condition has the operand "CategoryL1" with attribute "Animals & Pet Supplies".|Each of the *CategoryL* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *CategoryL1* and *CategoryL2*, but may not contain another node with the CategoryL2 operand.<br/><br/>If you set the operand to a product category from 1 through 5, they must be specified in ascending order. For example, the operand can be set to "CategoryL2" with attribute "Pet Supplies", if a higher level product partition has operand "CategoryL1" with attribute "Animals & Pet Supplies".<br/><br/>The prior level product category operand doesn't need to be specified in the immediate parent partition. For example a CategoryL2 condition could be specified for a product partition if the parent of its parent specified a CategoryL1 condition.|
|Channel|The Local Inventory Ads (LIA) channel.<br/><br/>Possible values include "Local Stores" and "Online".<br/><br/>If the campaign has not opted into [Local Inventory Ads](shoppingsetting.md#localinventoryadsenabled), all offers are by default Online only (Channel=Online) and Single-channel (ChannelExclusivity=Single-channel). For more information, see the [Local Inventory Ads](https://help.ads.microsoft.com/#apex/3/en/56858/1-500) help page.|The *Channel* operand may only be specified once per campaign product scope filter.|The *Channel* operand may be used in multiple branches, but may only be specified once per branch.|
|ChannelExclusivity|The Local Inventory Ads (LIA) channel exclusivity.<br/><br/>Possible values include "Single-channel" and "Multi-channel".<br/><br/>If the campaign has not opted into [Local Inventory Ads](shoppingsetting.md#localinventoryadsenabled), all offers are by default Online only (Channel=Online) and Single-channel (ChannelExclusivity=Single-channel). For more information, see the [Local Inventory Ads](https://help.ads.microsoft.com/#apex/3/en/56858/1-500) help page.|The *ChannelExclusivity* operand may only be specified once per campaign product scope filter.|The *ChannelExclusivity* operand may be used in multiple branches, but may only be specified once per branch.|
|Condition|The condition of the product.<br/><br/>If operand is set to Condition, the supported attribute values that you can specify are *New*, *Used*, and *Refurbished*.|The *Condition* operand may only be specified once per campaign product scope filter.|The *Condition* operand may be used in multiple branches, but may only be specified once per branch.|
|CustomLabel0-4<br/><br/>Five custom label operand values are available i.e. CustomLabel0, CustomLabel1, CustomLabel2, CustomLabel3, and CustomLabel4.|A custom label defined by the merchant.<br/><br/>Custom labels e.g. CustomLabel0 and CustomLabel4 are not validated based on any hierarchy.<br/><br/>A maximum of 100 characters.<br/><br/>This operand is not applicable with [Sponsored Products](../guides/product-ads.md#setup-cooperative).|Each of the *CustomLabel* operands may be used once per campaign product scope filter.|Each of the *CustomLabel* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *CustomLabel0* and *CustomLabel1*, but may not contain another node with the *CustomLabel1* operand.|
|GTIN|The Global Trade Item Number defined by the merchant.<br/><br/>The GTIN field has a limit of 50 characters, with each GTIN value having up to 14 digits.<br/><br/>This operand is only applicable with [Sponsored Products](../guides/product-ads.md#setup-cooperative).|The *GTIN* operand may only be specified once per campaign product scope filter.|The *GTIN* operand may be used in multiple branches, but may only be specified once per branch.|
|Id|The product identifier defined by the merchant.<br/><br/>A maximum of 1,000 characters.|The *Id* operand may only be specified once per campaign product scope filter.|The *Id* operand may be used in multiple branches, but may only be specified once per branch.|
|MPN|The Global Trade Item Number defined by the merchant.<br/><br/>A maximum of 70 characters.<br/><br/>This operand is only applicable with [Sponsored Products](../guides/product-ads.md#setup-cooperative).|The *MPN* operand may only be specified once per campaign product scope filter.|The *MPN* operand may be used in multiple branches, but may only be specified once per branch.|
|ProductType1-5<br/><br/>Five product type operand values are available i.e. ProductType1, ProductType2, ProductType3, ProductType4, and ProductType5.|A product type or category defined by the merchant.<br/><br/>ProductType1 is the highest level product type, and ProductType5 is the lowest level or most granular product type.<br/><br/>A maximum of 100 characters.<br/><br/>This operand is not applicable with [Sponsored Products](../guides/product-ads.md#setup-cooperative).|Each of the product type operands may be used once per campaign product scope filter.<br/><br/>If you specify a product condition with operand set to a product type from 1 through 5,<br/>they must be specified in ascending order. For example, you can set the operand to "ProductType2" with attribute "Pet Supplies", if a preceding product condition has the operand "ProductType1" with attribute "Animals & Pet Supplies".|Each of the *ProductType* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *ProductType1* and *ProductType2*, but may not contain another node with the *ProductType2* operand.<br/><br/>If you set the operand to a product type from 1 through 5, they must be specified in ascending order. For example, the operand can be set to "ProductType2" with attribute "Pet Supplies", if a higher level product partition has operand "ProductType1" with attribute "Animals & Pet Supplies".<br/><br/>The prior level product type operand doesn't need to be specified in the immediate parent partition. For example a ProductType2 condition could be specified for a product partition if the parent of its parent specified a ProductType1 condition.|

### <a name="productconditions-search"></a>Product Conditions for Search Campaigns

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry - it's coming soon!

Multiple product conditions can be specified for each Microsoft Search campaign with multimedia ads. Each condition is met if the product's attribute value equals the operand's attribute value. For example, if operand is set to Brand and attribute is set to Contoso, the condition is met if the value of the product catalog's Brand attribute is equal to Contoso.

In Search campaigns the product conditions can be set at campaign level. The following table describes Product Condition (operand) and Product Value (attribute) business rules for campaign [ProductScope](productscope.md) objects.

|Product Condition (Operand)|Product Value (Attribute) Description|Campaign Product Scope Rules|
|----------------|-------------------------|----------------------|
|Brand|The product's manufacturer, brand, or publisher.<br/><br/>A maximum of 1,000 characters.|The *Brand* operand may only be specified once per campaign product scope filter.|
|CategoryL1<br/><br/>One category operand value is available i.e. CategoryL1.|A product category defined by the Microsoft Merchant Center store. Please see [Bing Category Taxonomy](https://go.microsoft.com/fwlink?LinkId=507666) for valid category values and taxonomy.<br/><br/>A maximum of 100 characters.|Each of the *CategoryL* operands may be used once per campaign product scope filter.|
|Channel|The Local Inventory Ads (LIA) channel.<br/><br/>Possible values include "Local Stores" and "Online".<br/><br/>If the campaign has not opted into [Local Inventory Ads](shoppingsetting.md#localinventoryadsenabled), all offers are by default Online only (Channel=Online) and Single-channel (ChannelExclusivity=Single-channel). For more information, see the [Local Inventory Ads](https://help.ads.microsoft.com/#apex/3/en/56858/1-500) help page.|The *Channel* operand may only be specified once per campaign product scope filter.|
|ChannelExclusivity|The Local Inventory Ads (LIA) channel exclusivity.<br/><br/>Possible values include "Single-channel" and "Multi-channel".<br/><br/>If the campaign has not opted into [Local Inventory Ads](shoppingsetting.md#localinventoryadsenabled), all offers are by default Online only (Channel=Online) and Single-channel (ChannelExclusivity=Single-channel). For more information, see the [Local Inventory Ads](https://help.ads.microsoft.com/#apex/3/en/56858/1-500) help page.|The *ChannelExclusivity* operand may only be specified once per campaign product scope filter.|
|Condition|The condition of the product.<br/><br/>If operand is set to Condition, the supported attribute values that you can specify are *New*, *Used*, and *Refurbished*.|The *Condition* operand may only be specified once per campaign product scope filter.|
|CustomLabel0-4<br/><br/>Five custom label operand values are available i.e. CustomLabel0, CustomLabel1, CustomLabel2, CustomLabel3, and CustomLabel4.|A custom label defined by the merchant.<br/><br/>Custom labels e.g. CustomLabel0 and CustomLabel4 are not validated based on any hierarchy.<br/><br/>A maximum of 100 characters.<br/><br/>This operand is not applicable with [Sponsored Products](../guides/product-ads.md#setup-cooperative).|Each of the *CustomLabel* operands may be used once per campaign product scope filter.|
|Id|The product identifier defined by the merchant.<br/><br/>A maximum of 1,000 characters.|The *Id* operand may only be specified once per campaign product scope filter.|
|ProductType1<br/><br/>One product type operand values is available i.e. ProductType1.|A product type or category defined by the merchant.<br/><br/>ProductType1 is the highest level product type.<br/><br/>A maximum of 100 characters.<br/><br/>This operand is not applicable with [Sponsored Products](../guides/product-ads.md#setup-cooperative).|Each of the product type operands may be used once per campaign product scope filter.|

### <a name="productconditions-pmax"></a>Product Conditions for Performance Max Campaigns

Multiple product conditions can be specified for each Microsoft Performance Max asset group. Each condition is met if the product's attribute value equals the operand's attribute value. For example, if operand is set to Brand and attribute is set to Contoso, the condition is met if the value of the product catalog's Brand attribute is equal to Contoso.

In Performance Max campaigns the product conditions can be set only at asset group level. The following table describes Product Condition (operand) and Product Value (attribute) business rules for asset group [AssetGroupListingGroup](assetgrouplistinggroup.md) objects. 

|Product Condition (Operand)|Product Value (Attribute) Description|Asset Group Product Partition Rules |
|----------------|-------------------------|----------------------|
|All|Must be null.|For an asset group's product partitions, the root node must have operand set to *All* and attribute set to null or empty.|
|Brand|The product's manufacturer, brand, or publisher.<br/><br/>A maximum of 1,000 characters.|For an asset group's product partitions, the root node must have operand set to *All* and attribute set to null or empty.|
|CategoryL1-5<br/><br/>Five category operand values are available i.e. CategoryL1, CategoryL2, CategoryL3, CategoryL4, and CategoryL5.|A product category defined by the Microsoft Merchant Center store. Please see [Bing Category Taxonomy](https://go.microsoft.com/fwlink?LinkId=507666) for valid category values and taxonomy.<br/><br/>CategoryL0 is the highest level category, and CategoryL4 is the lowest level or most granular category.<br/><br/>A maximum of 100 characters.|Each of the *CategoryL* operands may be used in multiple branches.<br/><br/>Each of the *CategoryL* operands may be used in multiple branches but may only be specified once per branch. For example, one branch may contain *CategoryL1* and *CategoryL2*, but may not contain another node with the *CategoryL2* operand.<br/><br/>If you set the operand to a product category from 1 through 5, they must be specified in ascending order. For example, the operand can be set to *CategoryL2* with the attribute *Pet Supplies*, if a higher-level product partition has operand *CategoryL1* with attribute *Animals & Pet Supplies*.<br/><br/>The prior level product category operand doesn't need to be specified in the immediate parent partition. For example, a *CategoryL2* condition could be specified for a product partition if the parent of its parent specified a *CategoryL1* condition.|
|Channel|The Local Inventory Ads (LIA) channel.<br/><br/>Possible values include "Local Stores" and "Online".<br/><br/>If the campaign has not opted into [Local Inventory Ads](shoppingsetting.md#localinventoryadsenabled), all offers are by default Online only (Channel=Online) and Single-channel (ChannelExclusivity=Single-channel). For more information, see the [Local Inventory Ads](https://help.ads.microsoft.com/#apex/3/en/56858/1-500) help page.|The *Channel* operand may be used in multiple branches, but may only be specified once per branch.|
|ChannelExclusivity|The Local Inventory Ads (LIA) channel exclusivity.<br/><br/>Possible values include "Single-channel" and "Multi-channel".<br/><br/>If the campaign has not opted into [Local Inventory Ads](shoppingsetting.md#localinventoryadsenabled), all offers are by default Online only (Channel=Online) and Single-channel (ChannelExclusivity=Single-channel). For more information, see the [Local Inventory Ads](https://help.ads.microsoft.com/#apex/3/en/56858/1-500) help page.|The *ChannelExclusivity* operand may be used in multiple branches, but may only be specified once per branch.|
|Condition|The condition of the product.<br/><br/>If operand is set to Condition, the supported attribute values that you can specify are *New*, *Used*, and *Refurbished*.|The *Condition* operand may be used in multiple branches, but may only be specified once per branch.|
|CustomLabel0-4<br/><br/>Five custom label operand values are available i.e. CustomLabel0, CustomLabel1, CustomLabel2, CustomLabel3, and CustomLabel4.|A custom label defined by the merchant.<br/><br/>Custom labels e.g. CustomLabel0 and CustomLabel4 are not validated based on any hierarchy.<br/><br/>A maximum of 100 characters.|Each of the *CustomLabel* operands may be used in multiple branches, but may only be specified once per branch. For example, one branch may contain *CustomLabel0* and *CustomLabel1*, but may not contain another node with the *CustomLabel1* operand.|
|Id|The product identifier defined by the merchant.<br/><br/>A maximum of 1,000 characters.|The *Id* operand may be used in multiple branches, but may only be specified once per branch.|
|ProductType1-5<br/><br/>Five product type operand values are available i.e. ProductType1, ProductType2, ProductType3, ProductType4, and ProductType5.|A product type or category defined by the merchant.<br/><br/>ProductType1 is the highest level product type, and ProductType5 is the lowest level or most granular product type.<br/><br/>A maximum of 100 characters.|Each of the *ProductType* operands may be used in multiple branches, but may only be specified once per branch. For example one branch may contain *ProductType1* and *ProductType2*, but may not contain another node with the *ProductType2* operand.<br/><br/>If you set the operand to a product type from 1 through 5, they must be specified in ascending order. For example, the operand can be set to *ProductType2* with attribute *Pet Supplies*, if a higher-level product partition has operand *ProductType1* with attribute *Animals & Pet Supplies*.<br/><br/>The prior level product type operand doesn't need to be specified in the immediate parent partition. For example, a *ProductType2* condition could be specified for a product partition if the parent of its parent specified a *ProductType1* condition.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AssetGroupListingGroup](assetgrouplistinggroup.md)  
[ProductPartition](productpartition.md)  
[ProductScope](productscope.md)  
