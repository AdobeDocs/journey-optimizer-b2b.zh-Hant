---
title: 登陸頁面
description: 建立、設計和發佈個人歷程的登陸頁面 — 從頭開始建立、匯入HTML、新增表單、個人化內容，以及從Journey Optimizer B2B Prime中的電子郵件連結。
autotag-review: '2026-06-12T22:53:39.337Z'
TQID: 'https://experienceleague.adobe.com/BvtB0i5CzlVutPA6HAzZy-Gfymw7ppZwthyBauyciLc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: a96755d6-1f54-4f3f-a971-d31f83705ab7
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 21f0ab524176df40128212fef920e10b06b5c317
workflow-type: tm+mt
source-wordcount: 2180
ht-degree: 7%

---

# 登陸頁面

登入頁面是獨立的網頁，您可以在聯絡人和客戶點按電子郵件、簡訊或任何數位位置中的連結專案後，指引他們。 您可以將這些頁面併入您的歷程，讓潛在客戶和客戶在網頁上檢視您的訊息，並在您的歷程中前進。 您可以在登入頁面視覺設計空間中建立、個人化和預覽登入頁面。

登入頁面的常見使用案例：

* 提供加入或退出行銷通訊或特定服務。 在電子郵件或其他通訊中使用指向目標清單的連結。
* 在傳送通訊之前收集同意，並在選擇加入或選擇退出時傳送確認電子郵件。
* 使用登入頁面上的表單來擷取或更新設定檔資料（漸進式設定檔、偏好設定、註冊和類似案例）。
* 將人們引導至專為您的歷程協調設計的行銷活動特定資訊。
* 將使用者重新導向至專用網路表單，而不需在Journey Optimizer B2B Prime外部建立外部頁面。

<!-- 
## Landing page workflow

To direct members of a journey audience to a defined web page when they click a specific link, create a landing page in Journey Optimizer B2B Edition: 


1. [Create the page](./landing-pages-create-publish.md) - Select a preset, set up the primary page, and add any required subpages.
1. [Design the landing page content](./landing-page-design.md) - Build the page content using drag-and-drop visual design components.
1. [Test the landing page](./landing-pages-create.md) - Preview the page, test form behavior, and then publish to make it live.
1. [Link to the page from your journey](#link-to-a-landing-page) - Add the landing page URL to an email, SMS, or journey action so that recipients can reach it.


For example, you can create and design landing pages to direct your users to online information. The page could include a form where they can opt in or opt out from receiving your communications. Or it could be an opportunity to subscribe to a recurring communications, such as a newsletter. 

You can create, personalize, and preview landing pages in the visual design space.
-->

## 存取及管理登入頁面 {#access-manage-landing-pages}

若要存取Journey Optimizer B2B Prime中的登入頁面，請前往左側導覽並按一下&#x200B;**[!UICONTROL 內容管理]** > **[!UICONTROL 登入頁面]**。 此動作會顯示執行個體中建立的所有登入頁面清單。

此清單是根據&#x200B;_[!UICONTROL 已修改]_&#x200B;欄排序，最近更新的專案位於頂端。 按一下欄標題，在升序和降序之間變更。

### 篩選登入頁面清單 {#filter-list}

若要依名稱搜尋登入頁面，請在搜尋列中輸入文字字串以尋找相符專案。 按一下&#x200B;_篩選器_&#x200B;圖示（![顯示或隱藏篩選器圖示](../../user/assets/do-not-localize/icon-filter.svg)）以顯示可用的篩選器選項，並變更設定以根據您指定的條件篩選顯示的專案。

![篩選顯示的登入頁面](./assets/landing-pages-list-filtered.png){width="800" zoomable="yes"}

<!-- 
This is going away? ### Customize the column display

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. 

In the dialog, select the columns to display and click **[!UICONTROL Apply]**.

![Select the columns that you want to display](./assets/landing-pages-customize-table-dialog.png){width="300"} 
-->

### 登陸頁面狀態和生命週期 {#landing-page-status}

登入頁面狀態會決定其是否可用於您的電子郵件和簡訊內容中的連結，以及您可以對其進行的變更。

| 狀態 | 說明 |
| -------------------- | ----------- |
| 草稿 | 建立登入頁面時，其狀態為草稿。 當您定義或編輯視覺內容時，它會保持此狀態，直到您將其發佈為託管頁面為止。 可用的動作： <br/><ul><li>編輯名稱或說明</li><li>編輯連結網址</li><li>在視覺設計空間編輯</li><li>發佈</li><li>重複</li><li>刪除</li></ul> |
| 發佈日期 | 發佈登入頁面時，該頁面會託管於Journey Optimizer B2B Prime例項，且可在電子郵件或簡訊內容中用於連結。 可用的動作： <br/><ul><li>編輯名稱或說明</li><li>編輯連結網址</li><li>在電子郵件或簡訊內容中新增連結</li><li>建立草稿版本</li><li>重複</li><li>刪除</li></ul> |
| 已與草稿一起發佈 | 當您從已發佈的登陸頁面建立草稿時，已發佈的版本會保留，而且草稿內容可以在視覺設計空間中進行修改。 如果您發佈草稿版本，草稿版本會取代目前發佈的版本，且託管頁面中的內容會更新。 可用的動作： <br/><ul><li>編輯名稱或說明</li><li>編輯連結網址</li><li>在電子郵件或簡訊內容中新增連結</li><li>在視覺化設計空間中編輯草稿版本</li><li>發佈草稿版本</li><li>重複</li><li>刪除（刪除兩個版本）</li><li>捨棄草稿（返回已發佈狀態）</li></ul> |

<!-- ![Landing page status lifecycle](./assets/status-lifecycle-diagram.png){zoomable="yes"} -->

## 建立登陸頁面 {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_create"
>title="定義和設定您的登陸頁面"
>abstract="若要建立登陸頁面，您需要選取一個預設集，然後設定主要頁面和子頁面，最後在發佈頁面之前進行測試。"

若要在個人歷程對象成員按一下特定連結時，將其導向至已定義的網頁，請在[!DNL Journey Optimizer B2B Prime]中建立登陸頁面。 您選取預設集、設定主要頁面和任何子頁面、[測試頁面](#test-landing-page)並發佈。

>[!IMPORTANT]
>
>在建立第一個登入頁面之前，請先完成登入頁面設定。 這包括設定子網域以託管登陸頁面，以及定義至少一個指定子網域和其他管道設定的預設集。 建立登入頁面時，您可以選取預設集。 如需管理員設定，請參閱[登入頁面設定](../admin/configuration-presets-landing-pages.md)。
>
>針對資料擷取使用案例，請先建立[表單](./forms.md)，再將其內嵌至登陸頁面。

若要建立登入頁面，請執行下列步驟：

1. 前往左側導覽並選取&#x200B;**[!UICONTROL 內容管理]** > **[!UICONTROL 登入頁面]**。

1. 從登入頁面清單中，按一下&#x200B;**[!UICONTROL 建立登入頁面]**。

1. 輸入&#x200B;**[!UICONTROL Title]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。

   標題和說明條件：

   * **標題** — 最多100個字元。 必須是唯一的（不區分大小寫）。
   * **描述** — 最多300個字元。
   * 允許使用Alpha、數值和特殊字元。
   * 保留的字元是&#x200B;**_不允許_**： `\ / : * ? " < > |`

1. 選取&#x200B;**[!UICONTROL 預設集]**。

   管理員[建立登陸頁面預設集](../admin/configuration-presets-landing-pages.md#lp-presets)，以定義用於登陸頁面的子網域和其他設定。 選取預設集，然後按一下「**[!UICONTROL 檢視預設集]**」以檢閱其設定，並確認符合您的登陸頁面需求。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   主要頁面及其屬性隨即顯示。 瞭解如何[設定主要頁面設定](#configure-primary-page)。

1. 若要新增子頁面（例如，感謝或錯誤頁面），請按一下&#x200B;**+**&#x200B;圖示。

   每個登入頁面最多可新增兩個子頁面。

設定並設計主要頁面和任何子頁面後，請在發佈登陸頁面[&#128279;](#test-landing-page)之前對其進行測試。

>[!CAUTION]
>
>即使頁面已發佈，您仍無法透過復制定義的URL並將其貼到網頁瀏覽器中來存取登入頁面。 使用預覽功能測試頁面，如[測試登入頁面](#test-landing-page)中所述。

## 設定主要頁面 {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_primary_page"
>title="定義您的主要頁面設定"
>abstract="定義主要頁面，當收件者從電子郵件或網站等內容中按一下登陸頁面連結時，就會立即顯示該頁面。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_access_settings"
>title="定義您的登陸頁面 URL"
>abstract="在本區段中，定義一個唯一的登陸頁面 URL。 URL 的第一部分需要您預先設定一個登陸頁面子網域作為您所選預設集的一部分。"

主要頁面是收件者按一下登入頁面連結（例如從電子郵件或網站）時立即顯示的頁面。

若要定義主要頁面設定，請執行下列步驟：

1. 根據您的需求變更&#x200B;**[!UICONTROL 頁面名稱]**，預設為&#x200B;_主要頁面_。

1. 定義頁面URL的結束部分。

   您選取的預設集決定了URL的第一個部分。 管理員將[登陸頁面子網域](../admin/configuration-presets-landing-pages.md#lp-subdomains)設定為預設集的一部分。

   >[!CAUTION]
   >
   >登陸頁面URL必須是唯一的。
   >
   >您無法將此URL複製並貼到網頁瀏覽器以存取登入頁面，即使頁面已發佈亦然。 使用[測試登入頁面](#test-landing-page)中所述的預覽功能來測試它。

1. 如果您想要匿名登陸頁面，請停用&#x200B;**[!UICONTROL 需要已識別的使用者]**&#x200B;選項。

1. 按一下&#x200B;_行事曆_&#x200B;圖示以設定&#x200B;**[!UICONTROL 頁面到期日]**。

   選取到期日後，請選擇頁面到期時的動作：

   * **[!UICONTROL 重新導向URL]** — 輸入要做為重新導向之頁面的URL。
   * **[!UICONTROL 瀏覽器錯誤]** — 輸入要取代頁面的錯誤文字。

## 測試登陸頁面 {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_preview_lp_profiles"
>title="預覽和測試您的登陸頁面"
>abstract="在您定義登陸頁面設定和內容後，請使用測試輪廓來預覽該頁面。"

定義登入頁面設定和內容時，您可以使用測試設定檔來預覽頁面。 如果您已插入[個人化內容](email-authoring.md#personalization)，您可以使用測試設定檔資料檢查此內容在登入頁面中的顯示方式。

>[!PREREQUISITES]
>
>若要預覽和測試登入頁面，您必須擁有&#x200B;**[!UICONTROL 發佈訊息]**&#x200B;許可權，以及包含測試設定檔的已定義資料集。

1. 按一下&#x200B;**[!UICONTROL 預覽和測試]**&#x200B;以開啟測試設定檔選取專案。

   >[!NOTE]
   >
   >當您在視覺化設計空間時，也可以使用&#x200B;**[!UICONTROL 模擬內容]**。

1. 從&#x200B;_[!UICONTROL 模擬]_&#x200B;畫面選取測試設定檔。

   如果未列出您需要的設定檔，請按一下[管理測試設定檔] **，使用已知的測試設定檔電子郵件地址，並將其新增至清單。**

   +++新增測試設定檔

   針對&#x200B;**[!UICONTROL 身分識別名稱空間]**，按一下&#x200B;_選取_&#x200B;圖示（![選取圖示](../../user/assets/do-not-localize/icon-select-data.svg) ）並選擇用於測試設定檔的`Email`名稱空間。

   在&#x200B;**[!UICONTROL 識別值]**&#x200B;欄位中，輸入識別測試設定檔的電子郵件地址，然後按一下&#x200B;**[!UICONTROL 新增設定檔]**。 您可以重複此步驟以新增多個設定檔。

   按一下左上方的向後箭頭，返回&#x200B;_[!UICONTROL 模擬]_&#x200B;頁面。

   +++

1. 選取&#x200B;**[!UICONTROL 開啟預覽]**&#x200B;以測試您的登陸頁面。

   登入頁面預覽會在新標籤中開啟。 選取的測試設定檔資料會取代個人化元素。

1. 選取其他測試設定檔以預覽登陸頁面每個變體的呈現。

## 編輯登入頁面 {#edit-landing-page}

對登入頁面的編輯取決於其目前狀態：

* 當登入頁面處於&#x200B;**_草稿_**&#x200B;狀態時，您可以編輯其任何詳細資料、URL和視覺內容。
* 當登入頁面處於&#x200B;**_已發佈_**&#x200B;狀態時，您可以編輯說明，但不能編輯名稱。 若要變更視覺內容，您必須建立頁面的草稿版本。
* 當登入頁面處於&#x200B;**_以草稿_**&#x200B;狀態發佈時，編輯詳細資料僅限於說明。 您也可以編輯草稿版本的視覺內容。

>[!BEGINTABS]

>[!TAB 草稿]

1. 從&#x200B;_[!UICONTROL 登入頁面]_&#x200B;清單頁面，按一下登入頁面名稱以開啟。

   接著會顯示視覺內容的預覽，登陸頁面的詳細資訊位於右側。

1. 修改任何詳細資訊，例如名稱和說明。

   <!-- ![Details for landing page with Draft status](./assets/landing-page-draft-details.png){width="700" zoomable="yes"} -->

1. 若要變更視覺化設計空間中的內容，請按一下&#x200B;**[!UICONTROL 編輯登陸頁面]**。

1. 按一下「**[!UICONTROL 儲存]**」，或「**[!UICONTROL 儲存並關閉]**」以返回登陸頁面的詳細資料。

1. 當頁面符合您的條件且您想要可供顯示時，請按一下&#x200B;**[!UICONTROL 發佈]**。

>[!TAB 已發佈]

1. 從&#x200B;_[!UICONTROL 登入頁面]_&#x200B;清單頁面，按一下頁面名稱以開啟。

   接著會顯示視覺內容的預覽，登陸頁面的詳細資訊位於右側。

1. 視需要修改說明。

   針對已發佈的登陸頁面，無法變更所有其他詳細資料。

1. 若要更新內容，請按一下右側的&#x200B;**[!UICONTROL 編輯登陸頁面]**。

   在對話方塊中按一下&#x200B;**[!UICONTROL 建立草稿版本]**，在視覺化設計空間開啟草稿版本。

1. 按一下「**[!UICONTROL 儲存]**」，或「**[!UICONTROL 儲存並關閉]**」以返回登陸頁面的詳細資料。

1. 當草稿登入頁面符合您的條件，而您想要讓變更可在已發佈的頁面上使用時，請按一下&#x200B;**[!UICONTROL 發佈]**。

   當您發佈草稿版本時，它會取代目前發佈的版本，並更新頁面URL的內容。

>[!TAB 已發佈草稿]

當您開啟登入頁面時，會顯示草稿版本。 預覽空間頂端的索引標籤可讓您在已發佈版本和草稿版本之間切換顯示。 草稿動作和詳細資訊會顯示在右側。

<!-- ![Preview and details for the landing page draft version](./assets/landing-page-published-draft-details.png){width="700" zoomable="yes"} -->

若要更新內容：

1. 按一下右上方的&#x200B;**[!UICONTROL 編輯登陸頁面]**。

1. 按一下「**[!UICONTROL 儲存]**」，或「**[!UICONTROL 儲存並關閉]**」以返回登陸頁面的詳細資料。

1. 當草稿頁面符合您的條件且您想要讓變更可用時，請按一下[發佈]。**&#x200B;**

   當您發佈草稿版本時，草稿版本會取代目前發佈的版本，而託管頁面中的內容會更新。

>[!ENDTABS]

## 複製登陸頁面 {#duplicate-landing-page}

您可以使用下列其中一種方法來複製登入頁面：

* 從&#x200B;_[!UICONTROL 登陸頁面]_&#x200B;清單頁面，按一下&#x200B;_更多_&#x200B;圖示(**...**) 在登入頁面名稱旁邊，並選擇&#x200B;**[!UICONTROL 複製]**。
* 在登入頁面詳細資訊頁面的右上方，按一下&#x200B;**[!UICONTROL ...更多]**&#x200B;並選擇&#x200B;**[!UICONTROL 複製]**。

<!-- ![Duplicate the landing page](./assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"} -->

在對話方塊中，輸入有用的名稱（唯一）和說明（選擇性）。 按一下&#x200B;**[!UICONTROL 複製]**&#x200B;以完成動作。

<!-- ![Enter a name and description for the duplicated landing page](./assets/landing-page-duplicate-dialog.png){width="350"} -->

然後，重複的（新）頁面會出現在&#x200B;_登陸頁面_&#x200B;清單中。

## 刪除登陸頁面 {#delete-landing-page}

您可以使用下列其中一種方法來刪除登入頁面：

* 從&#x200B;_[!UICONTROL 登陸頁面]_&#x200B;清單頁面，按一下&#x200B;_更多_&#x200B;圖示(**...**) 在登入頁面名稱旁邊，並選擇&#x200B;**[!UICONTROL 刪除]**。
* 在登入頁面詳細資訊頁面的右上方，按一下&#x200B;**[!UICONTROL ...更多]**&#x200B;並選擇&#x200B;**[!UICONTROL 刪除]**。

此動作會開啟確認對話方塊。 您可以按一下&#x200B;**[!UICONTROL 取消]**，或按一下&#x200B;**[!UICONTROL 刪除]**&#x200B;確認刪除，以中止程式。

<!-- ![Delete landing page dialog](./assets/landing-page-delete-dialog.png){width="400"} -->

## 連結至登入頁面 {#link-to-landing-page}

作為產生電子郵件、片段和頁面內容的行銷人員或創意人員，您可以內嵌連結至在Journey Optimizer B2B Prime例項中建立的已發佈（即時）登陸頁面。

1. 當您在片段、電子郵件、登入頁面或範本的視覺設計空間工作時，請為連結選取文字片段、按鈕元件或影像元件。

   **[!UICONTROL 連結]**&#x200B;選項會顯示在右側面板中。

1. 針對&#x200B;**[!UICONTROL Type]**&#x200B;選項，請選擇&#x200B;**[!UICONTROL 登陸頁面]**。

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-settings.png){width="700" zoomable="yes"} -->

1. 針對&#x200B;**[!UICONTROL 登陸頁面]**&#x200B;選項，按一下&#x200B;_選取頁面_&#x200B;圖示（![顯示連結圖示](../../user/assets/do-not-localize/icon-landing-page-select.svg) ）。

1. 在「選取登陸頁面」對話方塊中，將&#x200B;**[!UICONTROL 登陸頁面來源]**&#x200B;設定為&#x200B;**[!UICONTROL Journey Optimizer B2B edition]**，從已發佈頁面的清單中選取登陸頁面的核取方塊，然後按一下「選取&#x200B;**[!UICONTROL 」]**。

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-landing-page-select.png){width="600" zoomable="yes"} -->

1. 針對&#x200B;**[!UICONTROL Target]**&#x200B;選項，選擇連結目標行為：

   * **[!UICONTROL 無]** — 使用瀏覽器預設行為開啟連結。
   * **[!UICONTROL 空白]** — 在新視窗或索引標籤中開啟連結。
   * **[!UICONTROL Self]** — 在相同框架中開啟連結。
   * **[!UICONTROL 父系]** — 在父框架中開啟連結。
   * **[!UICONTROL Top]** — 在視窗的整個內文中開啟連結。

1. （僅限文字連結）如果要將連結的文字加底線，請選取&#x200B;**[!UICONTROL 加底線連結]**&#x200B;核取方塊。

   您可以選取右側面板中的&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤，為連結文字設定其他樣式，包括連結顏色。
