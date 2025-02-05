---
title: 資產
description: 瞭解Journey Optimizer B2B edition的資產管理。
feature: Assets, Content
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
source-git-commit: 728d5316cfdeee92bd4f67277d299bbec2773a4f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# 資產

在Adobe Journey Optimizer B2B edition中，資產通常是設計內容以支援帳戶歷程時使用的影像。 您可以透過資產選擇器或視覺內容編輯器中的簡單拖放介面，在電子郵件、電子郵件範本和片段中使用這些影像。

Adobe Journey Optimizer B2B edition讓行銷人員能夠存取兩種型別的資產資料庫：Adobe Marketo Engage Design Studio和Adobe Experience Manager Assetsas a Cloud Service。 您可以只使用Adobe Marketo Engage Design Studio，或使用同時設定的兩個程式庫(根據您擁有的AEM Assets授權)。

## 資產管理

如果您已布建Adobe Experience Manager作為Cloud Service，則當您的使用者帳戶具有所需許可權時，您即可存取Marketo Engage Design Studio和Adobe Experience Manager Assetsas a Cloud Service的存放庫。 這些存放庫是分開且不同步。 您可以使用任一來源的影像。

### Adobe Marketo Engage資產

所有Adobe Marketo Engage B2B edition訂閱預設都會提供Journey Optimizer Design Studio資產存放庫。 這表示您可以存取任何儲存在Adobe Marketo Engage中的影像資產（[!UICONTROL Design Studio] > [!UICONTROL 影像與檔案]）。 您可以使用此存放庫作為本機資產庫，包括上傳和下載資產功能。 您也可以在歷程內容中使用這些資產。

有內建的護欄可防止從Journey Optimizer B2B edition編輯Marketo Engage資產，以及阻止刪除和移動操作。 這些保護功能可確保維護來源資產(Marketo Engage Design Studio)，同時允許在Journey Optimizer B2B edition中順暢地讀取和重複使用。

支援的檔案格式：JPG、JPEG、GIF、PNG、EPS、SVG和RGB

### Adobe Experience Manager Assetsas a Cloud Service

使用Adobe Experience Manager Assets將行銷和創意工作流程結合在一起。 它與Adobe Journey Optimizer B2B edition原生整合，因此您可以輕鬆存取Assets as a Cloud Service，以探索和使用數位資產。 它提供您Assets存放庫的存取權，供您用來填入訊息。

Adobe Journey Optimizer B2B edition可連線至Adobe Experience Manager Assets as a Cloud Service以進行集中式資產管理，進而擴充您的創意系統並統一數位資產以進行體驗傳送。 Adobe Experience Manager Assets as a Cloud Service提供簡單易用的雲端解決方案，有助於有效率地管理數位資產管理和Dynamic Media運作。 它緊密整合了進階功能，包括人工智慧和機器學習。

在[Adobe Experience Manager as a Cloud Service檔案](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/overview)中進一步瞭解。

{{aem-assets-licensing-note}}

從內容設計左側導覽中的&#x200B;**[!UICONTROL Adobe Experience Manager Assets]**&#x200B;專案，直接在Journey Optimizer B2B edition中存取Experience Manager Assets。 在設計電子郵件、電子郵件範本和視覺片段內容時，您也可以存取資產和資料夾。

目前，您只能在Adobe Journey Optimizer B2B edition中使用Adobe Experience Manager Assets的影像。

## 使用資產進行內容製作

在撰寫電子郵件、電子郵件範本及視覺片段時使用資產。 視覺化內容編輯器可讓您存取連線資產存放庫中的影像。 如果您有Experience Manager Assetsas a Cloud Service以及預設Adobe Marketo Engage Design Studio的訂閱，您可以從任一來源選擇影像資產。 您也可以上傳影像資產，將其置於已連線之Marketo Engage Design Studio存放庫的Journey Optimizer B2B edition工作區中。

您可以在編輯影像元件的設定時或直接在畫布上選擇影像來源。

* **_影像元件設定_** — 當您在視覺化設計工具中選取影像元件時，您可以在右側面板中檢視及編輯設定。 若要新增或變更元件中顯示的影像檔案，請選擇來源型別並選取影像檔案。

  ![在右側面板中編輯影像元件設定](./assets/content-assets-image-settings.png){width="350"}

* **_空白元件_** — 當您在視覺化設計工具中新增影像元件時，該元件會是空的，而且可供您輕鬆選擇來源及選取影像檔案。

  ![選擇來源以選取空白影像元件的影像檔](./assets/content-assets-image-component-empty.png){width="500"}

* **_影像元件工具列_** — 當您在視覺化設計工具中選取影像元件時，工具列可讓您輕鬆選擇來源並選取影像檔案。

  ![使用工具列選擇來源，以選取影像元件的影像檔](./assets/content-assets-image-toolbar-settings.png){width="500"}

您可以在編寫內容時新增影像資產，實際取決於影像資產來源。

>[!BEGINTABS]

>[!TAB Marketo EngageAssets]

按一下&#x200B;**[!UICONTROL Marketo EngageAssets]**&#x200B;以開啟資產選擇器，您可在此從Marketo Engage工作區或Journey Optimizer B2B edition工作區中選擇影像。

![從工作區中選取影像資產](./assets/content-assets-image-me-selected.png){width="700" zoomable="yes"}

您可以使用搜尋和篩選來找出所需的影像資產。 選取該資產，然後按一下&#x200B;**[!UICONTROL 選取]**&#x200B;以將其用於影像元件。

如需有關使用Marketo Engage影像資產的詳細資訊，請參閱[在您的內容中使用資產](./marketo-engage-design-studio.md#use-assets-in-your-content)。

>[!TAB Experience Manager Assets]

按一下&#x200B;**[!UICONTROL Experience Manager Assets]**&#x200B;以開啟資產選擇器，您可在此從Experience Manage Assets存放庫中選擇影像。

![從AEM Assets存放庫選取影像資產](./assets/content-assets-image-aem-selected.png){width="700" zoomable="yes"}

您可以使用搜尋和篩選來找出所需的影像資產。 選取該資產，然後按一下&#x200B;**[!UICONTROL 選取]**&#x200B;以將其用於影像元件。

如需有關使用Experience Manager Assets影像檔案的詳細資訊，請參閱[存取AEM Assets影像](./aem-assets.md#access-aem-assets-images)。

>[!TAB 匯入媒體]

按一下&#x200B;**[!UICONTROL 匯入媒體]**&#x200B;以選取影像檔案，並將其匯入為可用於Journey Optimizer B2B edition內容的資產。

![選取您自己的影像檔案，以匯入為資產](./assets/content-assets-image-import-file-selected.png){width="500" zoomable="yes"}

拖放檔案或從檔案系統選取檔案後，按一下[匯入]。**** 匯入的資產會儲存在Adobe Marketo Engage Design Studio存放庫的Journey Optimizer B2B edition工作區中。

>[!ENDTABS]
