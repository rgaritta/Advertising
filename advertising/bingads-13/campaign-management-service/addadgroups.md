---
title: AddAdGroups Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Adds new ad groups to a specified campaign.
dev_langs: 
- csharp
- java
- php
- python
---
# AddAdGroups Service Operation - Campaign Management
Adds new ad groups to a specified campaign.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *AddAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroups"></a>AdGroups|An array of [AdGroup](adgroup.md) objects to add to the specified campaign.<br/><br/>You can add a maximum of 1,000 ad groups in a single call. Each campaign can have up to 20,000 ad groups.|[AdGroup](adgroup.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to add the ad groups to.|**long**|
|<a name="returninheritedbidstrategytypes"></a>ReturnInheritedBidStrategyTypes|Reserved for future use.|**boolean**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupids"></a>AdGroupIds|A list of unique system identifiers corresponding to the ad groups that were added.<br/><br/>The list of identifiers corresponds directly to the list of ad groups in the request. Items of the list may be returned as null. For each list index where an ad group was not added, the corresponding element will be null.|**long** array|
|<a name="inheritedbidstrategytypes"></a>InheritedBidStrategyTypes|Reserved for future use.|**string** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">AddAdGroups</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <AddAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <CampaignId>ValueHere</CampaignId>
      <AdGroups i:nil="false">
        <AdGroup>
          <AdRotation i:nil="false">
            <EndDate i:nil="false">ValueHere</EndDate>
            <StartDate i:nil="false">ValueHere</StartDate>
            <Type i:nil="false">ValueHere</Type>
          </AdRotation>
          <AudienceAdsBidAdjustment i:nil="false">ValueHere</AudienceAdsBidAdjustment>
          <BiddingScheme i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <ManualCpc i:nil="false">ValueHere</ManualCpc>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpvBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpmBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType i:nil="false">ValueHere</InheritedBidStrategyType>
            <!--This field is applicable if the derived type attribute is set to PercentCpcBiddingScheme-->
            <MaxPercentCpc i:nil="false">ValueHere</MaxPercentCpc>
            <!--This field is applicable if the derived type attribute is set to CommissionBiddingScheme-->
            <CommissionRate i:nil="false">ValueHere</CommissionRate>
            <!--This field is applicable if the derived type attribute is set to ManualCpaBiddingScheme-->
            <ManualCpi i:nil="false">ValueHere</ManualCpi>
            <!--This field is applicable if the derived type attribute is set to CostPerSaleBiddingScheme-->
            <TargetCostPerSale i:nil="false">ValueHere</TargetCostPerSale>
          </BiddingScheme>
          <CommissionRate i:nil="false">
            <RateAmount i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </RateAmount>
          </CommissionRate>
          <CpcBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </CpcBid>
          <EndDate i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </EndDate>
          <FinalUrlSuffix i:nil="false">ValueHere</FinalUrlSuffix>
          <ForwardCompatibilityMap xmlns:e49="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e49:KeyValuePairOfstringstring>
              <e49:key i:nil="false">ValueHere</e49:key>
              <e49:value i:nil="false">ValueHere</e49:value>
            </e49:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <FrequencyCapSettings i:nil="false">
            <FrequencyCapSettings>
              <CapValue>ValueHere</CapValue>
              <TimeGranularity>ValueHere</TimeGranularity>
            </FrequencyCapSettings>
          </FrequencyCapSettings>
          <Id i:nil="false">ValueHere</Id>
          <Language i:nil="false">ValueHere</Language>
          <MultimediaAdsBidAdjustment i:nil="false">ValueHere</MultimediaAdsBidAdjustment>
          <Name i:nil="false">ValueHere</Name>
          <Network i:nil="false">ValueHere</Network>
          <PercentCpcBid i:nil="false">
            <RateAmount i:nil="false">
              <Amount i:nil="false">ValueHere</Amount>
            </RateAmount>
          </PercentCpcBid>
          <PrivacyStatus i:nil="false">ValueHere</PrivacyStatus>
          <Settings i:nil="false">
            <Setting i:type="-- derived type specified here with the appropriate prefix --">
              <Type i:nil="false">ValueHere</Type>
              <!--This field is applicable if the derived type attribute is set to VerifiedTrackingSetting-->
              <Details xmlns:e50="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
                <e50:ArrayOfKeyValuePairOfstringstring>
                  <e50:KeyValuePairOfstringstring>
                    <e50:key i:nil="false">ValueHere</e50:key>
                    <e50:value i:nil="false">ValueHere</e50:value>
                  </e50:KeyValuePairOfstringstring>
                </e50:ArrayOfKeyValuePairOfstringstring>
              </Details>
              <!--This field is applicable if the derived type attribute is set to DynamicFeedSetting-->
              <FeedId i:nil="false">ValueHere</FeedId>
              <!--This field is applicable if the derived type attribute is set to TargetSetting-->
              <Details i:nil="false">
                <TargetSettingDetail>
                  <CriterionTypeGroup>ValueHere</CriterionTypeGroup>
                  <TargetAndBid>ValueHere</TargetAndBid>
                </TargetSettingDetail>
              </Details>
              <!--These fields are applicable if the derived type attribute is set to CoOpSetting-->
              <BidBoostValue i:nil="false">ValueHere</BidBoostValue>
              <BidMaxValue i:nil="false">ValueHere</BidMaxValue>
              <BidOption i:nil="false">ValueHere</BidOption>
              <!--This field is applicable if the derived type attribute is set to DisclaimerSetting-->
              <DisclaimerAdsEnabled>ValueHere</DisclaimerAdsEnabled>
              <!--This field is applicable if the derived type attribute is set to HotelSetting-->
              <HotelAdGroupType>ValueHere</HotelAdGroupType>
              <!--This field is applicable if the derived type attribute is set to ResponsiveSearchAdsSetting-->
              <AutoGeneratedAssetsEnabled i:nil="false">ValueHere</AutoGeneratedAssetsEnabled>
              <!--These fields are applicable if the derived type attribute is set to PerformanceMaxSetting-->
              <AutoGeneratedImageOptOut i:nil="false">ValueHere</AutoGeneratedImageOptOut>
              <AutoGeneratedTextOptOut i:nil="false">ValueHere</AutoGeneratedTextOptOut>
              <CostPerSaleOptOut i:nil="false">ValueHere</CostPerSaleOptOut>
              <FinalUrlExpansionOptOut>ValueHere</FinalUrlExpansionOptOut>
              <PageFeedIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:long>ValueHere</a1:long>
              </PageFeedIds>
              <!--These fields are applicable if the derived type attribute is set to CallToActionSetting-->
              <AutomatedCallToActionOptOut i:nil="false">ValueHere</AutomatedCallToActionOptOut>
              <CallToActionOptOut i:nil="false">ValueHere</CallToActionOptOut>
              <!--These fields are applicable if the derived type attribute is set to VanityPharmaSetting-->
              <DisplayUrlMode i:nil="false">ValueHere</DisplayUrlMode>
              <WebsiteDescription i:nil="false">ValueHere</WebsiteDescription>
              <!--These fields are applicable if the derived type attribute is set to AppSetting-->
              <AppId i:nil="false">ValueHere</AppId>
              <AppStore>ValueHere</AppStore>
              <!--This field is applicable if the derived type attribute is set to ThirdPartyMeasurementSetting-->
              <Details xmlns:e51="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
                <e51:ArrayOfKeyValuePairOfstringstring>
                  <e51:KeyValuePairOfstringstring>
                    <e51:key i:nil="false">ValueHere</e51:key>
                    <e51:value i:nil="false">ValueHere</e51:value>
                  </e51:KeyValuePairOfstringstring>
                </e51:ArrayOfKeyValuePairOfstringstring>
              </Details>
              <!--These fields are applicable if the derived type attribute is set to NewCustomerAcquisitionGoalSetting-->
              <AdditionalConversionValue i:nil="false">ValueHere</AdditionalConversionValue>
              <NewCustomerAcquisitionBidOnlyMode i:nil="false">ValueHere</NewCustomerAcquisitionBidOnlyMode>
              <NewCustomerAcquisitionGoalId i:nil="false">ValueHere</NewCustomerAcquisitionGoalId>
            </Setting>
          </Settings>
          <StartDate i:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </StartDate>
          <Status i:nil="false">ValueHere</Status>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters i:nil="false">
            <Parameters i:nil="false">
              <CustomParameter>
                <Key i:nil="false">ValueHere</Key>
                <Value i:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <UseOptimizedTargeting i:nil="false">ValueHere</UseOptimizedTargeting>
          <UsePredictiveTargeting i:nil="false">ValueHere</UsePredictiveTargeting>
          <AdScheduleUseSearcherTimeZone i:nil="false">ValueHere</AdScheduleUseSearcherTimeZone>
          <AdGroupType i:nil="false">ValueHere</AdGroupType>
          <CpvBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </CpvBid>
          <CpmBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </CpmBid>
          <McpaBid i:nil="false">
            <Amount i:nil="false">ValueHere</Amount>
          </McpaBid>
        </AdGroup>
      </AdGroups>
      <ReturnInheritedBidStrategyTypes i:nil="false">ValueHere</ReturnInheritedBidStrategyTypes>
    </AddAdGroupsRequest>
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
    <AddAdGroupsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AdGroupIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AdGroupIds>
      <InheritedBidStrategyTypes d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:string>ValueHere</a1:string>
      </InheritedBidStrategyTypes>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e52="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e52:KeyValuePairOfstringstring>
              <e52:key d4p1:nil="false">ValueHere</e52:key>
              <e52:value d4p1:nil="false">ValueHere</e52:value>
            </e52:KeyValuePairOfstringstring>
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
    </AddAdGroupsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddAdGroupsResponse> AddAdGroupsAsync(
	long campaignId,
	IList<AdGroup> adGroups,
	bool? returnInheritedBidStrategyTypes)
{
	var request = new AddAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroups = adGroups,
		ReturnInheritedBidStrategyTypes = returnInheritedBidStrategyTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddAdGroupsAsync(r), request));
}
```
```java
static AddAdGroupsResponse addAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroup adGroups,
	boolean returnInheritedBidStrategyTypes) throws RemoteException, Exception
{
	AddAdGroupsRequest request = new AddAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroups(adGroups);
	request.setReturnInheritedBidStrategyTypes(returnInheritedBidStrategyTypes);

	return CampaignManagementService.getService().addAdGroups(request);
}
```
```php
static function AddAdGroups(
	$campaignId,
	$adGroups,
	$returnInheritedBidStrategyTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroups = $adGroups;
	$request->ReturnInheritedBidStrategyTypes = $returnInheritedBidStrategyTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddAdGroups($request);
}
```
```python
response=campaignmanagement_service.AddAdGroups(
	CampaignId=CampaignId,
	AdGroups=AdGroups,
	ReturnInheritedBidStrategyTypes=ReturnInheritedBidStrategyTypes)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```POST
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/AdGroups
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/AdGroups
```

-----

## <a name="request"></a>Request Elements
The *AddAdGroupsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroups"></a>AdGroups|An array of [AdGroup](adgroup.md) objects to add to the specified campaign.<br/><br/>You can add a maximum of 1,000 ad groups in a single call. Each campaign can have up to 20,000 ad groups.|[AdGroup](adgroup.md) array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign to add the ad groups to.|**long**|
|<a name="returninheritedbidstrategytypes"></a>ReturnInheritedBidStrategyTypes|Reserved for future use.|**boolean**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *AddAdGroupsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupids"></a>AdGroupIds|A list of unique system identifiers corresponding to the ad groups that were added.<br/><br/>The list of identifiers corresponds directly to the list of ad groups in the request. Items of the list may be returned as null. For each list index where an ad group was not added, the corresponding element will be null.|**long** array|
|<a name="inheritedbidstrategytypes"></a>InheritedBidStrategyTypes|Reserved for future use.|**string** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

Below is an example that is applicable if the type of [BiddingScheme](biddingscheme.md) is [CommissionBiddingScheme](commissionbiddingscheme.md), [Setting](setting.md) is [AppSetting](appsetting.md).

```json
{
  "CampaignId": "LongValueHere",
  "AdGroups": [
    {
      "AdGroupType": "ValueHere",
      "AdRotation": {
        "EndDate": "ValueHere",
        "StartDate": "ValueHere",
        "Type": "ValueHere"
      },
      "AdScheduleUseSearcherTimeZone": "ValueHere",
      "AudienceAdsBidAdjustment": IntValueHere,
      "BiddingScheme": {
        "Type": "CommissionBiddingScheme",
        "CommissionRate": DoubleValueHere
      },
      "CommissionRate": {
        "RateAmount": {
          "Amount": DoubleValueHere
        }
      },
      "CpcBid": {
        "Amount": DoubleValueHere
      },
      "CpmBid": {
        "Amount": DoubleValueHere
      },
      "CpvBid": {
        "Amount": DoubleValueHere
      },
      "EndDate": {
        "Day": IntValueHere,
        "Month": IntValueHere,
        "Year": IntValueHere
      },
      "FinalUrlSuffix": "ValueHere",
      "ForwardCompatibilityMap": [
        {
          "key": "ValueHere",
          "value": "ValueHere"
        }
      ],
      "FrequencyCapSettings": [
        {
          "CapValue": IntValueHere,
          "TimeGranularity": "ValueHere"
        }
      ],
      "Id": "LongValueHere",
      "Language": "ValueHere",
      "McpaBid": {
        "Amount": DoubleValueHere
      },
      "MultimediaAdsBidAdjustment": IntValueHere,
      "Name": "ValueHere",
      "Network": "ValueHere",
      "PercentCpcBid": {
        "RateAmount": {
          "Amount": DoubleValueHere
        }
      },
      "PrivacyStatus": "ValueHere",
      "Settings": [
        {
          "Type": "AppSetting",
          "AppId": "ValueHere",
          "AppStore": "ValueHere"
        }
      ],
      "StartDate": {
        "Day": IntValueHere,
        "Month": IntValueHere,
        "Year": IntValueHere
      },
      "Status": "ValueHere",
      "TrackingUrlTemplate": "ValueHere",
      "UrlCustomParameters": {
        "Parameters": [
          {
            "Key": "ValueHere",
            "Value": "ValueHere"
          }
        ]
      },
      "UseOptimizedTargeting": "ValueHere",
      "UsePredictiveTargeting": "ValueHere"
    }
  ],
  "ReturnInheritedBidStrategyTypes": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

Below is an example that is applicable if the type of [BatchError](batcherror.md) is [EditorialError](editorialerror.md).

```json
{
  "AdGroupIds": [
    "LongValueHere"
  ],
  "InheritedBidStrategyTypes": [
    "ValueHere"
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
public async Task<AddAdGroupsResponse> AddAdGroupsAsync(
	long campaignId,
	IList<AdGroup> adGroups,
	bool? returnInheritedBidStrategyTypes)
{
	var request = new AddAdGroupsRequest
	{
		CampaignId = campaignId,
		AdGroups = adGroups,
		ReturnInheritedBidStrategyTypes = returnInheritedBidStrategyTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddAdGroupsAsync(r), request));
}
```
```java
static AddAdGroupsResponse addAdGroups(
	java.lang.Long campaignId,
	ArrayOfAdGroup adGroups,
	boolean returnInheritedBidStrategyTypes) throws RemoteException, Exception
{
	AddAdGroupsRequest request = new AddAdGroupsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroups(adGroups);
	request.setReturnInheritedBidStrategyTypes(returnInheritedBidStrategyTypes);

	return CampaignManagementService.getService().addAdGroups(request);
}
```
```php
static function AddAdGroups(
	$campaignId,
	$adGroups,
	$returnInheritedBidStrategyTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddAdGroupsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroups = $adGroups;
	$request->ReturnInheritedBidStrategyTypes = $returnInheritedBidStrategyTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddAdGroups($request);
}
```
```python
response=campaignmanagement_service.AddAdGroups(
	CampaignId=CampaignId,
	AdGroups=AdGroups,
	ReturnInheritedBidStrategyTypes=ReturnInheritedBidStrategyTypes)
```

::: zone-end
