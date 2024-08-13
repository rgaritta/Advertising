---
title: GetAssetGroupListingGroupsByIds Service Operation Test - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
zone_pivot_groups: api-reference
description: Retrieves the specified AssetGroupListingGroups.(test)
dev_langs: 
- csharp
- java
- php
- python
---
# GetAssetGroupListingGroupsByIds Service Operation Test - Campaign Management
Retrieves the specified AssetGroupListingGroups.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetAssetGroupListingGroupsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="assetgroupid"></a>AssetGroupId|The ID of the AssetGroup. |**long**|
|<a name="assetgrouplistinggroupids"></a>AssetGroupListingGroupIds|A list of identifiers that identify the listing groups that had the action applied. The list of identifiers corresponds directly to the list of listing groups in the request. <br /><br />If any listing group action failed, then all remaining listing group actions will fail, and all elements in this list will be null.  |**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAssetGroupListingGroupsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="assetgrouplistinggroups"></a>AssetGroupListingGroups|The list of listing groups that correspond directly to the identifiers specified in the request. If an identifier in the list is not valid, the corresponding item in the response is set to null. |[AssetGroupListingGroup](assetgrouplistinggroup.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetAssetGroupListingGroupsByIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetAssetGroupListingGroupsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AssetGroupId>ValueHere</AssetGroupId>
      <AssetGroupListingGroupIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AssetGroupListingGroupIds>
    </GetAssetGroupListingGroupsByIdsRequest>
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
    <GetAssetGroupListingGroupsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AssetGroupListingGroups d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AssetGroupListingGroup>
          <AssetGroupId>ValueHere</AssetGroupId>
          <AssetGroupListingType>ValueHere</AssetGroupListingType>
          <Dimension d4p1:nil="false">
            <Attribute d4p1:nil="false">ValueHere</Attribute>
            <Operand d4p1:nil="false">ValueHere</Operand>
            <Operator d4p1:nil="false">ValueHere</Operator>
          </Dimension>
          <Id d4p1:nil="false">ValueHere</Id>
          <IsExcluded>ValueHere</IsExcluded>
          <ParentListingGroupId d4p1:nil="false">ValueHere</ParentListingGroupId>
        </AssetGroupListingGroup>
      </AssetGroupListingGroups>
    </GetAssetGroupListingGroupsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAssetGroupListingGroupsByIdsResponse> GetAssetGroupListingGroupsByIdsAsync(
	long assetGroupId,
	IList<long> assetGroupListingGroupIds)
{
	var request = new GetAssetGroupListingGroupsByIdsRequest
	{
		AssetGroupId = assetGroupId,
		AssetGroupListingGroupIds = assetGroupListingGroupIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAssetGroupListingGroupsByIdsAsync(r), request));
}
```
```java
static GetAssetGroupListingGroupsByIdsResponse getAssetGroupListingGroupsByIds(
	java.lang.Long assetGroupId,
	ArrayOflong assetGroupListingGroupIds) throws RemoteException, Exception
{
	GetAssetGroupListingGroupsByIdsRequest request = new GetAssetGroupListingGroupsByIdsRequest();

	request.setAssetGroupId(assetGroupId);
	request.setAssetGroupListingGroupIds(assetGroupListingGroupIds);

	return CampaignManagementService.getService().getAssetGroupListingGroupsByIds(request);
}
```
```php
static function GetAssetGroupListingGroupsByIds(
	$assetGroupId,
	$assetGroupListingGroupIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAssetGroupListingGroupsByIdsRequest();

	$request->AssetGroupId = $assetGroupId;
	$request->AssetGroupListingGroupIds = $assetGroupListingGroupIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAssetGroupListingGroupsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAssetGroupListingGroupsByIds(
	AssetGroupId=AssetGroupId,
	AssetGroupListingGroupIds=AssetGroupListingGroupIds)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```Post
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/AssetGroupListingGroups/QueryByIds
```

# [Sandbox URL](#tab/sandbox)

```Post
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/AssetGroupListingGroups/QueryByIds
```

-----

## <a name="request"></a>Request Elements
The *GetAssetGroupListingGroupsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="assetgroupid"></a>AssetGroupId|The ID of the AssetGroup. |**long**|
|<a name="assetgrouplistinggroupids"></a>AssetGroupListingGroupIds|A list of identifiers that identify the listing groups that had the action applied. The list of identifiers corresponds directly to the list of listing groups in the request. <br /><br />If any listing group action failed, then all remaining listing group actions will fail, and all elements in this list will be null.  |**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAssetGroupListingGroupsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="assetgrouplistinggroups"></a>AssetGroupListingGroups|The list of listing groups that correspond directly to the identifiers specified in the request. If an identifier in the list is not valid, the corresponding item in the response is set to null. |[AssetGroupListingGroup](assetgrouplistinggroup.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "AssetGroupId": "ValueHere",
  "AssetGroupListingGroupIds": [
    "ValueHere"
  ]
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

```json
{
  "AssetGroupListingGroups": [
    {
      "AssetGroupId": "ValueHere",
      "AssetGroupListingType": "ValueHere",
      "Dimension": {
        "Attribute": "ValueHere",
        "Operand": "ValueHere",
        "Operator": "ValueHere"
      },
      "Id": "ValueHere",
      "IsExcluded": "ValueHere",
      "ParentListingGroupId": "ValueHere"
    }
  ]
}
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAssetGroupListingGroupsByIdsResponse> GetAssetGroupListingGroupsByIdsAsync(
	long assetGroupId,
	IList<long> assetGroupListingGroupIds)
{
	var request = new GetAssetGroupListingGroupsByIdsRequest
	{
		AssetGroupId = assetGroupId,
		AssetGroupListingGroupIds = assetGroupListingGroupIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAssetGroupListingGroupsByIdsAsync(r), request));
}
```
```java
static GetAssetGroupListingGroupsByIdsResponse getAssetGroupListingGroupsByIds(
	java.lang.Long assetGroupId,
	ArrayOflong assetGroupListingGroupIds) throws RemoteException, Exception
{
	GetAssetGroupListingGroupsByIdsRequest request = new GetAssetGroupListingGroupsByIdsRequest();

	request.setAssetGroupId(assetGroupId);
	request.setAssetGroupListingGroupIds(assetGroupListingGroupIds);

	return CampaignManagementService.getService().getAssetGroupListingGroupsByIds(request);
}
```
```php
static function GetAssetGroupListingGroupsByIds(
	$assetGroupId,
	$assetGroupListingGroupIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAssetGroupListingGroupsByIdsRequest();

	$request->AssetGroupId = $assetGroupId;
	$request->AssetGroupListingGroupIds = $assetGroupListingGroupIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAssetGroupListingGroupsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAssetGroupListingGroupsByIds(
	AssetGroupId=AssetGroupId,
	AssetGroupListingGroupIds=AssetGroupListingGroupIds)
```

::: zone-end