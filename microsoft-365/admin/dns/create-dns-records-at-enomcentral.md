---
title: Erstellen von DNS-Einträgen bei eNomCentral für Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter enomcentral für Microsoft einrichten.
ms.openlocfilehash: b43261c601b953eef7f98170f04b51d8dcf97d8d
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939271"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="83cc1-103">Erstellen von DNS-Einträgen bei eNomCentral für Microsoft</span><span class="sxs-lookup"><span data-stu-id="83cc1-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="83cc1-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="83cc1-105">Wenn "eNomCentral" Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="83cc1-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="83cc1-106">Nachdem Sie diese Einträge bei eNomCentral hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="83cc1-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="83cc1-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="83cc1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="83cc1-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="83cc1-110">Add a TXT record for verification</span></span>
<span data-ttu-id="83cc1-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="83cc1-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="83cc1-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83cc1-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="83cc1-116">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="83cc1-116">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="83cc1-p104">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="83cc1-120">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="83cc1-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="83cc1-122">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="83cc1-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="83cc1-124">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="83cc1-125">Wählen Sie in der Dropdownliste den Wert des **Datensatztyps** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="83cc1-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="83cc1-126">**Host Name**</span></span> <br/> |<span data-ttu-id="83cc1-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="83cc1-127">**Record Type**</span></span> <br/> |<span data-ttu-id="83cc1-128">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="83cc1-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="83cc1-129">TXT</span><span class="sxs-lookup"><span data-stu-id="83cc1-129">TXT</span></span>  <br/> |<span data-ttu-id="83cc1-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="83cc1-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="83cc1-131">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="83cc1-131">**Note:** This is an example.</span></span> <span data-ttu-id="83cc1-132">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="83cc1-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="83cc1-133">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="83cc1-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="83cc1-135">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-135">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="83cc1-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="83cc1-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="83cc1-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="83cc1-139">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="83cc1-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="83cc1-140">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="83cc1-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="83cc1-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="83cc1-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="83cc1-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="83cc1-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="83cc1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="83cc1-147">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="83cc1-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="83cc1-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="83cc1-149">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="83cc1-149">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="83cc1-p107">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="83cc1-153">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="83cc1-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="83cc1-155">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Email Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="83cc1-157">Wählen Sie in der Dropdownliste **Service Selection** die Option **User (MX)** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="83cc1-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="83cc1-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="83cc1-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="83cc1-160">**Host Name**</span></span>|<span data-ttu-id="83cc1-161">**Address**</span><span class="sxs-lookup"><span data-stu-id="83cc1-161">**Address**</span></span>|<span data-ttu-id="83cc1-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="83cc1-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="83cc1-163">*\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="83cc1-164">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="83cc1-165">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="83cc1-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="83cc1-166">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="83cc1-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="83cc1-167">10  </span><span class="sxs-lookup"><span data-stu-id="83cc1-167">10</span></span>  <br/> <span data-ttu-id="83cc1-168">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="83cc1-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="83cc1-170">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-170">Select **save**.</span></span>
    
    ![eNom-BP-configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="83cc1-172">Wenn bereits andere MX-Einträge vorhanden sind, aktivieren Sie die Kontrollkästchen für diese Einträge, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="83cc1-174">Wählen Sie **Delete checked**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="83cc1-176">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="83cc1-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="83cc1-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="83cc1-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="83cc1-178">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="83cc1-178">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="83cc1-p109">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="83cc1-182">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="83cc1-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="83cc1-184">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="83cc1-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="83cc1-186">Wählen Sie **neue Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-186">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="83cc1-188">Geben Sie in den Feldern für die sechs neuen Einträge die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="83cc1-189">Wählen Sie in der Dropdownliste den Wert des **Datensatztyps** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="83cc1-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="83cc1-190">**Host Name**</span></span>|<span data-ttu-id="83cc1-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="83cc1-191">**Record Type**</span></span>|<span data-ttu-id="83cc1-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="83cc1-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="83cc1-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="83cc1-193">autodiscover</span></span>  <br/> |<span data-ttu-id="83cc1-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="83cc1-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="83cc1-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="83cc1-196">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="83cc1-197">sip</span><span class="sxs-lookup"><span data-stu-id="83cc1-197">sip</span></span>  <br/> |<span data-ttu-id="83cc1-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="83cc1-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="83cc1-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="83cc1-200">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="83cc1-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="83cc1-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="83cc1-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="83cc1-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="83cc1-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="83cc1-204">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="83cc1-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="83cc1-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="83cc1-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="83cc1-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="83cc1-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="83cc1-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="83cc1-208">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="83cc1-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="83cc1-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="83cc1-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="83cc1-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="83cc1-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="83cc1-212">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="83cc1-213">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-213">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="83cc1-215">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="83cc1-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="83cc1-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="83cc1-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="83cc1-217">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="83cc1-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="83cc1-218">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="83cc1-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="83cc1-219">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="83cc1-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="83cc1-220">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="83cc1-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="83cc1-221">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="83cc1-221">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="83cc1-p111">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="83cc1-225">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="83cc1-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="83cc1-227">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="83cc1-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="83cc1-229">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="83cc1-230">Wählen Sie in der Dropdownliste den Wert des **Datensatztyps** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="83cc1-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="83cc1-231">**Host Name**</span></span>|<span data-ttu-id="83cc1-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="83cc1-232">**Record Type**</span></span>|<span data-ttu-id="83cc1-233">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="83cc1-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="83cc1-234">TXT</span><span class="sxs-lookup"><span data-stu-id="83cc1-234">TXT</span></span>  <br/> |<span data-ttu-id="83cc1-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="83cc1-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="83cc1-236">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="83cc1-238">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-238">Select **save**.</span></span>
    
    ![eNom-BP-configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="83cc1-240">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="83cc1-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="83cc1-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="83cc1-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="83cc1-242">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="83cc1-242">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="83cc1-p112">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83cc1-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="83cc1-246">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="83cc1-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="83cc1-248">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="83cc1-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="83cc1-250">Wählen Sie rechts neben **neue Zeile** **SRV oder SPF-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="83cc1-252">Geben Sie in die Felder für die zwei neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83cc1-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="83cc1-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="83cc1-253">**Service**</span></span>|<span data-ttu-id="83cc1-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="83cc1-254">**Protocol**</span></span>|<span data-ttu-id="83cc1-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="83cc1-255">**Priority**</span></span>|<span data-ttu-id="83cc1-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="83cc1-256">**Weight**</span></span>|<span data-ttu-id="83cc1-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="83cc1-257">**Port**</span></span>|<span data-ttu-id="83cc1-258">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="83cc1-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="83cc1-259">_sip</span><span class="sxs-lookup"><span data-stu-id="83cc1-259">_sip</span></span>  <br/> |<span data-ttu-id="83cc1-260">_tls</span><span class="sxs-lookup"><span data-stu-id="83cc1-260">_tls</span></span>  <br/> |<span data-ttu-id="83cc1-261">100</span><span class="sxs-lookup"><span data-stu-id="83cc1-261">100</span></span>  <br/> |<span data-ttu-id="83cc1-262">1</span><span class="sxs-lookup"><span data-stu-id="83cc1-262">1</span></span>  <br/> |<span data-ttu-id="83cc1-263">443</span><span class="sxs-lookup"><span data-stu-id="83cc1-263">443</span></span>  <br/> |<span data-ttu-id="83cc1-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="83cc1-265">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="83cc1-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="83cc1-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="83cc1-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="83cc1-267">_tcp</span></span>  <br/> |<span data-ttu-id="83cc1-268">100</span><span class="sxs-lookup"><span data-stu-id="83cc1-268">100</span></span>  <br/> |<span data-ttu-id="83cc1-269">1</span><span class="sxs-lookup"><span data-stu-id="83cc1-269">1</span></span>  <br/> |<span data-ttu-id="83cc1-270">5061</span><span class="sxs-lookup"><span data-stu-id="83cc1-270">5061</span></span>  <br/> |<span data-ttu-id="83cc1-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="83cc1-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="83cc1-272">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="83cc1-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="83cc1-274">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="83cc1-274">Select **save**</span></span>
    
    ![eNom-BP-configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="83cc1-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="83cc1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

