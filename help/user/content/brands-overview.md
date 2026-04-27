---
title: 使用品牌來產生內容並維持一致性
description: 定義品牌准則，以建立一致的內容 — 在Journey Optimizer B2B Edition中維持視覺識別、訊息一致性和真實的聲音。
badge: label="Beta" type="Informative"
feature: Content, Brand Identity
role: User
level: Beginner, Intermediate
exl-id: 83d210bc-a204-4b7e-8b7e-07b0ec5413b9
source-git-commit: a99560d6f32222f8912c7711ff1913777a1161b6
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 12%

---

# 使用品牌來產生內容並維持一致性 {#brands}

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_overview"
>title="開始使用品牌"
>abstract="建立並自訂您的品牌來定義您獨特的視覺和語言識別，同時更輕鬆地產生與您品牌風格和語調相符的內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_ai_menu"
>title="選取您的品牌"
>abstract="選擇您的品牌，以確保所有 AI 產生的內容都是量身打造，符合您品牌的規格和準則。"

品牌可協助定義&#x200B;_品牌識別_，並在確保以一致且有效的方式建立內容以準確代表您的品牌識別、價值和訊息方面發揮關鍵作用。 透過遵循清楚定義的品牌樣式，組織可以跨管道和接觸點維持一致和可辨識的品牌存在感，並強化其在目標受眾中的品牌認知度、信任度和忠誠度。

+++使用品牌的好處

您的組織可以透過在建立和評估內容中使用品牌來實現重大價值，例如：

* **一致的品牌識別** — 品牌指引是視覺和語言識別的基本藍圖。 它們定義讓品牌可辨識的核心元素，例如標誌、調色盤、印刷樣式、影像樣式和語調。 透過遵循這些准則，內容創作者可確保從網頁文案、社群媒體貼文到電子郵件行銷活動的所有行銷資料持續反映獨特的品牌個性和視覺識別。 這種一致性有助於加強品牌認知度，並在目標市場內建立信任。

* **一致的訊息和定位** — 品牌指引通常包含概述品牌價值主張、關鍵訊息支柱和定位宣告的訊息指引。 遵循這些方針，內容創作者就能確保其內容中的訊息符合整體品牌定位和價值主張。 這種訊息的一致性有助於強化其獨特的賣點和差異點，讓客戶更容易瞭解並連結品牌產品。

* **真實品牌語調和語調** — 品牌指引通常包含對語調、溝通風格和語言使用的詳細指引。 這些指引可協助內容創作者捕捉品牌個性，並打造正確的語調，不論是友好平易近人、專業且權威，或是有趣且機智。 在所有內容上維持一致的品牌語調，有助於為客戶提供更真實、更吸引人的品牌體驗。

* **視覺內聚力與品牌認知度** — 品牌指引為視覺元素（例如圖志、調色盤、印刷樣式、影像樣式和版面範本）提供清晰的規則和規格。 遵循這些准則可確保所有視覺內容保持一致和可識別的品牌美感。 這種視覺一致性有助於加強品牌認知度並與客戶建立信任，因為他們可以輕鬆識別內容並將內容與品牌建立關聯。

* **品牌權益與信譽維護** — 持續遵守品牌准則有助於維護和保護品牌的權益與聲譽。 當所有內容和行銷資料都準確地反映品牌識別、價值和訊息時，就會加強品牌可信度並鞏固其在市場中的地位。 這種公平性和聲譽可導致提高客戶忠誠度和宣傳活動，最終為品牌的長期成功做出貢獻。

+++

>[!AVAILABILITY]
>
>此功能目前以公開測試版的形式提供。
>
>您必須先取得[使用者合約](https://www.adobe.com/tw/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}，才能在Adobe Journey Optimizer B2B Edition中使用AI支援的功能。 如需詳細資訊，請聯絡您的 Adobe 代表。

已定義的品牌可為您的創意團隊提供當他們建立任何視覺或書面內容時使用的&#x200B;_真實來源_。 When these guidelines are compiled and the brand assets are shared, any team member or collaborator can create on-brand content for your product. To enable on-brand content creation in Journey Optimizer B2B Edition, complete these tasks:

1. Prepare your brand definition.

   * High-level brand characteristics
   * 寫作風格
   * Visual elements

1. Assemble this information in one or more PDF files.

1. Use the PDF file to [create the brand](./brands-manage-create.md#create-and-define-a-brand) in Journey Optimizer B2B Edition.

1. When it is ready for use, [publish the brand](./brands-manage-create.md#publish-the-brand).

1. Use the brand for [email content alignment](./content-evaluation.md#brand-alignment-score).
<!-- 
1. Use the brand to generate content. 
-->

>[!BEGINSHADEBOX]

## Brand-related permissions

Product administrators can enable access to the brand management and brand alignment features by assigning the **[!UICONTROL Manage brand kit]** or **[!UICONTROL Enable AI assistant]** resource permissions through the _Permissions_ UI in Adobe Experience Cloud.

1. In the Permissions app, go to the **[!UICONTROL Roles]** tab and select the desired [role](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/access-control/abac/permissions-ui/roles){target="_blank"}.

1. 按一下&#x200B;**[!UICONTROL 編輯]**&#x200B;以修改權限。

1. Add the **[!UICONTROL AI Assistant]** resource, then select **[!UICONTROL Manage brand kit]** or **[!UICONTROL Enable Ai assistant]**

   >[!NOTE]
   >
   >The **[!UICONTROL Enable Ai assistant]** permission provides read-only access to the **[!UICONTROL Brands]** library.

   ![Add AI Assitant permission for brands access](./assets/brands-aep-permissions.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]** to apply the changes.

   Permissions are automatically updated for any users that are already assigned to the role.

1. To assign this role to new users, select the **[!UICONTROL Users]** tab within the _[!UICONTROL Roles]_ dashboard and click **[!UICONTROL Add User]**.

   * Enter the user name and email address, or choose an existing user from the list.

     If the user is not yet created, refer to the [Experience Platform documentation](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/access-control/abac/permissions-ui/users){target="_blank"}.

   * Click **[!UICONTROL Save]** to apply the changes.

>[!ENDSHADEBOX]
