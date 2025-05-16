---
title: 帳戶受眾節點
description: 瞭解可用於在Journey Optimizer B2B edition中定義帳戶歷程輸入的帳戶對象節點型別。
feature: Account Journeys, Audiences, Account Lists
role: User
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 5%

---

# 帳戶對象歷程節點

帳戶對象節點會定義歷程的輸入帳戶。 當您[建立帳戶歷程](./journey-overview.md#create-an-account-journey)時，它一律以定義歷程輸入的&#x200B;_帳戶對象_&#x200B;節點開始。

您可以針對此節點使用兩種型別的輸入：

* **[帳戶對象](../audiences/account-audience-overview.md)** — 這是從Experience Platform Segmentation Service同步的基本對象。
* **[帳戶清單](../accounts/account-lists.md)** — 這是可用於目標歷程協調的具名帳戶集合。 帳戶會根據定義的條件（例如產業、地點或公司規模）列出具名帳戶的目標。

_若要設定節點的對象：_

1. 按一下&#x200B;**[!UICONTROL 帳戶對象]**&#x200B;節點，在右側顯示節點屬性。

   ![帳戶對象節點](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. 選擇帳戶輸入型別以輸入歷程：

   * **[!UICONTROL 帳戶對象]**

     選擇此型別，然後按一下&#x200B;**[!UICONTROL 新增帳戶對象]**。

     在&#x200B;_[!UICONTROL 新增對象]_&#x200B;對話方塊中，選取先前建立的對象區段，然後按一下&#x200B;**[!UICONTROL 新增對象]**。

     ![選取節點的對象區段](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL 帳戶清單]**

     選擇此型別，然後按一下&#x200B;**[!UICONTROL 新增帳戶清單]**。

     在&#x200B;_[!UICONTROL 選取即時帳戶清單]_&#x200B;對話方塊中，選取先前發佈的帳戶清單，然後按一下&#x200B;**[!UICONTROL 儲存]**。

     ![選取節點的即時帳戶清單](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     請移至[帳戶清單](../accounts/account-lists.md)，以取得有關建立和發佈帳戶清單的詳細資訊。

_若要建立對象區段：_

1. 在左側導覽中，選擇「**[!UICONTROL 帳戶]** > **[!UICONTROL 客群]**」。

1. 按一下右上角的「**[!UICONTROL 建立客群]**」。

   ![建立對象區段](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. 請依照[Segmentation Service指南](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/account-audiences){target="_blank"}中所述的步驟操作。
