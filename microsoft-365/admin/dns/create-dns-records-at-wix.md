---
title: Erstellen von DNS-Einträgen bei WiX für Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei WiX für Microsoft einrichten.
ms.openlocfilehash: 01317f7e2da87b532c93f12269fd65b7d4fe2dd6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656879"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="b71fd-103">Erstellen von DNS-Einträgen bei WiX für Microsoft</span><span class="sxs-lookup"><span data-stu-id="b71fd-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="b71fd-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b71fd-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b71fd-105">[] Wenn Wix Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b71fd-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="b71fd-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="b71fd-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="b71fd-107">[Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="b71fd-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="b71fd-108">[Fügen Sie einen MX-Eintrag hinzu, damit e-Mails für Ihre Domäne an Microsoft gesendet werden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="b71fd-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="b71fd-109">[Fügen Sie die fünf CNAME-Einträge hinzu, die für Microsoft erforderlich sind](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="b71fd-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="b71fd-110">[Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="b71fd-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="b71fd-111">[Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="b71fd-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="b71fd-112">Nachdem Sie diese Einträge bei WiX hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b71fd-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b71fd-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b71fd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b71fd-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b71fd-116">Add a TXT record for verification</span></span>
<span data-ttu-id="b71fd-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="b71fd-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="b71fd-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="b71fd-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b71fd-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="b71fd-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="b71fd-122">WiX unterstützt keine DNS-Einträge für Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="b71fd-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="b71fd-123">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="b71fd-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b71fd-124">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b71fd-125">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="b71fd-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b71fd-126">Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="b71fd-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b71fd-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="b71fd-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="b71fd-128">Host Name</span></span> <br/> | <span data-ttu-id="b71fd-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="b71fd-129">TXT Value</span></span> <br/> | <span data-ttu-id="b71fd-130">TTL</span><span class="sxs-lookup"><span data-stu-id="b71fd-130">TTL</span></span> <br/> |
   |<span data-ttu-id="b71fd-131">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="b71fd-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="b71fd-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b71fd-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b71fd-133">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b71fd-133">**Note:** This is an example.</span></span> <span data-ttu-id="b71fd-134">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b71fd-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="b71fd-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b71fd-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="b71fd-136">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="b71fd-137">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b71fd-138">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b71fd-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b71fd-139">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="b71fd-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b71fd-140">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b71fd-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b71fd-141">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="b71fd-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b71fd-142">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="b71fd-143">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="b71fd-144">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b71fd-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b71fd-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b71fd-148">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b71fd-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="b71fd-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="b71fd-150">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="b71fd-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b71fd-151">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b71fd-152">Wählen Sie auf der Seite **Meine Domänen** im Bereich **Postfächer** den Link **MX-Einträge konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="b71fd-153">Wählen Sie in der Dropdownliste **Ihres e-Mail-Anbieters** die Option **Sonstiges** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="b71fd-154">Wählen Sie **+ Add other** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="b71fd-155">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="b71fd-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b71fd-156">Hostname</span><span class="sxs-lookup"><span data-stu-id="b71fd-156">Host Name</span></span> | <span data-ttu-id="b71fd-157">Points to </span><span class="sxs-lookup"><span data-stu-id="b71fd-157">Points to</span></span> | <span data-ttu-id="b71fd-158">Priority</span><span class="sxs-lookup"><span data-stu-id="b71fd-158">Priority</span></span> | <span data-ttu-id="b71fd-159">TTL</span><span class="sxs-lookup"><span data-stu-id="b71fd-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="b71fd-160">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="b71fd-160">Automatically populated</span></span> <br/> | <span data-ttu-id="b71fd-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b71fd-162">**Hinweis:** Holen Sie sich Ihr  *\<domain-key\>*  Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="b71fd-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="b71fd-163">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b71fd-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="b71fd-164">0</span><span class="sxs-lookup"><span data-stu-id="b71fd-164">0</span></span>  <br/> <span data-ttu-id="b71fd-165">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="b71fd-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="b71fd-166">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-166">1 Hour</span></span>|
   
6. <span data-ttu-id="b71fd-167">Wenn andere MX-Einträge aufgeführt sind, löschen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="b71fd-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="b71fd-168">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="b71fd-169">Wählen Sie im Dialogfeld Bestätigung die Option **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b71fd-170">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b71fd-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b71fd-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="b71fd-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="b71fd-p109">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b71fd-174">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="b71fd-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b71fd-175">Wählen Sie **+ Add other** in der Zeile **CNAME (Aliases)** des DNS-Editors für jeden CNAME-Eintrag aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="b71fd-176">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="b71fd-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b71fd-177">Hostname</span><span class="sxs-lookup"><span data-stu-id="b71fd-177">Host Name</span></span> | <span data-ttu-id="b71fd-178">Points to </span><span class="sxs-lookup"><span data-stu-id="b71fd-178">Points to</span></span> | <span data-ttu-id="b71fd-179">TTL</span><span class="sxs-lookup"><span data-stu-id="b71fd-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="b71fd-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b71fd-180">autodiscover</span></span>  <br/> |<span data-ttu-id="b71fd-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="b71fd-182">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="b71fd-183">sip</span><span class="sxs-lookup"><span data-stu-id="b71fd-183">sip</span></span>  <br/> |<span data-ttu-id="b71fd-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b71fd-185">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="b71fd-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b71fd-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b71fd-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="b71fd-188">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="b71fd-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b71fd-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b71fd-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b71fd-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="b71fd-191">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="b71fd-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b71fd-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b71fd-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="b71fd-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="b71fd-195">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b71fd-196">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b71fd-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b71fd-197">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b71fd-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b71fd-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="b71fd-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b71fd-199">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="b71fd-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b71fd-200">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="b71fd-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b71fd-201">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="b71fd-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b71fd-202">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="b71fd-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="b71fd-203">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="b71fd-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b71fd-204">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b71fd-205">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="b71fd-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b71fd-206">Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="b71fd-207">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="b71fd-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b71fd-208">Hostname</span><span class="sxs-lookup"><span data-stu-id="b71fd-208">Host Name</span></span> | <span data-ttu-id="b71fd-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="b71fd-209">TXT Value</span></span> | <span data-ttu-id="b71fd-210">TTL</span><span class="sxs-lookup"><span data-stu-id="b71fd-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="b71fd-211">[leer lassen]</span><span class="sxs-lookup"><span data-stu-id="b71fd-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="b71fd-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b71fd-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b71fd-213">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="b71fd-214">TXT</span><span class="sxs-lookup"><span data-stu-id="b71fd-214">TXT</span></span>  <br/> | <span data-ttu-id="b71fd-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-215">1 Hour</span></span> |
   
5. <span data-ttu-id="b71fd-216">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b71fd-217">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b71fd-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b71fd-218">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="b71fd-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b71fd-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="b71fd-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="b71fd-220">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="b71fd-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b71fd-221">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b71fd-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b71fd-222">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="b71fd-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b71fd-223">Wählen Sie **+ Add other** in der Zeile **SRV** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="b71fd-224">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="b71fd-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b71fd-225">Dienst</span><span class="sxs-lookup"><span data-stu-id="b71fd-225">Service</span></span> | <span data-ttu-id="b71fd-226">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b71fd-226">Protocol</span></span> | <span data-ttu-id="b71fd-227">Name</span><span class="sxs-lookup"><span data-stu-id="b71fd-227">Name</span></span> | <span data-ttu-id="b71fd-228">Schriftbreite</span><span class="sxs-lookup"><span data-stu-id="b71fd-228">Weight</span></span> | <span data-ttu-id="b71fd-229">Port</span><span class="sxs-lookup"><span data-stu-id="b71fd-229">Port</span></span> | <span data-ttu-id="b71fd-230">Ziel</span><span class="sxs-lookup"><span data-stu-id="b71fd-230">Target</span></span> | <span data-ttu-id="b71fd-231">Priority</span><span class="sxs-lookup"><span data-stu-id="b71fd-231">Priority</span></span> | <span data-ttu-id="b71fd-232">TTL</span><span class="sxs-lookup"><span data-stu-id="b71fd-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="b71fd-233">sip</span><span class="sxs-lookup"><span data-stu-id="b71fd-233">sip</span></span>  |<span data-ttu-id="b71fd-234">tls</span><span class="sxs-lookup"><span data-stu-id="b71fd-234">tls</span></span>  |<span data-ttu-id="b71fd-235">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="b71fd-235">Automatically populated</span></span> |<span data-ttu-id="b71fd-236">1 </span><span class="sxs-lookup"><span data-stu-id="b71fd-236">1</span></span>  |<span data-ttu-id="b71fd-237">443</span><span class="sxs-lookup"><span data-stu-id="b71fd-237">443</span></span>   |<span data-ttu-id="b71fd-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="b71fd-239">100</span><span class="sxs-lookup"><span data-stu-id="b71fd-239">100</span></span> |<span data-ttu-id="b71fd-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-240">1 Hour</span></span> |
   |<span data-ttu-id="b71fd-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="b71fd-241">sipfed</span></span>|<span data-ttu-id="b71fd-242">tcp</span><span class="sxs-lookup"><span data-stu-id="b71fd-242">tcp</span></span> |<span data-ttu-id="b71fd-243">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="b71fd-243">Automatically populated</span></span>|<span data-ttu-id="b71fd-244">1 </span><span class="sxs-lookup"><span data-stu-id="b71fd-244">1</span></span> |<span data-ttu-id="b71fd-245">5061</span><span class="sxs-lookup"><span data-stu-id="b71fd-245">5061</span></span> |<span data-ttu-id="b71fd-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b71fd-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="b71fd-247">100</span><span class="sxs-lookup"><span data-stu-id="b71fd-247">100</span></span> | <span data-ttu-id="b71fd-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b71fd-248">1 Hour</span></span> |
   
5. <span data-ttu-id="b71fd-249">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="b71fd-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b71fd-250">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b71fd-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b71fd-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b71fd-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
