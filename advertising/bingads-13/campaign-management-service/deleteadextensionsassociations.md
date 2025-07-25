---
title: DeleteAdExtensionsAssociations Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Removes the specified association from the respective campaigns or ad groups.
dev_langs: 
- csharp
- java
- php
- python
---
# DeleteAdExtensionsAssociations Service Operation - Campaign Management
Removes the specified association from the respective campaigns or ad groups.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *DeleteAdExtensionsAssociationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the extensions.|**long**|
|<a name="adextensionidtoentityidassociations"></a>AdExtensionIdToEntityIdAssociations|The list of ad extensions that are associated with campaigns or ad groups before calling this  operation.<br/><br/>You can specify a maximum of 100 associations to delete or remove.|[AdExtensionIdToEntityIdAssociation](adextensionidtoentityidassociation.md) array|
|<a name="associationtype"></a>AssociationType|The entity type or types associated with an ad extension.|[AssociationType](associationtype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteAdExtensionsAssociationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">DeleteAdExtensionsAssociations</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <DeleteAdExtensionsAssociationsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AccountId>ValueHere</AccountId>
      <AdExtensionIdToEntityIdAssociations i:nil="false">
        <AdExtensionIdToEntityIdAssociation>
          <AdExtensionId>ValueHere</AdExtensionId>
          <EntityId>ValueHere</EntityId>
        </AdExtensionIdToEntityIdAssociation>
      </AdExtensionIdToEntityIdAssociations>
      <AssociationType>ValueHere</AssociationType>
    </DeleteAdExtensionsAssociationsRequest>
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
    <DeleteAdExtensionsAssociationsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e159="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e159:KeyValuePairOfstringstring>
              <e159:key d4p1:nil="false">ValueHere</e159:key>
              <e159:value d4p1:nil="false">ValueHere</e159:value>
            </e159:KeyValuePairOfstringstring>
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
    </DeleteAdExtensionsAssociationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteAdExtensionsAssociationsResponse> DeleteAdExtensionsAssociationsAsync(
	long accountId,
	IList<AdExtensionIdToEntityIdAssociation> adExtensionIdToEntityIdAssociations,
	AssociationType associationType)
{
	var request = new DeleteAdExtensionsAssociationsRequest
	{
		AccountId = accountId,
		AdExtensionIdToEntityIdAssociations = adExtensionIdToEntityIdAssociations,
		AssociationType = associationType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.DeleteAdExtensionsAssociationsAsync(r), request));
}
```
```java
static DeleteAdExtensionsAssociationsResponse deleteAdExtensionsAssociations(
	java.lang.Long accountId,
	ArrayOfAdExtensionIdToEntityIdAssociation adExtensionIdToEntityIdAssociations,
	AssociationType associationType) throws RemoteException, Exception
{
	DeleteAdExtensionsAssociationsRequest request = new DeleteAdExtensionsAssociationsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionIdToEntityIdAssociations(adExtensionIdToEntityIdAssociations);
	request.setAssociationType(associationType);

	return CampaignManagementService.getService().deleteAdExtensionsAssociations(request);
}
```
```php
static function DeleteAdExtensionsAssociations(
	$accountId,
	$adExtensionIdToEntityIdAssociations,
	$associationType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new DeleteAdExtensionsAssociationsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionIdToEntityIdAssociations = $adExtensionIdToEntityIdAssociations;
	$request->AssociationType = $associationType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->DeleteAdExtensionsAssociations($request);
}
```
```python
response=campaignmanagement_service.DeleteAdExtensionsAssociations(
	AccountId=AccountId,
	AdExtensionIdToEntityIdAssociations=AdExtensionIdToEntityIdAssociations,
	AssociationType=AssociationType)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```DELETE
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/AdExtensionsAssociations
```

# [Sandbox URL](#tab/sandbox)

```DELETE
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/AdExtensionsAssociations
```

-----

## <a name="request"></a>Request Elements
The *DeleteAdExtensionsAssociationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the extensions.|**long**|
|<a name="adextensionidtoentityidassociations"></a>AdExtensionIdToEntityIdAssociations|The list of ad extensions that are associated with campaigns or ad groups before calling this  operation.<br/><br/>You can specify a maximum of 100 associations to delete or remove.|[AdExtensionIdToEntityIdAssociation](adextensionidtoentityidassociation.md) array|
|<a name="associationtype"></a>AssociationType|The entity type or types associated with an ad extension.|[AssociationType](associationtype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *DeleteAdExtensionsAssociationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

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
  "AccountId": "LongValueHere",
  "AdExtensionIdToEntityIdAssociations": [
    {
      "AdExtensionId": "LongValueHere",
      "EntityId": "LongValueHere"
    }
  ],
  "AssociationType": "ValueHere"
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
public async Task<DeleteAdExtensionsAssociationsResponse> DeleteAdExtensionsAssociationsAsync(
	long accountId,
	IList<AdExtensionIdToEntityIdAssociation> adExtensionIdToEntityIdAssociations,
	AssociationType associationType)
{
	var request = new DeleteAdExtensionsAssociationsRequest
	{
		AccountId = accountId,
		AdExtensionIdToEntityIdAssociations = adExtensionIdToEntityIdAssociations,
		AssociationType = associationType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.DeleteAdExtensionsAssociationsAsync(r), request));
}
```
```java
static DeleteAdExtensionsAssociationsResponse deleteAdExtensionsAssociations(
	java.lang.Long accountId,
	ArrayOfAdExtensionIdToEntityIdAssociation adExtensionIdToEntityIdAssociations,
	AssociationType associationType) throws RemoteException, Exception
{
	DeleteAdExtensionsAssociationsRequest request = new DeleteAdExtensionsAssociationsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionIdToEntityIdAssociations(adExtensionIdToEntityIdAssociations);
	request.setAssociationType(associationType);

	return CampaignManagementService.getService().deleteAdExtensionsAssociations(request);
}
```
```php
static function DeleteAdExtensionsAssociations(
	$accountId,
	$adExtensionIdToEntityIdAssociations,
	$associationType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new DeleteAdExtensionsAssociationsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionIdToEntityIdAssociations = $adExtensionIdToEntityIdAssociations;
	$request->AssociationType = $associationType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->DeleteAdExtensionsAssociations($request);
}
```
```python
response=campaignmanagement_service.DeleteAdExtensionsAssociations(
	AccountId=AccountId,
	AdExtensionIdToEntityIdAssociations=AdExtensionIdToEntityIdAssociations,
	AssociationType=AssociationType)
```

::: zone-end
