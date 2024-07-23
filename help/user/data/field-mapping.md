---
title: xdm欄位對應
description: 檢閱AEP XDM結構、Marketo Engage和Journey Optimizer B2B版本之間的欄位對應。
source-git-commit: af287825508b2372f51aa8ea629cc6eda0a50b35
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 17%

---

# xdm欄位對應

中的資料傳輸服務(DTS)負責將資料從Adobe Experience Platform同步至Journey Optimizer B2B Edition。 DTS仰賴Experience PlatformXDM結構欄位與其Marketo Engage中同等專案之間的對應。

## XDM商業人士預設欄位對應

| XDM業務人員 | Marketo Engage人員顯示名稱 | AJO B2B人員顯示名稱 | XDM型別 | Marketo型別 | XDM說明 |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
| `workAddress.street1` | 地址 | ？ | 字串 | 文字 | 主要街道層級資訊、公寓號碼、街道號碼和街道名稱。 |
| `workAddress.city ` | 城市 | 城市 | 字串 | 字串 | 城市的名稱。 |
| `b2b.companyName` | 公司名稱 | ? | 字串 | 字串 | 與業務人員相關聯之公司的名稱。 |
| `workAddress.country` | 國家 | 國家 | 字串 | 字串 | 政府管理的領土的名稱。 除了`xdm:countryCode`，這是自由格式的欄位，可以有任何語言的國家名稱。 |
| `person.birthDate` | 出生日期 | 出生日期 | 字串 | 日期 | 個人出生的完整日期。  YYYY-MM-DD |
| `workEmail.address` | 電子郵件地址 | 電子郵件地址 | 字串 | 電子郵件 | 技術位址，例如，RFC2822和後續標準中通常定義的&#39;<name@domain.com>&#39;。 |
| `workEmail.status` | 電子郵件已暫停 | 電子郵件已暫停 | 字串 | 布林值 | 使用電子郵件地址能力的指示。 |
| `faxPhone.number` | 傳真號碼 | ? | 字串 | 電話 | 傳真電話號碼。 |
| `person.name.firstName` | 名字 | 名字 | 字串 | 字串 | 在姓名的語言中最常被接受的書寫順序的第一個姓名區段。 在許多文化中，這是個人偏好名稱或名字。 FirstName和lastName屬性的引入是為了與現有系統保持相容性，現有系統以簡化、非語意和無法國際化的方式模型化名稱。 使用xdm：fullName一定更可取。 |
| `extendedWorkDetails.jobTitle` | 職稱 | 職稱 | 字串 | 字串 | 個人的職稱。 |
| `person.name.lastName` | 姓氏 | 姓氏 | 字串 | 字串 | 在姓名的語言中最常被接受的書寫順序的最後一個姓名區段。 在許多文化中，這是繼承的姓氏、父名或母名。 FirstName和lastName屬性的引入是為了與現有系統保持相容性，現有系統以簡化、非語意和無法國際化的方式模型化名稱。 使用xdm：fullName一定更可取。 |
| `b2b.personStatus` | 銷售機會狀態 | ? | 字串 | 字串 | 記錄人員目前行銷/銷售狀態的欄位。 |
| `b2b.isMarketingSuspended` | 行銷活動已暫停 | ? | 布林值 | 布林值 | 表示該人員的行銷活動是否暫停。 |
| `b2b.marketingSuspendedCause` | 行銷活動暫停原因 | ? | 字串 | 字串 | 如果針對該人員暫停行銷，此屬性會提供原因。 |
| `person.name.middleName` | 中間名 | ? | 字串 | 電話 | 名字和姓氏之間提供的中間名、備用名或附加名。 |
| `mobilePhone.number` | 手機號碼 | 手機號碼 | 字串 | 電話 | 行動電話號碼。 |
| `workPhone.number` | 電話號碼 | 電話號碼 | 字串 | 電話 | 公司電話號碼。 |
| `workAddress.postalCode` | 郵遞區號 | 郵遞區號 | 字串 | 字串 | 地點的郵遞區號。 郵遞區號並非適用於所有國家/地區。 在某些國家/地區，這僅包含郵遞區號的一部分。 |
| `person.name.courtesyTitle` | 問候語 | ? | 字串 | 字串 | 通常是人員職稱、敬語或稱呼語的縮寫。 在開場白中，courtesyTitle用於全名或姓氏之前。 例如，「先生」、「小姐」或「博士」。 |
| `workAddress.state` | 州別 | 州別 | 字串 | 字串 | 州名。 此為自由格式的欄位。 |
| `consents.marketing.email.val` | 退訂 | 退訂 | 字串 | 布林值 | 如果取消訂閱為true （例如，值= 1），則將`consents.marketing.email.val`設為(n)。 如果取消訂閱為false （例如，值= 0），則將consents.marketing.email.val設定為null。 |
| `consents.marketing.email.reason` | 取消訂閱原因 | 取消訂閱原因 | 字串 | 字串 |  |
| `b2b.companyWebsite` | 網站 | ? | 字串 | url | 與業務人員相關聯之公司的網站。 |

