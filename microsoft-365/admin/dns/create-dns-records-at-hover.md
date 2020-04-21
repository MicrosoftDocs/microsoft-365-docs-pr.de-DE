---
title: Erstellen von DNS-Einträgen bei Hover für Microsoft
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Hover für Microsoft einrichten.
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629515"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="fdccc-103">Erstellen von DNS-Einträgen bei Hover für Microsoft</span><span class="sxs-lookup"><span data-stu-id="fdccc-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="fdccc-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fdccc-105">Wenn Hover Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fdccc-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="fdccc-106">Nachdem Sie diese Einträge bei Hover hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="fdccc-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="fdccc-107">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="fdccc-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="fdccc-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fdccc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fdccc-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fdccc-111">Add a TXT record for verification</span></span>
<span data-ttu-id="fdccc-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fdccc-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fdccc-113">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="fdccc-114">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fdccc-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="fdccc-117">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fdccc-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fdccc-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="fdccc-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fdccc-121">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="fdccc-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fdccc-123">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-123">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fdccc-125">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-125">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fdccc-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fdccc-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="fdccc-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="fdccc-128">Hostname</span></span>  <br/> |<span data-ttu-id="fdccc-129">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="fdccc-129">Record Type</span></span>  <br/> |<span data-ttu-id="fdccc-130">Value</span><span class="sxs-lookup"><span data-stu-id="fdccc-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="fdccc-131">TXT</span><span class="sxs-lookup"><span data-stu-id="fdccc-131">TXT</span></span>  <br/> |<span data-ttu-id="fdccc-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fdccc-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fdccc-133">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fdccc-133">**Note:** This is an example.</span></span> <span data-ttu-id="fdccc-134">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fdccc-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="fdccc-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="fdccc-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="fdccc-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdccc-137">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="fdccc-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fdccc-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fdccc-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="fdccc-141">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="fdccc-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fdccc-142">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="fdccc-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fdccc-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fdccc-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fdccc-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fdccc-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fdccc-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fdccc-149">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="fdccc-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fdccc-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fdccc-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="fdccc-151">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fdccc-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fdccc-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="fdccc-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fdccc-155">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="fdccc-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fdccc-157">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-157">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fdccc-159">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-159">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fdccc-161">Wählen Sie in den Feldern für den neuen Eintrag für **Record Type** die Option **MX** aus, und geben Sie dann die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fdccc-162">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="fdccc-162">**Hostname**</span></span>|<span data-ttu-id="fdccc-163">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="fdccc-163">**Record Type**</span></span>|<span data-ttu-id="fdccc-164">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="fdccc-164">**Priority**</span></span>|<span data-ttu-id="fdccc-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="fdccc-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fdccc-166">MX</span><span class="sxs-lookup"><span data-stu-id="fdccc-166">MX</span></span>  <br/> |<span data-ttu-id="fdccc-167">0</span><span class="sxs-lookup"><span data-stu-id="fdccc-167">0</span></span>  <br/> <span data-ttu-id="fdccc-168">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="fdccc-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="fdccc-169">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="fdccc-170">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="fdccc-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="fdccc-171">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="fdccc-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="fdccc-173">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdccc-173">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="fdccc-175">Wenn andere MX-Einträge vorhanden sind, führen Sie die beiden folgenden Schritte aus, um diese zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="fdccc-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="fdccc-176">Klicken Sie zuerst auf einen Datensatz, den Sie entfernen möchten, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Maus über und wählen Sie löschen](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="fdccc-178">Klicken Sie zweitens auf **Ja** , um den Löschvorgang zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Wählen Sie ja aus, um das Löschen zu bestätigen](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="fdccc-180">Wiederholen Sie diesen Vorgang, bis Sie alle MX-Einträge mit Ausnahme des Eintrags, den Sie zuvor in diesem Verfahren hinzugefügt haben, gelöscht sind.</span><span class="sxs-lookup"><span data-stu-id="fdccc-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fdccc-181">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="fdccc-181">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="fdccc-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fdccc-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="fdccc-183">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fdccc-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fdccc-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="fdccc-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fdccc-187">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="fdccc-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fdccc-189">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-189">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fdccc-191">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdccc-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="fdccc-192">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-192">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fdccc-194">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **CNAME** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="fdccc-195">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="fdccc-195">**Hostname**</span></span>|<span data-ttu-id="fdccc-196">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="fdccc-196">**Record Type**</span></span>|<span data-ttu-id="fdccc-197">**Zielhost**</span><span class="sxs-lookup"><span data-stu-id="fdccc-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fdccc-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fdccc-198">autodiscover</span></span>  <br/> |<span data-ttu-id="fdccc-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="fdccc-199">CNAME</span></span>  <br/> |<span data-ttu-id="fdccc-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="fdccc-201">sip</span><span class="sxs-lookup"><span data-stu-id="fdccc-201">sip</span></span>  <br/> |<span data-ttu-id="fdccc-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="fdccc-202">CNAME</span></span>  <br/> |<span data-ttu-id="fdccc-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fdccc-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fdccc-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fdccc-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="fdccc-205">CNAME</span></span>  <br/> |<span data-ttu-id="fdccc-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fdccc-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fdccc-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fdccc-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="fdccc-208">CNAME</span></span>  <br/> |<span data-ttu-id="fdccc-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fdccc-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="fdccc-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fdccc-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fdccc-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="fdccc-211">CNAME</span></span>  <br/> |<span data-ttu-id="fdccc-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="fdccc-214">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdccc-214">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="fdccc-216">Fügen Sie die anderen fünf CNAME-Einträge hinzu, indem Sie die vorangegangenen drei Schritte mit den Werten aus den anderen fünf Zeilen in der Tabelle wiederholen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fdccc-217">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="fdccc-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fdccc-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fdccc-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdccc-219">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="fdccc-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fdccc-220">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="fdccc-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fdccc-221">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fdccc-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fdccc-222">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="fdccc-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="fdccc-223">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fdccc-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fdccc-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="fdccc-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fdccc-227">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="fdccc-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fdccc-229">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-229">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fdccc-231">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-231">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fdccc-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fdccc-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fdccc-234">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="fdccc-234">**Hostname**</span></span>|<span data-ttu-id="fdccc-235">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="fdccc-235">**Record Type**</span></span>|<span data-ttu-id="fdccc-236">**Value**</span><span class="sxs-lookup"><span data-stu-id="fdccc-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fdccc-237">TXT</span><span class="sxs-lookup"><span data-stu-id="fdccc-237">TXT</span></span>  <br/> |<span data-ttu-id="fdccc-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fdccc-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="fdccc-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="fdccc-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="fdccc-241">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdccc-241">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fdccc-243">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fdccc-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fdccc-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fdccc-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="fdccc-245">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="fdccc-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fdccc-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.hover.com/domains) zu Ihrer Domänenseite bei Hover. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="fdccc-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="fdccc-249">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="fdccc-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="fdccc-251">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-251">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="fdccc-253">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdccc-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="fdccc-254">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fdccc-254">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="fdccc-256">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **SRV** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="fdccc-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="fdccc-257">**Hostname**</span></span>|<span data-ttu-id="fdccc-258">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="fdccc-258">**Record Type**</span></span>|<span data-ttu-id="fdccc-259">**Priority**</span><span class="sxs-lookup"><span data-stu-id="fdccc-259">**Priority**</span></span>|<span data-ttu-id="fdccc-260">**Weight**</span><span class="sxs-lookup"><span data-stu-id="fdccc-260">**Weight**</span></span>|<span data-ttu-id="fdccc-261">**Port**</span><span class="sxs-lookup"><span data-stu-id="fdccc-261">**Port**</span></span>|<span data-ttu-id="fdccc-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="fdccc-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fdccc-263">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="fdccc-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="fdccc-264">SRV</span><span class="sxs-lookup"><span data-stu-id="fdccc-264">SRV</span></span>  <br/> |<span data-ttu-id="fdccc-265">100</span><span class="sxs-lookup"><span data-stu-id="fdccc-265">100</span></span>  <br/> |<span data-ttu-id="fdccc-266">1</span><span class="sxs-lookup"><span data-stu-id="fdccc-266">1</span></span>  <br/> |<span data-ttu-id="fdccc-267">443</span><span class="sxs-lookup"><span data-stu-id="fdccc-267">443</span></span>  <br/> |<span data-ttu-id="fdccc-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fdccc-269">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="fdccc-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="fdccc-270">SRV</span><span class="sxs-lookup"><span data-stu-id="fdccc-270">SRV</span></span>  <br/> |<span data-ttu-id="fdccc-271">100</span><span class="sxs-lookup"><span data-stu-id="fdccc-271">100</span></span>  <br/> |<span data-ttu-id="fdccc-272">1</span><span class="sxs-lookup"><span data-stu-id="fdccc-272">1</span></span>  <br/> |<span data-ttu-id="fdccc-273">5061</span><span class="sxs-lookup"><span data-stu-id="fdccc-273">5061</span></span>  <br/> |<span data-ttu-id="fdccc-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fdccc-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="fdccc-276">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdccc-276">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="fdccc-278">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die vorangegangenen drei Schritte mit den Werten aus der zweiten Zeile in der Tabelle wiederholen.</span><span class="sxs-lookup"><span data-stu-id="fdccc-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fdccc-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fdccc-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
