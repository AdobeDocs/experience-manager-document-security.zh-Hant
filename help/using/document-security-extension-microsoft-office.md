---
title: Microsoft® Office 適用的 AEM Document Security Extension 介紹
description: 使用Microsoft&amp； reg； Office適用的Document Security Extension，您可以將預先定義的機密性設定套用至Microsoft&amp； reg； Office檔案。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 68%

---

# Microsoft® Office 適用的 AEM Document Security Extension 介紹{#introduction-to-aem-document-security-extension-for-microsoft-office}

Microsoft® Office 適用的 Adobe® Experience Manager Document Security Extension 可確保，只有您授權的人才能使用含有您智慧財產的 Word、Excel 和 PowerPoint 檔案。您可以使用 Microsoft® Office 適用的 Document Security Extension，將預先定義的機密設定套用至您的檔案。

Microsoft® Office適用的Document Security Extension增強了Adobe Experience Manager Forms的LiveCycleRights Management和Document Security。 它可保護Office檔案，並可讓授權的使用者根據已建立的機密性設定，存取受原則保護的檔案。

## Document Security 如何保護智慧財產 {#how-document-security-protects-intellectual-property}

Document Security 可確保只有您授權的人員才能使用包含您智慧財產的檔案。使用 Document Security，即可以透過使用機密性原則來保護檔案。*原則*&#x200B;是包含機密性設定和授權使用者清單的資訊集合。您在原則中指明的設定可確定收件者如何使用您套用原則的檔案。例如，您可以指明收件人是否可以列印或複製文字或儲存變更。

Document Security 管理員和使用者會建立原則。管理員會建立適用於所有授權使用者的組織原則。管理員或原則組專員也可建立稱為&#x200B;*原則組*&#x200B;且適用於部分使用者的原則群組。使用者可以建立他們自己可以使用的原則。管理員、原則組專員和使用者會使用Document Security網頁來建立原則。

雖然原則儲存在Document Security中，但您可以透過Word、Excel或PowerPoint將其套用至檔案。 當您將原則套用於檔案時，檔案所含資訊將受到原則所指明的機密性設定的保護。當您分發受原則保護的檔案時，只有獲授權的收件者才能存取其內容。

使用原則來保護檔案，可以讓您持續控制該檔案，即使在分發文件之後也是如此。您可以稽核事件以追蹤收件者何時及如何使用您的檔案。 您也可以變更原則、防止使用者繼續存取檔案，以及變更附加至檔案的原則。

## 原則如何運作 {#how-policies-work}

原則包含有關授權使用者的資訊，以及套用至智慧財產的機密性設定。Document Security可辨識包含在已連結LDAP或Active Directory清單中的使用者。 使用者也可以是被邀請註冊 Document Security 的人，或管理員為他們建立帳戶的人。

原則中的機密性設定可確定收件人如何使用受該原則保護的檔案。例如，原則會指明收件人是否能列印檔案、將內容複製到其他檔案，或是否可儲存變更至受保護的檔案。原則還可以為不同使用者指明不同的機密性設定。

當您將原則套用於檔案時，檔案所含資訊將受到原則所指明的機密性設定的保護。當您分發文件時，Document Security 會對嘗試開啟檔案的收件人進行驗證，並根據原則中指定的權限來授權存取權。

將原則套用到檔案後，可以隨時變更原則的機密性設定。您可以在使用者收到檔案後，新增或移除獲授權的使用者或變更使用者的許可權。 套用至檔案的原則可以變更。 而且，檔案的存取權可以撤銷，這樣擁有該檔案副本的任何人都無法再開啟。

如果原則准許離線存取，則收件人也可以在原則指定的時限內離線使用受原則保護的檔案 (沒有有效網際網路或網絡連線)。

## 受原則保護的檔案如何運作 {#how-policy-protected-files-work}

若要讓使用者開啟並使用受原則保護的Word、Excel和PowerPoint檔案，原則必須包含使用者作為收件者。 或者，它必須允許匿名存取。 使用者必須安裝Microsoft® Office適用的Document Security Extension。 若要將受原則保護的檔案提供給沒有Microsoft® Office適用的Document Security Extension的人，您可以為他們提供軟體副本。 或者，您可以告訴他們如何從您的網站下載。 如果您沒有安裝程序，可以從[下載頁面](https://experienceleague.adobe.com/en/docs/experience-manager-document-security/using/download-installer)下載。

當使用者嘗試開啟受原則保護的檔案時，Microsoft® Office適用的Document Security Extension會連線至Document Security，以驗證使用者。 如果將 Document Security 設為稽核檔案使用情況，則使用者會看到通知並指明正在稽核檔案使用情況。文件全性會確定授予使用者哪些檔案權限，然後使用者可以根據原則設定使用檔案，但前提為：

* 在原則中指定的有效期限。
* 直到管理員或套用原則的人撤銷檔案存取權或變更原則為止。

  如果套用原則的人變更原則或撤銷檔案存取權，使用者的檔案權限會變更或移除，即使使用者擁有該檔案也一樣。如果檔案本身被撤銷，使用者可能會收到 URL 以取得更新版本。

  如果原則允許離線存取，使用者可以在指定的離線租期內，不透過網際網路或網路連線開啟受原則保護的檔案。 在離線租期結束時，使用者必須上線並與 Document Security 同步處理，這樣便會展開新的租期。

  如果原則允許離線存取，使用者可以在指定的離線租期內，不透過網際網路或網路連線開啟受原則保護的檔案。 活動 (例如嘗試開啟新檔案的活動) 也將與原始檔案一樣進行稽核和記錄。

## 使用 Document Security 來保護您的檔案 {#using-document-security-to-protect-your-files}

您可在各種情況下使用原則來保護檔案。

例如，生產商正在接受新產品零件提供商的標單。生產商必須為投標人提供他們完成標單所需的專有資訊。生產商可使用 Document Security 的原則來保護檔案；該原則是用來允許投標者開啟文件並查看資訊。但是，投標者將無法變更、列印或複製檔案；如果沒有權限，任何人都無法開啟檔案。

接受投標後，生產商會更新原則以授予中標者許可權，讓他們可以在本機列印、複製和儲存變更。 生產商也會移除未中標者，撤銷其開啟檔案的許可權。

生產商與得標者合作時，他們的工程師會變更檔案中的部分設計規格。為了發布新規格，生產商會撤銷部分檔案的存取權並發布新版本。當得標者的工程師嘗試開啟檔案時，他們會看到一個訊息指出檔案存取權已被撤銷。這個訊息含有一個 URL，讓他們下載檔案的新版本。

## 其他資訊 {#additional-information}

下表資源可以幫助您了解更多有關 AEM Document Security：

<table >
 <tbody>
  <tr>
   <th><p>關於後述資訊：</p> </th>
   <th><p>請參閱</p> </th>
  </tr>
  <tr>
   <td><p>AEM Forms 管理員說明</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">管理員說明</a>，或在「Document Security」管理頁面上，按一下頁面右上角的「說明」連結。</p> </td>
  </tr>
  <tr>
   <td><p>Patch 更新、技術提示，以及有關此產品版的其他資訊</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home#support">Experience Cloud 技術支援</a></p> </td>
  </tr>
 </tbody>
</table>
