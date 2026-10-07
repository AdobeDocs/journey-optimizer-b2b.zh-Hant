---
title: 匯出帳戶
description: 將已篩選帳戶清單匯出為 CSV，以用於 Journey Optimizer B2B Edition 中使用購買群組和參與度分數篩選器的第三方平台。
feature: Audiences
role: User
exl-id: 3ec8e8fd-1bc2-4efa-840f-f06520099060
autotag-review: 2026-03-30T19:51:33.392Z
TQID: 'https://experienceleague.adobe.com/fvkVLjO9oIF7hOuoqdSS-jU4wAvsrPnKp1fIabH-Ewk'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: e935834c-48b7-43d8-b754-a815196a1b05
    internal-label: Account lists
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 21fbce544faf291ad01a3301a9981add95442097
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 100%
---
# 匯出帳戶

使用&#x200B;_匯出帳戶_&#x200B;功能，根據您定義的篩選器匯出所有帳戶或一組帳戶。 匯出流程會產生一個 CSV 檔案，並在通知中傳送所儲存檔案的 URL。 在需要時，您可以使用此功能將帳戶移動至第三方平台。

1. 在 Journey Optimizer B2B Edition，前往左側導覽中的「**[!UICONTROL 帳戶]** > **[!UICONTROL 購買群組]**」。

1. 選取「**[!UICONTROL 瀏覽]**」索引標籤。

1. 按一下右上角的「**[!UICONTROL 匯出帳戶]**」。

   ![編輯帳戶詳細資訊](./assets/export-accounts.png){width="800" zoomable="yes"}

1. 在對話框中，定義要匯出的帳戶客群參數。

   ![指定帳戶客群篩選條件](./assets/export-accounts-dialog.png){width="400"}

   在「**[!UICONTROL 參與度分數]**」中，`Between` 運算子是包含性的，百分比範圍亦同。 例如，5.1 和 5 均是在 5 和 6 _之間_。

   空白篩選參數被視為 `Is Any`。

1. 按一下「**[!UICONTROL 匯出帳戶]**」，使用特定篩選器來產生 CSV 檔案。

1. 當您收到匯出完成的通知時，按一下通知連結即可存取該 CSV 檔案。

   ![按一下通知以下載所匯出的帳戶清單 CSV 檔案](./assets/export-accounts-notification.png){width="425"}

   >[!NOTE]
   >
   >如果您已在 Adobe 使用者帳戶偏好設定中設定了電子郵件訂閱通知，便可能會收到電子郵件通知。

   應用程式頁面將重新導向至「_購買群組_」瀏覽索引標籤，且系統會顯示儲存檔案對話框來提示您將檔案儲存至系統。 如需共用資料，可以使用團隊的檔案分享系統。
