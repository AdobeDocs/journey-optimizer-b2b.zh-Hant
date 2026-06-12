---
title: 新增歷程節點
description: 個人歷程節點的預留位置頁面。
source-git-commit: 2f19137465c71f2292d37bea5786533b1df6e286
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 2%

---

# 新增歷程節點

建立人員歷程後，新增對象並使用節點建置歷程。 歷程地圖提供畫布，您可以在其中建立多步驟B2B行銷使用案例。

_[!UICONTROL 個人對象]_&#x200B;節點會自動成為歷程中的第一個節點。 選取對象後，將不同的動作、事件和設計節點視為多步驟、跨管道情境，結合以建立您的歷程。 歷程的每個節點代表邏輯路徑上的一個步驟。

## 個人受眾節點

「人員」對象節點會指定哪些人員記錄進入歷程。 當您建立個人歷程時，歷程一律以定義其輸入的個人受眾節點開始。

1. 按一下節點加以選取。
1. 在右側的節點屬性面板中，對「人員」對象歷程節點使用下列其中一個輸入選項：

   * **[!UICONTROL 動態清單]** — 使用以規則為基礎的動態人員清單。 清單規則會在歷程執行階段進行評估，以符合歷程成員的資格。 之後不符合動態清單資格的人不會從歷程中移除。

   * **[!UICONTROL 靜態清單]** — 使用靜態人員清單作為歷程的成員。 目前清單成員資格會在歷程執行階段進行評估，以符合歷程成員的資格。 之後從靜態清單中移除的人員不會從歷程中移除。

## 人員動作節點

在人員歷程中，當您想要將變更套用至節點路徑上的所有人員時，可對人員使用動作。 對於帳戶歷程，此節點型別可用於依人員分割路徑或依帳戶分割路徑。

### 動作和限制

| 動作 | 限制 |
| ------ | ---------- |
| **[!UICONTROL 傳送電子郵件]** | <li>建立電子郵件 <li>傳送時間最佳化（選擇性） |
| **[!UICONTROL 變更資料值]** | <li>選取人員屬性 <li>設定新值 |

### 新增動作節點

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 執行動作]**。

1. 在右側的節點屬性中，從清單中選取動作，並設定該動作的任何值。

<!-- ![Person journey node - take an action](./assets/node-take-action-people.png){width="700" zoomable="yes"} -->

+++[!UICONTROL 傳送電子郵件]

使用此動作傳送電子郵件。 建立節點的電子郵件之後，您可以在電子郵件設計空間設計、個人化和預覽電子郵件訊息（請參閱[電子郵件編寫](../content/email-authoring.md)）。

<!-- ![Take an action - Send email](./assets/node-action-send-email-from-marketo.png){width="300"} -->

您可以使用[傳送時間最佳化](../marketing/email-send-time-optimization.md)，透過預測每個設定檔最有可能參與的時間來個人化電子郵件傳遞時間。

<!--
>[!NOTE]
>
>You can use email deduplication in account journeys to ensure that the same email is not sent multiple times to the same email address within a journey. For more information, see [Email deduplication](../content/email-deduplication.md).
-->

+++

+++[!UICONTROL 變更資料值]

使用此動作來變更資料庫中人員設定檔屬性的值。 選取屬性，然後設定新值。

<!-- ![Take an action - Update person profile](./assets/node-action-update-person-profile.png){width="300"} -->

+++

## 事件節點

新增&#x200B;_接聽事件_&#x200B;節點，以便在事件發生時，將您的對象移至歷程的下一個步驟。

### 人員事件篩選器

| 篩選器 | 說明 |
| ------- | ----------- |
| 活動歷史記錄>電子郵件 | 根據使用一或多封所選電子郵件訊息評估的條件，以電子郵件活動為基礎： <li>電子郵件中已點選的連結 <li>開啟電子郵件 |
| 活動歷史記錄>資料值已變更 | 針對選取的人員屬性，發生值變更。 這些變更型別包括： <li>新值 <li>上一個值 <li>原因 <li>來源 <li>活動日期 <li> 最低 次數 |

### 新增事件節點

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

1. 在右側的節點屬性中，選擇事件型別的&#x200B;**[!UICONTROL 人員]**。

   <!-- ![Journey node - listen to events on people](./assets/node-listen-events-people.png){width="700" zoomable="yes"} -->

1. 從清單中選取事件。

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的詳細資料。

>[!NOTE]
>
>監聽事件節點的逾時功能目前無法運作，將於稍後階段啟用。

## 分割路徑節點

使用分割節點，根據您定義的條件來劃分人員。 根據條件建立對象清單的路徑，使用區段的動作和事件節點定義每個路徑，然後組合路徑並繼續歷程。

「分割路徑」節點會根據人員篩選器定義一或多個分段路徑。

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->


_&#x200B;**依人員節點分割路徑的運作方式**&#x200B;_

* 每個路徑的評估方式都是從上到下。 如果人員符合第一個和第二個路徑，則他們只會沿著第一個路徑前進。
* 此節點支援&#x200B;_其他人_&#x200B;路徑的定義，您可以在此為不符合其中一個已定義區段/路徑的人員新增動作或事件。

### 相符的篩選器

對於您為節點定義的每個路徑，請使用下列篩選器型別，根據一或多個條件來比對人員：

* 活動歷史記錄 — 您可以根據與以下專案相關的人員活動來定義路徑：

   * 電子郵件訊息
   * 資料值變更

* 個人屬性 — 根據個人的屬性定義條件，例如國家、職稱或清單會籍。

### 新增分割路徑節點

<!--
>[!NOTE]
>
>When you split paths by people, a _Close split paths_ node is automatically inserted to end the split. A split-by-people path allows only _Take an action_ on people nodes.
-->

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 分割路徑]**。

   <!-- ![Add journey node - split paths](./assets/add-node-split.png){width="300" zoomable="no"} -->

1. 若要定義適用於&#x200B;_[!UICONTROL 路徑1]_&#x200B;的條件，請按一下&#x200B;**[!UICONTROL 套用條件]**。

1. 在條件編輯器中，新增一或多個篩選器以定義分割路徑。

   * 從左側導覽拖放任何人員篩選器，並完成相符定義。

   * 在上方套用&#x200B;**[!UICONTROL 篩選邏輯]**，微調條件。 您可以選擇符合所有條件或任一條件。

     <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

   * 按一下「**[!UICONTROL 完成]**」。

1. 若要新增更多路徑，請按一下[新增路徑] **&#x200B;**，並重複上述步驟以新增適用於路徑的條件。

   您也可以根據這些條件來標示每個路徑，或使用預設標籤。

1. 如有需要，請根據您想要分割的優先順序來重新排序路徑。

   路徑篩選是以由上到下的順序評估。 每個人都會沿著第一個符合的路徑前進。

   按一下每個路徑卡片右上角的向上和向下箭頭，將其在路徑清單中向上或向下移動。

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. 啟用&#x200B;**[!UICONTROL 其他人]**&#x200B;選項，為不符合所定義路徑的人新增預設路徑。

   未啟用此選項時，不符合已定義區段/路徑的訪客會經過分割，繼續歷程的下一個步驟。

為每個路徑定義條件後，您可以新增要套用至路徑上人員的動作或事件節點。

## 合併路徑節點

1. 導覽至歷程圖，並找出具有兩個或多個路徑的分割路徑節點。

   每個路徑都應該有動作和事件的組合。

1. 按一下任一路徑結尾的加號( **+** )圖示，然後從顯示的選項中選擇&#x200B;**[!UICONTROL 合併路徑]**。

   <!-- ![Journey node - merge paths](./assets/node-plus-icon-merge-paths.png){width="400" zoomable="no"} -->

1. 在右側的節點屬性中，選取您要合併的路徑。

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   此時，路徑會合併，以便來自所選路徑的人合併成單一路徑，繼續完成歷程。

1. 如有需要，您可以導覽回合併路徑節點屬性，並清除您要移除之任何路徑的核取方塊，以取消合併路徑。
