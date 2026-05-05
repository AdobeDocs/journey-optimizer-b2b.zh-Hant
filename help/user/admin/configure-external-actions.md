---
title: 外部動作設定
description: 瞭解開發人員、管理員和行銷人員如何共同實施、設定和使用外部動作，將Journey Optimizer B2B edition與帳戶歷程中的外部服務連結。
feature: Setup, Integrations
role: Admin, Developer
exl-id: 226fbf23-7df2-4fd7-b5a4-2057a417a261
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
autotag-review: '2026-04-29T23:21:59.633Z'
source-git-commit: 0216cf3b1cbc1124b50ad99e649778aef71f5aca
workflow-type: tm+mt
source-wordcount: 907
ht-degree: 1%

---

# 外部動作設定

外部動作可讓Journey Optimizer B2B edition中的帳戶歷程直接從歷程畫布連線外部系統。 當帳戶對象到達外部動作節點時，系統會非同步呼叫已設定的外部服務，傳遞帳戶、人員或兩者的對象屬性資料。 外部服務使用回呼處理資料及回應，傳回可用於引導歷程執行的對象資料及中繼資料。

此功能支援兩種歷程節點型別：

* **外部動作** — 呼叫外部服務並沿著單一傳出路徑繼續。 適合&#x200B;_引發並忘記_&#x200B;整合，例如更新CRM記錄或觸發下游通知。
* **外部分割路徑** — 呼叫外部服務並評估回應，以沿著數個已定義的路徑之一路由帳戶。

>[!NOTE]
>
>僅帳戶歷程支援外部動作服務。 這些節點型別不適用於個人歷程。

## 實施概述

設定外部動作需要依序在三個角色之間進行協調：

| | 角色 | 任務 |
| ---- | ---- | ---- |
| 1 | Developer | [實作並發佈外部服務](#implement-service) |
| 2 | 管理員 | [在Journey Optimizer B2B edition中設定動作](#configure-action) |
| 3 | 行銷人員 | [將外部節點新增至帳戶歷程](#add-journey-node) |

## 實作外部服務 {#implement-service}

開發人員必須建立並發佈符合[Adobe Journey Optimizer B2B edition外部動作服務提供者介面](https://developer.adobe.com/journey-optimizer-b2b-apis/)的公開顯示網頁服務。

>[!NOTE]
>
>回呼函式需要持有人權杖。 請在Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)中為您的IMS組織設定[OAuth伺服器對伺服器認證，以擷取此專案。

服務上線後，將OpenAPI規格的URL和驗證認證提供給負責設定動作的產品管理員。

## 設定動作 {#configure-action}

必須先設定並啟動動作，行銷人員才能在歷程中使用。 動作以&#x200B;_草稿_&#x200B;狀態建立，且您的變更會自動儲存。 在您啟動它之前，它一直保持為草稿。

>[!PREREQUISITES]
>
>在新增設定之前，請先向開發人員取得OpenAPI規格的URL和驗證認證。
>
>若要定義及啟用外部動作，您必須擁有&#x200B;_[!UICONTROL 管理B2B管理組態]_ [產品許可權](./user-management.md#b2b-product-permissions)。

1. 移至&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 組態]**。

1. 按一下中繼面板上的&#x200B;**[!UICONTROL 外部動作]**。

   ![存取外部動作設定空間](./assets/configuration-external-actions-list.png){width="800" zoomable="yes"}

1. 按一下右上角的&#x200B;**[!UICONTROL 建立動作]**。

1. 輸入外部服務的OpenAPI規格URL，然後按一下&#x200B;**[!UICONTROL 建立]**。

   ![輸入服務URL](./assets/configuration-external-actions-create-url.png){width="500"}

   >[!NOTE]
   >
   >您的外部服務必須為即時狀態且可連線，此步驟才能成功。

1. 當URL成功解析時，請檢閱&#x200B;**[!UICONTROL 服務詳細資料]**。

   建立動作時，會直接從OpenAPI規格讀取服務詳細資料。 建立後，您無法在設定中變更這些屬性。

   | 屬性 | 說明 | OpenAPI規格屬性 |
   | -------- | ----------- | --------------------- |
   | [!UICONTROL 名稱] | 動作的名稱 | `info.title` |
   | [!UICONTROL 說明] | 動作的說明 | `info.description` |
   | [!UICONTROL URL] | 定義外部服務的OpenAPI規格的URL | `servers.url` |

1. 輸入外部服務(`components.securitySchemes`)的&#x200B;**[!UICONTROL 驗證]**&#x200B;認證。

   >[!NOTE]
   >
   >顯示的認證欄位取決於外部服務中定義的驗證機制。 支援的型別為API金鑰、OAuth2和HTTP基本驗證。

   ![新增驗證認證](./assets/configuration-external-actions-auth-credentials.png){width="600" zoomable="yes"}

   當設定的動作處於&#x200B;_草稿_&#x200B;或&#x200B;_作用中_&#x200B;狀態時，您可以視需要變更認證。

1. 按一下&#x200B;**[!UICONTROL 下一步]**。

1. 設定&#x200B;**[!UICONTROL 組態]**&#x200B;屬性以定義動作與外部服務交換資料的方式。

   >[!NOTE]
   >
   >標示為&#x200B;_靜態_&#x200B;的屬性在設定時不可更新，而且是以服務定義為基礎。

   * **[!UICONTROL 動作型別]** （_靜態_） — 支援的歷程節點型別：

      * [!UICONTROL 外部動作] (`enableSplitPath` = false)
      * [!UICONTROL 外部動作分割路徑] (`enableSplitPath` = true)

     建立動作設定後，您無法變更動作型別。

   * **[!UICONTROL 存取子]** （_靜態_） — （僅限外部動作分割路徑）外部服務傳回的變數可用作外部分割路徑節點中的路徑條件。 (`invocationPayloadDef.accessorsMetadata`)

   * **[!UICONTROL 歷程內容]** （_靜態_） — 要求中傳送的對象資料範圍(`supportedEntityType`)：

      * [!UICONTROL 帳戶] — 僅傳送帳戶

      * [!UICONTROL 人員] — 僅傳送人員

      * [!UICONTROL 帳戶中的人員] — 傳送帳戶和與帳戶相關的人員

   * **[!UICONTROL 傳出欄位]** — 將表格中的每個欄位對應到[XDM欄位](../admin/xdm-field-management.md)。 這些欄位會在要求內文中傳送給外部服務。 服務定義屬性： `invocationPayloadDef.accountFields`， `invocationPayloadDef.fields`。

   ![對應外部動作傳出欄位](./assets/configuration-external-actions-fields.png){width="600" zoomable="yes"}

   * **[!UICONTROL 傳入欄位]** — 將資料表中的每個欄位對應到[可更新的XDM欄位](../admin/xdm-field-management.md#updatable-fields)。 這些欄位會從外部服務回應填入。 服務定義屬性： `callbackPayloadDef.accountFields`， `callbackPayloadDef.fields`。 建立後可更新。

   * **[!UICONTROL 標頭引數]** — 輸入每個資料列的值，以作為要求中的HTTP標頭傳遞。 服務定義屬性： `invocationPayloadDef.headers`。

   * **[!UICONTROL 逾時]** — 輸入在要求被視為失敗之前，等待外部服務呼叫回呼的分鐘數。 服務定義屬性： `timeout`。

   * **[!UICONTROL 全域屬性]** — 輸入每個資料列的值，以做為要求內文中的靜態欄位。 服務定義屬性： `invocationPayloadDef.globalAttributes`。

   ![外部動作標頭引數、逾時和全域屬性](./assets/configuration-external-actions-header-timeout-global.png){width="600" zoomable="yes"}

1. 按一下&#x200B;_上一箭號_&#x200B;以返回清單並將動作保持在&#x200B;_草稿_&#x200B;狀態。

   或者，按一下[啟動]****&#x200B;將動作組態變更為[啟動]__&#x200B;狀態。 設定的外部動作必須處於作用中狀態，才能用於帳戶歷程。

## 將外部節點新增至歷程 {#add-journey-node}

動作啟動後，行銷人員可以將&#x200B;_[!UICONTROL 外部動作]_&#x200B;或&#x200B;_[!UICONTROL 外部分割路徑]_&#x200B;節點新增至任何帳戶歷程。 如需如何在帳戶歷程畫布中新增及使用這些節點的詳細資訊，請參閱[外部節點](../journeys/external-nodes.md)。
