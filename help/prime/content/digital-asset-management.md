---
title: 資產
description: 從Journey Optimizer B2B edition管理電子郵件、範本和視覺片段的影像資產。
feature: Assets, Content
role: User
badge: label="Beta" type="Informative"
autotag-review: '2026-06-18T20:11:57.611Z'
TQID: 'https://experienceleague.adobe.com/Xsl4zqpk4xqXuOS85Z5U08tnbv8GWm3FXdqsegPCBI4'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 85f61c8fa8eda07dfe8ea1e83f3c261c9159976f
workflow-type: tm+mt
source-wordcount: 495
ht-degree: 3%

---

# 資產

在[!DNL Adobe Journey Optimizer B2B Prime]中，資產通常是設計內容以支援歷程時使用的影像。 您可以在電子郵件、電子郵件範本以及資產選擇器的視覺片段中，或在視覺化設計空間內的簡單拖放介面中使用這些影像。

支援的檔案格式：JPG、JPEG、GIF、PNG、EPS、SVG 以及 RGB


&#x200B;>>
您尚無法從外部系統（例如Marketo Engage DAM）匯入資產，也無法存取預先填入的資產資料庫。 預計未來版本將包括從現有系統匯入資產、資料夾支援和擴充的資產管理功能。

<!-- You can [edit these assets using Adobe Express](./image-edit-adobe-express.md), and move them into folders to organize them for use across your emails, templates, and fragments. -->

**Assets**&#x200B;資料庫可讓您存取集中式存放庫，以儲存和管理影像和其他創意資產。 其中包括AI支援的功能，可自動產生中繼資料並啟用自然語言搜尋。

在左側導覽列中，展開&#x200B;**[!UICONTROL 內容管理]**&#x200B;並選取&#x200B;**[!UICONTROL Assets]**。

>[!NOTE]
>
>在此Beta版本中，您可以直接從電子郵件畫布中的Marketo Engage資產庫一次性副本選擇影像和資產。 您也可以從&#x200B;_[!UICONTROL Assets]_&#x200B;資料庫或內容設計空間上傳其他影像資產。 這些上傳的資產只能在[!DNL Adobe Journey Optimizer B2B Prime]執行個體中使用。

![Assets資料庫](./assets/dam-asset-library-list-view.png){width="800" zoomable="yes"}

>[!BEGINSHADEBOX]

第一次存取&#x200B;_[!UICONTROL Assets]_&#x200B;資料庫時，請檢閱&#x200B;_[!UICONTROL 創作AI使用條款]_&#x200B;並按一下&#x200B;**[!UICONTROL 同意並繼續]**。

![Assets資料庫](./assets/dam-asset-library-gen-ai-agree.png){width="500"}

>[!ENDSHADEBOX]

程式庫支援兩種版面配置選項：

* **[!UICONTROL 清單]** — 按一下&#x200B;_清單檢視_ （![清單檢檢視示](../../assets/do-not-localize/icon-falco-list-view.svg) ）圖示，以使用中繼資料資料欄的可排序表格顯示資產。
* **[!UICONTROL 資產庫]** — 按一下&#x200B;_資產庫檢視_ （![資產庫檢檢視示](../../assets/do-not-localize/icon-falco-gallery-view.svg)）圖示，將資產顯示為視覺縮圖格線。

## 搜尋資產 {#find-assets}

使用&#x200B;_[!UICONTROL 搜尋]_&#x200B;欄位，以自然語言描述您需要的內容來尋找資產。 搜尋結果以AI產生的中繼資料為基礎，因此您不限於依檔案名稱搜尋。

**範例：**

* `team members`
* `nature`
* `exercise`

![從Assets資料庫中的搜尋結果中選取的影像](./assets/dam-asset-library-select-image.png){width="700" zoomable="yes"}

## 檢視資產詳細資訊 {#view-details}

選取要開啟其詳細資料檢視的資產。 詳細資料檢視會顯示AI產生的說明、標籤和關鍵字，以及其他中繼資料欄位。 上傳資產時，會自動產生此資訊。

在清單或資產庫檢視中選取任何資產，以在右側開啟其詳細資料檢視。 選取AI中繼資料標籤以檢視AI產生的說明、標籤和中繼資料。

![從Assets資料庫中的搜尋結果中選取的影像](./assets/dam-asset-library-select-image-metadata.png){width="700" zoomable="yes"}

## 上傳資產 {#upload}

1. 按一下右上方的&#x200B;**[!UICONTROL 上傳]**。

1. 在對話方塊中，從本機系統拖放檔案。

   ![上傳影像資產](./assets/dam-upload-assets-dialog.png){width="450"}

   或者，您可以按一下[從電腦中選取檔案]&#x200B;**&#x200B;**，使用本機檔案系統來尋找及選取檔案。

1. 按一下&#x200B;**[!UICONTROL 上傳檔案]**&#x200B;以確認並上傳檔案到存放庫。

上傳完成後，系統會自動產生說明、指定標籤和關鍵字，並擷取視覺屬性，例如主旨和設定。 不需要手動標籤。 在此程式完成之前，新影像會以&#x200B;_[!UICONTROL 處理]_&#x200B;狀態顯示。

![處理狀態中的新影像資產](./assets/dam-asset-library-upload-processing.png){width="700" zoomable="yes"}
