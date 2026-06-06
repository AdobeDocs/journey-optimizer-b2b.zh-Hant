---
title: 啟動Marketo Engage以支援歷程動作
description: 啟用Marketo Engage連線以支援歷程動作，讓行銷人員能夠協調Marketo Engage與Journey Optimizer B2B edition之間的行銷活動。
feature: Setup, Integrations
role: Admin
exl-id: e324a11b-1025-4850-865f-ef8886a6b2bb
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
autotag-review: 2026-03-27T22:48:47.183Z
TQID: https://experienceleague.adobe.com/nM-Jxcj7wekzRks2xCqshOdlY7W8K0WKCXtWCNSb388
source-git-commit: ca0c6b10cf6a979249901d514116f373014544ad
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 75%

---

# 啟用Marketo Engage連線以支援動作

Marketo Engage動作是&#x200B;_以人物為基礎的_&#x200B;動作，可讓您在Journey Optimizer B2B edition與Marketo Engage中的&#x200B;_潛在客戶為基礎的_&#x200B;行銷工作之間，協調您的&#x200B;_以帳戶為基礎的_&#x200B;行銷協調。 使用這些動作來編排靜態清單成員資格，並將人員放入行銷活動。

若要使用Marketo Engage歷程動作，管理員必須先在Marketo Engage中建立[自訂服務](https://experienceleague.adobe.com/zh-hant/docs/marketo-developer/marketo/rest/custom-services){target="_blank"}，此服務提供驗證所需的認證。 接著，Journey Optimizer B2B edition的產品管理員會使用這些憑證來建立與Marketo Engage的連線。 接著Journey Optimizer B2B edition使用者可以參考連線，以設定個人和帳戶歷程中的Marketo Engage動作：

* [!UICONTROL 新增至Marketo清單]
* [!UICONTROL 從Marketo清單移除]
* [!UICONTROL 新增至Marketo要求行銷活動]

## 設定 Marketo Engage 連線 {#external-marketo-configure}

>[!CONTEXTUALHELP]
>id="ajo-b2b_marketo-configure-connections"
>title="外部 Marketo Engage 連線"
>abstract="產品管理員可以設定與外部 Marketo Engage 執行個體的連線，使其能用於歷程動作。"

若要設定與歷程動作搭配使用的外部Marketo Engage執行個體，請完成下列工作。

### 建立Marketo Engage自訂服務

1. 以系統管理員身分登入Marketo Engage，並[建立自訂服務](https://experienceleague.adobe.com/zh-hant/docs/marketo/using/product-docs/administration/additional-integrations/create-a-custom-service-for-use-with-rest-api){target="_blank"}。
1. 複製下列值以用於Journey Optimizer B2B edition連線：

   * Munchkin ID
   * 用戶端 ID
   * 使用者端密碼

自訂服務[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/marketo-developer/marketo/rest/custom-services#permission-list){target="_blank"}中指派的角色許可權可控管Marketo Engage工作區中資產的可見度，例如清單和行銷活動。 行銷人員可以在一個歷程中多次使用相同的連線，並在同一歷程中使用不同的Marketo Engage連線。

### 新增整合

![新增整合詳細資料](assets/integration-connection-details.png){width="800" zoomable="yes"}

1. 在Journey Optimizer B2B edition中，導覽至&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 設定]**。
1. 選取&#x200B;**[!UICONTROL 整合]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL 建立連線]**。
1. 輸入&#x200B;**[!UICONTROL Name]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。
1. 選取用於將動作套用至相符人員記錄的更新原則。

   針對連線的Marketo Engage執行個體執行動作時，選取的&#x200B;_更新原則_&#x200B;會決定Marketo Engage中的人員記錄，以選取整合式人員設定檔中是否有多個識別碼。

   * **[!UICONTROL 更新所有相符的記錄]**
   * **[!UICONTROL 僅更新最舊的相符記錄]**
   * **[!UICONTROL 只更新最新的相符記錄]**

   >[!NOTE]
   >
   >除非發生錯誤，否則不論相符專案為何，人員/潛在客戶都會繼續經過歷程。 不存在相符的記錄時，歷程動作不會在Marketo Engage中建立新的個人記錄。

1. 輸入在外部Munchkin例項中建立之服務的Marketo Engage ID、使用者端ID和使用者端密碼。
1. 按一下&#x200B;**[!UICONTROL 連線至Marketo]**。
1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 在歷程動作中使用連線

當行銷人員在歷程中使用Marketo Engage動作時，他們可以使用連線名稱設定節點。

>[!NOTE]
>
>從歷程執行的Marketo Engage動作不適用於連線的Marketo Engage執行個體的REST API限制。

完成整合後，便可從節點屬性中的&#x200B;:_&#x200B;**上的**&#x200B;_Actions使用Marketo Engage動作。

![Marketo動作清單](assets/marketo-actions-list.png){width="800" zoomable="yes"}
