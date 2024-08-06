---
title: Adobe Journey Optimizer B2B版本概觀
description: 探索 Adobe Journey Optimizer B2B 版主要功能、使用案例和架構。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
source-git-commit: 78d82aa8b3bb8b8d432eeb187d75e2354dbff3ee
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 1%

---

# Adobe Journey Optimizer B2B版本概觀

透過Adobe Journey Optimizer B2B Edition，您可以使用內建的創作AI和領先業界的自動化功能，透過符合行銷資格的購買群組，協調帳戶和購買群組歷程，以最大化特定產品的需求。

## 購買群組的帳戶歷程

將Adobe Journey Optimizer B2B Edition與Marketo Engage和Adobe Journey Optimizer Standard進行比較時，關鍵的區別在於帳戶歷程會透過Journey移動帳戶，而非人員。 與帳戶相關聯的個人最有可能具有非線性進展（根據帳戶整個歷程的進度，而不是根據其個別動作）。 例如，當帳戶處於購買歷程的早期階段時，傳送的資訊可能會有關一般解決方案功能或特性。 在購買過程中，內容可能會變得更加針對特定優惠或其他旨在結束銷售的專案。 購買解決方案後，資訊可能會再次變更，以提供操作指南、最佳實務、或有關即將舉辦之活動的資訊，或有關其他追加銷售的內容。 即使個人尚未與早期階段內容互動，您仍希望根據他們自己的動作，而不是根據其帳戶或購買群組中的其他人的動作，將其推進到目前階段。

## 高階架構

Adobe Journey Optimizer B2B Edition使用Adobe Experience Platform中的&#x200B;_帳戶對象_&#x200B;和帳戶的&#x200B;_人員對象_&#x200B;來推動在Marketo Engage內執行的帳戶歷程。 Experience Platform一律是這些資料的真實來源，但帳戶歷程的所有執行和處理都發生在Marketo EngageB2B行銷基礎結構內。 協調流程透過現有的Marketo Engage- Adobe Real-Time CDP B2B Edition來源聯結器，近乎即時地將資料帶回Experience Platform，這會串流不同Marketo Engage的資料變更Experience Platform。

![高階資料架構](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

### 訂閱模式

Journey Optimizer B2B Edition訂閱是由具有Marketo Engage _munchkin_&#x200B;訂閱的一對Experience Platform(AEP)沙箱所定義。 單一Marketo Engage訂閱無法與多個AEP沙箱配對。 如果您未選擇搭配Journey Optimizer B2B Edition使用現有的Marketo Engage訂閱，或您目前未使用Marketo Engage，則會為您布建新的空白Marketo Engage訂閱，以便搭配Journey Optimizer B2B Edition使用。

在此設定中Experience Platform的目的是提供來自Marketo Engage執行個體（以及任何附加的CRM系統）的資料的統一檢視，然後能夠使用帳戶歷程對統一資料採取行動。

### 帳戶歷程作業

帳戶歷程是在Journey Optimizer B2B Edition中撰寫，並儲存在與訂閱相關聯的Marketo Engage執行個體中。 雖然它儲存在Marketo Engage資料存放區中，但無法從Marketo EngageUI中看見，而且只能從Journey Optimizer B2B Edition中使用。

帳戶歷程一律以選取要作為歷程帳戶對象的帳戶區段開始。 選取對象時會使用標準Experience Platform對象選擇器元件。 行銷人員隨後可透過根據自己的條件分割歷程路徑來實施帳戶歷程，該條件可包括帳戶條件、人員條件或購買群組條件。 在每個分支上，可以採取動作來實施歷程，例如傳送電子郵件或等待事件發生。

建立帳戶歷程後，必須發佈歷程。 在發佈時，帳戶歷程經過驗證，並轉換為實作歷程體驗的一系列Marketo Engage行銷活動，接著會聯絡資料整合服務以啟動資料流程，接著啟動帳戶歷程作業。 第一步是為帳戶的使用者建立區段。

### 資料流程

Journey Optimizer B2B Edition使用Real-Time CDP帳戶區段來定義和執行帳戶區段，以及歷程所需的相關帳戶個人區段。 隨著已發佈的歷程執行，有關人員和帳戶的資料可能會變更，並且會收集與歷程互動之人員的資料。 Journey Optimizer B2B Edition仰賴Real-Time CDP B2B Edition的Marketo Engage來源聯結器將資料變更流回Experience Platform沙箱，這是事實來源。  此資料會以幾近即時的方式傳送至AEP。

只有Marketo Engage來源聯結器支援的現有資料型別（帳戶、人員和機會）會回到Real-Time CDP。 這表示購買群組資料不會流入AEP，而是位於Journey Optimizer B2B Edition訂閱所使用的Marketo Engage例項中。
