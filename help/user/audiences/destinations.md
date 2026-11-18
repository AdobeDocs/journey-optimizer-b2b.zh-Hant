---
title: 目的地
description: 瞭解支援的Experience Platform目的地，以及如何連線目的地以在Journey Optimizer B2B Edition中啟用靜態人物清單。
feature: Audiences, Integrations
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
source-git-commit: 734966636b6d2addf014905431fa755f6fe92ee6
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 4%
---

# 目的地

目的地是預先建立的整合，可讓您將[靜態人員清單](./people-lists-static.md)成員和帳戶歷程對象傳送至社交平台。 將靜態清單啟用至目的地，可讓成員資格保持同步。 將人員新增至清單或從清單中移除時，目標對象會相應新增或移除人員，延伸至對象摘要的任何行銷活動。

有三種方式可將人員啟用至連線的目的地：

* **從靜態清單** — 直接從&#x200B;**_[!UICONTROL 人員清單]_**&#x200B;索引標籤啟動現有的靜態清單。 請參閱&#x200B;[_啟用至目的地_](./people-lists-static.md#static-list-activate)。
* **從帳戶歷程** — 將&#x200B;**_[!UICONTROL 啟用至目的地]_**&#x200B;動作節點新增至歷程路徑，以便合格帳戶在到達該節點時啟用至目的地。 請參閱&#x200B;[_在目的地_](../journeys/action-nodes.md#activate-deactivate-destination)&#x200B;啟動或停用。
* **來自購買群組** — 若要填入購買群組中的空角色，您可以啟用LinkedIn相符對象來鎖定符合購買群組引數的潛在客戶。 檢視[_LinkedIn帳戶符合audience_s](../data/linkedin-account-matched-audiences.md#activate-buying-group)。

>[!BEGINSHADEBOX]

## 必要權限 {#required-permissions}

完整目的地功能需要下列[!DNL Adobe Experience Platform]許可權。

| 類別 | 權限 |
|--- |--- |--- |
| 沙箱 | 沙箱存取 |
| 儀表板 | 檢視標準儀表板 |
| 儀表板 | 管理標準儀表板 |
| 目的地 | 檢視目的地 |
| 目的地 | 管理目的地 |
| 目的地 | 啟用目的地 |
| 目的地 | 啟用區段而不進行對應 |
| 目的地 | 管理和啟用資料集目的地 |
| 目的地 | 目的地製作 |
| 資料治理 | 檢視資料使用原則 |
| 資料治理 | 管理資料使用原則 |
| 資料擷取 | 檢視來源 |
| 資料擷取 | 管理來源 |
| 輪廓管理 | 檢視設定檔設定 |
| 輪廓管理 | 管理設定檔設定 |

>[!ENDSHADEBOX]

## 支援的目的地 {#supported-destinations}

目的地必須存在於目的地目錄中，您才能啟用靜態清單。 在左側導覽列中，展開&#x200B;**[!UICONTROL 連線]**&#x200B;並選取&#x200B;**[!UICONTROL 目的地]**。 [!DNL Journey Optimizer B2B Edition]目前支援&#x200B;**[!UICONTROL LinkedIn相符對象]** (Social)目的地。 檢視&#x200B;[_LinkedIn帳戶符合的對象_](../data/linkedin-account-matched-audiences.md)

<!-- 
the following destinations:

* **[!UICONTROL Google Customer Match]** (Advertising)
* **[!UICONTROL Facebook Custom Audience]** (Social)
* **[!UICONTROL LinkedIn Matched Audience]** (Social)

![Access the available connector types](./assets/destinations-catalog.png){width="800" zoomable="yes"}

-->

>[!NOTE]
>
>顯示的目錄不是完整的[!DNL Adobe Experience Platform]目的地目錄。 如果您直接從[!DNL Experience Platform]存取目的地，您會看到較大型的目錄，但目前在[!DNL Journey Optimizer B2B Edition]中只能啟用這些目的地。 未來版本計畫推出其他目的地。

## 設定目的地 {#set-up-destination}

每個支援的目的地卡片都會顯示&#x200B;**[!UICONTROL 設定新的目的地]**。 設定目的地是啟用的先決條件。

1. 在聯結器卡中，按一下&#x200B;**[!UICONTROL 設定新的目的地]**。

   ![設定新的目的地](./assets/destinations-configure-new.png){width="500"}

1. Select **[!UICONTROL 現有帳戶]**&#x200B;或&#x200B;**[!UICONTROL 新帳戶]**，然後輸入帳戶詳細資料，例如帳戶名稱和說明。

1. 按一下&#x200B;**[!UICONTROL 連線到目的地]**。

   OAuth流程可讓您登入對應的帳戶：LinkedIn、Google或Facebook。

   >[!IMPORTANT]
   >
   >此時，請勿輸入&#x200B;_[!UICONTROL 目的地詳細資料]_。 只需要連線。

1. 完成人員屬性與目的地所需欄位之間的任何所需欄位對應。

1. 檢閱資料控管和行銷動作設定，然後按一下[儲存]。**&#x200B;**

如需完整的設定步驟，請參閱[!DNL Experience Platform]檔案中的[建立新的目的地連線](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/ui/connect-destination){target="_blank"}。

設定後，目的地可供您在[!DNL Journey Optimizer B2B Edition]中選取目的地的所有地方啟動。

## 啟用與同步 {#activation-sync}

啟用由靜態清單成員資格驅動，在清單和目的地對象之間具有雙向同步：

* 將人員新增至靜態清單會在24小時內將其啟用至目的地，新增至目的地對象，接著新增至對象摘要的任何促銷活動。
* 從靜態清單中移除人員，會將其從目的地停用。 它們會從目的地對象及任何已連線的行銷活動中移除。
* 同一份清單可一次啟用至多個目的地。 會籍會同步至所有成員。

>[!TIP]
>
>若要針對區段執行LinkedIn行銷活動，請針對您的LinkedIn相符對象目的地啟用這些人員的靜態清單。 清單中的所有人都會新增至LinkedIn中的相符對象，行銷活動可鎖定這些人，且對象會在清單變更時自動保持最新狀態。
