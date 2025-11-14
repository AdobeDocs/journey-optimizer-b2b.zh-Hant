---
title: 個人化語法
description: 瞭解Journey Optimizer B2B edition中Handlebars型個人化語法，包括運算式、協助程式、常值型別和格式規則。
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: 運算式，編輯器，語法，個人化
source-git-commit: fee5bddcce11b3035da6ab93b18bcc7006b4b554
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 2%

---

# 個人化語法 {#personalization-syntax}

[!DNL Journey Optimizer B2B Edition] [個人化編輯器](./personalization.md#personalization-editor)中的運算式是以&#x200B;_Handlebars_&#x200B;範本語法為基礎。 它會使用範本和輸入物件來產生HTML或其他文字格式。 Handlebars範本看起來像含有內嵌Handlebars運算式的規則文字。

如需Handlebars及其運作方式的詳細資訊，請參閱[HandlebarsJS檔案](https://handlebarsjs.com/){target="_blank"}。

## 一般規則

簡單運算式範例：

```
{{account.accountName}}
```

其中：

* `account`是名稱空間。
* `accountName`是由屬性組成的Token。

  >[!NOTE]
  >
  >屬性結構是在[Adobe Experience Platform XDM結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home){target="_blank"}中定義。

* 識別碼可以是任何的Unicode字元，但下列字元除外：

  ```
  Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
  ```

* 語法區分大小寫。

* 字詞&#x200B;**true**、**false**、**null**&#x200B;和&#x200B;**未定義**&#x200B;只允許在路徑運算式的第一個部分中。

* 在Handlebars中，{\{expression}\}傳回的值是&#x200B;_HTML逸出_。 如果運算式包含`&`，則會產生傳回的HTML逸出輸出為`&amp;`。 如果您不希望Handlebars逸出值，請使用+triple-stash_。

<!-- For example:

    If the value of the field `profile.person.name` is _Mark & Mary_, the `{\{profile.person.name}\}` value generates as `Mark &amp; Mary` and `{\{\{profile.person.name}}}` renders as `Mark & Mary`. -->

* 對於常值函式引數，範本化語言剖析器不支援單一未逸出的反斜線(`\`)符號。 此字元必須使用額外的反斜線(`\`)符號逸出。 例如：

  ```
  {%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}
  ```

## 輔助程式 {#helpers-all}

Handlebars協助程式函式是可附加引數的簡單識別碼。 每個引數都是Handlebars運算式。 這些協助程式可從電子郵件範本中的任何內容存取。

```sql
{{#each account.accountOrganization.annualRevenue.amount}}
    <li>{{this.name}}</li>
{{/each }}
```

<!-- These block helpers are identified with a `#` preceding the helper name and require a matching closing `/`, of the same name. 

Blocks are expressions that have a block opening ( {\{# }\} ) and closing ( {\{/} } ). -->

如需這些函式的詳細資訊，請參閱[協助程式函式](./personalization-helper-functions.md)。

## 常值型別 {#literal-types}

[!DNL Adobe Journey Optimizer B2B Edition]支援下列常值型別：

| 常值 | 定義 |
| ------- | ---------- |
| 字串 | 由雙引號包住的字元所組成的資料型別。 <br>範例： `"prospect"`， `"jobs"`， `"articles"` |
| 布林值 | 為true或false的資料型別。 |
| 整數 | 代表整數的資料型別。 可以是正數、負數或零。 <br>範例： `-201`， `0`， `412` |
| 陣列 | 一種資料型別，由一組其他常值組成。 它使用方括弧將不同值分組，並使用逗號分隔不同值。<br> **注意：**&#x200B;您無法直接存取陣列中專案的屬性。 <br>範例： `[1, 4, 7]`， `["US", "FR"]` |

>[!CAUTION]
>
>個人化運算式無法使用&#x200B;**xEvent**&#x200B;變數。 對xEvent的任何參考都會導致驗證失敗。
