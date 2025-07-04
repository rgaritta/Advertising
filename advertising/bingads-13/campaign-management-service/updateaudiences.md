---
title: UpdateAudiences Service Operation - Campaign Management
ms.service: bing-ads
ms.subservice: campaign-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
zone_pivot_groups: api-reference
description: Updates the specified audiences.
dev_langs: 
- csharp
- java
- php
- python
---
# UpdateAudiences Service Operation - Campaign Management
Updates the specified audiences.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *UpdateAudiencesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|A list of audiences to update.<br/><br/>The maximum size of the array is 100.<br/><br/>You can only update [RemarketingList](remarketinglist.md) and [CustomAudience](customaudience.md) objects. You cannot update [InMarketAudience](inmarketaudience.md) objects.|[Audience](audience.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAudiencesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">UpdateAudiences</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <UpdateAudiencesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <Audiences i:nil="false">
        <Audience i:type="-- derived type specified here with the appropriate prefix --">
          <AudienceNetworkSize i:nil="false">ValueHere</AudienceNetworkSize>
          <CustomerShare i:nil="false">
            <CustomerAccountShares i:nil="false">
              <CustomerAccountShare>
                <AccountId i:nil="false">ValueHere</AccountId>
                <Associations i:nil="false">
                  <CustomerAccountShareAssociation>
                    <AssociationCount i:nil="false">ValueHere</AssociationCount>
                    <UsageType i:nil="false">ValueHere</UsageType>
                  </CustomerAccountShareAssociation>
                </Associations>
                <CustomerId i:nil="false">ValueHere</CustomerId>
              </CustomerAccountShare>
            </CustomerAccountShares>
            <OwnerCustomerId i:nil="false">ValueHere</OwnerCustomerId>
          </CustomerShare>
          <Description i:nil="false">ValueHere</Description>
          <ForwardCompatibilityMap xmlns:e423="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e423:KeyValuePairOfstringstring>
              <e423:key i:nil="false">ValueHere</e423:key>
              <e423:value i:nil="false">ValueHere</e423:value>
            </e423:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <MembershipDuration i:nil="false">ValueHere</MembershipDuration>
          <Name i:nil="false">ValueHere</Name>
          <ParentId i:nil="false">ValueHere</ParentId>
          <Scope i:nil="false">ValueHere</Scope>
          <SearchSize i:nil="false">ValueHere</SearchSize>
          <SupportedCampaignTypes i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </SupportedCampaignTypes>
          <Type>ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to RemarketingList-->
          <Rule i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
            <Type i:nil="false">ValueHere</Type>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsRule-->
            <NormalForm i:nil="false">ValueHere</NormalForm>
            <RuleItemGroups i:nil="false">
              <RuleItemGroup>
                <Items i:nil="false">
                  <RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <Type i:nil="false">ValueHere</Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                    <!--These fields are applicable if the derived type attribute is set to NumberRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                  </RuleItem>
                </Items>
              </RuleItemGroup>
            </RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoVisitedAnotherPageRule-->
            <AnotherRuleItemGroups i:nil="false">
              <RuleItemGroup>
                <Items i:nil="false">
                  <RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <Type i:nil="false">ValueHere</Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                    <!--These fields are applicable if the derived type attribute is set to NumberRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                  </RuleItem>
                </Items>
              </RuleItemGroup>
            </AnotherRuleItemGroups>
            <RuleItemGroups i:nil="false">
              <RuleItemGroup>
                <Items i:nil="false">
                  <RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <Type i:nil="false">ValueHere</Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                    <!--These fields are applicable if the derived type attribute is set to NumberRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                  </RuleItem>
                </Items>
              </RuleItemGroup>
            </RuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to PageVisitorsWhoDidNotVisitAnotherPageRule-->
            <ExcludeRuleItemGroups i:nil="false">
              <RuleItemGroup>
                <Items i:nil="false">
                  <RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <Type i:nil="false">ValueHere</Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                    <!--These fields are applicable if the derived type attribute is set to NumberRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                  </RuleItem>
                </Items>
              </RuleItemGroup>
            </ExcludeRuleItemGroups>
            <IncludeRuleItemGroups i:nil="false">
              <RuleItemGroup>
                <Items i:nil="false">
                  <RuleItem i:type="-- derived type specified here with the appropriate prefix --">
                    <Type i:nil="false">ValueHere</Type>
                    <!--These fields are applicable if the derived type attribute is set to StringRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                    <!--These fields are applicable if the derived type attribute is set to NumberRuleItem-->
                    <Operand i:nil="false">ValueHere</Operand>
                    <Operator>ValueHere</Operator>
                    <Value i:nil="false">ValueHere</Value>
                  </RuleItem>
                </Items>
              </RuleItemGroup>
            </IncludeRuleItemGroups>
            <!--These fields are applicable if the derived type attribute is set to CustomEventsRule-->
            <Action i:nil="false">ValueHere</Action>
            <ActionOperator>ValueHere</ActionOperator>
            <Category i:nil="false">ValueHere</Category>
            <CategoryOperator>ValueHere</CategoryOperator>
            <Label i:nil="false">ValueHere</Label>
            <LabelOperator>ValueHere</LabelOperator>
            <Value i:nil="false">ValueHere</Value>
            <ValueOperator>ValueHere</ValueOperator>
          </Rule>
          <TagId i:nil="false">ValueHere</TagId>
          <!--No additional fields are applicable if the derived type attribute is set to CustomAudience-->
          <!--No additional fields are applicable if the derived type attribute is set to InMarketAudience-->
          <!--These fields are applicable if the derived type attribute is set to ProductAudience-->
          <ProductAudienceType i:nil="false">ValueHere</ProductAudienceType>
          <TagId i:nil="false">ValueHere</TagId>
          <!--This field is applicable if the derived type attribute is set to SimilarRemarketingList-->
          <SourceId>ValueHere</SourceId>
          <!--This field is applicable if the derived type attribute is set to CombinedList-->
          <CombinationRules i:nil="false">
            <CombinationRule>
              <AudienceIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:long>ValueHere</a1:long>
              </AudienceIds>
              <Operator>ValueHere</Operator>
            </CombinationRule>
          </CombinationRules>
          <!--No additional fields are applicable if the derived type attribute is set to CustomerList-->
          <!--These fields are applicable if the derived type attribute is set to ImpressionBasedRemarketingList-->
          <AdGroupId i:nil="false">ValueHere</AdGroupId>
          <CampaignId i:nil="false">ValueHere</CampaignId>
          <EntityType>ValueHere</EntityType>
        </Audience>
      </Audiences>
    </UpdateAudiencesRequest>
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
    <UpdateAudiencesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e424="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e424:KeyValuePairOfstringstring>
              <e424:key d4p1:nil="false">ValueHere</e424:key>
              <e424:value d4p1:nil="false">ValueHere</e424:value>
            </e424:KeyValuePairOfstringstring>
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
    </UpdateAudiencesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAudiencesResponse> UpdateAudiencesAsync(
	IList<Audience> audiences)
{
	var request = new UpdateAudiencesRequest
	{
		Audiences = audiences
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateAudiencesAsync(r), request));
}
```
```java
static UpdateAudiencesResponse updateAudiences(
	ArrayOfAudience audiences) throws RemoteException, Exception
{
	UpdateAudiencesRequest request = new UpdateAudiencesRequest();

	request.setAudiences(audiences);

	return CampaignManagementService.getService().updateAudiences(request);
}
```
```php
static function UpdateAudiences(
	$audiences)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateAudiencesRequest();

	$request->Audiences = $audiences;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateAudiences($request);
}
```
```python
response=campaignmanagement_service.UpdateAudiences(
	Audiences=Audiences)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```PUT
https://campaign.api.bingads.microsoft.com/CampaignManagement/v13/Audiences
```

# [Sandbox URL](#tab/sandbox)

```PUT
https://campaign.api.sandbox.bingads.microsoft.com/CampaignManagement/v13/Audiences
```

-----

## <a name="request"></a>Request Elements
The *UpdateAudiencesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="audiences"></a>Audiences|A list of audiences to update.<br/><br/>The maximum size of the array is 100.<br/><br/>You can only update [RemarketingList](remarketinglist.md) and [CustomAudience](customaudience.md) objects. You cannot update [InMarketAudience](inmarketaudience.md) objects.|[Audience](audience.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header-rest.md)]

## <a name="response"></a>Response Elements
The *UpdateAudiencesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

Below is an example that is applicable if the type of [Audience](audience.md) is [CombinedList](combinedlist.md).

```json
{
  "Audiences": [
    {
      "AudienceNetworkSize": "LongValueHere",
      "CustomerShare": {
        "CustomerAccountShares": [
          {
            "AccountId": "LongValueHere",
            "Associations": [
              {
                "AssociationCount": "LongValueHere",
                "UsageType": "ValueHere"
              }
            ],
            "CustomerId": "LongValueHere"
          }
        ],
        "OwnerCustomerId": "LongValueHere"
      },
      "Description": "ValueHere",
      "ForwardCompatibilityMap": [
        {
          "key": "ValueHere",
          "value": "ValueHere"
        }
      ],
      "Id": "LongValueHere",
      "MembershipDuration": IntValueHere,
      "Name": "ValueHere",
      "ParentId": "LongValueHere",
      "Scope": "ValueHere",
      "SearchSize": "LongValueHere",
      "SupportedCampaignTypes": [
        "ValueHere"
      ],
      "Type": "CombinedList",
      "CombinationRules": [
        {
          "AudienceIds": [
            "LongValueHere"
          ],
          "Operator": "ValueHere"
        }
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
public async Task<UpdateAudiencesResponse> UpdateAudiencesAsync(
	IList<Audience> audiences)
{
	var request = new UpdateAudiencesRequest
	{
		Audiences = audiences
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateAudiencesAsync(r), request));
}
```
```java
static UpdateAudiencesResponse updateAudiences(
	ArrayOfAudience audiences) throws RemoteException, Exception
{
	UpdateAudiencesRequest request = new UpdateAudiencesRequest();

	request.setAudiences(audiences);

	return CampaignManagementService.getService().updateAudiences(request);
}
```
```php
static function UpdateAudiences(
	$audiences)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateAudiencesRequest();

	$request->Audiences = $audiences;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateAudiences($request);
}
```
```python
response=campaignmanagement_service.UpdateAudiences(
	Audiences=Audiences)
```

::: zone-end
