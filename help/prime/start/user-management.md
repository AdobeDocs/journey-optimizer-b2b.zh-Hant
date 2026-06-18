---
title: 使用者存取與許可權
description: 在Adobe Admin Console中管理使用者存取權：建立Journey Optimizer B2B edition Prime的使用者群組、指派產品設定檔，以及設定角色型許可權。
source-git-commit: f471a870b1e54b4588317d495eb7f7625051ac65
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 75%

---

# 使用者存取和許可權

布建完成並繫結沙箱後，請完成下列步驟，為團隊和使用者提供Adobe Journey Optimizer B2B edition存取權。

1. [在Admin Console中建立Adobe Journey Optimizer B2B edition產品設定檔](#ajo-b2b-profile) （僅限一次性/初始設定）。
1. 在Admin Console中[新增使用者群組](#add-user-group)。
1. 在Adobe Experience Platform許可權中[編輯內建角色](#edit-roles-for-product-permissions)或[建立具有Journey Optimizer B2B edition許可權的自訂角色](#create-a-custom-role)。
1. [新增使用者](#add-users-to-a-role)或[群組](#add-user-groups-to-a-role)至Adobe Experience Platform中的角色。

作為管理員，您可以在Adobe Admin Console中完成這些工作，這是管理您的Adobe產品授權和使用者的中心位置。 在Admin Console中，您可以在單一位置而非在各種個別解決方案中建立和管理使用者。 若要瞭解其功能的詳細資訊，請參閱[Admin Console概觀](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)頁面。

## 存取Admin Console

在使用Admin Console管理團隊中的使用者之前，您需要確保您可以存取Admin Console並擁有適當的許可權。

1. 作為系統管理員，您應該會在上線流程中收到來自Adobe的多封電子郵件。

   尋找歡迎電子郵件，提供您被授予存取權的組織名稱相關資訊。

1. 按一下歡迎電子郵件中的&#x200B;**[!UICONTROL 開始使用]**&#x200B;連結，以瀏覽至Admin Console。

   如果找不到電子郵件，請直接在[https://adminconsole.adobe.com](https://adminconsole.adobe.com)開啟瀏覽器並存取Admin Console。

1. 使用您的Adobe ID登入。

   登入成功後，您會看到Adobe Admin Console的&#x200B;_概觀_&#x200B;頁面。

1. 如果您可以存取多個組織，請確保您已登入正確的組織。

   若要變更您的組織，請按一下右上角的組織名稱，然後選擇您需要存取的組織。

1. 從&#x200B;_[!UICONTROL 使用者]_&#x200B;卡中選擇&#x200B;**[!UICONTROL 管理員]**&#x200B;以驗證您是系統管理員。

   ![Admin Console概觀 — 按一下[管理員]](./assets/admin-console-overview-administrators.png){width="800" zoomable="yes"}

1. 透過輸入您的Adobe ID電子郵件、使用者名稱、名字或姓氏進行搜尋。

   * 如果您的存取權設定正確，搜尋會傳回您的記錄。

   * 如果&#x200B;**[!UICONTROL 管理員角色]**&#x200B;欄中的值顯示`System`，您就知道您（或顯示的使用者）是系統管理員。

## 建立Adobe Journey Optimizer B2B edition產品設定檔 {#ajo-b2b-profile}

在授與使用者Adobe解決方案的存取權時，您不一定要授與他們完整的存取權。 產品設定檔使每個解決方案都可以擁有自己的一組使用者許可權。 使用Admin Console指派產品設定檔。

如需有關使用產品設定檔取得使用者許可權的詳細資訊，請參閱Admin Console檔案中的&#x200B;[_管理企業使用者的產品設定檔_](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html){target="_blank"}。

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或Adobe Journey Optimizer B2B edition產品管理員可以執行下列步驟。

1. 登入[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 選取「**[!UICONTROL 產品]**」標籤。

1. 開啟您想要新增設定檔的Adobe Journey Optimizer B2B edition執行個體，然後按一下&#x200B;**[!UICONTROL 新增設定檔]**。

   ![Experience Platform — 使用者群組](./assets/admin-console-product-profiles.png){width="600" zoomable="yes"}的產品設定檔

1. 輸入產品設定檔名稱，例如&#x200B;_B2B使用者_。

1. 按一下[下一步]****，然後按一下[儲存]****。

## 新增使用者群組 {#add-user-group}

使用者群組是獲授一組共用許可權的使用者集合。 您可以在使用者群組中新增或移除使用者。 當群組內的使用者變更時，群組許可權會維持不變。

如需有關如何使用使用者群組來管理許可權的詳細資訊，請參閱Admin Console檔案中的[管理使用者群組](https://helpx.adobe.com/tw/enterprise/using/user-groups.html){target="_blank"}。

![系統管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員可以執行下列步驟。

1. 登入[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 選取&#x200B;**[!UICONTROL 使用者]**&#x200B;索引標籤。

1. 在左側導覽中選擇&#x200B;**[!UICONTROL 使用者群組]**。

1. 按一下右上角的&#x200B;**[!UICONTROL 新增使用者群組]**。

1. 輸入使用者群組的名稱，例如&#x200B;_B2B歷程使用者_，然後按一下&#x200B;**[!UICONTROL 儲存]**。

   ![Admin Console — 新增使用者群組](./assets/admin-console-new-user-group.png){width="600" zoomable="yes"}

## 將使用者新增至新群組 {#add-users}

如需使用者管理的相關資訊，請參閱Admin Console檔案中的&#x200B;[_Adobe Admin Console使用者_](https://helpx.adobe.com/tw/enterprise/using/users.html){target="_blank"}。

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或產品管理員可以執行下列步驟。 產品管理員只能新增其組織中已存在的使用者。

1. 移至[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 在&#x200B;_[!UICONTROL 快速連結]_&#x200B;下，按一下&#x200B;**[!UICONTROL 新增使用者]**。

1. 新增每個使用者：

   * 輸入使用者的電子郵件地址、名字和姓氏。

     ![Admin Console — 新增新群組的使用者設定檔](./assets/admin-console-user-group-add-users.png){width="600" zoomable="yes"}

   * 若為&#x200B;**[!UICONTROL 使用者群組]**，請按一下&#x200B;**+**。

   * 選取您先前建立的使用者群組。

   * 按一下&#x200B;**[!UICONTROL 套用]**。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 指派產品設定檔 {#assign-profile}

>[!IMPORTANT]
>
>設定使用者群組時，請一律將使用者新增至群組，然後再將產品設定檔指派至群組。 將產品設定檔指派給空白使用者群組及之後新增使用者時，無法正確傳播存取權。 為確保套用許可權，請先以成員填入使用者群組，然後指派產品設定檔。

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}產品管理員可以執行下列步驟。

1. 按一下您新增使用者的使用者群組。

1. 選取&#x200B;**[!UICONTROL 指派的產品設定檔]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL 指派設定檔]**。

1. 按一下&#x200B;**+**&#x200B;並新增下列產品的每個執行個體：

   * [!UICONTROL Adobe Journey Optimizer B2B edition — 使用者設定檔]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform Data Collection — 預設資料收集所有存取權]
   * [!UICONTROL Adobe Experience Platform — 預設的生產所有存取權]

   ![Admin Console — 使用者群組的產品設定檔](./assets/admin-console-product-profiles.png){width="600" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 編輯產品許可權的角色 {#edit-roles-for-product-permissions}

許可權是統一許可權，可讓您定義指派給產品設定檔的授權。 每個許可權都會分組在功能底下，例如歷程或購買群組，代表Journey Optimizer B2B edition中的功能。

Adobe Experience Platform的&#x200B;_許可權_&#x200B;區域是管理員可以定義使用者角色和存取原則，以管理產品應用程式內功能和物件的存取許可權。 在此應用程式中，您可以建立和管理角色，並為這些角色指派所需的資源許可權。 許可權也可讓您管理與特定角色相關聯的沙箱和使用者。

如需Experience Platform中角色許可權的詳細資訊，請參閱Experience Platform檔案中的[管理角色](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"}。

<!--

### B2B product permissions {#b2b-product-permissions}

The following permissions govern access to Journey Optimizer B2B Edition capabilities:

| Category | Description | Permissions |
| -------- | ----------- | ---------- |
| B2B Account Lists | Configure, manage, view, and publish permissions for B2B account lists. These permissions include actions such as add, remove, import, and delete accounts from account lists. | <li>Manage B2B Account Lists |
| B2B Admin Configurations | Configure, manage, and view permissions for B2B administrative configurations. These permissions include digital asset management connections, asset repositories, and events. | <li>Manage B2B Admin Configurations |
| B2B Assets | Configure, manage, and view permissions for B2B assets. These permissions include emails, SMS, landing pages, fragments, templates, and images. | <li>Manage B2B Assets <li>Manage B2B Templates <li>Manage B2B Fragments <li>Manage B2B Emails |
| B2B Buying Groups | Configure, manage, and view permissions for B2B buying groups. These permissions include solution interests, roles templates, and buying group status. | <li>Manage B2B Buying Groups <li>Manage B2B Solution Interests <li>Manage B2B Role Templates <li>Manage B2B Stages <li>View B2B Buying Groups |
| B2B Channel Configurations | Configure, manage, and view permissions for B2B channel configurations. These permissions include settings for communication limits, API credentials, and security settings. | <li>Manage B2B Channels Configurations |
| B2B Dashboards | Configure and view permissions for B2B dashboards. These permissions include account engagement, buying group stages, surging accounts, and contact coverage. | <li>View B2B Engagement Dashboard |
| B2B Journeys | Configure, manage, view, and publish permissions for B2B journeys. These permissions include account and person actions, event listeners, and split paths. | <li>Manage B2B Account Journeys |
| Journey Optimizer Rules | Access and configure frequency rules (communication limits). These permissions should be limited to product administrators. | <li>View Frequency Rules <li>Manage Frequency Rules |
-->

### B2B內建角色 {#b2b-built-in-roles}

當貴組織布建Journey Optimizer B2B edition產品時，Experience Platform會包含一組內建（預設）角色，您可將其用於管理對產品功能的存取：

| 角色 | 權限 |
| ---- | ----------- |
| B2B Journey Manager | <li>管理B2B歷程 <li>管理B2B購買群組 <li>管理B2B帳戶清單 <li>檢視B2B參與儀表板 <li>檢視B2B見解控制面板 |
| B2B頻道管理員 | <li>管理B2B Assets <li>管理B2B範本 <li>管理B2B片段 |
| B2B系統管理員 | <li>管理B2B通道設定 <li>管理B2B管理設定 |
| B2B銷售使用者 | <li>檢視B2B參與儀表板 <li>檢視B2B購買群組 <li>存取In-CRM Insights |

### 編輯角色許可權 {#edit-role-permissions}

對於內建或自訂角色，您可以隨時決定新增或刪除許可權。 如果您修改預設或自訂角色，則會影響指派給該角色的每個使用者。

在以下範例中，您想要為指派給B2B頻道管理員角色的使用者，新增與B2B歷程資源相關的許可權。 此變更可讓該角色的使用者同時管理帳戶歷程。

>[!NOTE]
>
>Admin Console系統管理員可以執行這些步驟。

若要變更角色&#x200B;:_的許可權(_T)

1. 移至[experience.adobe.com](https://experience.adobe.com/)。

1. 在&#x200B;_[!UICONTROL 快速存取]_&#x200B;面板中，選取&#x200B;**[!UICONTROL 許可權]**。

   >[!NOTE]
   >
   >如果您沒有看到&#x200B;_[!UICONTROL 許可權]_，您可能需要按一下「檢視全部&#x200B;**[!UICONTROL 」]**，然後從可用的應用程式中選取它。

   ![Experience Platform — 存取許可權](./assets/aep-permissions.png){width="700" zoomable="yes"}

1. 在左側導覽中選取&#x200B;**[!UICONTROL 角色]**。

1. 按一下&#x200B;**_B2B頻道管理員_**&#x200B;角色名稱。

1. 在詳細資訊頁面中，按一下右上方的&#x200B;**[!UICONTROL 編輯]**。

   ![Experience Platform — 編輯角色](../../user/admin/assets/aep-permissions-role-edit.png){width="700" zoomable="yes"}

   在角色編輯器中，_[!UICONTROL 資源]_&#x200B;功能表會顯示套用至Experience Cloud - Platform支援的應用程式產品的資源清單。

   您可以在搜尋工具中輸入&#x200B;_B2B_，以篩選B2B產品許可權的清單。

1. 按一下B2B歷程資源的&#x200B;_新增_&#x200B;圖示(**+**)。

   ![Experience Platform - B2B歷程資源已新增至頻道管理員角色](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL B2B歷程]_&#x200B;許可權卡中，選取&#x200B;**[!UICONTROL 管理B2B帳戶歷程]**。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

   <!-- ![Experience Platform - B2B Journeys permissions saved for Channel Manager role](../../user/admin/assets/aep-permissions-role-edit-b2b-journeys-done.png){width="700" zoomable="yes"} -->

1. 按一下&#x200B;**[!UICONTROL 關閉]**&#x200B;以返回詳細資料頁面。

### 將使用者新增至角色 {#add-users-to-a-role}

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或AEP產品管理員可以執行下列步驟。

1. 開啟角色詳細資料，並選取&#x200B;**[!UICONTROL 使用者]**&#x200B;索引標籤。

   此標籤會顯示指派給角色的所有使用者清單。

1. 按一下&#x200B;**[!UICONTROL 新增使用者]**。

   ![Experience Platform — 將使用者新增至角色](../../user/admin/assets/aep-permissions-role-add-users.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 新增使用者]_&#x200B;對話方塊中，找出並選取您要新增至角色的使用者。

   * 您可以使用搜尋工具來篩選使用者清單。

   * 選取每個使用者的核取方塊。

   ![Experience Platform — 新增使用者對話方塊](../../user/admin/assets/aep-permissions-role-add-users-dialog.png){width="600" zoomable="yes"}

1. 當您選取要新增的所有使用者時，請按一下&#x200B;**[!UICONTROL 儲存]**。

### 將使用者群組新增至角色 {#add-user-groups-to-a-role}

如需使用者管理的相關資訊，請參閱Admin Console檔案中的&#x200B;[_Adobe Admin Console使用者_](https://helpx.adobe.com/tw/enterprise/using/users.html){target="_blank"}。

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或AEP產品管理員可以執行下列步驟。

1. 開啟角色詳細資料，並選取&#x200B;**[!UICONTROL 使用者群組]**&#x200B;索引標籤。

   此標籤會顯示指派給角色的所有使用者群組清單。

1. 按一下&#x200B;**[!UICONTROL 新增群組]**。

   ![Experience Platform — 將群組新增至角色](../../user/admin/assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 新增群組]_&#x200B;對話方塊中，找出並選取您要新增至角色的群組。

   * 您可以使用搜尋工具來篩選使用者群組清單。

   * 選取每個使用者群組的核取方塊。

   ![Experience Platform — 新增群組對話方塊](../../user/admin/assets/aep-permissions-role-add-groups-dialog.png){width="600" zoomable="yes"}

1. 當您選取要新增的所有群組時，請按一下&#x200B;**[!UICONTROL 儲存]**。

## 建立自訂角色 {#create-a-custom-role}

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或AEP產品管理員可以執行下列步驟。

1. 在左側導覽中選取&#x200B;**[!UICONTROL 角色]**，然後選取&#x200B;**[!UICONTROL 建立角色]**。

1. 在&#x200B;_[!UICONTROL 建立新角色]_&#x200B;對話方塊中，輸入角色的名稱，例如&#x200B;_B2B行銷人員_，以及說明（選擇性）。

1. 按一下「**[!UICONTROL 確認]**」。

1. 選取您的沙箱。

   ![Experience Platform — 為新的角色新增沙箱](../../user/admin/assets/aep-permissions-role-sandboxes.png){width="700" zoomable="yes"}

1. 新增B2B產品許可權：

   <!-- To determine which product capabilities that you want for the role, refer to the list of [B2B product permissions](#b2b-product-permissions). -->

   在左側的&#x200B;_[!UICONTROL 資源]_&#x200B;清單中，找到B2B專案，然後按一下&#x200B;_新增_ (**+**)圖示以新增您想要為角色啟用的每個屬性。

   您可以在搜尋工具中輸入&#x200B;_B2B_，以篩選B2B產品許可權的清單。

   ![Experience Platform - B2B許可權](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. 按一下右上角的&#x200B;**[!UICONTROL 儲存]**。

1. 前往角色詳細資料，並選取&#x200B;**[!UICONTROL 使用者群組]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 新增群組]**。

   ![Experience Platform — 選取自訂角色的使用者群組](../../user/admin/assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. 選取您先前在Admin Console中建立的使用者群組旁的核取方塊。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

您的自訂角色已設定，且指派群組中的使用者現在可以存取您選取的Journey Optimizer B2B edition功能。
