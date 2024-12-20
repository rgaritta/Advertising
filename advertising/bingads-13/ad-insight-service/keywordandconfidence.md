---
title: KeywordAndConfidence Data Object - Ad Insight
ms.service: bing-ads
ms.subservice: ad-insight-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines an object that contains a suggested keyword and a confidence score.
---
# KeywordAndConfidence Data Object - Ad Insight
Defines an object that contains a suggested keyword and a confidence score. The confidence score indicates the probability that the keyword would match a user's search query.

## Syntax

# [XML](#tab/xml)

```xml
<xs:complexType name="KeywordAndConfidence" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="SuggestedKeyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ConfidenceScore" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

# [JSON](#tab/json)

```json
{
  "ConfidenceScore": DoubleValueHere,
  "SuggestedKeyword": "ValueHere"
}
```

-----

## <a name="elements"></a>Elements

The [KeywordAndConfidence](keywordandconfidence.md) object has the following elements: [ConfidenceScore](#confidencescore), [SuggestedKeyword](#suggestedkeyword).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="confidencescore"></a>ConfidenceScore|A score from 0.0 to 1.0 that indicates the probability that the keyword would match a user's search query.|**double**|
|<a name="suggestedkeyword"></a>SuggestedKeyword|The suggested keyword.|**string**|

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[KeywordSuggestion](keywordsuggestion.md)  
[SuggestKeywordsForUrl](suggestkeywordsforurl.md)  
