---
title: Erstellen von DNS-Einträgen bei DNSMadeEasy für Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter DNSMadeEasy für Microsoft einrichten.
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629683"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="20524-103">Erstellen von DNS-Einträgen bei DNSMadeEasy für Microsoft</span><span class="sxs-lookup"><span data-stu-id="20524-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="20524-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="20524-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="20524-105">Wenn DNSMadeEasy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="20524-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="20524-106">Nachdem Sie diese Einträge bei DNSMadeEasy hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="20524-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="20524-107">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="20524-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="20524-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine Änderung vorgenommen wurde, die Sie über das DNS-System des Internets aktualisiert haben. Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="20524-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="20524-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="20524-111">Add a TXT record for verification</span></span>
<span data-ttu-id="20524-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="20524-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="20524-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="20524-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20524-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="20524-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="20524-p104">Bei DNSMadeEasy-Konten wurde die Domäne, die Sie hinzugefügt haben, bei einer anderen Domänenregistrierungsstelle gekauft. DNSMadeEasy bietet keine Domänenregistrierungsdienste. Die Möglichkeit, sich bei DNSMadeEasy anzumelden und den DNS-Eintrag zu erstellen, ist als Nachweis des Besitzes ausreichend.</span><span class="sxs-lookup"><span data-stu-id="20524-p104">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="20524-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="20524-p105">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="20524-122">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20524-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="20524-123">Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement (**+**) (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="20524-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="20524-124">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="20524-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="20524-125">Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="20524-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="20524-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="20524-126">**Name**</span></span> <br/> |<span data-ttu-id="20524-127">**Wert**</span><span class="sxs-lookup"><span data-stu-id="20524-127">**Value**</span></span> <br/> |<span data-ttu-id="20524-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20524-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="20524-129">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="20524-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="20524-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="20524-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="20524-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle. [Wie finde ich diese?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="20524-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="20524-134">1800</span><span class="sxs-lookup"><span data-stu-id="20524-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="20524-135">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="20524-136">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="20524-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="20524-137">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="20524-137">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="20524-138">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="20524-138">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="20524-139">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="20524-139">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="20524-140">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="20524-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="20524-141">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="20524-142">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="20524-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine Änderung vorgenommen wurde, die Sie über das DNS-System des Internets aktualisiert haben. Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="20524-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="20524-146">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="20524-146">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="20524-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="20524-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="20524-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="20524-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="20524-150">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20524-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="20524-151">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20524-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="20524-153">Wählen Sie auf der Seite **Managed DNS** im Bereich **MX Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="20524-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="20524-154">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="20524-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="20524-156">Geben Sie im Bereich **Add MX Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="20524-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="20524-157">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="20524-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="20524-158">**Name**</span><span class="sxs-lookup"><span data-stu-id="20524-158">**Name**</span></span>|<span data-ttu-id="20524-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="20524-159">**Server**</span></span>|<span data-ttu-id="20524-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="20524-160">**MX Level**</span></span>|<span data-ttu-id="20524-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20524-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20524-162">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="20524-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="20524-163">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20524-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="20524-164">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="20524-p109">**Hinweis:** Rufen Sie \<Ihren *Domänenschlüssel* \> von Ihrem Microsoft-Konto ab. [Wie finde ich diese?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="20524-p109">**Note:** Get your \<*domain-key*\> from your Microsoft account. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="20524-167">10</span><span class="sxs-lookup"><span data-stu-id="20524-167">10</span></span>  <br/> <span data-ttu-id="20524-168">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="20524-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="20524-169">1800</span><span class="sxs-lookup"><span data-stu-id="20524-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="20524-171">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="20524-173">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie alle Einträge, indem Sie sie alle auswählen.</span><span class="sxs-lookup"><span data-stu-id="20524-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="20524-175">Wenn Sie alle Einträge markiert sind, wählen Sie **Delete selected** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="20524-177">Wählen Sie im Dialogfeld **Delete MX Records** den Befehl **Delete** aus, um Ihre Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="20524-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="20524-179">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="20524-179">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="20524-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="20524-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="20524-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="20524-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="20524-183">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20524-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="20524-184">Wählen Sie auf der Seite **Managed DNS** im Bereich **CNAME Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="20524-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="20524-185">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="20524-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="20524-187">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="20524-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="20524-188">Geben Sie im Bereich **Add CNAME Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="20524-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="20524-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="20524-189">**Name**</span></span>|<span data-ttu-id="20524-190">**Alias für**</span><span class="sxs-lookup"><span data-stu-id="20524-190">**Alias to**</span></span>|<span data-ttu-id="20524-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20524-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20524-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="20524-192">autodiscover</span></span>  <br/> |<span data-ttu-id="20524-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="20524-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="20524-194">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-195">1800</span><span class="sxs-lookup"><span data-stu-id="20524-195">1800</span></span>  <br/> |
    |<span data-ttu-id="20524-196">sip</span><span class="sxs-lookup"><span data-stu-id="20524-196">sip</span></span>  <br/> |<span data-ttu-id="20524-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="20524-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="20524-198">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-199">1800</span><span class="sxs-lookup"><span data-stu-id="20524-199">1800</span></span>  <br/> |
    |<span data-ttu-id="20524-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="20524-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="20524-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="20524-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="20524-202">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-203">1800</span><span class="sxs-lookup"><span data-stu-id="20524-203">1800</span></span>  <br/> |
    |<span data-ttu-id="20524-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="20524-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="20524-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="20524-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="20524-206">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-207">1800</span><span class="sxs-lookup"><span data-stu-id="20524-207">1800</span></span>  <br/> |
    |<span data-ttu-id="20524-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="20524-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="20524-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="20524-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="20524-210">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-211">1800</span><span class="sxs-lookup"><span data-stu-id="20524-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="20524-213">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="20524-215">Fügen Sie die vier anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="20524-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="20524-216">Wählen Sie im Abschnitt **CNAME Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="20524-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="20524-217">Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="20524-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="20524-218">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="20524-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="20524-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="20524-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20524-p111">Sie können für eine Domäne nicht mehr als einen TXT-Eintrag für SPF haben. Wenn Ihre Domäne über mehr als einen SPF-Eintrag verfügt, erhalten Sie sowohl e-Mail-Fehler als auch Zustellungs-und Spam Klassifikations Probleme. Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft. Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält. Benötigen Sie Beispiele? Sehen Sie sich diese [externen Domänennamen-System Einträge für Microsoft an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Zum Überprüfen des SPF-Eintrags können Sie eines dieser[SPF-Überprüfungstools](../setup/domains-faq.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="20524-p111">You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Microsoft. Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="20524-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="20524-p112">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="20524-229">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20524-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="20524-230">Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="20524-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="20524-231">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="20524-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="20524-233">Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="20524-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="20524-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="20524-234">**Name**</span></span>|<span data-ttu-id="20524-235">**Wert**</span><span class="sxs-lookup"><span data-stu-id="20524-235">**Value**</span></span>|<span data-ttu-id="20524-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20524-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20524-237">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="20524-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="20524-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="20524-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="20524-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="20524-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="20524-240">1800</span><span class="sxs-lookup"><span data-stu-id="20524-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="20524-242">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="20524-244">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="20524-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="20524-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="20524-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="20524-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="20524-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="20524-248">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20524-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="20524-249">Wählen Sie auf der Seite **Managed DNS** im Bereich **SRV Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="20524-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="20524-250">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="20524-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="20524-252">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="20524-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="20524-253">Geben Sie im Bereich **Add SRV Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="20524-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="20524-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="20524-254">**Name**</span></span>|<span data-ttu-id="20524-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="20524-255">**Priority**</span></span>|<span data-ttu-id="20524-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="20524-256">**Weight**</span></span>|<span data-ttu-id="20524-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="20524-257">**Port**</span></span>|<span data-ttu-id="20524-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="20524-258">**Host**</span></span>|<span data-ttu-id="20524-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20524-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20524-260">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="20524-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="20524-261">100</span><span class="sxs-lookup"><span data-stu-id="20524-261">100</span></span>  <br/> |<span data-ttu-id="20524-262">1</span><span class="sxs-lookup"><span data-stu-id="20524-262">1</span></span>  <br/> |<span data-ttu-id="20524-263">443</span><span class="sxs-lookup"><span data-stu-id="20524-263">443</span></span>  <br/> |<span data-ttu-id="20524-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="20524-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="20524-265">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-266">1800</span><span class="sxs-lookup"><span data-stu-id="20524-266">1800</span></span>  <br/> |
    |<span data-ttu-id="20524-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="20524-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="20524-268">100</span><span class="sxs-lookup"><span data-stu-id="20524-268">100</span></span>  <br/> |<span data-ttu-id="20524-269">1</span><span class="sxs-lookup"><span data-stu-id="20524-269">1</span></span>  <br/> |<span data-ttu-id="20524-270">5061</span><span class="sxs-lookup"><span data-stu-id="20524-270">5061</span></span>  <br/> |<span data-ttu-id="20524-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="20524-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="20524-272">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="20524-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="20524-273">1800</span><span class="sxs-lookup"><span data-stu-id="20524-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="20524-275">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="20524-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="20524-277">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="20524-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="20524-278">Wählen Sie im Abschnitt **SRV Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="20524-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="20524-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine Änderung vorgenommen wurde, die Sie über das DNS-System des Internets aktualisiert haben. Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="20524-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

