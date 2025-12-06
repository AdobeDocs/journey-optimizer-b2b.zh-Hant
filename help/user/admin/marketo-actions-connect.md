---
title: 啟動Marketo Engage以支援歷程動作
description: 啟用Marketo Engage連線以支援歷程動作，讓行銷人員能夠協調Marketo Engage與Journey Optimizer B2B edition之間的行銷活動。
feature: Integrations, Audiences, Buying Groups
role: User, Admin
source-git-commit: 9b77570ddb9b416251f38db51a57507a935a526a
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 1%

---


# 啟動Marketo Engage執行個體以支援動作

Marketo Engage動作是&#x200B;_以人物為基礎的_&#x200B;動作，可讓您在Journey Optimizer B2B edition與Marketo Engage中的&#x200B;_潛在客戶為基礎的_&#x200B;行銷工作之間，協調您的&#x200B;_以帳戶為基礎的_&#x200B;行銷協調。 使用這些動作來編排靜態清單成員資格，並將人員放入行銷活動。

若要使用Marketo Engage歷程動作，管理員必須先在Marketo Engage中建立[自訂服務](https://experienceleague.adobe.com/zh-hant/docs/marketo-developer/marketo/rest/custom-services){target="_blank"}，此服務提供驗證所需的認證。 接著，Journey Optimizer B2B edition的產品管理員會使用這些憑證來建立與Marketo Engage的連線。 接著Journey Optimizer B2B edition使用者可以參考連線，在<!-- person and -->帳戶歷程中設定Marketo Engage動作，例如從Marketo Engage清單新增或移除人員，或將他們新增至請求行銷活動。

## 設定Marketo Engage連線 {#external-marketo-configure}

>[!CONTEXTUALHELP]
>id="ajo-b2b_marketo-configure-connections"
>title="外部Marketo Engage連線"
>abstract="產品管理員可以設定與外部Marketo Engage執行個體的連線，以便用於歷程動作。"

完成下列工作，設定與歷程動作搭配使用的外部Marketo Engage執行個體。

### 建立Marketo Engage自訂服務

1. 以系統管理員身分登入Marketo Engage，並[建立自訂服務](https://experienceleague.adobe.com/zh-hant/docs/marketo/using/product-docs/administration/additional-integrations/create-a-custom-service-for-use-with-rest-api){target="_blank"}。
1. 複製下列值以用於Journey Optimizer B2B edition連線：

   * Munchkin ID
   * 用戶端 ID
   * 使用者端密碼

資產（例如清單和行銷活動）的Marketo Engage工作區可見度是由自訂服務中指派的[角色許可權](https://experienceleague.adobe.com/zh-hant/docs/marketo-developer/marketo/rest/custom-services#permission-list){target="_blank"}所管理。 行銷人員可以在一個歷程中多次使用相同的連線，並在同一歷程中使用不同的Marketo Engage連線。

### 新增整合

![新增整合詳細資料](assets/integration-connection-details.png){width="800" zoomable="yes"}

1. 在Journey Optimizer B2B edition中，導覽至&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 設定]**。
1. 選取&#x200B;**[!UICONTROL 整合]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL 建立連線]**。
1. 輸入&#x200B;**[!UICONTROL Name]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。
1. 選取用於將動作套用至符合個人記錄的更新原則。

   針對連線的Marketo Engage執行個體執行動作時，選取的&#x200B;_更新原則_&#x200B;會決定Marketo Engage中的人員記錄，以選取整合式人員設定檔中是否有多個識別碼。

   * **[!UICONTROL 更新所有相符的記錄]**
   * **[!UICONTROL 僅更新最舊的相符記錄]**
   * **[!UICONTROL 只更新最新的相符記錄]**

   >[!NOTE]
   >
   >除了發生錯誤外，無論符合何項，人員都會繼續此歷程。

1. 輸入在外部Munchkin例項中建立之服務的Marketo Engage ID、使用者端ID和使用者端密碼。
1. 按一下&#x200B;**[!UICONTROL 連線至Marketo]**。
1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 在歷程動作中使用連線

當行銷人員在歷程中使用Marketo Engage動作時，他們可以使用連線名稱設定節點。

完成整合後，便可從節點屬性中的&#x200B;**動作：**&#x200B;取得Marketo Engage動作。

![Marketo動作清單](assets/marketo-actions-list.png){width="800" zoomable="yes"}