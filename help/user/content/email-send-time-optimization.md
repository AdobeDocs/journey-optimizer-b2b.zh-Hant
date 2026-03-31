---
title: 電子郵件傳送時間最佳化
description: Adobe Journey Optimizer中的傳送時間最佳化(STO)可將個人歷程的電子郵件傳遞個人化。 瞭解如何啟用STO及改善參與。
feature: Person Journeys, Channels
role: User
source-git-commit: 55cfcd3b4ee777ee8945ea9a1cd1429625ee61c3
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# 電子郵件傳送時間最佳化

使用傳送時間最佳化(STO)功能，透過預測每個設定檔最有可能參與的時間，個人化[個人歷程](../journeys/journeys-overview.md)的電子郵件傳送時間。 STO不會使用固定的傳送時間，而是使用歷史電子郵件參與訊號，將每個收件者的傳送排程在最佳時間，藉此提升整體參與。

STO會使用大型語言模型來分析每個設定檔的歷史參與。 它會預測並排名可能的傳送時間，然後在最佳化期間內，以排名最高的時間排程傳送。

## 目前的可用性和範圍

目前支援以下專案的傳送時間最佳化：

* **歷程型別**：人員歷程
* **頻道**：電子郵件
* **組態**： _傳送電子郵件_&#x200B;動作節點
* **報告**：透過歷程可觀察性技能的AI助理

  效能深入分析（例如使用情形、參與提升度，以及STO與非STO的比較）可透過AI Assistant中的自然語言查詢取得。

>[!BEGINSHADEBOX]

已為STO規劃許多&#x200B;**_未來的增強功能_**：

* 支援&#x200B;_帳戶歷程_
* _[!UICONTROL 管理員]_&#x200B;區域中的全域STO設定
* 歷程層級STO啟用
* 可設定的測試/控制拆分
* 專用的STO報告儀表板

>[!ENDSHADEBOX]

## 設定

當您[新增&#x200B;_[!UICONTROL 採取動作]_&#x200B;節點](../journeys/action-nodes.md)至個人歷程時，您可以設定傳送時間最佳化。

1. 針對&#x200B;_[!UICONTROL 選取動作]_，請選擇&#x200B;**[!UICONTROL 傳送電子郵件]**。

1. 使用&#x200B;**[!UICONTROL 傳送時間最佳化]**&#x200B;切換以啟用此功能。

1. 設定STO選項以指定視窗和測試分佈：

   * **[!UICONTROL 下次]**&#x200B;內傳送 — 此值會決定最佳化時段（以天為單位），亦即可以傳遞電子郵件的時間範圍。 例如，對於在五天內進行的網路研討會，您可以設定四或五天的視窗。 STO會為此視窗中的每個設定檔選取最佳預測傳送時間。

   * **STO /固定分佈** - STO會自動建立&#x200B;_測試和控制分割_，以將合格的設定檔分割為最佳化和固定傳送時間。 分割可讓您直接比較效能。 （未來的增強功能預計會允許自訂分割百分比）。

   >[!NOTE]
   >
   >具有強大參與歷程記錄的設定檔會平均分割為控制和測試群組，以測量STO影響。 為了確保統計上可靠的結果，STO與非STO分割的限制在30%到70%之間。 這有助於防止較小的同類群組扭曲結果，並確保進行有意義的比較。

   ![傳送電子郵件歷程節點 — 傳送時間最佳化選項](./assets/email-node-send-time-optimization.png){width="700" zoomable="no"}

1. 直接在&#x200B;_[!UICONTROL 傳送電子郵件]_&#x200B;節點之後，[新增&#x200B;_等待_&#x200B;節點](../journeys/wait-nodes.md)。

   等待節點必須緊跟在啟用STO的電子郵件動作之後。 新增此節點可確保設定檔保留在歷程中，直到完全最佳化視窗被清除且所有STO傳送完成為止。 如果您省略此節點，系統會將設定標示為無效。

1. 在您完成其餘的人員歷程後，請繼續進行[發佈](../journeys/create-publish-journey.md#publish-a-journey)。

## STO深入分析

STO深入分析是透過&#x200B;_AI小幫手_&#x200B;使用Journey Agent [_可觀察性技能_](../agents/journey-agent.md#journey-observability-skill)&#x200B;傳遞。 您可以查詢使用狀況、參與量度、測試/控制結果、節點效能和整體歷程影響。
