---
title: LinkedIn 帳號配對客群
description: 瞭解如何連線LinkedIn帳戶並為帳戶成員啟用資料流。
feature: Integrations, Audiences, Buying Groups
role: User, Admin
exl-id: d2303529-16c4-4b0b-b8c8-404dff8ec63d
source-git-commit: 1cc50d33e396e490f401330688e5d322270090e3
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 13%

---

# LinkedIn 帳號配對客群

Journey Optimizer B2B edition可讓您透過帳戶相符的受眾來產生LinkedIn廣告受眾，其目的是協助您在購買群組中填入空角色。 透過定義一組購買群組篩選器，您可以維護「LinkedIn相符對象」，以鎖定符合您購買群組引數的潛在客戶。 您也可以從&#x200B;_採取動作_&#x200B;節點的帳戶歷程啟用對象。

此功能善用 Experience Platform 目標來管理整合的某些部分。資料流上限為10個。

在從Journey Optimizer B2B edition起始資料流之前，您必須至少有一個[（公司） LinkedIn相符對象目的地聯結器](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/social/linkedin#connect){target="_blank"}的執行個體，而且已在Experience Platform應用程式中設定LinkedIn促銷活動管理員帳戶。

## 設定新的 LinkedIn 帳戶連結 {#linkedin-destination-setup}

>[!CONTEXTUALHELP]
>id="ajo-b2b_linkedin_destination_setup"
>title="需要進行 LinkedIn 目的地設定"
>abstract="傳送依照購買群組篩選的帳戶至 Linkedin 目的地，與潛在的購買群組成員互動。您可以為 10 個不同的已篩選帳戶群組建立最多 10 個資料流。若要開始使用此功能，請先新增 Linkedin 目的地。"

1. 在Experience Platform中，前往左側導覽中的&#x200B;**[!UICONTROL 連線]** > **[!UICONTROL 目的地]**，然後選取&#x200B;**[!UICONTROL 目錄]**&#x200B;索引標籤。

1. 在目錄中，找到&#x200B;**[!UICONTROL （公司） LinkedIn相符的受眾]**&#x200B;聯結器。

   >[!TIP]
   >
   >您可以在搜尋方塊中輸入`LinkedIn`以快速找到聯結器。

1. 在聯結器卡中，按一下&#x200B;_更多_ (**...**)圖示並選擇&#x200B;**[!UICONTROL 設定新目的地]**。

   ![存取（公司） LinkedIn相符對象聯結器](./assets/aep-destinations-catalog-linkedin.png){width="800" zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 新帳戶]**&#x200B;並按一下&#x200B;**[!UICONTROL 連線到目的地]**。

   ![連線新的LinkedIn帳戶](./assets/aep-destinations-catalog-linkedin-new-account.png){width="500"}

1. 提供您的LinkedIn憑證並登入。

   驗證後，LinkedIn帳戶會連線為Experience Platform中的目的地。

   ![顯示帳戶連線確認](./assets/aep-destinations-catalog-linkedin-connected.png){width="400"}

   >[!IMPORTANT]
   >
   >此時，**不要**&#x200B;輸入&#x200B;_[!UICONTROL 目的地詳細資料]_。 只需要連線。

## 更新帳戶詳細資料

在Journey Optimizer B2B edition中，購買群組可以看到LinkedIn帳戶的名稱和說明。 最佳實務是更新這些資訊，以便與購買群組合作的行銷人員可輕鬆識別這些資訊。 您可以在Experience Platform或Journey Optimizer B2B edition UI中變更帳戶詳細資料。

1. 前往左側導覽中的&#x200B;**[!UICONTROL 連線]** > **[!UICONTROL 目的地]**，然後選取&#x200B;**[!UICONTROL 帳戶]**&#x200B;標籤。

1. 針對您建立的新帳戶，按一下&#x200B;_更多_ (**...**)功能表，然後選擇&#x200B;**[!UICONTROL 編輯詳細資料]**。

   ![編輯帳戶詳細資訊](./assets/aep-destinations-accounts-edit-details.png){width="800" zoomable="yes"}

1. 在對話方塊中，更新名稱和說明。

   ![編輯名稱和描述](./assets/destinations-linkedin-account-edit-details-dialog.png){width="500"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 啟用購買群組的帳戶

>[!NOTE]
>
>如果您已有10個資料流，則無法建立另一個資料流。 如果您已達到最大數量，請先刪除Experience Platform中的一個專案，然後再在Journey Optimizer B2B edition中建立新專案。

1. 在 Journey Optimizer B2B Edition，前往左側導覽中的「**[!UICONTROL 帳戶]** > **[!UICONTROL 購買群組]**」。

1. 選取「**[!UICONTROL 瀏覽]**」索引標籤。

1. 按一下右上角的&#x200B;**[!UICONTROL 啟用至LinkedIn目的地]**。

   ![編輯帳戶詳細資訊](./assets/activate-linkedin-destination.png){width="800" zoomable="yes"}

1. 為資料流提供描述性名稱和說明（選用）。

   儲存之後，您為資料流指定的名稱會加上&#x200B;_AJOB2B_，以協助識別Experience Platform中的資料流。

1. 輸入LinkedIn行銷活動管理員帳戶[的](https://www.linkedin.com/help/lms/answer/a424270)帳戶ID。

   您可以在Campaign Manager UI中依帳戶名稱尋找您的帳戶ID。

   ![新增資料流詳細資料](./assets/destinations-linkedin-activate-details.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 選取購買群組篩選器]**&#x200B;並定義帳戶對象的引數。

   >[!IMPORTANT]
   >
   >目前，在啟動資料流後無法編輯篩選器。 啟動資料流之前，請仔細檢查您的工作。

   ![根據購買群組指定帳戶對象篩選](./assets/destinations-linkedin-activate-buying-group-filters.png){width="400"}

   在「**[!UICONTROL 參與度分數]**」中，`Between` 運算子是包含性的，百分比範圍亦同。例如，5.1 和 5 均是在 5 和 6 _之間_。

   空白條件的處理方式如同`Is Any`。

   按一下&#x200B;**[!UICONTROL 儲存]**&#x200B;以新增指定的篩選器。

1. 按一下&#x200B;**[!UICONTROL 選取LinkedIn目的地]**，然後選擇您要使用的已設定LinkedIn目的地。

   啟用時，此設定會使用目的地設定和對應的虛擬區段來建立資料流。

1. 仔細檢查您的設定，然後按一下右上方的&#x200B;**[!UICONTROL [啟動]]**。

   在確認對話方塊中再按一下&#x200B;**[!UICONTROL 啟動]**。

   橫幅會顯示連結，連至Experience Platform中的資料流功能表，讓您檢視資料流記錄。

## 從帳戶歷程啟用對象

從2025.10版開始，對帳戶使用&#x200B;_對目的地啟用_&#x200B;動作，直接從您的歷程對LinkedIn目的地啟用帳戶。 針對LinkedIn目的地使用動作，可消除多系統移交並減少延遲，進而簡化行銷活動的執行作業。 例如，身為行銷人員，您可以在關鍵購買角色遺失時，自動對LinkedIn啟用高意圖帳戶以重新進行目標定位，或根據閒置篩選器重新與休眠帳戶互動。

1. 在歷程畫布中選取&#x200B;_執行動作_&#x200B;節點後，將帳戶&#x200B;**[!UICONTROL 上的]**&#x200B;動作設定為&#x200B;**[!UICONTROL 啟用到目的地]**。

1. 按一下&#x200B;**[!UICONTROL 選取目的地]**。

   ![歷程節點 — 對帳戶採取動作 — 啟用到目的地](../journeys/assets/node-activate-destination-select-destination.png){width="600" zoomable="yes"}

1. 在對話方塊中，選取設定的LinkedIn目的地，然後按一下&#x200B;**[!UICONTROL 儲存]**。

   ![歷程節點 — 對帳戶採取動作 — 啟用到目的地 — 選取目的地對話方塊](../journeys/assets/node-activate-destination-select-destination-dialog.png){width="700" zoomable="yes"}

1. 輸入用來識別目的地中已啟動對象的&#x200B;**[!UICONTROL 對象名稱]**。

   ![歷程節點 — 對帳戶採取動作 — 啟用到目的地 — 完成的設定](../journeys/assets/node-activate-destination-settings.png){width="550" zoomable="yes"}

## 協調付費媒體參與

您可以透過付費媒體管道（例如LinkedIn廣告對象）與帳戶成員互動，以取得、培養客戶並符合銷售資格。 使用帳戶歷程中的&#x200B;_執行動作_&#x200B;節點，透過最適合不同帳戶成員的外部管道，自動與帳戶的主要成員進行互動。

>[!VIDEO](https://video.tv.adobe.com/v/3448649/?learn=on)