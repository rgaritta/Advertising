---
title: GetAdsByIds Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Retrieves the specified ads from the specified ad group.
dev_langs: 
- csharp
- java
- php
- python
---
# GetAdsByIds Service Operation - Campaign Management
Retrieves the specified ads from the specified ad group.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetAdsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that contains the ads to get.|**long**|
|<a name="adids"></a>AdIds|A maximum of 20 identifiers of the requested ads.<br/><br/>If the ad identifiers do not match the requested ad types, then the operation will return a batch error for each requested ad.|**long** array|
|<a name="adtypes"></a>AdTypes|One or more types of ads to return.|[AdType](adtype.md) array|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding elements will be included by default.<br/><br/>This request element is optional.|[AdAdditionalField](adadditionalfield.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ads"></a>Ads|An array of [Ad](ad.md) objects that corresponds directly to the ad identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an ad was not retrieved, the corresponding element will be null.|[Ad](ad.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetAdsByIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetAdsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AdGroupId>ValueHere</AdGroupId>
      <AdIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdIds>
      <AdTypes i:nil="false">
        <AdType>ValueHere</AdType>
      </AdTypes>
      <ReturnAdditionalFields i:nil="false">ValueHere</ReturnAdditionalFields>
    </GetAdsByIdsRequest>
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
    <GetAdsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <Ads d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Ad d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AdFormatPreference d4p1:nil="false">ValueHere</AdFormatPreference>
          <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
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
          <ForwardCompatibilityMap xmlns:e251="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e251:KeyValuePairOfstringstring>
              <e251:key d4p1:nil="false">ValueHere</e251:key>
              <e251:value d4p1:nil="false">ValueHere</e251:value>
            </e251:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <Type d4p1:nil="false">ValueHere</Type>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to TextAd-->
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayUrl d4p1:nil="false">ValueHere</DisplayUrl>
          <Text d4p1:nil="false">ValueHere</Text>
          <Title d4p1:nil="false">ValueHere</Title>
          <!--This field is applicable if the derived type attribute is set to ProductAd-->
          <PromotionalText d4p1:nil="false">ValueHere</PromotionalText>
          <!--No additional fields are applicable if the derived type attribute is set to HotelAd-->
          <!--These fields are applicable if the derived type attribute is set to AppInstallAd-->
          <AppPlatform d4p1:nil="false">ValueHere</AppPlatform>
          <AppStoreId d4p1:nil="false">ValueHere</AppStoreId>
          <Text d4p1:nil="false">ValueHere</Text>
          <Title d4p1:nil="false">ValueHere</Title>
          <!--These fields are applicable if the derived type attribute is set to ExpandedTextAd-->
          <Domain d4p1:nil="false">ValueHere</Domain>
          <Path1 d4p1:nil="false">ValueHere</Path1>
          <Path2 d4p1:nil="false">ValueHere</Path2>
          <Text d4p1:nil="false">ValueHere</Text>
          <TextPart2 d4p1:nil="false">ValueHere</TextPart2>
          <TitlePart1 d4p1:nil="false">ValueHere</TitlePart1>
          <TitlePart2 d4p1:nil="false">ValueHere</TitlePart2>
          <TitlePart3 d4p1:nil="false">ValueHere</TitlePart3>
          <!--These fields are applicable if the derived type attribute is set to DynamicSearchAd-->
          <Path1 d4p1:nil="false">ValueHere</Path1>
          <Path2 d4p1:nil="false">ValueHere</Path2>
          <Text d4p1:nil="false">ValueHere</Text>
          <TextPart2 d4p1:nil="false">ValueHere</TextPart2>
          <!--These fields are applicable if the derived type attribute is set to ResponsiveAd-->
          <AdSubType d4p1:nil="false">ValueHere</AdSubType>
          <BusinessName d4p1:nil="false">ValueHere</BusinessName>
          <CallToAction d4p1:nil="false">ValueHere</CallToAction>
          <CallToActionLanguage d4p1:nil="false">ValueHere</CallToActionLanguage>
          <Descriptions d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </Descriptions>
          <Headline d4p1:nil="false">ValueHere</Headline>
          <Headlines d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </Headlines>
          <Images d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </Images>
          <ImpressionTrackingUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </ImpressionTrackingUrls>
          <LongHeadline d4p1:nil="false">
            <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Id d4p1:nil="false">ValueHere</Id>
              <Name d4p1:nil="false">ValueHere</Name>
              <Type d4p1:nil="false">ValueHere</Type>
              <!--This field is applicable if the derived type attribute is set to TextAsset-->
              <Text d4p1:nil="false">ValueHere</Text>
              <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
              <CropHeight d4p1:nil="false">ValueHere</CropHeight>
              <CropWidth d4p1:nil="false">ValueHere</CropWidth>
              <CropX d4p1:nil="false">ValueHere</CropX>
              <CropY d4p1:nil="false">ValueHere</CropY>
              <SubType d4p1:nil="false">ValueHere</SubType>
              <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
              <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
              <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
              <SubType d4p1:nil="false">ValueHere</SubType>
              <ThumbnailImage d4p1:nil="false">
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
              </ThumbnailImage>
            </Asset>
            <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
            <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
            <PinnedField d4p1:nil="false">ValueHere</PinnedField>
          </LongHeadline>
          <LongHeadlineString d4p1:nil="false">ValueHere</LongHeadlineString>
          <LongHeadlines d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </LongHeadlines>
          <Text d4p1:nil="false">ValueHere</Text>
          <VerifiedTrackingSettings d4p1:nil="false">
            <Details xmlns:e252="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
              <e252:ArrayOfKeyValuePairOfstringstring>
                <e252:KeyValuePairOfstringstring>
                  <e252:key d4p1:nil="false">ValueHere</e252:key>
                  <e252:value d4p1:nil="false">ValueHere</e252:value>
                </e252:KeyValuePairOfstringstring>
              </e252:ArrayOfKeyValuePairOfstringstring>
            </Details>
          </VerifiedTrackingSettings>
          <Videos d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </Videos>
          <!--These fields are applicable if the derived type attribute is set to ResponsiveSearchAd-->
          <Descriptions d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </Descriptions>
          <Domain d4p1:nil="false">ValueHere</Domain>
          <Headlines d4p1:nil="false">
            <AssetLink>
              <Asset d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
                <Id d4p1:nil="false">ValueHere</Id>
                <Name d4p1:nil="false">ValueHere</Name>
                <Type d4p1:nil="false">ValueHere</Type>
                <!--This field is applicable if the derived type attribute is set to TextAsset-->
                <Text d4p1:nil="false">ValueHere</Text>
                <!--These fields are applicable if the derived type attribute is set to ImageAsset-->
                <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                <CropX d4p1:nil="false">ValueHere</CropX>
                <CropY d4p1:nil="false">ValueHere</CropY>
                <SubType d4p1:nil="false">ValueHere</SubType>
                <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                <!--These fields are applicable if the derived type attribute is set to VideoAsset-->
                <SubType d4p1:nil="false">ValueHere</SubType>
                <ThumbnailImage d4p1:nil="false">
                  <CropHeight d4p1:nil="false">ValueHere</CropHeight>
                  <CropWidth d4p1:nil="false">ValueHere</CropWidth>
                  <CropX d4p1:nil="false">ValueHere</CropX>
                  <CropY d4p1:nil="false">ValueHere</CropY>
                  <SubType d4p1:nil="false">ValueHere</SubType>
                  <TargetHeight d4p1:nil="false">ValueHere</TargetHeight>
                  <TargetWidth d4p1:nil="false">ValueHere</TargetWidth>
                </ThumbnailImage>
              </Asset>
              <AssetPerformanceLabel d4p1:nil="false">ValueHere</AssetPerformanceLabel>
              <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
              <PinnedField d4p1:nil="false">ValueHere</PinnedField>
            </AssetLink>
          </Headlines>
          <Path1 d4p1:nil="false">ValueHere</Path1>
          <Path2 d4p1:nil="false">ValueHere</Path2>
        </Ad>
      </Ads>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e253="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e253:KeyValuePairOfstringstring>
              <e253:key d4p1:nil="false">ValueHere</e253:key>
              <e253:value d4p1:nil="false">ValueHere</e253:value>
            </e253:KeyValuePairOfstringstring>
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
    </GetAdsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdsByIdsResponse> GetAdsByIdsAsync(
	long adGroupId,
	IList<long> adIds,
	IList<AdType> adTypes,
	AdAdditionalField? returnAdditionalFields)
{
	var request = new GetAdsByIdsRequest
	{
		AdGroupId = adGroupId,
		AdIds = adIds,
		AdTypes = adTypes,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdsByIdsAsync(r), request));
}
```
```java
static GetAdsByIdsResponse getAdsByIds(
	java.lang.Long adGroupId,
	ArrayOflong adIds,
	ArrayOfAdType adTypes,
	ArrayList<AdAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdsByIdsRequest request = new GetAdsByIdsRequest();

	request.setAdGroupId(adGroupId);
	request.setAdIds(adIds);
	request.setAdTypes(adTypes);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdsByIds(request);
}
```
```php
static function GetAdsByIds(
	$adGroupId,
	$adIds,
	$adTypes,
	$returnAdditionalFields)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdsByIdsRequest();

	$request->AdGroupId = $adGroupId;
	$request->AdIds = $adIds;
	$request->AdTypes = $adTypes;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdsByIds(
	AdGroupId=AdGroupId,
	AdIds=AdIds,
	AdTypes=AdTypes,
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
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/Ads/QueryByIds
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/Ads/QueryByIds
```

-----

## <a name="request"></a>Request Elements
The *GetAdsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that contains the ads to get.|**long**|
|<a name="adids"></a>AdIds|A maximum of 20 identifiers of the requested ads.<br/><br/>If the ad identifiers do not match the requested ad types, then the operation will return a batch error for each requested ad.|**long** array|
|<a name="adtypes"></a>AdTypes|One or more types of ads to return.|[AdType](adtype.md) array|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding elements will be included by default.<br/><br/>This request element is optional.|[AdAdditionalField](adadditionalfield.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *GetAdsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ads"></a>Ads|An array of [Ad](ad.md) objects that corresponds directly to the ad identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an ad was not retrieved, the corresponding element will be null.|[Ad](ad.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "AdGroupId": "LongValueHere",
  "AdIds": [
    "LongValueHere"
  ],
  "AdTypes": [
    "ValueHere"
  ],
  "ReturnAdditionalFields": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

Below is an example that is applicable if the type of [Ad](ad.md) is [AppInstallAd](appinstallad.md), [BatchError](batcherror.md) is [EditorialError](editorialerror.md).

```json
{
  "Ads": [
    {
      "AdFormatPreference": "ValueHere",
      "DevicePreference": "LongValueHere",
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
      "ForwardCompatibilityMap": [
        {
          "key": "ValueHere",
          "value": "ValueHere"
        }
      ],
      "Id": "LongValueHere",
      "Status": "ValueHere",
      "TrackingUrlTemplate": "ValueHere",
      "Type": "AppInstall",
      "UrlCustomParameters": {
        "Parameters": [
          {
            "Key": "ValueHere",
            "Value": "ValueHere"
          }
        ]
      },
      "AppPlatform": "ValueHere",
      "AppStoreId": "ValueHere",
      "Text": "ValueHere",
      "Title": "ValueHere"
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
public async Task<GetAdsByIdsResponse> GetAdsByIdsAsync(
	long adGroupId,
	IList<long> adIds,
	IList<AdType> adTypes,
	AdAdditionalField? returnAdditionalFields)
{
	var request = new GetAdsByIdsRequest
	{
		AdGroupId = adGroupId,
		AdIds = adIds,
		AdTypes = adTypes,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdsByIdsAsync(r), request));
}
```
```java
static GetAdsByIdsResponse getAdsByIds(
	java.lang.Long adGroupId,
	ArrayOflong adIds,
	ArrayOfAdType adTypes,
	ArrayList<AdAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdsByIdsRequest request = new GetAdsByIdsRequest();

	request.setAdGroupId(adGroupId);
	request.setAdIds(adIds);
	request.setAdTypes(adTypes);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdsByIds(request);
}
```
```php
static function GetAdsByIds(
	$adGroupId,
	$adIds,
	$adTypes,
	$returnAdditionalFields)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdsByIdsRequest();

	$request->AdGroupId = $adGroupId;
	$request->AdIds = $adIds;
	$request->AdTypes = $adTypes;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdsByIds(
	AdGroupId=AdGroupId,
	AdIds=AdIds,
	AdTypes=AdTypes,
	ReturnAdditionalFields=ReturnAdditionalFields)
```

::: zone-end
