---
title: 分割與合併路徑
description: 瞭解您可以在Journey Optimizer B2B edition中用於協調帳戶歷程的分割路徑和合併路徑節點型別。
feature: Account Journeys
exl-id: 563d6a85-504d-4c70-b075-8a9a9e88bd6b
source-git-commit: 0902e5569847be148bb5037c99cadf0b00c67b8c
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 4%

---

# 分割和合併路徑

在您的帳戶歷程中使用分割和合併路徑節點，以協調您的帳戶歷程。 您可以根據您定義的條件來細分對象，然後組合區段以繼續。

![影片](../../assets/do-not-localize/icon-video.svg){width="30"} [觀看概觀影片](#overview-video)

## 分割路徑

新增&#x200B;_分割路徑_&#x200B;節點以根據帳戶或人員屬性定義一或多個分段路徑。

>[!NOTE]
>
>最多支援25個路徑。

**依帳戶分割路徑**：依帳戶分割的路徑可同時包含帳戶和人員動作與事件。 這些路徑可以進一步分割。

_依帳戶節點分割路徑如何運作？_

* 您新增的每個路徑都包含一個能夠向每個邊緣新增節點的結束節點。
* 依帳號節點分割可以巢狀化 — 您可以重複依帳號分割路徑。
* 評估從上到下的路徑。 如果帳戶符合第一和第二個路徑，則只沿著第一個路徑進行。
* 可使用合併節點來合併兩個或多個路徑。
* 支援&#x200B;_[!UICONTROL 其他帳戶]_&#x200B;路徑的定義，您可以為不符合其中一個已定義區段/路徑的帳戶新增動作或事件。

![歷程節點 — 依帳戶分割路徑](./assets/node-split-paths-account.png){width="700" zoomable="yes"}

**依人員分割路徑**：依人員分割的路徑，且只能包含人員動作。 這些路徑無法再次分割並自動聯結。

_依人員節點分割路徑如何運作？_

* _群組節點_&#x200B;分割合併組合中的函式。 分割路徑會自動合併，以便對象中的所有人能夠前進到下一個步驟，而不會失去其帳戶內容。
* 依人員節點分割無法巢狀化 — 您無法在此群組節點內的路徑中為人員新增分割路徑。
* 評估從上到下的路徑。 如果人員符合第一個和第二個路徑，則他們只會沿著第一個路徑前進。
* 支援使用&#x200B;_帳戶 — 人員關係_，可讓您根據角色範本中定義的角色（例如約聘人員或全職員工）來篩選人員。
* 支援&#x200B;_[!UICONTROL 其他人員]_&#x200B;路徑的定義，您可以為不符合其中一個已定義區段/路徑的人員新增動作或事件。

![歷程節點 — 依人員分割路徑](./assets/node-split-paths-people.png){width="700" zoomable="yes"}

### 路徑條件 {#path-conditions}

| 節點內容 | 路徑條件 | 說明 |
| ------------ | --------------- | ----------- |
| [帳戶](#add-a-split-path-by-account-node) | 帳戶屬性 | 帳戶設定檔中的屬性，包括： <li>年收入</li><li>城市</li><li>國家/地區</li><li>員工人數</li><li>行業</li><li>名稱</li><li>SIC代碼</li><li>狀態</li> |
| | [!UICONTROL 特殊篩選器] > [!UICONTROL 有購買群組] | 帳戶是否擁有購買群組的成員。 也可以根據下列一或多個條件進行評估： <li>解決方案興趣</li><li>購買群組狀態</li><li>完整度分數</li><li>參與分數</li> |
| | [!UICONTROL 特殊篩選器] > [!UICONTROL 有商機] | 帳戶是否與商機相關。 也可以針對下列一或多個機會屬性進行評估： <li>數量<li>結束日期<li>說明<li>預期收入<li>會計季度<li>會計年度<li>預測類別<li>預測類別名稱<li>已結束<li>獲勝</li><li>上次活動日期</li><li>個人來源<li>名稱</li><li>下一步</li><li>機率<li>數量<li>階段</li><li>類型 |
| [人員](#add-a-split-path-by-people-node) >僅[!UICONTROL 人員屬性] | [!UICONTROL 個人屬性] | 個人設定檔中的屬性，包括： <li>城市</li><li>國家/地區</li><li>出生日期</li><li>電子郵件地址</li><li>電子郵件無效</li><li>電子郵件已暫停</li><li>名字</li><li>推斷的狀態區域</li><li>職稱</li><li>姓氏</li><li>行動電話號碼</li><li>電話號碼</li><li>郵遞區號</li><li>狀態</li><li>退訂</li><li>取消訂閱的原因</li> |
| | [!UICONTROL 活動歷史記錄] > [!UICONTROL 電子郵件] | 與歷程相關聯的電子郵件活動： <li>[!UICONTROL 已點按電子郵件中的連結]</li><li>已開啟的電子郵件</li><li>已傳遞電子郵件</li><li>已傳送電子郵件</li> 會使用歷程中先前選取的電子郵件訊息評估這些條件。 |
| | [!UICONTROL 活動歷史記錄] > [!UICONTROL 資料值已變更] | 針對選取的人員屬性，發生值變更。 這些變更型別包括： <li>新值</li><li>上一個值</li><li>原因</li><li>來源</li><li>活動日期</li><li>最低 次數</li> |
| | [!UICONTROL 活動歷史記錄] > [!UICONTROL 有趣的時刻] | 在關聯的Marketo Engage例項中定義的有趣時刻活動。 限制包括： <li>里程碑</li><li>電子郵件</li><li>網頁</li> |
| | [!UICONTROL 特殊篩選器] > [!UICONTROL 購買團體成員] | 該人員是或不是根據下列一或多個條件評估的購買群組成員： <li>解決方案興趣</li><li>購買群組狀態</li><li>完整度分數</li><li>參與分數</li><li>角色</li> |
| | [!UICONTROL 特殊篩選器] > [!UICONTROL 清單成員] | 此人是否為一或多個Marketo Engage清單的成員。 |
| | [!UICONTROL 特殊篩選器] > [!UICONTROL 計畫成員] | 此人是否為一或多個Marketo Engage方案的成員。 |
| [People](#add-a-split-path-by-people-node) >僅[!UICONTROL Account-person屬性] | 帳戶屬性中的角色 | 此人是否在帳戶中被指派角色。 選擇性限制： <li>輸入角色名稱</li> |

<!-- 

Add back for next release:

People:

| | [!UICONTROL Activity history] > [!UICONTROL SMS Message] | SMS activities associated with the journey: <li>[!UICONTROL Clicked link in SMS]</li><li>[!UICONTROL SMS Bounced]</li>These conditions are evaluated using a selected SMS message from earlier in the journey.  |

-->

### 依帳戶節點新增分割路徑

1. 導覽至歷程編輯器。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 分割路徑]**。

   ![新增歷程節點 — 分割路徑](./assets/add-node-split.png){width="300"}

1. 在右側的節點屬性中，選擇&#x200B;**[!UICONTROL 帳戶]**&#x200B;進行分割。

1. 若要定義適用於&#x200B;_[!UICONTROL 路徑1]_&#x200B;的條件，請按一下&#x200B;**[!UICONTROL 套用條件]**。

   ![分割路徑節點 — 新增條件](./assets/node-split-properties-apply-condition.png){width="500"}

1. 在條件編輯器中，新增一或多個篩選器以定義分割路徑。

   * 從左側導覽拖放篩選器屬性，並完成比對定義。

   * 在上方套用&#x200B;**[!UICONTROL 篩選邏輯]**，微調條件。 您可以選擇符合所有屬性條件或任何條件。

     ![分割路徑節點 — 條件帳戶篩選邏輯](./assets/node-split-conditions-accounts.png){width="700" zoomable="yes"}

   * 按一下&#x200B;**[!UICONTROL 「完成」]**。

1. 若要新增更多路徑，請按一下[新增路徑] ****，並重複先前步驟以新增適用於此路徑的條件。

   您也可以根據這些條件來標示每個路徑，或使用預設標籤。

1. 如有需要，請根據您想要分割的優先順序來重新排序路徑。

   路徑篩選是以由上到下的順序評估。 每個帳戶都會沿著第一個相符的路徑進行。

   按一下每個路徑卡片右上角的向上和向下箭頭，將其在路徑清單中向上或向下移動。

   ![分割路徑節點 — 重新排序路徑](./assets/node-split-reorder-paths-accounts.png){width="500" zoomable="yes"}

1. 啟用&#x200B;**[!UICONTROL 其他帳戶]**&#x200B;選項，為不符合所定義區段/路徑的帳戶定義預設路徑。

   未啟用此選項時，歷程會針對不符合分割內已定義區段/路徑的帳戶結束。

### 依人員節點新增分割路徑

>[!NOTE]
>
>依人員分割路徑時，會自動插入&#x200B;_封閉分割路徑_&#x200B;節點以結束分割。 依人員分割的路徑只允許對人員節點&#x200B;_執行動作_。

1. 導覽至歷程編輯器。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 分割路徑]**。

   ![新增歷程節點 — 分割路徑](./assets/add-node-split.png){width="300"}

1. 在右側的節點屬性中，選擇&#x200B;**[!UICONTROL 人員]**&#x200B;進行分割。

1. 設定用於條件&#x200B;]**的**[!UICONTROL &#x200B;屬性。

   * 選擇&#x200B;**[!UICONTROL 僅人員屬性]**&#x200B;以使用與人員設定檔和事件相關的條件。
   * 選擇&#x200B;**[!UICONTROL 僅限帳號 — 個人屬性]**&#x200B;以使用帳號中與個人角色成員資格相關的條件。

1. 若要定義適用於&#x200B;_[!UICONTROL 路徑1]_&#x200B;的條件，請按一下&#x200B;**[!UICONTROL 套用條件]**。

1. 在條件編輯器中，新增一或多個篩選器以定義分割路徑。

   * 從左側導覽拖放任何人員屬性，並完成比對定義。

     >[!NOTE]
     >
     >如果您在Experience Platform的帳戶對象結構描述中定義了自訂人員欄位，這些欄位也可在條件中作為人員屬性使用。

   * 在上方套用&#x200B;**[!UICONTROL 篩選邏輯]**，微調條件。 您可以選擇符合所有屬性條件或任何條件。

     ![分割路徑節點 — 條件人員篩選邏輯](./assets/node-split-conditions-people.png){width="700" zoomable="yes"}

   * 按一下&#x200B;**[!UICONTROL 「完成」]**。

1. 若要新增更多路徑，請按一下[新增路徑] ****，並重複先前步驟以新增適用於此路徑的條件。

   您也可以根據這些條件來標示每個路徑，或使用預設標籤。

1. 如有需要，請根據您想要分割的優先順序來重新排序路徑。

   路徑篩選是以由上到下的順序評估。 每個人都會沿著第一個符合的路徑前進。

   按一下每個路徑卡片右上角的向上和向下箭頭，將其在路徑清單中向上或向下移動。

   ![分割路徑節點 — 重新排序路徑](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"}

1. 啟用&#x200B;**[!UICONTROL 其他人]**&#x200B;選項，為不符合所定義路徑的人新增預設路徑。

   未啟用此選項時，不符合已定義區段/路徑的人員會經過分割，並繼續歷程中的下一個步驟。

>[!BEGINSHADEBOX 「Marketo Engage清單成員資格」]

在Marketo Engage中，_智慧行銷活動_&#x200B;會檢查方案成員資格，以確保潛在客戶不會收到重複的電子郵件，而且不會同時成為多個電子郵件串流的成員。 在Journey Optimizer B2B中，您可以檢查Marketo Engage清單成員資格，並以此作為依人員分割路徑的條件，以協助消除歷程活動中的重複。

若要在分割條件中使用清單成員資格，請展開&#x200B;**[!UICONTROL 特殊篩選器]**，並將&#x200B;**[!UICONTROL 清單成員]**&#x200B;條件拖曳到篩選器空間。 完成篩選器定義以評估一或多個Marketo Engage清單中的成員資格。

![依人員條件分割Marketo Engage清單成員資格的路徑](./assets/node-split-paths-conditions-people-member-of-list.png){width="700" zoomable="yes"}

>[!ENDSHADEBOX]

當您針對在人員層級上分割對象的每個路徑定義條件時，您可以新增要對人員採取的動作。

>[!NOTE]
>
>依人員分割對象時，您只能新增人員動作，直到路徑關閉或合併為止。

## 合併路徑

新增&#x200B;_合併路徑_&#x200B;節點以在您的歷程中依帳戶結合不同的分割路徑。

1. 導覽至歷程編輯器。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 分割路徑]**。

1. 按一下分割節點以開啟其右側屬性。

1. 按一下[!UICONTROL 新增路徑]以建立三個路徑。

1. 將動作和事件的組合新增至每個路徑。

1. 按一下任一路徑的加號( **+** )圖示，然後從顯示的選項中選擇&#x200B;**[!UICONTROL 合併]**。

   ![歷程節點 — 合併路徑](./assets/node-plus-icon-merge-paths.png){width="400"}

1. 在合併路徑節點屬性中，選取您要合併的路徑。

   ![歷程節點 — 合併路徑](./assets/node-merge-select-paths.png){width="600" zoomable="yes"}

   此時，路徑會合併，以便來自所選路徑的帳戶合併為單一路徑，繼續完成歷程。

1. 如有需要，您可以導覽回合併路徑節點屬性，並清除您要移除之任何路徑的核取方塊，以取消合併路徑。

## 概觀影片

>[!VIDEO](https://video.tv.adobe.com/v/3443231/?learn=on)
