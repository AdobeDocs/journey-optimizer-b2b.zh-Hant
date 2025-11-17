---
title: 簡化的架構設定
description: 在簡化的架構上設定Journey Optimizer B2B edition。 設定XDM結構描述、電子郵件/簡訊頻道、Marketo Engage歷程動作和使用者。
feature: Setup, Administration
role: Admin, Data Engineer
hide: true
hidefromtoc: true
source-git-commit: 3f91b2cc92a1ce42d2c62dcfe7eb9de332116023
workflow-type: tm+mt
source-wordcount: '1385'
ht-degree: 6%

---

# 簡化的架構設定

現在可透過簡化的架構使用 Adobe Journey Optimizer B2B Edition。透過此新版架構，Journey Optimizer B2B Edition 和 Marketo Engage 不再位於相同的系統和相同的資料存放庫。Journey Optimizer B2B Edition 只會接收來自 Adobe Experience Platform 的資料。但是仍要仰賴 Marketo Engage 的權限和部分設定功能來進行系統佈建和設定。

簡化的架構是解鎖Adobe Journey Optimizer B2B edition新功能的基礎：

* **輕鬆統一並擴充您的資料：**&#x200B;新平台支援複雜的資料模型，包括自訂物件、購買群組和帳戶事件。 

* **連線多個Adobe Marketo Engage執行個體：**&#x200B;在一個位置管理並統一來自多個Adobe Marketo Engage環境的資料。

* **保護您的資料安全：**&#x200B;進階的隱私和安全性功能，可協助保護您的客戶資訊。 （_即將推出_）

* **為未來打造：**&#x200B;此升級可讓您持續改進與創新。 

針對針對此架構布建的環境，請使用下列設定准則。

## 名稱空間和結構描述

請參閱Experience Platform檔案中的[B2B名稱空間和結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces)以取得概覽。

### 環境設定

設定Postman環境以支援B2B名稱空間和結構描述自動產生公用程式。

* 您可以從[GitHub存放庫](https://github.com/adobe/experience-platform-postman-samples/tree/master/Postman%20Collections/CDP%20Namespaces%20and%20Schemas%20Utility)下載名稱空間和結構描述自動產生公用程式集合和環境。

* 如需有關使用Experience Platform API的資訊，包括如何收集必要標題的值以及讀取範例API呼叫的詳細資訊，請參閱[Experience Platform API快速入門](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-apis/api-guide)指南。

* 如需如何產生Experience Platform API認證的相關資訊，請參閱有關[驗證及存取Experience Platform API](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication)的教學課程。

* 如需有關為Experience Platform API設定Postman的資訊，請參閱Adobe Experience Platform中[Postman](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/postman)的詳細步驟。

設定Experience Platform開發人員控制檯和Postman後，您現在可以開始將適當的環境值套用至您的Postman環境。

### 執行指令碼

透過您的Postman集合和環境設定，您可以透過Postman介面執行指令碼。

在Postman介面中，選取自動產生器公用程式的根資料夾，然後從頂端標題選取&#x200B;**執行**。

顯示Runner介面時，請確定已選取所有核取方塊，然後選取&#x200B;**執行名稱空間和結構描述自動產生公用程式**。

成功的請求會建立B2B所需的名稱空間和結構描述。

## XDM欄位選擇

您可以在Journey Optimizer B2B edition UI中管理整個應用程式內可用的XDM欄位。 這些欄位僅會顯示與建立&#x200B;**_歷程_**、**_購買群組_**&#x200B;或&#x200B;**_電子郵件個人化_**&#x200B;相關的欄位，有助於簡化您的執行個體。

### XDM類別

#### 標準類別

使用下列步驟來定義標準XDM類別的欄位：

1. 瀏覽至&#x200B;**[!UICONTROL 管理] > [!UICONTROL 組態]**。

1. 在導覽面板中，選取&#x200B;**[!UICONTROL XDM類別]**。

1. 選取&#x200B;**[!UICONTROL 標準]**&#x200B;標籤以檢視可用的XDM類別：

   * XDM 個人輪廓

   * XDM商業帳戶

#### 受管理的欄位

定義在整個應用程式中可用的欄位。

1. 按一下&#x200B;_更多功能表_ (**...**)圖示並選取&#x200B;**[!UICONTROL 編輯受管理的欄位]**。

1. 檢閱可用欄位清單（按一下欄位中繼資料的&#x200B;_資訊_&#x200B;圖示）。

1. 選取您要包含的欄位，並清除不需要的欄位選擇。

1. 使用&#x200B;**[!UICONTROL 僅顯示選取的欄位]**&#x200B;滑桿來檢閱您的選取。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

#### 可更新欄位

選擇可以透過&#x200B;**[!UICONTROL 更新帳戶設定檔]**&#x200B;或&#x200B;**[!UICONTROL 更新個人設定檔]**&#x200B;歷程動作修改的欄位。

1. 按一下&#x200B;_更多功能表_ (**...**)圖示並選取&#x200B;**[!UICONTROL 編輯可更新欄位]**。

1. 選取&#x200B;**[!UICONTROL 結構描述]**，然後選取&#x200B;**[!UICONTROL 資料集]**。

   這些結構描述和資料集由您的組織提供。

1. 檢閱可更新欄位清單（按一下中繼資料的&#x200B;_資訊_&#x200B;圖示）。

   只能編輯受管理的欄位。

1. 選取您想讓歷程更新的欄位。

1. 按一下&#x200B;**儲存**

### 關聯式結構描述

選取[關聯式結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational)以用於&#x200B;**_歷程決策_**&#x200B;和&#x200B;**_個人化_**。 目前，這些結構描述適用於自訂物件使用案例。 在未來，關聯式結構描述也可用於其他物件使用案例。

1. 選取&#x200B;**[!UICONTROL 關聯式]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 選取關聯式XDM類別]**。

   目前僅支援帳戶多對一自訂物件。

1. 檢閱結構描述欄位清單（按一下&#x200B;_資訊_&#x200B;圖示以檢視中繼資料）。

1. 選取您要包含的欄位。

1. 使用&#x200B;**[!UICONTROL 僅顯示選取的欄位]**&#x200B;滑桿來檢閱您的選取。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

>[!NOTE]
>
>請注意，關聯式結構描述必須具備下列設定：
>
><li>行為：記錄
>&gt; <li>區段：已啟用
>&gt; <li>關係型別：多對一
>&gt; <li>參考結構描述： <a href="https://experienceleague.adobe.com/zh-hant/docs/platform-learn/tutorials/schemas/create-schemas-for-b2b-data">B2B帳戶 — XDM商業帳戶結構描述</a>
>&gt; <li>必填欄位：主索引鍵、外部索引鍵和版本描述項
>&gt; <li>關聯的資料集：已定義並對應到結構描述

### 事件

選取要在&#x200B;**_歷程決策_**&#x200B;中使用的體驗事件。

1. 選取&#x200B;**[!UICONTROL 事件]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 選取體驗事件]**。

1. 按一下&#x200B;**[!UICONTROL 選取事件型別]**、選取事件型別、按一下&#x200B;**[!UICONTROL 選取]**。

1. 按一下&#x200B;**[!UICONTROL 選取欄位]**，選擇您需要的欄位，按一下&#x200B;**[!UICONTROL 選取]**。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 電子郵件設定

應將以下專案設定為從Journey Optimizer B2B edition傳送電子郵件。  

[https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols)

### 追蹤和電子郵件傳送的協定

1. [建立電子郵件的DNS記錄](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#create-dns-records-for-landing-pages-and-email)

1. [設定SPF和DKIM](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-spf-and-dkim)

1. [設定DMARC](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-dmarc)

1. [為您的網域設定MX記錄](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-mx-records-for-your-domain)

1. [將輸出IP位址新增至允許清單](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/get-started/email-protocols#outbound-ip-addresses)

1. 如果您需要共用專用的IP集區，請聯絡傳遞團隊以瞭解可行性和協助設定。

### 電子郵件通道設定

在簡化的架構中，電子郵件設定是從Marketo Engage UI進行設定。 完成電子郵件相關設定步驟： [https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps)

[https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails)

### 通訊限制

1. 在左側導覽列中，選擇&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 管道]**。

1. 在導覽面板中，選取&#x200B;**[!UICONTROL 通訊限制]**。

1. 建立全域通訊限制規則集(預設會在每個Journey Optimizer B2B edition執行個體中建立此規則集)。

   如果未建立全域規則集，則沒有通訊限制。

<!-- In the future, you can also add local communication limit rule sets (AJO B2C doc can be found here [https://experienceleague.adobe.com/en/docs/journey-optimizer/using/conflict-prioritization/capping-rules/rule-sets](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/conflict-prioritization/capping-rules/rule-sets). We may need a small update for our B2B version.) -->

### 共用通訊限制

在新架構中，Journey Optimizer B2B edition和Marketo Engage預設會有獨立的通訊限制。

如果您希望Marketo Engage執行個體能分享Journey Optimizer B2B edition執行個體中設定的通訊限制，請聯絡Adobe支援以取得設定協助或開啟支援票證。 工程團隊可應要求啟用Journey Optimizer B2B edition與一或多個Marketo Engage執行個體之間的通訊限制共用。

目前，Marketo Engage例項中的共用通訊限制必須透過API呼叫進行設定。

例如，當：

* Journey Optimizer B2B edition執行個體的munchkinId是`JKL-567-MNO`。
* Marketo Engage執行個體的munchkinId為`ABC-123-DEF`，且位於SJ資料中心

API要求應該看起來類似下列：

```
curl --location --request POST 'http://sjrest2a.marketo.org/rest/v1/fm.json?_munchkinId=ABC-123-DEF&featureName=Mktmail%20Config&paramName=ajoB2bMappingMunchkinId&dataType=string&value=JKL-567-MNO'
```

## 簡訊頻道設定

如需詳細資訊，請參閱&#x200B;[_簡訊設定_](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-sms)。

## 歷程中的Marketo Engage動作

您可以設定一或多個遠端&#x200B;**_Marketo Engage_**&#x200B;執行個體，以搭配下列歷程動作使用：

* 新增至Marketo清單
* 從Marketo清單移除
* 新增至Marketo請求行銷活動

完成下列步驟來設定這些連線：

1. 瀏覽至&#x200B;**[!UICONTROL 管理] > [!UICONTROL 組態]**。

1. 在導覽面板中，選取&#x200B;**[!UICONTROL XDM類別]**。

1. 選取&#x200B;**[!UICONTROL 整合]**&#x200B;索引標籤。

1. 按一下&#x200B;**[!UICONTROL 建立連線]**。

1. 輸入&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 描述]**。

1. 選取&#x200B;**[!UICONTROL 更新原則]**&#x200B;以取得相符的人員記錄。

1. 輸入&#x200B;**[!UICONTROL Munchkin ID]**、**[!UICONTROL 使用者端識別碼]**、**[!UICONTROL 使用者端密碼]**，然後按一下&#x200B;**[!UICONTROL 連線至Marketo]**。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 使用者上線

如需概觀，請參閱[使用者管理](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/user-management)頁面。

### 現有使用者群組

如果所有現有Journey Optimizer B2B edition使用者都需要存取新架構，請使用現有Journey Optimizer B2B edition使用者群組。 系統管理員或產品管理員可以執行下列步驟。

1. 在專用的Marketo Engage中建立產品設定檔。

1. 將現有的使用者群組新增到已建立的產品設定檔。

設定檔會授與已指派給該使用者群組的所有角色和許可權，且使用者應已設定這些角色和許可權，以存取Journey Optimizer B2B edition。 如果只有部分使用者應存取新架構，請完成以下概述的步驟。 在[目前檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/user-management)中取得更多詳細資料。

### 建立新的使用者群組

1. 在專用的Marketo Engage執行個體中建立產品設定檔。
1. 為新使用者建立使用者群組。
1. 選擇並將所需的產品設定檔指派給使用者群組：

   * 您建立的Marketo Engage設定檔
   * Adobe Experience Platform設定檔
      * AEP-Default-All-Users
      * Adobe Experience Platform 資料彙集
      * 資料收集所有存取權

1. 將使用者新增至使用者群組。
1. 在Experience Platform中新增使用者群組至Journey Optimizer B2B edition角色。
