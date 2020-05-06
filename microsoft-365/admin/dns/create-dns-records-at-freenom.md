---
title: Erstellen von DNS-Einträgen bei Freenom für Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Freenom für Microsoft einrichten.
ms.openlocfilehash: 39963b5c0f5f3f82fe193160e8aa8ab03894cedd
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049035"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="6cd19-103">Erstellen von DNS-Einträgen bei Freenom für Microsoft</span><span class="sxs-lookup"><span data-stu-id="6cd19-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="6cd19-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="6cd19-105">Die Freenom-Website unterstützt keine SRV-Einträge, was bedeutet, dass mehrere Skype for Business Online und Outlook Web App Funktionen nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6cd19-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="6cd19-106">Unabhängig davon, welchen Microsoft-Plan Sie verwenden, gibt es erhebliche Diensteinschränkungen, und Sie möchten möglicherweise zu einem anderen DNS-Hostanbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="6cd19-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="6cd19-107">Wenn Sie trotz der Diensteinschränkungen ihre eigenen Microsoft-DNS-Einträge bei Freenom verwalten möchten, befolgen Sie die Schritte in diesem Artikel, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6cd19-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="6cd19-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6cd19-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6cd19-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="6cd19-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6cd19-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="6cd19-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="6cd19-p103">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="6cd19-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cd19-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6cd19-117">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="6cd19-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="6cd19-118">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6cd19-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="6cd19-120">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="6cd19-122">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="6cd19-124">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="6cd19-126">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **TXT** aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="6cd19-128">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="6cd19-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="6cd19-129">**Name**</span></span>|<span data-ttu-id="6cd19-130">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6cd19-130">**Type**</span></span>|<span data-ttu-id="6cd19-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cd19-131">**TTL**</span></span>|<span data-ttu-id="6cd19-132">**Target**</span><span class="sxs-lookup"><span data-stu-id="6cd19-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cd19-133">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="6cd19-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="6cd19-134">TXT</span><span class="sxs-lookup"><span data-stu-id="6cd19-134">TXT</span></span>  <br/> |<span data-ttu-id="6cd19-135">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-136">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="6cd19-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="6cd19-137">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6cd19-137">**Note:** This is an example.</span></span> <span data-ttu-id="6cd19-138">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6cd19-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6cd19-139">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="6cd19-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="6cd19-141">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="6cd19-143">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6cd19-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6cd19-144">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="6cd19-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6cd19-145">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="6cd19-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6cd19-146">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="6cd19-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6cd19-147">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6cd19-148">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6cd19-149">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6cd19-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6cd19-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6cd19-153">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="6cd19-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6cd19-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="6cd19-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="6cd19-155">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="6cd19-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="6cd19-156">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6cd19-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="6cd19-158">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="6cd19-160">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="6cd19-162">Legen Sie den Namen dient für Ihre Domäne auf die standardmäßigen Freenom Namenserver.</span><span class="sxs-lookup"><span data-stu-id="6cd19-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="6cd19-163">Wählen Sie **Verwaltungs Tools**aus, und wählen Sie dann Namen **Server**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="6cd19-165">Stellen Sie sicher, dass **Standardnamen Server verwenden** ausgewählt ist, und wählen Sie dann Namen von Namen **Servern ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="6cd19-167">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom wählen Sie Manage Freenom DNS aus.](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="6cd19-169">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **MX** aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="6cd19-171">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="6cd19-172">**Name**</span><span class="sxs-lookup"><span data-stu-id="6cd19-172">**Name**</span></span>|<span data-ttu-id="6cd19-173">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6cd19-173">**Type**</span></span>|<span data-ttu-id="6cd19-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cd19-174">**TTL**</span></span>|<span data-ttu-id="6cd19-175">**Target**</span><span class="sxs-lookup"><span data-stu-id="6cd19-175">**Target**</span></span>|<span data-ttu-id="6cd19-176">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="6cd19-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cd19-177">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="6cd19-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="6cd19-178">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="6cd19-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="6cd19-179">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-180">\<Domain-Key\>. Mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="6cd19-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6cd19-181">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="6cd19-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="6cd19-182">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="6cd19-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6cd19-183">10  </span><span class="sxs-lookup"><span data-stu-id="6cd19-183">10</span></span>  <br/> <span data-ttu-id="6cd19-184">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="6cd19-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="6cd19-186">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="6cd19-188">Wenn es weitere MX-Einträge gibt, löschen Sie sie alle: Wählen Sie für jeden Eintrag Delete (Löschen) aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="6cd19-189">Wählen Sie für jeden Datensatz **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-189">For each record, select **Delete**.</span></span> <span data-ttu-id="6cd19-190">Wenn die Nachricht möchten **Sie diesen Eintrag wirklich entfernen?** angezeigt wird, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd19-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6cd19-191">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="6cd19-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6cd19-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="6cd19-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="6cd19-193">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="6cd19-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="6cd19-194">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6cd19-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="6cd19-196">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="6cd19-198">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="6cd19-200">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom wählen Sie Manage Freenom DNS aus.](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="6cd19-202">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **SNAME** aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="6cd19-p113">Erstellen Sie den ersten CNAME-Eintrag. Geben Sie dann in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="6cd19-206">**Name**</span><span class="sxs-lookup"><span data-stu-id="6cd19-206">**Name**</span></span>|<span data-ttu-id="6cd19-207">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="6cd19-207">**Record type**</span></span>|<span data-ttu-id="6cd19-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cd19-208">**TTL**</span></span>|<span data-ttu-id="6cd19-209">**Target**</span><span class="sxs-lookup"><span data-stu-id="6cd19-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cd19-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6cd19-210">autodiscover</span></span>  <br/> |<span data-ttu-id="6cd19-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cd19-211">CNAME</span></span>  <br/> |<span data-ttu-id="6cd19-212">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6cd19-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6cd19-214">sip</span><span class="sxs-lookup"><span data-stu-id="6cd19-214">sip</span></span>  <br/> |<span data-ttu-id="6cd19-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cd19-215">CNAME</span></span>  <br/> |<span data-ttu-id="6cd19-216">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6cd19-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6cd19-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6cd19-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6cd19-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cd19-219">CNAME</span></span>  <br/> |<span data-ttu-id="6cd19-220">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6cd19-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6cd19-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6cd19-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6cd19-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cd19-223">CNAME</span></span>  <br/> |<span data-ttu-id="6cd19-224">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6cd19-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6cd19-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6cd19-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6cd19-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="6cd19-227">CNAME</span></span>  <br/> |<span data-ttu-id="6cd19-228">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6cd19-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="6cd19-231">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="6cd19-233">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="6cd19-234">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6cd19-235">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="6cd19-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6cd19-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="6cd19-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cd19-237">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="6cd19-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6cd19-238">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="6cd19-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6cd19-239">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="6cd19-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6cd19-240">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="6cd19-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="6cd19-241">Um zu beginnen, navigieren Sie über [diesen Link](https://my.freenom.com/)zu ihrer Domänen Seite in Freenom.</span><span class="sxs-lookup"><span data-stu-id="6cd19-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="6cd19-242">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6cd19-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="6cd19-244">Wählen Sie **Dienste**aus, und wählen Sie dann **Meine Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="6cd19-246">Wählen Sie für die Domäne, die Sie bearbeiten möchten, die Option **Domäne verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="6cd19-248">Wählen Sie **Freenom DNS verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom wählen Sie Manage Freenom DNS aus.](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="6cd19-250">Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **TXT** aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="6cd19-252">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6cd19-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="6cd19-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="6cd19-253">**Name**</span></span>|<span data-ttu-id="6cd19-254">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="6cd19-254">**Record type**</span></span>|<span data-ttu-id="6cd19-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6cd19-255">**TTL**</span></span>|<span data-ttu-id="6cd19-256">**Target**</span><span class="sxs-lookup"><span data-stu-id="6cd19-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6cd19-257">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="6cd19-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="6cd19-258">TXT</span><span class="sxs-lookup"><span data-stu-id="6cd19-258">TXT</span></span>  <br/> |<span data-ttu-id="6cd19-259">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="6cd19-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="6cd19-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6cd19-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="6cd19-261">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="6cd19-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="6cd19-263">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="6cd19-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

