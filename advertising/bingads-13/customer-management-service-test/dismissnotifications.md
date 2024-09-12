---
title: DismissNotifications Service Operation Test - Customer Management
ms.service: bing-ads
ms.subservice: customer-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
zone_pivot_groups: api-reference
description: A service operation to dismiss notifications.(test)
dev_langs: 
- csharp
- java
- php
- python
---
# DismissNotifications Service Operation Test - Customer Management
A service operation to dismiss notifications.

::: zone pivot="soap"

## <a name="request"></a>Request Elements
The *DismissNotificationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="notificationtypepairs"></a>NotificationTypePairs|The key and value of a notification entity.|[KeyValueEntityOflongint](keyvalueentityoflongint.md) array|
|<a name="userid"></a>UserId|The user's identification number.|**int**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DismissNotificationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements
There are not any elements in the operation's response body.

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">DismissNotifications</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <DismissNotificationsRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <UserId i:nil="false">ValueHere</UserId>
      <NotificationTypePairs xmlns:e449="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e449:KeyValueEntityOflongint>
          <e449:Key>ValueHere</e449:Key>
          <e449:Value>ValueHere</e449:Value>
        </e449:KeyValueEntityOflongint>
      </NotificationTypePairs>
    </DismissNotificationsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <DismissNotificationsResponse xmlns="https://bingads.microsoft.com/Customer/v13" />
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DismissNotificationsResponse> DismissNotificationsAsync(
	int? userId,
	IList<KeyValueEntityOflongint> notificationTypePairs)
{
	var request = new DismissNotificationsRequest
	{
		UserId = userId,
		NotificationTypePairs = notificationTypePairs
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.DismissNotificationsAsync(r), request));
}
```
```java
static DismissNotificationsResponse dismissNotifications(
	int userId,
	ArrayOfKeyValueEntityOflongint notificationTypePairs) throws RemoteException, Exception
{
	DismissNotificationsRequest request = new DismissNotificationsRequest();

	request.setUserId(userId);
	request.setNotificationTypePairs(notificationTypePairs);

	return CustomerManagementService.getService().dismissNotifications(request);
}
```
```php
static function DismissNotifications(
	$userId,
	$notificationTypePairs)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new DismissNotificationsRequest();

	$request->UserId = $userId;
	$request->NotificationTypePairs = $notificationTypePairs;

	return $GLOBALS['CustomerManagementProxy']->GetService()->DismissNotifications($request);
}
```
```python
response=customermanagement_service.DismissNotifications(
	UserId=UserId,
	NotificationTypePairs=NotificationTypePairs)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

::: zone-end

::: zone pivot="rest"

## <a name="url"></a>Request Url

# [Production URL](#tab/prod)

```Post
https://clientcenter.api.bingads.microsoft.com/CustomerManagement/v13/Notifications/Dismiss
```

# [Sandbox URL](#tab/sandbox)

```Post
https://clientcenter.api.sandbox.bingads.microsoft.com/CustomerManagement/v13/Notifications/Dismiss
```

-----

## <a name="request"></a>Request Elements
The *DismissNotificationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request.

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="notificationtypepairs"></a>NotificationTypePairs|The key and value of a notification entity.|[KeyValueEntityOflongint](keyvalueentityoflongint.md) array|
|<a name="userid"></a>UserId|The user's identification number.|**int**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DismissNotificationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response JSON](#response-json).

### <a name="response-body"></a>Response Body Elements
There are not any elements in the operation's response body.

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-json"></a>Request JSON
This template was generated by a tool to show the [body](#request-body) and [header](#request-header) elements for the JSON request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```json
{
  "UserId": IntValueHere,
  "NotificationTypePairs": [
    {
      "Key": "LongValueHere",
      "Value": IntValueHere
    }
  ]
}
```

## <a name="response-json"></a>Response JSON
This template was generated by a tool to show the [body](#response-body) and [header](#response-header) elements for the JSON response.

```json
{}
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DismissNotificationsResponse> DismissNotificationsAsync(
	int? userId,
	IList<KeyValueEntityOflongint> notificationTypePairs)
{
	var request = new DismissNotificationsRequest
	{
		UserId = userId,
		NotificationTypePairs = notificationTypePairs
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.DismissNotificationsAsync(r), request));
}
```
```java
static DismissNotificationsResponse dismissNotifications(
	int userId,
	ArrayOfKeyValueEntityOflongint notificationTypePairs) throws RemoteException, Exception
{
	DismissNotificationsRequest request = new DismissNotificationsRequest();

	request.setUserId(userId);
	request.setNotificationTypePairs(notificationTypePairs);

	return CustomerManagementService.getService().dismissNotifications(request);
}
```
```php
static function DismissNotifications(
	$userId,
	$notificationTypePairs)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new DismissNotificationsRequest();

	$request->UserId = $userId;
	$request->NotificationTypePairs = $notificationTypePairs;

	return $GLOBALS['CustomerManagementProxy']->GetService()->DismissNotifications($request);
}
```
```python
response=customermanagement_service.DismissNotifications(
	UserId=UserId,
	NotificationTypePairs=NotificationTypePairs)
```

::: zone-end