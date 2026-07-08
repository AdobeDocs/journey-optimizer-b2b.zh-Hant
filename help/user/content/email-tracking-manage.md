---
title: 管理電子郵件開啟追蹤
description: 停用個別電子郵件的電子郵件開啟追蹤，或擷取個人的追蹤偏好設定，並使用分割路徑來傳送追蹤和非追蹤電子郵件變體。
feature: Account Journeys, Channels
topic: Content Management
role: User
level: Beginner, Intermediate
autotag-review: '2026-07-08T00:02:50.497Z'
TQID: 'https://experienceleague.adobe.com/LIutoajlpVQTeJP2y4i0Wv7H-WqGj-c-LVsOGfin384'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: e666e996-b2cf-4c45-8fc2-1c625212ababid: f01b5556-e951-40ba-8625-2e3001864f2b
subfeature_v2: id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 61481d57fb8eca805d9a9bc545124aed568b5416
workflow-type: tm+mt
source-wordcount: 860
ht-degree: 0%

---

# 管理電子郵件開啟追蹤

您可以停用個別電子郵件的開啟追蹤，或在Adobe Experience Platform中擷取每個人的追蹤偏好設定，並使用分割路徑將人們路由至追蹤和非追蹤電子郵件變體。

>[!BEGINSHADEBOX &quot;CNIL關於電子郵件追蹤畫素的指南&quot;]

在2026年4月14日，*國家資訊與自由委員會* (CNIL)發佈了關於在電子郵件中使用追蹤畫素的[建議](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)。 此指引澄清何時需要同意，並強調正確同意實務對於電子郵件畫素追蹤的重要性。 此政策可能會影響任何實體傳送電子郵件給法國訂閱者的傳送實務。

電子郵件追蹤畫素是內嵌在電子郵件HTML中的1x1透明影像。 收件者的電子郵件使用者端載入該影像時，畫素會偵測伺服器並記錄時間戳記、裝置型別、電子郵件使用者端等資料，有時還會偵測大致位置的IP位址。 然後，該記錄會繫結至收件者的記錄，讓行銷人員知道電子郵件是否已開啟。

此處說明的[!UICONTROL Journey Optimizer B2B edition]產品功能是建置區塊，只要設定及運作正確，即可支援相容的實作。 每位客戶都有責任決定及遵守其適用法律所規範的義務。

>[!ENDSHADEBOX]

## 停用單一電子郵件的追蹤 {#disable-tracking-single-email}

當您想要特定電子郵件永不報告開啟的活動時，無論該活動的接收者為何，請使用此選項。

1. 從右側的歷程節點屬性中，開啟電子郵件。

1. 在電子郵件屬性中，選取&#x200B;**[!UICONTROL 停用開啟追蹤]**&#x200B;核取方塊。

   ![停用電子郵件開啟追蹤](./assets/email-tracking-disable-all.png){width="500" zoomable="yes"}

   如需電子郵件屬性的完整清單，請參閱[定義電子郵件設定](./add-email.md#define-the-email-settings)。

## 依追蹤偏好設定來劃分人員 {#segment-people-tracking-preference}

如果您想要讓每個人都選擇是否追蹤其電子郵件開啟，請在Adobe Experience Platform (AEP)中將該偏好設定擷取為人員屬性。 您可以在[登陸頁面表單](./forms.md)中使用此欄位，讓您的連絡人有機會選擇退出電子郵件開啟追蹤。 接著，您可以在歷程中使用&#x200B;_分割路徑_&#x200B;節點，將追蹤與非追蹤人員路由至不同的電子郵件變體。 這可讓您在不停用每個人的開啟追蹤的情況下，執行個別的選擇退出。

工作流程包含三個部分：

1. [在AEP中新增追蹤偏好設定的自訂欄位](#add-custom-field-tracking-preference)，並透過表單連結傳送選擇退出通訊。
1. [在歷程中新增追蹤選擇退出的分割路徑](#add-split-path-tracking)。
1. [為每個路徑設定追蹤與非追蹤電子郵件變體](#configure-tracking-and-non-tracking-email-variants)。

### 新增自訂欄位以追蹤偏好設定 {#add-custom-field-tracking-preference}

>[!NOTE]
>
>新增和對應自訂XDM欄位是Adobe Experience Platform管理工作。 請與您的AEP管理員或資料工程團隊合作，以完成此步驟。

1. 在AEP中，開啟用於您B2B人員設定檔的結構描述（例如，_B2B人員_）。

1. 在租使用者ID底下，找到或建立您組織同意管理欄位的欄位群組（例如，`consents`）。

1. 將欄位新增至欄位群組，例如名為`emailTracking`的布林欄位，以表示人員是否同意開啟追蹤。

1. 輸入欄位名稱和顯示名稱、設定型別、將其指派給欄位群組，然後按一下&#x200B;**[!UICONTROL 套用]**。

1. 按一下[儲存]儲存結構描述變更。****

   ![將emailTracking欄位新增至AEP結構描述同意欄位群組](./assets/email-tracking-xdm-field-aep-schema.png){width="800" zoomable="yes"}

1. 在[!DNL Journey Optimizer B2B Edition]中，選取該欄位作為[XDM欄位管理](../admin/xdm-field-management.md#managed-fields)中[!UICONTROL XDM個別設定檔]類別的&#x200B;_受管理欄位_，讓此欄位可供使用。

   ![在XDM欄位管理中選取emailTracking作為Managed欄位](./assets/email-tracking-xdm-field-select.png){width="450"}

   這使得該欄位可在分割路徑節點中作為條件使用。

### 新增分割路徑以追蹤選擇退出 {#add-split-path-tracking}

將&#x200B;[_依人員分割的路徑_&#x200B;節點](../journeys/split-merge-paths-nodes.md#split-paths-by-people)新增至您的歷程，並定義每個追蹤偏好設定值的路徑。

1. 新增&#x200B;**[!UICONTROL 分割路徑]**&#x200B;節點並選擇&#x200B;**[!UICONTROL 人員]**&#x200B;進行分割。

1. 對於第一個路徑，請使用您的自訂追蹤偏好設定欄位套用條件（例如，`emailTracking`為`true`）以識別允許開啟追蹤的人員。

   ![分割路徑條件 — 將電子郵件追蹤欄位新增為true](./assets/email-tracking-condition-true.png){width="700" zoomable="yes"}

1. 新增第二個路徑並套用反向條件（`emailTracking`為`false`），以識別選擇退出追蹤的人。

   如需新增路徑、套用條件和重新排序路徑的一般步驟，請參閱[依人員節點新增分割路徑](../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node)。

   ![依人員分割路徑 — 開啟和關閉條件的電子郵件追蹤](./assets/email-tracking-split-paths.png){width="500" zoomable="yes"}

### 設定追蹤和非追蹤電子郵件變體 {#configure-tracking-and-non-tracking-email-variants}

將[_[!UICONTROL 傳送電子郵件&#x200B;]_動作節點](./add-email.md)新增至每個路徑，讓每個人都能收到符合其追蹤偏好設定的電子郵件變體。

1. 在啟用追蹤的路徑上，新增&#x200B;**[!UICONTROL 傳送電子郵件]**&#x200B;動作，然後照常選取或建立電子郵件，保留&#x200B;**[!UICONTROL 停用開啟追蹤]**&#x200B;在電子郵件屬性中清除。

1. 在選擇退出路徑上，使用相同或重複的電子郵件新增&#x200B;**[!UICONTROL 傳送電子郵件]**&#x200B;動作，然後在右側的電子郵件屬性中選取&#x200B;**[!UICONTROL 停用開啟追蹤]**&#x200B;核取方塊。

   ![追蹤路徑的電子郵件 — 停用開啟追蹤](./assets/email-tracking-disable.png){width="600" zoomable="yes"}

1. [發佈此歷程](../journeys/create-publish-journey.md#publish-a-journey)。

   系統會自動將人員路由至符合其追蹤偏好設定欄位值的電子郵件變體，他們對其偏好設定所做的任何更新會在下次進入歷程時反映出來。
