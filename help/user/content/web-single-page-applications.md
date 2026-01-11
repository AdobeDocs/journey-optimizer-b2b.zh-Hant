---
title: 單頁應用程式
description: 為單頁應用程式(SPA)建立網站體驗 — 在Journey Optimizer B2B edition中設定檢視追蹤、處理動態內容並管理使用者端導覽。
feature: Channels, Personalization
role: User
badgeBeta: label="Beta" type="informative" tooltip="此功能目前在有限測試版中提供"
source-git-commit: e50b6830736bf763d3aae6a58595e868bbac36e0
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 0%

---

# 單頁應用程式

單頁應用程式(SPA)對網頁個人化提出獨特挑戰，因為它們會動態更新頁面內容，而不會重新載入完整頁面。 Journey Optimizer B2B edition提供專門工具，讓您有效處理SPA個人化。

## 瞭解SPA

傳統多頁網站每次導覽都會觸發完整頁面載入，SPA則不同，SPA會使用JavaScript以動態方式更新內容，同時維持單一HTML頁面。 此方法可為網頁體驗建立數個考量事項：

* **沒有頁面重新載入** — 發生內容變更時，不會觸發傳統的頁面載入事件。
* **虛擬檢視** — 在SPA內需以個別頁面追蹤的不同&#x200B;_檢視_&#x200B;或&#x200B;_熒幕_。
* **使用者端路由** - JavaScript路由器(例如React路由器、Vue路由器和Angular路由器)會處理導覽而非伺服器要求。
* **動態DOM** — 頁面元素可在初始頁面載入後建立、修改或移除。

## 設定SPA支援

為了有效個人化SPA，您需要設定檢視追蹤，以便Journey Optimizer B2B edition能夠識別使用者何時在虛擬檢視之間導覽。

### 設定檢視宣告

請與您的開發團隊合作，使用Adobe Web SDK實作檢視宣告。 使用這些檢視宣告涉及在SPA導覽至新檢視時呼叫包含檢視資訊的`sendEvent`命令。

**實作範例：**

```javascript
// When a new view is rendered in your SPA
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webPageDetails": {
        "viewName": "product-detail",
        "URL": window.location.href
      }
    }
  },
  "data": {
    "__adobe": {
      "target": {
        "viewName": "product-detail"
      }
    }
  }
});
```

### 檢視命名慣例

使用與應用程式邏輯結構相符的一致描述性檢視名稱：

| 檢視 | 範例名稱 |
| ---- | ------------ |
| 首頁 | `home` |
| 產品清單 | `product-list` |
| 產品詳細資料 | `product-detail` |
| 購物車 | `cart` |
| 簽出 | `checkout` |
| 帳戶儀表板 | `account-dashboard` |

>[!NOTE]
>
>檢視名稱區分大小寫。 在您的實施中使用一致的命名慣例（建議使用小寫搭配連字型大小）。

## 建立SPA的網站體驗

建立SPA的Web體驗時，請考慮下列最佳實務：

### Target特定檢視

* 在[網頁通道設定](../admin/configure-channels-web.md)中，設定符合您SPA路由結構的URL比對規則。

* 建立修改時，請指定應套用修改的檢視。

* 使用以每個檢視特定元素為目標的CSS選取器。

### 處理動態內容

SPA通常會在初始頁面轉譯後動態載入內容。 使用這些技巧以確保修改正確套用：

#### 等待元素

設定修改，以等待目標元素存在後再套用：

1. 在非視覺化編輯器中，使用CSS選取器新增修改。

1. 啟用&#x200B;**[!UICONTROL 等候專案]**&#x200B;並指定等候時間上限。

1. 目標元素出現在DOM中後，修改即適用。

#### 使用突變觀察者

針對高度動態內容，Web SDK包含內建的變異觀察者，可偵測何時將新元素新增至頁面。 這些觀察者可確保即使元素非同步載入也會套用修改。

### SPA架構

Journey Optimizer B2B edition Web體驗搭配常用的SPA架構運作：

| 框架 | 考量事項 |
| --------- | -------------- |
| **React** | 在React將元件轉譯為DOM後套用修改。 使用類別名稱或資料屬性來鎖定目標。 |
| **Angular** | Angular的變更偵測執行後的目標元素。 避免在轉譯之前使用`*ngIf`來鎖定目標元素。 |
| **Vue.js** | 等待Vue的`nextTick`，以確定元素位於DOM中。 使用參考或自訂屬性以穩定鎖定目標。 |
| **Next.js / Nuxt.js** | 對於SSR/SSG頁面，在預期修改之前，請確定網頁SDK水合已完成。 |

## SPA個人化的最佳作法

### 使用穩定選擇器

SPA通常會產生動態類別名稱或ID （尤其是使用CSS-in-JS解決方案）。 另外，您也可以使用：

* **資料屬性** — 新增自訂資料屬性（`data-testid`、`data-section`等）至您要鎖定的元素。
* **語意HTML** — 目標以HTML結構和語意元素為基礎。
* **ID屬性** — 儘可能使用穩定識別碼屬性。

**範例：**

```html
<!-- Instead of targeting dynamic class names -->
<button class="css-1a2b3c4d">Sign Up</button>

<!-- Add a stable data attribute -->
<button class="css-1a2b3c4d" data-action="signup">Sign Up</button>
```

**CSS選取器：** `[data-action="signup"]`

### 測試檢視

測試SPA Web體驗時：

1. 瀏覽所有套用修改的檢視。

1. 測試完整的使用者流程，包括：
   * 直接導覽至檢視（深層連結）
   * 從SPA內的其他檢視導覽
   * 瀏覽器前後導覽

1. 確認回到先前造訪的檢視時，修改會重新套用。

### 處理檢視轉變

有些SPA會使用動畫或檢視之間的切換。 請考慮：

* **計時** — 確保在轉換動畫完成之後套用修改。
* **元素可見性** — 元素可能存在，但在轉換期間會隱藏。
* **閃爍** — 請儘早套用修改，以避免可見的內容變更。

## 疑難排解

檢閱SPA設計變更時，請使用下列建議來解決一些常見問題：

* **修改未出現** — 如果修改未出現在您的SPA上：

   1. **檢查檢視追蹤** — 確認`sendEvent`呼叫包含正確的檢視名稱。

   1. **驗證元素是否存在** — 套用修改時，請確定目標元素位於DOM中。

   1. **檢閱選取器** — 確認CSS選取器符合實際的DOM結構。

   1. **檢查主控台** — 尋找可能阻止修改的JavaScript錯誤。

* **短暫出現然後消失的修改** — 此問題通常會在SPA重新呈現並取代修改的元素時發生：

   1. 請使用在轉譯器上保持穩定的更特定CSS選取器。

   1. 啟用變異觀察者，以在重新建立元素時重新套用修改。

   1. 與您的開發團隊合作，將穩定屬性新增至目標元素。

* **重複修改** — 如果修改出現多次：

   1. 核取每個檢視轉變僅引發一次檢視追蹤事件。

   1. 確認修改已限定特定檢視的範圍，而非全域套用。

## 相關主題

* [網站體驗概觀](./web-experiences.md)
* [網站體驗設計](./web-experience-design.md)
* [Web頻道設定](../admin/configure-channels-web.md)