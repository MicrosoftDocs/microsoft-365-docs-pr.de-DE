---
title: Erstellen von DNS-Einträgen bei DNSMadeEasy für Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter DNSMadeEasy für Microsoft einrichten.
ms.openlocfilehash: 266f5e8460395ae10b9c430cf66e1f443126ff64
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646211"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="4f872-103">Erstellen von DNS-Einträgen bei DNSMadeEasy für Microsoft</span><span class="sxs-lookup"><span data-stu-id="4f872-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="4f872-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="4f872-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4f872-105">Wenn DNSMadeEasy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4f872-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4f872-106">Nachdem Sie diese Einträge bei DNSMadeEasy hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4f872-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="4f872-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4f872-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4f872-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="4f872-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4f872-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4f872-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4f872-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="4f872-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f872-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="4f872-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4f872-p104">Bei DNSMadeEasy-Konten wurde die Domäne, die Sie hinzugefügt haben, bei einer anderen Domänenregistrierungsstelle gekauft. DNSMadeEasy bietet keine Domänenregistrierungsdienste. Die Möglichkeit, sich bei DNSMadeEasy anzumelden und den DNS-Eintrag zu erstellen, ist als Nachweis des Besitzes ausreichend.</span><span class="sxs-lookup"><span data-stu-id="4f872-p104">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="4f872-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f872-p105">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="4f872-121">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f872-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="4f872-122">Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement (**+**) (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="4f872-123">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="4f872-124">Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4f872-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="4f872-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="4f872-125">**Name**</span></span> <br/> |<span data-ttu-id="4f872-126">**Wert**</span><span class="sxs-lookup"><span data-stu-id="4f872-126">**Value**</span></span> <br/> |<span data-ttu-id="4f872-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f872-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="4f872-128">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4f872-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4f872-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4f872-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="4f872-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="4f872-133">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="4f872-134">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="4f872-135">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f872-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4f872-136">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="4f872-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4f872-137">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="4f872-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4f872-138">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="4f872-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4f872-139">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4f872-140">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4f872-141">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4f872-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4f872-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4f872-145">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4f872-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4f872-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4f872-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4f872-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f872-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="4f872-149">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f872-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="4f872-150">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f872-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="4f872-152">Wählen Sie auf der Seite **Managed DNS** im Bereich **MX Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="4f872-153">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="4f872-155">Geben Sie im Bereich **Add MX Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4f872-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f872-156">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="4f872-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="4f872-157">**Name**</span></span>|<span data-ttu-id="4f872-158">**Server**</span><span class="sxs-lookup"><span data-stu-id="4f872-158">**Server**</span></span>|<span data-ttu-id="4f872-159">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="4f872-159">**MX Level**</span></span>|<span data-ttu-id="4f872-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f872-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4f872-161">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="4f872-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4f872-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4f872-163">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="4f872-164">**Hinweis:** Erhalten Sie Ihren \<*domain-key*\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="4f872-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="4f872-165">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="4f872-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4f872-166">10 </span><span class="sxs-lookup"><span data-stu-id="4f872-166">10</span></span>  <br/> <span data-ttu-id="4f872-167">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="4f872-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="4f872-168">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="4f872-170">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="4f872-172">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie alle Einträge, indem Sie sie alle auswählen.</span><span class="sxs-lookup"><span data-stu-id="4f872-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="4f872-174">Wenn Sie alle Einträge markiert sind, wählen Sie **Delete selected** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="4f872-176">Wählen Sie im Dialogfeld **Delete MX Records** den Befehl **Delete** aus, um Ihre Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="4f872-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4f872-178">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="4f872-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4f872-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4f872-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4f872-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f872-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="4f872-182">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f872-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="4f872-183">Wählen Sie auf der Seite **Managed DNS** im Bereich **CNAME Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="4f872-184">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="4f872-186">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f872-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="4f872-187">Geben Sie im Bereich **Add CNAME Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4f872-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="4f872-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="4f872-188">**Name**</span></span>|<span data-ttu-id="4f872-189">**Alias für**</span><span class="sxs-lookup"><span data-stu-id="4f872-189">**Alias to**</span></span>|<span data-ttu-id="4f872-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f872-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4f872-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4f872-191">autodiscover</span></span>  <br/> |<span data-ttu-id="4f872-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4f872-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="4f872-193">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-194">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-194">1800</span></span>  <br/> |
    |<span data-ttu-id="4f872-195">sip</span><span class="sxs-lookup"><span data-stu-id="4f872-195">sip</span></span>  <br/> |<span data-ttu-id="4f872-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f872-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f872-197">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-198">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-198">1800</span></span>  <br/> |
    |<span data-ttu-id="4f872-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4f872-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4f872-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f872-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f872-201">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-202">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-202">1800</span></span>  <br/> |
    |<span data-ttu-id="4f872-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4f872-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4f872-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="4f872-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="4f872-205">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-206">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-206">1800</span></span>  <br/> |
    |<span data-ttu-id="4f872-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4f872-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4f872-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4f872-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="4f872-209">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-210">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="4f872-212">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="4f872-214">Fügen Sie die vier anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f872-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="4f872-215">Wählen Sie im Abschnitt **CNAME Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4f872-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="4f872-216">Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4f872-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4f872-217">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="4f872-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4f872-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4f872-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f872-219">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="4f872-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4f872-220">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="4f872-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4f872-221">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="4f872-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4f872-222">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="4f872-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="4f872-223">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="4f872-223">Need examples?</span></span> <span data-ttu-id="4f872-224">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="4f872-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="4f872-225">Zum Überprüfen des SPF-Eintrags können Sie eines dieser[SPF-Überprüfungstools](../setup/domains-faq.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f872-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="4f872-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f872-p112">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="4f872-228">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f872-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="4f872-229">Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="4f872-230">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="4f872-232">Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4f872-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="4f872-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="4f872-233">**Name**</span></span>|<span data-ttu-id="4f872-234">**Wert**</span><span class="sxs-lookup"><span data-stu-id="4f872-234">**Value**</span></span>|<span data-ttu-id="4f872-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f872-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4f872-236">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4f872-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4f872-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4f872-238">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4f872-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4f872-239">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="4f872-241">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4f872-243">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="4f872-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4f872-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4f872-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4f872-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f872-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="4f872-247">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f872-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="4f872-248">Wählen Sie auf der Seite **Managed DNS** im Bereich **SRV Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="4f872-249">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="4f872-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="4f872-251">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f872-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="4f872-252">Geben Sie im Bereich **Add SRV Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4f872-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="4f872-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="4f872-253">**Name**</span></span>|<span data-ttu-id="4f872-254">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4f872-254">**Priority**</span></span>|<span data-ttu-id="4f872-255">**Weight**</span><span class="sxs-lookup"><span data-stu-id="4f872-255">**Weight**</span></span>|<span data-ttu-id="4f872-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="4f872-256">**Port**</span></span>|<span data-ttu-id="4f872-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="4f872-257">**Host**</span></span>|<span data-ttu-id="4f872-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4f872-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4f872-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4f872-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="4f872-260">100</span><span class="sxs-lookup"><span data-stu-id="4f872-260">100</span></span>  <br/> |<span data-ttu-id="4f872-261">1</span><span class="sxs-lookup"><span data-stu-id="4f872-261">1</span></span>  <br/> |<span data-ttu-id="4f872-262">443</span><span class="sxs-lookup"><span data-stu-id="4f872-262">443</span></span>  <br/> |<span data-ttu-id="4f872-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f872-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f872-264">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-265">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-265">1800</span></span>  <br/> |
    |<span data-ttu-id="4f872-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4f872-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="4f872-267">100</span><span class="sxs-lookup"><span data-stu-id="4f872-267">100</span></span>  <br/> |<span data-ttu-id="4f872-268">1</span><span class="sxs-lookup"><span data-stu-id="4f872-268">1</span></span>  <br/> |<span data-ttu-id="4f872-269">5061</span><span class="sxs-lookup"><span data-stu-id="4f872-269">5061</span></span>  <br/> |<span data-ttu-id="4f872-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f872-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f872-271">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f872-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4f872-272">1800</span><span class="sxs-lookup"><span data-stu-id="4f872-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="4f872-274">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="4f872-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="4f872-276">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f872-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="4f872-277">Wählen Sie im Abschnitt **SRV Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4f872-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="4f872-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4f872-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

