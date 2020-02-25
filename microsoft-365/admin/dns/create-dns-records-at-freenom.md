---
title: Erstellen von DNS-Einträgen für Office 365 bei Freenom
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Freenom für Office 365 einrichten.
ms.openlocfilehash: a1396964c7dc9c279589a6020e0c741fd0cb29d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244773"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="72a67-103">Erstellen von DNS-Einträgen für Office 365 bei Freenom</span><span class="sxs-lookup"><span data-stu-id="72a67-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="72a67-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="72a67-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="72a67-p101">Die Freenom-Website unterstützt keine SRV-Einträge. Das bedeutet, dass mehrere Features von Skype for Business Online und Outlook Web App nicht funktionieren. Unabhängig vom verwendeten Office 365-Plan bestehen erhebliche Diensteinschränkungen, und es kann sinnvoll sein, zu einem anderen DNS-Hostinganbieter zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="72a67-p101">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="72a67-107">Wenn Sie trotz dieser Diensteinschränkungen Ihre Office 365-DNS-Einträge bei Freenom selbst verwalten möchten, folgen Sie den Schritten in diesem Artikel, um die Domäne zu überprüfen und DNS-Einträge für E-Mail und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="72a67-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="72a67-108">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="72a67-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="72a67-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="72a67-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="72a67-112">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="72a67-112">Add a TXT record for verification</span></span>
<span data-ttu-id="72a67-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="72a67-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="72a67-p103">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="72a67-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72a67-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="72a67-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="72a67-118">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="72a67-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="72a67-119">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="72a67-119">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="72a67-121">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="72a67-123">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="72a67-125">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="72a67-127">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **TXT** aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="72a67-129">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="72a67-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="72a67-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="72a67-130">**Name**</span></span>|<span data-ttu-id="72a67-131">**Typ**</span><span class="sxs-lookup"><span data-stu-id="72a67-131">**Type**</span></span>|<span data-ttu-id="72a67-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="72a67-132">**TTL**</span></span>|<span data-ttu-id="72a67-133">**Target**</span><span class="sxs-lookup"><span data-stu-id="72a67-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="72a67-134">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="72a67-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="72a67-135">TXT</span><span class="sxs-lookup"><span data-stu-id="72a67-135">TXT</span></span>  <br/> |<span data-ttu-id="72a67-136">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="72a67-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="72a67-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="72a67-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Freenom TXT values for verification](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="72a67-142">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="72a67-144">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="72a67-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="72a67-145">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="72a67-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="72a67-146">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="72a67-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="72a67-147">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="72a67-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="72a67-148">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="72a67-149">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="72a67-150">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="72a67-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="72a67-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="72a67-154">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="72a67-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="72a67-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="72a67-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="72a67-156">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="72a67-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="72a67-157">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="72a67-157">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="72a67-159">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="72a67-161">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="72a67-163">Legen Sie den Namen dient für Ihre Domäne auf die standardmäßigen Freenom Namenserver.</span><span class="sxs-lookup"><span data-stu-id="72a67-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="72a67-164">Wählen Sie **Verwaltungs Tools**aus, und wählen Sie dann Namen **Server**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="72a67-166">Stellen Sie sicher, dass **Standardnamen Server verwenden** ausgewählt ist, und wählen Sie dann Namen von Namen **Servern ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="72a67-168">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom wählen Sie Manage Freenom DNS aus.](../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="72a67-170">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **MX** aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="72a67-172">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="72a67-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="72a67-173">**Name**</span><span class="sxs-lookup"><span data-stu-id="72a67-173">**Name**</span></span>|<span data-ttu-id="72a67-174">**Typ**</span><span class="sxs-lookup"><span data-stu-id="72a67-174">**Type**</span></span>|<span data-ttu-id="72a67-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="72a67-175">**TTL**</span></span>|<span data-ttu-id="72a67-176">**Target**</span><span class="sxs-lookup"><span data-stu-id="72a67-176">**Target**</span></span>|<span data-ttu-id="72a67-177">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="72a67-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="72a67-178">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="72a67-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="72a67-179">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="72a67-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="72a67-180">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-181">\<Domain-Key\>. Mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="72a67-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="72a67-182">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="72a67-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="72a67-183">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="72a67-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="72a67-184">10 </span><span class="sxs-lookup"><span data-stu-id="72a67-184">10</span></span>  <br/> <span data-ttu-id="72a67-185">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="72a67-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="72a67-187">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="72a67-189">Wenn es weitere MX-Einträge gibt, löschen Sie sie alle: Wählen Sie für jeden Eintrag Delete (Löschen) aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="72a67-190">Wählen Sie für jeden Datensatz **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-190">For each record, select **Delete**.</span></span> <span data-ttu-id="72a67-191">Wenn die Nachricht möchten **Sie diesen Eintrag wirklich entfernen?** angezeigt wird, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="72a67-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="72a67-192">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="72a67-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="72a67-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="72a67-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="72a67-194">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="72a67-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="72a67-195">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="72a67-195">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="72a67-197">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="72a67-199">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="72a67-201">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom wählen Sie Manage Freenom DNS aus.](../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="72a67-203">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **SNAME** aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="72a67-p113">Erstellen Sie den ersten CNAME-Eintrag. Geben Sie dann in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="72a67-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="72a67-207">**Name**</span><span class="sxs-lookup"><span data-stu-id="72a67-207">**Name**</span></span>|<span data-ttu-id="72a67-208">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="72a67-208">**Record type**</span></span>|<span data-ttu-id="72a67-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="72a67-209">**TTL**</span></span>|<span data-ttu-id="72a67-210">**Target**</span><span class="sxs-lookup"><span data-stu-id="72a67-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="72a67-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="72a67-211">autodiscover</span></span>  <br/> |<span data-ttu-id="72a67-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="72a67-212">CNAME</span></span>  <br/> |<span data-ttu-id="72a67-213">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="72a67-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="72a67-215">sip</span><span class="sxs-lookup"><span data-stu-id="72a67-215">sip</span></span>  <br/> |<span data-ttu-id="72a67-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="72a67-216">CNAME</span></span>  <br/> |<span data-ttu-id="72a67-217">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="72a67-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="72a67-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="72a67-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="72a67-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="72a67-220">CNAME</span></span>  <br/> |<span data-ttu-id="72a67-221">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="72a67-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="72a67-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="72a67-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="72a67-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="72a67-224">CNAME</span></span>  <br/> |<span data-ttu-id="72a67-225">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="72a67-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="72a67-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="72a67-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="72a67-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="72a67-228">CNAME</span></span>  <br/> |<span data-ttu-id="72a67-229">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="72a67-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="72a67-232">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="72a67-234">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72a67-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="72a67-235">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="72a67-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="72a67-236">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="72a67-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="72a67-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="72a67-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="72a67-238">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="72a67-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="72a67-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="72a67-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="72a67-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="72a67-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="72a67-241">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="72a67-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="72a67-242">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="72a67-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="72a67-243">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="72a67-243">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="72a67-245">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="72a67-247">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="72a67-249">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom wählen Sie Manage Freenom DNS aus.](../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="72a67-251">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **TXT** aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="72a67-253">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="72a67-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="72a67-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="72a67-254">**Name**</span></span>|<span data-ttu-id="72a67-255">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="72a67-255">**Record type**</span></span>|<span data-ttu-id="72a67-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="72a67-256">**TTL**</span></span>|<span data-ttu-id="72a67-257">**Target**</span><span class="sxs-lookup"><span data-stu-id="72a67-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="72a67-258">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="72a67-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="72a67-259">TXT</span><span class="sxs-lookup"><span data-stu-id="72a67-259">TXT</span></span>  <br/> |<span data-ttu-id="72a67-260">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="72a67-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="72a67-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="72a67-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="72a67-262">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="72a67-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="72a67-264">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="72a67-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

