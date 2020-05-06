---
title: Erstellen von DNS-Einträgen bei WiX für Microsoft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei WiX für Microsoft einrichten.
ms.openlocfilehash: 6f88cc65ae19f747a9fc3740ea1578f30d18b5e2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048855"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="5347a-103">Erstellen von DNS-Einträgen bei WiX für Microsoft</span><span class="sxs-lookup"><span data-stu-id="5347a-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="5347a-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="5347a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5347a-105">[] Wenn Wix Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="5347a-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5347a-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="5347a-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="5347a-107">[Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="5347a-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="5347a-108">[Fügen Sie einen MX-Eintrag hinzu, damit e-Mails für Ihre Domäne an Microsoft gesendet werden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="5347a-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="5347a-109">[Fügen Sie die fünf CNAME-Einträge hinzu, die für Microsoft erforderlich sind](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="5347a-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="5347a-110">[Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="5347a-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="5347a-111">[Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="5347a-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="5347a-112">Nachdem Sie diese Einträge bei WiX hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="5347a-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5347a-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5347a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5347a-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="5347a-116">Add a TXT record for verification</span></span>
<span data-ttu-id="5347a-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="5347a-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="5347a-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="5347a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5347a-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="5347a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5347a-122">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="5347a-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="5347a-123">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5347a-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5347a-124">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="5347a-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="5347a-125">Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="5347a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5347a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="5347a-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5347a-127">**Host Name**</span></span> <br/> |<span data-ttu-id="5347a-128">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="5347a-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="5347a-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5347a-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="5347a-130">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="5347a-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="5347a-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5347a-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5347a-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5347a-132">**Note:** This is an example.</span></span> <span data-ttu-id="5347a-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5347a-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="5347a-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="5347a-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="5347a-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="5347a-136">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="5347a-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5347a-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5347a-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="5347a-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5347a-139">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="5347a-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5347a-140">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="5347a-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5347a-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="5347a-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="5347a-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5347a-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5347a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5347a-147">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5347a-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5347a-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="5347a-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="5347a-149">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="5347a-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="5347a-150">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5347a-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5347a-151">Wählen Sie auf der Seite **Meine Domänen** im Bereich **Postfächer** den Link **MX-Einträge konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="5347a-152">Wählen Sie in der Dropdownliste **Ihres e-Mail-Anbieters** die Option **Sonstiges** aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="5347a-153">Wählen Sie **+ Add other**aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="5347a-154">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="5347a-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="5347a-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5347a-155">**Host Name**</span></span>|<span data-ttu-id="5347a-156">**Points to**</span><span class="sxs-lookup"><span data-stu-id="5347a-156">**Points to**</span></span>|<span data-ttu-id="5347a-157">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="5347a-157">**Priority**</span></span>|<span data-ttu-id="5347a-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5347a-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5347a-159">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="5347a-159">Automatically populated</span></span> <br/> | <span data-ttu-id="5347a-160">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5347a-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5347a-161">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="5347a-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="5347a-162">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="5347a-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="5347a-163">0</span><span class="sxs-lookup"><span data-stu-id="5347a-163">0</span></span>  <br/> <span data-ttu-id="5347a-164">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="5347a-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="5347a-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-165">1 Hour</span></span>|
   
6. <span data-ttu-id="5347a-166">Wenn andere MX-Einträge aufgeführt sind, löschen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="5347a-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="5347a-167">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="5347a-168">Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5347a-169">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="5347a-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5347a-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="5347a-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="5347a-p109">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5347a-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5347a-173">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="5347a-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="5347a-174">Wählen Sie **+ Add other** in der Zeile **CNAME (Aliases)** des DNS-Editors für jeden CNAME-Eintrag aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="5347a-175">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="5347a-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="5347a-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5347a-176">**Host Name**</span></span>|<span data-ttu-id="5347a-177">**Points to**</span><span class="sxs-lookup"><span data-stu-id="5347a-177">**Points to**</span></span>|<span data-ttu-id="5347a-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5347a-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5347a-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5347a-179">autodiscover</span></span>  <br/> |<span data-ttu-id="5347a-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5347a-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="5347a-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="5347a-182">sip</span><span class="sxs-lookup"><span data-stu-id="5347a-182">sip</span></span>  <br/> |<span data-ttu-id="5347a-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5347a-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5347a-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="5347a-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5347a-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5347a-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5347a-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="5347a-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="5347a-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5347a-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5347a-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5347a-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="5347a-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="5347a-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5347a-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5347a-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5347a-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="5347a-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="5347a-194">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="5347a-195">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5347a-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5347a-196">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="5347a-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5347a-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="5347a-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5347a-198">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="5347a-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5347a-199">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="5347a-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5347a-200">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="5347a-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5347a-201">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="5347a-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="5347a-202">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="5347a-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="5347a-203">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5347a-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5347a-204">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="5347a-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="5347a-205">Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="5347a-206">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="5347a-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="5347a-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5347a-207">**Host Name**</span></span>|<span data-ttu-id="5347a-208">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="5347a-208">**TXT Value**</span></span>|<span data-ttu-id="5347a-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5347a-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5347a-210">[leer lassen]</span><span class="sxs-lookup"><span data-stu-id="5347a-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="5347a-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5347a-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5347a-212">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="5347a-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="5347a-213">TXT</span><span class="sxs-lookup"><span data-stu-id="5347a-213">TXT</span></span>  <br/> | <span data-ttu-id="5347a-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-214">1 Hour</span></span> |
   
5. <span data-ttu-id="5347a-215">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="5347a-216">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5347a-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5347a-217">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="5347a-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5347a-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="5347a-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="5347a-219">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="5347a-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="5347a-220">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5347a-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5347a-221">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="5347a-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="5347a-222">Wählen Sie **+ Add other** in der Zeile **SRV** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="5347a-223">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="5347a-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="5347a-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="5347a-224">**Service**</span></span>|<span data-ttu-id="5347a-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="5347a-225">**Protocol**</span></span>|<span data-ttu-id="5347a-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="5347a-226">**Name**</span></span>|<span data-ttu-id="5347a-227">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5347a-227">**Weight**</span></span>|<span data-ttu-id="5347a-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="5347a-228">**Port**</span></span>|<span data-ttu-id="5347a-229">**Target**</span><span class="sxs-lookup"><span data-stu-id="5347a-229">**Target**</span></span>|<span data-ttu-id="5347a-230">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="5347a-230">**Priority**</span></span>|<span data-ttu-id="5347a-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5347a-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5347a-232">sip</span><span class="sxs-lookup"><span data-stu-id="5347a-232">sip</span></span>  |<span data-ttu-id="5347a-233">tls</span><span class="sxs-lookup"><span data-stu-id="5347a-233">tls</span></span>  |<span data-ttu-id="5347a-234">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="5347a-234">Automatically populated</span></span> |<span data-ttu-id="5347a-235">1</span><span class="sxs-lookup"><span data-stu-id="5347a-235">1</span></span>  |<span data-ttu-id="5347a-236">443</span><span class="sxs-lookup"><span data-stu-id="5347a-236">443</span></span>   |<span data-ttu-id="5347a-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5347a-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="5347a-238">100</span><span class="sxs-lookup"><span data-stu-id="5347a-238">100</span></span> |<span data-ttu-id="5347a-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-239">1 Hour</span></span> |
|<span data-ttu-id="5347a-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="5347a-240">sipfed</span></span>|<span data-ttu-id="5347a-241">tcp</span><span class="sxs-lookup"><span data-stu-id="5347a-241">tcp</span></span> |<span data-ttu-id="5347a-242">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="5347a-242">Automatically populated</span></span>|<span data-ttu-id="5347a-243">1</span><span class="sxs-lookup"><span data-stu-id="5347a-243">1</span></span> |<span data-ttu-id="5347a-244">5061</span><span class="sxs-lookup"><span data-stu-id="5347a-244">5061</span></span> |<span data-ttu-id="5347a-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5347a-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="5347a-246">100</span><span class="sxs-lookup"><span data-stu-id="5347a-246">100</span></span> | <span data-ttu-id="5347a-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="5347a-247">1 Hour</span></span> |
   
5. <span data-ttu-id="5347a-248">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="5347a-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="5347a-249">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5347a-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="5347a-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5347a-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

