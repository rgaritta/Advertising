---
title: GetAdExtensionsByIds Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Gets the specified ad extensions from the account's ad extension library.
dev_langs: 
- csharp
- java
- php
- python
---
# GetAdExtensionsByIds Service Operation - Campaign Management
Gets the specified ad extensions from the account's ad extension library.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *GetAdExtensionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the ad extensions.|**long**|
|<a name="adextensionids"></a>AdExtensionIds|A list of ad extension identifiers.<br/><br/>You can specify a maximum of 100 identifiers.|**long** array|
|<a name="adextensiontype"></a>AdExtensionType|The types of ad extensions that the list of identifiers contains.<br/><br/>You may include multiple values as flags. How you specify multiple flags depends on the programming language that you use. For example, C# treats these values as flag values and Java treats them as an array of strings. The SOAP should include a string that contains a space-delimited list of values for example, `<AdExtensionType>LocationAdExtension CallAdExtension</AdExtensionType>`.|[AdExtensionsTypeFilter](adextensionstypefilter.md)|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|Reserved for future use.|[AdExtensionAdditionalField](adextensionadditionalfield.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdExtensionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensions"></a>AdExtensions|A list of [AdExtension](adextension.md) objects. The list corresponds directly to the list of identifiers in the request. If an ad extension ID in the request is not valid or the extension is not of the type specified, the corresponding item in this list is null.|[AdExtension](adextension.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetAdExtensionsByIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetAdExtensionsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AccountId>ValueHere</AccountId>
      <AdExtensionIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdExtensionIds>
      <AdExtensionType>ValueHere</AdExtensionType>
      <ReturnAdditionalFields i:nil="false">ValueHere</ReturnAdditionalFields>
    </GetAdExtensionsByIdsRequest>
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
    <GetAdExtensionsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AdExtensions d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdExtension d4p1:type="-- derived type specified here with the appropriate prefix --">
          <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
          <ForwardCompatibilityMap xmlns:e223="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e223:KeyValuePairOfstringstring>
              <e223:key d4p1:nil="false">ValueHere</e223:key>
              <e223:value d4p1:nil="false">ValueHere</e223:value>
            </e223:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Scheduling d4p1:nil="false">
            <DayTimeRanges d4p1:nil="false">
              <DayTime>
                <Day>ValueHere</Day>
                <EndHour>ValueHere</EndHour>
                <EndMinute>ValueHere</EndMinute>
                <StartHour>ValueHere</StartHour>
                <StartMinute>ValueHere</StartMinute>
              </DayTime>
            </DayTimeRanges>
            <EndDate d4p1:nil="false">
              <Day>ValueHere</Day>
              <Month>ValueHere</Month>
              <Year>ValueHere</Year>
            </EndDate>
            <StartDate d4p1:nil="false">
              <Day>ValueHere</Day>
              <Month>ValueHere</Month>
              <Year>ValueHere</Year>
            </StartDate>
            <UseSearcherTimeZone d4p1:nil="false">ValueHere</UseSearcherTimeZone>
          </Scheduling>
          <Status d4p1:nil="false">ValueHere</Status>
          <Type d4p1:nil="false">ValueHere</Type>
          <Version d4p1:nil="false">ValueHere</Version>
          <!--These fields are applicable if the derived type attribute is set to LocationAdExtension-->
          <Address d4p1:nil="false">
            <CityName d4p1:nil="false">ValueHere</CityName>
            <CountryCode d4p1:nil="false">ValueHere</CountryCode>
            <PostalCode d4p1:nil="false">ValueHere</PostalCode>
            <ProvinceCode d4p1:nil="false">ValueHere</ProvinceCode>
            <ProvinceName d4p1:nil="false">ValueHere</ProvinceName>
            <StreetAddress d4p1:nil="false">ValueHere</StreetAddress>
            <StreetAddress2 d4p1:nil="false">ValueHere</StreetAddress2>
          </Address>
          <CompanyName d4p1:nil="false">ValueHere</CompanyName>
          <GeoCodeStatus d4p1:nil="false">ValueHere</GeoCodeStatus>
          <GeoPoint d4p1:nil="false">
            <LatitudeInMicroDegrees>ValueHere</LatitudeInMicroDegrees>
            <LongitudeInMicroDegrees>ValueHere</LongitudeInMicroDegrees>
          </GeoPoint>
          <PhoneNumber d4p1:nil="false">ValueHere</PhoneNumber>
          <!--These fields are applicable if the derived type attribute is set to CallAdExtension-->
          <CountryCode d4p1:nil="false">ValueHere</CountryCode>
          <IsCallOnly d4p1:nil="false">ValueHere</IsCallOnly>
          <IsCallTrackingEnabled d4p1:nil="false">ValueHere</IsCallTrackingEnabled>
          <PhoneNumber d4p1:nil="false">ValueHere</PhoneNumber>
          <RequireTollFreeTrackingNumber d4p1:nil="false">ValueHere</RequireTollFreeTrackingNumber>
          <!--These fields are applicable if the derived type attribute is set to ImageAdExtension-->
          <AlternativeText d4p1:nil="false">ValueHere</AlternativeText>
          <Description d4p1:nil="false">ValueHere</Description>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayText d4p1:nil="false">ValueHere</DisplayText>
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
          <ImageMediaIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </ImageMediaIds>
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
          <Layouts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Layouts>
          <SourceType d4p1:nil="false">ValueHere</SourceType>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to AppAdExtension-->
          <AppPlatform d4p1:nil="false">ValueHere</AppPlatform>
          <AppStoreId d4p1:nil="false">ValueHere</AppStoreId>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayText d4p1:nil="false">ValueHere</DisplayText>
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
          <!--These fields are applicable if the derived type attribute is set to ReviewAdExtension-->
          <IsExact>ValueHere</IsExact>
          <Source d4p1:nil="false">ValueHere</Source>
          <Text d4p1:nil="false">ValueHere</Text>
          <Url d4p1:nil="false">ValueHere</Url>
          <!--This field is applicable if the derived type attribute is set to CalloutAdExtension-->
          <Text d4p1:nil="false">ValueHere</Text>
          <!--These fields are applicable if the derived type attribute is set to SitelinkAdExtension-->
          <Description1 d4p1:nil="false">ValueHere</Description1>
          <Description2 d4p1:nil="false">ValueHere</Description2>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayText d4p1:nil="false">ValueHere</DisplayText>
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
          <!--These fields are applicable if the derived type attribute is set to ActionAdExtension-->
          <ActionType>ValueHere</ActionType>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrlSuffix d4p1:nil="false">ValueHere</FinalUrlSuffix>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <Language d4p1:nil="false">ValueHere</Language>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to StructuredSnippetAdExtension-->
          <Header d4p1:nil="false">ValueHere</Header>
          <Values d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Values>
          <!--These fields are applicable if the derived type attribute is set to PriceAdExtension-->
          <FinalUrlSuffix d4p1:nil="false">ValueHere</FinalUrlSuffix>
          <Language d4p1:nil="false">ValueHere</Language>
          <PriceExtensionType>ValueHere</PriceExtensionType>
          <TableRows d4p1:nil="false">
            <PriceTableRow>
              <CurrencyCode d4p1:nil="false">ValueHere</CurrencyCode>
              <Description d4p1:nil="false">ValueHere</Description>
              <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalMobileUrls>
              <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalUrls>
              <Header d4p1:nil="false">ValueHere</Header>
              <Price>ValueHere</Price>
              <PriceQualifier>ValueHere</PriceQualifier>
              <PriceUnit>ValueHere</PriceUnit>
              <TermsAndConditions d4p1:nil="false">ValueHere</TermsAndConditions>
              <TermsAndConditionsUrl d4p1:nil="false">ValueHere</TermsAndConditionsUrl>
            </PriceTableRow>
          </TableRows>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to PromotionAdExtension-->
          <CurrencyCode d4p1:nil="false">ValueHere</CurrencyCode>
          <DiscountModifier d4p1:nil="false">ValueHere</DiscountModifier>
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
          <Language d4p1:nil="false">ValueHere</Language>
          <MoneyAmountOff d4p1:nil="false">ValueHere</MoneyAmountOff>
          <OrdersOverAmount d4p1:nil="false">ValueHere</OrdersOverAmount>
          <PercentOff d4p1:nil="false">ValueHere</PercentOff>
          <PromotionCode d4p1:nil="false">ValueHere</PromotionCode>
          <PromotionEndDate d4p1:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </PromotionEndDate>
          <PromotionItem d4p1:nil="false">ValueHere</PromotionItem>
          <PromotionOccasion d4p1:nil="false">ValueHere</PromotionOccasion>
          <PromotionStartDate d4p1:nil="false">
            <Day>ValueHere</Day>
            <Month>ValueHere</Month>
            <Year>ValueHere</Year>
          </PromotionStartDate>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to FilterLinkAdExtension-->
          <AdExtensionHeaderType d4p1:nil="false">ValueHere</AdExtensionHeaderType>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrlSuffix d4p1:nil="false">ValueHere</FinalUrlSuffix>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <Language d4p1:nil="false">ValueHere</Language>
          <Texts d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Texts>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to FlyerAdExtension-->
          <Description d4p1:nil="false">ValueHere</Description>
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
          <FlyerName d4p1:nil="false">ValueHere</FlyerName>
          <ImageMediaIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </ImageMediaIds>
          <ImageMediaUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </ImageMediaUrls>
          <StoreId d4p1:nil="false">ValueHere</StoreId>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to VideoAdExtension-->
          <ActionText d4p1:nil="false">ValueHere</ActionText>
          <AlternativeText d4p1:nil="false">ValueHere</AlternativeText>
          <DisplayText d4p1:nil="false">ValueHere</DisplayText>
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
          <Name d4p1:nil="false">ValueHere</Name>
          <ThumbnailId d4p1:nil="false">ValueHere</ThumbnailId>
          <ThumbnailUrl d4p1:nil="false">ValueHere</ThumbnailUrl>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <VideoId d4p1:nil="false">ValueHere</VideoId>
          <!--These fields are applicable if the derived type attribute is set to DisclaimerAdExtension-->
          <DisclaimerLayout d4p1:nil="false">ValueHere</DisclaimerLayout>
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
          <LineText d4p1:nil="false">ValueHere</LineText>
          <Name d4p1:nil="false">ValueHere</Name>
          <PopupText d4p1:nil="false">ValueHere</PopupText>
          <Title d4p1:nil="false">ValueHere</Title>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to LogoAdExtension-->
          <BusinessLogo d4p1:nil="false">ValueHere</BusinessLogo>
          <BusinessLogoUrl d4p1:nil="false">ValueHere</BusinessLogoUrl>
          <BusinessName d4p1:nil="false">ValueHere</BusinessName>
          <DomainName d4p1:nil="false">ValueHere</DomainName>
        </AdExtension>
      </AdExtensions>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e224="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e224:KeyValuePairOfstringstring>
              <e224:key d4p1:nil="false">ValueHere</e224:key>
              <e224:value d4p1:nil="false">ValueHere</e224:value>
            </e224:KeyValuePairOfstringstring>
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
    </GetAdExtensionsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdExtensionsByIdsResponse> GetAdExtensionsByIdsAsync(
	long accountId,
	IList<long> adExtensionIds,
	AdExtensionsTypeFilter adExtensionType,
	AdExtensionAdditionalField? returnAdditionalFields)
{
	var request = new GetAdExtensionsByIdsRequest
	{
		AccountId = accountId,
		AdExtensionIds = adExtensionIds,
		AdExtensionType = adExtensionType,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdExtensionsByIdsAsync(r), request));
}
```
```java
static GetAdExtensionsByIdsResponse getAdExtensionsByIds(
	java.lang.Long accountId,
	ArrayOflong adExtensionIds,
	ArrayList<AdExtensionsTypeFilter> adExtensionType,
	ArrayList<AdExtensionAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdExtensionsByIdsRequest request = new GetAdExtensionsByIdsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionIds(adExtensionIds);
	request.setAdExtensionType(adExtensionType);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdExtensionsByIds(request);
}
```
```php
static function GetAdExtensionsByIds(
	$accountId,
	$adExtensionIds,
	$adExtensionType,
	$returnAdditionalFields)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdExtensionsByIdsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionIds = $adExtensionIds;
	$request->AdExtensionType = $adExtensionType;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdExtensionsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdExtensionsByIds(
	AccountId=AccountId,
	AdExtensionIds=AdExtensionIds,
	AdExtensionType=AdExtensionType,
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
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/AdExtensions/QueryByIds
```

# [Sandbox URL](#tab/sandbox)

```POST
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/AdExtensions/QueryByIds
```

-----

## <a name="request"></a>Request Elements
The *GetAdExtensionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the ad extensions.|**long**|
|<a name="adextensionids"></a>AdExtensionIds|A list of ad extension identifiers.<br/><br/>You can specify a maximum of 100 identifiers.|**long** array|
|<a name="adextensiontype"></a>AdExtensionType|The types of ad extensions that the list of identifiers contains.<br/><br/>You may include multiple values as flags. How you specify multiple flags depends on the programming language that you use. For example, C# treats these values as flag values and Java treats them as an array of strings. The SOAP should include a string that contains a space-delimited list of values for example, `<AdExtensionType>LocationAdExtension CallAdExtension</AdExtensionType>`.|[AdExtensionsTypeFilter](adextensionstypefilter.md)|
|<a name="returnadditionalfields"></a>ReturnAdditionalFields|Reserved for future use.|[AdExtensionAdditionalField](adextensionadditionalfield.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *GetAdExtensionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensions"></a>AdExtensions|A list of [AdExtension](adextension.md) objects. The list corresponds directly to the list of identifiers in the request. If an ad extension ID in the request is not valid or the extension is not of the type specified, the corresponding item in this list is null.|[AdExtension](adextension.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "AccountId": "LongValueHere",
  "AdExtensionIds": [
    "LongValueHere"
  ],
  "AdExtensionType": "ValueHere",
  "ReturnAdditionalFields": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

Below is an example that is applicable if the type of [AdExtension](adextension.md) is [ActionAdExtension](actionadextension.md), [BatchError](batcherror.md) is [EditorialError](editorialerror.md).

```json
{
  "AdExtensions": [
    {
      "DevicePreference": "LongValueHere",
      "ForwardCompatibilityMap": [
        {
          "key": "ValueHere",
          "value": "ValueHere"
        }
      ],
      "Id": "LongValueHere",
      "Scheduling": {
        "DayTimeRanges": [
          {
            "Day": "ValueHere",
            "EndHour": IntValueHere,
            "EndMinute": "ValueHere",
            "StartHour": IntValueHere,
            "StartMinute": "ValueHere"
          }
        ],
        "EndDate": {
          "Day": IntValueHere,
          "Month": IntValueHere,
          "Year": IntValueHere
        },
        "StartDate": {
          "Day": IntValueHere,
          "Month": IntValueHere,
          "Year": IntValueHere
        },
        "UseSearcherTimeZone": "ValueHere"
      },
      "Status": "ValueHere",
      "Type": "ActionAdExtension",
      "Version": IntValueHere,
      "ActionType": "ValueHere",
      "FinalMobileUrls": [
        "ValueHere"
      ],
      "FinalUrls": [
        "ValueHere"
      ],
      "FinalUrlSuffix": "ValueHere",
      "Language": "ValueHere",
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
public async Task<GetAdExtensionsByIdsResponse> GetAdExtensionsByIdsAsync(
	long accountId,
	IList<long> adExtensionIds,
	AdExtensionsTypeFilter adExtensionType,
	AdExtensionAdditionalField? returnAdditionalFields)
{
	var request = new GetAdExtensionsByIdsRequest
	{
		AccountId = accountId,
		AdExtensionIds = adExtensionIds,
		AdExtensionType = adExtensionType,
		ReturnAdditionalFields = returnAdditionalFields
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdExtensionsByIdsAsync(r), request));
}
```
```java
static GetAdExtensionsByIdsResponse getAdExtensionsByIds(
	java.lang.Long accountId,
	ArrayOflong adExtensionIds,
	ArrayList<AdExtensionsTypeFilter> adExtensionType,
	ArrayList<AdExtensionAdditionalField> returnAdditionalFields) throws RemoteException, Exception
{
	GetAdExtensionsByIdsRequest request = new GetAdExtensionsByIdsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionIds(adExtensionIds);
	request.setAdExtensionType(adExtensionType);
	request.setReturnAdditionalFields(returnAdditionalFields);

	return CampaignManagementService.getService().getAdExtensionsByIds(request);
}
```
```php
static function GetAdExtensionsByIds(
	$accountId,
	$adExtensionIds,
	$adExtensionType,
	$returnAdditionalFields)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdExtensionsByIdsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionIds = $adExtensionIds;
	$request->AdExtensionType = $adExtensionType;
	$request->ReturnAdditionalFields = $returnAdditionalFields;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdExtensionsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdExtensionsByIds(
	AccountId=AccountId,
	AdExtensionIds=AdExtensionIds,
	AdExtensionType=AdExtensionType,
	ReturnAdditionalFields=ReturnAdditionalFields)
```

::: zone-end
