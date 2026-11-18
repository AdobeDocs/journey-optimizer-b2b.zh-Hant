---
title: 人員清單
description: 瞭解人員清單，以及如何在Journey Optimizer B2B Edition中瀏覽、檢視、編輯、刪除及使用人員清單。
feature: Audiences
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
source-git-commit: d713d57bddf2ac6f8cf7e7a7d163281f607d729c
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 1%
---

# 人員清單

在[!DNL Journey Optimizer B2B Edition]中，人員清單是人員設定檔的已命名集合，您可以在歷程中重複使用。 與其在每個歷程中重新建立相同的篩選器集，不如定義一次人員群組，然後視需要隨時參考。 例如，使用人員清單將內部員工或現有客戶從培養歷程中排除，或追蹤在一個歷程中完成步驟的人員，以便另一個歷程可以對其採取行動。

有兩種型別的人員清單：

* **[!UICONTROL 靜態]** — 只有當您明確新增或移除人員時，成員資格才會變更。 您可以套用篩選器集來根據目前人員資料填入清單，或是透過帳戶或人員歷程新增和移除人員，藉此新增人員。 檢視[靜態人員清單](./people-lists-static.md)。
* **[!UICONTROL 動態]** — 您定義一組規則（篩選器）以自動組織清單。 當使用者符合或不符合規則定義的資格時，清單會以動態方式重新整理。 檢視[動態人員清單](./people-lists-dynamic.md)。

您可以[在帳戶歷程與個人歷程中使用人員清單](./people-lists-journeys.md)，根據清單成員資格來分割路徑，以及在靜態清單中新增或移除人員。

>[!NOTE]
>
>人員清單包含已同步且可在[!DNL Journey Optimizer B2B Edition]中使用的人員設定檔。 評估清單時，不會直接從[!DNL Adobe Experience Platform]對象讀取設定檔。

## 存取及瀏覽人員清單 {#access-browse}

從左側導覽存取人員清單，以檢視、建立和管理清單成員資格。

>[!AVAILABILITY]
>
>下列產品許可權可控制對人員清單的存取：
>
>* [!UICONTROL 管理B2B人員清單] — 檢視、建立、編輯和刪除人員清單。
>* [!UICONTROL 檢視B2B人員清單] — 檢視人員清單及其成員（唯讀）。
>
>如需指派許可權的資訊，請參閱[使用者存取與許可權](../admin/user-management.md#b2b-product-permissions)。

* 在左側導覽列中，展開&#x200B;**[!UICONTROL 帳戶]**&#x200B;並選取&#x200B;**[!UICONTROL 人員清單]**。

* Select **[!UICONTROL 動態清單]**&#x200B;或&#x200B;**[!UICONTROL 靜態清單]**，以在這兩種清單型別之間切換。

* 在清單頂端的&#x200B;_搜尋_&#x200B;欄位中輸入文字，依名稱篩選顯示的清單。

  ![存取人員清單以管理您的人員層級對象](./assets/people-lists-browse-search.png){width="800" zoomable="yes"}

* 按一下右上角的&#x200B;_欄設定_ （![欄設定圖示](../assets/do-not-localize/icon-column-settings-new.svg) ）圖示，以選取或清除顯示的欄。

* 若要變更欄寬，請拖曳欄標題之間的分隔線。

每個索引標籤都包含&#x200B;**[!UICONTROL 名稱]**、**[!UICONTROL 上次更新時間]**、**[!UICONTROL 更新者]**、**[!UICONTROL 建立於]**，以及&#x200B;**[!UICONTROL 建立者]**&#x200B;欄。 按一下人員清單名稱以檢視其詳細資訊。

您也可以從此頁面執行下列作業：

* 建立新的動態和靜態清單。
* 開啟清單並[檢閱目前的成員](#view-list-members)。
* 按一下清單的&#x200B;_更多動作_ ( **...** )圖示，然後選擇[編輯](#edit-list-properties)或[刪除](#delete-people-list)。

## 建立人員清單 {#create-people-list}

1. 按一下&#x200B;_[!UICONTROL 人員清單]_&#x200B;頁面右上角的&#x200B;**[!UICONTROL 建立清單]**。

   ![建立人員清單對話方塊](./assets/people-list-create-dialog.png){width="450"}

1. 輸入清單的&#x200B;**[!UICONTROL Name]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。

   此名稱最多可包含180個字元，且在相同型別的清單中必須是唯一的。 說明最多可包含2,000個字元。

1. 選擇清單&#x200B;**[!UICONTROL 型別]**：

   * [**[!UICONTROL 靜態]**](./people-lists-static.md) — 資格篩選條件會在您將其套用至清單時決定成員資格。 只有在您手動新增人員或歷程新增或移除人員時，成員資格才會更新。
   * [**[!UICONTROL 動態]**](./people-lists-dynamic.md) — 資格篩選器會動態決定成員資格。 成員資格會自動重新整理。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   新人員清單會在其詳細資訊頁面上開啟，而篩選編輯器會開啟，以便您為清單定義人員。 若要將人員新增至靜態清單，請套用一或多個篩選器。 針對動態清單，定義清單成員資格的規則。

## 檢視清單成員 {#view-list-members}

在人員清單的詳細資訊頁面上，**[!UICONTROL 成員]**&#x200B;清單會顯示清單中的人員。 清單中的總人數會顯示在表格頂端。

「成員」表格包含下列資料欄：

* **[!UICONTROL 名稱]**
* **[!UICONTROL 電子郵件地址]**
* **[!UICONTROL 職稱]**
* **[!UICONTROL 公司]**
* **[!UICONTROL 已取消訂閱]**
* **[!UICONTROL 建立於]**
* **[!UICONTROL 上次修改時間]**

依預設，系統會依&#x200B;**[!UICONTROL 上次修改時間]**&#x200B;排序成員，先顯示最近修改的人員。 您也可以依&#x200B;**[!UICONTROL 名稱]**、**[!UICONTROL 電子郵件地址]**&#x200B;或&#x200B;**[!UICONTROL 建立日期]**&#x200B;進行排序。

* 若要尋找特定成員，請使用&#x200B;_搜尋_&#x200B;欄位。 您可以依名字、電子郵件地址或公司進行搜尋。
* 若要選擇要顯示的欄，請按一下&#x200B;_欄設定_&#x200B;圖示，然後選取或清除核取方塊。 _[!UICONTROL Name]_&#x200B;資料行一律顯示。
* 若要檢視最新的成員資格，請使用&#x200B;_[!UICONTROL 更多]_&#x200B;功能表選擇&#x200B;**[!UICONTROL 重新整理成員]**。
* 若要檢視個人的詳細資訊，請按一下該人的名稱以開啟[個人詳細資料](../accounts/person-details.md)頁面，您可以在此檢視其摘要和最近的活動。

## 編輯人員清單屬性 {#edit-list-properties}

您可以變更靜態或動態人員清單的名稱和說明。

1. 使用下列其中一種方法開啟&#x200B;_[!UICONTROL 編輯清單]_&#x200B;對話方塊：

   * 在&#x200B;_[!UICONTROL 人員清單]_&#x200B;頁面上，按一下清單的&#x200B;_更多動作_ ( **...** )圖示，然後選擇&#x200B;**[!UICONTROL 編輯]**。
   * 在清單的詳細資訊頁面上，按一下&#x200B;**[!UICONTROL 編輯清單屬性]**。

1. 更新&#x200B;**[!UICONTROL 名稱]**&#x200B;或&#x200B;**[!UICONTROL 描述]**。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 刪除人員清單 {#delete-people-list}

>[!IMPORTANT]
>
>刪除人員清單是永久性的，且無法復原。 您無法刪除作用中歷程正在使用的人員清單。

1. 使用下列其中一種方法刪除清單：

   * 在&#x200B;_[!UICONTROL 人員清單]_&#x200B;頁面上，按一下清單名稱旁的&#x200B;_更多動作_ ( **...** )圖示，然後選擇&#x200B;**[!UICONTROL 刪除]**。
   * 在清單的詳細資訊頁面上，按一下&#x200B;**[!UICONTROL 刪除清單]**。

1. 在確認對話框中，按一下「**[!UICONTROL 刪除]**」。
