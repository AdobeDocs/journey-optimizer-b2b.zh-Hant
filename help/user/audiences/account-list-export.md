---
title: 匯出帳戶清單
description: 瞭解如何根據購買群組篩選器匯出帳戶清單。
source-git-commit: c51ee8c8b58e8154c81f6a2ffada3f58a08eb6b4
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 匯出帳戶清單

使用&#x200B;_匯出帳戶清單_&#x200B;功能，根據您定義的篩選條件匯出所有帳戶或一組帳戶。 匯出程式會產生CSV檔案，並在脈衝通知中傳送已儲存檔案的URL。 如有需要，您可以使用此功能將帳戶移至協力廠商平台。

1. 在Journey Optimizer B2B edition中，在左側導覽中前往&#x200B;**[!UICONTROL 帳戶]** > **[!UICONTROL 購買群組]**。

1. 選取&#x200B;**[!UICONTROL 瀏覽]**&#x200B;標籤。

1. 按一下右上角的&#x200B;**[!UICONTROL 匯出帳戶]**。

   ![編輯帳戶詳細資料](./assets/export-accounts.png){width="800" zoomable="yes"}

1. 在對話方塊中，定義要匯出的帳戶對象引數。

   ![指定帳戶對象篩選](./assets/export-accounts-dialog.png){width="400"}

   對於&#x200B;**[!UICONTROL 參與分數]**，運運算元`Between`為包含型別，百分比範圍亦同。 例如，5.1和5都是介於&#x200B;_5和6之間的_。

   空白的篩選引數會被視為類似`Is Any`。

1. 按一下&#x200B;**[!UICONTROL 匯出帳戶]**&#x200B;以使用指定的篩選器產生CSV檔案。

1. 當您收到匯出完成的通知時，請按一下通知連結以存取CSV檔案。

   ![按一下通知即可下載匯出的帳戶清單CSV檔案](./assets/export-accounts-notification.png){width="425"}

   >[!NOTE]
   >
   >如果您的Adobe使用者帳戶偏好設定中已設定電子郵件通知的通知訂閱，則可能是電子郵件通知。

   應用程式頁面會重新導向至&#x200B;_購買群組_&#x200B;瀏覽標籤，而系統儲存檔案對話方塊會提示您儲存檔案至系統。 如果您需要共用資料，可以使用您團隊的檔案共用系統。
