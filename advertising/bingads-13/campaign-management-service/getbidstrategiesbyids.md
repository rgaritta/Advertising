---
title: GetBidStrategiesByIds Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Gets bid strategies in an account's portfolio bid strategy library.
dev_langs: 
- csharp
- java
- php
- python
---
# GetBidStrategiesByIds Service Operation - Campaign Management
Gets bid strategies in an account's portfolio bid strategy library.

A portfolio bid strategy is an automated bidding feature that manages bidding across multiple campaigns that are all working toward the same goal. To include a campaign in the portfolio bid strategy, set the campaign's [BidStrategyId](campaign.md#bidstrategyid) to the bid strategy [Id](bidstrategy.md#id).  

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry - it's coming soon!

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetBidStrategiesByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidstrategyids"></a>BidStrategyIds|A list of unique bid strategy identifiers that identify the bid strategies to get.<br/><br/>You can include a maximum of 100 IDs in a single call.<br/><br/>The bid strategy IDs must be in the same account that you specified in the required *CustomerAccountId* header element.<br/><br/>If you leave this element nil or empty, then the operation will return all portfolio bid strategies in the account.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBidStrategiesByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidstrategies"></a>BidStrategies|An array of [BidStrategy](bidstrategy.md) objects that corresponds directly to the bid strategy identifiers that you specified in the request. Items of the list may be returned as null. For each list index where a bid strategy was not retrieved, the corresponding element will be null.|[BidStrategy](bidstrategy.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetBidStrategiesByIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetBidStrategiesByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <BidStrategyIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </BidStrategyIds>
    </GetBidStrategiesByIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetBidStrategiesByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <BidStrategies d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BidStrategy>
          <AssociatedCampaignType d4p1:nil="false">ValueHere</AssociatedCampaignType>
          <AssociationCount d4p1:nil="false">ValueHere</AssociationCount>
          <BiddingScheme d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to MaxClicksBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--These fields are applicable if the derived type attribute is set to MaxConversionsBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetCpa d4p1:nil="false">ValueHere</TargetCpa>
            <!--These fields are applicable if the derived type attribute is set to TargetCpaBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetCpa d4p1:nil="false">ValueHere</TargetCpa>
            <!--This field is applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <ManualCpc d4p1:nil="false">ValueHere</ManualCpc>
            <!--No additional fields are applicable if the derived type attribute is set to EnhancedCpcBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpvBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpmBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType d4p1:nil="false">ValueHere</InheritedBidStrategyType>
            <!--These fields are applicable if the derived type attribute is set to TargetRoasBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetRoas d4p1:nil="false">ValueHere</TargetRoas>
            <!--This field is applicable if the derived type attribute is set to MaxRoasBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--This field is applicable if the derived type attribute is set to MaxConversionValueBiddingScheme-->
            <TargetRoas d4p1:nil="false">ValueHere</TargetRoas>
            <!--These fields are applicable if the derived type attribute is set to TargetImpressionShareBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetAdPosition d4p1:nil="false">ValueHere</TargetAdPosition>
            <TargetImpressionShare d4p1:nil="false">ValueHere</TargetImpressionShare>
            <!--This field is applicable if the derived type attribute is set to PercentCpcBiddingScheme-->
            <MaxPercentCpc d4p1:nil="false">ValueHere</MaxPercentCpc>
            <!--This field is applicable if the derived type attribute is set to CommissionBiddingScheme-->
            <CommissionRate d4p1:nil="false">ValueHere</CommissionRate>
            <!--This field is applicable if the derived type attribute is set to ManualCpaBiddingScheme-->
            <ManualCpi d4p1:nil="false">ValueHere</ManualCpi>
            <!--This field is applicable if the derived type attribute is set to CostPerSaleBiddingScheme-->
            <TargetCostPerSale d4p1:nil="false">ValueHere</TargetCostPerSale>
          </BiddingScheme>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
        </BidStrategy>
      </BidStrategies>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e279="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e279:KeyValuePairOfstringstring>
              <e279:key d4p1:nil="false">ValueHere</e279:key>
              <e279:value d4p1:nil="false">ValueHere</e279:value>
            </e279:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialError-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchError>
      </PartialErrors>
    </GetBidStrategiesByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBidStrategiesByIdsResponse> GetBidStrategiesByIdsAsync(
	IList<long> bidStrategyIds)
{
	var request = new GetBidStrategiesByIdsRequest
	{
		BidStrategyIds = bidStrategyIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetBidStrategiesByIdsAsync(r), request));
}
```
```java
static GetBidStrategiesByIdsResponse getBidStrategiesByIds(
	ArrayOflong bidStrategyIds) throws RemoteException, Exception
{
	GetBidStrategiesByIdsRequest request = new GetBidStrategiesByIdsRequest();

	request.setBidStrategyIds(bidStrategyIds);

	return CampaignManagementService.getService().getBidStrategiesByIds(request);
}
```
```php
static function GetBidStrategiesByIds(
	$bidStrategyIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetBidStrategiesByIdsRequest();

	$request->BidStrategyIds = $bidStrategyIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetBidStrategiesByIds($request);
}
```
```python
response=campaignmanagement_service.GetBidStrategiesByIds(
	BidStrategyIds=BidStrategyIds)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```POST
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/BidStrategies/QueryByIds
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/BidStrategies/QueryByIds
```

-----

## <a name="request"></a>Request Elements
The *GetBidStrategiesByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidstrategyids"></a>BidStrategyIds|A list of unique bid strategy identifiers that identify the bid strategies to get.<br/><br/>You can include a maximum of 100 IDs in a single call.<br/><br/>The bid strategy IDs must be in the same account that you specified in the required *CustomerAccountId* header element.<br/><br/>If you leave this element nil or empty, then the operation will return all portfolio bid strategies in the account.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *GetBidStrategiesByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidstrategies"></a>BidStrategies|An array of [BidStrategy](bidstrategy.md) objects that corresponds directly to the bid strategy identifiers that you specified in the request. Items of the list may be returned as null. For each list index where a bid strategy was not retrieved, the corresponding element will be null.|[BidStrategy](bidstrategy.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "BidStrategyIds": [
    "LongValueHere"
  ]
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

Below is an example that is applicable if the type of [BiddingScheme](biddingscheme.md) is [CommissionBiddingScheme](commissionbiddingscheme.md), [BatchError](batcherror.md) is [EditorialError](editorialerror.md).

```json
{
  "BidStrategies": [
    {
      "AssociatedCampaignType": "ValueHere",
      "AssociationCount": IntValueHere,
      "BiddingScheme": {
        "Type": "CommissionBiddingScheme",
        "CommissionRate": DoubleValueHere
      },
      "Id": "LongValueHere",
      "Name": "ValueHere"
    }
  ],
  "PartialErrors": [
    {
      "Code": IntValueHere,
      "Details": "ValueHere",
      "ErrorCode": "ValueHere",
      "FieldPath": "ValueHere",
      "ForwardCompatibilityMap": [
        {
          "key": "ValueHere",
          "value": "ValueHere"
        }
      ],
      "Index": IntValueHere,
      "Message": "ValueHere",
      "Type": "EditorialError",
      "Appealable": "ValueHere",
      "DisapprovedText": "ValueHere",
      "Location": "ValueHere",
      "PublisherCountry": "ValueHere",
      "ReasonCode": IntValueHere
    }
  ]
}
```

## <a name="example"></a>Code Syntax
To call REST API through SDKs, you need to upgrade SDK to a certain version and configure the system parameters.The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md).
See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBidStrategiesByIdsResponse> GetBidStrategiesByIdsAsync(
	IList<long> bidStrategyIds)
{
	var request = new GetBidStrategiesByIdsRequest
	{
		BidStrategyIds = bidStrategyIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetBidStrategiesByIdsAsync(r), request));
}
```
```java
static GetBidStrategiesByIdsResponse getBidStrategiesByIds(
	ArrayOflong bidStrategyIds) throws RemoteException, Exception
{
	GetBidStrategiesByIdsRequest request = new GetBidStrategiesByIdsRequest();

	request.setBidStrategyIds(bidStrategyIds);

	return CampaignManagementService.getService().getBidStrategiesByIds(request);
}
```
```php
static function GetBidStrategiesByIds(
	$bidStrategyIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetBidStrategiesByIdsRequest();

	$request->BidStrategyIds = $bidStrategyIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetBidStrategiesByIds($request);
}
```
```python
response=campaignmanagement_service.GetBidStrategiesByIds(
	BidStrategyIds=BidStrategyIds)
```

::: zone-end
