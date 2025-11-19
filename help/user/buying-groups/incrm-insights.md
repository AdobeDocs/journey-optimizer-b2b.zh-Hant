---
title: In-CRM Insights
description: 直接在Salesforce中存取Journey Optimizer B2B edition購買群組。 銷售團隊成員可以使用In-CRM Insights檢視參與資料並識別銷售機會。
feature: Sales Insights, Buying Groups
role: User
source-git-commit: de7f5620556a48fe6f12ed1c70e925e11ec770f1
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# In-CRM Insights

CRM Insights是整合至Salesforce的網頁型應用程式，可讓您直接在Salesforce中存取Journey Optimizer B2B edition購買群組。 它可讓您找出提升參與度和銷售潛力的機會。

In-CRM Insights應用程式可在[Marketo Sales Insights套件](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/marketo-sales-insight/msi-for-salesforce/installation/install-marketo-sales-insight-package-in-salesforce-appexchange)中使用。

## 權限

若要存取應用程式，使用者必須在角色中擁有&#x200B;**Sales Insights:View Sales Insights**&#x200B;許可權的成員。

如果您想要將使用者群組限製為InCRM-Insights，請使用下列指引建立專為InCRM-Insights的自訂角色：

* 建立僅具有&#x200B;**Sales Insights:View Sales Insights**&#x200B;許可權集的自訂角色。
* 建立新的使用者群組，而不新增任何產品設定檔。
* 建立另一個使用者群組並新增AEP產品設定檔，或將現有AEP設定檔新增至您剛才建立的使用者群組。
* 將新使用者群組指派給新角色，並將新使用者新增至新使用者群組。

## 使用In-CRM Insights

In-CRM Insights應用程式可透過應用程式啟動器在Salesforce中使用。

1. 按一下Salesforce中的應用程式啟動器。
1. 選取或搜尋`Journey Optimizer B2B Edition`。
1. 在顯示的標籤中，使用您的Adobe憑證登入。
1. 選擇託管您的帳戶歷程的沙箱。

您的購買群組已載入並可供使用。 透過In-CRM Insights以唯讀方式提供資料。

>[!NOTE]
>
>必須具備[B2B銷售使用者](../admin/user-management.md#b2b-built-in-roles)產品角色的成員資格，才能存取In-CRM Insights。

選取購買群組後，您可以瀏覽[群組詳細資料](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/sales-experience/buying-group-details#)，就像在Journey Optimizer B2B edition中一樣。
