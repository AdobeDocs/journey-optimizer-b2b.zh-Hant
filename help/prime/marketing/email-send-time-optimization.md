---
title: 電子郵件傳送時間最佳化
description: Adobe Journey Optimizer B2B Prime中的傳送時間最佳化(STO)可將人員歷程的電子郵件傳遞個人化。 瞭解如何啟用STO及改善參與。
autotag-review: '2026-06-17T20:52:02.535Z'
TQID: 'https://experienceleague.adobe.com/wlxhS7E8DnbThm5ge-wzTkMcn-eBzFUXfw3ZGrfcRHA'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: bef5003b-cad2-4f40-bdb2-a80426d52ef5id: f01b5556-e951-40ba-8625-2e3001864f2bid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1fid: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
source-git-commit: 951d9ceaa95656952e36b6d8f238348b08c796ca
workflow-type: tm+mt
source-wordcount: 403
ht-degree: 0%

---

# 電子郵件傳送時間最佳化

使用傳送時間最佳化(STO)功能，透過預測每個設定檔最有可能參與的時間，個人化[個人歷程](./person-journeys.md)的電子郵件傳送時間。 STO不會使用固定的傳送時間，而是使用歷史電子郵件參與訊號，將每個收件者的傳送排程在最佳時間，藉此提升整體參與。

STO會使用大型語言模型來分析每個設定檔的歷史參與。 它會預測並排名可能的傳送時間，然後在最佳化期間內，以排名最高的時間排程傳送。

<!-- Performance insights, such as usage, engagement lift, and STO vs. non-STO comparisons, are available through natural language queries in the AI Assistant. -->

>[!BEGINSHADEBOX]

已為STO規劃許多&#x200B;**_未來的增強功能_**：

* _[!UICONTROL 管理員]_&#x200B;區域中的全域STO設定
* 歷程層級STO啟用
* 可設定的測試/控制拆分

>[!ENDSHADEBOX]

## 設定 {#configuration}

當您[新增&#x200B;_[!UICONTROL 採取動作]_&#x200B;節點](./action-nodes.md)至個人歷程並選擇&#x200B;**[!UICONTROL 傳送電子郵件]**&#x200B;動作時，您可以設定傳送時間最佳化。

1. 選取&#x200B;_傳送電子郵件_&#x200B;歷程動作節點。

1. 在右側的節點屬性中，啟用&#x200B;**[!UICONTROL 傳送時間最佳化]**&#x200B;選項。

   ![傳送電子郵件歷程節點 — 傳送時間最佳化選項](./assets/email-node-send-time-optimization.png){width="450" zoomable="no"}

1. 若要指定視窗和測試分佈，請設定STO選項：

   * **[!UICONTROL 下次]**&#x200B;內傳送 — 此值會決定最佳化時段（以天為單位），亦即可以傳遞電子郵件的時間範圍。 例如，對於在五天內進行的網路研討會，您可以設定四或五天的視窗。 STO會為此視窗中的每個設定檔選取最佳預測傳送時間。

   * **STO /固定分佈** - STO會自動建立&#x200B;_測試和控制分割_，以將合格的設定檔分割為最佳化和固定傳送時間。 分割可讓您直接比較效能。 （未來的增強功能預計會允許自訂分割百分比）。

   >[!NOTE]
   >
   >具有強大參與歷程記錄的設定檔會平均分割為控制和測試群組，以測量STO影響。 為了確保統計上可靠的結果，STO與非STO分割的限制在30%到70%之間。 這有助於防止較小的同類群組扭曲結果，並確保進行有意義的比較。

1. 直接在&#x200B;_[!UICONTROL 傳送電子郵件]_&#x200B;節點之後，[新增&#x200B;_等待_&#x200B;節點](./wait-nodes.md)。

   等待節點必須緊跟在啟用STO的電子郵件動作之後。 新增此節點可確保設定檔保留在歷程中，直到完全最佳化視窗被清除且所有STO傳送完成為止。 如果您省略此節點，系統會將設定標示為無效。

1. 在您完成其餘的人員歷程後，請繼續進行[發佈](./person-journeys.md#publish)。

## 報告


