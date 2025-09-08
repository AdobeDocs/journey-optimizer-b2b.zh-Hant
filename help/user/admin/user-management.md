---
title: User Management
description: 使用Experience Cloud Admin Console管理使用者存取 — 建立Journey Optimizer B2B edition的使用者群組、指派產品設定檔及設定角色型許可權。
feature: Setup, Permissions
roles: Admin
exl-id: ddbdc6a5-49bc-46cd-8d9b-1d37223dffe2
source-git-commit: 9ed2d2a36dbdaf39c107a18632d951003c86197b
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 1%

---

# 使用者管理

布建完成並繫結沙箱後，請完成下列步驟，為團隊和使用者提供Adobe Journey Optimizer B2B edition存取權。

1. [在Admin Console中建立Marketo Engage產品設定檔](#marketo-engage-profile) (僅限新的Marketo Engage執行個體)。
1. 在Admin Console中[建立使用者群組](#create-user-group)。
<!-- 1. [Edit built-in roles](#edit-roles) or [create a custom role](#create-a-custom-role) with Journey Optimizer B2B Edition permissions. -->
1. [新增使用者](#add-users)或[群組](#add-user-groups-to-a-role)至角色。

作為管理員，您可以在Adobe Admin Console中完成這些工作，這是管理您的Adobe產品授權和使用者的中心位置。 在Admin Console中，您可以在單一位置而非在各種個別解決方案中建立和管理使用者。 請參閱[Admin Console概觀](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)頁面，進一步瞭解其功能和特性。

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

1. 從&#x200B;**[!UICONTROL 使用者]**&#x200B;卡中選擇&#x200B;_[!UICONTROL 管理員]_&#x200B;以驗證您是系統管理員。

   ![Admin Console概觀 — 按一下[管理員]](./assets/admin-console-overview-administrators.png){width="700" zoomable="yes"}

1. 透過輸入您的Adobe ID電子郵件、使用者名稱、名字或姓氏進行搜尋。

   * 如果您的存取權設定正確，搜尋會傳回您的記錄。

   * 如果&#x200B;**[!UICONTROL 管理員角色]**&#x200B;欄中的值顯示`System`，您就知道您（或顯示的使用者）是系統管理員。

## 建立Marketo Engage產品設定檔 {#marketo-engage-profile}

在授與使用者Adobe解決方案的存取權時，您不一定要授與他們完整的存取權。 產品設定檔使每個解決方案都可以擁有自己的一組使用者許可權。 使用Admin Console指派產品設定檔。

如需有關使用產品設定檔取得使用者許可權的詳細資訊，請參閱Admin Console檔案中的[管理企業使用者的產品設定檔](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html){target="_blank"}。

>[!BEGINSHADEBOX]

新增使用者至Marketo Engage產品設定檔時，他們隨後會新增至Marketo Engage訂閱預設工作區中的&#x200B;_標準使用者_&#x200B;角色。 此角色會授予他們該工作區中Marketo Engage的所有&#x200B;_標準使用者_&#x200B;許可權。 目前，所有Journey Optimizer B2B edition使用者都必須是Marketo Engage使用者。 Marketo Engage管理員可以更新&#x200B;_標準使用者_&#x200B;角色的許可權，或將使用者移至其他具有更嚴格許可權的Marketo Engage使用者角色，以限制存取權。

如需有關在Marketo Engage中管理這些許可權的詳細資訊，請參閱Marketo Engage檔案中的[管理使用者角色和許可權](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/users-and-roles/managing-user-roles-and-permissions){target="_blank"}。

>[!ENDSHADEBOX]

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或Marketo Engage產品管理員可以執行下列步驟。

1. 登入[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 選取「**[!UICONTROL 產品]**」標籤。

1. 開啟您想要新增設定檔的Marketo Engage執行個體，然後按一下&#x200B;**[!UICONTROL 新增設定檔]**。

   ![Admin Console - Marketo Engage執行個體 — 新設定檔](./assets/admin-console-marketo-engage-instance-new-profile.png){width="700" zoomable="yes"}

1. 輸入產品設定檔名稱，例如&#x200B;_標準使用者_。

1. 按一下[下一步]****，然後按一下[儲存]****。

## 建立使用者群組 {#create-user-group}

使用者群組是使用者被授予一組共用許可權的集合。 您可以在使用者群組中新增或移除使用者。 當群組內的使用者變更時，群組許可權會維持不變。

如需有關如何使用使用者群組來管理許可權的詳細資訊，請參閱Admin Console檔案中的[管理使用者群組](https://helpx.adobe.com/tw/enterprise/using/user-groups.html){target="_blank"}。

![系統管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員可以執行下列步驟。

1. 登入[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 選取&#x200B;**[!UICONTROL 使用者]**&#x200B;索引標籤。

1. 在左側導覽中選擇&#x200B;**[!UICONTROL 使用者群組]**。

1. 按一下右上角的&#x200B;**[!UICONTROL 新增使用者群組]**。

1. 輸入使用者群組的名稱，例如&#x200B;_標準使用者_，然後按一下&#x200B;**[!UICONTROL 儲存]**。

1. 按一下您剛建立的使用者群組。

1. 選取&#x200B;**[!UICONTROL 指派的產品設定檔]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL 指派設定檔]**。

1. 按一下&#x200B;**+**&#x200B;並新增下列產品的每個執行個體：

   * [!UICONTROL Marketo Engage]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform資料彙集]
   * [!UICONTROL 資料收集所有存取權]

   ![Admin Console — 使用者群組 — 新增產品](./assets/admin-console-user-group-add-products.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 新增使用者至群組

如需使用者管理的相關資訊，請參閱Admin Console檔案中的[Admin Console使用者](https://helpx.adobe.com/tw/enterprise/using/user-groups.html)。

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或產品管理員可以執行下列步驟。 產品管理員只能新增其組織中已存在的使用者。

1. 移至[https://adminconsole.adobe.com](https://adminconsole.adobe.com)。

1. 在&#x200B;_[!UICONTROL 快速連結]_&#x200B;下，按一下&#x200B;**[!UICONTROL 新增使用者]**。

1. 新增每個使用者：

   * 輸入使用者的電子郵件地址、名字和姓氏。

     ![Experience Platform — 新增新角色的設定檔](./assets/admin-console-add-users.png){width="600" zoomable="yes"}

   * 若為&#x200B;**[!UICONTROL 使用者群組]**，請按一下&#x200B;**+**。

   * 選取您先前建立的使用者群組。

   * 按一下&#x200B;**[!UICONTROL 套用]**。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

<!-- ## Edit roles for product permissions {#edit-roles}

Permissions are unitary rights that allow you to define the authorizations assigned to a product profile. Each permission is gathered under a capability, such as journeys or buying groups, which represents the different functionalities or objects in Journey Optimizer B2B Edition.

The _Permissions_ area of Adobe Experience Platform is where administrators can define user roles and access policies to manage access permissions for features and objects within a product application. In this app, you can create and manage roles, as well as assign the desired resource permissions for these roles. Permissions also allow you to manage the sandboxes and users associated with a specific role.

For more information about role permissions in Experience Platform, see [Manage permissions for a role](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"} in the Experience Platform documentation.

### B2B product permissions

The following permissions govern access to Journey Optimizer B2B Edition capabilities:

| Category | Description | Permissions |
| -------- | ----------- | ---------- |
| B2B Account Lists | Configure, manage, view, and publish permissions for B2B account lists. These permissions include actions such as add, remove, import, and delete accounts from account lists. | <li>Manage B2B Account Lists |
| B2B Admin Configurations | Configure, manage, and view permissions for B2B administrative configurations. These permissions include digital asset management connections, asset repositories, and events. | <li>Manage B2B Admin Configurations |
| B2B Assets | Configure, manage, and view permissions for B2B assets. These permissions include emails, SMS, landing pages, fragments, templates, and images. | <li>Manage B2B Assets <li>Manage B2B Templates <li>Manage B2B Fragments|
| B2B Buying Groups | Configure, manage, and view permissions for B2B buying groups. These permissions include solution interests, roles templates, and buying group status. | <li>Manage B2B Buying Groups |
| B2B Channel Configurations | Configure, manage, and view permissions for B2B channel configurations. These permissions include settings for communication limits, API credentials, and security settings. | <li>Manage B2B Channels Configurations |
| B2B Dashboards |Configure and view permissions for B2B dashboards. These permissions include account engagement, buying group stages, surging accounts, and contact coverage. | <li>Manage B2B Dashboards |
| B2B Journeys | Configure manage, view, and publish permissions for B2B journeys. These permissions include account and person actions, event listeners, and split paths | <li>Manage B2B Journeys |

### B2B built-in roles

When your organization has the Journey Optimizer B2B Edition product provisioned, Experience Platform includes a set of built-in (default) roles that you can use to manage access to the product capabilities:

| Role | Permissions |
| ---- | ----------- |
| B2B Journey Manager | <li>Manage B2B Journeys <li>Manage B2B Buying Groups <li>Manage B2B Account Lists <li>View B2B Engagement Dashboard <li>View B2B Insights Dashboard |
| B2B Channel Manager | <li>Manage B2B Assets <li>Manage B2B Templates <li>Manage B2B Fragments |
| B2B System Administrator | <li>Manage B2B Channels Configurations <li>Manage B2B Admin Configurations |
| B2B Sales User | <li>View B2B Engagement Dashboard |

### Edit role permissions

For built-in or custom roles, you can decide at any time to add or delete permissions. If you modify a default or custom role, it impacts every user assigned to the role.

In the following example, you want to add permissions related to the B2B Journeys resource for users assigned to the B2B Channel Manager role. This change enables users for that role to manage account journeys also.

>[!NOTE]
>
>An Admin Console system administrator can perform these steps.

_To change the permissions for a role:_

1. Go to [experience.adobe.com](https://experience.adobe.com/).

1. In the _[!UICONTROL Quick access]_ panel, select **[!UICONTROL Permissions]**.

   >[!NOTE]
   >
   >If you don't see _[!UICONTROL Permissions]_, you may need to click **[!UICONTROL View all]** and select it from the available applications.

   ![Experience Platform - access Permissions](./assets/aep-permissions.png){width="700" zoomable="yes"}

1. Select **[!UICONTROL Roles]** in the left navigation.

1. Click the **_B2B Channel Manager_** role name.

1. In the details page, click **[!UICONTROL Edit]** at the top right.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-edit.png){width="700" zoomable="yes"}

   In the role editor, the _[!UICONTROL Resources]_ menu displays the list of resources that apply to the Experience Cloud - Platform powered applications products.

   You can enter _B2B_ in the search tool to filter the list for the B2B product permissions. 
   
1. Click the _Add_ icon (**+**) for the B2B Journeys resource.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-edit-b2b-journeys-add.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL B2B Journeys]_ permissions card, select **[!UICONTROL Manage B2B Account Journeys]**.

1. Click **[!UICONTROL Save]**.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-edit-b2b-journeys-done.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Close]** to return to the details page.

### Add users to a role

![Administrator role requirements](../../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or AEP product administrator can perform the following steps. 

1. Open the role details and select the **[!UICONTROL Users]** tab.

   This tab displays a list of all users assigned to the role.

1. Click **[!UICONTROL Add users]**.

   ![Experience Platform - add users to the role](./assets/aep-permissions-role-add-users.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL Add users]_ dialog, locate and select the users that you want to add to the role.

   * You can use the Search tool to filter the list of users. 

   * Select the checkbox for each user.

   ![Experience Platform - Add users dialog](./assets/aep-permissions-role-add-users-dialog.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Save]** when you have selected all the users that you want to add.

### Add user groups to a role

For information about user management, see [Admin Console users](https://helpx.adobe.com/enterprise/using/user-groups.html) in the Admin Console documentation.

![Administrator role requirements](../../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or AEP product administrator can perform the following steps. 

1. Open the role details and select the **[!UICONTROL User groups]** tab.

   This tab displays a list of all user groups assigned to the role. 

1. Click **[!UICONTROL Add Groups]**.

   ![Experience Platform - add users to the role](./assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL Add groups]_ dialog, locate and select the groups that you want to add to the role.

   * You can use the Search tool to filter the list of user groups. 

   * Select the checkbox for each user group.

   ![Experience Platform - Add groups dialog](./assets/aep-permissions-role-add-groups-dialog.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Save]** when you have selected all the users that you want to add. -->

## 建立自訂角色

![管理員角色需求](../../assets/do-not-localize/icon-admin-user.svg){width="30"}系統管理員或AEP產品管理員可以執行下列步驟。

1. 在左側導覽中選取&#x200B;**[!UICONTROL 角色]**，然後選取&#x200B;**[!UICONTROL 建立角色]**。

1. 在&#x200B;_[!UICONTROL 建立新角色]_&#x200B;對話方塊中，輸入角色的名稱，例如&#x200B;_B2B行銷人員_，以及說明（選擇性）。

1. 按一下「**[!UICONTROL 確認]**」。

1. 選取您的沙箱。

   ![Experience Platform — 為新的角色新增沙箱](./assets/aep-permissions-role-sandboxes.png){width="700" zoomable="yes"}

1. 新增設定檔許可權：

   * 在左側的&#x200B;_[!UICONTROL 資源]_&#x200B;清單中，找到&#x200B;**[!UICONTROL 設定檔管理]**&#x200B;專案，然後按一下&#x200B;_新增_ (**+**)圖示以新增屬性。

   * 針對屬性，新增下列許可權：
      * [!UICONTROL 檢視區段]
      * [!UICONTROL 管理區段]
      * [!UICONTROL 檢視設定檔]
      * [!UICONTROL 管理設定檔]
      * [!UICONTROL 檢視B2B設定檔]
      * [!UICONTROL 管理B2B設定檔]

   ![Experience Platform — 新增新角色的設定檔](./assets/aep-permissions-role-profiles.png){width="700" zoomable="yes"}

1. 新增B2B產品許可權：

   請參閱[B2B產品許可權](#b2b-product-permissions)清單，以決定您想要用於此角色的產品功能。

   在左側的&#x200B;_[!UICONTROL 資源]_&#x200B;清單中，找到&#x200B;**[!UICONTROL B2B]**&#x200B;專案，然後按一下&#x200B;_新增_ (**+**)圖示以新增您想要為角色啟用的每個屬性。

   您可以在搜尋工具中輸入&#x200B;_B2B_，以篩選B2B產品許可權的清單。

1. 按一下右上角的&#x200B;**[!UICONTROL 儲存]**。

1. 前往角色詳細資料，並選取&#x200B;**[!UICONTROL 使用者群組]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 新增群組]**。

   ![Experience Platform — 新增新角色的設定檔](./assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. 選取您先前在Admin Console中建立的使用者群組旁的核取方塊。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。
