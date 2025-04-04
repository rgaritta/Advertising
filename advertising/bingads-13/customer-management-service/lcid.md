---
title: LCID Value Set - Customer Management
ms.service: bing-ads
ms.subservice: customer-management-api
ms.topic: article
author: jonmeyers
ms.author: jonmeyers
ms.date: 11/13/2024
description: Defines a selection of locale values.
---
# LCID Value Set - Customer Management
Defines a selection of locale values.

> [!NOTE]
> The value set defines a broad selection of locales; however, not all languages are supported in each market. For a list of supported languages by market country or region, see [Ad Languages](../guides/ad-languages.md).

## Syntax
```xml
<xs:simpleType name="LCID" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="ArabicSaudiArabia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1025</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicAlgeria">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">5121</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicBahrain">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">15361</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicEgypt">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3073</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicIraq">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2049</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicJordan">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">11265</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicKuwait">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">13313</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicLebanon">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">12289</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicLibya">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4097</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicMorocco">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">6145</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicOman">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8193</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicQatar">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16385</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicTunisia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">7169</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicUnitedArabEmirates">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">14337</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ArabicYemen">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">9217</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ChineseTaiwan">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1028</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DanishDenmark">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1030</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="GermanGermany">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1031</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishUS">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1033</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishSpain">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1034</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FinnishFinland">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1035</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FrenchFrance">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1036</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="HebrewIsrael">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1037</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ItalianItaly">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1040</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="JapaneseJapan">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1041</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="KoreanKorea">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1042</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="DutchNetherlands">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1043</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="NorwegianNorway">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1044</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="PortugueseBrazil">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1046</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="RussianRussia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1049</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SwedishSweden">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1053</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishThailand">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1054</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishIndonesia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1057</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Slovenian">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1060</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Latvian">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1062</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishVietnam">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1066</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ChineseChina">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2052</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="GermanSwitzerland">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2055</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishUK">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2057</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishMexico">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2058</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ChineseHongKong">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3076</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="GermanAustria">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3079</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishAustralia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3081</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FrenchCanada">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3084</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishCanada">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4105</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishNewZealand">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">5129</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishIreland">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">6153</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishVenezuela">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8202</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishColombia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">9226</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishPeru">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">10250</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishArgentina">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">11274</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishPhilippines">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">13321</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="SpanishChile">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">13322</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishIndia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16393</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishMalaysia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">17417</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="EnglishSingapore">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">18441</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="TurkishTurkey">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1055</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FilipinoPhilippines">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1124</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="PolandPolish">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1045</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="MalayMalaysia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1086</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="UkrainianUkraine">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1058</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="CzechRepublicCZ">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1029</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="RomaniaRO">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1048</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="GreekGreece">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1032</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="HungaryHU">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1038</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="HindiIndia">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1081</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Bulgarian">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1026</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Lithuanian">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1063</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Croatian">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1050</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [LCID](lcid.md) value set has the following values: [ArabicAlgeria](#arabicalgeria), [ArabicBahrain](#arabicbahrain), [ArabicEgypt](#arabicegypt), [ArabicIraq](#arabiciraq), [ArabicJordan](#arabicjordan), [ArabicKuwait](#arabickuwait), [ArabicLebanon](#arabiclebanon), [ArabicLibya](#arabiclibya), [ArabicMorocco](#arabicmorocco), [ArabicOman](#arabicoman), [ArabicQatar](#arabicqatar), [ArabicSaudiArabia](#arabicsaudiarabia), [ArabicTunisia](#arabictunisia), [ArabicUnitedArabEmirates](#arabicunitedarabemirates), [ArabicYemen](#arabicyemen), [Bulgarian](#bulgarian), [ChineseChina](#chinesechina), [ChineseHongKong](#chinesehongkong), [ChineseTaiwan](#chinesetaiwan), [Croatian](#croatian), [CzechRepublicCZ](#czechrepubliccz), [DanishDenmark](#danishdenmark), [DutchNetherlands](#dutchnetherlands), [EnglishAustralia](#englishaustralia), [EnglishCanada](#englishcanada), [EnglishIndia](#englishindia), [EnglishIndonesia](#englishindonesia), [EnglishIreland](#englishireland), [EnglishMalaysia](#englishmalaysia), [EnglishNewZealand](#englishnewzealand), [EnglishPhilippines](#englishphilippines), [EnglishSingapore](#englishsingapore), [EnglishThailand](#englishthailand), [EnglishUK](#englishuk), [EnglishUS](#englishus), [EnglishVietnam](#englishvietnam), [FilipinoPhilippines](#filipinophilippines), [FinnishFinland](#finnishfinland), [FrenchCanada](#frenchcanada), [FrenchFrance](#frenchfrance), [GermanAustria](#germanaustria), [GermanGermany](#germangermany), [GermanSwitzerland](#germanswitzerland), [GreekGreece](#greekgreece), [HebrewIsrael](#hebrewisrael), [HindiIndia](#hindiindia), [HungaryHU](#hungaryhu), [ItalianItaly](#italianitaly), [JapaneseJapan](#japanesejapan), [KoreanKorea](#koreankorea), [Latvian](#latvian), [Lithuanian](#lithuanian), [MalayMalaysia](#malaymalaysia), [NorwegianNorway](#norwegiannorway), [PolandPolish](#polandpolish), [PortugueseBrazil](#portuguesebrazil), [RomaniaRO](#romaniaro), [RussianRussia](#russianrussia), [Slovenian](#slovenian), [SpanishArgentina](#spanishargentina), [SpanishChile](#spanishchile), [SpanishColombia](#spanishcolombia), [SpanishMexico](#spanishmexico), [SpanishPeru](#spanishperu), [SpanishSpain](#spanishspain), [SpanishVenezuela](#spanishvenezuela), [SwedishSweden](#swedishsweden), [TurkishTurkey](#turkishturkey), [UkrainianUkraine](#ukrainianukraine).

|Value|Description|
|-----------|---------------|
|<a name="arabicalgeria"></a>ArabicAlgeria|Arabic (Algeria), 5121|
|<a name="arabicbahrain"></a>ArabicBahrain|Arabic (Bahrain), 15361|
|<a name="arabicegypt"></a>ArabicEgypt|Arabic (Egypt), 3073|
|<a name="arabiciraq"></a>ArabicIraq|Arabic (Iraq), 2049|
|<a name="arabicjordan"></a>ArabicJordan|Arabic (Jordan), 11265|
|<a name="arabickuwait"></a>ArabicKuwait|Arabic (Kuwait), 13313|
|<a name="arabiclebanon"></a>ArabicLebanon|Arabic (Lebanon), 12289|
|<a name="arabiclibya"></a>ArabicLibya|Arabic (Libya), 4097|
|<a name="arabicmorocco"></a>ArabicMorocco|Arabic (Morocco), 6145|
|<a name="arabicoman"></a>ArabicOman|Arabic (Oman), 8193|
|<a name="arabicqatar"></a>ArabicQatar|Arabic (Qatar), 16385|
|<a name="arabicsaudiarabia"></a>ArabicSaudiArabia|Arabic (Saudi Arabia), 1025|
|<a name="arabictunisia"></a>ArabicTunisia|Arabic (Tunisia), 7169|
|<a name="arabicunitedarabemirates"></a>ArabicUnitedArabEmirates|Arabic (United Arab Emirates), 14337|
|<a name="arabicyemen"></a>ArabicYemen|Arabic (Yemen), 9217|
|<a name="bulgarian"></a>Bulgarian|Bulgarian (Bulgaria), 1026|
|<a name="chinesechina"></a>ChineseChina|Chinese (China), 2052|
|<a name="chinesehongkong"></a>ChineseHongKong|Chinese (Hong Kong SAR), 3076|
|<a name="chinesetaiwan"></a>ChineseTaiwan|Chinese (Taiwan), 1028|
|<a name="croatian"></a>Croatian|Croatian (Croatia), 1050|
|<a name="czechrepubliccz"></a>CzechRepublicCZ|Czech (Czech Republic), 1029|
|<a name="danishdenmark"></a>DanishDenmark|Danish (Denmark), 1030|
|<a name="dutchnetherlands"></a>DutchNetherlands|Dutch (Netherlands), 1043|
|<a name="englishaustralia"></a>EnglishAustralia|English (Australia), 3081|
|<a name="englishcanada"></a>EnglishCanada|English (Canada), 4105|
|<a name="englishindia"></a>EnglishIndia|English (India), 16393|
|<a name="englishindonesia"></a>EnglishIndonesia|English (Indonesia), 1057|
|<a name="englishireland"></a>EnglishIreland|English (Ireland), 6153|
|<a name="englishmalaysia"></a>EnglishMalaysia|English (Malaysia), 17417|
|<a name="englishnewzealand"></a>EnglishNewZealand|English (New Zealand), 5129|
|<a name="englishphilippines"></a>EnglishPhilippines|English (Philippines), 13321|
|<a name="englishsingapore"></a>EnglishSingapore|English (Singapore), 18441|
|<a name="englishthailand"></a>EnglishThailand|English (Thailand), 1054|
|<a name="englishuk"></a>EnglishUK|English (United Kingdom), 2057|
|<a name="englishus"></a>EnglishUS|English (United States), 1033|
|<a name="englishvietnam"></a>EnglishVietnam|English (Vietnam), 1066|
|<a name="filipinophilippines"></a>FilipinoPhilippines|Filipino (Philippines), 1124|
|<a name="finnishfinland"></a>FinnishFinland|Finnish (Finland), 1035|
|<a name="frenchcanada"></a>FrenchCanada|French (Canada), 3084|
|<a name="frenchfrance"></a>FrenchFrance|French (France), 1036|
|<a name="germanaustria"></a>GermanAustria|German (Austria), 3079|
|<a name="germangermany"></a>GermanGermany|German (Germany), 1031|
|<a name="germanswitzerland"></a>GermanSwitzerland|German (Switzerland), 2055|
|<a name="greekgreece"></a>GreekGreece|Greek (Greece), 1032|
|<a name="hebrewisrael"></a>HebrewIsrael|Hebrew (Israel), 1037|
|<a name="hindiindia"></a>HindiIndia|Hindi (India), 1081|
|<a name="hungaryhu"></a>HungaryHU|Hungarian (Hungary), 1038|
|<a name="italianitaly"></a>ItalianItaly|Italian (Italy), 1040|
|<a name="japanesejapan"></a>JapaneseJapan|Japanese (Japan), 1041|
|<a name="koreankorea"></a>KoreanKorea|Korean (Korea), 1042|
|<a name="latvian"></a>Latvian|Latvian (Latvia), 1062|
|<a name="lithuanian"></a>Lithuanian|Lithuanian (Lithuania), 1063|
|<a name="malaymalaysia"></a>MalayMalaysia|Malay (Malaysia), 1086|
|<a name="norwegiannorway"></a>NorwegianNorway|Norwegian (Norway), 1044|
|<a name="polandpolish"></a>PolandPolish|Polish (Poland), 1045|
|<a name="portuguesebrazil"></a>PortugueseBrazil|Portuguese (Brazil), 1046|
|<a name="romaniaro"></a>RomaniaRO|Romanian (Romania), 1048|
|<a name="russianrussia"></a>RussianRussia|Russian (Russia), 1049|
|<a name="slovenian"></a>Slovenian|Slovenian (Slovenia), 1060|
|<a name="spanishargentina"></a>SpanishArgentina|Spanish (Argentina), 11274|
|<a name="spanishchile"></a>SpanishChile|Spanish (Chile), 13322|
|<a name="spanishcolombia"></a>SpanishColombia|Spanish (Colombia), 9226|
|<a name="spanishmexico"></a>SpanishMexico|Spanish (Mexico), 2058|
|<a name="spanishperu"></a>SpanishPeru|Spanish (Peru), 10250|
|<a name="spanishspain"></a>SpanishSpain|Spanish (Spain), 1034|
|<a name="spanishvenezuela"></a>SpanishVenezuela|Spanish (Venezuela), 8202|
|<a name="swedishsweden"></a>SwedishSweden|Swedish (Sweden), 1053|
|<a name="turkishturkey"></a>TurkishTurkey|Turkish (Turkey), 1055|
|<a name="ukrainianukraine"></a>UkrainianUkraine|Ukranian (Ukraine), 1058|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

## Used By
[User](user.md)  
[UserInvitation](userinvitation.md)  
