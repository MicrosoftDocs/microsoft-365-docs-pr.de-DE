---
title: Erstellen von DNS-Einträgen für Office 365 bei Dreamhost
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter DreamHost für Office 365 einrichten.
ms.openlocfilehash: 201452bc68f82138c08e2054452747a900ed0e6b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349486"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="58107-103">Erstellen von DNS-Einträgen für Office 365 bei Dreamhost</span><span class="sxs-lookup"><span data-stu-id="58107-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="58107-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="58107-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="58107-105">[] Wenn DreamHost Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="58107-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="58107-106">Nachdem Sie diese Einträge bei DreamHost hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="58107-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="58107-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="58107-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="58107-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="58107-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="58107-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="58107-111">Add a TXT record for verification</span></span>
<span data-ttu-id="58107-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="58107-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="58107-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="58107-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58107-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="58107-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="58107-p104">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="58107-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="58107-120">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="58107-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="58107-122">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="58107-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="58107-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="58107-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="58107-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="58107-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="58107-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="58107-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="58107-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="58107-127">**Name**</span></span>|<span data-ttu-id="58107-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="58107-128">**Type**</span></span>|<span data-ttu-id="58107-129">**Wert**</span><span class="sxs-lookup"><span data-stu-id="58107-129">**Value**</span></span>|<span data-ttu-id="58107-130">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="58107-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58107-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="58107-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="58107-132">TXT</span><span class="sxs-lookup"><span data-stu-id="58107-132">TXT</span></span>  <br/> |<span data-ttu-id="58107-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="58107-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="58107-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="58107-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="58107-137">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-137">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="58107-139">Wählen Sie **jetzt Record hinzufügen!**</span><span class="sxs-lookup"><span data-stu-id="58107-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="58107-141">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="58107-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="58107-142">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="58107-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="58107-143">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="58107-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="58107-144">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="58107-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="58107-145">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="58107-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="58107-146">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="58107-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="58107-147">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="58107-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="58107-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="58107-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="58107-151">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="58107-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="58107-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="58107-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="58107-153">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="58107-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="58107-p107">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="58107-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="58107-157">Wählen Sie auf der Seite **Dashboard** die Option **e-Mail**und dann **benutzerdefiniertes MX**aus.</span><span class="sxs-lookup"><span data-stu-id="58107-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="58107-159">Wählen Sie im Abschnitt **e-Mail-Zustellung verwalten** in der Spalte **Aktionen** die Option **Bearbeiten** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="58107-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="58107-161">Geben Sie im Abschnitt **Custom MX Record** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="58107-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="58107-162">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="58107-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="58107-163">(Wenn weitere MX-Einträge vorhanden sind, markieren Sie diese Einträge zum Löschen.)</span><span class="sxs-lookup"><span data-stu-id="58107-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="58107-164">**MX-Eintrag (erforderlich)**</span><span class="sxs-lookup"><span data-stu-id="58107-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="58107-165">0  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="58107-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="58107-166">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="58107-p108">Die 0 ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="58107-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="58107-169">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="58107-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="58107-170">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="58107-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DreamHost-BP-configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="58107-172">Wählen Sie **diese Domäne ändern aus, um benutzerdefinierte MX-Einträge jetzt zu verwenden!**</span><span class="sxs-lookup"><span data-stu-id="58107-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="58107-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="58107-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="58107-176">Wenn Sie alle Einträge gelöscht haben, wählen Sie **jetzt Ihre benutzerdefinierten MX-Einträge aktualisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="58107-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="58107-178">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="58107-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="58107-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="58107-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="58107-180">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="58107-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="58107-p110">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="58107-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="58107-184">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="58107-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="58107-186">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="58107-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="58107-188">Geben Sie im Abschnitt **Add a custom DNS record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="58107-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="58107-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="58107-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="58107-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="58107-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="58107-191">**Name**</span><span class="sxs-lookup"><span data-stu-id="58107-191">**Name**</span></span>|<span data-ttu-id="58107-192">**Typ**</span><span class="sxs-lookup"><span data-stu-id="58107-192">**Type**</span></span>|<span data-ttu-id="58107-193">**Wert**</span><span class="sxs-lookup"><span data-stu-id="58107-193">**Value**</span></span>|<span data-ttu-id="58107-194">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="58107-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58107-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="58107-195">autodiscover</span></span>  <br/> |<span data-ttu-id="58107-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="58107-196">CNAME</span></span>  <br/> |<span data-ttu-id="58107-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="58107-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="58107-198">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-199">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="58107-200">sip</span><span class="sxs-lookup"><span data-stu-id="58107-200">sip</span></span>  <br/> |<span data-ttu-id="58107-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="58107-201">CNAME</span></span>  <br/> |<span data-ttu-id="58107-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58107-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="58107-203">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-204">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="58107-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="58107-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="58107-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="58107-206">CNAME</span></span>  <br/> |<span data-ttu-id="58107-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58107-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="58107-208">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-209">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="58107-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="58107-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="58107-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="58107-211">CNAME</span></span>  <br/> |<span data-ttu-id="58107-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="58107-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="58107-213">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-214">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="58107-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="58107-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="58107-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="58107-216">CNAME</span></span>  <br/> |<span data-ttu-id="58107-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="58107-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="58107-218">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-219">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-219">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="58107-221">Wählen Sie **jetzt Record hinzufügen!**</span><span class="sxs-lookup"><span data-stu-id="58107-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="58107-223">Verwenden Sie die beiden vorherigen Schritte und die Werte aus den anderen fünf Zeilen in der Tabelle, und fügen Sie jeden der anderen fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="58107-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="58107-224">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="58107-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="58107-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="58107-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="58107-226">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="58107-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="58107-227">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="58107-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="58107-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="58107-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="58107-229">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="58107-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="58107-230">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="58107-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="58107-p112">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="58107-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="58107-234">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="58107-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="58107-236">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="58107-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="58107-238">Geben Sie im Abschnitt **Add a custom DNS record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="58107-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="58107-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="58107-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="58107-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="58107-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="58107-241">**Name**</span><span class="sxs-lookup"><span data-stu-id="58107-241">**Name**</span></span>|<span data-ttu-id="58107-242">**Typ**</span><span class="sxs-lookup"><span data-stu-id="58107-242">**Type**</span></span>|<span data-ttu-id="58107-243">**Wert**</span><span class="sxs-lookup"><span data-stu-id="58107-243">**Value**</span></span>|<span data-ttu-id="58107-244">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="58107-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58107-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="58107-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="58107-246">TXT</span><span class="sxs-lookup"><span data-stu-id="58107-246">TXT</span></span>  <br/> |<span data-ttu-id="58107-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="58107-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="58107-248">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="58107-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="58107-249">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-249">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="58107-251">Wählen Sie **jetzt Record hinzufügen!**</span><span class="sxs-lookup"><span data-stu-id="58107-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="58107-253">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die beiden vorherigen Schritte unter Verwendung der Werte aus der zweiten Zeile in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="58107-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="58107-254">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="58107-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="58107-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="58107-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="58107-256">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="58107-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="58107-p113">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="58107-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="58107-260">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="58107-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="58107-262">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="58107-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="58107-264">Geben Sie im Abschnitt **Add a custom DNS record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="58107-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="58107-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="58107-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="58107-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="58107-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="58107-267">**Name**</span><span class="sxs-lookup"><span data-stu-id="58107-267">**Name**</span></span>|<span data-ttu-id="58107-268">**Typ**</span><span class="sxs-lookup"><span data-stu-id="58107-268">**Type**</span></span>|<span data-ttu-id="58107-269">**Wert**</span><span class="sxs-lookup"><span data-stu-id="58107-269">**Value**</span></span>|<span data-ttu-id="58107-270">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="58107-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58107-271">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="58107-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="58107-272">SRV</span><span class="sxs-lookup"><span data-stu-id="58107-272">SRV</span></span>  <br/> |<span data-ttu-id="58107-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="58107-273">100 1 443</span></span>  <br/> <span data-ttu-id="58107-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58107-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="58107-275">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-276">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="58107-277">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="58107-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="58107-278">SRV</span><span class="sxs-lookup"><span data-stu-id="58107-278">SRV</span></span>  <br/> |<span data-ttu-id="58107-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="58107-279">100 1 5061</span></span>  <br/> <span data-ttu-id="58107-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="58107-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="58107-281">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="58107-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="58107-282">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="58107-282">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="58107-284">Wählen Sie **jetzt Record hinzufügen!**.</span><span class="sxs-lookup"><span data-stu-id="58107-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="58107-286">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die beiden vorherigen Schritte unter Verwendung der Werte aus der zweiten Zeile in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="58107-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="58107-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="58107-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
