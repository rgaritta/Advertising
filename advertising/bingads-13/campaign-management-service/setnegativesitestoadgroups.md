---
title: SetNegativeSitesToAdGroups Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Sets the negative site URLs directly to ad groups.
dev_langs: 
- csharp
- java
- php
- python
---
# SetNegativeSitesToAdGroups Service Operation - Campaign Management
Sets the negative site URLs directly to ad groups. 

This operation replaces any negative sites that were previously assigned directly to the ad groups. 

Negative site URLs specified at the ad group level are used instead of any negative site URLs specified at the campaign level. If you associate any [website exclusion lists](placementexclusionlist.md) with an ad account, the list of [negative sites](negativesite.md) are used in addition to the [campaign negative sites](campaignnegativesites.md) or [ad group negative sites](adgroupnegativesites.md). 

The operation does not add negative sites to a shared website exclusion list. See [AddListItemsToSharedList](addlistitemstosharedlist.md) for more information. 

> [!TIP] 
> For an overview, see the [Negative Sites](../guides/negative-sites.md) technical guide. 

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *SetNegativeSitesToAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupnegativesites"></a>AdGroupNegativeSites|An array of [AdGroupNegativeSites](adgroupnegativesites.md) objects that identify the ad groups to update with the specified negative site URLs.<br/><br/>The array can contain a maximum of 5,000 objects.<br/><br/>The total number of URLs that you can specify per request for all ad groups combined is 30,000. For example, if you specify 2,500 URLs per ad group, the maximum number of [AdGroupNegativeSites](adgroupnegativesites.md) objects that you should pass is 12.|[AdGroupNegativeSites](adgroupnegativesites.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SetNegativeSitesToAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">SetNegativeSitesToAdGroups</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <SetNegativeSitesToAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <CampaignId>ValueHere</CampaignId>
      <AdGroupNegativeSites i:nil="false">
        <AdGroupNegativeSites>
          <AdGroupId>ValueHere</AdGroupId>
          <NegativeSites i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </NegativeSites>
        </AdGroupNegativeSites>
      </AdGroupNegativeSites>
    </SetNegativeSitesToAdGroupsRequest>
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
    <SetNegativeSitesToAdGroupsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e387="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e387:KeyValuePairOfstringstring>
              <e387:key d4p1:nil="false">ValueHere</e387:key>
              <e387:value d4p1:nil="false">ValueHere</e387:value>
            </e387:KeyValuePairOfstringstring>
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
    </SetNegativeSitesToAdGroupsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SetNegativeSitesToAdGroupsResponse> SetNegativeSitesToAdGroupsAsync(
	long campaignId,
	IList<AdGroupNegativeSites> adGroupNegativeSites)
{
	var request = new SetNegativeSitesToAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroupNegativeSites = adGroupNegativeSites
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.SetNegativeSitesToAdGroupsAsync(r), request));
}
```
```java
static SetNegativeSitesToAdGroupsResponse setNegativeSitesToAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroupNegativeSites adGroupNegativeSites) throws RemoteException, Exception
{
	SetNegativeSitesToAdGroupsRequest request = new SetNegativeSitesToAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroupNegativeSites(adGroupNegativeSites);

	return CampaignManagementService.getService().setNegativeSitesToAdGroups(request);
}
```
```php
static function SetNegativeSitesToAdGroups(
	$campaignId,
	$adGroupNegativeSites)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new SetNegativeSitesToAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroupNegativeSites = $adGroupNegativeSites;

	return $GLOBALS['CampaignManagementProxy']->GetService()->SetNegativeSitesToAdGroups($request);
}
```
```python
response=campaignmanagement_service.SetNegativeSitesToAdGroups(
	CampaignId=CampaignId,
	AdGroupNegativeSites=AdGroupNegativeSites)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```POST
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/NegativeSites/SetToAdGroups
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/NegativeSites/SetToAdGroups
```

-----

## <a name="request"></a>Request Elements
The *SetNegativeSitesToAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupnegativesites"></a>AdGroupNegativeSites|An array of [AdGroupNegativeSites](adgroupnegativesites.md) objects that identify the ad groups to update with the specified negative site URLs.<br/><br/>The array can contain a maximum of 5,000 objects.<br/><br/>The total number of URLs that you can specify per request for all ad groups combined is 30,000. For example, if you specify 2,500 URLs per ad group, the maximum number of [AdGroupNegativeSites](adgroupnegativesites.md) objects that you should pass is 12.|[AdGroupNegativeSites](adgroupnegativesites.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *SetNegativeSitesToAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "CampaignId": "LongValueHere",
  "AdGroupNegativeSites": [
    {
      "AdGroupId": "LongValueHere",
      "NegativeSites": [
        "ValueHere"
      ]
    }
  ]
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

Below is an example that is applicable if the type of [BatchError](batcherror.md) is [EditorialError](editorialerror.md).

```json
{
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
public async Task<SetNegativeSitesToAdGroupsResponse> SetNegativeSitesToAdGroupsAsync(
	long campaignId,
	IList<AdGroupNegativeSites> adGroupNegativeSites)
{
	var request = new SetNegativeSitesToAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroupNegativeSites = adGroupNegativeSites
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.SetNegativeSitesToAdGroupsAsync(r), request));
}
```
```java
static SetNegativeSitesToAdGroupsResponse setNegativeSitesToAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroupNegativeSites adGroupNegativeSites) throws RemoteException, Exception
{
	SetNegativeSitesToAdGroupsRequest request = new SetNegativeSitesToAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroupNegativeSites(adGroupNegativeSites);

	return CampaignManagementService.getService().setNegativeSitesToAdGroups(request);
}
```
```php
static function SetNegativeSitesToAdGroups(
	$campaignId,
	$adGroupNegativeSites)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new SetNegativeSitesToAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroupNegativeSites = $adGroupNegativeSites;

	return $GLOBALS['CampaignManagementProxy']->GetService()->SetNegativeSitesToAdGroups($request);
}
```
```python
response=campaignmanagement_service.SetNegativeSitesToAdGroups(
	CampaignId=CampaignId,
	AdGroupNegativeSites=AdGroupNegativeSites)
```

::: zone-end
