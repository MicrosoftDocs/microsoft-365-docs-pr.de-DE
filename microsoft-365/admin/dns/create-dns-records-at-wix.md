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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei WiX für Microsoft einrichten.
ms.openlocfilehash: b5fe216e65954bbcbdd9a1da223258a8362743ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400292"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="ac6c4-103">Erstellen von DNS-Einträgen bei WiX für Microsoft</span><span class="sxs-lookup"><span data-stu-id="ac6c4-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="ac6c4-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ac6c4-105">[] Wenn Wix Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ac6c4-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="ac6c4-107">[Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="ac6c4-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="ac6c4-108">[Fügen Sie einen MX-Eintrag hinzu, damit e-Mails für Ihre Domäne an Microsoft gesendet werden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="ac6c4-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="ac6c4-109">[Fügen Sie die fünf CNAME-Einträge hinzu, die für Microsoft erforderlich sind](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="ac6c4-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="ac6c4-110">[Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="ac6c4-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="ac6c4-111">[Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="ac6c4-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="ac6c4-112">Nachdem Sie diese Einträge bei WiX hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ac6c4-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac6c4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ac6c4-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ac6c4-116">Add a TXT record for verification</span></span>
<span data-ttu-id="ac6c4-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ac6c4-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="ac6c4-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac6c4-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ac6c4-122">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ac6c4-123">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ac6c4-124">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ac6c4-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ac6c4-125">Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="ac6c4-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="ac6c4-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-127">**Host Name**</span></span> <br/> |<span data-ttu-id="ac6c4-128">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="ac6c4-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="ac6c4-130">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="ac6c4-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="ac6c4-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ac6c4-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ac6c4-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-132">**Note:** This is an example.</span></span> <span data-ttu-id="ac6c4-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="ac6c4-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ac6c4-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="ac6c4-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="ac6c4-136">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ac6c4-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ac6c4-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ac6c4-139">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ac6c4-140">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ac6c4-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="ac6c4-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="ac6c4-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ac6c4-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac6c4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ac6c4-147">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ac6c4-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ac6c4-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="ac6c4-149">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ac6c4-150">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ac6c4-151">Wählen Sie auf der Seite **Meine Domänen** im Bereich **Postfächer** den Link **MX-Einträge konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="ac6c4-152">Wählen Sie in der Dropdownliste **Ihres e-Mail-Anbieters** die Option **Sonstiges** aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="ac6c4-153">Wählen Sie **+ Add other**aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="ac6c4-154">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="ac6c4-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="ac6c4-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-155">**Host Name**</span></span>|<span data-ttu-id="ac6c4-156">**Points to**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-156">**Points to**</span></span>|<span data-ttu-id="ac6c4-157">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-157">**Priority**</span></span>|<span data-ttu-id="ac6c4-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac6c4-159">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="ac6c4-159">Automatically populated</span></span> <br/> | <span data-ttu-id="ac6c4-160">*\<domain-key\>*. Mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ac6c4-161">**Hinweis:** Holen Sie sich Ihr *\<domain-key\>* Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="ac6c4-162">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ac6c4-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="ac6c4-163">0</span><span class="sxs-lookup"><span data-stu-id="ac6c4-163">0</span></span>  <br/> <span data-ttu-id="ac6c4-164">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="ac6c4-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="ac6c4-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-165">1 Hour</span></span>|
   
6. <span data-ttu-id="ac6c4-166">Wenn andere MX-Einträge aufgeführt sind, löschen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="ac6c4-167">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="ac6c4-168">Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ac6c4-169">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="ac6c4-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ac6c4-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ac6c4-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="ac6c4-p109">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="ac6c4-173">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ac6c4-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ac6c4-174">Wählen Sie **+ Add other** in der Zeile **CNAME (Aliases)** des DNS-Editors für jeden CNAME-Eintrag aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="ac6c4-175">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="ac6c4-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="ac6c4-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-176">**Host Name**</span></span>|<span data-ttu-id="ac6c4-177">**Points to**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-177">**Points to**</span></span>|<span data-ttu-id="ac6c4-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac6c4-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ac6c4-179">autodiscover</span></span>  <br/> |<span data-ttu-id="ac6c4-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="ac6c4-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="ac6c4-182">sip</span><span class="sxs-lookup"><span data-stu-id="ac6c4-182">sip</span></span>  <br/> |<span data-ttu-id="ac6c4-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ac6c4-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="ac6c4-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ac6c4-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ac6c4-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="ac6c4-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="ac6c4-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ac6c4-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ac6c4-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ac6c4-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="ac6c4-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="ac6c4-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ac6c4-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ac6c4-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="ac6c4-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="ac6c4-194">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ac6c4-195">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ac6c4-196">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="ac6c4-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ac6c4-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ac6c4-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac6c4-198">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ac6c4-199">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ac6c4-200">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="ac6c4-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ac6c4-201">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="ac6c4-202">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ac6c4-203">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ac6c4-204">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ac6c4-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ac6c4-205">Wählen Sie **+ Add other** in der txt-Zeile **(Text)** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="ac6c4-206">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="ac6c4-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="ac6c4-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-207">**Host Name**</span></span>|<span data-ttu-id="ac6c4-208">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-208">**TXT Value**</span></span>|<span data-ttu-id="ac6c4-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac6c4-210">[leer lassen]</span><span class="sxs-lookup"><span data-stu-id="ac6c4-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="ac6c4-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ac6c4-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ac6c4-212">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="ac6c4-213">TXT</span><span class="sxs-lookup"><span data-stu-id="ac6c4-213">TXT</span></span>  <br/> | <span data-ttu-id="ac6c4-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-214">1 Hour</span></span> |
   
5. <span data-ttu-id="ac6c4-215">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ac6c4-216">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ac6c4-217">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="ac6c4-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ac6c4-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ac6c4-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="ac6c4-219">Im ersten Schritt navigieren Sie über [diesen Link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) zu Ihrer Domänenseite bei Wix.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="ac6c4-220">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ac6c4-221">Klicken Sie auf der Seite **Meine Domänen** im Bereich **erweitert** auf die Schaltfläche **DNS bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ac6c4-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="ac6c4-222">Wählen Sie **+ Add other** in der Zeile **SRV** des DNS-Editors aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="ac6c4-223">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="ac6c4-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="ac6c4-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-224">**Service**</span></span>|<span data-ttu-id="ac6c4-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-225">**Protocol**</span></span>|<span data-ttu-id="ac6c4-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-226">**Name**</span></span>|<span data-ttu-id="ac6c4-227">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-227">**Weight**</span></span>|<span data-ttu-id="ac6c4-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-228">**Port**</span></span>|<span data-ttu-id="ac6c4-229">**Target**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-229">**Target**</span></span>|<span data-ttu-id="ac6c4-230">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-230">**Priority**</span></span>|<span data-ttu-id="ac6c4-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac6c4-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac6c4-232">sip</span><span class="sxs-lookup"><span data-stu-id="ac6c4-232">sip</span></span>  |<span data-ttu-id="ac6c4-233">tls</span><span class="sxs-lookup"><span data-stu-id="ac6c4-233">tls</span></span>  |<span data-ttu-id="ac6c4-234">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="ac6c4-234">Automatically populated</span></span> |<span data-ttu-id="ac6c4-235">1 </span><span class="sxs-lookup"><span data-stu-id="ac6c4-235">1</span></span>  |<span data-ttu-id="ac6c4-236">443</span><span class="sxs-lookup"><span data-stu-id="ac6c4-236">443</span></span>   |<span data-ttu-id="ac6c4-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="ac6c4-238">100</span><span class="sxs-lookup"><span data-stu-id="ac6c4-238">100</span></span> |<span data-ttu-id="ac6c4-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-239">1 Hour</span></span> |
|<span data-ttu-id="ac6c4-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="ac6c4-240">sipfed</span></span>|<span data-ttu-id="ac6c4-241">tcp</span><span class="sxs-lookup"><span data-stu-id="ac6c4-241">tcp</span></span> |<span data-ttu-id="ac6c4-242">Automatisch aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="ac6c4-242">Automatically populated</span></span>|<span data-ttu-id="ac6c4-243">1 </span><span class="sxs-lookup"><span data-stu-id="ac6c4-243">1</span></span> |<span data-ttu-id="ac6c4-244">5061</span><span class="sxs-lookup"><span data-stu-id="ac6c4-244">5061</span></span> |<span data-ttu-id="ac6c4-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac6c4-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="ac6c4-246">100</span><span class="sxs-lookup"><span data-stu-id="ac6c4-246">100</span></span> | <span data-ttu-id="ac6c4-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="ac6c4-247">1 Hour</span></span> |
   
5. <span data-ttu-id="ac6c4-248">Wählen Sie die Schaltfläche " **DNS speichern** " oben im DNS-Editor aus.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="ac6c4-249">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac6c4-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="ac6c4-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac6c4-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

