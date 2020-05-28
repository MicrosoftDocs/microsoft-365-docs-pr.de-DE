---
title: Erstellen von DNS-Einträgen bei DreamHost für Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter DreamHost for Microsoft einrichten.
ms.openlocfilehash: 4b321138892cb4a7b5f67c37ed66f3baf0f6c45a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400509"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="7610f-103">Erstellen von DNS-Einträgen bei DreamHost für Microsoft</span><span class="sxs-lookup"><span data-stu-id="7610f-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="7610f-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="7610f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7610f-105">[] Wenn DreamHost Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7610f-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="7610f-106">Nachdem Sie diese Einträge bei DreamHost hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="7610f-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="7610f-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7610f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7610f-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="7610f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7610f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7610f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7610f-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="7610f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7610f-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="7610f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7610f-p104">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7610f-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7610f-119">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7610f-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7610f-121">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7610f-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7610f-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7610f-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7610f-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7610f-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7610f-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7610f-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7610f-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="7610f-126">**Name**</span></span>|<span data-ttu-id="7610f-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="7610f-127">**Type**</span></span>|<span data-ttu-id="7610f-128">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7610f-128">**Value**</span></span>|<span data-ttu-id="7610f-129">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="7610f-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7610f-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7610f-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7610f-131">TXT</span><span class="sxs-lookup"><span data-stu-id="7610f-131">TXT</span></span>  <br/> |<span data-ttu-id="7610f-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7610f-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7610f-133">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7610f-133">**Note:** This is an example.</span></span> <span data-ttu-id="7610f-134">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7610f-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7610f-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="7610f-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7610f-136">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-136">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="7610f-138">Wählen Sie **jetzt Record hinzufügen!**</span><span class="sxs-lookup"><span data-stu-id="7610f-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="7610f-140">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7610f-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7610f-141">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="7610f-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7610f-142">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="7610f-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7610f-143">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="7610f-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7610f-144">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7610f-145">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7610f-146">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7610f-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7610f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7610f-150">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7610f-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7610f-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7610f-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7610f-152">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7610f-p107">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7610f-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7610f-156">Wählen Sie auf der Seite **Dashboard** die Option **e-Mail**und dann **benutzerdefiniertes MX**aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="7610f-158">Wählen Sie im Abschnitt **e-Mail-Zustellung verwalten** in der Spalte **Aktionen** die Option **Bearbeiten** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7610f-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="7610f-160">Geben Sie im Abschnitt **Custom MX Record** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7610f-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="7610f-161">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7610f-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7610f-162">(Wenn weitere MX-Einträge vorhanden sind, markieren Sie diese Einträge zum Löschen.)</span><span class="sxs-lookup"><span data-stu-id="7610f-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="7610f-163">**MX-Eintrag (erforderlich)**</span><span class="sxs-lookup"><span data-stu-id="7610f-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="7610f-164">0 *\<domain-key\>* . Mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7610f-165">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7610f-p108">Die 0 ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="7610f-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="7610f-168">**Hinweis:** Holen Sie sich Ihr *\<domain-key\>* Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="7610f-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="7610f-169">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="7610f-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DreamHost-BP-configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="7610f-171">Wählen Sie **diese Domäne ändern aus, um benutzerdefinierte MX-Einträge jetzt zu verwenden!**</span><span class="sxs-lookup"><span data-stu-id="7610f-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="7610f-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="7610f-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="7610f-175">Wenn Sie alle Einträge gelöscht haben, wählen Sie **jetzt Ihre benutzerdefinierten MX-Einträge aktualisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="7610f-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7610f-177">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="7610f-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7610f-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7610f-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7610f-179">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7610f-p110">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7610f-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7610f-183">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7610f-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7610f-185">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7610f-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7610f-187">Geben Sie im Abschnitt **Add a custom DNS record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7610f-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7610f-188">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7610f-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7610f-189">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7610f-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7610f-190">**Name**</span><span class="sxs-lookup"><span data-stu-id="7610f-190">**Name**</span></span>|<span data-ttu-id="7610f-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="7610f-191">**Type**</span></span>|<span data-ttu-id="7610f-192">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7610f-192">**Value**</span></span>|<span data-ttu-id="7610f-193">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="7610f-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7610f-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7610f-194">autodiscover</span></span>  <br/> |<span data-ttu-id="7610f-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="7610f-195">CNAME</span></span>  <br/> |<span data-ttu-id="7610f-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7610f-197">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-198">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7610f-199">sip</span><span class="sxs-lookup"><span data-stu-id="7610f-199">sip</span></span>  <br/> |<span data-ttu-id="7610f-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="7610f-200">CNAME</span></span>  <br/> |<span data-ttu-id="7610f-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7610f-202">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-203">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7610f-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7610f-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7610f-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="7610f-205">CNAME</span></span>  <br/> |<span data-ttu-id="7610f-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7610f-207">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-208">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7610f-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7610f-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7610f-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="7610f-210">CNAME</span></span>  <br/> |<span data-ttu-id="7610f-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7610f-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7610f-212">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-213">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7610f-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7610f-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7610f-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="7610f-215">CNAME</span></span>  <br/> |<span data-ttu-id="7610f-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7610f-217">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-218">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-218">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="7610f-220">Wählen Sie **jetzt Record hinzufügen!**</span><span class="sxs-lookup"><span data-stu-id="7610f-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="7610f-222">Verwenden Sie die beiden vorherigen Schritte und die Werte aus den anderen fünf Zeilen in der Tabelle, und fügen Sie jeden der anderen fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="7610f-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7610f-223">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="7610f-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7610f-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7610f-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7610f-225">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="7610f-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7610f-226">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="7610f-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7610f-227">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="7610f-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7610f-228">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="7610f-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="7610f-229">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7610f-p112">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7610f-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7610f-233">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7610f-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7610f-235">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7610f-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7610f-237">Geben Sie im Abschnitt **Add a custom DNS record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7610f-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7610f-238">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7610f-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7610f-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7610f-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7610f-240">**Name**</span><span class="sxs-lookup"><span data-stu-id="7610f-240">**Name**</span></span>|<span data-ttu-id="7610f-241">**Type**</span><span class="sxs-lookup"><span data-stu-id="7610f-241">**Type**</span></span>|<span data-ttu-id="7610f-242">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7610f-242">**Value**</span></span>|<span data-ttu-id="7610f-243">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="7610f-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7610f-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7610f-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7610f-245">TXT</span><span class="sxs-lookup"><span data-stu-id="7610f-245">TXT</span></span>  <br/> |<span data-ttu-id="7610f-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7610f-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7610f-247">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="7610f-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7610f-248">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-248">(This field is optional.)</span></span>  <br/> |
   
   ![DreamHost-BP-configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="7610f-250">Wählen Sie **jetzt Record hinzufügen!**</span><span class="sxs-lookup"><span data-stu-id="7610f-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="7610f-252">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die beiden vorherigen Schritte unter Verwendung der Werte aus der zweiten Zeile in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="7610f-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7610f-253">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="7610f-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7610f-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7610f-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7610f-255">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7610f-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7610f-p113">Navigieren Sie zuerst über [diesen Link](https://panel.dreamhost.com/) zu Ihrer Domänenseite bei DreamHost. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7610f-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7610f-259">Wählen Sie auf der Seite **Dashboard** die Option **Domänen**aus, und verwalten Sie dann **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7610f-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7610f-261">Wählen Sie auf der Seite **Domänen verwalten** im Abschnitt **Domäne** die Option **DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7610f-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7610f-263">Geben Sie im Abschnitt **Add a custom DNS record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7610f-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7610f-264">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7610f-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7610f-265">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7610f-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7610f-266">**Name**</span><span class="sxs-lookup"><span data-stu-id="7610f-266">**Name**</span></span>|<span data-ttu-id="7610f-267">**Type**</span><span class="sxs-lookup"><span data-stu-id="7610f-267">**Type**</span></span>|<span data-ttu-id="7610f-268">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7610f-268">**Value**</span></span>|<span data-ttu-id="7610f-269">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="7610f-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7610f-270">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7610f-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="7610f-271">SRV</span><span class="sxs-lookup"><span data-stu-id="7610f-271">SRV</span></span>  <br/> |<span data-ttu-id="7610f-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="7610f-272">100 1 443</span></span>  <br/> <span data-ttu-id="7610f-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7610f-274">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-275">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7610f-276">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7610f-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7610f-277">SRV</span><span class="sxs-lookup"><span data-stu-id="7610f-277">SRV</span></span>  <br/> |<span data-ttu-id="7610f-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="7610f-278">100 1 5061</span></span>  <br/> <span data-ttu-id="7610f-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7610f-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="7610f-280">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7610f-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7610f-281">(Dieses Feld ist optional.)</span><span class="sxs-lookup"><span data-stu-id="7610f-281">(This field is optional.)</span></span>  <br/> |
   
    ![DreamHost-BP-configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="7610f-283">Wählen Sie **jetzt Record hinzufügen!**.</span><span class="sxs-lookup"><span data-stu-id="7610f-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="7610f-285">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die beiden vorherigen Schritte unter Verwendung der Werte aus der zweiten Zeile in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="7610f-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="7610f-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7610f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
