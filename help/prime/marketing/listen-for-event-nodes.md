---
title: 接聽事件節點
description: 預留位置
autotag-review: '2026-06-12T23:00:36.531Z'
TQID: 'https://experienceleague.adobe.com/SBEfrrIKSCnO5x1tGXQTz1EZryH0IKhQx4tuqVn78FI'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d0031543-532c-4a26-8f90-01af2b91e6d0
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: bf2854a777f62ba2f74f79942ee3336b6e8ab9dd
workflow-type: tm+mt
source-wordcount: 165
ht-degree: 10%

---

# 接聽事件節點

新增&#x200B;_接聽事件_&#x200B;節點，以便在事件發生時，將您的對象移至歷程的下一個步驟。

## 人員事件篩選器

| 篩選器 | 說明 |
| ------- | ----------- |
| 活動歷史記錄>電子郵件 | 根據使用一或多封所選電子郵件訊息評估的條件，以電子郵件活動為基礎： <li>電子郵件中已點選的連結 <li>開啟電子郵件 |
| 活動歷史記錄>資料值已變更 | 針對選取的人員屬性，發生值變更。 這些變更型別包括： <li>新值 <li>上一個值 <li>原因 <li>來源 <li>活動日期 <li> 最低 次數 |

## 新增事件節點

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

1. 在右側的節點屬性中，選擇事件型別的&#x200B;**[!UICONTROL 人員]**。

   <!-- ![Journey node - listen to events on people](./assets/node-listen-events-people.png){width="700" zoomable="yes"} -->

1. 從清單中選取事件。

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的詳細資料。

>[!NOTE]
>
>監聽事件節點的逾時功能目前無法運作，將於稍後階段啟用。
