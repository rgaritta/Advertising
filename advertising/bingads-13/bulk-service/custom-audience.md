---
title: "Custom Audience Record - Bulk"
ms.service: bing-ads
ms.subservice: bulk-api
ms.topic: "article"
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Describes the Custom Audience fields in a Bulk file.
dev_langs:
  - csharp
---
# Custom Audience Record - Bulk
Defines a custom audience that can be downloaded and uploaded in a bulk file. 

> [!NOTE]
> Only update of the [Audience](#audience) (audience name) and [Description](#description) fields are supported for upload. You can delete but cannot add a custom audience using the Bing Ads API. Having said that, you can add and delete custom audience associations and exclusions.

A custom audience is a type of remarketing list that is generated by using your own customer data to create richer user segments. You can use custom audiences in conjunction with your remarketing lists, usually through your data management provider (DMP). When your DMP connects to our custom audience feature, you can then import your custom audiences into Microsoft Advertising for search remarketing. You can use custom audiences separately from remarketing, with no UET required.

> [!TIP]
> For an overview and more information about audiences, see the [Audience APIs](../guides/universal-event-tracking.md#audience) technical guide. 

You can download all *Custom Audience* records in the account by including the [DownloadEntity](downloadentity.md) value of *CustomAudiences* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would update the description of a custom audience. _Note_: For a custom audience the membership duration is not set in the Microsoft Advertising web application, and Microsoft Advertising defers to your custom audience provider settings.

```csv
Type,Status,Id,Parent Id,Client Id,Modified Time,Name,Description,Scope,Audience,Supported Campaign Types
Format Version,,,,,,6.0,,,,,
Custom Audience,Active,IdHere,ParentIdHere,ClientIdGoesHere,,,Updated Custom Audience Description,30,Account,Custom Audience,Search;DynamicSearchAds;Shopping;Audience
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkCustomAudience* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCustomAudience
var bulkCustomAudience = new BulkCustomAudience
{
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // CustomAudience object of the Campaign Management service.
    CustomAudience = new CustomAudience
    {
        // 'Audience Network Size' column header in the Bulk file
        AudienceNetworkSize = null,
        // 'Description' column header in the Bulk file
        Description = "Updated Custom Audience Description",
        // 'Id' column header in the Bulk file
        Id = customAudienceIdKey,
        // 'Audience' column header in the Bulk file
        Name = null,
        // 'Parent Id' column header in the Bulk file
        ParentId = accountIdKey,
        // 'Scope' column header in the Bulk file
        Scope = null,
        // 'Audience Search Size' column header in the Bulk file
        SearchSize = null,
        // 'Supported Campaign Types' column header in the Bulk file
        SupportedCampaignTypes = null,
    },
                
    // 'Status' column header in the Bulk file
    Status = Status.Active
};

uploadEntities.Add(bulkCustomAudience);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkServiceManager.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

For a *Custom Audience* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Audience](#audience)
- [Audience Network Size](#audiencenetworksize)
- [Audience Search Size](#audiencesearchsize)
- [Client Id](#clientid)
- [Description](#description)
- [Id](#id)
- [Membership Duration](#membershipduration)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Scope](#scope)
- [Status](#status)
- [Supported Campaign Types](#supportedcampaigntypes)

## <a name="audience"></a>Audience
The name of the custom audience.

The name can contain a maximum of 128 characters.  

**Add:** Not supported  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="audiencenetworksize"></a>Audience Network Size
The total number of people who are active members of this audience in the Audience network. This gives you an idea of how many Audience network users you can target.

The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.

**Add:** Not supported  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="audiencesearchsize"></a>Audience Search Size
The total number of people who are active members of this audience in the Search network. This gives you an idea of how many search users you can target.

The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.

This property will be empty for up to 24 hours while the audience is being built, for example if you have imported new custom audiences from DMP, it takes 24 hours to build the audience, and in the meantime this property will be empty.

**Add:** Not supported  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Not supported  
**Update:** Optional    
**Delete:** Read-only  

## <a name="description"></a>Description
The description of the custom audience. Use a description to help you remember what audience you are targeting with this custom audience.

The description can contain a maximum of 1,024 characters.

**Add:** Not supported  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.    
**Delete:** Read-only  

## <a name="id"></a>Id
The system-generated identifier of the custom audience.

**Add:** Not supported  
**Update:** Required  
**Delete:** Read-only and Required  

## <a name="membershipduration"></a>Membership Duration
The membership duration determines how far back in time Microsoft Advertising should look for actions that match your custom audience definition in order to add people to your list. For a custom audience the membership duration is not set in the Microsoft Advertising web application, and Microsoft Advertising defers to your custom audience provider settings.

When you request the custom audience via Bing Ads API, the returned membership duration will be null.

**Add:** Not supported  
**Update:** Not supported  
**Delete:** Read-only  

## <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Not supported  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The Microsoft Advertising identifier of the customer that contains the custom audience.

**Add:** Not supported  
**Update:** Required  
**Delete:** Read-only  

## <a name="scope"></a>Scope
Scope defines what accounts can use this custom audience. For a custom audience the only supported scope is *Customer*, and the custom audience can be associated with any campaigns and ad groups across all of the customer's accounts.

**Add:** Not supported  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="status"></a>Status
The custom audience status.

Possible values are *Active* or *Deleted*. 

**Add:** Not supported  
**Update:** Read-only    
**Delete:** Required. The Status must be set to *Deleted*.  

## <a name="supportedcampaigntypes"></a>Supported Campaign Types
The semicolon delimited list of campaign types that support this custom audience.

Supported values are Audience, DynamicSearchAds, Search, and Shopping. New campaign types might be added in the future, so you should not take any dependency on a fixed set of values.

**Add:** Not supported  
**Update:** Read-only    
**Delete:** Read-only
