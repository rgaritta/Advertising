---
title: GetClipchampTemplates Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Gets the specified clip champ templates.
dev_langs: 
- csharp
- java
- php
- python
---
# GetClipchampTemplates Service Operation - Campaign Management
Gets the specified clip champ templates.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetClipchampTemplatesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="locale"></a>Locale|Reserved.|**string**|
|<a name="maxadscount"></a>MaxAdsCount|Reserved.|**int**|
|<a name="mock"></a>Mock|Reserved.|**boolean**|
|<a name="templatefilter"></a>TemplateFilter|Reserved.|[VideoTemplateFilter](videotemplatefilter.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetClipchampTemplatesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="templates"></a>Templates|Reserved.|[ClipchampTemplateInfo](clipchamptemplateinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetClipchampTemplates</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetClipchampTemplatesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <Mock i:nil="false">ValueHere</Mock>
      <MaxAdsCount i:nil="false">ValueHere</MaxAdsCount>
      <TemplateFilter i:nil="false">
        <AspectRatios i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:string>ValueHere</a1:string>
        </AspectRatios>
        <Durations i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:int>ValueHere</a1:int>
        </Durations>
        <MaxMediaAssetCount>ValueHere</MaxMediaAssetCount>
        <MaxTextAssetCount>ValueHere</MaxTextAssetCount>
        <TemplateIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:string>ValueHere</a1:string>
        </TemplateIds>
        <Themes i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:string>ValueHere</a1:string>
        </Themes>
      </TemplateFilter>
      <Locale i:nil="false">ValueHere</Locale>
    </GetClipchampTemplatesRequest>
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
    <GetClipchampTemplatesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <Templates d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <ClipchampTemplateInfo>
          <AspectRatio d4p1:nil="false">ValueHere</AspectRatio>
          <Duration>ValueHere</Duration>
          <NumberOfImages>ValueHere</NumberOfImages>
          <NumberOfLogos>ValueHere</NumberOfLogos>
          <NumberOfText>ValueHere</NumberOfText>
          <TemplateDescription d4p1:nil="false">ValueHere</TemplateDescription>
          <TemplateId d4p1:nil="false">ValueHere</TemplateId>
          <TemplateName d4p1:nil="false">ValueHere</TemplateName>
          <TemplatePreviewUrl d4p1:nil="false">ValueHere</TemplatePreviewUrl>
          <TemplateThumbnailUrl d4p1:nil="false">ValueHere</TemplateThumbnailUrl>
          <Themes d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Themes>
        </ClipchampTemplateInfo>
      </Templates>
    </GetClipchampTemplatesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetClipchampTemplatesResponse> GetClipchampTemplatesAsync(
	bool? mock,
	int? maxAdsCount,
	VideoTemplateFilter templateFilter,
	string locale)
{
	var request = new GetClipchampTemplatesRequest
	{
		Mock = mock,
		MaxAdsCount = maxAdsCount,
		TemplateFilter = templateFilter,
		Locale = locale
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetClipchampTemplatesAsync(r), request));
}
```
```java
static GetClipchampTemplatesResponse getClipchampTemplates(
	boolean mock,
	int maxAdsCount,
	VideoTemplateFilter templateFilter,
	java.lang.String locale) throws RemoteException, Exception
{
	GetClipchampTemplatesRequest request = new GetClipchampTemplatesRequest();

	request.setMock(mock);
	request.setMaxAdsCount(maxAdsCount);
	request.setTemplateFilter(templateFilter);
	request.setLocale(locale);

	return CampaignManagementService.getService().getClipchampTemplates(request);
}
```
```php
static function GetClipchampTemplates(
	$mock,
	$maxAdsCount,
	$templateFilter,
	$locale)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetClipchampTemplatesRequest();

	$request->Mock = $mock;
	$request->MaxAdsCount = $maxAdsCount;
	$request->TemplateFilter = $templateFilter;
	$request->Locale = $locale;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetClipchampTemplates($request);
}
```
```python
response=campaignmanagement_service.GetClipchampTemplates(
	Mock=Mock,
	MaxAdsCount=MaxAdsCount,
	TemplateFilter=TemplateFilter,
	Locale=Locale)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```POST
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/ClipchampTemplates/Query
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/ClipchampTemplates/Query
```

-----

## <a name="request"></a>Request Elements
The *GetClipchampTemplatesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="locale"></a>Locale|Reserved.|**string**|
|<a name="maxadscount"></a>MaxAdsCount|Reserved.|**int**|
|<a name="mock"></a>Mock|Reserved.|**boolean**|
|<a name="templatefilter"></a>TemplateFilter|Reserved.|[VideoTemplateFilter](videotemplatefilter.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *GetClipchampTemplatesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="templates"></a>Templates|Reserved.|[ClipchampTemplateInfo](clipchamptemplateinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "Mock": "ValueHere",
  "MaxAdsCount": IntValueHere,
  "TemplateFilter": {
    "AspectRatios": [
      "ValueHere"
    ],
    "Durations": [
      IntValueHere
    ],
    "MaxMediaAssetCount": IntValueHere,
    "MaxTextAssetCount": IntValueHere,
    "TemplateIds": [
      "ValueHere"
    ],
    "Themes": [
      "ValueHere"
    ]
  },
  "Locale": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

```json
{
  "Templates": [
    {
      "AspectRatio": "ValueHere",
      "Duration": IntValueHere,
      "NumberOfImages": IntValueHere,
      "NumberOfLogos": IntValueHere,
      "NumberOfText": IntValueHere,
      "TemplateDescription": "ValueHere",
      "TemplateId": "ValueHere",
      "TemplateName": "ValueHere",
      "TemplatePreviewUrl": "ValueHere",
      "TemplateThumbnailUrl": "ValueHere",
      "Themes": [
        "ValueHere"
      ]
    }
  ]
}
```

## <a name="example"></a>Code Syntax
To call REST API through SDKs, you need to upgrade SDK to a certain version and configure the system parameters.The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md).
See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetClipchampTemplatesResponse> GetClipchampTemplatesAsync(
	bool? mock,
	int? maxAdsCount,
	VideoTemplateFilter templateFilter,
	string locale)
{
	var request = new GetClipchampTemplatesRequest
	{
		Mock = mock,
		MaxAdsCount = maxAdsCount,
		TemplateFilter = templateFilter,
		Locale = locale
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetClipchampTemplatesAsync(r), request));
}
```
```java
static GetClipchampTemplatesResponse getClipchampTemplates(
	boolean mock,
	int maxAdsCount,
	VideoTemplateFilter templateFilter,
	java.lang.String locale) throws RemoteException, Exception
{
	GetClipchampTemplatesRequest request = new GetClipchampTemplatesRequest();

	request.setMock(mock);
	request.setMaxAdsCount(maxAdsCount);
	request.setTemplateFilter(templateFilter);
	request.setLocale(locale);

	return CampaignManagementService.getService().getClipchampTemplates(request);
}
```
```php
static function GetClipchampTemplates(
	$mock,
	$maxAdsCount,
	$templateFilter,
	$locale)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetClipchampTemplatesRequest();

	$request->Mock = $mock;
	$request->MaxAdsCount = $maxAdsCount;
	$request->TemplateFilter = $templateFilter;
	$request->Locale = $locale;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetClipchampTemplates($request);
}
```
```python
response=campaignmanagement_service.GetClipchampTemplates(
	Mock=Mock,
	MaxAdsCount=MaxAdsCount,
	TemplateFilter=TemplateFilter,
	Locale=Locale)
```

::: zone-end
