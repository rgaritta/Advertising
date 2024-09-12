---
title: GetBidOpportunities Service Operation Test - Ad Insight
ms.service: bing-ads
ms.subservice: ad-insight-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
zone_pivot_groups: api-reference
description: Gets the keyword bid opportunities of the specified ad group.(test)
dev_langs: 
- csharp
- java
- php
- python
---
# GetBidOpportunities Service Operation Test - Ad Insight
Gets the keyword bid opportunities of the specified ad group.

The estimates are based on the last 7 days of performance data, and not a prediction or guarantee of future performance.

> [!NOTE]
> This operation is optimized for search campaigns using the manual CPC bid strategy. With the sunset of manual CPC for search campaigns in April 2021, this operation is deprecated. 

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetBidOpportunitiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group for which you want to determine keyword bid opportunities.<br/><br/>If this element is nil or empty, the operation will return all bid opportunities for the specified campaign.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that owns the ad group specified in the *AdGroupId* element.<br/><br/>If this element is nil or empty, then the *AdGroupId* must also be nil or empty, and the operation will return all bid opportunities for the account.|**long**|
|<a name="opportunitytype"></a>OpportunityType|Determines the type or types of bid opportunities corresponding to your ad position goals.<br/><br/>The operation will only return opportunities if there's a suggested increase within 100% of your current bid that will help you achieve the specified goal.|[BidOpportunityType](bidopportunitytype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBidOpportunitiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="opportunities"></a>Opportunities|An array of *BidOpportunity* objects that identifies the keywords whose clicks and impressions may increase if you were to apply the suggested match-type bid value.<br/><br/>Currently up to 1,000 list items can be returned although the limit is subject to change.|[BidOpportunity](bidopportunity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/AdInsight/v13">
    <Action mustUnderstand="1">GetBidOpportunities</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetBidOpportunitiesRequest xmlns="https://bingads.microsoft.com/AdInsight/v13">
      <AdGroupId i:nil="false">ValueHere</AdGroupId>
      <CampaignId i:nil="false">ValueHere</CampaignId>
      <OpportunityType>ValueHere</OpportunityType>
    </GetBidOpportunitiesRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/AdInsight/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetBidOpportunitiesResponse xmlns="https://bingads.microsoft.com/AdInsight/v13">
      <Opportunities d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BidOpportunity>
          <AdGroupId>ValueHere</AdGroupId>
          <CampaignId>ValueHere</CampaignId>
          <CurrentBid>ValueHere</CurrentBid>
          <EstimatedIncreaseInClicks>ValueHere</EstimatedIncreaseInClicks>
          <EstimatedIncreaseInCost>ValueHere</EstimatedIncreaseInCost>
          <EstimatedIncreaseInImpressions>ValueHere</EstimatedIncreaseInImpressions>
          <KeywordId>ValueHere</KeywordId>
          <MatchType d4p1:nil="false">ValueHere</MatchType>
          <SuggestedBid>ValueHere</SuggestedBid>
        </BidOpportunity>
      </Opportunities>
    </GetBidOpportunitiesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBidOpportunitiesResponse> GetBidOpportunitiesAsync(
	long? adGroupId,
	long? campaignId,
	BidOpportunityType opportunityType)
{
	var request = new GetBidOpportunitiesRequest
	{
		AdGroupId = adGroupId,
		CampaignId = campaignId,
		OpportunityType = opportunityType
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetBidOpportunitiesAsync(r), request));
}
```
```java
static GetBidOpportunitiesResponse getBidOpportunities(
	java.lang.Long adGroupId,
	java.lang.Long campaignId,
	ArrayList<BidOpportunityType> opportunityType) throws RemoteException, Exception
{
	GetBidOpportunitiesRequest request = new GetBidOpportunitiesRequest();

	request.setAdGroupId(adGroupId);
	request.setCampaignId(campaignId);
	request.setOpportunityType(opportunityType);

	return AdInsightService.getService().getBidOpportunities(request);
}
```
```php
static function GetBidOpportunities(
	$adGroupId,
	$campaignId,
	$opportunityType)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetBidOpportunitiesRequest();

	$request->AdGroupId = $adGroupId;
	$request->CampaignId = $campaignId;
	$request->OpportunityType = $opportunityType;

	return $GLOBALS['AdInsightProxy']->GetService()->GetBidOpportunities($request);
}
```
```python
response=adinsight_service.GetBidOpportunities(
	AdGroupId=AdGroupId,
	CampaignId=CampaignId,
	OpportunityType=OpportunityType)
```

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```Post
https://adinsight.api.bingads.microsoft.com/AdInsight/v13/BidOpportunities/Query
```

# [Sandbox URL](#tab/sandbox)

```Post
https://adinsight.api.sandbox.bingads.microsoft.com/AdInsight/v13/BidOpportunities/Query
```

-----

## <a name="request"></a>Request Elements
The *GetBidOpportunitiesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group for which you want to determine keyword bid opportunities.<br/><br/>If this element is nil or empty, the operation will return all bid opportunities for the specified campaign.|**long**|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that owns the ad group specified in the *AdGroupId* element.<br/><br/>If this element is nil or empty, then the *AdGroupId* must also be nil or empty, and the operation will return all bid opportunities for the account.|**long**|
|<a name="opportunitytype"></a>OpportunityType|Determines the type or types of bid opportunities corresponding to your ad position goals.<br/><br/>The operation will only return opportunities if there's a suggested increase within 100% of your current bid that will help you achieve the specified goal.|[BidOpportunityType](bidopportunitytype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBidOpportunitiesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="opportunities"></a>Opportunities|An array of *BidOpportunity* objects that identifies the keywords whose clicks and impressions may increase if you were to apply the suggested match-type bid value.<br/><br/>Currently up to 1,000 list items can be returned although the limit is subject to change.|[BidOpportunity](bidopportunity.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "AdGroupId": "LongValueHere",
  "CampaignId": "LongValueHere",
  "OpportunityType": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

```json
{
  "Opportunities": [
    {
      "AdGroupId": "LongValueHere",
      "CampaignId": "LongValueHere",
      "CurrentBid": DoubleValueHere,
      "EstimatedIncreaseInClicks": DoubleValueHere,
      "EstimatedIncreaseInCost": DoubleValueHere,
      "EstimatedIncreaseInImpressions": "LongValueHere",
      "KeywordId": "LongValueHere",
      "MatchType": "ValueHere",
      "SuggestedBid": DoubleValueHere
    }
  ]
}
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetBidOpportunitiesResponse> GetBidOpportunitiesAsync(
	long? adGroupId,
	long? campaignId,
	BidOpportunityType opportunityType)
{
	var request = new GetBidOpportunitiesRequest
	{
		AdGroupId = adGroupId,
		CampaignId = campaignId,
		OpportunityType = opportunityType
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetBidOpportunitiesAsync(r), request));
}
```
```java
static GetBidOpportunitiesResponse getBidOpportunities(
	java.lang.Long adGroupId,
	java.lang.Long campaignId,
	ArrayList<BidOpportunityType> opportunityType) throws RemoteException, Exception
{
	GetBidOpportunitiesRequest request = new GetBidOpportunitiesRequest();

	request.setAdGroupId(adGroupId);
	request.setCampaignId(campaignId);
	request.setOpportunityType(opportunityType);

	return AdInsightService.getService().getBidOpportunities(request);
}
```
```php
static function GetBidOpportunities(
	$adGroupId,
	$campaignId,
	$opportunityType)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetBidOpportunitiesRequest();

	$request->AdGroupId = $adGroupId;
	$request->CampaignId = $campaignId;
	$request->OpportunityType = $opportunityType;

	return $GLOBALS['AdInsightProxy']->GetService()->GetBidOpportunities($request);
}
```
```python
response=adinsight_service.GetBidOpportunities(
	AdGroupId=AdGroupId,
	CampaignId=CampaignId,
	OpportunityType=OpportunityType)
```

::: zone-end