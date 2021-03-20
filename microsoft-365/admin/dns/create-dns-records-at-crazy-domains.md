---
title: Erstellen von DNS-Einträgen bei Crazy Domains für Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Crazy Domains for Microsoft einrichten.
ms.openlocfilehash: 425ecfa6f8b6c4085bdffb3d2701008ecb895b84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910462"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="7c40c-103">Erstellen von DNS-Einträgen bei Crazy Domains für Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c40c-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="7c40c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7c40c-105">Wenn Crazy Domains Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7c40c-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7c40c-106">Nachdem Sie diese Einträge bei Crazy Domains hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="7c40c-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="7c40c-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c40c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7c40c-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="7c40c-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7c40c-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7c40c-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7c40c-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c40c-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7c40c-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c40c-119">Wählen Sie **im Abschnitt Mein Konto** die Option Domänen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c40c-121">Wählen Sie **auf der** Seite Domänennamen im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7c40c-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c40c-123">Wählen Sie **im Abschnitt DNS-Einstellungen** das Dropdownlistensymbol aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c40c-125">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c40c-127">Wählen Sie in der Dropdownliste **Add Record** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="7c40c-129">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7c40c-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="7c40c-131">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7c40c-132">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c40c-132">**Sub Domain**</span></span>|<span data-ttu-id="7c40c-133">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="7c40c-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c40c-134">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="7c40c-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7c40c-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7c40c-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7c40c-136">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7c40c-136">**Note:** This is an example.</span></span> <span data-ttu-id="7c40c-137">Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7c40c-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7c40c-138">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="7c40c-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="7c40c-140">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="7c40c-142">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c40c-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7c40c-143">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="7c40c-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7c40c-144">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="7c40c-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7c40c-145">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="7c40c-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7c40c-146">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7c40c-147">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7c40c-148">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7c40c-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c40c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7c40c-152">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7c40c-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7c40c-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7c40c-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c40c-157">Wählen Sie **im Abschnitt Mein Konto** die Option Domänen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c40c-159">Wählen Sie **auf der** Seite Domänennamen im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7c40c-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c40c-161">Wählen Sie **im Abschnitt DNS-Einstellungen** das Dropdownlistensymbol aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c40c-163">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c40c-165">Wählen Sie in der Dropdownliste **Add Record:** den Eintrag **MX Record** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="7c40c-167">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7c40c-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="7c40c-169">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7c40c-170">(Wählen Sie den **Prioritätswert** aus der Dropdownliste aus.)</span><span class="sxs-lookup"><span data-stu-id="7c40c-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7c40c-171">**Mail For Zone**</span><span class="sxs-lookup"><span data-stu-id="7c40c-171">**Mail For Zone**</span></span>|<span data-ttu-id="7c40c-172">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7c40c-172">**Priority**</span></span>|<span data-ttu-id="7c40c-173">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="7c40c-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7c40c-174">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="7c40c-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7c40c-175">1</span><span class="sxs-lookup"><span data-stu-id="7c40c-175">1</span></span>  <br/> <span data-ttu-id="7c40c-176">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="7c40c-176">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="7c40c-177">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7c40c-178">**Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="7c40c-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="7c40c-179">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="7c40c-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="7c40c-181">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="7c40c-183">Wenn im Abschnitt MX **Record** weitere MX-Einträge aufgeführt sind, wählen Sie **Ändern für** einen dieser Einträge aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="7c40c-185">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="7c40c-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="7c40c-187">Wählen **Sie Aktualisieren** aus, um den Löschvorgang zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="7c40c-189">Wiederholen Sie diesen Vorgang, um alle anderen MX-Einträge aus der Liste zu entfernen, bis nur noch der Eintrag übrig ist, den Sie zuvor in diesem Verfahren hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="7c40c-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7c40c-190">Hinzufügen der für Microsoft erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="7c40c-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7c40c-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7c40c-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7c40c-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c40c-195">Wählen Sie **im Abschnitt Mein Konto** die Option Domänen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c40c-197">Wählen Sie **auf der** Seite Domänennamen im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7c40c-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c40c-199">Wählen Sie **im Abschnitt DNS-Einstellungen** das Dropdownlistensymbol aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c40c-201">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c40c-203">Wählen Sie in der Dropdownliste **Add Record** den Eintrag **CNAME Record** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="7c40c-205">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7c40c-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="7c40c-207">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c40c-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7c40c-208">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="7c40c-209">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c40c-209">**Sub Domain**</span></span>|<span data-ttu-id="7c40c-210">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="7c40c-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c40c-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7c40c-211">autodiscover</span></span>  <br/> |<span data-ttu-id="7c40c-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="7c40c-213">sip</span><span class="sxs-lookup"><span data-stu-id="7c40c-213">sip</span></span>  <br/> |<span data-ttu-id="7c40c-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7c40c-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7c40c-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7c40c-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7c40c-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7c40c-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7c40c-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7c40c-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="7c40c-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7c40c-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7c40c-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="7c40c-222">Wählen **Sie CNAME-Eintrag hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="7c40c-224">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c40c-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="7c40c-225">Verwenden Sie in den Feldern für den neuen Datensatz die Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **CNAME-Eintrag hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="7c40c-226">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7c40c-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="7c40c-227">Wählen **Sie Aktualisieren** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c40c-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7c40c-229">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="7c40c-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7c40c-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7c40c-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c40c-231">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="7c40c-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7c40c-232">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="7c40c-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7c40c-233">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="7c40c-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7c40c-234">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7c40c-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="7c40c-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c40c-238">Wählen Sie **im Abschnitt Mein Konto** die Option Domänen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c40c-240">Wählen Sie **auf der** Seite Domänennamen im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7c40c-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c40c-242">Wählen Sie **im Abschnitt DNS-Einstellungen** das Dropdownlistensymbol aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c40c-244">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c40c-246">Wählen Sie in der Dropdownliste **Add Record:** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="7c40c-248">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7c40c-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="7c40c-250">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7c40c-251">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c40c-251">**Sub Domain**</span></span>|<span data-ttu-id="7c40c-252">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="7c40c-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c40c-253">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="7c40c-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7c40c-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7c40c-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7c40c-255">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="7c40c-257">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7c40c-259">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="7c40c-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7c40c-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7c40c-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7c40c-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7c40c-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c40c-264">Wählen Sie **im Abschnitt Mein Konto** die Option Domänen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c40c-266">Wählen Sie **auf der** Seite Domänennamen im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7c40c-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c40c-268">Wählen Sie **im Abschnitt DNS-Einstellungen** das Dropdownlistensymbol aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c40c-270">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c40c-272">Wählen Sie in der Dropdownliste **Add Record:** den Eintrag **SRV Record** aus.</span><span class="sxs-lookup"><span data-stu-id="7c40c-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="7c40c-274">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7c40c-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="7c40c-276">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c40c-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7c40c-277">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7c40c-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="7c40c-278">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="7c40c-278">**Record Type**</span></span>|<span data-ttu-id="7c40c-279">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c40c-279">**Sub Domain**</span></span>|<span data-ttu-id="7c40c-280">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7c40c-280">**Priority**</span></span>|<span data-ttu-id="7c40c-281">**Weight**</span><span class="sxs-lookup"><span data-stu-id="7c40c-281">**Weight**</span></span>|<span data-ttu-id="7c40c-282">**Port**</span><span class="sxs-lookup"><span data-stu-id="7c40c-282">**Port**</span></span>|<span data-ttu-id="7c40c-283">**Target**</span><span class="sxs-lookup"><span data-stu-id="7c40c-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7c40c-284">SRV Record</span><span class="sxs-lookup"><span data-stu-id="7c40c-284">SRV Record</span></span>  <br/> |<span data-ttu-id="7c40c-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7c40c-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="7c40c-286">100</span><span class="sxs-lookup"><span data-stu-id="7c40c-286">100</span></span>  <br/> |<span data-ttu-id="7c40c-287">1</span><span class="sxs-lookup"><span data-stu-id="7c40c-287">1</span></span>  <br/> |<span data-ttu-id="7c40c-288">443</span><span class="sxs-lookup"><span data-stu-id="7c40c-288">443</span></span>  <br/> |<span data-ttu-id="7c40c-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7c40c-290">SRV Record</span><span class="sxs-lookup"><span data-stu-id="7c40c-290">SRV Record</span></span>  <br/> |<span data-ttu-id="7c40c-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7c40c-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7c40c-292">100</span><span class="sxs-lookup"><span data-stu-id="7c40c-292">100</span></span>  <br/> |<span data-ttu-id="7c40c-293">1</span><span class="sxs-lookup"><span data-stu-id="7c40c-293">1</span></span>  <br/> |<span data-ttu-id="7c40c-294">5061</span><span class="sxs-lookup"><span data-stu-id="7c40c-294">5061</span></span>  <br/> |<span data-ttu-id="7c40c-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c40c-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="7c40c-297">Wählen **Sie SRV-Eintrag hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="7c40c-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="7c40c-299">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c40c-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7c40c-300">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der zweiten Zeile der Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="7c40c-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="7c40c-301">Wählen **Sie Aktualisieren** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c40c-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="7c40c-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c40c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
