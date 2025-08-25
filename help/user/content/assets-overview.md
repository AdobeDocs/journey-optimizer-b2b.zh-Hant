---
title: 資產
description: 了解 Journey Optimizer B2B Edition 中的資產管理。
feature: Assets, Content
role: User
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
source-git-commit: ea2093b03ba89f9e8d3f0db60b65cb143603c217
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 54%

---

# 資產

在[!DNL Adobe Journey Optimizer B2B Edition]中，資產通常是設計內容以支援帳戶歷程時使用的影像。 您可以透過資產選擇器或視覺設計空間內的簡單拖放介面，在電子郵件、電子郵件範本和片段中使用這些影像。

[!DNL Journey Optimizer B2B Edition]為行銷人員提供兩種資產資料庫的存取權： [!DNL Adobe Marketo Engage] [!DNL Design Studio]和[!DNL Adobe Experience Manager Assets as a Cloud Service]。 您可以只使用Adobe Marketo Engage Design Studio，或使用同時設定的兩個程式庫（根據您擁有的[!DNL Experience Manager Assets]授權）。

## 資產管理

如果您已布建[!DNL Adobe Experience Manager as a Cloud Services]，則當您的使用者帳戶具有必要許可權時，您就可以存取[!DNL Marketo Engage Design Studio]和[!DNL Adobe Experience Manager Assets as a Cloud Service]的存放庫。 這些存放庫是獨立的而且不會同步。您可以使用任一來源的影像。

### Adobe Marketo Engage 資產

每個[!DNL Adobe Marketo Engage Design Studio]訂閱預設會提供[!DNL Journey Optimizer B2B Edition]資產存放庫。 這表示您可以存取任何儲存在[!DNL Adobe Marketo Engage]中的影像資產（[!UICONTROL Design Studio] > [!UICONTROL 影像與檔案]）。 您可以使用此存放庫做為您的本機資產庫，包含上傳和下載資產功能。您也可以在歷程內容中使用這些資產。

有內建護欄，可防止從[!DNL Marketo Engage]編輯[!DNL Journey Optimizer B2B Edition]資產，以及執行刪除和移動作業。 這些保護功能可確保維護來源資產(Marketo Engage Design Studio)，同時允許在[!DNL Journey Optimizer B2B Edition]中順暢地讀取和重複使用。

支援的檔案格式：JPG、JPEG、GIF、PNG、EPS、SVG 以及 RGB

### Adobe Experience Manager Assets as a Cloud Service

利用 [!DNL Adobe Experience Manager Assets] 將行銷與創意內容工作流程結合在一起。它與[!DNL Journey Optimizer B2B Edition]原生整合，因此您可以輕鬆存取Assets as a Cloud Service以探索及使用數位資產。 它提供 Assets 存放庫的存取權限，可讓您取得用於填入訊息的資產。

[!DNL Adobe Journey Optimizer B2B Edition]可以連線至[!DNL Adobe Experience Manager Assets as a Cloud Service]進行集中式資產管理，以擴充您的創意系統並統一數位資產以提供體驗傳遞。 [!DNL Adobe Experience Manager Assets as a Cloud Service]提供易於使用的雲端解決方案，以進行有效的數位資產管理和Dynamic Media作業。 其與進階功能包括人工智慧和機器學習無縫整合。

請參閱 [Adobe Experience Manager as a Cloud Service 文件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/overview){target="_blank"}以了解更多。

{{aem-assets-licensing-note}}

從內容設計左側導覽中的[!DNL Adobe Experience Manager Assets]Experience Manager Assets[!DNL Journey Optimizer B2B Edition]專案，直接存取&#x200B;**[!UICONTROL 中的]**。 您亦可以在設計電子郵件、電子郵件範本及視覺片段內容時存取資產和資料夾。

目前，您僅可在 Adobe Journey Optimizer B2B Edition 中使用來自 Adobe Experience Manager Assets 的影像。

## 使用資產編寫內容

在製作電子郵件、電子郵件範本及視覺片段時使用資產。視覺化內容編輯器可讓您存取已連接的資產存放庫中的影像。如果您訂閱 Experience Manager Assets as a Cloud Service 以及預設的 Adobe Marketo Engage Design Studio，則可以從任一來源選擇影像資產。您也可以上傳影像資產，將它放置在已連線[!DNL Journey Optimizer B2B Edition]存放庫的[!DNL Marketo Engage Design Studio]工作區中。

您可以在編輯影像元件的設定時選擇影像來源，或直接在畫布上選擇。

* **_影像元件設定_** — 當您在視覺化設計空間選取影像元件時，您可以在右側面板中檢視及編輯設定。 若要新增或變更元件中顯示的影像檔案，請選擇來源類型並選取一個影像檔案。

  ![在右側面板中編輯影像元件設定](./assets/content-assets-image-settings.png){width="350"}

* **_空白元件_** — 當您在視覺化設計空間新增影像元件時，該元件會是空白的，可讓您輕鬆選擇來源並選取影像檔案。

  ![選擇來源，以選取空白影像元件的影像檔案](./assets/content-assets-image-component-empty.png){width="500"}

* **_影像元件工具列_** — 當您在視覺設計空間選取影像元件時，工具列可讓您輕鬆選擇來源並選取影像檔案。

  ![使用工具列來選擇來源，以選取影像元件的影像檔案](./assets/content-assets-image-toolbar-settings.png){width="500"}

視影像資產來源而定，您可以在製作內容時新增影像資產。您也可以在結構元件的背景設定中選擇影像資產。

>[!BEGINTABS]

>[!TAB Marketo Engage Assets]

按一下&#x200B;**[!UICONTROL Marketo Engage Assets]**&#x200B;以開啟資產選擇器，您可在此從[!DNL Marketo Engage]工作區或Journey Optimizer B2B edition工作區中選擇影像。

![從工作區中選取影像資產](./assets/content-assets-image-me-selected.png){width="700" zoomable="yes"}

您可以使用搜尋和篩選器來找到所需的影像資產。選取資產並按一下「**[!UICONTROL 選取]**」，以便用作影像元件。

如需有關使用[!DNL Marketo Engage]影像資產的詳細資訊，請參閱[在您的內容中使用資產](./marketo-engage-design-studio.md#use-assets-in-your-content)。

>[!TAB Experience Manager Assets]

按一下「**[!UICONTROL Experience Manager Assets]**」以開啟資產選擇器，您可以從 Experience Manager Assets 存放庫中選擇一個影像。

![從 AEM Assets 存放庫中選取一個影像資產](./assets/content-assets-image-aem-selected.png){width="700" zoomable="yes"}

您可以使用搜尋和篩選器來找到所需的影像資產。選取資產並按一下「**[!UICONTROL 選取]**」，以便用作影像元件。

如需有關使用[!DNL Experience Manager Assets]影像檔案的詳細資訊，請參閱[存取AEM Assets影像](./aem-assets.md#access-aem-assets-images)。

>[!TAB 匯入媒體]

按一下「**[!UICONTROL 匯入媒體]**」來選取影像檔案，並將其匯入為可用於 Journey Optimizer B2B Edition 內容的資產。

![選取您自己的影像檔案以匯入做為資產](./assets/content-assets-image-import-file-selected.png){width="500" zoomable="yes"}

拖放檔案或從檔案系統中選取檔案後，按一下「**[!UICONTROL 匯入]**」。匯入的資產儲存在[!DNL Journey Optimizer B2B Edition]存放庫的[!DNL Adobe Marketo Engage Design Studio]工作區中。

>[!ENDTABS]
