---
title: 測試電子郵件呈現
description: 透過Litmus整合，跨案頭、行動和Web使用者端測試電子郵件呈現，以確保Journey Optimizer B2B edition中的收件匣相容性。
feature: Email Authoring, Integrations
level: Intermediate
role: User
exl-id: 26d87a56-6bd1-4d4a-8090-71f5b0a7e9f8
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: c8f3fb27-3167-48ac-a66a-fa4bc3f58ddaid: f01b5556-e951-40ba-8625-2e3001864f2bid: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: cad51180-f8ce-4cb7-aefc-437847b5d6d6
autotag-review: '2026-03-30T22:28:13.343Z'
source-git-commit: 8fe8318d7e1c63cbaa2749fc3928eb0a12967bd9
workflow-type: tm+mt
source-wordcount: 376
ht-degree: 2%

---

# 使用 Litmus 測試電子郵件轉譯

若要測試您的電子郵件，您可以利用Journey Optimizer B2B edition的[Litmus](https://www.litmus.com/email-testing){target="_blank"}企業帳戶。 透過這項整合，您可以在常用的電子郵件使用者端中預覽電子郵件呈現。 此工具可協助您確保電子郵件內容看起來不錯，並在每個收件匣中依設計運作。

>[!AVAILABILITY]
>
>這項整合僅適用於擁有Litmus Enterprise帳戶的Journey Optimizer B2B edition使用者。 如需詳細資訊，請參閱Litmus網站](https://www.litmus.com/solutions/esp/adobe-journey-optimizer){target="_blank"}上的[解決方案頁面。

1. 當您的電子郵件設計完成並準備好進行測試時，請在電子郵件設計空間按一下&#x200B;**[!UICONTROL 模擬內容]**。

1. 按一下右上角的&#x200B;**[!UICONTROL 轉譯電子郵件]**。

   ![轉譯電子郵件按鈕](./assets/email-simulate-render-button.png){width="700" zoomable="yes"}

   如果您尚未從Journey Optimizer B2B edition連線至您的Litmus帳戶，則顯示的頁面會提供啟動試用帳戶或連線至現有帳戶的選項。

1. 按一下右上角的&#x200B;**[!UICONTROL 連線您的Litmus帳戶]**，或使用頁面內的連結。

   ![連線您的Litmus帳戶](./assets/email-simulate-render-litmus-connect.png){width="700" zoomable="yes"}

1. 輸入您的Litmus帳戶認證，然後按一下&#x200B;**[!UICONTROL 登入]**。

1. 按一下「**[!UICONTROL 連線]**」以確認Litmus與Journey Optimizer B2B edition之間的連線，並傳送電子郵件內容以進行呈現。

   >[!IMPORTANT]
   >
   >將Litmus帳戶與Journey Optimizer B2B edition連線時，您同意將測試訊息傳送至Litmus。 然後，此內容會由Litmus管理，而非Adobe。 因此，Litmus資料保留電子郵件原則會套用至這些電子郵件，包括可能包含在測試訊息中的個人化資料。

1. 按一下右上角的&#x200B;**[!UICONTROL 執行測試]**&#x200B;以產生電子郵件預覽。

   ![執行Litmus演算測試](./assets/email-simulate-render-litmus-run-test.png){width="700" zoomable="yes"}

1. 在熱門的桌上型電腦、行動裝置和網頁型使用者端中檢查您的電子郵件內容。

   按一下顯示的縮圖可檢視任何演算後使用者端測試的詳細資料。

   ![Litmus電子郵件預覽](./assets/email-simulate-render-litmus-previews.png){width="700" zoomable="yes"}

1. 當您完成檢閱時，請按一下左上方的向後箭頭（ ![顯示或隱藏篩選器圖示](../../assets/do-not-localize/icon_back-arrow.svg) ）以返回「模擬內容」頁面。

   您可以選取其他設定檔並執行另一個演算測試，或返回電子郵件設計空間根據您的稽核進行任何需要的調整。
