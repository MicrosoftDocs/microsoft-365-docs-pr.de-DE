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
ms.openlocfilehash: 33231896b69c0883bc9af3153fa57533096a1a0f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629575"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="65a4c-103">Erstellen von DNS-Einträgen bei eNomCentral für Microsoft</span><span class="sxs-lookup"><span data-stu-id="65a4c-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="65a4c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="65a4c-105">Wenn "eNomCentral" Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="65a4c-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="65a4c-106">Nachdem Sie diese Einträge bei eNomCentral hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="65a4c-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="65a4c-107">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="65a4c-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="65a4c-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="65a4c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="65a4c-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="65a4c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="65a4c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="65a4c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="65a4c-113">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="65a4c-114">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="65a4c-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="65a4c-117">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="65a4c-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="65a4c-p104">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="65a4c-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="65a4c-121">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="65a4c-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="65a4c-123">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="65a4c-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="65a4c-125">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="65a4c-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="65a4c-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="65a4c-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="65a4c-127">**Host Name**</span></span> <br/> |<span data-ttu-id="65a4c-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="65a4c-128">**Record Type**</span></span> <br/> |<span data-ttu-id="65a4c-129">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="65a4c-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="65a4c-130">TXT</span><span class="sxs-lookup"><span data-stu-id="65a4c-130">TXT</span></span>  <br/> |<span data-ttu-id="65a4c-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="65a4c-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="65a4c-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="65a4c-132">**Note:** This is an example.</span></span> <span data-ttu-id="65a4c-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="65a4c-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="65a4c-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="65a4c-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="65a4c-136">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-136">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="65a4c-138">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="65a4c-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="65a4c-139">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="65a4c-140">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="65a4c-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="65a4c-141">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="65a4c-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="65a4c-142">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="65a4c-143">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="65a4c-144">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="65a4c-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="65a4c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="65a4c-148">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="65a4c-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="65a4c-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="65a4c-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="65a4c-150">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="65a4c-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="65a4c-p107">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="65a4c-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="65a4c-154">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="65a4c-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="65a4c-156">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Email Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="65a4c-158">Wählen Sie in der Dropdownliste **Service Selection** die Option **User (MX)** aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="65a4c-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="65a4c-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="65a4c-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="65a4c-161">**Host Name**</span></span>|<span data-ttu-id="65a4c-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="65a4c-162">**Address**</span></span>|<span data-ttu-id="65a4c-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="65a4c-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="65a4c-164">*\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="65a4c-165">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="65a4c-166">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="65a4c-166">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="65a4c-167">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="65a4c-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="65a4c-168">10  </span><span class="sxs-lookup"><span data-stu-id="65a4c-168">10</span></span>  <br/> <span data-ttu-id="65a4c-169">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="65a4c-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="65a4c-171">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-171">Select **save**.</span></span>
    
    ![eNom-BP-configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="65a4c-173">Wenn bereits andere MX-Einträge vorhanden sind, aktivieren Sie die Kontrollkästchen für diese Einträge, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="65a4c-175">Wählen Sie **Delete checked**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="65a4c-177">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="65a4c-177">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="65a4c-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="65a4c-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="65a4c-179">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="65a4c-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="65a4c-p109">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="65a4c-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="65a4c-183">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="65a4c-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="65a4c-185">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="65a4c-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="65a4c-187">Wählen Sie **neue Zeile**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-187">Select **new row**.</span></span>
    
    ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="65a4c-189">Geben Sie in den Feldern für die sechs neuen Einträge die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="65a4c-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="65a4c-190">**Host Name**</span></span>|<span data-ttu-id="65a4c-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="65a4c-191">**Record Type**</span></span>|<span data-ttu-id="65a4c-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="65a4c-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="65a4c-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="65a4c-193">autodiscover</span></span>  <br/> |<span data-ttu-id="65a4c-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="65a4c-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="65a4c-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="65a4c-196">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="65a4c-197">sip</span><span class="sxs-lookup"><span data-stu-id="65a4c-197">sip</span></span>  <br/> |<span data-ttu-id="65a4c-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="65a4c-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="65a4c-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="65a4c-200">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="65a4c-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="65a4c-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="65a4c-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="65a4c-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="65a4c-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="65a4c-204">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="65a4c-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="65a4c-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="65a4c-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="65a4c-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="65a4c-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="65a4c-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="65a4c-208">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="65a4c-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="65a4c-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="65a4c-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="65a4c-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="65a4c-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="65a4c-212">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="65a4c-214">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-214">Select **save**.</span></span>
    
    ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="65a4c-216">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="65a4c-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="65a4c-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="65a4c-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65a4c-218">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="65a4c-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="65a4c-219">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="65a4c-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="65a4c-220">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="65a4c-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="65a4c-221">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="65a4c-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="65a4c-222">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="65a4c-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="65a4c-p111">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="65a4c-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="65a4c-226">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="65a4c-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="65a4c-228">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="65a4c-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="65a4c-230">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="65a4c-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="65a4c-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="65a4c-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="65a4c-232">**Host Name**</span></span>|<span data-ttu-id="65a4c-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="65a4c-233">**Record Type**</span></span>|<span data-ttu-id="65a4c-234">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="65a4c-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="65a4c-235">TXT</span><span class="sxs-lookup"><span data-stu-id="65a4c-235">TXT</span></span>  <br/> |<span data-ttu-id="65a4c-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="65a4c-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="65a4c-237">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="65a4c-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="65a4c-239">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-239">Select **save**.</span></span>
    
    ![eNom-BP-configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="65a4c-241">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="65a4c-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="65a4c-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="65a4c-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="65a4c-243">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="65a4c-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="65a4c-p112">Im ersten Schritt navigieren Sie über [diesen Link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) zu Ihrer Domänenseite bei eNom Central. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="65a4c-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="65a4c-247">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="65a4c-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="65a4c-249">Wählen Sie in der Dropdownliste **Manage Domain** den Eintrag **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="65a4c-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="65a4c-251">Wählen Sie rechts neben **neue Zeile** **SRV oder SPF-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="65a4c-253">Geben Sie in die Felder für die zwei neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="65a4c-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="65a4c-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="65a4c-254">**Service**</span></span>|<span data-ttu-id="65a4c-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="65a4c-255">**Protocol**</span></span>|<span data-ttu-id="65a4c-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="65a4c-256">**Priority**</span></span>|<span data-ttu-id="65a4c-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="65a4c-257">**Weight**</span></span>|<span data-ttu-id="65a4c-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="65a4c-258">**Port**</span></span>|<span data-ttu-id="65a4c-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="65a4c-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="65a4c-260">_sip</span><span class="sxs-lookup"><span data-stu-id="65a4c-260">_sip</span></span>  <br/> |<span data-ttu-id="65a4c-261">_tls</span><span class="sxs-lookup"><span data-stu-id="65a4c-261">_tls</span></span>  <br/> |<span data-ttu-id="65a4c-262">100</span><span class="sxs-lookup"><span data-stu-id="65a4c-262">100</span></span>  <br/> |<span data-ttu-id="65a4c-263">1</span><span class="sxs-lookup"><span data-stu-id="65a4c-263">1</span></span>  <br/> |<span data-ttu-id="65a4c-264">443</span><span class="sxs-lookup"><span data-stu-id="65a4c-264">443</span></span>  <br/> |<span data-ttu-id="65a4c-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="65a4c-266">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="65a4c-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="65a4c-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="65a4c-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="65a4c-268">_tcp</span></span>  <br/> |<span data-ttu-id="65a4c-269">100</span><span class="sxs-lookup"><span data-stu-id="65a4c-269">100</span></span>  <br/> |<span data-ttu-id="65a4c-270">1</span><span class="sxs-lookup"><span data-stu-id="65a4c-270">1</span></span>  <br/> |<span data-ttu-id="65a4c-271">5061</span><span class="sxs-lookup"><span data-stu-id="65a4c-271">5061</span></span>  <br/> |<span data-ttu-id="65a4c-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="65a4c-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="65a4c-273">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="65a4c-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="65a4c-275">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="65a4c-275">Select **save**</span></span>
    
    ![eNom-BP-configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="65a4c-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="65a4c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

