---
title: B2B名稱空間和結構描述
description: 使用Experience Platform自動產生公用程式，為Journey Optimizer B2B edition設定Postman B2B名稱空間和結構描述。
feature: Setup, Data Management
role: Admin
source-git-commit: 023e44e1ad2baed2a5586d95a26ef8693020667a
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 7%

---

# B2B名稱空間和結構描述

簡化的架構上的Journey Optimizer B2B edition設定包括搭配B2B來源使用的Experience Platform名稱空間和結構描述的設定。 產生B2B名稱空間和結構描述需要Postman自動化公用程式。

>[!AVAILABILITY]
>
>- 您必須擁有[Adobe Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview){target="_blank"}的存取權，您的B2B結構描述才能在[即時客戶設定檔](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/profile/home){target="_blank"}中符合資格。
>
>- 您的Experience Platform B2B實體必須使用[B2B名稱空間和結構描述指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/schemas/b2b){target="_blank"}中概述的標準關係。

檢閱下列資訊，瞭解與B2B來源搭配使用的名稱空間和結構描述的基礎設定。 此外，也提供設定Postman自動化公用程式的詳細資訊；產生B2B名稱空間和結構描述時需要此公用程式。

## 設定自動產生公用程式

請參閱下列資源，瞭解先決條件以及如何設定您的[!DNL Postman]環境以支援B2B名稱空間和結構描述自動產生公用程式的詳細資訊。

- 從[GitHub存放庫](https://github.com/adobe/experience-platform-postman-samples/tree/master/Postman%20Collections/CDP%20Namespaces%20and%20Schemas%20Utility){target="_blank"}下載名稱空間和結構描述自動產生公用程式集合和環境。
- 如需有關使用Experience Platform API的資訊，包括有關收集必要標頭的值和讀取範例API呼叫的詳細資訊，請參閱&#x200B;[_Adobe Experience Platform API快速入門_](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-apis/api-guide){target="_blank"}。
- 如需有關產生Experience Platform API認證的資訊，請參閱&#x200B;[_驗證及存取Experience Platform API_](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-apis/api-authentication){target="_blank"}。
- 如需為Experience Platform API設定[!DNL Postman]的相關資訊，請參閱Adobe Experience Platform中的[_[!DNL Postman]_](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-apis/postman){target="_blank"}。

### 環境值

設定Experience Platform開發人員主控台和[!DNL Postman]後，您就可以將適當的環境值套用至您的[!DNL Postman]環境。 下表提供範例值，以及有關填入[!DNL Postman]環境的其他資訊：

| 變數 | 說明 | 範例 |
| --- | --- | --- |
| `CLIENT_SECRET` | 用來產生`{ACCESS_TOKEN}`的唯一識別碼。 | `{CLIENT_SECRET}` |
| `API_KEY` | 用於驗證Experience Platform API呼叫的唯一識別碼。 | `c8d9a2f5c1e03789bd22e8efdd1bdc1b` |
| `ACCESS_TOKEN` | 完成對Experience Platform API的呼叫所需的授權權杖。 | `Bearer {ACCESS_TOKEN}` |
| `META_SCOPE` | 關於[!DNL Journey Optimizer B2B]和[!DNL Marketo Engage]，此值是固定的，且一律設為： `ent_dataservices_sdk`。 | `ent_dataservices_sdk` |
| `CONTAINER_ID` | `global`容器保有所有標準Adobe和Experience Platform合作夥伴提供的類別、結構描述欄位群組、資料型別和結構描述。 關於[!DNL Marketo]，此值是固定的，且一律設為`global`。 | `global` |
| `TECHNICAL_ACCOUNT_ID` | 用來整合至Adobe I/O的認證。 | `D42AEVJZTTJC6LZADUBVPA15@techacct.adobe.com` |
| `IMS` | Identity Management系統(IMS)提供驗證Adobe服務的架構。 關於[!DNL Journey Optimizer B2B]和[!DNL Marketo Engage]，此值是固定的，且一律設為： `ims-na1.adobelogin.com`。 | `ims-na1.adobelogin.com` |
| `IMS_ORG` | 企業實體，可以擁有或授權產品及服務並允許存取其成員。 | `ABCEH0D9KX6A7WA7ATQE0TE@adobeOrg` |
| `SANDBOX_NAME` | 您正在使用的虛擬沙箱分割的名稱。 | `prod` |
| `TENANT_ID` | ID，用來確保您建立的資源已正確命名且包含在您的組織內。 | `b2bcdpproductiontest` |
| `PLATFORM_URL` | 您對其進行API呼叫的URL端點。 此值是固定的，且一律設為： `http://platform.adobe.io/`。 | `http://platform.adobe.io/` |

{style="table-layout:auto"}

### 執行指令碼

設定好環境值後，請使用[!DNL Postman]介面執行指令碼以建立名稱空間和結構描述。 選取自動產生器公用程式的根資料夾，然後從頂端標題選取&#x200B;**[!DNL Run]**。

![Postman UI中名稱空間和結構描述產生器的根資料夾](./assets/namespaces-schemas-postman-root-folder.png){width="500" zoomable="yes"}

[!DNL Runner]介面出現。 從這裡，確定已選取所有核取方塊，然後選取&#x200B;**[!DNL Run Namespaces and Schemas Autogeneration Utility]**。

![已選取名稱空間和結構描述集合中有數個請求的Postman UI。](./assets/namespaces-schemas-postman-run-generator.png){width="800" zoomable="yes"}

成功的請求會建立必要的B2B名稱空間和結構描述。

## B2B名稱空間

身分識別名稱空間是Experience Platform [[!DNL Identity Service]](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/home){target="_blank"}的元件，用來區分身分識別的內容。 完整身分包含身分值和名稱空間。 如需詳細資訊，請參閱[名稱空間概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces){target="_blank"}。

B2B名稱空間會用於實體的主要身分識別中。

| 顯示名稱 | 身分識別符號 | 身分型別 |
| --- | --- | --- |
| B2B人員 | `b2b_person` | `CROSS_DEVICE` |
| B2B 帳戶 | `b2b_account` | `B2B_ACCOUNT` |
| B2B 機會 | `b2b_opportunity` | `B2B_OPPORTUNITY` |
| B2B機會個人關係 | `b2b_opportunity_person_relation` | `B2B_OPPORTUNITY_PERSON` |
| B2B 行銷活動 | `b2b_campaign` | `B2B_CAMPAIGN` |
| B2B 行銷活動會員 | `b2b_campaign_member` | `B2B_CAMPAIGN_MEMBER` |
| B2B 行銷清單 | `b2b_marketing_list` | `B2B_MARKETING_LIST` |
| B2B 行銷清單成員 | `b2b_marketing_list_member` | `B2B_MARKETING_LIST_MEMBER` |
| B2B帳戶個人關係 | `b2b_account_person_relation` | `B2B_ACCOUNT_PERSON` |

{style="table-layout:auto"}

## B2B結構描述

Experience Platform使用結構描述，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。

在Experience Platform可以內嵌資料之前，必須有一個結構描述資料結構，並提供每個欄位可包含的資料型別限制。 結構描述包含一個基底類別和零個或多個結構描述欄位群組。

如需結構描述組合模型的詳細資訊，包括設計原則和最佳實務，請參閱&#x200B;[_結構描述組合基本概念_](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition){target="_blank"}。

+++ B2B 帳戶

<table>
    <tr>
        <td style="width: 30%;">基底類別</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-account" target="_blank">XDM商業帳戶</a></td>
    </tr>
    <tr>
        <td>欄位群組</td>
        <td>XDM商業帳戶細節</td>
    </tr>
    <tr>
        <td>[!DNL Profile] 在結構描述中</td>
        <td>啟用</td>
    </tr>
    <tr>
        <td>主要身分識別</td>
        <td><code>accountKey.sourceKey</code> 在基底類別中</td>
    </tr>
    <tr>
        <td>主要身分識別命名空間</td>
        <td>B2B 帳戶</td>
    </tr>
    <tr>
        <td>次要身分</td>
        <td><code>extSourceSystemAudit.externalKey.sourceKey</code> 在基底類別中</td>
    </tr>
    <tr>
        <td>次要身分名稱空間</td>
        <td>B2B 帳戶</td>
    </tr>
    <tr>
        <td>關係</td>
        <td><ul><li><code>accountParentKey.sourceKey</code> 在XDM商業帳戶詳細資訊欄位群組中</li><li>目的地屬性： <code>/accountKey/sourceKey</code></li><li>型別：一對一</li><li>參考結構描述：B2B帳戶</li><li>名稱空間： B2B帳戶</li></ul> </td>
    </tr>
</table>

+++

+++ B2B人員

<table>
    <tr>
        <td style="width: 30%;">基底類別</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/individual-profile">XDM個人設定檔</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>欄位群組</td>
        <td><ul><li>XDM商業人士細節</li><li>XDM商業人士要素</li><li>身分對應</li><li>同意和偏好設定詳細資料</li></ul> </td>
    </tr>
    <tr>
        <td>[!DNL Profile] 在結構描述中</td>
        <td>啟用</td>
    </tr>
    <tr>
        <td>主要身分識別</td>
        <td><code>b2b.personKey.sourceKey</code> 在XDM商業人士詳細資料欄位群組中</td>
    </tr>
    <tr>
        <td>主要身分識別命名空間</td>
        <td>B2B人員</td>
    </tr>
    <tr>
        <td>次要身分</td>
        <td><ol><li><code>extSourceSystemAudit.externalKey.sourceKey</code> 「XDM商業人士詳細資訊」欄位群組的</li><li><code>workEmail.address</code> 「XDM商業人士詳細資訊」欄位群組的</li></ol></td>
    </tr>
    <tr>
        <td>次要身分名稱空間</td>
        <td><ol><li>B2B人員</li><li>電子郵件</li></ol></td>
    </tr>
    <tr>
        <td>關係</td>
        <td><ul><li><code>personComponents.sourceAccountKey.sourceKey</code> 「XDM商業人士要素」欄位群組</li><li>型別：多對一</li><li>參考結構描述：B2B帳戶</li><li>名稱空間： B2B帳戶</li><li>目的地屬性： accountKey.sourceKey</li><li>來自目前結構描述的關係名稱：帳戶</li><li>來自參照結構描述的關係名稱：人員</li></ul> </td>
    </tr>
</table>

+++

<!--

+++B2B Opportunity

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-opportunity">XDM Business Opportunity</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Opportunity Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>opportunityKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Opportunity</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td><code>extSourceSystemAudit.externalKey.sourceKey</code> in the base class</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>B2B Opportunity</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td><ul><li><code>accountKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: <code>accountKey.sourceKey</code></li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: Opportunities</li></ul></td>
    </tr>
</table>

+++

+++B2B Opportunity Person Relation

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation">XDM Business Opportunity Person Relation</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>opportunityPersonKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Opportunity Person Relation</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td> **First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Opportunities</li></ul>**Second relationship**<ul><li><code>opportunityKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Opportunity </li><li>Namespace: B2B Opportunity </li><li>Destination property: <code>opportunityKey.sourceKey</code></li><li>Relationship name from current schema: Opportunity</li><li>Relationship name from reference schema: People</li></ul> </td>
    </tr>
</table>


+++

+++B2B Campaign

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-campaign">XDM Business Campaign</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Campaign Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>campaignKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Campaign</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>None</td>
    </tr>
</table>

+++

+++B2B Campaign Member

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-campaign-members">XDM Business Campaign Members</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Campaign Member Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>campaignMemberKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Campaign Member</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Campaigns</li></ul>**Second relationship**<ul><li><code>campaignKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Campaign</li><li>Namespace: B2B Campaign</li><li>Destination property: <code>campaignKey.sourceKey</code></li><li>Relationship name from current schema: Campaign</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

+++B2B Marketing List

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-marketing-list">XDM Business Marketing List</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>marketingListKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Marketing List</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>None</td>
    </tr>
</table>

>[!NOTE]
>
>Static List in [!UICONTROL Marketo Engage] is not synced from Salesforce and therefore does not have a secondary identity.

+++

+++B2B Marketing List Member

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members">XDM Business Marketing List Members</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>marketingListMemberKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Marketing List Member</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Marketing Lists</li></ul>**Second relationship**<ul><li><code>marketingListKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Marketing List</li><li>Namespace: B2B Marketing List</li><li>Destination property: <code>marketingListKey.sourceKey</code></li><li>Relationship name from current schema: Marketing List</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

>[!NOTE]
>
>Static List member in [!UICONTROL Marketo Engage] is not synced from Salesforce and therefore does not have a secondary identity.

+++

+++B2B Account Person Relation

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/classes/b2b/business-account-person-relation">XDM Business Account Person Relation</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>Identity Map</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>accountPersonKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Account Person Relation</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: People</li><li>Relationship name from reference schema: Account</li></ul>**Second relationship**<ul><li><code>accountKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: <code>accountKey.sourceKey</code></li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

+++

-->
