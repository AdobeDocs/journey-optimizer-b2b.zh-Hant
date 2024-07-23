---
title: 資產
description: 瞭解Journey Optimizer B2B版本中的資產管理。
feature: Assets, Content
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
source-git-commit: dcd8ab2820d60654e8970944054142fc296ed54f
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 0%

---

# 資產

Assets通常是用來在Adobe Journey Optimizer B2B版本中建立歷程內容的影像。 您可以透過資產選擇器或視覺內容編輯器中的簡單拖放介面，在電子郵件、電子郵件範本和Journey Optimizer B2B Edition中編寫的片段中使用這些影像。

Adobe Journey Optimizer B2B Edition讓行銷人員能夠存取兩種型別的資產資料庫：Adobe Marketo Engage Design Studio和Adobe Experience Manager Assetsas a Cloud Service。 您可以只使用Adobe Marketo Engage Design Studio，或使用同時設定的兩個程式庫(根據您擁有的AEM Assets授權)。

## 資產管理

如果您已布建Marketo Engage帳戶和Adobe Experience Manager作為Cloud Service，則當您的使用者帳戶擁有必要許可權時，您即可存取Marketo EngageDAM和Adobe Experience Manager Assetsas a Cloud Service的存放庫。 這些存放庫是分開且不同步。 您可以使用來自任一來源的影像，但一次只可以在內容編輯器中啟用一個影像。 管理員可將從Marketo EngageDAM切換至Adobe Experience Manager Assetsas a Cloud Service。 左側導覽中的&#x200B;_[!UICONTROL Assets]_&#x200B;專案會顯示目前設定的存放庫。

### Adobe Marketo Engage Design Studio

所有Adobe Marketo Engage B2B Edition訂閱預設都會提供Journey Optimizer Design Studio資產存放庫。 這表示您可以存取儲存在「Adobe Marketo Engage > Design Studio >影像和檔案」中的任何影像資產。 您可以使用此存放庫作為本機資產庫，包括上傳、刪除和下載資產功能。 您也可以在歷程內容中使用這些資產。

支援的檔案格式：JPG、JPEG、GIF、PNG、EPS、SVG、RGB

### Adobe Experience Manager Assetsas a Cloud Service

使用Adobe Experience Manager Assets將行銷和創意工作流程結合在一起。 它與Adobe Journey Optimizer B2B Edition原生整合，因此您可以輕鬆存取Assets as a Cloud Service，以探索和使用數位資產。 它提供您Assets存放庫的存取權，供您用來填入訊息。

Adobe Experience Manager Assets可連線至Adobe Experience Manager Assets as a Cloud Service以集中處理資產工作區，進而擴充您的創意系統並統一數位資產以提供體驗傳送。 Adobe Experience Manager Assets as a Cloud Service提供簡單易用的雲端解決方案，有助於有效率地管理數位資產管理和Dynamic Media運作。 它緊密整合了進階功能，包括人工智慧和機器學習。

在[Adobe Experience Manager as a Cloud Service檔案](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/assets/overview)中進一步瞭解。

您可以從左側導覽中的&#x200B;**[!UICONTROL Assets]**&#x200B;專案，直接在Adobe Journey Optimizer B2B Edition中存取Adobe Experience Manager Assets。 在設計電子郵件內容時，您也可以存取資產和資料夾。

>[!NOTE]
>
>AEM Assets作為Cloud Service，以及Dynamic Media授權是這項整合的必要條件。<br/>
>根據您的合約和設定，您可以透過左側功能表Assets區段，直接從Adobe Journey Optimizer B2B Edition存取Adobe Experience Manager Assets as a Cloud Service 。 在設計電子郵件內容時，您也可以存取資產和資料夾。

目前，您只能在Adobe Journey Optimizer B2B版本中使用Adobe Experience Manager Assets的影像。

## 使用資產進行內容製作

在撰寫電子郵件、電子郵件範本及視覺片段時使用資產。 視覺化內容編輯器UI可讓您存取連線資產存放庫中的影像。

### 選擇資產來源

如果您有Experience Manager Assets as a Cloud Service以及預設Adobe Marketo Engage Design Studio的訂閱，您可以從任一來源選擇影像資產。 若要這麼做，您必須在建立新電子郵件、電子郵件範本或視覺化片段時選取影像來源。 或者，您可以在編輯內容時選取影像來源。 選取範圍僅適用於編輯體驗，您可以視需要變更影像來源，以從其他資料庫存取資產。

建立電子郵件

編輯電子郵件 — 若要在視覺編輯器中選擇影像資產來源，請使用畫布頂端的&#x200B;**[!UICONTROL 選取影像來源]**&#x200B;選取器。

### 將資產新增至您的內容

您可以在編寫內容時新增影像資產，實際取決於您選取的影像資產來源。

>[!BEGINTABS]

>[!TAB 新增Marketo Engage Design Studio影像資產]

您可以使用下列其中一種方法來新增Marketo Engage Design Studio資產：

* 新增結構元素，然後從左側導覽拖放資產至視覺畫布。
* 新增結構元素，然後將&#x200B;_影像_&#x200B;內容型別拖放至結構中。 在右側的屬性設定中，有兩種方式可指定影像：
   * 按一下&#x200B;**[!UICONTROL 瀏覽]**&#x200B;以開啟資產選擇器，您可在此從Adobe Marketo Engage Design Studio資產庫中選擇影像。
   * 按一下&#x200B;**[!UICONTROL 匯入媒體]**，從您的本機系統匯入資產。 匯入的資產會儲存在Adobe Marketo Engage Design Studio資料庫的Assets根資料夾中。

若要變更影像，您可以在右側屬性中更新影像的來源URL。

>[!TAB 新增Experience Manager Assets影像]

1. 在電子郵件設計工具中製作電子郵件內容時，請將影像元素拖曳至畫布上。

   右側的屬性可反映影像元素選取範圍。

1. 按一下&#x200B;**[!UICONTROL 選取資產]**&#x200B;以開啟Experience Manager資產選擇器。

   您可以在此處搜尋、篩選及存取所需的內容資產，以新增至行銷資產。 如需有關如何使用選取器的詳細資訊，請參閱本頁面。

   >[!NOTE]
   >
   >如果設定了多個存放庫，您可以使用資產選擇器上的存放庫切換器

1. 選取要插入電子郵件中的所需資產。

>[!ENDTABS]
