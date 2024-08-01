---
title: xdm欄位對應
description: 檢閱AEP XDM結構、Marketo Engage和Journey Optimizer B2B版本之間的欄位對應。
exl-id: 8c65fdec-e32d-4ba8-be7b-48522cc3dace
source-git-commit: 78d82aa8b3bb8b8d432eeb187d75e2354dbff3ee
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 16%

---

# xdm欄位對應

資料傳輸服務(DTS)負責將資料從Adobe Experience Platform同步至Journey Optimizer B2B Edition。 DTS仰賴Experience PlatformXDM結構欄位與其Marketo Engage中同等專案之間的對應。

## XDM商業人士預設欄位對應

| [XDM業務人員](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) | XDM顯示名稱 | Marketo Engage顯示名稱 | XDM型別 | Marketo型別 | XDM說明 |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
| `b2b.companyName` | 公司名稱 | 公司名稱 | 字串 | 字串 | 與業務人員相關聯之公司的名稱。 |
| `b2b.companyWebsite` | 公司網站 | 網站 | 字串 | url | 與業務人員相關聯之公司的網站。 |
| `b2b.isMarketingSuspended` | 行銷活動暫停指標 | 行銷活動已暫停 | 布林值 | 布林值 | 該值會指出該人員的行銷活動是否暫停。 |
| `b2b.marketingSuspendedCause` | 行銷活動暫停原因 | 行銷活動暫停原因 | 字串 | 字串 | 如果針對該人員暫停行銷，此屬性會提供原因。 |
| `b2b.personStatus` | 個人狀態 | 銷售機會狀態 | 字串 | 字串 | 記錄人員目前行銷/銷售狀態的欄位。 |
| `consents.marketing.email.reason` | 選擇不接收的原因 | 取消訂閱原因 | 字串 | 字串 | 與電子郵件選擇退出相關的原因。 |
| `consents.marketing.email.val` | 退訂 | 退訂 | 字串 | 布林值 | 如果取消訂閱為true （例如，值= 1），則將`consents.marketing.email.val`設為(n)。 如果取消訂閱為false （例如，值= 0），則將consents.marketing.email.val設定為null。 |
| `extendedWorkDetails.jobTitle` | 職稱 | 職稱 | 字串 | 字串 | 個人的職稱。 |
| `faxPhone.number` | 數字 | 傳真號碼 | 字串 | 電話 | 傳真電話號碼。 |
| `mobilePhone.number` | 數字 | 手機號碼 | 字串 | 電話 | 與個人關聯的行動電話號碼。 |
| `person.birthDate` | 出生日期(YYYY-MM-DD) | 出生日期 | 字串 | 日期 | 個人出生的完整日期。 YYYY-MM-DD |
| `person.name.courtesyTitle` | 尊稱 | 問候語 | 字串 | 字串 | 通常是人員的職稱、尊稱或稱呼語的縮寫。 在開場白中，courtesyTitle用於完整或姓氏的前面。 例如，「先生」、「女士」或「博士」。 |
| `person.name.firstName` | 名字 | 名字 | 字串 | 字串 | 在姓名的語言中最常被接受的書寫順序的第一個姓名區段。 在許多文化中，這是個人偏好名稱或名字。 FirstName和lastName屬性的引入是為了與現有系統保持相容性，現有系統以簡化、非語意和無法國際化的方式模型化名稱。 使用`xdm:fullName`永遠是較好的。 |
| `person.name.lastName` | 姓氏 | 姓氏 | 字串 | 字串 | 在姓名的語言中最常被接受的書寫順序的最後一個姓名區段。 在許多文化中，這是繼承的姓氏、父名或母名。 FirstName和lastName屬性的引入是為了與現有系統保持相容性，現有系統以簡化、非語意和無法國際化的方式模型化名稱。 使用`xdm:fullName`永遠是較好的。 |
| `person.name.middleName` | 中間名 | 中間名 | 字串 | 電話 | 名字和姓氏之間提供的中間名、備用名或附加名。 |
| `workAddress.city ` | 城市 | 城市 | 字串 | 字串 | 城市的名稱。 |
| `workAddress.country` | 國家/地區 | 國家/地區 | 字串 | 字串 | 政府管理的領土的名稱。 除了`xdm:countryCode`，它是自由格式的欄位，可以有任何語言的國家名稱。 |
| `workAddress.postalCode` | 郵遞區號 | 郵遞區號 | 字串 | 字串 | 地點的郵遞區號。 郵遞區號並非適用於所有國家/地區。 在某些國家/地區，它僅包含郵遞區號的一部分。 |
| `workAddress.state` | 狀態 | 狀態 | 字串 | 字串 | 地址的州名。 它是一個自由格式的欄位。 |
| `workAddress.street1` | 街道1 | 地址 | 字串 | 文字 | 主要街道層級資訊、公寓號碼、街道號碼和街道名稱。 |
| `workEmail.address` | 地址 | 電子郵件地址 | 字串 | 電子郵件 | 技術地址，例如，RFC2822和後續標準中通常定義的`<name@domain.com>`。 |
| `workEmail.status` | 狀態 | 電子郵件已暫停 | 字串 | 布林值 | 使用電子郵件地址能力的指示。 |
| `workPhone.number` | 數字 | 電話號碼 | 字串 | 電話 | 公司電話號碼。 |

## XDM商業帳戶預設欄位對應

| [XDM商業帳戶](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/account/account-details.schema.md) | XDM顯示名稱 | Marketo Engage顯示名稱 | XDM型別 | Marketo Engage型別 | XDM說明 |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
| `accountBillingAddress.city` | 城市 | 城市 | 字串 | 字串 | 帳單地址中使用的城市名稱。 |
| `accountBillingAddress.country` | 國家/地區 | 國家/地區 | 字串 | 字串 | 帳單地址中使用的政府管理區域名稱。 除了`xdm:countryCode`，它是自由格式的欄位，可以有任何語言的國家名稱。 |
| `accountBillingAddress.postalCode` | 郵遞區號 | 地址郵遞區號 | 字串 | 字串 | 帳單地址所在位置的郵遞區號。 郵遞區號並非適用於所有國家/地區。 在某些國家/地區，它僅包含郵遞區號的一部分。 |
| `accountBillingAddress.region` | 區域 | 地址區域 | 字串 | 字串 | 帳單地址的地區、國家或地區部分。 |
| `accountBillingAddress.state` | 狀態 | 狀態 | 字串 | 字串 | 帳單地址的州名。 它是一個自由格式的欄位。 |
| `accountBillingAddress.street1` | 街道1 | 街道1 | 字串 | 字串 | 帳單地址的主要街道層級資訊，通常包含公寓號碼、街道號碼和街道名稱。 |
| `accountName` | 名稱 | 名稱 | 字串 | 字串 | 公司名稱。 此欄位允許最多255個字元。 |
| `accountOrganization.annualRevenue.amount` | 年收入 | 年收入 | 數字 | 貨幣 | 預估的組織年收入金額。 |
| `accountOrganization.industry` | 產業 | 產業 | 字串 | 字串 | 歸因於組織的產業。 這是自由格式的欄位，建議使用結構化的值來進行查詢或使用`xdm:classifier`屬性。 |
| `accountOrganization.logoUrl` | 標誌Url | 標誌Url | 字串 | 字串 | 路徑將與Salesforce執行個體的URL （例如`https://yourInstance.salesforce.com/`）結合，以產生URL來請求與帳戶相關聯的社交網路設定檔影像。 產生的URL會傳回HTTP重新導向（代碼302）至帳戶的社交網路設定檔影像。 |
| `accountOrganization.numberOfEmployees` | 員工人數 | 員工人數 | 整數 | 整數 | 組織的員工人數。 |
| `accountOrganization.SICCode` | SIC 代碼 | SIC 代碼 | 字串 | 字串 | 標準產業分類(SIC)代碼，這是四位數的代碼，會根據公司的商業活動將其所屬的產業分類。 |
| `accountOrganization.website` | 網站URL | 網域名稱 | 字串 | 字串 | 組織網站的URL。 |
| `accountPhone.number` | 不適用 | 帳戶電話號碼 | 字串 | 字串 | 與帳戶相關聯的電話號碼。 |
| `accountSourceType` | 不適用 | 來源類型 | 字串 | 字串 | 帳戶的Source型別。 |
