---
title: "Ad Group Similar Remarketing List Association Record - Bulk"
ms.service: bing-ads
ms.subservice: bulk-api
ms.topic: "article"
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Describes the Ad Group Similar Remarketing List Association fields in a Bulk file.
dev_langs:
  - csharp
---
# Ad Group Similar Remarketing List Association Record - Bulk
Defines an Ad Group Similar Remarketing List Association that can be uploaded and downloaded in a bulk file. 

Audience targets cannot be set both campaign and ad group level. If you set any biddable campaign level audience criteria, then you cannot set any biddable ad group level audience criteria. Audience exclusions can be set at both campaign and ad group level. Microsoft Advertising applies a union of both campaign and ad group level exclusions.

> [!TIP]
> For an overview and more information about audiences, see the [Audience APIs](../guides/universal-event-tracking.md#audience) technical guide. 

You can download all *Ad Group Similar Remarketing List Association* records in the account by including the [DownloadEntity](downloadentity.md) value of *AdGroupSimilarRemarketingListAssociations* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group similar remarketing list association if a valid [Parent Id](#parentid) value is provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Bid Adjustment,Name,Audience Id,Audience
Format Version,,,,,,,,,6.0,,
Ad Group Similar Remarketing List Association,Paused,,-1111,,,ClientIdGoesHere,,10,,SimilarRemarketingListIdHere,My Similar Remarketing List
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkAdGroupSimilarRemarketingListAssociation* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupSimilarRemarketingListAssociation
var bulkAdGroupSimilarRemarketingListAssociation = new BulkAdGroupSimilarRemarketingListAssociation
{
    // 'Ad Group' column header in the Bulk file
    AdGroupName = null,

    // Map properties in the Bulk file to the 
    // BiddableAdGroupCriterion object of the Campaign Management service.
    BiddableAdGroupCriterion = new BiddableAdGroupCriterion
    {
        // 'Parent Id' column header in the Bulk file
        AdGroupId = adGroupIdKey,
        Criterion = new AudienceCriterion
        {
            // 'Audience Id' column header in the Bulk file
            AudienceId = similarRemarketingListIdKey,
        },
        // 'Bid Adjustment' column header in the Bulk file
        CriterionBid = new BidMultiplier
        {
            Multiplier = 10
        },
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Status' column header in the Bulk file
        Status = AdGroupCriterionStatus.Paused
    },
    // 'Campaign' column header in the Bulk file
    CampaignName = null,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
    // 'Audience' column header in the Bulk file
    AudienceName = null,
};

uploadEntities.Add(bulkAdGroupSimilarRemarketingListAssociation);

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

For an *Ad Group Similar Remarketing List Association* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Audience](#audience)
- [Audience Id](#audienceid)
- [Bid Adjustment](#bidadjustment)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)

## <a name="adgroup"></a>Ad Group
The name of the ad group that is associated with the similar remarketing list.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Ad Group](#adgroup) field.


## <a name="audience"></a>Audience
The name of the similar remarketing list.

This bulk field maps to the *Audience* field of the [Similar Remarketing List](similar-remarketing-list.md) record.

**Add:** Read-only and Required for some use cases. You must either specify the [Audience](#audience) or [Audience Id](#audienceid) field. If you are adding new ad group similar remarketing list associations with new similar remarketing lists in the same Bulk file, and if you do not set the [Audience Id](#audienceid) field, then this [Audience](#audience) field must be set as a logical key to the same value as the *Audience* field of the [Similar Remarketing List](similar-remarketing-list.md) record. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="audienceid"></a>Audience Id
The Microsoft Advertising identifier of the similar remarketing list associated with the ad group.

This bulk field maps to the *Id* field of the [Similar Remarketing List](similar-remarketing-list.md) record.

**Add:** Read-only and Required for some use cases. You must either specify the [Audience](#audience) or [Audience Id](#audienceid) field. If you set the [Audience Id](#audienceid) field, you must either specify an existing similar remarketing list identifier or specify a negative identifier that is equal to the *Id* field of the parent [Similar Remarketing List](similar-remarketing-list.md) record. If the [Audience Id](#audienceid) field is not set, then you must set the [Audience](#audience) field as a logical key to the same value as the *Audience* field of the [Similar Remarketing List](similar-remarketing-list.md) record. Any of these options are recommended if you are adding new ad group similar remarketing list associations with new similar remarketing lists in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="bidadjustment"></a>Bid Adjustment
The percentage you want to increase/decrease the bid amount for the similar remarketing list.

Supported values are negative ninety (-90.00) through positive nine hundred (900.00).

> [!IMPORTANT]
> If not specified, the default bid adjustment value is *0*. The default value is subject to change.

> [!IMPORTANT]
> Microsoft Advertising won't apply any bid boosts until the associated similar remarketing list has at least 1,000 users. If someone qualifies to be part of multiple similar remarketing lists AND the similar remarketing lists are associated with the same ad group with different bid adjustments, the highest bid adjustment will be applied. For more information about Remarketing in Paid Search, see [Reach your audience](https://help.ads.microsoft.com/#apex/3/en/n5022/1).

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

## <a name="id"></a>Id
The system-generated identifier for the association between an ad group and similar remarketing list.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

## <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The system-generated identifier of the ad group that is associated to the similar remarketing list.

This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are associating similar remarketing lists to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Ad Group](#adgroup) field.

## <a name="status"></a>Status
The association status. 

Possible values are *Active*, *Paused*, or *Deleted*. 

**Add:** Optional. The default status value is *Active*.   
**Update:** Optional    
**Delete:** Required. The Status must be set to *Deleted*.

