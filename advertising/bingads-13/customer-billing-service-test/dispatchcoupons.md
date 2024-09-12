---
title: DispatchCoupons Service Operation Test - Customer Billing
ms.service: bing-ads
ms.subservice: customer-billing-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
zone_pivot_groups: api-reference
description: Dispatch coupons of the specified coupon class name owned by the specified customer.(test)
dev_langs: 
- csharp
- java
- php
- python
---
# DispatchCoupons Service Operation Test - Customer Billing
Dispatch coupons of the specified coupon class name owned by the specified customer.

Coupons that are already redeemed or dispatched coupons won't be dispatched.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *DispatchCouponsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="couponclassname"></a>CouponClassName|The name of coupon class whose available coupons are dispatched.|**string**|
|<a name="customerid"></a>CustomerId|The identifier of the customer that the coupon class belongs to.|**long**|
|<a name="sendtoemails"></a>SendToEmails|Email addresses to which the coupons are dispatched. Email address count should not exceed 1000.|**string** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DispatchCouponsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that correspond to any email addresses where the coupon code could not be sent to.<br/><br/>The list can be empty if there were no errors.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v13">
    <Action mustUnderstand="1">DispatchCoupons</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <DispatchCouponsRequest xmlns="https://bingads.microsoft.com/Billing/v13">
      <SendToEmails i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </SendToEmails>
      <CustomerId>ValueHere</CustomerId>
      <CouponClassName i:nil="false">ValueHere</CouponClassName>
    </DispatchCouponsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Billing/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <DispatchCouponsResponse xmlns="https://bingads.microsoft.com/Billing/v13">
      <PartialErrors xmlns:e11="https://bingads.microsoft.com/Customer/v13/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e11:BatchError>
          <e11:Code>ValueHere</e11:Code>
          <e11:Details d4p1:nil="false">ValueHere</e11:Details>
          <e11:Index>ValueHere</e11:Index>
          <e11:Message d4p1:nil="false">ValueHere</e11:Message>
        </e11:BatchError>
      </PartialErrors>
    </DispatchCouponsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DispatchCouponsResponse> DispatchCouponsAsync(
	IList<string> sendToEmails,
	long customerId,
	string couponClassName)
{
	var request = new DispatchCouponsRequest
	{
		SendToEmails = sendToEmails,
		CustomerId = customerId,
		CouponClassName = couponClassName
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.DispatchCouponsAsync(r), request));
}
```
```java
static DispatchCouponsResponse dispatchCoupons(
	ArrayOfstring sendToEmails,
	java.lang.Long customerId,
	java.lang.String couponClassName) throws RemoteException, Exception
{
	DispatchCouponsRequest request = new DispatchCouponsRequest();

	request.setSendToEmails(sendToEmails);
	request.setCustomerId(customerId);
	request.setCouponClassName(couponClassName);

	return CustomerBillingService.getService().dispatchCoupons(request);
}
```
```php
static function DispatchCoupons(
	$sendToEmails,
	$customerId,
	$couponClassName)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new DispatchCouponsRequest();

	$request->SendToEmails = $sendToEmails;
	$request->CustomerId = $customerId;
	$request->CouponClassName = $couponClassName;

	return $GLOBALS['CustomerBillingProxy']->GetService()->DispatchCoupons($request);
}
```
```python
response=customerbilling_service.DispatchCoupons(
	SendToEmails=SendToEmails,
	CustomerId=CustomerId,
	CouponClassName=CouponClassName)
```

## Requirements
Service: [CustomerBillingService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/Billing/v13/CustomerBillingService.svc)  
Namespace: https\://bingads.microsoft.com/Billing/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```Post
https://clientcenter.api.bingads.microsoft.com/CustomerBilling/v13/Coupons/Dispatch
```

# [Sandbox URL](#tab/sandbox)

```Post
https://clientcenter.api.sandbox.bingads.microsoft.com/CustomerBilling/v13/Coupons/Dispatch
```

-----

## <a name="request"></a>Request Elements
The *DispatchCouponsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="couponclassname"></a>CouponClassName|The name of coupon class whose available coupons are dispatched.|**string**|
|<a name="customerid"></a>CustomerId|The identifier of the customer that the coupon class belongs to.|**long**|
|<a name="sendtoemails"></a>SendToEmails|Email addresses to which the coupons are dispatched. Email address count should not exceed 1000.|**string** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DispatchCouponsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that correspond to any email addresses where the coupon code could not be sent to.<br/><br/>The list can be empty if there were no errors.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "SendToEmails": [
    "ValueHere"
  ],
  "CustomerId": "LongValueHere",
  "CouponClassName": "ValueHere"
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

```json
{
  "PartialErrors": [
    {
      "Code": IntValueHere,
      "Details": "ValueHere",
      "Index": IntValueHere,
      "Message": "ValueHere"
    }
  ]
}
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DispatchCouponsResponse> DispatchCouponsAsync(
	IList<string> sendToEmails,
	long customerId,
	string couponClassName)
{
	var request = new DispatchCouponsRequest
	{
		SendToEmails = sendToEmails,
		CustomerId = customerId,
		CouponClassName = couponClassName
	};

	return (await CustomerBillingService.CallAsync((s, r) => s.DispatchCouponsAsync(r), request));
}
```
```java
static DispatchCouponsResponse dispatchCoupons(
	ArrayOfstring sendToEmails,
	java.lang.Long customerId,
	java.lang.String couponClassName) throws RemoteException, Exception
{
	DispatchCouponsRequest request = new DispatchCouponsRequest();

	request.setSendToEmails(sendToEmails);
	request.setCustomerId(customerId);
	request.setCouponClassName(couponClassName);

	return CustomerBillingService.getService().dispatchCoupons(request);
}
```
```php
static function DispatchCoupons(
	$sendToEmails,
	$customerId,
	$couponClassName)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerBillingProxy'];

	$request = new DispatchCouponsRequest();

	$request->SendToEmails = $sendToEmails;
	$request->CustomerId = $customerId;
	$request->CouponClassName = $couponClassName;

	return $GLOBALS['CustomerBillingProxy']->GetService()->DispatchCoupons($request);
}
```
```python
response=customerbilling_service.DispatchCoupons(
	SendToEmails=SendToEmails,
	CustomerId=CustomerId,
	CouponClassName=CouponClassName)
```

::: zone-end