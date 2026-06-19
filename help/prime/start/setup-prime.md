---
title: 設定檢查清單
description: 完成您的Journey Optimizer B2B Prime執行個體的初始設定工作，包括使用者存取設定和電子郵件傳遞能力基礎架構。
autotag-review: '2026-06-12T23:06:52.179Z'
TQID: 'https://experienceleague.adobe.com/D8qXM-F4anA8IVYmdlaclUoxgTwqQptN36xYFpsuvHY'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: f467931a-9b22-4ca8-869f-adfbd64061ceid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1fid: f6df9def-cdf7-4728-9ec8-3f65716828c7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: de83abd4ca48e2dfda8a1900f7c8074232bb9d8e
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 11%

---

# 設定檢查清單

完成這些工作以啟用您布建的[!DNL Journey Optimizer B2B Prime]執行個體中的功能。

## 啟用使用者存取 {#enable-user-access}

布建完成且沙箱已繫結時，請為您的團隊和使用者設定[!DNL Journey Optimizer B2B Edition]存取權。

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
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Admin Console中建立Journey Optimizer B2B edition產品設定檔（僅限一次性/初始設定）</td>
<td><a href="./user-management.md#create-profile">建立設定檔</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Admin Console中新增使用者群組</td>
<td><a href="./user-management.md#add-user-group">新增使用者群組</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>編輯內建角色，或建立具有產品許可權的自訂角色</td>
<td><a href="./user-management.md#edit-role-permissions">編輯角色</a> <br/> <a href="./user-management.md#create-a-custom-role">建立自訂角色</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Adobe Experience Platform中新增使用者或群組至角色</td>
<td><a href="./user-management.md#add-users-to-a-role">新增使用者</a> <br/><a href="./user-management.md#add-user-groups-to-a-role">新增群組</a></td>
</tr>
</tbody>
</table>

## 電子郵件傳遞能力 {#email-deliverability}

行銷人員從歷程傳送電子郵件之前，請先設定組織的傳送基礎架構，包括子網域委派、電子郵件驗證和頻道設定。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>設定電子郵件傳遞能力與通道設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>將子網域委派給Adobe （完全委派或CNAME）</td>
<td><a href="./admin/configuration-email-deliverability.md#delegate-fully-delegated">已完全委派</a> <br/> <a href="./admin/configuration-email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>為子網域設定DMARC</td>
<td><a href="./admin/configuration-email-deliverability.md#configure-dmarc">設定DMARC</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>檢閱和指派IP集區</td>
<td><a href="./admin/configuration-email-deliverability.md#review-ip-pool">檢閱IP集區</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>建立電子郵件通道設定</td>
<td><a href="./admin/configuration-email-deliverability.md#create-email-channel-configuration">設定電子郵件管道</a></td>
</tr>
</tbody>
