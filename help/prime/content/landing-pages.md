---
title: 登陸頁面
description: 建立、設計和發佈個人歷程的登陸頁面 — 從頭開始建立、匯入HTML、新增表單、個人化內容，以及從Journey Optimizer B2B Prime中的電子郵件連結。
source-git-commit: a2443f98ec7a8a5c1d4be2450042e2375f6150b7
workflow-type: tm+mt
source-wordcount: '1461'
ht-degree: 6%

---

# 登陸頁面

登入頁面是獨立的網頁，您可以在聯絡人和客戶點按電子郵件、簡訊或任何數位位置中的連結專案後，指引他們。 您可以將這些頁面合併到您的帳戶歷程中，讓您的潛在客戶和客戶在網頁上檢視您的訊息，並在您的帳戶歷程中前進。 您可以在登入頁面視覺設計空間中建立、個人化和預覽登入頁面。

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
1. [Test and publish the landing page](./landing-pages-create-publish.md) - Preview the page, test form behavior, and then publish to make it live.
1. [Link to the page from your journey](#link-to-a-landing-page) - Add the landing page URL to an email, SMS, or journey action so that recipients can reach it.


For example, you can create and design landing pages to direct your users to online information. The page could include a form where they can opt in or opt out from receiving your communications. Or it could be an opportunity to subscribe to a recurring communications, such as a newsletter. 

You can create, personalize, and preview landing pages in the visual design space.
-->
## 存取及管理登入頁面

若要存取Journey Optimizer B2B Prime中的登入頁面，請前往左側導覽並按一下&#x200B;**[!UICONTROL 內容管理]** > **[!UICONTROL 登入頁面]**。 此動作會顯示執行個體中建立的所有登入頁面清單。

此清單是根據&#x200B;_[!UICONTROL 已修改]_&#x200B;欄排序，最近更新的專案位於頂端。 按一下欄標題，在升序和降序之間變更。

### 篩選登入頁面清單

若要依名稱搜尋登入頁面，請在搜尋列中輸入文字字串以尋找相符專案。 按一下&#x200B;_篩選器_&#x200B;圖示<!-- ( ![Show or hide filters icon](../assets/do-not-localize/icon-filter.svg) ) -->以顯示可用的篩選器選項，並變更設定以根據您指定的條件篩選顯示的專案。

![篩選顯示的登入頁面](./assets/landing-pages-list-filtered.png){width="800" zoomable="yes"}

<!-- 
This is going away? ### Customize the column display

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. 

In the dialog, select the columns to display and click **[!UICONTROL Apply]**.

![Select the columns that you want to display](./assets/landing-pages-customize-table-dialog.png){width="300"} 
-->

### 登陸頁面狀態和生命週期

登入頁面狀態會決定其是否可用於您的電子郵件和簡訊內容中的連結，以及您可以對其進行的變更。

| 狀態 | 說明 |
| -------------------- | ----------- |
| 草稿 | 建立登入頁面時，其狀態為草稿。 當您定義或編輯視覺內容時，它會保持此狀態，直到您將其發佈為託管頁面為止。 可用的動作： <br/><ul><li>編輯名稱或說明<li>編輯連結網址<li>在視覺設計空間編輯<li>發佈<li>重複<li>刪除 |
| 發佈日期 | 發佈登入頁面時，該頁面會託管於Journey Optimizer B2B Prime例項，且可在電子郵件或簡訊內容中用於連結。 可用的動作： <br/><ul><li>編輯名稱或說明<li>編輯連結網址<li>在電子郵件或簡訊內容中新增連結<li>建立草稿版本<li>重複<li>刪除 |
| 已與草稿一起發佈 | 當您從已發佈的登陸頁面建立草稿時，已發佈的版本會保留，而且草稿內容可以在視覺設計空間中進行修改。 如果您發佈草稿版本，草稿版本會取代目前發佈的版本，且託管頁面中的內容會更新。 可用的動作： <br/><ul><li>編輯名稱或說明<li>編輯連結網址<li>在電子郵件或簡訊內容中新增連結<li>在視覺化設計空間中編輯草稿版本<li>發佈草稿版本<li>重複<li>刪除（刪除兩個版本）<li>捨棄草稿（返回已發佈狀態） |

<!-- ![Landing page status lifecycle](./assets/status-lifecycle-diagram.png){zoomable="yes"} -->

## 建立登陸頁面 {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_create"
>title="定義和設定您的登陸頁面"
>abstract="若要建立登陸頁面，您需要選取一個預設集，然後設定主要頁面和子頁面，最後在發佈頁面之前進行測試。"

待定

## 設定主要頁面 {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_primary_page"
>title="定義您的主要頁面設定"
>abstract="定義主要頁面，當收件者按一下登入頁面連結（例如從電子郵件或網站）時，就會立即顯示。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_access_settings"
>title="定義您的登陸頁面 URL"
>abstract="在本區段中，定義一個唯一的登陸頁面 URL。 URL的第一個部分會要求您先前將登陸頁面子網域設定為您所選預設集的一部分。"

待定

## 測試登陸頁面 {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_preview_lp_profiles"
>title="預覽和測試您的登陸頁面"
>abstract="定義登入頁面設定和內容後，請使用測試設定檔來預覽頁面。"

待定

## 編輯登入頁面

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

   <!-- 
   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)
   -->

1. 按一下「**[!UICONTROL 儲存]**」，或「**[!UICONTROL 儲存並關閉]**」以返回登陸頁面的詳細資料。

1. 當頁面符合您的條件且您想要可供顯示時，請按一下&#x200B;**[!UICONTROL 發佈]**。

>[!TAB 已發佈]

1. 從&#x200B;_[!UICONTROL 登入頁面]_&#x200B;清單頁面，按一下頁面名稱以開啟。

   接著會顯示視覺內容的預覽，登陸頁面的詳細資訊位於右側。

1. 視需要修改說明。

   針對已發佈的登陸頁面，無法變更所有其他詳細資料。

1. 若要更新內容，請按一下右側的&#x200B;**[!UICONTROL 編輯登陸頁面]**。

   在對話方塊中按一下&#x200B;**[!UICONTROL 建立草稿版本]**，在視覺化設計空間開啟草稿版本。

   <!-- 
   ![Create draft version dialog](./assets/landing-page-create-draft-version.png){width="300"} 

   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)
   -->

1. 按一下「**[!UICONTROL 儲存]**」，或「**[!UICONTROL 儲存並關閉]**」以返回登陸頁面的詳細資料。

1. 當草稿登入頁面符合您的條件，而您想要讓變更可在已發佈的頁面上使用時，請按一下&#x200B;**[!UICONTROL 發佈]**。

   當您發佈草稿版本時，它會取代目前發佈的版本，並更新頁面URL的內容。

>[!TAB 已發佈草稿]

當您開啟登入頁面時，會顯示草稿版本。 預覽空間頂端的索引標籤可讓您在已發佈版本和草稿版本之間切換顯示。 草稿動作和詳細資訊會顯示在右側。

<!-- ![Preview and details for the landing page draft version](./assets/landing-page-published-draft-details.png){width="700" zoomable="yes"} -->

若要更新內容：

1. 按一下右上方的&#x200B;**[!UICONTROL 編輯登陸頁面]**。

   <!--

   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)

   -->

1. 按一下「**[!UICONTROL 儲存]**」，或「**[!UICONTROL 儲存並關閉]**」以返回登陸頁面的詳細資料。

1. 當草稿頁面符合您的條件且您想要讓變更可用時，請按一下[發佈]。****

   當您發佈草稿版本時，草稿版本會取代目前發佈的版本，而託管頁面中的內容會更新。

>[!ENDTABS]

## 複製登陸頁面

您可以使用下列其中一種方法來複製登入頁面：

* 從&#x200B;_[!UICONTROL 登陸頁面]_&#x200B;清單頁面，按一下&#x200B;_更多_&#x200B;圖示(**...**) 在登入頁面名稱旁邊，並選擇&#x200B;**[!UICONTROL 複製]**。
* 在登入頁面詳細資訊頁面的右上方，按一下&#x200B;**[!UICONTROL ...更多]**&#x200B;並選擇&#x200B;**[!UICONTROL 複製]**。

<!-- ![Duplicate the landing page](./assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"} -->

在對話方塊中，輸入有用的名稱（唯一）和說明（選擇性）。 按一下&#x200B;**[!UICONTROL 複製]**&#x200B;以完成動作。

<!-- ![Enter a name and description for the duplicated landing page](./assets/landing-page-duplicate-dialog.png){width="350"} -->

然後，重複的（新）頁面會出現在&#x200B;_登陸頁面_&#x200B;清單中。

## 刪除登陸頁面

您可以使用下列其中一種方法來刪除登入頁面：

* 從&#x200B;_[!UICONTROL 登陸頁面]_&#x200B;清單頁面，按一下&#x200B;_更多_&#x200B;圖示(**...**) 在登入頁面名稱旁邊，並選擇&#x200B;**[!UICONTROL 刪除]**。
* 在登入頁面詳細資訊頁面的右上方，按一下&#x200B;**[!UICONTROL ...更多]**&#x200B;並選擇&#x200B;**[!UICONTROL 刪除]**。

此動作會開啟確認對話方塊。 您可以按一下&#x200B;**[!UICONTROL 取消]**，或按一下&#x200B;**[!UICONTROL 刪除]**&#x200B;確認刪除，以中止程式。

<!-- ![Delete landing page dialog](./assets/landing-page-delete-dialog.png){width="400"} -->

## 連結至登入頁面

作為產生電子郵件、片段和頁面內容的行銷人員或創意人員，您可以內嵌連結至在Journey Optimizer B2B Prime例項中建立的已發佈（即時）登陸頁面。

1. 當您在片段、電子郵件、登入頁面或範本的視覺設計空間工作時，請為連結選取文字片段、按鈕元件或影像元件。

   **[!UICONTROL 連結]**&#x200B;選項會顯示在右側面板中。

1. 針對&#x200B;**[!UICONTROL Type]**&#x200B;選項，請選擇&#x200B;**[!UICONTROL 登陸頁面]**。

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-settings.png){width="700" zoomable="yes"} -->

1. 針對&#x200B;**[!UICONTROL 登陸頁面]**&#x200B;選項，按一下&#x200B;_選取頁面_&#x200B;圖示<!-- ( ![Show links icon](/help/assets/do-not-localize/icon-landing-page-select.svg) ) -->。

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
