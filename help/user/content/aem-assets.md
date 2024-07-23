---
title: 使用Experience Manager Assets
description: 瞭解如何在Adobe Journey Optimizer B2B Edition中編寫內容時，使用已連線AEM Assets存放庫中的影像資產。
feature: Assets, Content
source-git-commit: 0bdf0da4db0cbfc781d16f1c50716b1fc8ea4db9
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# 使用Experience Manager資產

當Adobe Experience Manager Assets as a Cloud Service與Adobe Journey Optimizer B2B Edition整合時，您可以輕鬆探索和存取數位資產，以用於行銷內容。 當您編寫內容時，可以從左側導覽的&#x200B;_[!UICONTROL Assets]_&#x200B;專案存取資產，以及在編寫帳戶歷程的電子郵件內容時也可存取資產。 您也可以直接從AEM Assets B2B Edition上傳資產至已連線的Adobe Journey Optimizeras a Cloud Service存放庫。

>[!NOTE]
>
>目前，Adobe Journey Optimizer B2B Edition僅支援Adobe Experience Manager Assets的影像資產。 必須從Adobe Experience Manager Assets中央存放庫變更資產。 [瞭解更多](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets)

當您使用這些數位資產時，Assets as a Cloud Service中的最新變更會透過連結的參考自動傳播到即時電子郵件行銷活動。 如果在Adobe Experience Manager Assetsas a Cloud Service中刪除影像，這些影像在電子郵件中顯示時會有中斷的參照。 當帳戶歷程中目前使用的資產被修改或刪除時，歷程作者會收到有關影像變更和使用影像的歷程清單的通知。 對資產的所有變更必須在Adobe Experience Manager Assets中央存放庫中完成。

## 使用AEM Assets作為影像來源

如果您的環境有一或多個[Assets存放庫連線](../admin/configure-aem-repositories.md)，您可以在建立或檢視電子郵件、電子郵件範本或視覺化片段的詳細資料時，指定AEM Assets作為資產的來源。

* 建立新內容時，請在對話方塊中選擇`AEM Assets`做為&#x200B;**[!UICONTROL Image Source]**&#x200B;專案。

  ![在建立對話方塊中選取AEM Assets作為影像來源](./assets/create-dialog-aem-assets.png){width="500"}

* 開啟現有的內容資源時，請在右側的&#x200B;_[!UICONTROL 內文]_&#x200B;面板中選擇`AEM Assets`。

  ![在屬性中選取AEM Assets作為影像來源](./assets/content-source-aem-assets.png){width="700" zoomable="yes"}

## 存取資產以進行製作

>[!IMPORTANT]
>
>管理員需要將存取Assets的使用者新增至Assets消費者使用者或/和Assets使用者產品設定檔。 [瞭解更多](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support#managing-products-and-user-access-in-admin-console)

在視覺內容編輯器中，按一下左側邊欄中的&#x200B;_資產選擇器_&#x200B;圖示。 這會將工具面板變更為所選存放庫中的可用資產清單。

![按一下Assets選擇器圖示以存取影像資產](./assets/content-assets-selector-aem-assets.png){width="700" zoomable="yes"}

如果您有多個連線的AEM存放庫，請按一下&#x200B;**[!UICONTROL 存放庫]**&#x200B;的功能表箭頭，以選擇要使用的存放庫。

![選擇AEM Assets存放庫以存取影像資產](./assets/content-assets-selector-aem-repo.png){width="700" zoomable="yes"}

將影像資產新增至視覺畫布的方法有很多種：

* 從左側導覽拖放影像縮圖。

  ![選擇AEM Assets存放庫以存取影像資產](./assets/content-drag-drop-image-aem-assets.png){width="700" zoomable="yes"}

* 將影像元件新增至畫布並按一下&#x200B;**[!UICONTROL 瀏覽]**&#x200B;以開啟&#x200B;_[!UICONTROL 選取Assets]_&#x200B;對話方塊。

  從對話方塊中，您可以從選取的存放庫中選擇影像。

  有多種工具可協助您找到所需的資產。

  ![在[選取Assets]對話方塊中使用工具來尋找及選取影像資產](./assets/content-select-assets-dialog-aem.png){width="700" zoomable="yes"}

   * 變更右上角的&#x200B;**[!UICONTROL 存放庫]**。

   * 按一下右上角的「**[!UICONTROL 管理資產]**」，在其他瀏覽器分頁中開啟Assets存放庫，並使用AEM Assets管理工具。

   * 按一下右上角的&#x200B;_檢視型別_&#x200B;選擇器，將顯示變更為&#x200B;**[!UICONTROL 清單檢視]**、**[!UICONTROL 格線檢視]**、**[!UICONTROL 相簿檢視]**&#x200B;或&#x200B;**[!UICONTROL 瀑布檢視]**。

   * 按一下&#x200B;_排序順序_&#x200B;圖示，以變更升序與降序之間的排序順序。

   * 按一下&#x200B;**[!UICONTROL 排序依據]**&#x200B;功能表箭頭，將排序條件變更為&#x200B;**[!UICONTROL 名稱]**、**[!UICONTROL 大小]**&#x200B;或&#x200B;**[!UICONTROL 已修改]**。

   * 按一下左上方的&#x200B;_篩選器_&#x200B;圖示，以根據您的條件篩選顯示的專案。

   * 在搜尋欄位中輸入文字，以篩選顯示的專案以符合資產名稱。

  ![使用篩選和搜尋欄位來尋找資產](./assets/content-select-assets-dialog-aem-filter.png){width="700" zoomable="yes"}

<!-- 
## Upload assets

To import files to Assets as a Cloud Service, you first need to browse or create the folder to be used for storage. You can then import an asset and add it to your email content. After assets are uploaded, you can [use the image assets as you author content](./assets-overview.md#add-assets-to-your-content).

1. While authoring your content in the email designer, drag an image element into the canvas. 

   The properties on the right reflect the image element selection. 

1. Click **[!UICONTROL Import media]** to open the _[!UICONTROL Upload image]_ dialog.

1. If your file system is open to your image file, drag and drop the file on the box in the dialog.

   ![Upload image file to Assets repository](./assets/email-designer-image-upload.png){width="700" zoomable="yes"}

   You can also click the **[!UICONTROL Select a file from your computer]** link and use your file system to locate and select the image file. Click Open and the image file is displayed in the box.

1. Click **[!UICONTROL Import]**.

-->