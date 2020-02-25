---
title: Erstellen von DNS-Einträgen für Office 365 bei Hover
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Hover für Office 365 einrichten.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244996"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="a539c-103">Erstellen von DNS-Einträgen für Office 365 bei Hover</span><span class="sxs-lookup"><span data-stu-id="a539c-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="a539c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a539c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a539c-105">Wenn Hover Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a539c-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="a539c-106">Nachdem Sie diese Einträge bei Hover hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a539c-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a539c-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="a539c-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a539c-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a539c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a539c-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a539c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a539c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a539c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a539c-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="a539c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a539c-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="a539c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a539c-117">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a539c-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a539c-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a539c-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a539c-121">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a539c-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a539c-123">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-123">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a539c-125">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-125">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a539c-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a539c-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="a539c-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="a539c-128">Hostname</span></span>  <br/> |<span data-ttu-id="a539c-129">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="a539c-129">Record Type</span></span>  <br/> |<span data-ttu-id="a539c-130">Value</span><span class="sxs-lookup"><span data-stu-id="a539c-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="a539c-131">TXT</span><span class="sxs-lookup"><span data-stu-id="a539c-131">TXT</span></span>  <br/> |<span data-ttu-id="a539c-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a539c-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a539c-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a539c-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="a539c-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a539c-137">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="a539c-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a539c-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a539c-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a539c-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a539c-141">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="a539c-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a539c-142">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="a539c-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a539c-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a539c-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a539c-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a539c-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a539c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a539c-149">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="a539c-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a539c-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a539c-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a539c-151">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a539c-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a539c-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a539c-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a539c-155">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a539c-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a539c-157">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-157">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a539c-159">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-159">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a539c-161">Wählen Sie in den Feldern für den neuen Eintrag für **Record Type** die Option **MX** aus, und geben Sie dann die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a539c-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a539c-162">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a539c-162">**Hostname**</span></span>|<span data-ttu-id="a539c-163">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a539c-163">**Record Type**</span></span>|<span data-ttu-id="a539c-164">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="a539c-164">**Priority**</span></span>|<span data-ttu-id="a539c-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a539c-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a539c-166">MX</span><span class="sxs-lookup"><span data-stu-id="a539c-166">MX</span></span>  <br/> |<span data-ttu-id="a539c-167">0</span><span class="sxs-lookup"><span data-stu-id="a539c-167">0</span></span>  <br/> <span data-ttu-id="a539c-168">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a539c-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a539c-169">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a539c-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a539c-170">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="a539c-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="a539c-171">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="a539c-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="a539c-173">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a539c-173">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="a539c-175">Wenn andere MX-Einträge vorhanden sind, führen Sie die beiden folgenden Schritte aus, um diese zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="a539c-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="a539c-176">Klicken Sie zuerst auf einen Datensatz, den Sie entfernen möchten, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Maus über und wählen Sie löschen](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="a539c-178">Klicken Sie zweitens auf **Ja** , um den Löschvorgang zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="a539c-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Wählen Sie ja aus, um das Löschen zu bestätigen](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="a539c-180">Wiederholen Sie diesen Vorgang, bis Sie alle MX-Einträge mit Ausnahme des Eintrags, den Sie zuvor in diesem Verfahren hinzugefügt haben, gelöscht sind.</span><span class="sxs-lookup"><span data-stu-id="a539c-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a539c-181">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="a539c-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a539c-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a539c-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a539c-183">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a539c-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a539c-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a539c-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a539c-187">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a539c-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a539c-189">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-189">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a539c-191">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a539c-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a539c-192">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-192">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a539c-194">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **CNAME** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a539c-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a539c-195">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a539c-195">**Hostname**</span></span>|<span data-ttu-id="a539c-196">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a539c-196">**Record Type**</span></span>|<span data-ttu-id="a539c-197">**Zielhost**</span><span class="sxs-lookup"><span data-stu-id="a539c-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a539c-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a539c-198">autodiscover</span></span>  <br/> |<span data-ttu-id="a539c-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a539c-199">CNAME</span></span>  <br/> |<span data-ttu-id="a539c-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a539c-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a539c-201">sip</span><span class="sxs-lookup"><span data-stu-id="a539c-201">sip</span></span>  <br/> |<span data-ttu-id="a539c-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="a539c-202">CNAME</span></span>  <br/> |<span data-ttu-id="a539c-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a539c-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a539c-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a539c-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a539c-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="a539c-205">CNAME</span></span>  <br/> |<span data-ttu-id="a539c-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a539c-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a539c-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a539c-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a539c-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="a539c-208">CNAME</span></span>  <br/> |<span data-ttu-id="a539c-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a539c-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a539c-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a539c-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a539c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a539c-211">CNAME</span></span>  <br/> |<span data-ttu-id="a539c-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a539c-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="a539c-214">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a539c-214">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="a539c-216">Fügen Sie die anderen fünf CNAME-Einträge hinzu, indem Sie die vorangegangenen drei Schritte mit den Werten aus den anderen fünf Zeilen in der Tabelle wiederholen.</span><span class="sxs-lookup"><span data-stu-id="a539c-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a539c-217">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="a539c-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a539c-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a539c-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a539c-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="a539c-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a539c-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="a539c-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a539c-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a539c-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a539c-222">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a539c-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="a539c-223">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a539c-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a539c-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a539c-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a539c-227">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a539c-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a539c-229">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-229">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a539c-231">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-231">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a539c-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a539c-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a539c-234">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a539c-234">**Hostname**</span></span>|<span data-ttu-id="a539c-235">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a539c-235">**Record Type**</span></span>|<span data-ttu-id="a539c-236">**Value**</span><span class="sxs-lookup"><span data-stu-id="a539c-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a539c-237">TXT</span><span class="sxs-lookup"><span data-stu-id="a539c-237">TXT</span></span>  <br/> |<span data-ttu-id="a539c-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a539c-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="a539c-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="a539c-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="a539c-241">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a539c-241">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a539c-243">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="a539c-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a539c-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a539c-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a539c-245">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a539c-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a539c-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a539c-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="a539c-249">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a539c-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="a539c-251">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-251">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="a539c-253">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a539c-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a539c-254">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a539c-254">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="a539c-256">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **SRV** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a539c-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a539c-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="a539c-257">**Hostname**</span></span>|<span data-ttu-id="a539c-258">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a539c-258">**Record Type**</span></span>|<span data-ttu-id="a539c-259">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a539c-259">**Priority**</span></span>|<span data-ttu-id="a539c-260">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a539c-260">**Weight**</span></span>|<span data-ttu-id="a539c-261">**Port**</span><span class="sxs-lookup"><span data-stu-id="a539c-261">**Port**</span></span>|<span data-ttu-id="a539c-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="a539c-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a539c-263">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a539c-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="a539c-264">SRV</span><span class="sxs-lookup"><span data-stu-id="a539c-264">SRV</span></span>  <br/> |<span data-ttu-id="a539c-265">100</span><span class="sxs-lookup"><span data-stu-id="a539c-265">100</span></span>  <br/> |<span data-ttu-id="a539c-266">1</span><span class="sxs-lookup"><span data-stu-id="a539c-266">1</span></span>  <br/> |<span data-ttu-id="a539c-267">443</span><span class="sxs-lookup"><span data-stu-id="a539c-267">443</span></span>  <br/> |<span data-ttu-id="a539c-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a539c-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a539c-269">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a539c-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a539c-270">SRV</span><span class="sxs-lookup"><span data-stu-id="a539c-270">SRV</span></span>  <br/> |<span data-ttu-id="a539c-271">100</span><span class="sxs-lookup"><span data-stu-id="a539c-271">100</span></span>  <br/> |<span data-ttu-id="a539c-272">1</span><span class="sxs-lookup"><span data-stu-id="a539c-272">1</span></span>  <br/> |<span data-ttu-id="a539c-273">5061</span><span class="sxs-lookup"><span data-stu-id="a539c-273">5061</span></span>  <br/> |<span data-ttu-id="a539c-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a539c-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="a539c-276">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a539c-276">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="a539c-278">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die vorangegangenen drei Schritte mit den Werten aus der zweiten Zeile in der Tabelle wiederholen.</span><span class="sxs-lookup"><span data-stu-id="a539c-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a539c-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a539c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
