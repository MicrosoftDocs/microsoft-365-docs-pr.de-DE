---
title: Erstellen von DNS-Einträgen für Office 365 bei DNSMadeEasy
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei DNSMadeEasy für Office 365 einrichten.
ms.openlocfilehash: 29bdf78e3f9993267c5f0be3b107981bb9dd3fe3
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211799"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="a7e6a-103">Erstellen von DNS-Einträgen für Office 365 bei DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="a7e6a-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="a7e6a-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7e6a-105">Wenn DNSMadeEasy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a7e6a-106">Nachdem Sie diese Einträge bei DNSMadeEasy hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a7e6a-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7e6a-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7e6a-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a7e6a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a7e6a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e6a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a7e6a-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7e6a-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a7e6a-p104">Bei DNSMadeEasy-Konten wurde die Domäne, die Sie hinzugefügt haben, bei einer anderen Domänenregistrierungsstelle gekauft. DNSMadeEasy bietet keine Domänenregistrierungsdienste. Die Möglichkeit, sich bei DNSMadeEasy anzumelden und den DNS-Eintrag zu erstellen, ist als Nachweis des Besitzes ausreichend.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p104">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="a7e6a-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p105">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a7e6a-122">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="a7e6a-123">Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement (**+**) (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="a7e6a-124">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="a7e6a-125">Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="a7e6a-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-126">**Name**</span></span> <br/> |<span data-ttu-id="a7e6a-127">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-127">**Value**</span></span> <br/> |<span data-ttu-id="a7e6a-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="a7e6a-129">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a7e6a-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a7e6a-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a7e6a-p106">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="a7e6a-134">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="a7e6a-135">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="a7e6a-136">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7e6a-137">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a7e6a-138">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7e6a-139">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a7e6a-140">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a7e6a-141">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a7e6a-142">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7e6a-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a7e6a-146">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="a7e6a-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a7e6a-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e6a-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a7e6a-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a7e6a-150">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="a7e6a-151">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="a7e6a-153">Wählen Sie auf der Seite **Managed DNS** im Bereich **MX Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="a7e6a-154">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="a7e6a-156">Geben Sie im Bereich **Add MX Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a7e6a-157">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="a7e6a-158">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-158">**Name**</span></span>|<span data-ttu-id="a7e6a-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-159">**Server**</span></span>|<span data-ttu-id="a7e6a-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-160">**MX Level**</span></span>|<span data-ttu-id="a7e6a-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e6a-162">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="a7e6a-163">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7e6a-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a7e6a-164">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a7e6a-p109">**Hinweis:** Rufen Sie Ihren \<*Domänen-Schlüssel*\> aus Ihrem Office 365-Konto ab. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p109">**Note:** Get your \<*domain-key*\> from your Office 365 account. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="a7e6a-167">10</span><span class="sxs-lookup"><span data-stu-id="a7e6a-167">10</span></span>  <br/> <span data-ttu-id="a7e6a-168">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="a7e6a-169">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="a7e6a-171">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="a7e6a-173">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie alle Einträge, indem Sie sie alle auswählen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="a7e6a-175">Wenn Sie alle Einträge markiert sind, wählen Sie **Delete selected** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="a7e6a-177">Wählen Sie im Dialogfeld **Delete MX Records** den Befehl **Delete** aus, um Ihre Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a7e6a-179">Fügen Sie die für Office 365 erforderlichen fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a7e6a-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e6a-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a7e6a-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a7e6a-183">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="a7e6a-184">Wählen Sie auf der Seite **Managed DNS** im Bereich **CNAME Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="a7e6a-185">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="a7e6a-187">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="a7e6a-188">Geben Sie im Bereich **Add CNAME Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="a7e6a-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-189">**Name**</span></span>|<span data-ttu-id="a7e6a-190">**Alias für**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-190">**Alias to**</span></span>|<span data-ttu-id="a7e6a-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a7e6a-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a7e6a-192">autodiscover</span></span>  <br/> |<span data-ttu-id="a7e6a-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a7e6a-194">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-195">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-195">1800</span></span>  <br/> |
    |<span data-ttu-id="a7e6a-196">sip</span><span class="sxs-lookup"><span data-stu-id="a7e6a-196">sip</span></span>  <br/> |<span data-ttu-id="a7e6a-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a7e6a-198">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-199">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-199">1800</span></span>  <br/> |
    |<span data-ttu-id="a7e6a-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a7e6a-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a7e6a-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a7e6a-202">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-203">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-203">1800</span></span>  <br/> |
    |<span data-ttu-id="a7e6a-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a7e6a-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a7e6a-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="a7e6a-206">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-207">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-207">1800</span></span>  <br/> |
    |<span data-ttu-id="a7e6a-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a7e6a-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a7e6a-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="a7e6a-210">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-211">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="a7e6a-213">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="a7e6a-215">Fügen Sie die vier anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="a7e6a-216">Wählen Sie im Abschnitt **CNAME Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="a7e6a-217">Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7e6a-218">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="a7e6a-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7e6a-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e6a-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e6a-p111">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es bei Ihrer Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Office 365 keinen neuen, sondern fügen Sie die erforderlichen Office 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Sehen Sie sich die folgenden [Externen DNS-Einträge für Office 365 an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p111">You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="a7e6a-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p112">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a7e6a-229">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="a7e6a-230">Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="a7e6a-231">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="a7e6a-233">Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="a7e6a-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-234">**Name**</span></span>|<span data-ttu-id="a7e6a-235">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-235">**Value**</span></span>|<span data-ttu-id="a7e6a-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a7e6a-237">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a7e6a-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7e6a-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a7e6a-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a7e6a-240">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="a7e6a-242">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a7e6a-244">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="a7e6a-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a7e6a-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e6a-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a7e6a-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="a7e6a-248">Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="a7e6a-249">Wählen Sie auf der Seite **Managed DNS** im Bereich **SRV Records** das Steuerelement **(+)** (**Add new**) aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="a7e6a-250">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a7e6a-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="a7e6a-252">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a7e6a-253">Geben Sie im Bereich **Add SRV Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="a7e6a-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-254">**Name**</span></span>|<span data-ttu-id="a7e6a-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-255">**Priority**</span></span>|<span data-ttu-id="a7e6a-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-256">**Weight**</span></span>|<span data-ttu-id="a7e6a-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-257">**Port**</span></span>|<span data-ttu-id="a7e6a-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-258">**Host**</span></span>|<span data-ttu-id="a7e6a-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e6a-260">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a7e6a-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="a7e6a-261">100</span><span class="sxs-lookup"><span data-stu-id="a7e6a-261">100</span></span>  <br/> |<span data-ttu-id="a7e6a-262">1</span><span class="sxs-lookup"><span data-stu-id="a7e6a-262">1</span></span>  <br/> |<span data-ttu-id="a7e6a-263">443</span><span class="sxs-lookup"><span data-stu-id="a7e6a-263">443</span></span>  <br/> |<span data-ttu-id="a7e6a-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a7e6a-265">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-266">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-266">1800</span></span>  <br/> |
    |<span data-ttu-id="a7e6a-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a7e6a-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a7e6a-268">100</span><span class="sxs-lookup"><span data-stu-id="a7e6a-268">100</span></span>  <br/> |<span data-ttu-id="a7e6a-269">1</span><span class="sxs-lookup"><span data-stu-id="a7e6a-269">1</span></span>  <br/> |<span data-ttu-id="a7e6a-270">5061</span><span class="sxs-lookup"><span data-stu-id="a7e6a-270">5061</span></span>  <br/> |<span data-ttu-id="a7e6a-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a7e6a-272">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="a7e6a-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e6a-273">1800</span><span class="sxs-lookup"><span data-stu-id="a7e6a-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="a7e6a-275">Wählen Sie **Submit** aus.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="a7e6a-277">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a7e6a-278">Wählen Sie im Abschnitt **SRV Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a7e6a-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

