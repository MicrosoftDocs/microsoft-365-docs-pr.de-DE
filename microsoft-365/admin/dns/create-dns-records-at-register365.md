---
title: Erstellen von DNS-Einträgen für Office 365 bei Register365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Register365 für Office 365 einrichten.
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362850"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="5146c-103">Erstellen von DNS-Einträgen für Office 365 bei Register365</span><span class="sxs-lookup"><span data-stu-id="5146c-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="5146c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="5146c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5146c-105">Wenn Register365 Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="5146c-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="5146c-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="5146c-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="5146c-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="5146c-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="5146c-108">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="5146c-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="5146c-109">Hinzufügen der sechs für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="5146c-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="5146c-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="5146c-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="5146c-111">Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="5146c-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="5146c-112">Nachdem Sie diese Einträge bei Office 365 hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="5146c-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5146c-113">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5146c-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5146c-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5146c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5146c-117">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="5146c-117">Add a TXT record for verification</span></span>
<span data-ttu-id="5146c-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5146c-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5146c-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="5146c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5146c-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="5146c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5146c-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5146c-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="5146c-126">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5146c-127">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-127">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="5146c-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5146c-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5146c-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5146c-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="5146c-131">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="5146c-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="5146c-132">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5146c-133">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5146c-133">**Host name**</span></span>|<span data-ttu-id="5146c-134">**Type**</span><span class="sxs-lookup"><span data-stu-id="5146c-134">**Type**</span></span>|<span data-ttu-id="5146c-135">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="5146c-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5146c-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5146c-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5146c-137">TXT</span><span class="sxs-lookup"><span data-stu-id="5146c-137">TXT</span></span>  <br/> |<span data-ttu-id="5146c-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5146c-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5146c-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="5146c-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="5146c-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5146c-143">Select **Save**.</span></span>
    
    <span data-ttu-id="5146c-144">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-144">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie speichern aus.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="5146c-146">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5146c-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5146c-147">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5146c-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5146c-148">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="5146c-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5146c-149">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="5146c-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5146c-150">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5146c-151">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5146c-152">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5146c-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5146c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5146c-156">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="5146c-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5146c-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5146c-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5146c-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5146c-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="5146c-161">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5146c-162">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-162">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="5146c-164">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Mail exchange records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="5146c-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5146c-165">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5146c-166">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5146c-166">**Host name**</span></span>|<span data-ttu-id="5146c-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5146c-167">**Priority**</span></span>|<span data-ttu-id="5146c-168">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="5146c-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5146c-169">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5146c-170">1</span><span class="sxs-lookup"><span data-stu-id="5146c-170">1</span></span>  <br/> <span data-ttu-id="5146c-171">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5146c-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5146c-172">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5146c-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5146c-173">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="5146c-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="5146c-174">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="5146c-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="5146c-176">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5146c-176">Select **Save**.</span></span>
    
    <span data-ttu-id="5146c-177">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-177">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie speichern aus.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="5146c-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="5146c-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="5146c-181">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5146c-181">Select **Save**.</span></span>
    
    <span data-ttu-id="5146c-182">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-182">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie speichern aus.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5146c-184">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="5146c-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5146c-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5146c-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5146c-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5146c-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="5146c-189">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5146c-190">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-190">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="5146c-192">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **A, CNAME, AAAA, TXT and NS records** in den Feldern für die neuen Einträge die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="5146c-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5146c-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5146c-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="5146c-194">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="5146c-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="5146c-195">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5146c-196">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5146c-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="5146c-197">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5146c-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="5146c-198">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5146c-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5146c-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5146c-199">autodiscover</span></span>  <br/> |<span data-ttu-id="5146c-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="5146c-200">CNAME</span></span>  <br/> |<span data-ttu-id="5146c-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5146c-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5146c-202">sip</span><span class="sxs-lookup"><span data-stu-id="5146c-202">sip</span></span>  <br/> |<span data-ttu-id="5146c-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="5146c-203">CNAME</span></span>  <br/> |<span data-ttu-id="5146c-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5146c-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5146c-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5146c-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5146c-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="5146c-206">CNAME</span></span>  <br/> |<span data-ttu-id="5146c-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5146c-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5146c-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5146c-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5146c-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="5146c-209">CNAME</span></span>  <br/> |<span data-ttu-id="5146c-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5146c-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5146c-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5146c-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5146c-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="5146c-212">CNAME</span></span>  <br/> |<span data-ttu-id="5146c-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5146c-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="5146c-215">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5146c-215">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5146c-217">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="5146c-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5146c-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5146c-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5146c-219">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="5146c-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5146c-220">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="5146c-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5146c-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5146c-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5146c-222">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5146c-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5146c-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5146c-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="5146c-226">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5146c-227">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-227">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="5146c-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5146c-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5146c-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5146c-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="5146c-231">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="5146c-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="5146c-232">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5146c-233">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5146c-233">**Host name**</span></span>|<span data-ttu-id="5146c-234">**Type**</span><span class="sxs-lookup"><span data-stu-id="5146c-234">**Type**</span></span>|<span data-ttu-id="5146c-235">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="5146c-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5146c-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5146c-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5146c-237">TXT</span><span class="sxs-lookup"><span data-stu-id="5146c-237">TXT</span></span>  <br/> |<span data-ttu-id="5146c-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5146c-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="5146c-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="5146c-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="5146c-241">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5146c-241">Select **Save**.</span></span>
    
    <span data-ttu-id="5146c-242">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-242">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie speichern aus.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5146c-244">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="5146c-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5146c-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5146c-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5146c-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5146c-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="5146c-249">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="5146c-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5146c-250">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-250">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="5146c-252">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Service records** in den Feldern für die neuen Einträge die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="5146c-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5146c-253">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5146c-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="5146c-254">**Name**</span></span>|<span data-ttu-id="5146c-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5146c-255">**Priority**</span></span>|<span data-ttu-id="5146c-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5146c-256">**Weight**</span></span>|<span data-ttu-id="5146c-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="5146c-257">**Port**</span></span>|<span data-ttu-id="5146c-258">**Result**</span><span class="sxs-lookup"><span data-stu-id="5146c-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5146c-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5146c-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="5146c-260">100</span><span class="sxs-lookup"><span data-stu-id="5146c-260">100</span></span>  <br/> |<span data-ttu-id="5146c-261">1</span><span class="sxs-lookup"><span data-stu-id="5146c-261">1</span></span>  <br/> |<span data-ttu-id="5146c-262">443</span><span class="sxs-lookup"><span data-stu-id="5146c-262">443</span></span>  <br/> |<span data-ttu-id="5146c-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5146c-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5146c-264">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5146c-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5146c-265">100</span><span class="sxs-lookup"><span data-stu-id="5146c-265">100</span></span>  <br/> |<span data-ttu-id="5146c-266">1</span><span class="sxs-lookup"><span data-stu-id="5146c-266">1</span></span>  <br/> |<span data-ttu-id="5146c-267">5061</span><span class="sxs-lookup"><span data-stu-id="5146c-267">5061</span></span>  <br/> |<span data-ttu-id="5146c-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5146c-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Eingeben von Werten im Abschnitt "Diensteinträge"](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="5146c-270">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5146c-270">Select **Save**.</span></span>
    
    <span data-ttu-id="5146c-271">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="5146c-271">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie speichern aus.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="5146c-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5146c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
