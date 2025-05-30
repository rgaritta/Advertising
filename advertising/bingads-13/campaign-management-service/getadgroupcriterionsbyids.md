---
title: GetAdGroupCriterionsByIds Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Gets ad group criterions by identifiers and types.
dev_langs: 
- csharp
- java
- php
- python
---
# GetAdGroupCriterionsByIds Service Operation - Campaign Management
Gets ad group criterions by identifiers and types.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetAdGroupCriterionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterionids"></a>AdGroupCriterionIds|A list of unique identifiers that identify the criterions to get.<br/><br/>You can include up to 1,000 ad group criterion identifiers per request. <br/><br/>If this element is null, all criterions for the specified *AdGroupId* will be retrieved.|**long** array|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that owns the criterions to get.|**long**|
|<a name="criteriontype"></a>CriterionType|The type of criterion to get, for example *Webpage*. You can specify only one type. The *Targets* and *Audience* values are not allowed for this operation.|[AdGroupCriterionType](adgroupcriteriontype.md)|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|The list of additional properties that you want included within each returned ad group criterion. The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding elements will be included by default.<br/><br/>This request element is optional.|[CriterionAdditionalField](criterionadditionalfield.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdGroupCriterionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterions"></a>AdGroupCriterions|The list of criterions that correspond directly to the identifiers specified in the request. If an identifier in the list is not valid, the corresponding item in the response is set to null.|[AdGroupCriterion](adgroupcriterion.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetAdGroupCriterionsByIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetAdGroupCriterionsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AdGroupCriterionIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdGroupCriterionIds>
      <AdGroupId>ValueHere</AdGroupId>
      <CriterionType>ValueHere</CriterionType>
      <ReturnAdditionalFields i:nil="false">ValueHere</ReturnAdditionalFields>
    </GetAdGroupCriterionsByIdsRequest>
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
    <GetAdGroupCriterionsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AdGroupCriterions d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdGroupCriterion d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AdGroupId>ValueHere</AdGroupId>
          <Criterion d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--These fields are applicable if the derived type attribute is set to ProductPartition-->
            <Condition d4p1:nil="false">
              <Attribute d4p1:nil="false">ValueHere</Attribute>
              <Operand d4p1:nil="false">ValueHere</Operand>
              <Operator d4p1:nil="false">ValueHere</Operator>
            </Condition>
            <ParentCriterionId d4p1:nil="false">ValueHere</ParentCriterionId>
            <PartitionType>ValueHere</PartitionType>
            <!--These fields are applicable if the derived type attribute is set to HotelGroup-->
            <Listing d4p1:nil="false">
              <Attribute d4p1:nil="false">ValueHere</Attribute>
              <Operand d4p1:nil="false">ValueHere</Operand>
            </Listing>
            <ListingType>ValueHere</ListingType>
            <ParentCriterionId d4p1:nil="false">ValueHere</ParentCriterionId>
            <!--These fields are applicable if the derived type attribute is set to HotelAdvanceBookingWindowCriterion-->
            <MaxDays d4p1:nil="false">ValueHere</MaxDays>
            <MinDays d4p1:nil="false">ValueHere</MinDays>
            <!--These fields are applicable if the derived type attribute is set to HotelCheckInDateCriterion-->
            <EndDate d4p1:nil="false">ValueHere</EndDate>
            <StartDate d4p1:nil="false">ValueHere</StartDate>
            <!--This field is applicable if the derived type attribute is set to HotelCheckInDayCriterion-->
            <CheckInDay d4p1:nil="false">ValueHere</CheckInDay>
            <!--This field is applicable if the derived type attribute is set to HotelDateSelectionTypeCriterion-->
            <HotelDateSelectionType d4p1:nil="false">ValueHere</HotelDateSelectionType>
            <!--These fields are applicable if the derived type attribute is set to HotelLengthOfStayCriterion-->
            <MaxNights d4p1:nil="false">ValueHere</MaxNights>
            <MinNights d4p1:nil="false">ValueHere</MinNights>
            <!--This field is applicable if the derived type attribute is set to ProductScope-->
            <Conditions d4p1:nil="false">
              <ProductCondition>
                <Attribute d4p1:nil="false">ValueHere</Attribute>
                <Operand d4p1:nil="false">ValueHere</Operand>
                <Operator d4p1:nil="false">ValueHere</Operator>
              </ProductCondition>
            </Conditions>
            <!--This field is applicable if the derived type attribute is set to Webpage-->
            <Parameter d4p1:nil="false">
              <Conditions d4p1:nil="false">
                <WebpageCondition>
                  <Argument d4p1:nil="false">ValueHere</Argument>
                  <Operand>ValueHere</Operand>
                  <Operator d4p1:nil="false">ValueHere</Operator>
                </WebpageCondition>
              </Conditions>
              <CriterionName d4p1:nil="false">ValueHere</CriterionName>
            </Parameter>
            <!--This field is applicable if the derived type attribute is set to AgeCriterion-->
            <AgeRange d4p1:nil="false">ValueHere</AgeRange>
            <!--These fields are applicable if the derived type attribute is set to DeviceCriterion-->
            <DeviceName d4p1:nil="false">ValueHere</DeviceName>
            <OSName d4p1:nil="false">ValueHere</OSName>
            <!--These fields are applicable if the derived type attribute is set to DayTimeCriterion-->
            <Day d4p1:nil="false">ValueHere</Day>
            <FromHour d4p1:nil="false">ValueHere</FromHour>
            <FromMinute d4p1:nil="false">ValueHere</FromMinute>
            <ToHour d4p1:nil="false">ValueHere</ToHour>
            <ToMinute d4p1:nil="false">ValueHere</ToMinute>
            <!--This field is applicable if the derived type attribute is set to GenderCriterion-->
            <GenderType d4p1:nil="false">ValueHere</GenderType>
            <!--These fields are applicable if the derived type attribute is set to RadiusCriterion-->
            <LatitudeDegrees d4p1:nil="false">ValueHere</LatitudeDegrees>
            <LongitudeDegrees d4p1:nil="false">ValueHere</LongitudeDegrees>
            <Name d4p1:nil="false">ValueHere</Name>
            <Radius d4p1:nil="false">ValueHere</Radius>
            <RadiusUnit d4p1:nil="false">ValueHere</RadiusUnit>
            <!--These fields are applicable if the derived type attribute is set to LocationCriterion-->
            <DisplayName d4p1:nil="false">ValueHere</DisplayName>
            <EnclosedLocationIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
              <a1:long>ValueHere</a1:long>
            </EnclosedLocationIds>
            <LocationId d4p1:nil="false">ValueHere</LocationId>
            <LocationType d4p1:nil="false">ValueHere</LocationType>
            <!--This field is applicable if the derived type attribute is set to LocationIntentCriterion-->
            <IntentOption d4p1:nil="false">ValueHere</IntentOption>
            <!--These fields are applicable if the derived type attribute is set to AudienceCriterion-->
            <AudienceId d4p1:nil="false">ValueHere</AudienceId>
            <AudienceType d4p1:nil="false">ValueHere</AudienceType>
            <!--These fields are applicable if the derived type attribute is set to ProfileCriterion-->
            <ProfileId>ValueHere</ProfileId>
            <ProfileType>ValueHere</ProfileType>
            <!--This field is applicable if the derived type attribute is set to StoreCriterion-->
            <StoreId d4p1:nil="false">ValueHere</StoreId>
            <!--This field is applicable if the derived type attribute is set to DealCriterion-->
            <DealId>ValueHere</DealId>
            <!--This field is applicable if the derived type attribute is set to GenreCriterion-->
            <GenreId>ValueHere</GenreId>
            <!--These fields are applicable if the derived type attribute is set to PlacementCriterion-->
            <PlacementId>ValueHere</PlacementId>
            <PlacementName d4p1:nil="false">ValueHere</PlacementName>
          </Criterion>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to BiddableAdGroupCriterion-->
          <CriterionBid d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to RateBid-->
            <RateAmount d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </RateAmount>
            <!--This field is applicable if the derived type attribute is set to FixedBid-->
            <Amount>ValueHere</Amount>
            <!--This field is applicable if the derived type attribute is set to BidMultiplier-->
            <Multiplier>ValueHere</Multiplier>
          </CriterionBid>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls d4p1:nil="false">
            <AppUrl>
              <OsType d4p1:nil="false">ValueHere</OsType>
              <Url d4p1:nil="false">ValueHere</Url>
            </AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrlSuffix d4p1:nil="false">ValueHere</FinalUrlSuffix>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <CriterionCashback d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to CashbackAdjustment-->
            <CashbackPercent d4p1:nil="false">ValueHere</CashbackPercent>
          </CriterionCashback>
          <!--No additional fields are applicable if the derived type attribute is set to NegativeAdGroupCriterion-->
        </AdGroupCriterion>
      </AdGroupCriterions>
    </GetAdGroupCriterionsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdGroupCriterionsByIdsResponse> GetAdGroupCriterionsByIdsAsync(
	IList<long> adGroupCriterionIds,
	long adGroupId,
	AdGroupCriterionType criterionType,
	CriterionAdditionalField? returnAdditionalFields)
{
	var request = new GetAdGroupCriterionsByIdsRequest
	{
		AdGroupCriterionIds = adGroupCriterionIds,
		AdGroupId = adGroupId,
		CriterionType = criterionType,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdGroupCriterionsByIdsAsync(r), request));
}
```
```java
static GetAdGroupCriterionsByIdsResponse getAdGroupCriterionsByIds(
	ArrayOflong adGroupCriterionIds,
	java.lang.Long adGroupId,
	ArrayList<AdGroupCriterionType> criterionType,
	ArrayList<CriterionAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdGroupCriterionsByIdsRequest request = new GetAdGroupCriterionsByIdsRequest();

	request.setAdGroupCriterionIds(adGroupCriterionIds);
	request.setAdGroupId(adGroupId);
	request.setCriterionType(criterionType);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdGroupCriterionsByIds(request);
}
```
```php
static function GetAdGroupCriterionsByIds(
	$adGroupCriterionIds,
	$adGroupId,
	$criterionType,
	$returnAdditionalFields)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdGroupCriterionsByIdsRequest();

	$request->AdGroupCriterionIds = $adGroupCriterionIds;
	$request->AdGroupId = $adGroupId;
	$request->CriterionType = $criterionType;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdGroupCriterionsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdGroupCriterionsByIds(
	AdGroupCriterionIds=AdGroupCriterionIds,
	AdGroupId=AdGroupId,
	CriterionType=CriterionType,
	ReturnAdditionalFields=ReturnAdditionalFields)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```POST
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/AdGroupCriterions/QueryByIds
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/AdGroupCriterions/QueryByIds
```

-----

## <a name="request"></a>Request Elements
The *GetAdGroupCriterionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterionids"></a>AdGroupCriterionIds|A list of unique identifiers that identify the criterions to get.<br/><br/>You can include up to 1,000 ad group criterion identifiers per request. <br/><br/>If this element is null, all criterions for the specified *AdGroupId* will be retrieved.|**long** array|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that owns the criterions to get.|**long**|
|<a name="criteriontype"></a>CriterionType|The type of criterion to get, for example *Webpage*. You can specify only one type. The *Targets* and *Audience* values are not allowed for this operation.|[AdGroupCriterionType](adgroupcriteriontype.md)|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|The list of additional properties that you want included within each returned ad group criterion. The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding elements will be included by default.<br/><br/>This request element is optional.|[CriterionAdditionalField](criterionadditionalfield.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *GetAdGroupCriterionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupcriterions"></a>AdGroupCriterions|The list of criterions that correspond directly to the identifiers specified in the request. If an identifier in the list is not valid, the corresponding item in the response is set to null.|[AdGroupCriterion](adgroupcriterion.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "AdGroupCriterionIds": [
    "LongValueHere"
  ],
  "AdGroupId": "LongValueHere",
  "CriterionType": "ValueHere",
  "ReturnAdditionalFields": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

Below is an example that is applicable if the type of [AdGroupCriterion](adgroupcriterion.md) is [BiddableAdGroupCriterion](biddableadgroupcriterion.md), [Criterion](criterion.md) is [AgeCriterion](agecriterion.md), [CriterionBid](criterionbid.md) is [BidMultiplier](bidmultiplier.md), [CriterionCashback](criterioncashback.md) is [CashbackAdjustment](cashbackadjustment.md).

```json
{
  "AdGroupCriterions": [
    {
      "AdGroupId": "LongValueHere",
      "Criterion": {
        "Type": "AgeCriterion",
        "AgeRange": "ValueHere"
      },
      "Id": "LongValueHere",
      "Status": "ValueHere",
      "Type": "BiddableAdGroupCriterion",
      "CriterionBid": {
        "Type": "BidMultiplier",
        "Multiplier": DoubleValueHere
      },
      "CriterionCashback": {
        "Type": "CashbackAdjustment",
        "CashbackPercent": DoubleValueHere
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
  ]
}
```

## <a name="example"></a>Code Syntax
To call REST API through SDKs, you need to upgrade SDK to a certain version and configure the system parameters.The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md).
See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdGroupCriterionsByIdsResponse> GetAdGroupCriterionsByIdsAsync(
	IList<long> adGroupCriterionIds,
	long adGroupId,
	AdGroupCriterionType criterionType,
	CriterionAdditionalField? returnAdditionalFields)
{
	var request = new GetAdGroupCriterionsByIdsRequest
	{
		AdGroupCriterionIds = adGroupCriterionIds,
		AdGroupId = adGroupId,
		CriterionType = criterionType,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdGroupCriterionsByIdsAsync(r), request));
}
```
```java
static GetAdGroupCriterionsByIdsResponse getAdGroupCriterionsByIds(
	ArrayOflong adGroupCriterionIds,
	java.lang.Long adGroupId,
	ArrayList<AdGroupCriterionType> criterionType,
	ArrayList<CriterionAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdGroupCriterionsByIdsRequest request = new GetAdGroupCriterionsByIdsRequest();

	request.setAdGroupCriterionIds(adGroupCriterionIds);
	request.setAdGroupId(adGroupId);
	request.setCriterionType(criterionType);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdGroupCriterionsByIds(request);
}
```
```php
static function GetAdGroupCriterionsByIds(
	$adGroupCriterionIds,
	$adGroupId,
	$criterionType,
	$returnAdditionalFields)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdGroupCriterionsByIdsRequest();

	$request->AdGroupCriterionIds = $adGroupCriterionIds;
	$request->AdGroupId = $adGroupId;
	$request->CriterionType = $criterionType;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdGroupCriterionsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdGroupCriterionsByIds(
	AdGroupCriterionIds=AdGroupCriterionIds,
	AdGroupId=AdGroupId,
	CriterionType=CriterionType,
	ReturnAdditionalFields=ReturnAdditionalFields)
```

::: zone-end
