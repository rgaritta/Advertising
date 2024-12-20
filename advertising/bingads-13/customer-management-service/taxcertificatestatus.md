---
title: TaxCertificateStatus Value Set - Customer Management
ms.service: bing-ads
ms.subservice: customer-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines the TaxCertificateStatus Value Set.
---
# TaxCertificateStatus Value Set - Customer Management
Defines the TaxCertificateStatus Value Set.

## Syntax
```xml
<xs:simpleType name="TaxCertificateStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Valid">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">174</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Invalid">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">175</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Pending">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">176</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [TaxCertificateStatus](taxcertificatestatus.md) value set has the following values: [Invalid](#invalid), [Pending](#pending), [Valid](#valid).

|Value|Description|
|-----------|---------------|
|<a name="invalid"></a>Invalid|The status of the tax certificate is *Invalid*.|
|<a name="pending"></a>Pending|The status of the tax certificate is *Pending*.|
|<a name="valid"></a>Valid|The status of the tax certificate is *Valid*.|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

## Used By
[AccountTaxCertificate](accounttaxcertificate.md)  
