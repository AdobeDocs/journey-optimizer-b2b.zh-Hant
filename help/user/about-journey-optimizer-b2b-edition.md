---
title: Adobe Journey Optimizer B2B Edition 概觀
description: 了解 Adobe Journey Optimizer B2B Edition：透過購買群組、AI 洞察及 Experience Platform 整合來協調帳戶歷程，以進行 B2B 行銷。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
autotag-review: 2026-04-29T23:21:13.339Z
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: f467931a-9b22-4ca8-869f-adfbd64061ce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
TQID: https://experienceleague.adobe.com/L58cK4MP-S-8U9fFiXU2qZn4HCieNzjoOaSRCLkyanI
source-git-commit: 8d2fc3ebc7df1674ac9af441679228a9e19d8d5a
workflow-type: tm+mt
source-wordcount: 739
ht-degree: 15%

---

# Adobe Journey Optimizer B2B Edition 概觀

透過Adobe Journey Optimizer B2B edition，您可以使用內建的創作AI和領先業界的自動化功能，透過符合行銷資格的購買群組，協調人員和帳戶歷程，以最大化特定產品的需求。

## 使用購買群組的帳戶歷程

將帳戶歷程與Marketo Engage和Adobe Journey Optimizer standard中的歷程功能進行比較時，主要區別在於帳戶歷程會透過歷程移動帳戶，而非人員。 與某個帳戶關聯的人員，其歷程通常不會線性發展，而是取決於該帳戶在整個歷程中的進度，而非人員的個別動作。 例如，當帳戶處於購買歷程的早期階段時，傳送的資訊通常會是關於一般解決方案功能或功能的。 在購買過程中，內容會更針對特定優惠方案或旨在結束銷售的其他專案。 購買解決方案後，資訊會再次變更，以提供操作指南、最佳實務、有關即將舉辦活動的資訊，或有關其他追加銷售的內容。 即使個人尚未與早期階段內容互動，您仍可以根據其帳戶或購買群組內其他人的動作，將其推進至目前階段。

## 高階架構

Adobe Journey Optimizer B2B edition是以Adobe Experience Platform為基礎，包括Real-Time CDP B2B。 Journey Optimizer B2B edition和Marketo Engage會在不同的系統上執行，每個系統都有自己的資料存放區。 Experience Platform是帳戶、人員和機會的主要資料存放區和權威來源。 Journey Optimizer B2B edition擁有您的帳戶歷程、購買群組，以及購買群組角色。

專用的Marketo Engage執行個體支援每個Journey Optimizer B2B edition訂閱。 此例項不會儲存您的帳戶歷程、對象或購買群組。 而是提供許可權和後端服務，例如電子郵件傳送、寄件者設定和品牌化網域。

若要支援歷程動作，您也可以連線一或多個現有的Marketo Engage執行個體，包括生產執行個體。 歷程動作可讓行銷人員協調Journey Optimizer B2B edition中的帳戶型歷程與Marketo Engage中的潛在客戶型行銷活動，例如將人員新增至清單或請求行銷活動。 [進一步瞭解如何連線Marketo Engage執行個體](./admin/marketo-actions-connect.md)。

![高階資料架構，顯示連線至Adobe Experience Platform的Journey Optimizer B2B edition做為帳戶和人員對象真實來源的資料架構、提供權益和後端服務的專用Marketo Engage執行個體，以及用來執行歷程動作的選用生產Marketo Engage執行個體。](./assets/high-level-data-architecture.png){zoomable="yes"}

>[!NOTE]
>
>檢查您的授權權益和對應的[產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}，以取得效能護欄和靜態限制。

### 訂閱模型

Experience Platform沙箱與專用的Marketo Engage執行個體配對，可定義Journey Optimizer B2B edition訂閱。 此專用執行個體與您的生產Marketo Engage執行個體不同，其存在是為了支援權益和後端服務，而不是儲存帳戶歷程資料。 [進一步瞭解設定](./setup-ultimate.md)。

Experience Platform可讓您從連線的Marketo Engage執行個體和CRM系統中，以統一檢視資料。 使用該統一資料來建置和執行您的歷程。

### 歷程操作

Journey Optimizer B2B edition會建立、儲存和執行您的帳戶歷程。 帳戶歷程未出現在Marketo Engage中，僅可在Journey Optimizer B2B edition中使用。

歷程一律以符合潛在客戶或帳戶資格的受眾及其人員開始。 使用標準Experience Platform對象選擇器選取此對象。 行銷人員使用帳戶條件、人員條件或購買群組條件來分割路徑，以實施歷程。 在每個路徑上，動作會傳送通訊或等待事件發生。

建立帳戶歷程後，請發佈該歷程，讓歷程上線。 符合資格的帳戶會在24小時內進入已發佈的歷程。

### 資料流

Journey Optimizer B2B edition可當作Adobe Real-Time CDP B2B edition目的地使用。 使用Real-Time CDP帳戶細分來建置和評估帳戶對象，以及符合帳戶和人員歷程資格的人員對象。 當您發佈歷程時，Journey Optimizer B2B edition會從Experience Platform啟用合格對象。

購買群組、購買群組角色和購買群組分數會建立並儲存在Journey Optimizer B2B edition中。 [進一步瞭解購買群組](./buying-groups/buying-groups-overview.md)。
