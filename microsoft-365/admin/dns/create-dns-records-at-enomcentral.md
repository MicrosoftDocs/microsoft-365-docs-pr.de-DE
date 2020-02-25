---
title: Erstellen von DNS-Einträgen für Office 365 bei eNomCentral
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter enomcentral für Office 365 einrichten.
ms.openlocfilehash: c4cd12667ebf945aa2f354ccfa0bad1688dc9863
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241124"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="636ef-103">Erstellen von DNS-Einträgen für Office 365 bei eNomCentral</span><span class="sxs-lookup"><span data-stu-id="636ef-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="636ef-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="636ef-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="636ef-105">Wenn "eNomCentral" Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="636ef-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="636ef-106">Nachdem Sie diese Einträge bei eNomCentral hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="636ef-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="636ef-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="636ef-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="636ef-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="636ef-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="636ef-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="636ef-111">Add a TXT record for verification</span></span>
<span data-ttu-id="636ef-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="636ef-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="636ef-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="636ef-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="636ef-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="636ef-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="636ef-117">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="636ef-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="636ef-p104">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="636ef-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="636ef-121">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="636ef-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="636ef-123">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="636ef-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="636ef-125">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="636ef-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="636ef-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="636ef-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="636ef-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="636ef-127">**Host Name**</span></span> <br/> |<span data-ttu-id="636ef-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="636ef-128">**Record Type**</span></span> <br/> |<span data-ttu-id="636ef-129">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="636ef-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="636ef-130">TXT</span><span class="sxs-lookup"><span data-stu-id="636ef-130">TXT</span></span>  <br/> |<span data-ttu-id="636ef-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="636ef-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="636ef-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="636ef-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![eNom-BP-Verify-1-2](../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="636ef-136">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-136">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="636ef-138">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="636ef-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="636ef-139">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="636ef-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="636ef-140">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="636ef-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="636ef-141">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="636ef-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="636ef-142">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="636ef-143">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="636ef-144">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="636ef-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="636ef-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="636ef-148">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="636ef-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="636ef-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="636ef-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="636ef-150">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="636ef-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="636ef-p107">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="636ef-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="636ef-154">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="636ef-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="636ef-156">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Email Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-configure-1-3](../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="636ef-158">Wählen Sie in der Dropdownliste **Service Selection** die Option **User (MX)** aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-configure-1-4](../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="636ef-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="636ef-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="636ef-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="636ef-161">**Host Name**</span></span>|<span data-ttu-id="636ef-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="636ef-162">**Address**</span></span>|<span data-ttu-id="636ef-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="636ef-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="636ef-164">*\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="636ef-165">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="636ef-166">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="636ef-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="636ef-167">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="636ef-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="636ef-168">10 </span><span class="sxs-lookup"><span data-stu-id="636ef-168">10</span></span>  <br/> <span data-ttu-id="636ef-169">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="636ef-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-configure-2-1](../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="636ef-171">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-171">Select **save**.</span></span>
    
    ![eNom-BP-configure-2-2](../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="636ef-173">Wenn bereits andere MX-Einträge vorhanden sind, aktivieren Sie die Kontrollkästchen für diese Einträge, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="636ef-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-configure-2-3](../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="636ef-175">Wählen Sie **Delete checked**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-configure-2-4](../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="636ef-177">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="636ef-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="636ef-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="636ef-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="636ef-179">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="636ef-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="636ef-p109">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="636ef-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="636ef-183">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="636ef-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="636ef-185">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="636ef-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="636ef-187">Wählen Sie **neue Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-187">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="636ef-189">Geben Sie in den Feldern für die sechs neuen Einträge die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="636ef-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="636ef-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="636ef-190">**Host Name**</span></span>|<span data-ttu-id="636ef-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="636ef-191">**Record Type**</span></span>|<span data-ttu-id="636ef-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="636ef-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="636ef-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="636ef-193">autodiscover</span></span>  <br/> |<span data-ttu-id="636ef-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="636ef-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="636ef-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="636ef-196">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="636ef-197">sip</span><span class="sxs-lookup"><span data-stu-id="636ef-197">sip</span></span>  <br/> |<span data-ttu-id="636ef-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="636ef-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="636ef-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="636ef-200">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="636ef-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="636ef-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="636ef-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="636ef-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="636ef-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="636ef-204">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="636ef-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="636ef-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="636ef-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="636ef-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="636ef-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="636ef-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="636ef-208">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="636ef-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="636ef-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="636ef-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="636ef-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="636ef-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="636ef-212">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-3-2](../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="636ef-214">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-214">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="636ef-216">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="636ef-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="636ef-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="636ef-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="636ef-218">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="636ef-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="636ef-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="636ef-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="636ef-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="636ef-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="636ef-221">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="636ef-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="636ef-222">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="636ef-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="636ef-p111">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="636ef-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="636ef-226">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="636ef-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="636ef-228">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="636ef-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="636ef-230">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="636ef-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="636ef-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="636ef-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="636ef-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="636ef-232">**Host Name**</span></span>|<span data-ttu-id="636ef-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="636ef-233">**Record Type**</span></span>|<span data-ttu-id="636ef-234">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="636ef-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="636ef-235">TXT</span><span class="sxs-lookup"><span data-stu-id="636ef-235">TXT</span></span>  <br/> |<span data-ttu-id="636ef-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="636ef-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="636ef-237">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="636ef-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-configure-4-1](../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="636ef-239">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-239">Select **save**.</span></span>
    
    ![eNom-BP-configure-4-2](../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="636ef-241">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="636ef-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="636ef-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="636ef-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="636ef-243">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="636ef-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="636ef-p112">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="636ef-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="636ef-247">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="636ef-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="636ef-249">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="636ef-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="636ef-251">Wählen Sie rechts neben **neue Zeile** **SRV oder SPF-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-configure-5-1](../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="636ef-253">Geben Sie in die Felder für die zwei neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="636ef-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="636ef-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="636ef-254">**Service**</span></span>|<span data-ttu-id="636ef-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="636ef-255">**Protocol**</span></span>|<span data-ttu-id="636ef-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="636ef-256">**Priority**</span></span>|<span data-ttu-id="636ef-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="636ef-257">**Weight**</span></span>|<span data-ttu-id="636ef-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="636ef-258">**Port**</span></span>|<span data-ttu-id="636ef-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="636ef-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="636ef-260">_sip</span><span class="sxs-lookup"><span data-stu-id="636ef-260">_sip</span></span>  <br/> |<span data-ttu-id="636ef-261">_tls</span><span class="sxs-lookup"><span data-stu-id="636ef-261">_tls</span></span>  <br/> |<span data-ttu-id="636ef-262">100</span><span class="sxs-lookup"><span data-stu-id="636ef-262">100</span></span>  <br/> |<span data-ttu-id="636ef-263">1</span><span class="sxs-lookup"><span data-stu-id="636ef-263">1</span></span>  <br/> |<span data-ttu-id="636ef-264">443</span><span class="sxs-lookup"><span data-stu-id="636ef-264">443</span></span>  <br/> |<span data-ttu-id="636ef-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="636ef-266">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="636ef-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="636ef-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="636ef-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="636ef-268">_tcp</span></span>  <br/> |<span data-ttu-id="636ef-269">100</span><span class="sxs-lookup"><span data-stu-id="636ef-269">100</span></span>  <br/> |<span data-ttu-id="636ef-270">1</span><span class="sxs-lookup"><span data-stu-id="636ef-270">1</span></span>  <br/> |<span data-ttu-id="636ef-271">5061</span><span class="sxs-lookup"><span data-stu-id="636ef-271">5061</span></span>  <br/> |<span data-ttu-id="636ef-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="636ef-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="636ef-273">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="636ef-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-5-2](../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="636ef-275">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="636ef-275">Select **save**</span></span>
    
    ![eNom-BP-configure-5-3](../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="636ef-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="636ef-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

