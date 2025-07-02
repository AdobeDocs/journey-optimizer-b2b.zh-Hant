---
title: 管理員和行銷人員的上線指引
description: 作為 Journey Optimizer B2B Edition 的新管理員或使用者，了解上線流程中的關鍵內容。
role: Admin, User
level: Beginner
exl-id: 83f8e666-0b31-4323-9902-4fdf4446424c
source-git-commit: d0bd2d5153b972df92ff42c6f1eebb25448b222f
workflow-type: ht
source-wordcount: '685'
ht-degree: 100%

---

# 上線指引

您在 Adobe Journey Optimizer B2B Edition 中要使用的功能和工具會依據您在團隊中的角色而定。管理員可以根據您的組織定義數種使用者類型，並依這些使用者的權限授予特定功能的存取權。

>[!TIP]
>
>如需有關效能護欄和靜態限制的資訊，請同時參閱您的授權權益以及相對應的[產品描述](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}。

>[!BEGINTABS]

>[!TAB 管理員]

在您的團隊開始使用 Adobe Journey Optimizer B2B Edition 的功能之前，您必須執行幾個步驟做好環境準備。請執行這些步驟，以便資料工程師和行銷人員可以開始使用 Adobe Journey Optimizer B2B Edition。

作為系統管理員，您必須了解產品輪廓並指派沙箱管理和管道設定的權限。您也必須設定沙箱，並針對可用的產品輪廓進行管理。然後，您可以將團隊成員指派給產品輪廓。具有 Adobe Admin Console 存取權的產品管理員可以管理這些功能。[了解更多關於 Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。

請前往下列頁面，了解存取管理：

1. **建立沙箱**&#x200B;以將執行個體分區到獨立的虛擬環境中。 [了解更多](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home#understanding-sandboxes){target="_blank"}

1. **與您的資料工程師合作**，規劃與實施您的 B2B 客群和輪廓啟動。檢閱已發布的藍圖並根據您的要求遵循指南。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/blueprints-learn/architecture/b2b-activation/overview){target="_blank"}

1. **設定產品輪廓**。產品輪廓是 Adobe Experience Platform 中的一組單一權利，允許使用者存取介面中的某些功能或物件。[了解更多](../admin/user-management.md#create-the-marketo-engage-product-profile)

1. 針對產品輪廓 (包括沙箱) **設定使用者權限**，並將團隊成員指派至不同的產品輪廓，藉此授予存取權。此任務會在 Admin Console 執行。[了解更多](../admin/user-management.md#create-a-user-group)

1. 在 Marketo Engage 中&#x200B;**設定電子郵件傳送** ，使您的團隊能夠從帳戶旅程中發送電子郵件內容。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability){target="_blank"}

1. **設定 SMS 服務**。設定其中一個受支援的第三方 SMS 供應商，該供應商獨立提供簡訊服務，並在 Adobe Journey Optimizer B2B Edition 中設定帳戶認證。[了解更多](../admin/configure-channels-sms.md)

1. **針對使用 Assets as a Cloud Service 進行集中數位資產管理的團隊，設定並啟用 Adobe Experience Manager Assets**。[了解更多](../admin/configure-aem-repositories.md)

1. 針對負責建立監聽 AEP 體驗事件的帳戶歷程之團隊，**設定 Adobe Experience Platform (AEP) 體驗事件定義**。[了解更多](../admin/configure-aep-events.md)

>[!TAB 行銷人員]

身為行銷人員或&#x200B;_客戶歷程從業人員_，您負責設計歷程和製作內容。系統管理員和資料工程師把您的環境準備好並授予您相關存取權後，您便可以開始使用 Adobe Journey Optimizer B2B Edition。

關於設定您的第一個歷程、新增資產及傳送內容，請參閱下列章節：

1. **新增帳戶客群**。您可以使用 Journey Optimizer B2B Edition，直接在應用程式中透過區段定義來建立帳戶客群，並在您的帳戶歷程中利用這些客群。[了解更多](../audiences/account-audience-overview.md)

1. **建立購買群組**。定義達成業務目標與目的之關鍵元件，並建立購買群組來確定目標帳戶清單的成員。[了解更多](../buying-groups/buying-groups-overview.md)

1. **建立及管理資產**。Adobe Experience Manager Assets 提供單一的集中式資產存放庫，您可以使用其中資產來填入訊息。[了解更多](../content/assets-overview.md)

1. **新增個人化和動態的電子郵件範本**。利用 Journey Optimizer B2B Edition 個人化及動態內容功能，以便根據客群調整您的訊息內容。[了解更多](../content/email-templates.md)

1. **設計帳戶歷程以便傳遞符合內容情境的個人化體驗**。您可以利用 Journey Optimizer B2B Edition 儲存在事件或資料來源中符合內容情境的資料，建立即時協調流程使用案例。設計由下列功能提供支援的多步驟進階案例：

   * 傳送在收到事件時觸發的即時單一傳遞，或使用 Adobe Experience Platform 客群批次傳遞。

   * 使用各個事件中符合內容情境的資料、來自 Adobe Experience Platform 的資訊，或來自第三方 API 服務的資料。

   * 使用內建管道動作 (電子郵件和 SMS) 傳送在 Journey Optimizer B2B Edition 中設計的訊息。

   * 在歷程圖中，建立多步驟使用案例、新增條件以及傳送個人化訊息。

[了解更多](../journeys/journey-overview.md)

>[!ENDTABS]
