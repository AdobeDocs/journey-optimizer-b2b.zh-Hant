---
title: 簡化的架構設定
description: 在簡化的架構上設定Journey Optimizer B2B edition。 設定XDM結構描述、電子郵件/簡訊頻道、Marketo Engage歷程動作和使用者。
feature: Setup, Administration
role: Admin, Data Engineer
exl-id: 81232976-09d6-4e10-a034-5c193a63b7df
source-git-commit: 38d1794ed30a34dbb34dfaec2d3088bc3a4680ac
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 17%

---

# 簡化的架構設定

現在可透過簡化的架構使用 Adobe Journey Optimizer B2B Edition。 透過此架構，Journey Optimizer B2B edition和Marketo Engage不再是位於相同系統和相同資料存放區。 Journey Optimizer B2B Edition 只會接收來自 Adobe Experience Platform 的資料。 但是，它繼續仰賴Marketo Engage許可權和部分後端功能（例如電子郵件傳送）來布建和設定系統。

簡化的架構是解鎖Journey Optimizer B2B edition新功能的基礎：

* **輕鬆統一並擴充您的資料：**&#x200B;新平台支援複雜的資料模型，包括自訂物件、購買群組和帳戶事件。

* **連線多個Adobe Marketo Engage執行個體：**&#x200B;在一個位置管理並統一來自多個Marketo Engage環境的資料。

* **保護您的資料安全：**&#x200B;進階的隱私和安全性功能，可協助保護您的客戶資訊。 （_即將推出_）

* **為未來打造：**&#x200B;此升級可讓您持續改進與創新。

針對針對此架構布建的環境，請使用下列設定准則。

使用此檢查清單，在簡化的架構上完成Journey Optimizer B2B edition設定。

## &#x200B;1. 產生B2B名稱空間和結構描述

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>環境設定：</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>從GitHub下載名稱空間和結構描述自動產生公用程式。</td>
<td><a href="./data/namespaces-schemas.md#set-up-the-auto-generation-utility">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>收集Experience Platform API憑證和必要的標頭。</td>
<td><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-apis/api-guide">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>套用環境值至您的Postman環境。</td>
<td><a href="./data/namespaces-schemas.md#environment-values">了解更多</a></td>
</tr>
<tr>
<td colspan="2"><strong>執行指令碼：</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>在Postman中執行<em>名稱空間和結構描述</em>產生公用程式，並確認已建立名稱空間和結構描述。</td>
<td><a href="./data/namespaces-schemas.md#run-the-scripts">了解更多</a></td>
</tr>
</tbody>
</table>

## &#x200B;2. 設定XDM欄位和事件

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>標準XDM類別</strong>：設定XDM個人設定檔和XDM商業帳戶類別。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>選取要公開供歷程、購買群組和電子郵件個人化的受管理欄位。</td>
<td><a href="./admin/xdm-field-management.md#standard-classes">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>編輯結構描述的可更新欄位。</td>
<td><a href="./admin/xdm-field-management.md#updatable-fields">了解更多</a></td>
</tr>
<tr>
<td colspan="2"><strong>關聯式結構描述</strong>：選取關聯式XDM類別（帳戶多對一自訂物件）。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>請確定結構描述具有所需的設定值。</td>
<td><a href="./admin/xdm-field-management.md#relational-schemas">了解更多</a></td>
</tr>
<tr>
<td colspan="2"><strong>事件</strong>：設定Experience Platform事件型別和欄位。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>使用要在歷程決策/分割路徑中支援的欄位來設定每個Experience Platform事件型別。</td>
<td><a href="./admin/configure-aep-events.md">了解更多</a></td>
</tr>
</tbody>
</table>

## &#x200B;3. 設定追蹤和電子郵件傳遞能力

若要在簡化的架構上從[!DNL Journey Optimizer B2B Edition]傳送電子郵件，請在附加的[!DNL Marketo Engage]生產執行個體和[!DNL Journey Optimizer B2B Edition]應用程式中設定電子郵件追蹤與傳遞能力。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">附加的Marketo Engage執行個體的<strong>初始設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定新的CNAME以追蹤DNS記錄中的連結</td>
<td><a href="./start/email-protocols.md#create-dns-records-for-landing-pages-and-email">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>為附加的Marketo Engage執行個體設定品牌化網域</td>
<td><a href="./start/branding-domains.md">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>將DKIM和SPF設定到附加的Marketo Engage執行個體</td>
<td><a href="./start/email-protocols.md#set-up-spf-and-dkim">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定 DMARC</td>
<td><a href="./start/email-protocols.md#set-up-dmarc">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定您的網域的 MX 記錄</td>
<td><a href="./start/email-protocols.md#set-up-mx-records-for-your-domain">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>將輸出IP位址新增至允許清單</td>
<td><a href="./start/email-protocols.md#outbound-ip-addresses">了解更多</a></td>
</tr>
<tr>
<td colspan="2">附件之Marketo Engage執行個體的<strong>電子郵件設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定<em>從電子郵件</em>和<em>從標籤</em> （選擇性）</td>
<td><a href="./start/email-setup.md#from-email-and-label">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定<em>取消訂閱HTML</em>和<em>取消訂閱文字</em></td>
<td><a href="./start/email-setup.md#unsubscribe-messaging">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定<em>以網頁檢視HTML</em>和<em>以網頁文字檢視</em></td>
<td><a href="./start/email-setup.md#view-as-web-page">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定<em>自訂物件擷取限制</em></td>
<td><a href="./start/email-setup.md#custom-object-retrieval-limits">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定<em>自訂標頭選項</em></td>
<td><a href="./start/email-setup.md#custom-header-options">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定<em>機器人活動</em>篩選</td>
<td><a href="./start/email-setup.md#filter-email-bots">了解更多</a></td>
</tr>
<tr>
<td colspan="2">Journey Optimizer B2B edition的<strong>電子郵件通道設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>在Journey Optimizer B2B edition中設定<em>通訊限制</em></td>
<td><a href="./admin/configure-channels-emails.md#communication-limits">了解更多</a></td>
</tr>
</tbody>
</table>

<!-- TBD for later 

<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Email CC Settings</em></td>
<td>[Learn more](TBD)</td>
</tr>

<tr>
<td colspan="2"><strong>Additional configurations</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Location Settings</em> for the attached Marketo Engage instance</td>
<td>< [Learn more](TBD)</td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Define and configure which Binding Groups / IPs to move over</td>
<td>[Learn more](TBD)</td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Test Email Send</td>
<td>[Learn more](TBD)</td>
</tr>
-->

## &#x200B;4. 設定其他內容頻道

若要支援行銷人員將其他管道納入其歷程，請設定其他管道。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">Journey Optimizer B2B edition的<strong>簡訊</strong>頻道設定。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定您要支援的每個SMS帳戶。</td>
<td><a href="./admin/configure-channels-sms.md">了解更多</a></td>
</tr>
<tr>
<td colspan="2">Journey Optimizer B2B edition的<strong>登陸頁面</strong> (Beta)管道設定。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>完成登入頁面設定，以支援製作及發佈這些頁面的行銷人員</td>
<td><a href="./admin/landing-page-settings.md">了解更多</a></td>
</tr>
<tr>
<td colspan="2">適用於Journey Optimizer B2B edition的<strong>Web</strong> (Beta)管道設定</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定您的企業網站以支援Adobe Experience Platform Web SDK。</td>
<td><a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/js-overview">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>依照傳送內容的URL新增Web屬性。</td>
<td><a href="./admin/configure-channels-web.md">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>指示網頁體驗作者安裝Adobe Experience Cloud Visual Editing Helper瀏覽器擴充功能。</td>
<td><a href="./content/web-experiences.md#install-the-visual-editing-helper-extension">了解更多</a></td>
</tr>
</tbody>
</table>

## &#x200B;5. 連線Marketo Engage執行個體以支援歷程動作（選用）

如果您打算透過Marketo Engage中的行銷活動和方案補充Journey Optimizer B2B edition功能，請設定Marketo Engage動作支援。 這些動作可讓您的行銷團隊在Journey Optimizer B2B edition中協調其&#x200B;_以帳戶為基礎的_&#x200B;行銷，並在Marketo Engage中協調&#x200B;_以銷售機會為基礎的_&#x200B;行銷工作。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">針對每個Marketo Engage執行個體<strong>支援歷程動作</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>建立Marketo Engage自訂服務</td>
<td><a href="./admin/marketo-actions-connect.md#create-the-marketo-engage-custom-service">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>在Journey Optimizer B2B edition中新增整合</td>
<td><a href="./admin/marketo-actions-connect.md#add-the-integration">了解更多</a></td>
</tr>
</tbody>
</table>

## &#x200B;6. 啟用使用者存取

布建完成後，沙箱已繫結且初始設定任務已完成，請為團隊和使用者設定Journey Optimizer B2B edition和Marketo Engage存取權。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>為使用者提供產品存取和許可權</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>在Adobe Admin Console中建立Marketo Engage產品設定檔（僅限新的Marketo Engage執行個體）</td>
<td><a href="./admin/user-management.md#create-the-marketo-engage-product-profile">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>為設定檔新增使用者群組</td>
<td><a href="./admin/user-management.md#add-a-user-group-for-the-profile">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>設定B2B使用者角色</td>
<td><a href="./admin/user-management.md#b2b-built-in-roles">了解更多</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="核取方塊"/></td>
<td>將使用者或群組新增至角色</td>
<td><a href="./admin/user-management.md#add-users-to-a-role">了解更多</a></td>
</tr>
</tbody>
</table>
